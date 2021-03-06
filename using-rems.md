!!!!!!Important: Before you start using media queries and rems, make sure you tell the browser to use the viewport width. You have to tell the browser to use 
viewport width with a meta tag, otherwise your set widths might not work with your media queries. Here is an example:

<meta content="width=device-width, initial-scale=1" name="viewport" />

!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

/* Step 1: Set the html font-size to 62.5% */

html {
  font-size: 62.5%; 
}

/* Step 1 Explained: Since the browsers natural default font-size is 16px, 62.5% will represent a new default base font-size of 10px.
We set the html base font-size to 10px that way our rem conversions will be multiples of 10. This means 1 rem will be 10px, 2 rems will be 20px, 3 rems will be 30px
etc. Using a percentage to declare 10px for our html font-size simply allows users with visual disabilities to increase the base font-size if they need to.

Now, in the rest of your css document, simply use rems in place of pixels. 
*/

/* Step 2: Change all instances of pixels to rem */

nav-bar {
  padding-top: 1rem;
  font-size: 2rem;
}

/* Step 3: To make your page responsive across devices, all you now have to do is create media queries. Make the font-size percentage smaller
for smalller devices, and larger for larger devices. */

/* Note: You may want to use box-sizing: border-box; Doing so will make your element sizes more obvious. */

<img src="https://github.com/zm00622/toolbox/blob/main/Capture4.PNG-mh.png?raw=true">
