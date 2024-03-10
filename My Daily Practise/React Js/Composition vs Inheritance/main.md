## Inheritance
### For parent Class 
```Javascript
import React, { Component } from 'react'

export default class Emoji extends Component {
    addEmoji = (text, emoji) => `${emoji} ${text} ${emoji}`;
  render(override) {
    let text = 'I am the Emoji Component';
    if(override) text = override;
    return (
      <div>{text}</div>
    )
  }
}
```
### Inherited class
```javascript
import React, { Component } from 'react'
import Emoji from './Emoji'

export default class Text extends Emoji {
    constructor(props) {
      super(props);
    }
  render() {
    const decoredText = this.addEmoji('I am JavaScript Programming Language', 'Love');
    return super.render(decoredText);
  }
}
```

### Root directory
```javascript
import React from 'react'
import Text from './assets/Components/inheritance/Text'

const App = () => {
  return (
    <div>
      <Text />
    </div>
  )
}

export default App
```

`React recommend to avoid inheritance because `
- Components are tightly coupled.   
- From child, it's not clear what parent does
- not clear about the parent child relation
- future components are tightly coupled.
- nested extend - child that already extend their parent component.

## Composition
`React recommend to use composition`

### Main Directory
```javascript
import React from 'react'
import Emoji from './assets/Components/composition/Emoji'
import Text from './assets/Components/composition/Text'
import Brackets from './assets/Components/composition/Brackets'

const App = () => {
  return (
    <div>
      <Emoji >
      {({ addEmoji }) => (
                <Brackets>
                    {({ addBracket }) => <Text addEmoji={addEmoji} addBracket={addBracket} />}
                </Brackets>
            )}
      </Emoji>
    </div>
  )
}

export default App
```

### Parent Component
```javascript
import React, { Component } from 'react'

export default class Emoji extends Component {
    addEmoji = (text, emoji) => `${emoji} ${text} ${emoji}`;
  render() {
    return this.props.children({addEmoji: this.addEmoji})
  }
}

```


### Parent Component
```javascript
import React from 'react';

export default class Brackets extends React.Component {
    addBracket = (text) => `[ ${text} ]`;

    render() {
        return this.props.children({ addBracket: this.addBracket });
    }
}

```
### Child Component
```javascript

const Text = ({addEmoji, addBracket}) => {
    let text = 'I am Javascript Programming language';
    if(addEmoji){
        text = addEmoji(text, 'love');
    }
    if(addBracket){
        text = addBracket(text);
    }
  return (
    <div>{text}</div>
  )
}

export default Text
```
