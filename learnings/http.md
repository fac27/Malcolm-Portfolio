## 1. Write code that executes asynchronously

```js
function fetchCountryData(){
    fetch('https://restcountries.com/v3.1/all')
    .then(res => res.json())
```

The above fetch function was a core part of our app. It makes use of the fetch() and .then() methods to fetch data from the REST Countries API endpoint and process the response. Both fetch() and .then() return promises which execute asynchronously.

## 2. Use callbacks to access values that aren’t available synchronously

The same example (above) contains callbacks which grant access to information which is not available synchronously. The then() method executes asynchronously, and the callback function passed to it is executed only after the network request has been completed and the response has been received.

## 3. Use promises to access values that aren’t available synchronously



## 4. Use the fetch method to make HTTP requests and receive responses

## 5. Configure the options argument of the fetch method to make GET and POST requests

## 6. Use the map array method to create a new array containing new values

## 7. Use the filter array method to create a new array with certain values removed

## 8. Access DOM nodes using a variety of selectors

## 9. Add and remove DOM nodes to change the content on the page

## 10. Toggle the classes applied to DOM nodes to change their CSS properties

## 11. Use consistent layout and spacing

## 12. Follow a spacing guideline to give our app a consistent feel

## 13. Debug client side JS in our web browser

## 14. Use console.log() to help us debug our code
