# Read: Class 02 State and Props

## [React: Component Lifecycle Events](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)

1. Based on the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?
    - the render happens first.

1. What is the very first thing to happen in the lifecycle of React?
    - static getDerivedStateFromProps

1. Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates
    - constructor
    - render
    - componentDidMount
    - React Updates
    - componentWillUnmount
1. What does componentDidMount do?
    - load anything using a network request or initialize the DOM.
    - setState() can be called here, but it should be used sparingly because it will cause a rerender, which can lead to performance issues.

## [React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJI)

1. What types of things can you pass in the props?
    - the things that will not be changed by the user. like a title or a description

1. What is the big difference between props and state?
    - props are handled outside of the components while the state inside the components.
    - if the state is changed everything will be updated unlike the props

1. When do we re-render our application?
    - when the user changes something for example when the user enters some inputs.

1. What are some examples of things that we could store in state?
    - counter.
    - the output of user inputs.

## Things I want to know more about

how to use states in react classes
