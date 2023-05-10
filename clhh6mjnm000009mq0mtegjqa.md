---
title: "TypeScript and ESLint:"
seoTitle: "Understanding Static Analysis"
seoDescription: "Static analysis is a critical aspect of software development that helps to catch errors and improve code quality. Typescript,ESLint, and Prettier are tools"
datePublished: Wed May 10 2023 04:10:00 GMT+0000 (Coordinated Universal Time)
cuid: clhh6mjnm000009mq0mtegjqa
slug: typescript-and-eslint
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1683687269802/4d21c8c9-2c25-44a5-87f1-0909a12bb0aa.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1683691925828/532b9c53-7acf-4988-a27e-73679b1a034a.png
tags: programming-blogs, javascript, web-development, reactjs, typescript

---

## Overview

Static analysis is a critical aspect of software development that helps to catch errors and improve code quality. In a recent talk on TypeScript and ESLint by [Joshua K. Goldberg](https://www.joshuakgoldberg.com), he discussed the importance of ***static analysis*** in web development and the use of formatters and linters to improve code quality. The following is an expanded edit of my notes from said conference talk.

---

## Static Analysis:

### The term that defines it all.

---

Static Analysis is a type of analysis that scrutinizes code *without* running it. This analysis helps to catch errors early in the development process, making it easier to maintain code quality. Three tools used for static analysis are **formatters**, **linters**, and **type checkers**.

* Formatters are tools that read source code and edit it to a more readable format. This process does not involve running the code. A common example of a formatter is Prettier, which can be used as a Visual Studio Code (VS Code) or Integrated Development Environment (IDE) extension. Prettier can auto-format code to improve code readability.
    
* Linters are different from formatters as they run a set of checks on source code. They look at code and flag issues to help developers identify potential errors. Linters are also more customizable, as they have discreet rules that can be configured to suit the specific needs of a project. A common example of a linter is [ESLint](https://eslint.org/), a pluggable and configurable linter tool for identifying and reporting on patterns in JavaScript.
    
* Type Checkers are, in essence, a tool that aids programmers in catching errors caused by the data types of values and variables being used. As an example in Javascript we might write a simple function like this:
    

### Code Examples:  
  

```javascript
// Define a function that takes two numbers and returns their sum
function addNumbers(x, y) {
  return x + y;
}

// Call the function with two numbers - this will work as expected
const result = addNumbers(1, 2);
console.log(result); // 3
```

The pitfall of this is that, if it's your first time reading this code block, you have no idea if the variables have a specific data type. We can assume x and y represent numbers, but are they written as ints or strings? We're going to have to journey into a maze of console.log's and breakpoints to understand what's going on here.

Now imagine doing this for a codebase with ten's of thousands lines of code. A rather elegant solution is Typescript, which uses a type checker:

```typescript
// Define a function that takes two numbers and returns their sum
function addNumbers(x: number, y: number): number {
  return x + y;
}

// Try calling the function with a string argument - this will result in a compile-time error
addNumbers('1', '2'); // Error: Argument of type 'string' is not assignable to parameter of type 'number'

// Call the function with two numbers - this will work as expected
const result = addNumbers(1, 2);
console.log(result); // 3
```

Here we can see the type of each variable is declared in-line. It's beautiful. If we were to attempt to run the function with strings, we would get immediate error alerts before we even had to run our code.

We can see how in the context of TypeScript, a type checker is built into the language itself and helps ensure that your code is type-safe. This means that it checks that the types of variables and functions are compatible with the way they are being used in your code.

### Importance of Static Analysis:

---

Static analysis is a crucial part of software development, as it helps to catch errors early in the development process. It also ensures that code is written in a consistent and readable manner, making it easier for developers to understand and maintain the codebase. By using tools such as formatters and linters, developers can improve the quality of their code and avoid potential issues.

## Credits:

Joshua K. Goldberg is the author of ["Learning TypeScript](https://www.learningtypescript.com/)," a book that focuses on enhancing web development skills using type-safe JavaScript. He also is a key maintainer for [Typescript-ESLint](https://github.com/typescript-eslint/typescript-eslint), and a Philly cheesesteak connoisseur. Go out and give him a follow.