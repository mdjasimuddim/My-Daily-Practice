``` React Dom is valued Javascript Object```

### Normal Jsx
``` const element = <h1>Hello World </h1> ```
### Behind the seen, React Works like
``` const element = document.createElement(h1, null, 'Hello World!'); ```

```javascript
const index = 0;
const element = (<h1 className = "heading" tabIndex = {index} >
    <span className = "text">Hello World!</span>
    <img src = " " />
</h1>)
### Equivalent Above code, behind the seen
element = {
  type:'h1',
  props:{
    className:'heading',
    tabIndex:0,
    children:[
      {
        type:'span',
        props:{
          className:'text'
      }
    },
    {
        type:'img',
        props:{
          src:''
      }
    },

    ]
  }
}
```
## Jsx
- JSX is a syntax extension for JavaScript that allows you to write HTML-like code in your JavaScript code
- It is commonly used in React applications to define the structure and content of UI components.
- JSX is not a separate language, but a preprocessor that converts the HTML-like code into plain JavaScript.
- It enables you to use JavaScript expressions within your HTML-like code, making it easier to dynamically generate content.
- JSX can improve code readability and maintainability by allowing developers to write declarative, intuitive code.

## Jsx conventions
- You need to return a single parent element in JSX
You can implement JS directly in JSX
- All Tags Self-close in JSX
- ClassName and HTMLFor, not class and for in JSX
- Write all HTML Attributes in camelCase in JSX
- Write Inline Styles as Objects in JSX
