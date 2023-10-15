Basic Javascript :
======

## 1) Get Element
```javascript
<p id="demo"></p>
document.getElementById('demo');

<p class="demo"></p>
document.getElementsByClassName('demo');

<input name="demo" type="text"/>
document.getElementsByName('demo');

<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
document.getElementsByTagName("li");
```

## 2) Create/Remove Element
```javascript
const paragraph = document.createElement("p");
paragraph.innerText = "This is a paragraph";
document.body.appendChild(paragraph);
document.body.removeChild(paragraph);
```

## 3) Event & Listener
```javascript
button.addEventListener("click", function(){

});

//event
<input onchange="myFunction()">
<button onclick="myFunction()">Click me</button>
<p ondblclick="myFunction()">Double-click me</p>

<input oninput="myFunction()">
<img onmouseenter="bigImg(this)" src="smiley.gif" alt="Smiley">

<form onsubmit="myFunction()">
  Enter name: <input type="text">
  <input type="submit">
</form>

<body onload="myFunction()">
```

## 4) JQuery
```javascript
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.4/jquerymin.js"></script>

$(document).ready(function(){
  $("button").click(function(){
    $("p").hide();
    $("#test").hide();
    $(".test").css("background-color", "lightgray");
  });
});

//event
Mouse Events    |   Keyboard Events |   Form Events |	Document/Window Events
------------------------------------------------------------------------------
click	            keypress	        submit	        load
dblclick	        keydown	            change	        resize
mouseenter	        keyup	            focus	        scroll
mouseleave	 	                        blur	        unload
------------------------------------------------------------------------------

//action
fadeIn()	    Fades in the selected elements
fadeOut()	    Fades out the selected elements
fadeToggle()	Toggles between the fadeIn() and fadeOut() methods

hide()	        Hides the selected elements
show()	        Shows the selected elements
toggle()	    Toggles between the hide() and show() methods

slideDown()	    Slides-down (shows) the selected elements
slideToggle()	Toggles between the slideUp() and slideDown() methods
slideUp()	    Slides-up (hides) the selected elements

//method
$("p:first").addClass("intro");
$("p").after("<p>Hello world!</p>");	//Inserts content after selected elements
$("p").append("<b>Appended text</b>");	//Inserts content at the end of selected elements
$("<span>Hello World!</span>").appendTo("p");   //Inserts HTML elements at the end of selected elements

$("p").before("<p>Hello world!</p>");   //	Inserts content before selected elements
$("p").remove();
$("img").attr("width","500");
$("p").css("color", "red");
$("p").clone().appendTo("body");
$("p").html("Hello <b>world</b>!");
$("p").text("Hello world!");

$("input:text").val("Glenn Quagmire");
```

## 5) Async & fetch

```javascript
//get
async function getData(link) {
  let response = await fetch(link);
  let data = await response.json();
}

//post
async function postData(link) {
    let response = await fetch(link,{
        method: 'post,
        headers: {"Content-Type" : "application/json"},
        body: Json.stringify({
            'name':'Akmal',
            'age':'18'
        })
    });

    if (!response.ok) {
        throw new Error(`HTTP error! Status: ${response.status}`);
    }

    let data = await response.json();
}
```

