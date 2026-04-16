React apps are made out of **components**. 
A component is a piece of the UI (user interface) that has its own logic and appearance. 
A component can be as small as a button, or as large as an entire page.

✔️React components are JavaScript functions that return markup.

<h3>Creating Components</h3>

```jsx
function MyButton() {
  return (
    <button>I'm a button</button>
  );
}
```
✔️React component names must always start with a capital letter (MyButton).

<h3>Nesting Components</h3>

```jsx
export default function MyApp() {
  return (
    <div>
      <h1>Welcome to my app</h1>
      <MyButton />
    </div>
  );
}
```

✔️Components can't return multiple JSX tags. That's why we have to wrap them into a shared parent, like 
`<div> </div>` or an empty `<> </>` wrapper.


<h3>Styling Components</h3>

There are three ways to style a component:
<ol>
  <li>External - global styles/small projects</li>
  <li>Module - individual components that have their unique styles</li>
  <li>Inline - small components with minimal styling</li>
</ol>

<h4>External</h4>

Create a seperate *css* file in the same folder, then add styles according to class names:
```jsx
//Button.jsx
function Button() {
  return(
    <button className='button'>Click me</button>
  );
}
```

```css
/*index.css*/
.button{
  color: white;
  border-radius: 5px;
  cursor: pointer;
}
```

<h4>Module</h4>

Create a seperate *module.css* file in the same folder, write styles, then import *styles* from the file:
```jsx
//Button.jsx
import styles from './Button.module.css'

function Button() {
  return(
    <button className={styles.button}>Click me</button>
  );
}
```
```css
/*Button.module.css*/
.button{
  color: white;
  border-radius: 5px;
  cursor: pointer;
}
```

<h4>Inline</h4>

Create a variable in the same function(component), write style in it, then apply it to the element:
```jsx
//Button.jsx
function Button() {

  const styles = {
    color: "white",
    borderRadius: "5px",
    cursor: "pointer"
  }
  return(
    <button style={styles}>Click me</button>
  );
}
```
