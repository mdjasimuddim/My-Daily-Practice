```React Components return react elements```
#### Function Component
```javascript
function Clock({locale})
{
  return(
    <h1 className = "heading">
        <span>Hello {new Date(toLocaleTimeString(locale)}</span>
    </h1>
  )
}
```
```javascript
 <Clock locale = "BD-bd" />     // React Component
 // Babel will transpile this to valid Javascript
```

#### Class Component
Class Component is used to create stateful components.

```javascript
class Clock extends React.Component{
  render(){
    return (
      <h1 className = "heading">
          <span>Hello { new Date().toLocaleTimeString(this.props.locale)}</span>
      </h1>
    )
  }
}

<Clock locale = "bn-BD" />

```
`Encapsulation means all functionalities are self-contained`












` React automatically calls the Render Method`
