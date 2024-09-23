Digital Clock Code Documentation
This documentation explains the functionality of each part of the provided HTML, CSS, and JavaScript code used to create a digital clock.

1. HTML Structure
<html>...</html>
Defines the overall structure of the web page.
The document type is declared as HTML5 (<!DOCTYPE html>).
<head>...</head>
Contains metadata for the web page, such as character set, title, and links to external files.
<meta charset="UTF-8">: Specifies the character encoding as UTF-8.
<meta name="viewport" content="width=device-width, initial-scale=1.0">: Ensures the web page is responsive across different screen sizes.
<title>Digital Clock</title>: Defines the title of the web page, displayed in the browser tab.
<link rel="stylesheet" href="style.css">: Links to an external CSS file (style.css) for styling.
<body>...</body>
Contains the visible content of the web page.
<h2>Digital Clock</h2>: Heading that displays "Digital Clock".

<div class="clock">...</div>: Contains individual div elements for hours, minutes, seconds, and AM/PM display.

Each clock section has:

<span id="hour">00</span>: Displays the current hour.
<span id="minutes">00</span>: Displays the current minutes.
<span id="seconds">00</span>: Displays the current seconds.
<span id="ampm">AM</span>: Displays AM or PM.
<script src="index.js"></script>: Links the JavaScript file (index.js) that updates the clock in real-time.

2. CSS Styling (style.css)
body
Ensures the content is centered both vertically and horizontally on the page.
Applies a background image, stretches it to cover the entire page (background-size: cover), and hides overflow content.
h2
Styles the heading "Digital Clock" with uppercase letters, letter spacing, and custom fonts.
Adds a background color, slight opacity, and text color.
.clock
Defines the clock container using flexbox to align the time elements horizontally.
.clock div
Adds margin between each time block and positions the AM/PM marker relative to the clock.
.clock span
Styles each time block with a background color, text color, and shadow effects.
Centers the time values both vertically and horizontally.
.clock .text
Styles the text labels below the time values ("Hours", "Minutes", "Seconds").
.clock #ampm
Styles the AM/PM marker, positioned at the bottom of its container.
3. JavaScript Functionality (index.js)
Element Selection
const hourEl = document.getElementById("hour");: Selects the element where the hour will be displayed.
const minuteEl = document.getElementById("minutes");: Selects the element for minutes display.
const secondEl = document.getElementById("seconds");: Selects the element for seconds display.
const ampmEl = document.getElementById("ampm");: Selects the element for AM/PM display.
updateclock() Function
Retrieves the current time using JavaScript's Date() object.
Get Hours, Minutes, Seconds

let h = new Date().getHours();: Retrieves the current hour.
let m = new Date().getMinutes();: Retrieves the current minute.
let s = new Date().getSeconds();: Retrieves the current second.
Handle AM/PM

let ampm = "AM";: Default value is set to AM.
if(h > 12){ h = h-12; ampm = "PM"; }: Converts 24-hour time to 12-hour format and changes AM to PM when necessary.
Add Leading Zeros

Adds a leading zero to the time values if they are less than 10 (e.g., 09 instead of 9).
h = h<10 ? "0" + h : h;
Update Display

Updates the HTML elements with the current time:
hourEl.innerText = h;
minuteEl.innerText = m;
secondEl.innerText = s;
ampmEl.innerText = ampm;
Recursive Call

setTimeout(updateclock, 1000);: Calls the updateclock() function every 1000 milliseconds (1 second) to keep the clock updated in real-time.
Initial Call
updateclock();: Calls the updateclock() function to start the clock when the page loads.
