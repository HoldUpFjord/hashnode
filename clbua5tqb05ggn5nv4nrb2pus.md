# PREP: The formula for acing coding challenges

## What is PREP?

*PREP* stands for:

*   Parameters
    
*   Returns
    
*   Examples
    
*   Psuedocode
    

The process you should be using to approach every coding challenge from the infamous Leetcode problems to Codewars and beyond, can be distilled into this easy flow chart.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671185789932/6RlhDy4W7.jpg align="center")

### Inputs ➡️

**Parameters** are your inputs. What is it you are being given to work with? A string or an array? What does that array contain? Integers, strings, a mix? These are important considerations for *how* you begin to think through the problem. Why is it important though?

If we look at Javascript as an example, the majority of methods we will be using can be broken down into two categories: methods that work on *strings*, and methods that work with *arrays*. Finding out what kind of parameters a function is taking in already eliminates around ***half*** of the potential methods you could be using. Once we've outlined what ***parameters*** we're starting with, then we can examine the goal.

### Returns ↩️

Our **Returns** or, put another way, our output. Every coding challenge should describe what it's looking for at the end, what the smattering of code you type outputs given our Parameter(inputs).

### Examples: ✍️

Every coding challenge will come with something called Test Cases. Now while that might sound intimidating, in reality, they are simply examples that you are trying to achieve.

### Pseudocode 🪧

Pseudocode can be a tricky practice to nail down. The idea is that you are actively breaking down what you want your code to do in plain language. It's a useful tool for imagining what you want your code to do and working through how to accomplish it, without having to worry about syntax, typos or making sure you closed that last bracket `'}'`.

## Let's work through a problem!

Take a common beginner problem, reversing a string: [Reverse-String Challenge](https://www.codewars.com/kata/57a55c8b72292d057b000594/train/javascript)

It's easy to freeze up when approaching these challenges, so let's look at the description together:

*You need to write a function that reverses the words in a given string. A word can also fit an empty string. If this is not clear enough, here are some examples:*

*As the input may have trailing spaces, you will also need to ignore unnecessary whitespace.*

*Example (****Input*** *--&gt;* ***Output****)*

### Where do we go from here?

Let's do our ***PREP!***

`function reverse(string){ //your code here }`

Is the template they give us. Our **parameter** lies in between the parenthesis, a *string*. That is our input. Let's turn and look at our **return**. Our **output**. We should be asking a couple of questions here:

*   Does the *data-type* change?
    
    *   In this example we are starting with a *string*, what are we ending with? An array? An object? In this case, the answer is **no.** We start and end with a string.
        
*   What are we returning?
    
    *   One string, a sentence, with its words reversed
        

To make sure we understand the problem a bit better, let's look at some **examples**:

```plaintext
"Hello World" --> "World Hello"
"Hi There." --> "There. Hi"
```

These are the given examples to look at. If you want further clarification, you can check out the test cases. On Codewars, you can find them here:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671418210350/jW-3QtsWW.png align="center")

In each of these examples, we reaffirm that individual words are left as is, but their location in the string is reversed. Now unto our last step before actually writing code!

**Pseudocode**. There are a lot of ways to do this, I approach it by writing comments in my code that communicate what I'm intending as clearly as possible. I usually write in a combination of plain text and bits of code. Like so:

```javascript
function reverse(string){
  //psuedo-code here: what we want our code to do
  // have a empty result array to push to
  // split string
  //for( i = string.split(' ').length-1 ; i >= 0 ; i--)
        // push string.split(i) to result
  //return result.join(' ')
}
```

In this example, we use a common method pattern. `string.split()` and `string.join()` . This loops through the string and gives us an array filled with all the elements of said string. As long as we use `string.join()` at the end to then transform the array elements back into a string, we're golden 👍

```javascript
function reverse(string){
  let splitString = string.split(' ')
  let result = []
  for( i = splitString.length-1; i >= 0; i--){
    result.push(splitString[i])
  }
  return result.join(' ')
}
```

We can even use an additional method, `array.reverse()` to cut out our for loop *entirely.*

```javascript
function reverse(string){
return string.split(' ').reverse().join(' ')
}
```

Pretty cool right?!

## What's next? 🤔

It's time to practice! Nothing will help engrain this like getting some repetitions in.

*   [Codewars](https://www.codewars.com/dashboard) is a great and friendly place to start for newer programmers!
    
*   [Leetcode](https://leetcode.com/) is a bit more intensive, with questions commonly seen in interviews.
    

"But Dom, I really don't like the IDE's for either of these platforms!"

Well, check out [Replit](https://replit.com/) for an amazing online IDE!

Good luck with your future coding! 💪