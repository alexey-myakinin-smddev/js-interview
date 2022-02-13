# JS Interview

```javascript
// 1. Async
const foo = () => {
  new Promise(() => console.log("1")).then(() => console.log("then"));
  Promise.resolve().then(() => console.log("3"));
  setTimeout(() => console.log("4"), 0);
  console.log("5");
};
foo();

const promises = [Promise.resolve(), Promise.reject()];

Promise.all(promises);
Promise.allSettled(promises);
Promise.race(promises);

/**
 * 2. Events
 */
const EventsEmitter = require("events");
const emitter = new EventsEmitter();
emitter.on("event", () => console.log("Event"));
emitter.emit("event", 1, 2, 3, 4, 5);

emitter.once("once", () => console.log("Once"));
emitter.emit("once");
emitter.emit("once");

/**
 * 3. Misc
 */
const {
  promises: { readFile: readFile1 },
  readFile: readFile2,
} = require("fs");

readFile1();
readFile2();
```
