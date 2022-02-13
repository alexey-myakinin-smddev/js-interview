# JS Interview

```javascript
// 1. Async - назвать порядок вывода console.log()
const foo = () => {
  new Promise(() => console.log("1")).then(() => console.log("2"));
  Promise.resolve().then(() => console.log("3"));
  setTimeout(() => console.log("4"), 0);
  console.log("5");
};
foo();

// 2. Async - назвать разницу между Promise.all, Promise.allSettled и Promise.race
const promises = [Promise.resolve(), Promise.reject()];
Promise.all(promises);
Promise.allSettled(promises);
Promise.race(promises);

// 3. Events - зачем нужны, что выведет код ниже
const EventsEmitter = require("events");
const emitter = new EventsEmitter();
emitter.on("event", () => console.log("Event"));
emitter.emit("event", 1, 2, 3, 4, 5);
emitter.emit("event", 1, 2, 3, 4, 5);

emitter.once("once", () => console.log("Once"));
emitter.emit("once");
emitter.emit("once");

// 4. Разница readFile1 и readFile2
const {
  promises: { readFile: readFile1 },
  readFile: readFile2,
} = require("fs");

readFile1();
readFile2();
```
