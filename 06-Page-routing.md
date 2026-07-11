<h4>To connect pages in React:</h4>

1. Firstly we need to download 'react-router-dom' package

2. Then, in the `main.jsx` component, we wrap App component with BrowserRouter:
```jsx
import {BrowserRouter} from 'react-router-dom'

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </StrictMode>
)
```

3. Then, in the `App.jsx` component:
```jsx
import { Routes, Route } from 'react-router-dom'
```
and we add Routes:
```jsx
<Routes>
  <Route path='/' element={<Home />}/> 
  <Route path='/favorites' element={<Favorites />}/>  //page name with its Component
</Routes>
```

4. Lastly, to add linking to the pages, in another Component (for example NavBar):
```jsx
import { Link } from "react-router-dom"
```
and add Links:
```jsx
<Link to='/' className='nav-link'>Home</Link>
<Link to='/favorites' className='nav-link'>Favorites</Link>
```
then again in `App.jsx` add our Linking Component normally:
```jsx
<NavBar />
```
