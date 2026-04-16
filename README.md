# React

React = external library that helps us create websites easier

<h3>JSX</h3>
JSX (JavaScript XML) is a syntax extension for JavaScript, primarily used with React. It lets you write HTML-like code directly inside JavaScript files.

Features:

✔️You can embed JavaScript expressions inside `{}`:  
```jsx
function Food(){
  const food1 = 'Orange';
  const food2 = 'Banana';

  return(
    <ul>
      <li>Apple</li>
      <li>{food1}</li>
      <li>{food2.toUpperCase()}</li>
    </ul>
  );
}

export default Food
```
✔️It uses `className` instead of `class`, and `camelCase` for attributes (`onClick`, `onChange`)
