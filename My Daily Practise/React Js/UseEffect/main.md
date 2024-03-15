## UseEffect Hook
- working with side effects.

## Responsibilites of React?
- Render / re-render the UI & React to user Input/Actions.
- Render the Jsx Code
- Manage State & Props
- React to Events/Input
- Evaluating the State/Props Change

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

### Side Effects in Class Component?
```javascript
import React from 'react';

class MyComponent extends React.Component {
    state = {
        count: 0,
        date: new Date(),
    };

    componentDidMount() {
        const { count } = this.state;
        document.title = `Clicked ${count} times`;
        this.interval = setInterval(this.tick, 1000);
    }

    componentDidUpdate() {
        const { count } = this.state;
        document.title = `Clicked ${count} times`;
    }

    componentWillUnmount() {
        clearInterval(this.interval);
    }

    addClick = () => {
        this.setState(({ count }) => ({
            count: count + 1,
        }));
    };

    tick = () => {
        console.log('clock ticking');
        this.setState({
            date: new Date(),
        });
    };

    render() {
        const { date } = this.state;

        return (
            <div>
                <p>Time: {date.toLocaleTimeString()}</p>
                <p>
                    <button type="button" onClick={this.addClick}>
                        Click
                    </button>
                </p>
            </div>
        );
    }
}

export default MyComponent;
```
### Side Effects or useEffect-every Render in Functional Component?
```javascript
import { useEffect, useState } from 'react';

export default function MyComponent() {
    const [count, setCount] = useState(0);
    const [date, setDate] = useState(new Date());

    const tick = () => {
        console.log(`clock ticking!`);
        setDate(new Date());
    };

    useEffect(() => {
        console.log('updating document title');
        document.title = `Clicked ${count} times`;
    }, [count]);

    useEffect(() => {
        console.log('starting timer');
        const interval = setInterval(tick, 1000);

        // do the cleanup - stop the timer
        return () => {
            console.log('component unmounted');
            clearInterval(interval);
        };
    }, []);

    const addClick = () => {
        setCount((prevCount) => prevCount + 1);
    };

    return (
        <div>
            <p>Time: {date.toLocaleTimeString()}</p>
            <p>
                <button type="button" onClick={addClick}>
                    Click
                </button>
            </p>
        </div>
    );
}
```
`Inside useEffect function will be run as far as the component render.`

