# Random-HEX-Generator

This is a personal project done using HTML, CSS and JavaScript. 

The purpose of this code is to generate random HEX colors with their respective string values to be copied to the clipboard.

The first step was creating the basic HTML and CSS to work with. 

The second step was done in a JavaScript file. 

I started with the basic variables: 

```js
    var i = 0;
    var color = ([""]);
    var j = 0;
```


There I created the random color generator that would generate a random color if there is a click event inside the color box:
```js
          for (j = j; j < color.length; j++) {
                document.querySelector("box").addEventListener("click", function () {
                let randomColor = [`#${Math.floor(Math.random() * 0x1000000).toString(16).padStart(6, "0")}`];
                console.log(randomColor);
                color.push([randomColor]);
                i = i < color.length ? ++i : 0;
                document.querySelector("box").style.background = color[i];
```
This allowed me to generate a random HEX and log it, while also pushing it to the randomColor array.
Lastly, I pushed the new random color as the new background for the color box.

Note: the idea for the HEX generator was stolen from a youtube video, however I changed it to improve its functionality to generate
as many colors as we wanted, whereas the original idea had a limitation of colors generated.

Then I created the picker button functionality.

```js
                let clipboard = document.querySelector("h1").textContent = `${[randomColor]}`;
                const copy = (text) => navigator.clipboard.writeText(text);  
                const button = document.querySelector("button");
                button.addEventListener("click", () => {
                    copy(clipboard)
                    console.log(copy(clipboard)); //whenever we call the copy function inside an Event, it will copy the text chosen to be shown
                });
```
Here the new var clipboard will take as value the original text context from the h1 element, then it will change it to the new string from the randomColor array.

Then I created a function that would copy any text type with the const copy.

And finally I created the eventListener to the button which would call the copy function on the clipboard var, copying the text content from it.

The last step was to add these functionalities to the HTML code using inline JavaScript and CSS to the appropriate classes and elements. 

The greatest challenge in this project was logging the right color from the box to the clipboard while every click on the box would change the value.

I hope anyone finds this useful. 

