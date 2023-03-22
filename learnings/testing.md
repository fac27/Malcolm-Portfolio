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

We first defined some test helper functions which would steer our testing on the project. The key functions we created in this project made use of the above `equal()` function to ensure their outputs were satisfactory.

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



## 3. Write testable, modular functions

## 4. Write functions that add, remove or modify DOM nodes

## 5. Apply event listeners to HTML form elements

## 6. Use scope to control what variables are accessible inside functions and blocks 

## 7. Use CSS grid to create complex layouts

## 8. Use CSS grid to make layouts that adapt to the viewport size
