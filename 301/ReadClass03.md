# Read: Class 03 Passing Functions as Props

## [React Docs - lists and keys](https://reactjs.org/docs/lists-and-keys.html)

1. What does .map() return?
    - it return an array with the same length as the original array.

1. If I want to loop through an array and display each value in JSX, how do I do that in React?
    - we loop an array using the JavaScript map() function
1. Each list item needs a unique key.

1. What is the purpose of a key?
    - Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity

## [The Spread Operator](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)

1. What is the spread operator?
    - refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments.

1. List 4 things that the spread operator can do.
    - Using Math functions
    - Copying an array
    - Concatenating or combining arrays
    - Using an array as arguments

1. Give an example of using the spread operator to combine two arrays.
    - const myArray = [`🤪`,`🐻`,`🎌`]
    - const yourArray = [`🙂`,`🤗`,`🤩`]
    - const ourArray = [...myArray,...yourArray]

1. Give an example of using the spread operator to add a new item to an array.
    - const ourArray = [...myArray,'🍉', '🍍']

1. Give an example of using the spread operator to combine two objects into one.
    const objectOne = {hello: "🤪"}
    const objectTwo = {world: "🐻"}
    const objectThree = {...objectOne, ...objectTwo}

## [How to Pass Functions Between Components](https://www.youtube.com/watch?v=c05OL7XbwXU)

1. In the video, what is the first step that the developer does to pass functions between components?
    - create the function where you want to change the state

1. In your own words, what does the increment function do?
    - the increment function in the parent component is incrementing the count property in the people state by one
    - the function in the child component is calling the parent function and passing the proper arguments

1. How can you pass a method from a parent component into a child component?
    - passing it as a normal props(name the attribute and assign (this.name of the function) as a value)

1. How does the child component invoke a method that was passed to it from a parent component?
    - by creating another function in the child component that call the passed function.

## Things I want to know more about

surely props and state are interesting topics and we should learn more about
