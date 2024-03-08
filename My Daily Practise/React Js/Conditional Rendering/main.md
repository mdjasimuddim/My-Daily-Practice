## Conditional Rendering
#### Ternary Operator
{ locale === 'bn-BD' ? ( <Button change = {this.handleClick} locale = "en-US">Click Here</Button>):(<Button  change = {this.handleClick} locale = "en-US">Click Here</Button>) }

_if we want to declare conditional statement outside of the return, then we can use if-else block and we can not declare it within a return block in React._

