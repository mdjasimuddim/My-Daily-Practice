``` React Dom is valued Javascript Object```

### Normal Jsx
``` const element = <h1>Hello World </h1> ```
### Behind the seen, React Works like
``` const element = document.createElement(h1, null, 'Hello World!'); ```

```React
const index = 0;
const element = (<h1 className = "heading" tabIndex = {index} >
    <span className = "text">Hello World!</span>
    <img src = " " />
</h1>)

#### Equivalent Above code, behind the seen
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
