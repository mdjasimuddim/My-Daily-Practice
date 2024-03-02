## Functional Programming
Pass function as a parameter of another function or return a function from a function or both.   


## Higher Order Function
we can store a function in a variable or Pass function as a parameter of another function or return a function from a function or both.   

__Functional Programming__
```javascript
function sayHello(){
    return function(){
        console.log('Hello World!');
    }
}
sayHello()();
```

__Example 1 without higher order function__
```javascript
var numbers = [1, 2, 3, 4];
var result = [];

for(let i = 0; i < numbers.length; i++){
    result.push(numbers[i]*2);
}
console.log(result);

```

__Example 2 with higher order function__
```javascript
var numbers = [1, 2, 3];
var result = numbers.map((number)=> number * 2);
console.log(result);
```
__Example 3 without higher order function__
```javascript
var players = [
    {
        name:'Rahim',
        age : 33
    },
    {
        name:'Karim',
        age : 30
    },
    {
        name:'Jasim',
        age : 26
    },
    {
        name:'Maruf',
        age : 24
    }
]
var results = [];
for(let i = 0 ; i < players.length; i++){
    if(players[i].age >= 30){
        results.push(player[i]);
    }
}
console.log(results);
```

__Example 4 with higher order function__
```javascript
var players = [
    {
        name:'Rahim',
        age : 33
    },
    {
        name:'Karim',
        age : 30
    },
    {
        name:'Jasim',
        age : 26
    },
    {
        name:'Maruf',
        age : 24
    }
]
let results = players.filter(function(item){
    return item.age >= 30;
})
console.log(results);
```

__Example 5, Our own map function__
```javascript
const languages = ['Javascript', 'PHP', 'Python', 'C'];

function mapFunc(arr, fn){
    const newArr = [];
    for(let i = 0; i< arr.length; i++){
        newArr.push(fn(arr[i]))
    }
    return newArr;
}
let myArr = mapFunc(languages, function(language){
    return language.length;
});
console.log(myArr);
```







