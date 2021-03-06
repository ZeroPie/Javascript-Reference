
## Terms
- State: Minimal Representation of Data in your App
- Action: Minimal Representation of Change to that Data
- Reducer: Pure function that takes the previous state and an action and returns a new state


## Principles

### How is State Changed? 
You Dispatch an Action

- Components only know they have to dispatch an action. 

### Use Pure Functions (do not modify items or have side effects)

| Dont                   | Do                   |     Do (ES6)                    | 
| ---------------------- |:--------------------:|---------------------------------|
| Pre E6                 |                      |    ES6(Spread Operator)         |
| ```list.push(0)```     | ```list.concat([0]```| ```[...list, 0]```              |
| ```splice(index,1)```  | ```slice(0, index)```| ```[...list.slice(0, index)]``` |  

### Avoid Object Mutations

| Dont                   | Do                                  |   ES7(Object Spread)        |
| ---------------------- |:--------------------:               |   --------------------------|
|<pre>todo.completed =! todo.completed<br>return todo;</pre>   |<pre>return Object.assign({}, todo, {<br> completed:!todo.completed <br>});</pre>| <pre>return { <br>...todo,<br> completed: !todo.completed <br>};</pre> |



## Examples

1) Replace single value in Array without mutating it  
  ```
  
  slice(0, index)               //Take a slice before the index
  .concat([array[index] +1])     // Concat it with a single item array with a new value
  .concat(array.slice(index +1)) // Concat it with the rest of the original Array

  ```
