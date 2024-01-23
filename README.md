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
### The prototype of an object is not always **Object.prototype**.
**Example** - In this example prototype of myDate is a Data.prototype object.
![The prototype of an object is not always **Object.prototype**!](/prototype-001.png)
### Shadowing properties
Property Shadowing means that when an object and its prototype both contain a property with the same name, then the property present in the prototype gets shadowed by the property directly present in the object itself.
```javascript
var myDate = new Date(1995, 11, 17);

console.log(myDate.getYear()) // 95

myDate.getYear = function() {
	return "Hello World !!"
}

console.log(myDate.getYear()) // "Hello World !!"
```
### Setting a prototype.
There are various ways of setting an object's prototype in javascript. The two major ways are.
- Object.create
- Constructors
#### Using Object.create
```javascript
const person = {
	greet: function() {
  	console.log("Hello !!");
  }
}

const teacher = Object.create(person);

teacher.skill =  function() {
  console.log("I Can Teach !!");
}

teacher.skill(); // I Can Teach !!
teacher.greet(); // Hello !!
```
#### Constructors
In JavaScript, all functions have a property named **prototype**. When you call a function as a constructor, this property is set as the **prototype of the newly constructed object**.
```javascript
const person = {
	greet: function() {
  	console.log("Hello !!");
  }
}

function Person(skill) {
	this.skill = skill;
}

Object.assign(Person.prototype,person);

function skill() {
  console.log("I Can Teach !!");
}

const teacher = new Person(skill);

teacher.skill(); // I Can Teach !!
teacher.greet(); // Hello !!
```
![Explain Setting Prototype Using Constructor](/prototype-002.png)
### Difference between \_\_proto\_\_ and prototype.
- Prototype is a property of a Function object. It is the prototype of objects constructed by that function.
- \_\_proto\_\_ is an internal property of an object, pointing to its prototype. Current standards provide an equivalent Object.getPrototypeOf(obj) method, though the de facto standard \_\_proto\_\_ is quicker.
> [Credit Resource : user3840170](https://stackoverflow.com/a/9959771)


  
