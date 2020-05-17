# Classes, Inheritance, Functional programming :fire:

## Reading, Research, and Discussion :mag_right:

1. Name 3 advantages to **Test Driven Development**.
1. In what case would you need to use `beforeEach()` or `afterEach()` in a test suite?
1. What is one **downside** of Test Driven Development.
1. What’s the primary **difference** between ES6 Classes and Constructor/Prototype Classes?
1. Name a use case for a **static method**.
1. Write an example of a **Higher Order function** and describe the use case it solves.

#### What Is Test-Driven Development? :question:

**Test-driven development (TDD)** is a software development process that relies on the repetition of a very short development cycle
**Benefits** of Test-Driven Development: :thumbsup:

1. You are able to **identify the errors** and problems quickly.
2. Test-driven development tells you whether your last change (or refactoring) broke previously working code.
3. Test-driven development allows the _design_ to _evolve_ and _adapt_ to your changing understanding of the problem.

**downsides** of Test Driven Development: :thumbsdown:

1. take **much time** of the actual implementation.
2. **Additional Complexity**. for complex cases, your test cases are harder to calculate.
3. **Design Impacts**. Sometimes the design is **not clear** at the start and evolves as you go along - this will force you to redo your test which will generate a big-time lose.

#### What’s the primary difference between ES6 Classes and Constructor/Prototype Classes? :thought_balloon:

**JavaScript objects** use **prototype-based inheritance**. Its design is logically similar (but different in implementation) from class inheritance in strictly Object Oriented Programming languages like Java and C#.
`It can be loosely described by saying that when methods or properties are attached to object’s prototype they become available for use on that object and its descendants, but not directly attached to them`

**Data Modeling** => **JavaScripts AND Prototypes** => **ES6 Classes** (which will make the Objects and Inheritance much ,ore easier to understand)
_Object_ has attributes related to it and methods

_EXAMPLE_

```
function Animal(name) {
  this.name = name;
  this.legs=legs;
  this.eat= function () {
      this.isEating=true;
  }
}

Animal.prototype.walk=function(){
    this.isWalking=true;
}
```

#### In what case would you need to use `beforeEach` or `afterEach()` in a test suite :grin:

The `beforeEach` and `afterEach` commands allow you to define setup and teardown tasks that are performed **at the beginning and end of every It block**.This can **eliminate duplication** of code in test scripts, and perform any necessary **cleanup tasks** after each test.
`beforeEach` and `afterEach` blocks may be defined inside of any **Describe** or **Context**.

**Example**

```
Describe 'Testing BeforeEach and AfterEach' {
    $afterEachVariable = 'AfterEach has not been executed yet'

    It 'Demonstrates that BeforeEach may be defined after the It command' {
        $beforeEachVariable | Should -Be 'Set in a describe-scoped BeforeEach'
        $afterEachVariable | Should -Be 'AfterEach has not been executed yet'
    }

    It 'Demonstrates that AfterEach has executed after the end of the first test' {
        $afterEachVariable | Should -Be 'AfterEach has been executed'
    }

    BeforeEach {
        $beforeEachVariable = 'Set in a describe-scoped BeforeEach'
    }

    AfterEach {
        $afterEachVariable = 'AfterEach has been executed'
    }
}
```

#### Functional Programming :green_heart:

what is the **functional programming** is ?
It is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects.

1. **Pure functions** which :gem::

    - Given the same inputs, always returns the same output, and
    - Has no side-effects

1. **Impure fuction** :waxing_crescent_moon:
   is the opposite of the pure function, like having a function then I'll call another function inside of it that unitized as a variable from out of the scope.

   - with global var
   - readings external files
   - random number generator

1. **Higher order function** :1st_place_medal:

   - takes one or more functions as arguments
   - returns a function as its result
     is any function which takes a function as an argument, returns a function, or both. Higher order functions are often used to:

   - Abstract or isolate actions, effects, or async flow control using callback functions, promises, monads, etc…
   - Create utilities which can act on a wide variety of data types.
   - Partially apply a function to its arguments or create a **curried** function for the purpose of reuse or function composition.
   - Take a list of functions and return some composition of those input functions
     **Example**

- we can have functions that create new functions.

```
function greaterThan(n) {
  return m => m > n;
}
let greaterThan10 = greaterThan(10);
```

- And we can have functions that change other functions.

```
function noisy(f) {
  return (...args) => {
    console.log("calling with", args);
    let result = f(...args);
    console.log("called with", args, ", returned", result);
    return result;
  };
}
```

- We can even write functions that provide new types of control flow.

```
function unless(test, then) {
  if (!test) then();
}

repeat(3, n => {
  unless(n % 2 == 1, () => {
    console.log(n, "is even");
  });
});
```

## Document the following Vocabulary Terms :memo:

| Term                              | Documentation                                                                                                                                                                                                              |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| functional programming            | It is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects.                                                                                                 |
| pure function                     | accept an input and returns a value without modifying any data outside its scope                                                                                                                                           |
| higher-order function             | is a function that can take another function as an argument, or that returns a function as a result                                                                                                                        |
| immutable state                   | is state that cannot be changed , an immutable object is an object whose state cannot be modified after it is created                                                                                                      |
| object                            | standalone entity, with properties and type.                                                                                                                                                                               |
| object-oriented programming (OOP) | refers to a type of computer programming (software design) in which programmers define the data type of a data structure, and also the types of operations (functions) that can be applied to the data structure           |
| class                             | is an extensible program-code-template for creating objects, providing initial values for state (member variables) and implementations of behavior (member functions or methods).                                          |
| prototype                         | is an object that is associated with every functions and objects by default in JavaScript, where function's prototype property is accessible and modifiable and object's prototype property (aka attribute) is not visible |
| `super`                           | keyword is used to access and call functions on an object's parent.                                                                                                                                                        |
| inheritance                       | inheritance is supported by using prototype object. Some people call it "Prototypal Inheriatance" and some people call it "Behaviour Delegation".                                                                          |
| constructor                       | is a special type of subroutine called to create an object.                                                                                                                                                                |
| instance                          | means a reference to an “object” created by “new” or the equivalent.                                                                                                                                                       |
| context                           | It refers to the object to which a function belongs.                                                                                                                                                                       |
| `this`                            | keyword refers to an object, that object which is executing the current bit of javascript code                                                                                                                             |
| Test Driven Development (TDD)     | is a software development process that relies on the repetition of a very short development cycle                                                                                                                          |
| Jest                              | testing framework designed to ensure correctness of any JavaScript codebase.                                                                                                                                               |
| Continuous Integration (CI)       | is the process of automating the build and testing of code every time a team member commits changes to version control.                                                                                                    |
| unit test                         | is a software testing where individual units (components) of a software are tested                                                                                                                                         |
### Additional Resources :pager:


**Videos** :smirk:

- [TDD in JS](http://www.letscodejavascript.com/)
- [javascript context tutorial](https://www.youtube.com/watch?v=fjJoX9F_F5g)


**Bookmark / Skim** :star:

- [MDN inheritance](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
- [MDN this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
- [MDN class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
- [node error docs](https://nodejs.org/dist/latest-v6.x/docs/api/errors.html)
- [jest docs](https://jestjs.io/docs/en/getting-started)