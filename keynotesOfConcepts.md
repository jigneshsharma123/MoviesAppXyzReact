what is state in reactjs ? 

ans==> The state of a component is an object that represents its dynamic information, allowing it to keep tarack of changes and re-reander when necessary, State is a fundamental concept in react and is crucial for Building intereactive and dynamic user interface.
 
==> keyPoints about  React State : 
   1-> Mutable Data
       * State is mutable, meaning it can be changed or updated over  time. 
       * Components can initialize their state during construction and update it using the 'setState' method
   2-> Component-level 
       * Each component is react can have it's own state.
       * State is local to a component and is not directly accessible from other components. 
   3-> Rendring Trigger
       * when the state of a component changes, React re-renders the component, updating the user interface to reflect the new state. 
       * The 'render' method is called again with the updated state, and ther virtual DOM is efficiently updated. 
   4-> Initialization : 
       * State is typically initialized in the 'constructor' method of a class component.
       * In functional components, the 'useState' hook is used to decleaare and initialize state variable 
   5-> Setting state : 
       * The 'setState' method is used to update the state in class component. 
       * In functional components, the 'useState' hooks provides a function to update the state.  

===> Here's a simple example of state usage in a class component
   
     import React, {Component } from 'react';
     class Counter extens Component {
      constructor(props) {
        super(props);
        this.state = {
            count : 0,
        };
      }
       incrementCount = () => {
        this.setState({count:this.state.count + 1});
       };
       
     } //end of the class counter component 
      render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.incrementCount}>Increment</button>
      </div>
    );
  }
}

export default Counter;

//end of the example 

2nd example using functional components
 
 import React, { useState } from 'react';

const Counter = () => {
  // Using the useState hook to declare a state variable 'count' with an initial value of 0
  const [count, setCount] = useState(0);

  // Function to increment the count
  const incrementCount = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={incrementCount}>Increment</button>
    </div>
  );
};

export default Counter;

In this example:
  
* The 'useState' hook is called with an initial value of '0' to declar a state varible 'count'.
* The count state variable is used in the component's render method to display the current count.
* The setCount function, provided by useState, is used to update the count state when the "Increment" button is clicked.
* Clicking the button triggers a re-render of the component with the updated state, and the new count is displayed.


what is Hooks in react and why and when it used ? 

Ans ==> In React, hooks are functions that allow functional components to use state and lifecycle features that were previously only available in class components. Hooks were introduced in React 16.8 to provide a more concise and readable way to manage state and side effects in functional components.

They serve the following purposes:
1--> State Management 
    useState: Allows functional components to have state variables. It returns an array with two elements: the current state value and a function that lets you update it.
    
    e.g=> const [count, setCount] = useState(0);

2--> Effect Handling : 
    *-> 'useEffect' :  Enables functional components to perform side effects, such as data fetching, subscriptions, or manually changing the DOM.

    e.g ==> useEffect(() => {
  // Side effect code
  console.log('Component did mount or update');
  // Cleanup function (optional)
  return () => {
    console.log('Component will unmount');
  };
}, [dependencies]);

When to Use Hooks:
  ** Functional Components: Hooks are designed to be used in functional components. If you are using functional components and need state or lifecycle methods, hooks are the way to go.

  ** Reusable Logic: If you find yourself duplicating logic across components, consider creating a custom hook to encapsulate that logic and make it reusable.

  ** Side Effects: When you need to perform side effects like data fetching, subscriptions, or manual DOM manipulations, useEffect is a suitable hook.

  ** State Management: If you need local state in your components, useState provides a straightforward way to manage it.

  Using hooks makes functional components more powerful, modular, and easier to understand. They offer a simpler and more consistent way to work with stateful logic and side effects in React applications.