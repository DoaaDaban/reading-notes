# Read: Class 04 React and Forms

## [React Docs - Forms](https://reactjs.org/docs/forms.html)

1. What is a ‘Controlled Component’?
    - React component that renders a form also controls what happens in that form on subsequent user input. An input form element whose value is controlled by React

1. Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.
    - update the state with their responses as soon as they enter them; you can pass the value to other UI elements, or reset it from other event handlers.

1. How do we target what the user is entering if we have an event handler on an input field?
    - by adding onChange to the input element and assigning a function, the function will runs on every keystroke to update the React state, and the value will be in event.target.value

## [The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)

1. Why would we use a ternary operator?
    - we use it instead of if statement because it is shorter

1. Rewrite the following statement using a ternary statement:

<p>if (x === y){ <br>
    console.log(true);<br>
} else {<br>
    console.log(false);<br>
}</p>

    - x===y ? console.log(true) : console.log(false)


## Things I want to know more about
I want to know about all of the form elements in React.