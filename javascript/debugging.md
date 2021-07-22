# Debugging

## What is debugging?

Debugging is the process of detecting and removing of existing and potential errors \(also called as ‘bugs’\) in a software code that can cause it to behave unexpectedly or crash.

Debugging allows us to stop the execution of the code, and go step by step to see what the code is doing in every line.

## How to debug?

We can debug in the client or in the server:

### Client side

In the client side, we can debug with the builtin debugger of the browser, we can stop the execution by putting a `debugger` in the source code or a breakpoint

![Example of a breakpoint](../.gitbook/assets/image%20%2858%29.png)

Once we put the breakpoint, the execution will stop in this line, and we'll be able to move in the code and see the variables at this time, even if they're not setted in this moment.

![Example of a stopped execution](../.gitbook/assets/image%20%2860%29.png)

![Commands in the debugger](../.gitbook/assets/image%20%2871%29.png)

This bar will be our way to move along the code.



![](../.gitbook/assets/image%20%2877%29.png)

This one will continue the execution to the next breakpoint or will execute all the code if there wasn't breakpoints.

![](../.gitbook/assets/image%20%2874%29.png)

This icon will step to the next function call, not entering in this function, this one will only execute the function and jump to the next one.

![](../.gitbook/assets/image%20%2876%29.png)

This arrow will enter in the function, and we'll be able to see every step that the function has to do.

![](../.gitbook/assets/image%20%2880%29.png)

This one will 'step out' of the function, if we've entered in a very long function with this one we can escape from it.

![](../.gitbook/assets/image%20%2878%29.png)

This one will jump to the next line, no matter what function come next.



In the IDE will be the same,

![](../.gitbook/assets/image%20%2873%29.png)

