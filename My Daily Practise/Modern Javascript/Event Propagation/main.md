## Event Propagation
Technique of Event Propagation
- Event Bubbling
- Event Capturing
- Event Delegation

Event Bubbling    
    - Default behavior of javascript--Direction from child to parent

```event.target means the targetted element```   
```javascript
const parent = document.getElementById('parent');
const form = document.getElementById('form');
const button = document.getElementById('button');

parent.addEventListener("click", listener);

form.addEventListener("click", listener);

button.addEventListener("click", listener);

function listener(event){
    console.log(event.target);   // 3 button
}
```
```event.currentTarget means the current targetted element```
```javascript
const parent = document.getElementById('parent');
const form = document.getElementById('form');
const button = document.getElementById('button');

parent.addEventListener("click", listener);

form.addEventListener("click", listener);

button.addEventListener("click", listener);

function listener(event){
    console.log(event.currentTarget); //button, form, parent
}

```

```event.currentTarget and this are same```
```javascript
const parent = document.getElementById('parent');
const form = document.getElementById('form');
const button = document.getElementById('button');

parent.addEventListener("click", listener);

form.addEventListener("click", listener);

button.addEventListener("click", listener);

function listener(event){
    console.log(event.currentTarget === this); //true
}

```
### Event Capturing - Direction from parent to child
// third parameter true means capturing working
```javascript
const parent = document.getElementById('parent');
const form = document.getElementById('form');
const button = document.getElementById('button');

parent.addEventListener("click", listener, {
    capture:true
});

form.addEventListener("click", listener, {
    capture:true
});

button.addEventListener("click", listener, {
    capture:true
});

function listener(event){
    console.log(event.currentTarget.tagname);   // div, form, button tag
    //console.log(this.tagname);  
}

```
we can write only true in third parameter
```javascript
const parent = document.getElementById('parent');
const form = document.getElementById('form');
const button = document.getElementById('button');

parent.addEventListener("click", listener);

form.addEventListener("click", listener, true);

button.addEventListener("click", listener);

function listener(event){
    console.log(event.currentTarget.tagname);   // form, button, div tag 
}

```

