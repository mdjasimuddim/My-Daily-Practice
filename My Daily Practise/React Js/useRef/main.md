### How to use useRef ?
```javascript
import React, { useEffect, useRef } from 'react'
import Input from './Input'

const Form = () => {
    const inputRef = useRef(null);
    useEffect(()=>{
      console.log(inputRef.current.focus());
    },[])
  return (
    <div>
        <p>
            <Input ref={inputRef} type='text' placeholder='Enter for something' />
        </p>
    </div>
  )
}

export default Form
```
### How to use forwardRef ?
```javascript
import React from 'react'

const Input = ({text, placeholder}, ref) => {   // get the ref as a second parameter
  return <input ref={ref} type={text} placeholder={placeholder} />
}
const forwardedInput = React.forwardRef(Input);

export default forwardedInput;
```
### useRef as a storage ?
```javascript
import React, { useEffect, useRef, useState } from 'react'

const Time = () => {
    const [date, setDate] = useState(new Date());
    const buttonRef = useRef();

    const tick = () => {
        setDate(new Date());
    }

    useEffect(()=>{
        buttonRef.current = setInterval(tick, 1000);

        return () => {
            clearInterval(buttonRef.current);
        }
    })
  return (
    <div>
        <p>Time : {date.toLocaleTimeString()}</p>
        <p>
            <button type='button' onClick = {()=> clearInterval(buttonRef.current)}>
                cleanUp
            </button>
        </p>
    </div>
  )
}

export default Time
```
