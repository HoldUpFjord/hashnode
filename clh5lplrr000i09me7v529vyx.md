---
title: "Bubble-Sorting:"
seoDescription: "Teaching programming and Data Structures and Algorithm's. Learn trough brief and well written articles to help new developers and software engineers in Tech"
datePublished: Tue May 02 2023 01:39:03 GMT+0000 (Coordinated Universal Time)
cuid: clh5lplrr000i09me7v529vyx
slug: bubble-sorting
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682970952075/3c8e9c12-51fe-48ce-8413-33e17d724d06.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1682991539609/11588abb-11e4-42e6-aab2-7b88f5331bfd.png
tags: algorithms, programming-blogs, javascript, web-development, data-structures

---

## The Code 🖥️:

---

  
Here is the code with comments:

```javascript
 function quickSorting(array) {
    //loop through array
    for(i = 0; i < array.length; i++){
      // For every loop from previous line, loop again.
      // Decrease loop length by one for each main loop, or the value of i
      for(j = 0; j < array.length - 1 - i ; j++){
        //if current index is larger than next index
        if(array[j] > array[j + 1] ){
          // save current index 'i' in variable
          const temp = array[j]
          // assign 'i' value to the value of 'i+1'
          array[j] = array[j + 1]
          // assign stored value of 'i' to next index 'i+1' 
          array[j + 1] = temp
        }
      }
    
    }
      return array
  };
```

  

## The How & Why🙋:

---

Bubble sort is a surprisingly simple algorithm to implement; it's also, in my opinion, one of the greatest.  
  
Defining what a sorted array is can be a bit abstract, but to put it in technical terms: *A sorted array is any array in which a value "****X"*** *at index "****i"*** *comes before another value "****X"*** *at index "****i+1 "****.*  
  
Put into more plain terms, a sorted array is *any array that is ordered in a logical way*.  
Below we can see this as a graphic in which 0 marks the 0th index of the array, and N marks the final index of the array.  

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682971660154/30407147-a5c2-48da-95e4-db9a2264a968.png align="center")

### How does Bubble Sort, sort?

---

\-Let's start by defining an array we can work with:

* `[2, 6, 14, 8, 4]`  
    

What bubble sort does as an operation is compare the current index *Xi* with the next index *Xi+1*, if the next index is larger than the first index, they swap positions.  
  
With the example, we will loop through the array, and at the 2nd index find that it's value `14` is bigger than the following index `8`. We then swap the index of those two values so we get an array that looks like this: `[ 2, 6, 8, 14, 4]`.  
  
In the next following sub-loop, we would perform a similar swap. Resulting in moving `14` to the last index in the array. Congrats! We now have the largest value where it needs to be.

%[https://giphy.com/gifs/high-five-bro-12vP3dyG40ttqE] 

### **To Recap:**

In a single iteration of Bubble Sort we have seen the array altered in such a way that *the largest value is at the end* as follows:

1. `[2, 6, 14, 8, 4]`
    
2. `[ 2, 6, 8, 14, 4]`
    
3. `[2, 6, 8, 4, 14]`
    
      
      
    

This is after just a **single pass** through the array and is a defining characteristic of this algorithm.  
The length of the next iteration can also be `array.length - 1` as the first iteration will always place the largest value in the final index of the array.  
The next iteration will see:

* `[ 2, 6, 8, 4, 14]` turn into `[ 2, 6, 4, 8, 14]`
    

And the next will finish at :

* `[ 2, 6, 4, 8, 14]` to `[ 2, 4, 6, 8, 14]`
    

## That's Bubble Sort!

A straightforward algorithm that is, in its own right awesome, and also serves as a baseline for more complex algorithms going forward.