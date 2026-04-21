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
