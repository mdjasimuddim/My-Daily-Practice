`useMemo and useCallBack Hook is used to optimize the performance`   
_Multiple re-render affect in performance_   
__To Avoid multiple times re-render in different component, we use firstly React.memo()__   
```javascript
import React, { useState } from 'react'
import Button from './Button';
import Title from './Title';
import ShowCount from './ShowCount';

const MainCallback = () => {
    const [count1, setCount1] = useState(0);
    const [count2, setCount2] = useState(0);

    const incrementByOne = () => {
        setCount1((prevCount)=> prevCount + 1);
    }
    const incrementByFive = () => {
        setCount2((prevCount)=> prevCount + 5);
    }
  return (
    <div>
        <Title />
        {/* <ShowCount count = {count1} title = "Counter 1" /> */}
        <ShowCount count = {count1} title = "Counter 1" /> 
        <Button handleClick = {incrementByOne}>Increment By One</Button>
        <hr />
        <ShowCount count = {count2} title = "Counter 2" /> 
        <Button handleClick = {incrementByFive}>Increment By Five</Button>
    </div>
  )
}

export default MainCallback
```
```javascript
import React from 'react'

const Title = () => {
    console.log('Rendering Title.......');
  return (
    <h2>useCallBack Hook Tutorial</h2>
  )
}

export default React.memo(Title);
```

```javascript
import React from 'react';

function ShowCount({ count, title }) {
    console.log(`rendering ${title}....`);

    return (
        <p>
            {title} is {count}
        </p>
    );
}

export default React.memo(ShowCount);
```

```javascript
import React from 'react';

function Button({ handleClick, children }) {
    console.log(`rendering button ${children}`);

    return (
        <p>
            <button type="button" onClick={handleClick}>
                {children}
            </button>
        </p>
    );
}

export default React.memo(Button);
```

`if change the props or state, react will be re-render or render`  
__useCallBack can remove extra rendering in react component__   
```javascript
import React, { useState , useCallback } from 'react'
import Button from './Button';
import Title from './Title';
import ShowCount from './ShowCount';

const MainCallback = () => {
    const [count1, setCount1] = useState(0);
    const [count2, setCount2] = useState(0);

    const incrementByOne = useCallback(() => {
        setCount1((prevCount)=> prevCount + 1);
    },[])
    const incrementByFive = useCallback(() => {
        setCount2((prevCount)=> prevCount + 5);
    },[])
  return (
    <div>
        <Title />
        {/* <ShowCount count = {count1} title = "Counter 1" /> */}
        <ShowCount count = {count1} title = "Counter 1" /> 
        <Button handleClick = {incrementByOne}>Increment By One</Button>
        <hr />
        <ShowCount count = {count2} title = "Counter 2" /> 
        <Button handleClick = {incrementByFive}>Increment By Five</Button>
    </div>
  )
}

export default MainCallback
```
### useCallback
remain a callback function and will be forgotten when the depend on value changes.

### useMemo
remain a return value of the function and will be forgotten when the depend on value changes.
