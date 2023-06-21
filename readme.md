# Day-3 JS
---
## Q-1 What are promises and why do we need them?
-  Promise are use to handle async operation in JS. easy to handle callback hell, also use to handle the error.
    - basically in promise there are Three stage
        1. Pending
        2. Resolve - (then method)
        3. reject - (catch mentod)
-  initial stage of any promise is always pending.

```bash
const varPromise = new Promise((resolve, reject) => {
    if(false){
        resolve('This is New Promise One')
    }  
    else{
        reject("Promise Rejected")
    }
})

function funcPromise(){
    return new Promise((res, rej) => {
        setTimeout(() => {
            res('Promise resolve')
        })
    })
}
```
---
## Q-2 We have three promise, and we want to combine all then and catch method by using Promise.all.
- Promise.all - 
The Promise.all() static method takes an iterable of promises as input and returns a single Promise. This returned promise fulfills when all of the input's promises fulfill (including when an empty iterable is passed), with an array of the fulfillment values. It rejects when any of the input's promises rejects, with this first rejection reason.

```bash
Promise.all([varPromise, funcPromise()])
.then((data)=> console.log(data))
.catch((err) => console.log(err))

let pro1= new Promise((res,rej)=>{
    setTimeout(()=>{
     console.log("1")   
    },1000)
})
let pro2= new Promise((res,rej)=>{
    setTimeout(()=>{
     console.log("2")   
    },2000)
})
let pro3= new Promise((res,rej)=>{
    setTimeout(()=>{
     console.log("3")   
    },3000)
})
let pro4= new Promise((res,rej)=>{
    setTimeout(()=>{
     console.log("4")   
    },4000)
})
let pro5= new Promise((res,rej)=>{
    setTimeout(()=>{
     console.log("5")   
    },5000)
})

Promise.all([pro1,pro2,pro3,pro4,pro5])
.then((b)=>{
    console.log(b)
})

```
---
## Q-3 What is promise chaining?

- Its a technique to chain multiple asynchronous operation together using promises.
- Promise chaining is a technique in JavaScript to execute multiple asynchronous operations in a specific order by chaining promises together using the then method
- Multiple .then method.

```bash
function display(Num, timeout){
    return new Promise((res, rej) => {
        setTimeout(() => {
            console.log(Num);
            res('Promise Resolved...')
        }, timeout);
    })
}
display(1, 1000)
.then(() => display(2, 6000))
.then(() => display(3, 5000))
.then(() => display(4, 4000))
.then(() => display(5, 3000))
.then(() => display(6, 2000))
.then((data) => console.log('Promise Completed....'))
```
---
## Q-4 What is the DOM?
- Document object model. basically it is javascript mechanism by which we can change the document structure, style, and content.
- DOM is the data representation of the objects that comprise the structure and content of a document on the web.
 - Different method in DOM
      - Id - getElementById - return unique value
      - querySelector -  return unique value    
      - Class - getElementsByClassName 
      - tag Name - getElementsByTagName
      - querySelectorAll 
      - addEventListener - (event, callback function)

      ```bash
      let container1 = document.getElementbyId("ID")
      let container2 = document.getElementsbyClassName("class name")
      let container3 = document.getElementTag
      Name("Tag name")
      let container4 = document.querySelectAll("")

      document.addEventListener("click", myFunction);

     function myFunction() {
    document.getElementById("demo").innerHTML = "Hello World";
    }
      ```
      ---
## Q-5 What are closures? Give an example of closure?
- A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment).
    - Closure is the combination of two function (min).
    - inner function is able to excess the outer function variable but vise-varsa not possible.
    - outer func and inner func is going to create a Lixical environment.

    ```bash
    example-1
    function length(L){
    {
        function breadth(B){
            console.log(`area of the rectangle ${L*B}`)
        }
    }
    breadth(10)
   }

    length(20)
    ```
     ```bash
    example-2
    function Sum(a){
    function result(b){
        return a*b;
        }
        return result
   }
   let resultVar= Sum(10);
  let res= resultVar(20);
  console.log(res);
    ```
    ---
## Q-6 How many operators do we have in JS ?
1. Arithemic operator :-

 - Add, Sub, Multi, Div(/), Module (%), Expontial (**), increment ++, decrement--

2. Assignment Operator :-

- Assign (=), Add Assign (+=), Sub Assign (-=), (*=), (/=), (%=)

3. Bitwise Operator:-

 - Bitwise OR (|), Bitwise AND (&), Bitwise NOT (~), Left shift (<<), right shift(>>)

4. Comparision Operator
 - equal (==), strict equal (===), Not equal (!=), Strict Not equal (!==), greate than, less than, greate than equal, less than equal


5. Logical Operator
- AND (&&)
- OR (||)
- Not (!)

6. Ternary Operator
-  (Condition) ? "Execute True Condition" : "Execute False Condition"

7. typeof Operator
- return datatype
---
## Q-7 What are objects in javascript?
- Non-premitive data type
    - store date in the form of Key-Value pair saparated by colon.
    - Key - Properties : Value
```bash
//Method 1

var Obj1 = {
    name: 'John',
}

// Method 2
let Obj2 = new Object();
Obj2.age = 23;
Obj2['name']='Jane';

console.log(Obj2['name']);
```