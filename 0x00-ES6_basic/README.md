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

1. Const or let?
    
    **Modify**
    1. function `taskFirst` to instantiate variables using `const`
    2. function `taskNext` to instantiate variables using `let`
    ```javascript
    export function taskFirst() {
        var task = 'I prefer const when I can.';
        return task;
    }

    export function getLast() {
        return ' is okay';
    }

    export function taskNext() {
        var combination = 'But sometimes let';
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

1. Block Scope
   
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