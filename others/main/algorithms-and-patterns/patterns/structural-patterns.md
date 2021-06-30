# Structural patterns

## Adapter

The _Adapter_ pattern translates one interface \(an object‘s properties and methods\) to another. Adapters allows programming components to work together that otherwise wouldn't because of mismatched interfaces. The Adapter pattern is also referred to as the Wrapper Pattern

One scenario where Adapters are commonly used is when new components need to be integrated and work together with existing components in the application.

Another scenario is refactoring in which parts of the program are rewritten with an improved interface, but the old code still expects the original interface.

![Diagram of Adapter](../../../../.gitbook/assets/image%20%2848%29.png)

The example code below shows an online shopping cart in which a shipping object is used to compute shipping costs. The old `Shipping` object is replaced by a new and improved Shipping object that is more secure and offers better prices.

The new object is named `AdvancedShipping` and has a very different interface which the client program does not expect. `ShippingAdapter` allows the client program to continue functioning without any API changes by mapping \(adapting\) the old `Shipping` interface to the new `AdvancedShipping` interface.  


```javascript
// old interface

function Shipping() {
    this.request = function (zipStart, zipEnd, weight) {
        // ...
        return "$49.75";
    }
}

// new interface

function AdvancedShipping() {
    this.login = function (credentials) { /* ... */ };
    this.setStart = function (start) { /* ... */ };
    this.setDestination = function (destination) { /* ... */ };
    this.calculate = function (weight) { return "$39.50"; };
}

// adapter interface

function ShippingAdapter(credentials) {
    var shipping = new AdvancedShipping();

    shipping.login(credentials);

    return {
        request: function (zipStart, zipEnd, weight) {
            shipping.setStart(zipStart);
            shipping.setDestination(zipEnd);
            return shipping.calculate(weight);
        }
    };
}

function run() {

    var shipping = new Shipping();
    var credentials = { token: "30a8-6ee1" };
    var adapter = new ShippingAdapter(credentials);

    // original shipping object and interface

    var cost = shipping.request("78701", "10010", "2 lbs");
    console.log("Old cost: " + cost);

    // new shipping object with adapted interface

    cost = adapter.request("78701", "10010", "2 lbs");

    console.log("New cost: " + cost);
}
```



