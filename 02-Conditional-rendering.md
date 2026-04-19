Conditional rendering allows you what gets rendered in your application based on certain conditions.

✔️In JSX, `{cond ? <A /> : <B />}` means “if cond, render <A />, otherwise <B />”.

✔️In JSX, `{cond && <A />}` means “if cond, render <A />, otherwise nothing”.

Example:

We can write the same code in different forms: 
```jsx
function UserGreeting(props) {
  //First
  if(props.isLoggedIn) {
    return <h2>Welcome, {props.username}</h2>
  } else{
    return <h2>Please, log in to continue</h2>
  }

  //Second
  const welcomeMessage = <h2 className="welcome-message">Welcome, {props.username}</h2>;
  const loginPrompt = <h2 className="login-prompt">Please, log in to continue, {props.username}</h2>;

  return(props.isLoggedIn ? welcomeMessage : loginPrompt);


  //Third
  return(props.isLoggedIn ? <h2 className="welcome-message">Welcome, {props.username}</h2> : <h2 className="login-prompt">Please, log in to continue, {props.username}</h2>);
}
```
