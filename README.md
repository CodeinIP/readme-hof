# WE-THEORY

## Props and State

In a React component, props are variables passed to it by its parent component. State on the other hand is still variables, but directly initialized and managed by the component.
The parent can pass a prop by using this syntax:

```
< ChildComponent count=10 />
```

## State

A state is a variable which exists inside a component, that cannot be acessed and modified outside the component and can only be used inside the component.

- Works very similarly to a variable that is declared inside a function that cannot be accessed outside the scope of the function in normal javascript.
- State can be modified using the.setStae.
- State can be asynchronous.
  Whenever this.setState is used to chnge the state class is rerender itself.
  `const [state,setState] = React.useState(null); setState(state=> state+1)`

## Javascript HOF - MAP, REDUCE, FILTER

## MAP

`let newArray = arr.map(callback(currentValue,index,arr)){ return currentValue; } console.log(newArray)`

```
MAP takes argument array element,index and array itself and  return the array of required output
```

`let arr =[1,2,3,4,5] let res = arr.map((ele,index,arr)=>{ return ele*ele }) console.log(res) ===> [1,4,9,16,25];`

## REDUCE

- The reduce() method executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.

- The first time that the callback is run there is no "return value of the previous calculation"
- If supplied, an initial value may be used in its place. Otherwise the array element at index 0 is used as the initial value and iteration starts from the next element (index 1 instead of index 0).

- Perhaps the easiest-to-understand case for reduce() is to return the sum of all the elements in an array:
  `const array = [1,2,3,4,5]; const initValue = 0; const sumWithInit = array.reduce( previousValue,currentValue)=>previousValue+currentValue,initValue )` ===> 10

  `reduce((previousValue,currentValue,currentIndex,array)=>{},initialValue)`
  reduce() returns the value that is returned from the callback function on the final iteration of the array.

When to not use reduce()
Recursive functions like reduce() can be powerful but sometimes difficult to understand, especially for less experienced JavaScript developers. If code becomes clearer when using other array methods, developers must weigh the readability tradeoff against the other benefits of using reduce(). In cases where reduce() is the best choice, documentation and semantic variable naming can help mitigate readability drawbacks.

Behavior during array mutations
The reduce() method itself does not mutate the array it is used on. However, it is possible for code inside the callback function to mutate the array. These are the possible scenarios of array mutations and how reduce() behaves in these scenarios:

If elements are appended to the array after reduce() begins to iterate over the array, the callback function does not iterate over the appended elements.
If existing elements of the array do get changed, the values passed to the callback function will be the values from the time that reduce() was first called on the array.
Array elements that are deleted after the call to reduce() begins and before being iterated over are not visited by reduce().
Edge cases
If the array only has one element (regardless of position) and no initialValue is provided, or if initialValue is provided but the array is empty, the solo value will be returned without calling callbackFn.

If initialValue is provided and the array is not empty, then the reduce method will always invoke the callback function starting at index 0.

If initialValue is not provided then the reduce method will act differently for arrays with length larger than 1, equal to 1 and 0, as shown in the following example:

const getMax = (a, b) => Math.max(a, b);

// callback is invoked for each element in the array starting at index 0
[1, 100].reduce(getMax, 50); // 100
[ 50].reduce(getMax, 10); // 50

// callback is invoked once for element at index 1
[1, 100].reduce(getMax); // 100

// callback is not invoked
[ 50].reduce(getMax); // 50
[ ].reduce(getMax, 1); // 1

[ ].reduce(getMax); // TypeError
