React hook = special function that allows functional components 
to use React features without writing class components

<h2>useState()</h2>
A React hook that allows the creation of a stateful variable 
and a setter function to update its value in the Virtual DOM. 

✔️Returns an array with two elements: `[name, setName]`

If we want to make a change in a stateful variable, we will use `set...` function:

```jsx
import {useState} from "react"   //must import the function

function Component() {
  const [name, setName] = useState();

  const updateName = () => {
      setName('Jessica');
    }
  return(
      <p>Name: {name}</p>
      <button onClick={updateName}>Set Name</button>
  );
}
//When button is clicked, name Jessica will appear
```
Initial state:
```jsx
const [name, setName] = useState('Name');
//this will be like a placeholder before the variable changes
```
Toggle:
```jsx
const [isOn, setIsOn] = useState(false);

const toggleSwitch = () => {
  setIsOn(!isOn);    //if true --> false, if false --> true
}
```

<h3>Updater Function:</h3>

A function passed as an argument to `setState()` usually. For example:

Instead of `setYear(year+1)`, we write `setYear(updater function)`.

✔️Allow for safe updates based on the previous state.

✔️Used with multiple state updates and asynchronous functions.

If we write `setState()` function multiple times in the same function to update the same state variable, React batches together state updates for performance reasons:
```jsx
function increment(){
  setCount(count+1);
  setCount(count+1);
  setCount(count+1);
}
//Only adds 1
```
⭕Uses the *current* state to calculate the *next* state.

So, we must use updater function, for example, arrow function to use `setState()` multiple times and React puts it in a queue:
```jsx
function increment(){
  setCount(c => c + 1);
  setCount(c => c + 1);
  setCount(c => c + 1);
}
```
⭕Uses the *pending* state to calculate the *next* state.

<h5>Update OBJECT</h5>

For example:
```jsx
const [car, setCar] = useState({year: 2024, make: 'Ford', model: 'Mustang'});

function handleYearChange(event) {
    setCar(c => ({...c, year: event.target.value}));
  }
  function handleMakeChange(event) {
    setCar(c => ({...c, make: event.target.value}));
  }
  function handleModelChange(event) {
    setCar(c => ({...c, model: event.target.value}));
  }
```
We use updater function, but adding `{}` to create an object.

✔️`...object` means remaining other object values the same.

<h5>Update ARRAY</h5>

For example:
```jsx
const [foods, setFoods] = useState(['Apple', 'Banana']);

function handleAddFood() {
  const newFood = document.getElementById('foodInput').value;
  document.getElementById('foodInput').value = "";

  setFoods(f => [...f, newFood]);
}
function handleRemoveFood(index) {
  setFoods(foods.filter((_, i) => i !== index));
}
return(
  <div>
    <ul>
      {foods.map((food, index) => 
        <li key={index} onClick={() => handleRemoveFood(index)}>{food}</li>)}
    </ul>
    <input type="text" id='foodInput' placeholder='Enter food name' />
    <button onClick={handleAddFood}>Add Food</button>
  </div>
)
```

<h2>useEffect()</h2>

React Hook that tells React DO SOME CODE WHEN ... :
- This component re-renders
- This component mounts
- The state of a value

✔️`useEffect(function, [dependencies])`

1. `useEffect(() => {})` - runs after every re-render
2. `useEffect(() => {}, [])` - runs only on mount
3. `useEffect(() => {}, [values])` - runs on mount + when value changes

<h5>Uses:</h5>

1. Event listeners
2. DOM manipulation
3. Subscription (real-time updates)
4. Fetching Data from an API
5. Clean up when a component unmounts
