# Minification and Obfuscation

## Minification

It's the process of removing unnecessary or redundant data without affecting how the resource is processed by the browser. Eg. Remove comments, format, shorter variables names, etc. Thanks to minify we can improve the site speed and the accesibility.

```javascript
    // return random number between 1 and 6
function dieToss() {
  return Math.floor(Math.random() * 6) + 1;  
}
// function returns a promise that succeeds if a 6 is tossed
function tossASix() {
  return new RSVP.Promise(function(fulfill, reject) {
    var number = Math.floor(Math.random() * 6) + 1;
    if (number === 6) {
      fulfill(number);
    } else {
      reject(number);
    }
  });
}
// display toss result and launch another toss
function logAndTossAgain(toss) {
  console.log("Tossed a " + toss + ", need to try again.");
  return tossASix();
}

function logSuccess(toss) {
  console.log("Yay, managed to toss a " + toss + ".");
}

function logFailure(toss) {
  console.log("Tossed a " + toss + ". Too bad, couldn't roll a six");
}
// use promise paradigm to try three times to toss a 6
tossASix()
  .then(null, logAndTossAgain)   //Roll first time
  .then(null, logAndTossAgain)   //Roll second time
  .then(logSuccess, logFailure); //Roll third and last time
```

Without Minification



```javascript
function dieToss(){return Math.floor(6*Math.random())+1}function tossASix(){return new RSVP.Promise(function(a,b){var c=Math.floor(6*Math.random())+1;6===c?a(c):b(c)})}function logAndTossAgain(a){return console.log("Tossed a "+a+", need to try again."),tossASix()}function logSuccess(a){console.log("Yay, managed to toss a "+a+".")}function logFailure(a){console.log("Tossed a "+a+". Too bad, couldn't roll a six")}tossASix().then(null,logAndTossAgain).then(null,logAndTossAgain).then(logSuccess,logFailure);
```

With minification



## Obfuscation

It's the technique of making a source code of an application difficult to read and to comprehend by an human, so it's become almos impossible reverse engineer it. This process converts the code into a form which returns the un-obfuscated code.

```javascript
var _0x2695=['.\x20Too\x20bad,\x20couldn\x27t\x20roll\x20a\x20six',',\x20need\x20to\x20try\x20again.','Promise','Tossed\x20a\x20','then','floor','log'];(function(_0x4675d0,_0x27e03f){var _0x2695b1=function(_0x2bb6e8){while(--_0x2bb6e8){_0x4675d0['push'](_0x4675d0['shift']());}};_0x2695b1(++_0x27e03f);}(_0x2695,0x122));var _0x2bb6=function(_0x4675d0,_0x27e03f){_0x4675d0=_0x4675d0-0x196;var _0x2695b1=_0x2695[_0x4675d0];return _0x2695b1;};var _0x3bc1ea=_0x2bb6;function dieToss(){var _0x21acfb=_0x2bb6;return Math[_0x21acfb(0x198)](Math['random']()*0x6)+0x1;}function tossASix(){var _0x4db9b6=_0x2bb6;return new RSVP[(_0x4db9b6(0x19c))](function(_0x2aa096,_0x506e91){var _0x2b10d4=Math['floor'](Math['random']()*0x6)+0x1;_0x2b10d4===0x6?_0x2aa096(_0x2b10d4):_0x506e91(_0x2b10d4);});}function logAndTossAgain(_0x3c8b5b){var _0x4ed940=_0x2bb6;return console['log'](_0x4ed940(0x196)+_0x3c8b5b+_0x4ed940(0x19b)),tossASix();}function logSuccess(_0x1a98dc){var _0x573477=_0x2bb6;console[_0x573477(0x199)]('Yay,\x20managed\x20to\x20toss\x20a\x20'+_0x1a98dc+'.');}function logFailure(_0x2c7871){var _0x391ba8=_0x2bb6;console['log']('Tossed\x20a\x20'+_0x2c7871+_0x391ba8(0x19a));}tossASix()[_0x3bc1ea(0x197)](null,logAndTossAgain)['then'](null,logAndTossAgain)[_0x3bc1ea(0x197)](logSuccess,logFailure);
```

Same code as before, but ofuscated.



## Obfuscators and Minificators

The most pupular package is [WebPack](https://webpack.js.org/), but [Rollup](https://rollupjs.org/guide/en/) is getting more used nowadays.

