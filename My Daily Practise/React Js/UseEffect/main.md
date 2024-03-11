## UseEffect Hook
- working with side effects.

### Examples of side Effects
- Fetching data from any api.
- Updating the Dom
- Setting any Subscriptions

### What are side Effects in Class Component
```javascript
componentDidMount(){
  const {count} = this.state;
  document.title = `Clicked ${count} times`;
  this.interval = setInterval(this.tick, 1000);  
}
componentDidUpdate(){
  const {count} = this.state;
  document.title = `Clicked ${count} times`;
}
componentWillUnmount(){
  const {count} = this.state;
  document.title = `Clicked ${count} times`;
}
```
### Why we avoid side effects in Class Component ?
- Repeating Code
- Unorganized Code

### Why use Effect ?
- Help us perform side effects in functional components
- solves all problems of lifecycle methods in Class Components
- Replaces componentDidMount(), componentDidUpdate() & componentWillUnmount()
