![Banner](banner.png)

# Javascript Drum Kit 

A virtual drum kit that users can play with on a webpage. Built upon an existing codebase as part of the[Javascript 30](https://javascript30.com/) challenge. 

Technologies used:
-----

* Javascript DOM
* CSS
* HTML 


Key Concepts 
-----

## Event Listeners

 In this challenge, we use two event handlers to help us manage the program state:
 
### Keydown Events 

When a user presses a key on our page, our program fires an event listener that looks to see if there is a HTML5 `audio` element with a data key that matches the `data-key` property of the keydown event:

```Javascript

 const playSound = (event) => {
    const audio = document.querySelector(`audio[data-key="${event.keyCode}"]`)
    const key = document.querySelector(`.key[data-key="${event.keyCode}"]`)
    if (!audio) return; 
    audio.currentTime = 0; // Ensure the audio element restarts upon successive clicks 
    audio.play();
    key.classList.add('playing');
  } 

window.addEventListener('keydown', playSound);
```
If a match is found, the programme will the matchin audio clip with the built in `play` method.

### Adding and Removing Element Classes

If a matching element is found on the page, that element is given the 'playing' class using the `add` method availible to DOM elements through the `classList` property:

```Javascript 
const key = document.querySelector(`.key[data-key="${event.keyCode}"]`)
key.classList.add('playing');
```
This enables objects to have dynamic styling according to how a user interacts with the page. in this example, it allows us to highlight which audio element is being played:

![classList](classList.png)

## Running the Program 

1. Clone this repo
2. Open the index.html file in your browser





