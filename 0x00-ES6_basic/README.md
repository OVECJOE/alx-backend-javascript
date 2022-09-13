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
    ```
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
    ```
        bob@dylan:~$ cat 0-main.js
        import { taskFirst, taskNext } from './0-constants.js';

        console.log(`${taskFirst()} ${taskNext()}`);

        bob@dylan:~$ 
        bob@dylan:~$ npm run dev 0-main.js 
        I prefer const when I can. But sometimes let is okay
        bob@dylan:~$ 
    ```