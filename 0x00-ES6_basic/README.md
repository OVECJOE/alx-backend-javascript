# ES6 Basics

> I learnt the basics of ES6 and **accomplished** the **project's objectives** below:

## Objectives

- What ES6 is
- New features introduced in ES6
- The difference between a constant and a variable
- Block-scoped variables
- Arrow functions and function parameters default to them
- Rest and spread function parameters
- String templating in ES6
- Object creation and their properties in ES6
- Iterators and for-of loops

## Tasks

1. **Const or let?**

   **Modify**

   1. function `taskFirst` to instantiate variables using `const`
   2. function `taskNext` to instantiate variables using `let`

   ```javascript
   export function taskFirst() {
     var task = "I prefer const when I can.";
     return task;
   }

   export function getLast() {
     return " is okay";
   }

   export function taskNext() {
     var combination = "But sometimes let";
     combination += getLast();

     return combination;
   }
   ```

   **Execution example:**

   ```javascript
   bob@dylan:~$ cat 0-main.js
   import { taskFirst, taskNext } from './0-constants.js';

   console.log(`${taskFirst()} ${taskNext()}`);

   bob@dylan:~$
   bob@dylan:~$ npm run dev 0-main.js
   I prefer const when I can. But sometimes let is okay
   bob@dylan:~$
   ```

1. **Block Scope**

   Given what you’ve read about `var` and hoisting, modify the variables inside the function `taskBlock` so that the variables aren’t overwritten inside the conditional block.

   ```javascript
   export default function taskBlock(trueOrFalse) {
     var task = false;
     var task2 = true;

     if (trueOrFalse) {
       var task = true;
       var task2 = false;
     }

     return [task, task2];
   }
   ```

   **Execution:**

   ```
    bob@dylan:~$ cat 1-main.js
    import taskBlock from './1-block-scoped.js';

    console.log(taskBlock(true));
    console.log(taskBlock(false));
    bob@dylan:~$
    bob@dylan:~$ npm run dev 1-main.js
    [ false, true ]
    [ false, true ]
    bob@dylan:~$
   ```

1. **Arrow functions**

   Rewrite the following standard function to use ES6’s arrow syntax of the function add (it will be an anonymous function after)

   ```javascript
   export default function getNeighborhoodsList() {
     this.sanFranciscoNeighborhoods = ["SOMA", "Union Square"];

     const self = this;
     this.addNeighborhood = function add(newNeighborhood) {
       self.sanFranciscoNeighborhoods.push(newNeighborhood);
       return self.sanFranciscoNeighborhoods;
     };
   }
   ```

   **Execution:**

   ```
    bob@dylan:~$ cat 2-main.js
    import getNeighborhoodsList from './2-arrow.js';

    const neighborhoodsList = new getNeighborhoodsList();
    const res = neighborhoodsList.addNeighborhood('Noe Valley');
    console.log(res);
    bob@dylan:~$
    bob@dylan:~$ npm run dev 2-main.js
    [ 'SOMA', 'Union Square', 'Noe Valley' ]
    bob@dylan:~$
   ```

1. **Parameter defaults**

   Condense the internals of the following function to 1 line - without changing the name of each function/variable.

   > Hint: The key here to define default parameter values for the function parameters.

   ```javascript
   export default function getSumOfHoods(
     initialNumber,
     expansion1989,
     expansion2019
   ) {
     if (expansion1989 === undefined) {
       expansion1989 = 89;
     }

     if (expansion2019 === undefined) {
       expansion2019 = 19;
     }
     return initialNumber + expansion1989 + expansion2019;
   }
   ```

   **Execution:**

   ```
    bob@dylan:~$ cat 3-main.js
    import getSumOfHoods from './3-default-parameter.js';

    console.log(getSumOfHoods(34));
    console.log(getSumOfHoods(34, 3));
    console.log(getSumOfHoods(34, 3, 4));
    bob@dylan:~$
    bob@dylan:~$ npm run dev 3-main.js
    142
    56
    41
    bob@dylan:~$
   ```
5. **Rest parameter syntax for functions**
   
   Modify the following function to return the number of arguments passed to it using the rest parameter syntax

   ```javascript
    export default function returnHowManyArguments() {

    }
   ```
   Example:
   ```bash
    > returnHowManyArguments("Hello", "Holberton", 2020);
    3
    >
   ```
    **Execution:**
    ```bash
    bob@dylan:~$ cat 4-main.js
    import returnHowManyArguments from './4-rest-parameter.js';

    console.log(returnHowManyArguments("one"));
    console.log(returnHowManyArguments("one", "two", 3, "4th"));
    bob@dylan:~$
    bob@dylan:~$ npm run dev 4-main.js 
    1
    4
    bob@dylan:~$
    ```
6. **The wonders of spread syntax**
   
   Using spread syntax, concatenate 2 arrays and each character of a string by modifying the function below. Your function body should be one line long.

   ```javascript
    export default function concatArrays(array1, array2, string) {
    
    }
   ```
   **Execution:**
   ```bash
    bob@dylan:~$ cat 5-main.js
    import concatArrays from './5-spread-operator.js';

    console.log(concatArrays(['a', 'b'], ['c', 'd'], 'Hello'));

    bob@dylan:~$
    bob@dylan:~$ npm run dev 5-main.js 
    [
      'a', 'b', 'c',
      'd', 'H', 'e',
      'l', 'l', 'o'
    ]
    bob@dylan:~$
   ```