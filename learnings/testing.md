![image](https://user-images.githubusercontent.com/117777716/228564687-aa82a6df-68b7-479b-b809-37cbe778b088.png)

Our final project was focused on testing, and for this project we created JustDoIt, a to do list app.

## 1. Check that passing a given input into our tests returns the expected output

```js
function equal(actual, expected, message) {
  if (actual === expected) {
    const defaultMessage = `Expected ${expected} and received ${actual}`;
    console.info("Pass: " + (message || defaultMessage));
  } else {
    const defaultMessage = `Expected ${expected} but received ${actual} instead`;
    console.error("Fail: " + (message || defaultMessage));
  }
}

function test(name, testFunction) {
  console.group(name);
  testFunction();
  console.groupEnd(name);
}
```

We first defined some test helper functions which would steer our testing on the to do list project. The key functions we created in this project made use of the above `equal()` function to ensure their outputs were satisfactory.

```js
test("Submitting a new task adds it to the list", () => {
  const result = addTask([], "item");
  equal(result.length, 1, "Submitting a new task adds it to the list");
});
```

Within this test, we pass an empty array and "item" string (the name of the task the user has input) as arguments to the `addTask()` function. 

The `addTask()` function creates an array of task objects. Using the `.find` method, it searches for the first task object which contains the "item" string as a name property. If no such task exists, the `addTask()` function will create a task object and `.push` it with the specified name property into the empty array.

The test is expected to return an array with a length of 1. It will succeed, since in this case we submit a single task to the empty array, filling it with one object.

## 2. Write tests to mimic the behaviour of a user performing different actions

Unfortunately we weren't able to finish these tests, as we only focused on Unit Testing within our app.

## 3. Write testable, modular functions

The size of our functions grew as we continued on in our project, and by the end of it, some of these became quite complicated in terms of testability. One function which typifies a modular style function was the `saveTasksToLocalStorage` function, which if we had the time to, we could have returned to test:

```js
const saveTasksToLocalStorage = () => {
  localStorage.setItem("tasks", JSON.stringify(tasks));
};
```

## 4. Write functions that add, remove or modify DOM nodes

A few of our functions modified DOM nodes, one example of this was the `filterCheckedTasks` function which. in the first part of the function, alters tasks in the to do list, removing them from the list if they are checked off:

```js
const filterCheckedTasks = () => {
  const taskItems = document.querySelectorAll("#todo-list .task");
  const completedTaskItems = document.querySelectorAll("#done-list .task");

  if (filterIncompleteBtn.textContent === "Show Incomplete Tasks") {
    taskItems.forEach((taskItem) => {
      const checkbox = taskItem.querySelector(".todo-item");
      if (checkbox.checked) {
        taskItem.style.display = "none";
      }
    });
    
    ...
    
};
```

## 5. Apply event listeners to HTML form elements

We had a number of event listeners which performed specific functions relevant to the task list. The following function adds a delete functionality to tasks in the 'Completed Items' list:

```js
  completedList.addEventListener("click", deleteItem);
```

## 6. Use scope to control what variables are accessible inside functions and blocks 

Scope control featured heavily in our JavaScript. We had the following variables in the global scope:

```js
const taskList = document.querySelector("#todo-list");
const completedList = document.querySelector("#done-list");
const form = document.getElementById("task-form");
const tasks = JSON.parse(localStorage.getItem('tasks') || '[]');
const completedTasks = JSON.parse(localStorage.getItem('completedTasks') || '[]');
let nextId = 1;
```

And some functions with dedicated variables, specific and accessed only by these functions themselves such as `newTaskTemplate` and `newTask`:

```js
const createTaskElement = (task) => {
  const newTaskTemplate = document.querySelector("#newTaskTemplate");
  const newTask = newTaskTemplate.content.cloneNode(true);
  
  ...
  
 };
```

## 7. Use CSS grid to create complex layouts

The below CSS grid styling was used, and adapted to viewport size also.

```css
@media screen and (min-width: 450px) {
  .two-columns {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr;
    gap: 10px;
  }
  #todo-list {
    grid-column-start: 1;
    grid-column-end: 2;
  }
  #completes {
    grid-column-start: 2;
    grid-column-end: 3;
  }
}
```
