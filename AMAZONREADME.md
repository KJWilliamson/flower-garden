In a number of previous projects, you have added "click" event listeners to html elements. Today you will learn how to use a method as an event listener. Using a method as an event listener and retaining the desired `this` value brings up the concept of execution context. 

In short: the **execution context** refers to the scope of accessible variables for the function being executed. That also includes the value that is assigned to the `this` keyword. Whenever any code is run in JavaScript, it’s run inside an execution context. Remember from the methods and `this` lesson: 

> `this` allows a function to access information dynamically about the object which is calling it.

Let's take a look at an example:

```js
const person = {
  name: 'peter',
  birthYear: 1994,
  calcAge: function() {
    console.log(2018 - this.birthYear);
  }
}
person.calcAge(); 
// 'this' refers to 'person', because 'calcAge' was called with 'person' object reference
const calculateAge = person.calcAge;
calculateAge();
// 'this' refers to the global window object, because no object reference was given
```
*Citation: [Sukhjinder Arora](https://blog.bitsrc.io/understanding-execution-context-and-execution-stack-in-javascript-1c9ea8642dd0#0f5d)*

So, how does this tie in to event listeners? Well, remember that event listeners pass our function as a callback function to the element object that is being clicked. So, the element object is the object calling the event listener callback function, so the element object becomes the `this` value.

TODO: add event listener example and show execution context

Fork and clone a copy of [this repository.](https://github.com/KenzieAcademy/activity-object-handle-event)

The code implemented so far will show 5 seedlings on the screen. Follow the instructions in the TODO comment within the js file.

Here is an example of how the page should behave after you have completed the handleEvent method:

![flower_garden_sml.gif](https://s3.us-east-2.amazonaws.com/images.kenzie.academy/frontend-se/flower_garden_sml.gif)
