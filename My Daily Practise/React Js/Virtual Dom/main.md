## Reconciliation
Reconciliation is React's way of diffing the virtual DOM tree with the updated virtual DOM to determine the most efficient way to update the real DOM.

## Dom and virtual Dom
Real DOM is the actual structure represented in the User Interface while Virtual DOM is the memory representation of the same.

### is Dom slow?
No, After changing the dom when we see it in the browser, there will be a process and the process will be slow.

#### Dom is our structure of the webpage object model.
#### CssOM is the webpage style model.

### How can we recover it ?
(I) Do Batch Update
(II) Use less Dom Operation

### Example
```javascript
let array = [];
let increment = 0;
let container = document.querySelector('.container'):
// fast
while(increment < 1000)
{
  array.push(++increment);
}
container.innerHTML = array.join(' ');
```
```javascript
let array = [];
let increment = 0;
let container = document.querySelector('.container'):
// slow
while(increment < 10000)
{
  increment++;
  container.innerHTML = ' ' + increment;
}
container.innerHTML = array.join(' ');
```
`Without Virtual Dom, we can Batch Update`

## What to do Virtual Dom ?
- React make his own world or different Dom
- will be work with Javascript Object.
- Will make simple Javasript Object on Browser
- Replicate the Dom of Browser
