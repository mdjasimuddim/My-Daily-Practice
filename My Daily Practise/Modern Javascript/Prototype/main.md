## Prototype
Prototype is a property of any Javascript Function that is point to an Object.

```javascript
function Person(name, age){
    let person = Object.create(Person.prototype);
    person.name = name;
    person.age = age;
}
Person.prototype = {
    eat(){
        console.log(`Person is eating`);
    }

    play(){
        console.log(`Person is playing`);
    }
    sleep(){
        console.log(`Person is sleeping`);
    }
}

const sakib = Person("sakib", 35);
console.log(sakib.play());


```

### Same code using new and this keyword
```javascript
function Person(name, age){
    this.name = name;
    this.age = age;
}


Person.prototype = {
    eat(){
        console.log(`Person is eating`);
    }

    play(){
        console.log(`Person is playing`);
    }
    sleep(){
        console.log(`Person is sleeping`);
    }
}

```

### same code using class method
```javascript
class Person{
    constructor(name, age){
        this.name = name;
        this.age = age;
    }
    eat(){
        console.log(`Person is eating`);
    }

    play(){
        console.log(`Person is playing`);
    }
    sleep(){
        console.log(`Person is sleeping`);
    }
}
```

```javascript
let persons = new Array();
console.log(persons.prototype);
```

```javascript
// Prototype chaining
var f = function person() {};
Object.prototype.sumit = function(){
    console.log("i am sumit");
}
var p = {};
p.sumit();

```

## Javascript Inheritance Before Es6 and now
```javascript
function Person(name, age){
    this.name = name;
    this.age = age;
}

function Cricketer(name, age, type, country)
{
    Person.call(this);
    this.name = name;
    this.age = age;
    this.type = type;
    this.country = country;
}

Person.prototype = {
    eat:function(){
        console.log(`${this.name} is eating`);
    }
}

Cricketer.prototype = Object.create(Person.prototype);
Cricketer.prototype.constructor = Cricketer;
Cricketer.prototype.play = function(){
    console.log(`${this.name} is playing`);
};

let Sakib = new Cricketer("Jasim", 26, "Student", "Bangladesh");

console.log(Sakib.play());
```

```javascript
// modern js
class Person{
    constructor(name, age){
        this.name = name;
        this.age = age;
    }
    eat(){
        console.log(`${this.name} is eating `);
    }
}
class Cricketer{
    constructor(name, age, type, country){
        super(name, age);
        this.name = name;
        this.age = age;
        this.type = type;
        this.country = country;
    }
    play(){
        console.log(`${this.name} is playig`);
    }
}
let sakib = new Cricketer("Sakib", 35, "All-Rounder", "Bangladesh");
```
## getter and setter Method

```javascript
class Person{
    constructor(name, age){
        this.name = name;  //property
        this.age = age;
    }
    eat(){  //method
        console.log(`${this.name} is eating`);
    }
    //getter
    get getName(){
        return "Sumit";
    }

    //setter
    set setName(name){
        this.name = name;
    }

}
let Jasim = new Person("jasim", 25);
// access to getter Method
console.log(Jasim.getName);
//access to setter Method 
Jasim.setName = "Rahim";
console.log(Jasim.name);
```

## Static Method
```javascript
 class Person{
    constructor(name, age){
        this.name = name;  //property
        this.age = age;
    }
    eat(){  //method
        console.log(`${this.name} is eating`);
    }
    static isEqualAge(circketer1, cricketer2){
        return cricketer1.age === cricketer2.age;
        // if you use this, here this refers to the person object.
    }
 }

let sakib = new Person("Sakib", 35);
let tamim = new Person("Tamim", 35);
// it can not be accessable
Person.eat()
// But using Static, it can be accessable
console.log(Person.isEqualAge(sakib, tamim)); // 
```

## Polymorphism
When inherited class or child class override the method of parent class then it is called to Polymorphism   



### Example of Polymorphism
```javascript
class Person{
    constructor(name, age){
        this.name = name;
        this.age = age;
    }
    play(){
        console.log(`${this.name} is playing`);
    }
}

class Cricketer extends Person{
    constructor(name, age, type, country){
        super(name, age);
        this.name = name;
        this.age = age;
        this.type = type;
        this.country = country;
    }

    play(){
        super.play();   // inheritate the Person Class function
        console.log(`${this.name} is playing Cricket`);
    }
}
let Tamim = new Cricketer("Tamim", 35, "All Rounder", "Bangladesh");
Tamim.play();

```