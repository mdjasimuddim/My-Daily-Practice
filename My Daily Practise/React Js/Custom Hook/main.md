### Why custom hook ? 
- start with use keyword
- share logic within different component
- solve many hard problem


### Example - useWindowObject.jsx
```javascript
import React, {useState, useEffect} from 'react'

const useWindowObject = () => {
    const [onSmallScreen, setOnSmallScreen] = useState(false);

    const checkSreenSize = () => {
        setOnSmallScreen(window.innerWidth < 768);
    }
    useEffect(()=> {
        checkSreenSize();
        window.addEventListener('resize', checkSreenSize);

        return () => window.removeEventListener('resize', checkSreenSize);
    }, [])
  return onSmallScreen;
}

export default useWindowObject
```

### share this component in different Component
```javascript
import React, { useEffect, useState } from 'react'
import useWindowObject from '../useWindowObject'

const LayoutComponentOne = () => {
    const onSmallScreen = useWindowObject();
  return (
    <div>
        <h1>You are browsing on {onSmallScreen ? "small":"large"} size.</h1>
    </div>
  )
}

export default LayoutComponentOne
```
### share this component in different Component
```javascript
import React, { useEffect, useState } from 'react'
import useWindowObject from '../useWindowObject'

const LayoutComponentTwo = () => {
    const onSmallScreen = useWindowObject();
  return (
    <div className= {onSmallScreen ? "small":"large"} >
        <h1>You are browsing on another size.</h1>
    </div>
  )
}

export default LayoutComponentTwo
```

