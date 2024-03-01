## implicit Binding
### Example
```javascript
var person = {
    name: 'jasim',
    age: 26,
    printPersonName:function(){
        console.log(`My name is ${this.name}`);
    } 
}
person.printPersonName();
// In this case, Two things to be reminder
- where the function is called
- Have the (.) is used and what will be access before (.)
```

```javascript
var printPlayerNameFunction = function(obj){
    obj.printPlayerName = function(){
        console.log(this.name);
    }
}

var Jasim = {
    name: 'Jasim',
    age : 26
}
var Rahim = {
    name: 'Rahim',
    age : 27
}
printPlayerNameFunction(Jasim);
Jasim.printPlayerName()
printPlayerNameFunction(Rahim);
Rahim.printPlayerName()
```


```javascript
// In Factory function 
var Person = function(name, age){
    return{
        name,
        age,
        printName(){
            console.log(this.name);
        }
    }
}
var Jasim = Person('Jasim', 25);
Jasim.printName();

```

```javascript
var Person = function(name, age){
    return{
        name,
        age,
        printName(){
            console.log(this.name);
        },
        father:{
            name:'Md. Emarul Haque',
            printName:function(){
                console.log(this.name);
            }
        }
    }
}
var Jasim = Person('Jasim', 25);
Jasim.printName();
Jasim.father.printName();

```


## explicit Binding
### call, apply, bind
```javascript 
// call
var printName = function(v1, v2, v3){
    console.log(`${this.name} is ${v1}, ${v2} & ${v3}`);
}
var sakib = {
    name:"sakib",
    age: 35
}
var v1 = "Handsome";
var v2 = "All-rounder",
var v3 = "Best Player"
printName.call(sakib, v1, v2, v3);
```

```javascript 
// apply
var printName = function(v1, v2, v3){
    console.log(`${this.name} is ${v1}, ${v2} & ${v3}`);
}
var sakib = {
    name:"sakib",
    age: 35
}
var v1 = "Handsome";
var v2 = "All-rounder";
var v3 = "Best Player";
var v = [v1, v2, v3];
printName.call(sakib, v);
```

```javascript 
// apply
var printName = function(v1, v2, v3){
    console.log(`${this.name} is ${v1}, ${v2} & ${v3}`);
}
var sakib = {
    name:"sakib",
    age: 35
}
var v1 = "Handsome";
var v2 = "All-rounder";
var v3 = "Best Player";
const func = printName.bind(sakib, v1, v2, v3);
func();

```
## new Binding
```javascript
function Person(name, age){
    // let this = Object.create(null);
    this.name = name;
    this.age = age;
    console.log(`${this.name} is ${this.age} years old`);
    //return this;
}
var Jasim = new Person("Jasim", 26);
```
## window Binding
```javascript
var printName = function(){
    console.log(this.name);  //undefined
}
var Jasim = {
    name:'jasim'
}

// it is a bad practice in javascript and solve this issue using "use strict"
printName();
```