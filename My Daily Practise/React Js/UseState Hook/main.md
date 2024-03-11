### Hook management in Class Component
```javascript
import React, { Component } from 'react'

export default class ClassTodo extends Component {
    state = {
        todo:'',
        warning:null
    };
    handleInput = (e) => {
        const inputValue = e.target.value;
        const warning = inputValue.includes('.js') ?
        "You need to Javascript skill to complete the task. Do you have it ?":null;
        this.setState({
            todo:inputValue,
            warning
        })
    }
  render() {
    const {todo, warning} = this.state;
    return (
      <div>
        <p>{todo}</p>
        <p>
            <textarea name = "todo" value={todo} onChange={this.handleInput} />
        </p>
        <hr />
        <h2>{warning || "Good Choice"}</h2>
      </div>
    )
  }
}

```

### State Management in Functional Component using useState
- useState is a buildin Object that is used to hold data or information in your component.
```javascript
import React, { useState } from 'react'

function FunctionalTodo(){
  const [todo, setTodo] = useState("");
  const [missing, setMissing] = useState(null);
  let inputChange = (e) => {
    const inputValue = e.target.value;
    const updatedMissing = inputValue.includes('.js') ? "You have to learn JavaScript":null;
    setTodo(e.target.value);
    setMissing(updatedMissing);
  }
    return (
      <div>
        <p>{todo}</p>
        <p>
          <textarea value = {todo} name = "todo" onChange={inputChange} />
        </p>
        <p>{missing || "Good Choice"}</p>
      </div>
    )
}
export default FunctionalTodo;

```

### useState with Object/Array
```javascript
import React, { useState } from 'react'

 function Todo() {
    const [todo, setTodo] = useState({
      title:'',
      description:''
    })
    const {title, description} = todo;
    return (
      <div>
        <p>{title}</p>
        <p>
            <input name = "todo" value={title} onChange={(e)=>setTodo({
              ...todo,
              title:e.target.value
            })} />
        </p>
        <p>
            <textarea name = "todo" value={description} onChange={(e)=>setTodo({
              ...todo,
              description:e.target.value
            })} />
        </p>
      </div>
    )
}
export default Todo;
```
### useState with Previous State
```javascript
import React, { useState } from 'react'

const Increment = () => {
    const [count, setCount] = useState(0);
  return (
    <div>
        {count}
        <p>
            <button type='button' onClick={()=> setCount((prevState)=> prevState + 1)}>
                Add One
            </button>
        </p>
        // This is not the correct way in React
        <p>
            <button type='button' onClick={()=>setCount(count+1)}>
                Add Two
            </button>
        </p>
    </div>
  )
}

export default Increment
```
