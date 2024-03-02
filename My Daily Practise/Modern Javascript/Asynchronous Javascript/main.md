## Blocking Behavior / Javasript Synchronous
```javascript
const processOrder = (customer) =>{
    console.log(`processing order for customer 1`);
    var currentTime = new Date().getTime();
    while(currentTime + 3000 >= new Date().getTime());
    console.log(`order processed for customer 1`);
}
console.log(`take order for customer 1`);
processOrder();
console.log(`completed order for customer 1`);
```
__Event loop means compare between call stack and callback unique__
## Asynchornous Javascript
Javascript will not wait to do any work and go to the next code.
```javascript
const processOrder = (customer) =>{
    console.log(`processing order for customer 1`);
    setTimeout(()=>{
        console.log(`cooking completed`);
    }, 3000)
    console.log(`order processed for customer 1`);
}
console.log(`take order for customer 1`);
processOrder();
console.log(`completed order for customer 1`);
```
## Callback Function
Callback function is a function that will be executed after another function.
```javascript
const takeOrder = (customer, callback) =>{
    console.log(`take order for ${customer}`);
    callback(customer);
}

const processOrder = (customer, callback) => {
    console.log(`processing order for ${customer}`);
    
    setTimeOut(()=>{
        console.log(`cooking comleted`);
        console.log(`order processed for ${customer}`);
        callback(customer);
    }, 3000)
}
const completeOrder = (customer) => {
    console.log(`completed order for ${customer}`);
}

takeOrder("customer 1", (customer)=>{
    processOrder(customer, (customer)=>{
        completeOrder(customer);
    })
})
console.log(`Hello`);


```
## Promise
used to handle the asynchronous Operation and remove callback hell.
- if Operation is success, Promise will be resolved.
- if Operation is fail, Promise will be failed.

### Example - 
```javascript
const hasMeeting = false;

const meeting = new Promise((resolve, reject) =>{
    if(!hasMeeting){
        const meetingDetails = {
            name: "Technical Meeting",
            location: "Google Meet",
            time: "10.00PM"
        }
        resolve(meetingDetails);
    }else{
        reject(new Error("Meeting already scheduled!"));
    }
})
meeting
.then((res)=>{
    console.log(JSON.stringify(res));
}).catch((err)=>{
    console.log(error.message);
})

```

```javascript
const hasMeeting = false;

const meeting = new Promise((resolve, reject) =>{
    if(!hasMeeting){
        const meetingDetails = {
            name: "Technical Meeting",
            location: "Google Meet",
            time: "10.00PM"
        }
        resolve(meetingDetails);
    }else{
        reject(new Error("Meeting already scheduled!"));
    }
})
const addToCalender = (meetingDetails) => {
    const calendar = `${meetingDetails.name} was scheduled on ${meetingDetails.location} at ${meetingDetails.time}`;
    return Promise.resolve(calendar);
}
meeting
.then(addToCalender)
.then((res)=>{
    console.log(JSON.stringify(res));
}).catch((err)=>{
    console.log(error.message);
})

```

### Promises all example
```javascript
const promise1 = Promise.resolve("Promise 1 resolved");
const promise2 = Promise.resolve((resolve, reject)=>{
    setTimeout(()=>{
        resolve(`Promise 2 resolved`);
    }, 2000)
})
Promise.all([promise1, promise2]).then((res)=>{
    console.log(res);
})
```

### Promise race

```javascript
// priority for who has ahead in race
Promise.race([promise1, promise2]).then((res)=>{
    console.log(res);  // second promise  ahead than first promise
})
```

## async await
to write like the synchronous form from asynchronous.
```javascript
const hasMeeting = false;

const meeting = new Promise((resolve, reject) =>{
    if(!hasMeeting){
        const meetingDetails = {
            name: "Technical Meeting",
            location: "Google Meet",
            time: "10.00PM"
        }
        resolve(meetingDetails);
    }else{
        reject(new Error("Meeting already scheduled!"));
    }
})
const addToCalender = (meetingDetails) => {
    const calendar = `${meetingDetails.name} was scheduled on ${meetingDetails.location} at ${meetingDetails.time}`;
    return Promise.resolve(calendar);
}
async function myMeeting(){
   try{
     const meetingDetails = await meeting;
    const calendar = await addToCalendar(meetingDetails);
    console.log(calendar);
   }catch{
    console.log('something went wrong');
   }
}
myMeeting();


```

