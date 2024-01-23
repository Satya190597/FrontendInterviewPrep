# FrontendInterviewPrep

## Prototypes
- Prototypes are the mechanism by which JavaScript objects inherits features from one another.
- Every object in JavaScript has a **built-in property, which is called its prototype**. The prototype is itself an object, so the prototype will have its own prototype making what's called a **prototype chain**.
  - Object -> Prototype (Object) -> Prototype (Object) -> Null.
- The standard way to access an object's prototype is the **Object.getPrototypeOf()** method
    ```javascript
    var myObject = {
      message: 'Hello World'
    }
    Object.getPrototypeOf(myObject);
    ```
