## Conditional Rendering
#### Ternary Operator
```javascript
{ locale === 'bn-BD' ? ( <Button change = {this.handleClick} locale = "en-US">Click Here</Button>):(<Button  change = {this.handleClick} locale = "en-US">Click Here</Button>) }
```

_if we want to declare conditional statement outside of the return, then we can use if-else block and we can not declare it within a return block in React._

```javascript
import React, { Component } from 'react'

export default class Form extends Component {
    state = {
        title: 'Javascript',
        text: 'Javascript is awesome',
        library:'React',
        isAwesome: true
    }
    handleChange = (e) => {
        if(e.target.type === 'text'){
            this.setState({
                title:e.target.value
            })
        } else if(e.target.type ==='textarea'){
            this.setState({
                text:e.target.value
            })
        }
        else if(e.target.type ==='select-one'){
            this.setState({
                library:e.target.value
            })
        }
        else if(e.target.type ==='checkbox'){
            this.setState({
                isAwesome:e.target.checked
            })
        }
        else {
            console.log('nothing here');
        }
    }   
    submitHandler = (e) => {
        const {title, text, library, isAwesome} = this.state;
        e.preventDefault();
        console.log(title, text, library, isAwesome);
    }

  render() {
    const {title, text, library, isAwesome} = this.state;
    return (
        <div>
            <form onSubmit={this.submitHandler}>
                <input type="text" />
                <br /><br />
                <input type="text" placeholder='Enter title' value={title} onChange={this.handleChange}   />
                <br />
                <br />
                <textarea type="text" value={text} onChange={this.handleChange}  />
                <br />
                <br />
                <select value={library} onChange={this.handleChange} >
                    <option value="React">React</option>
                    <option value="Angular">Angular</option>
                </select>
                <br />
                <br />
                <input type="checkbox" checked = {isAwesome} onChange={this.handleChange}  />
                <br />
                <br />
                <input type="submit" value="Submit" />
            </form>
        </div>
      )
  }
}


```
### Uncontrolled Components
`Uncontrolled Components are the components that are not controlled by the React state and are handled by the DOM (Document Object Model). So in order to access any value that has been entered we take the help of refs.`
### Controlled Components
`In React, Controlled Components are those in which form’s data is handled by the component’s state. It takes its current value through props and makes changes through callbacks like onClick, onChange, etc. A parent component manages its own state and passes the new values as props to the controlled component.`
