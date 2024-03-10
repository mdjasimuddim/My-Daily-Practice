### Top Most Root
```javascript
import ClickCounter from './components/ClickCounter';
import Counter from './components/Counter';
import HoverCounter from './components/HoverCounter';

function App() {
    return (
        <div className="app">
            <Counter>
                {(counter, incrementCount) => (
                    <ClickCounter count={counter} incrementCount={incrementCount} />
                )}
            </Counter>
            <Counter>
                {(counter, incrementCount) => (
                    <HoverCounter count={counter} incrementCount={incrementCount} />
                )}
            </Counter>
        </div>
    );
}

export default App;
```

```javascript
import React from 'react';

export default function ClickCounter({ count, incrementCount }) {
    return (
        <div>
            <button type="button" onClick={incrementCount}>
                Clicked {count} times
            </button>
        </div>
    );
}
```
### Render Props
```javascript
import React from 'react';

class Counter extends React.Component {
    state = {
        count: 0,
    };

    incrementCount = () => {
        this.setState((prevState) => ({ count: prevState.count + 1 }));
    };

    render() {
        const { children } = this.props;
        const { count } = this.state;
        return children(count, this.incrementCount);
    }
}

export default Counter;
```


```javascript
import React from 'react';

export default function HoverCounter({ count, incrementCount }) {
    return (
        <div>
            <h1 onMouseOver={incrementCount}>Hovered {count} times</h1>
        </div>
    );
}
```
