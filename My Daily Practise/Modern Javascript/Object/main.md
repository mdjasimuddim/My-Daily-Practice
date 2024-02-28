## Object
```Object -> key-value or property-value```
```javascript
const product = {
    name: 'Print T-shirt',
    price: 10,
    'is available': true
}
//Dynamically access properties
const availability = 'is available';
console.log(product.name); //Print T-shirt
console.log(product[name]);
console.log(product['is available']);
console.log(product['availability']);
``` 

### Methods
Method is a javascript function
```javascript
const product = {
    name:'print T-shirt',
    price : 10,
    'is available' : true,
    productDesc : function(){  // methods
        return `${this.name} - $${this.price}`;
    }
}
console.log(product.productDesc())
```

_we can write function in a object without function keyword_
```javascript
const product = {
    name:'print T-shirt',
    price : 10,
    'is available' : true,
    productDesc(){  // methods
        return `${this.name} - $${this.price}`;
    }
}
console.log(product.productDesc())
```

## Factory Function
Create different objects with the same properties and used for:
- to overcome code repetition.
- to overcome multiple object declaration.



```javascript
function product(name, price, availability){
    return {
        name,
        price,
        'is available':availability,
        productDesc(){
            return `${this.name} - $${this.price}`;
        }
    }
}
console.log(product('Print T-shirt', 10, true))
console.log(product('Sneakers', 60, true))
```   

## Constructor Function
Constructor calls once at the time of object creation.
To create different objects with the same properties, we would need to use the keyword "new" and the keyword "this".

```javascript
function product(name, price){
    this.name = name;
    this.price = price;
    this.productDesc = function(){
        return `${this.name} - $${this.price}`;
    }
}
const product1 = new Product('sneakers', 60);
console.log(product1);
```
