<p align="center">
    <img src="https://user-images.githubusercontent.com/117777716/221961530-f9314f8c-b230-4e38-a1e3-71b319255fd1.JPG"></img>
</p>

Our HTTP project was [Atlas Adventure](https://fac27.github.io/Atlas-Adventure/), a country guessing game which challenged users to guess as many countries as they could in 60 seconds using 2 pictures, continent names and currency symbols. It queried 2 APIs: the REST Countries and Unsplash APIs, presenting a combination of two data sources part of the project goals.

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

In addition, the same example uses promises through the `res.json()` function, which is executed asynchronously, so it does not immediately return a value but returns a Promise that resolves to that value.

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

Our project did not make use of any specific POST methods, however our fetch methods make use of the GET request each time they are used. 

## 6. Use the map array method to create a new array containing new values

We did not need to make use of the `.map()` array method for our project, however, we could have done so within the following function which takes an array containing numbers which represent countries (a variable in our project called `countriesArray`), and then appends these to DOM elements:

```js
function appendFlags(array) {
  array.map((country, index) => {
    flagImages[index].src = country.flags.png;
    flagImages[index].id = country.name.common;
    flagName[index].innerHTML = country.name.common;
  });
}
```

## 7. Use the filter array method to create a new array with certain values removed

Similarly, our project did not require the use of the `.filter()` method, but it could have been implemented in the above `appendFlags()` function, potentially by filtering through `countriesArray` to create an array of countries with populations of over 100 million:

```js
function filterCountriesByPopulation(array) {
  const filteredArray = array.filter(country => country.population > 100000000);
  return filteredArray;
}
```

## 8. Access DOM nodes using a variety of selectors

```js
const imageContainer = document.querySelector("#imageContainer");
const flagImages = document.getElementsByClassName("flagImages");
const flagName = document.getElementsByClassName("flagName");
const facts = document.getElementsByClassName("facts");
const locationImg = document.getElementsByClassName("LocationImg");
const startGameBtn = document.querySelector("#startGameBtn");
const startGameScreen = document.querySelector("#startGameScreen");
const loadingElement = document.querySelector("#loadingScreen div:nth-child(1)");
const loadingScreen = document.querySelector("#loadingScreen");
const gameScreen = document.querySelector("#game-Screen");
const countdownEl = document.getElementById('countdown');
const playAgain = document.querySelector("#playAgain");
const EndGame = document.querySelector("#gameStat");
let totalScore = document.querySelector("#TotalScore");
let bestScore = document.querySelector("#highScore");
let headerHighScore = document.querySelector("#bestScore");
```

As much of our project was focused on generating information, visual updates and UI feedback to support a fuly-fledged game, we made extensive use of DOM methods to target different areas of our game screen.

## 9. Add and remove DOM nodes to change the content on the page

We did not use any methods to specifically add or remove DOM nodes in our JS, however a few examples of methods we could use would be:

- `document.createElement()` to create a new element
- `document.appendChild()` to add content to an existing element on the page

## 10. Toggle the classes applied to DOM nodes to change their CSS properties

<p align="center">
    <img src="https://user-images.githubusercontent.com/117777716/221965790-64fbc85e-d744-4ab8-8945-cd573456f3b6.JPG"></img>
</p>

A prime example of this would be our `gameEnd()` function, which shows a summary of players' progress at the end of a round. We used this a callback function elsewhere in our code to display and hide multiple elements of the game screen:

```js
function gameEnd(){
    clearInterval(countdown);
    gameScreen.classList.add("displayNone");
    countdownEl.classList.add("displayNone")
    EndGame.classList.remove("displayNone");
    totalScore.innerHTML = score;
    bestScore.innerHTML = highScore;
    
}
```

## 11. Use consistent layout and spacing

We focused content in the centre of the players' screens, and to help do this we designed and made repeated use of a `.flexCenter{}` CSS class selector which was applied to multiple elements of our game screen HTML code:

```css
.flexCenter{
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Throughout the project, we made use of small, succinct CSS layout primitives like the above which we then applied to individual elements.

## 12. Debug client side JS in our web browser

We needed to make sure certain functions were pulling the correct information from the REST Countries API. In the below function, we log currency identifiers (3 letter codes) in our `console.log(firstKey)` call, showing specific information for the correct country the player needed to select to pass to the next challenge:

```js
function appendFacts(array){
  const keys = Object.keys(array.currencies);
  const firstKey = keys[0];
  console.log(firstKey)
}
```

This example shows the 'EUR' code in the web browser console for Latvia, which was generated as a result of the above `console.log` logging the value of firstKey, which contained this currency information:

<p align="center">
    <img src="https://user-images.githubusercontent.com/117777716/221969026-370b7df3-a605-4ee0-8001-0ca8baaf577e.JPG"></img>
</p>

