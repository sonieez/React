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
