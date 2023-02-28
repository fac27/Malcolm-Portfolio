## 1. Write code that executes asynchronously

```js
function fetchCountryData(){
    fetch('https://restcountries.com/v3.1/all')
    .then(res => res.json())
```

The above fetch function was a core part of our app. It makes use of the `fetch()` and `.then()` methods to fetch data from the REST Countries API endpoint and process the response. Both `fetch()` and `.then()` return promises which execute asynchronously.

## 2. Use callbacks to access values that aren’t available synchronously

The same example (above) contains callbacks which grant access to information which is not available synchronously. The `then()` method executes asynchronously, and the callback function passed to it is executed only after the network request has been completed and the response has been received.

## 3. Use promises to access values that aren’t available synchronously

In addition, the same example uses promises through the `res.json()` function, which is executed asynchronously, so it does not immediately return a value but returns a Promise that resolves to the value.

## 4. Use the fetch method to make HTTP requests and receive responses

```js
function fetchUnsplash(country){
fetch(`https://api.unsplash.com/search/photos?&query=${chosenCountry.name.common} Landmarks&client_id=${apiKey}&count=${count}`)
.then((res) => res.json())
.then((data) => rand3(data))
.catch((error) => backupFetch())
}
```

We had a second `fetch()` method which requested specific country imagery from the Unsplash API, which through our function `rand3(data)`, was appended to DOM elements which we created within our JavaScript to display on our game page.

## 5. Configure the options argument of the fetch method to make GET and POST requests

Our project did not make use of any specific GET or POST methods, however our code above could be edited to use a GET method:

```js
function fetchUnsplash(country) {
  const url = `https://api.unsplash.com/search/photos?&query=${country.name.common} Landmarks&client_id=${apiKey}&count=${count}`;
  const options = {
    method: 'GET'
  };

  fetch(url, options)
    .then((res) => res.json())
    .then((data) => rand3(data))
    .catch((error) => backupFetch());
}
```

## 6. Use the map array method to create a new array containing new values

## 7. Use the filter array method to create a new array with certain values removed

## 8. Access DOM nodes using a variety of selectors

## 9. Add and remove DOM nodes to change the content on the page

## 10. Toggle the classes applied to DOM nodes to change their CSS properties

## 11. Use consistent layout and spacing

## 12. Follow a spacing guideline to give our app a consistent feel

## 13. Debug client side JS in our web browser

## 14. Use console.log() to help us debug our code
