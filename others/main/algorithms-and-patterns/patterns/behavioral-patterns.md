# Behavioral patterns

## Strategy

The _Strategy_ pattern encapsulates alternative algorithms \(or strategies\) for a particular task. It allows a method to be swapped out at runtime by any other method \(strategy\) without the client realizing it. Essentially, Strategy is a group of algorithms that are interchangeable.

Say we like to test the performance of different sorting algorithms to an array of numbers: shell sort, heap sort, bubble sort, quicksort, etc. Applying the Strategy pattern to these algorithms allows the test program to loop through all algorithms, simply by changing them at runtime and test each of these against the array. For Strategy to work all method signatures must be the same so that they can vary without the client program knowing about it.

In JavaScript the Strategy pattern is widely used as a plug-in mechanism when building extensible frameworks. This can be a very effective approach.

![Diagram of strategy](../../../../.gitbook/assets/image%20%2845%29.png)

In this example we have a product order that needs to be shipped from a warehouse to a customer. Different shipping companies are evaluated to determine the best price. This can be useful with shopping carts where customers select their shipping preferences and the selected Strategy returns the estimated cost.

`Shipping` is the Context and the 3 shipping companies `UPS`, `USPS`, and `Fedex` are the Strategies. The shipping companies \(strategies\) are changed 3 times and each time we calculate the cost of shipping. In a real-world scenario the calculate methods may call into the shipper's Web service. At the end we display the different costs.

```javascript
var Shipping = function () {
    this.company = "";
};

Shipping.prototype = {
    setStrategy: function (company) {
        this.company = company;
    },

    calculate: function (package) {
        return this.company.calculate(package);
    }
};

var UPS = function () {
    this.calculate = function (package) {
        // calculations...
        return "$45.95";
    }
};

var USPS = function () {
    this.calculate = function (package) {
        // calculations...
        return "$39.40";
    }
};

var Fedex = function () {
    this.calculate = function (package) {
        // calculations...
        return "$43.20";
    }
};

function run() {

    var package = { from: "76712", to: "10012", weigth: "lkg" };

    // the 3 strategies

    var ups = new UPS();
    var usps = new USPS();
    var fedex = new Fedex();

    var shipping = new Shipping();

    shipping.setStrategy(ups);
    console.log("UPS Strategy: " + shipping.calculate(package));
    shipping.setStrategy(usps);
    console.log("USPS Strategy: " + shipping.calculate(package));
    shipping.setStrategy(fedex);
    console.log("Fedex Strategy: " + shipping.calculate(package));
}
```

## Observer

The _Observer_ pattern offers a subscription model in which objects subscribe to an event and get notified when the event occurs. This pattern is the cornerstone of event driven programming, including JavaScript. The Observer pattern facilitates good object-oriented design and promotes loose coupling.

When building web apps you end up writing many event handlers. Event handlers are functions that will be notified when a certain event fires. These notifications optionally receive an event argument with details about the event \(for example the x and y position of the mouse at a click event\).

The event and event-handler paradigm in JavaScript is the manifestation of the Observer design pattern. Another name for the Observer pattern is Pub/Sub, short for Publication/Subscription.

![Diagram for Observer](../../../../.gitbook/assets/image%20%2839%29.png)

The `Click` object represents the Subject. The `clickHandler` function is the subscribing Observer. This handler subscribes, unsubscribes, and then subscribes itself while events are firing. It gets notified only of events \#1 and \#3.

Notice that the `fire` method accepts two arguments. The first one has details about the event and the second one is the context, that is, the `this` value for when the eventhandlers are called. If no context is provided `this` will be bound to the global object \(window\).

```javascript
function Click() {
    this.handlers = [];  // observers
}

Click.prototype = {

    subscribe: function (fn) {
        this.handlers.push(fn);
    },

    unsubscribe: function (fn) {
        this.handlers = this.handlers.filter(
            function (item) {
                if (item !== fn) {
                    return item;
                }
            }
        );
    },

    fire: function (o, thisObj) {
        var scope = thisObj || window;
        this.handlers.forEach(function (item) {
            item.call(scope, o);
        });
    }
}

function run() {

    var clickHandler = function (item) {
        console.log("fired: " + item);
    };

    var click = new Click();

    click.subscribe(clickHandler);
    click.fire('event #1');
    click.unsubscribe(clickHandler);
    click.fire('event #2');
    click.subscribe(clickHandler);
    click.fire('event #3');
}
```

## State

The _State_ pattern provides state-specific logic to a limited set of objects in which each object represents a particular state.

Say a customer places an online order for a TV. While this order is being processed it can in one of many states: New, Approved, Packed, Pending, Hold, Shipping, Completed, or Canceled. If all goes well the sequence will be New, Approved, Packed, Shipped, and Completed. However, at any point something unpredictable may happen, such as no inventory, breakage, or customer cancelation. If that happens the order needs to be handled appropriately.

Applying the State pattern to this scenario will provide you with 8 State objects, each with its own set of properties \(state\) and methods \(i.e. the rules of acceptable state transitions\). State machines are often implemented using the State pattern. These state machines simply have their State objects swapped out with another one when a state transition takes place.

Two other examples where the State pattern is useful include: vending machines that dispense products when a correct combination of coins is entered, and elevator logic which moves riders up or down depending on certain complex rules that attempt to minimize wait and ride times.

![Diagram for State](../../../../.gitbook/assets/image%20%2842%29.png)

Our example is a traffic light \(i.e. `TrafficLight` object\) with 3 different states: `Red`, `Yellow` and `Green`, each with its own set of rules. The rules go like this: Say the traffic light is Red. After a delay the Red state changes to the Green state. Then, after another delay, the Green state changes to the Yellow state. After a very brief delay the Yellow state is changed to Red. And on and on.

It is important to note that it is the State object that determines the transition to the next state. And it is also the State object that changes the current state in the TrafficLight -- not the TrafficLight itself.

For demonstration purposes, a built-in counter limits the number of state changes, or else the program would run indefinitely.

```javascript
var TrafficLight = function () {
    var count = 0;
    var currentState = new Red(this);

    this.change = function (state) {
        // limits number of changes
        if (count++ >= 10) return;
        currentState = state;
        currentState.go();
    };

    this.start = function () {
        currentState.go();
    };
}

var Red = function (light) {
    this.light = light;

    this.go = function () {
        console.log("Red --> for 1 minute");
        light.change(new Green(light));
    }
};

var Yellow = function (light) {
    this.light = light;

    this.go = function () {
        console.log("Yellow --> for 10 seconds");
        light.change(new Red(light));
    }
};

var Green = function (light) {
    this.light = light;

    this.go = function () {
        console.log("Green --> for 1 minute");
        light.change(new Yellow(light));
    }
};

function run() {

    var light = new TrafficLight();
    light.start();
}

```

