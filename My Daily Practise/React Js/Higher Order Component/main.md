### Higher Order Component
- Higher Order Component is a function that takes component as a parameter and return the new Component.

### Higher order Component code
```javascript
import React from 'react';

const withCounter = (OriginalComponent) => {
    class NewComponent extends React.Component {
        state = {
            count: 0,
        };

        incrementCount = () => {
            this.setState((prevState) => ({ count: prevState.count + 1 }));
        };

        render() {
            const { count } = this.state;
            return <OriginalComponent count={count} incrementCount={this.incrementCount} />;
        }
    }
    return NewComponent;
};

export default withCounter;
```
### Child component of Hoc
```javascript
import withCounter from './HOC/withCounter';

const ClickCounter = (props) => {
    const { count, incrementCount } = props;
    return (
        <div>
            <button type="button" onClick={incrementCount}>
                Clicked {count} times
            </button>
        </div>
    );
};

export default withCounter(ClickCounter);
```

### Child component of Hoc
```javascript
import withCounter from './HOC/withCounter';

const HoverCounter = (props) => {
    const { count, incrementCount } = props;
    return (
        <div>
            <h1 onMouseOver={incrementCount}>Hovered {count} times</h1>
        </div>
    );
};

export default withCounter(HoverCounter);
```
