**This file contains tips for using Express.js**

Upon running through a tutorial, I had an issue getting my express server to run.

This is because the tutorial used jade as a dependency. Jade has been deprecated and is now pug.

After installing pug globally and locally, I renamed the views folder to have the .pug extension instead of the .jade extension.
Whats more, I added the following lines of code to the App.js file:

Add this line

app.engine('pug', require('pug').__express)

before

app.set('views', path.join(__dirname, 'views'));
app.set('view engine', 'pug');

This solved the same problem for me!

This fix was discovered in part by searching Stack Overflow. Thank you Stack Overflow.

MEAN Stack Tutorial Link (Part 3)
https://youtu.be/dT1ID4q57fs

