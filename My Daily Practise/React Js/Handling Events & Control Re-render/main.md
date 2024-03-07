```javascript
 const javascript = {
   name: "javascript",
   libraries: ["React", "Vue", "Angular"];
   printLibraries:function(){
      this.libraries.forEach(function(library){
          console.log(`${this.name} loves ${library}`);
        })
      }
    }
```
`Above code, ${this.name} represents window object and we don't get the accurate output, we can handle this situation using arrow function`

```javascript
 const javascript = {
   name: "javascript",
   libraries: ["React", "Vue", "Angular"];
   printLibraries:function(){
      this.libraries.forEach((library)=>{
          console.log(`${this.name} loves ${library}`);
        })
      }
    }
```
`Arrow function don't care this keyword, Arrow function comes to remove the this confusion`

#### We can handle this situation explicitly, using bind keyword
```javascript
 const javascript = {
   name: "javascript",
   libraries: ["React", "Vue", "Angular"];
   printLibraries:function(){
      this.libraries.forEach(function(library){
          console.log(`${this.name} loves ${library}`);
        }.bind(this))
      }
    }
```
#### we can store the this keyword using a variable to store this keyword
```javascript
 const javascript = {
   name: "javascript",
   libraries: ["React", "Vue", "Angular"];
   printLibraries:function(){
     let self = this
      this.libraries.forEach(function(library){
          console.log(`${this.name} loves ${library}`);
        })
      }
    }
```


