React lets you add event handlers to your JSX. 
Event handlers are your own functions that will be triggered in response to interactions like 
clicking, hovering, focusing form inputs, and so on.

<h2>Click events</h2>

Click event = an interaction when a user clicks on a specific element.

✔️We can respond to clicks by passing a callback to the `onClick` event handler.

```jsx
function Button() {
  const handleClick = () => console.log('OUCH!');

  return(<button onClick={handleClick}>Click me</button>);   //simply runs the function
}
export default Button
```
We defined the handleClick function and then passed it as a prop to <button>.  
`handleClick` is an event handler. Event handler functions:

- Are usually defined inside your components.
- Have names that start with handle, followed by the name of the event.

With argument (prop):
```jsx
function Button() {
  const handleClick = (name) => console.log(`${name} stop clicking me`);

  return(<button onClick={() => handleClick('Jessica')}>Click me</button>);

  //WRONG WAY --> onClick={handleClick2('Jeesica')}  
}
export default Button
```

<h3>Event</h3>

To use the built-in event functions or methods we can save the event object inside the 
argument and use it:

```jsx
function Button() {
  const handleClick = (e) => console.log(e);

  return(<button onClick={(event) => handleClick(event)}>Click me</button>);
  //it will save click event argument, then pass it to the function for using as e.
}
```

To change the context:
```jsx
function Button() {
  const handleClick = (event) => event.target.textContent = 'OUCH!';

  return(<button onClick={(event) => handleClick(event)}>Click me</button>);
}
```

To make the clicked object (for instance, an image) disappear:

```jsx
function Picture() {
  const handleClick = (event) => event.target.style.display = 'none';

  return(
    <img onClick={(event) => handleClick(event)} src='...'></img>
  );
}
export default Picture
```

<h3>Double Click</h3>

`onDoubleClick` works only when an element is clicked twice:
```jsx
<button onDoubleClick={(event) => handleClick(event)}>Click me</button>
```
