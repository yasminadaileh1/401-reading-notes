# Node Ecosystem, TDD, CI/CD :star:

1.  **Why would you want to run JavaScript code outside of a browser?**
    :page_facing_up:
    **Answer**:
    JavaScript is no longer just a browser scripting language, it is allows you to write programs which can be run inside and outside a browser.

        1. Running JavaScript **inside a browser** means:
           - **interacting with Web UI** (HTML and CSS components) which is displayed on a user's screen.
        1. Running JavaScript **without/outside a browser** means:
           - using **node.js technology** to execute the JavaScript code.

1.  **What is the difference between a module and a package?**
    :page_facing_up:
    **Answer**:
    A **module** is a **single JavaScript file** (or files) that are imported under one import and used and has some reasonable functionality
    A **package** is a **collection of modules** in directories that give a package hierarchy.

1.  **What does the node package manager do?**
    :page\*facing_up:
    **Answer**:
    **npm**, short for **Node Package Manager**, is two things:

        1. an online repository for the publishing of open-source Node. js projects.
        1. a command line tool that installs, updates or uninstalls Node. js packages and dependency management in your application.

1.  **Provide code snippets showing 3 different ways to export a function from a node module.**
    - Requiring a Module:
      `const express = require('express');`
    - Creating and Exporting a Module:
      `const getName = () => { return "Jim"; }; exports.getName = getName;`
    - Exporting a Default Value:
    ```
    class User {
    constructor(name, age, email) {
    this.name = name;
    this.age = age;
    this.email = email;
    }
    module.exports = User;
    ```

### Document the following Vocabulary Terms :memo:

| Term                       | Documentation                                                                                                                                                                                 |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ecosystem                  | a collection of software projects, which are developed and co-evolve in the same environment                                                                                                  |
| Node.js                    | is an open source development platform for executing JavaScript code server-side.                                                                                                             |
| V8 Engine                  | V8 is Google’s open source high-performance JavaScript and WebAssembly engine, written in C++. It is used in Chrome and in Node.js, among others.                                             |
| module                     | a software component or part of a program that contains one or more routines. One or more independently developed modules make up a program.                                                  |
| package                    | namespace that organizes a set of related classes and interfaces.                                                                                                                             |
| node package manager (npm) | a package manager for the JavaScript programming language. It is the default package manager for the JavaScript runtime environment Node. js                                                  |
| server                     | a computer program or device that provides a service to another computer program and its user, also known as the client                                                                       |
| environment                | the set of processes and programming tools used to create the program or software product.                                                                                                    |
| interpreter                | computer program that directly executes instructions written in a programming or scripting language, without requiring them previously to have been compiled into a machine language program. |
| compiler                   | a special program that processes statements written in a particular programming language and turns them into machine language or "code" that a computer's processor uses.                     |

**What is the difference between** (_npm start and node server.js_)

1. npm is shortcut to say npm (the start in the scripts from the package.json file in the repo)
   **So npm start runs node server.js**
1. node server.js its important b/c when we will go to heroku and run node server.js it will run npm start for you to start your server
1. npm is a code runner
   npm install -g nodemon (so i will not have to stop and start the server every time i update it)
   so run nodemon on the terminal and it will start to watch the server every time i save the changes it will start npm