## Event Delegation
Keep a Event Listener between multiple elements and After adding elements, listener will be work as like another elements.

```javascript
const list = document.getElementById('list'); // un-order list  with multiple list elements
list.addEventListener('click' (e)=>{
    if(e.target.matches("li")){
        if(e.target.innerText === "Javascript"){
            e.target.style.backgroundColor = 'yellow';
        }else{
            e.target.style.backgroundColor = 'red';
        }
    }
})
// new element create

function addElement(){
    const newElement = document.createElement('li');
    newElement.textContent = '. Net';
    list.appendChild(newElement);
}
```