#### Difference between Class Component and Function Component?
Class Component is a stateful Component, which means a class component can have its state.

_After seeing render() function, React will be understood, we have to do re-render the virtual dom._

`State is simple Javascript Object.`   
`Super just calls the base classs constructor`

```javascript
constructor(props){
  super(props);
  this.state = {
    date: new Date()
  }
}
componentDidMount(){
  setInterval(()=> {
    this.setState({
      date: new Date()
    });
  },1000)
}
```
### We can write the above code in alternative way
```javascript
state = { date : new Date()};

componentDidMount(){
    this.clockTime =   setInterval(()=> this.trick(),1000)
}
componentWillUnmount(){
  clearInterval(this.clockTime)
}
trick() {
  this.setState({
    date: new Date()
});
}

```
`componentDidMount() runs after component has been rendered to the Dom`   

`never ever change props inside component`



