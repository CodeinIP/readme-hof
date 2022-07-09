# WE-THEORY

## Props and State
In a React component, props are variables passed to it by its parent component. State on the other hand is still variables, but directly initialized and managed by the component.
The parent can pass a prop by using this syntax:
````
< ChildComponent count=10 />
````
## State 
A state is a variable which exists inside a component, that cannot be acessed and modified outside the component and can only be used inside the component.
* Works very similarly to a variable that is declared inside a function that cannot be accessed outside the scope of the function in normal javascript.
* State can be modified using the.setStae.
* State can be asynchronous.
 Whenever this.setState is used to chnge the state class is rerender itself.
 `const [state,setState] = React.useState(null);
    setState(state=> state+1)`