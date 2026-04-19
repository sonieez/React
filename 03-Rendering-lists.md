<h3>Displaying simple lists</h3>

We can display simple lists with `map(<function>)` function: 
```jsx
const fruits = ["apple", 'orange', 'banana', 'coconut', 'pineapple'];
const listItems = fruits.map(fruit => <li>{fruit}</li>);
 
return(<ol>{listItems}</ol>);
//or
return(<ul>{listItems}</ul>);
```

<h3>Displaying lists of objects</h3>

```jsx
const fruits = [{id: 1, name: "apple"}, {id: 2, name: 'orange'}, {id: 3, name: 'banana'}];

const listItems = fruits.map(fruit => 
    <li key={fruit.id}> {fruit.name} </li>
  );

return(<ul>{listItems}</ul>);
```
When creating elements from objects, it is required to add key(id) to each element. (`key={}`)

<h3>Filtering lists</h3>

We can filter lists with `filter(<function>)` function:
```jsx
const lowCalFruits = fruits.filter(fruit => fruit.calories < 100);
const listItems = lowCalFruits.map(lowCalFruit => 
    <li key={lowCalFruit.id}> {lowCalFruit.name}: <b>{lowCalFruit.calories}</b> </li>
  );
//or
const highCalFruits = fruits.filter(fruit => fruit.calories >= 100);
const listItems = highCalFruits.map(highCalFruit => 
    <li key={highCalFruit.id}> {highCalFruit.name}: <b>{highCalFruit.calories}</b> </li>
  );

return(<ul>{listItems}</ul>);
```

<h3>Sorting lists</h3>

We use `sort(<function>)` when sorting a list:

```jsx
list.sort((a,b) => /*code*/);
//a - first item, b - second item
```
📍For Reverse sorting, change a and b order in the *code*.

✔️Alphabetical sort:
```jsx
const fruits = [{id: 1, name: "apple"}, {id: 2, name: 'orange'}, {id: 3, name: 'banana'}];
fruits.sort((a, b) => a.name.localeCompare(b.name));

//Reverse:
fruits.sort((a, b) => b.name.localeCompare(a.name));
```

✔️Numerical sort:
```jsx
const fruits = [{id: 1, name: "apple", calories: 95}, 
                  {id: 2, name: 'orange', calories: 45}, 
                  {id: 3, name: 'banana', calories: 105}];

fruits.sort((a, b) => a.calories - b.calories);

//Reverse:
fruits.sort((a, b) => b.calories - a.calories);
```
