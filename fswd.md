# unit 1

### 1. Canvas and SVG in Detail

#### Canvas
The `<canvas>` element is used to draw graphics on a web page using JavaScript. It provides a means for drawing graphics via scripting (usually JavaScript). It can be used for rendering graphs, game graphics, or other visual images on the fly.

##### Example Program using Canvas
```html
<!DOCTYPE html>
<html>
<body>

<canvas id="myCanvas" width="200" height="100" style="border:1px solid #000000;">
Your browser does not support the HTML5 canvas tag.
</canvas>

<script>
var canvas = document.getElementById("myCanvas");
var ctx = canvas.getContext("2d");
ctx.fillStyle = "#FF0000";
ctx.fillRect(0, 0, 150, 75);
</script>

</body>
</html>
```

#### SVG
SVG (Scalable Vector Graphics) is an XML-based markup language for describing two-dimensional vector graphics. SVG is used to define graphics for the Web, providing high-quality images that are scalable and easy to animate.

##### Example Program using SVG
```html
<!DOCTYPE html>
<html>
<body>

<svg width="100" height="100">
  <rect width="100" height="100" style="fill:rgb(0,0,255);stroke-width:1;stroke:rgb(0,0,0)" />
</svg>

</body>
</html>
```

##### example for drawing circle
```html
<!DOCTYPE html>
<html>
<body>
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40"
  stroke="green" stroke-width="4" fill="yellow" />
</svg>
 </body>
</html>
```

##### example for drawing rectangle

```html
<html>
<body>
<svg width="400" height="100">
  <rect width="400" height="100" 
  style="fill:rgb(0,0,255);stroke-width:10;stroke:rgb(0,0,0)" />
</svg>
 </body>
</html>
```
##### example for drawing  round edge rectangle

```html
<!DOCTYPE html>
<html>
<body>
<svg width="400" height="180">
  <rect x="50" y="20" rx="20" ry="20" width="150" height="150"
  style="fill:red;stroke:black;stroke-width:5;opacity:0.5" />
</svg>
</body>
</html>
```
##### example for drawing star

```html
<!DOCTYPE html>
<html>
<body>
<svg width="300" height="200">
  <polygon points="100,10 40,198 190,78 10,78 160,198"
  style="fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;" />
</svg>
 </body>
</html>
```

## Differences Between Canvas and SVG 


![image](https://github.com/ace2884/3-2-shorts/assets/119153850/8ec9f301-d9dd-4fc2-a50f-d1f6d5b4ee16)



### 2. Web Storage in Detail

Web storage refers to mechanisms that web applications can use to store data in the client's browser. It provides a way to persistently store data locally on the user's device, allowing the application to retrieve and update this data as needed. Web storage is essential for building responsive and interactive web applications, enabling features such as caching, offline support, and improving performance by reducing server-side requests.

### Types of Web Storage

There are two main types of web storage supported by modern browsers:

1. **Session Storage**
2. **Local Storage**

#### 1. Session Storage

- **Scope**: Data stored in session storage is specific to the current browser tab or window session. When the user closes the tab or window, the session storage data is cleared.
- **Usage**: Session storage is useful for storing temporary data that should be available during the current browser session but does not need to persist beyond that.
- **Access**: Data in session storage can be accessed and manipulated using JavaScript APIs (`sessionStorage` object).

###### Example Usage:

```javascript
// Store data in session storage
sessionStorage.setItem('username', 'john_doe');

// Retrieve data from session storage
let username = sessionStorage.getItem('username');
console.log('Username:', username);

// Remove data from session storage
sessionStorage.removeItem('username');
```

#### 2. Local Storage

- **Scope**: Data stored in local storage persists indefinitely until explicitly deleted by the application or cleared by the user.
- **Usage**: Local storage is suitable for storing data that needs to be available across sessions, such as user preferences or cached data.
- **Access**: Data in local storage can be accessed and manipulated using JavaScript APIs (`localStorage` object).

###### Example Usage:

```javascript
// Store data in local storage
localStorage.setItem('theme', 'dark');

// Retrieve data from local storage
let theme = localStorage.getItem('theme');
console.log('Theme:', theme);

// Remove data from local storage
localStorage.removeItem('theme');
```

###### Features and Considerations

- **Capacity**: Both session storage and local storage typically offer a storage capacity of 5-10MB per domain, although this can vary by browser.
- **Performance**: Web storage operations (reading and writing data) are synchronous and relatively fast, making it suitable for storing small to moderate amounts of data.
- **Security**: Data stored in web storage is scoped to the origin (protocol, host, and port), meaning data stored by one website cannot be accessed by another website.
- **APIs**: Web storage is accessed using simple and consistent APIs (`setItem`, `getItem`, `removeItem`, etc.) provided by the `localStorage` and `sessionStorage` objects in JavaScript.

###### Use Cases

- **User Preferences**: Storing user-selected themes, language preferences, or layout settings.
- **Caching**: Storing data fetched from a server to reduce the number of requests and improve application performance.
- **Offline Support**: Storing essential data locally to provide basic functionality when the user is offline.

###### Browser Support

Web storage is widely supported by modern web browsers, including Chrome, Firefox, Safari, Edge, and Internet Explorer (versions 8 and above). However, it's essential to handle cases where web storage might not be available or disabled by the user's browser settings.




### 3. Differences Between HTML and HTML5

![image](https://github.com/ace2884/3-2-shorts/assets/119153850/47be880e-ebcb-4dfb-9cb9-c0d06e25d8dd)


## 4. HTML5 Elements  Video and Audio

#### Video Element
```html
<!DOCTYPE html>
<html>
<body>

<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

</body>
</html>
```

#### Audio Element
```html
<!DOCTYPE html>
<html>
<body>

<audio controls>
  <source src="audio.mp3" type="audio/mp3">
  Your browser does not support the audio element.
</audio>

</body>
</html>
```

## 5. HTML Code for Drag and Drop

```html
<!DOCTYPE html>
<html>
<head>
<style>
#div1 {
  width: 350px;
  height: 70px;
  padding: 10px;
  border: 1px solid #aaaaaa;
}
</style>
</head>
<body>

<h2>Drag and Drop Example</h2>
<p>Drag the image into the rectangle:</p>

<img id="drag1" src="img_logo.gif" draggable="true" ondragstart="drag(event)" width="336" height="69">

<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

<script>
function allowDrop(ev) {
  ev.preventDefault();
}

function drag(ev) {
  ev.dataTransfer.setData("text", ev.target.id);
}

function drop(ev) {
  ev.preventDefault();
  var data = ev.dataTransfer.getData("text");
  ev.target.appendChild(document.getElementById(data));
}
</script>

</body>
</html>
```

## 6. Geolocation

The Geolocation API allows the user to provide their location to web applications if they so desire. It can be used to find a user's location and display it on a map.

#### Example Usage of Geolocation
```html
<!DOCTYPE html>
<html>
<body>

<p>Click the button to get your coordinates:</p>

<button onclick="getLocation()">Try It</button>

<p id="demo"></p>

<script>
var x = document.getElementById("demo");

function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else { 
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}

function showPosition(position) {
  x.innerHTML = "Latitude: " + position.coords.latitude + 
  "<br>Longitude: " + position.coords.longitude;
}
</script>

</body>
</html>
```

## 7. Five Bootstrap CSS Classes

Bootstrap is a popular front-end framework that helps developers create responsive and mobile-first web designs. It comes with a variety of CSS classes that can be used to style HTML elements efficiently. Here are five essential Bootstrap CSS classes:

1. **.container**: Used to create a responsive fixed-width container.
2. **.row**: Used to create a horizontal group of columns.
3. **.col**: Used for grid columns to define their width and layout.
4. **.btn**: Used to style buttons.
5. **.alert**: Used to create alert messages.


#### 1. `.container` and `.container-fluid`

- **`.container`**:
  - **Description**: This class creates a fixed-width container that is responsive and centered on the page.
  - **Usage**: It provides a responsive fixed width for the page content. The width of `.container` varies depending on the viewport size.
  - **Example**:
    ```html
    <div class="container">
      <p>This is a fixed-width container.</p>
    </div>
    ```

- **`.container-fluid`**:
  - **Description**: This class creates a full-width container that spans the entire width of the viewport.
  - **Usage**: Use this class when you want your container to take up the full width of the viewport, regardless of its size.
  - **Example**:
    ```html
    <div class="container-fluid">
      <p>This is a full-width container.</p>
    </div>
    ```

#### 2. `.row` and `.col`

- **`.row`**:
  - **Description**: This class is used to create a row in the Bootstrap grid system. Rows are wrappers for columns.
  - **Usage**: Use `.row` to create a new row in the grid layout.
  - **Example**:
    ```html
    <div class="container">
      <div class="row">
        <div class="col">
          <p>Column 1</p>
        </div>
        <div class="col">
          <p>Column 2</p>
        </div>
      </div>
    </div>
    ```

- **`.col`**:
  - **Description**: This class is used to create columns inside a row. It can be used with numbers to specify the width of the column, e.g., `.col-6`.
  - **Usage**: Use `.col` to create equal-width columns, or specify a number to create columns of different widths.
  - **Example**:
    ```html
    <div class="container">
      <div class="row">
        <div class="col-4">
          <p>Column 1</p>
        </div>
        <div class="col-8">
          <p>Column 2</p>
        </div>
      </div>
    </div>
    ```

#### 3. `.btn`

- **Description**: This class is used to style buttons in Bootstrap.
- **Usage**: Use `.btn` along with other modifier classes to style buttons (`.btn-primary`, `.btn-secondary`, `.btn-success`, etc.).
- **Example**:
  ```html
  <button class="btn btn-primary">Primary Button</button>
  <button class="btn btn-secondary">Secondary Button</button>
  <button class="btn btn-success">Success Button</button>
  ```

#### 4. `.alert`

- **Description**: This class is used to create alert messages.
- **Usage**: Use `.alert` along with modifier classes like `.alert-primary`, `.alert-secondary`, `.alert-success`, etc., to create different types of alerts.
- **Example**:
  ```html
  <div class="alert alert-primary" role="alert">
    This is a primary alert.
  </div>
  <div class="alert alert-success" role="alert">
    This is a success alert.
  </div>
  <div class="alert alert-danger" role="alert">
    This is a danger alert.
  </div>
  ```

#### 5. `.card`

- **Description**: This class is used to create card components, which are flexible and extensible content containers.
- **Usage**: Use `.card` to create a card, and use additional classes like `.card-body`, `.card-title`, `.card-text`, etc., to structure the content inside the card.
- **Example**:
  ```html
  <div class="card" style="width: 18rem;">
    <img class="card-img-top" src="image.jpg" alt="Card image cap">
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
  ```

## form validation


```html
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Page Title</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
    <script >
        function validate(){
            var fname = document.reg_form.fname;
            var lname =document.reg_form.lname;
            var gender = document.reg_form.gen;
            var mobile= document.reg_form.mob;
            var email=document.reg_form.email;
            var submit=document.reg_form.submit;
            if (fname.value.length ==0|| lname.value.length==0 ||gender.value.length==0){
                alert("Enter all the fields");
                return false;
            }
            var alpha=/^[A-Za-z]+$/;
            if (!fname.value.match(alpha)||!lname.value.match(alpha)){
                alert("Enter valid first and last name")
                return false;
            }
            if(mobile.value.length != 10){
                alert("Enter 10 digit mobile no");
                return false;
            }
            var validregx= /^[a-zA-Z0-9.!#$%&+/=?^_'{|}~-]+@[a-zA-Z0-9]+(?:\.[a-zA-Z0-9]+)*$/;
            if(email.value.match(validregex)){
                alert("enter valid email id");
                return false;

            }   
            if (submit.value=validate){
                alert("registered sucessfully");
                return true;
            }         
        }
    </script>
</head>
<body>
    <center>
        <form action="" onsubmit="return validate()" name="reg_form">
        <table border="1">
            <thread>
                <th colspan="2"> registration form validation</th>
            </thread>
            <tbody>
                <tr>
                    <td> First name:</td>
                    <td><input type="text" id="fname"></td>

                </tr>
                <tr>
                    <td>last name:</td>
                    <td><input type="text" id="lname">
                    </td>
                </tr>
                <tr>
                    <td>gender :</td>
                    <td>male <input type="radio" id="gen" name="gen">Female <input type="radio" id="gen" name="gen"></td>
                </tr>
                <tr>
                    <td>Mobile no:</td>
                    <td><input type="text" id="mob"></td>

                </tr>
                <tr>
                    <td>email:</td>
                    <td><input type="text" id="email"></td>
                </tr>
                <tr>
                    <td><input type="submit" onclick="confSubmit(this.form);" value="registration"/></td>
                    <td><input type="submit" value="rest"/></td>
                </tr>
            </tbody>
        </table>
        </form>
    </center>
    
</body>
</html>
```

  
## moving car

  
### index.html

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>css car</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
    <link rel="stylesheet" href="main.css">
    <script src='main.js'></script>
</head>
<body>
    <div class="container">
        <div class="sky">
            <div class="buildings"></div>
                <div class="road"></div>
                <div class="car">
                    <div class="wheel">
                        <img src="car_wheel_left.png" alt=" ">
                    </div>
                    <div class="wheel2">
                        <img src="car_wheel_right.png" alt=" ">
                    </div>
            </div>      
        </div>  
    </div>
</body>
</html>
``` 


### main.css

```css
*{
    margin: 0;
    padding:0;

}
body{
    overflow:hidden;
    animation: shakebody linear 8s infinte;

}
.sky{
    height: 100vh;
    width: 100%;
    background-image: url(background.jpg);
    background-repeat: no-repeat;
    position: absolute;
}
.buildings{
    height: 100vh;
    width: 100%;
    background-image: url(buldings.jpg);
    background-size: cover;
    position: absolute;
    top: -144px;

}
.road{
    height: 60vh;
    width: 800vw;
    background-image: url(road.png);
    background-repeat: repeat-x;
    position: absolute;
    top: 70vh;
    animation: carMove linear 13s infinite;

}
.car{
    height: 100px;
    width: 380px;
    background-image: url(car_body.png);
    background-size: cover;
    background-repeat: no-repeat;
    position:absolute;
    left: 444px;
    bottom: 30vh;
    animation:shake linear .9s infinite;
}
.wheel img{
    width: 77px;
    position:relative;
    top:42px;
    left:42px;
    animation:wheelRotation linear .5s infinite;

}
.wheel2 img{
    width: 77px;
    position:relative;
    top:-39px;
    left:235px;
    animation:wheelRotation linear .87s infinite;
}  

@keyframes wheelRotation{
    100%
    {
        transform: rotate(360deg);

    }
}
@keyframes  carMove
{
 100%{
    transform: translateX(-500vw);
 }
}

@keyframes shake{
    0%
    {
        transform:translate(-5px);
    }
    50%
    {
        transform: translate(5px);
    }
    100%
    {
        transform: translateY(-5px);
    }
}
```
## CSS positions

CSS provides several ways to position elements on a web page. The positioning of an element is defined by the `position` property, which can have several values: `static`, `relative`, `absolute`, and `fixed`. Here's a brief explanation of each:

### 1. Static Positioning
- **`position: static;`**
- This is the default value for all elements. Elements are positioned according to the normal flow of the document.
- They are not affected by top, bottom, left, or right properties.
- Example:
  ```css
  .static {
    position: static;
  }
  ```

### 2. Relative Positioning
- **`position: relative;`**
- The element is positioned relative to its normal position. Setting the top, right, bottom, or left properties will cause it to be adjusted from its normal position.
- Other content will not be adjusted to fit into any gap left by the element.
- Example:
  ```css
  .relative {
    position: relative;
    top: 10px;   /* Move down 10px from its normal position */
    left: 20px;  /* Move right 20px from its normal position */
  }
  ```

### 3. Absolute Positioning
- **`position: absolute;`**
- The element is positioned relative to its nearest positioned ancestor (an ancestor with a position other than `static`).
- If there is no such ancestor, it uses the document body and moves along with page scrolling.
- The element is removed from the normal document flow, and other elements behave as if the element does not exist.
- Example:
  ```css
  .absolute {
    position: absolute;
    top: 50px;   /* 50px from the top of the nearest positioned ancestor */
    left: 100px; /* 100px from the left of the nearest positioned ancestor */
  }
  ```

### 4. Fixed Positioning
- **`position: fixed;`**
- The element is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled.
- The element is removed from the normal document flow, and other elements behave as if the element does not exist.
- Example:
  ```css
  .fixed {
    position: fixed;
    top: 20px;   /* 20px from the top of the viewport */
    right: 30px; /* 30px from the right of the viewport */
  }
  ```

### Comparison and Use Cases

- **Static**: Use when no specific positioning is needed. It's the default and useful for elements that fit within the normal flow of the document.
- **Relative**: Use when you need to adjust the position of an element without affecting the layout of surrounding elements. Great for slight adjustments.
- **Absolute**: Use when you need to place an element at a specific position regardless of the normal flow. Common for dropdown menus, modals, and tooltips.
- **Fixed**: Use when you want an element to stay fixed at a specific position relative to the viewport, useful for navigation bars, headers, and footers that remain visible during scrolling.

 

### 8. HTML Bootstrap Code for Forms

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
<body>

<div class="container">
  <h2>Bootstrap Form Example</h2>
  <form>
    <div class="form-group">
      <label for="email">Email address:</label>
      <input type="email" class="form-control" id="email" placeholder="Enter email" name="email">
    </div>
    <div class="form-group">
      <label for="pwd">Password:</label>
      <input type="password" class="form-control" id="pwd" placeholder="Enter password" name="pwd">
    </div>
    <div class="form-group form-check">
      <label class="form-check-label">
        <input class="form-check-input" type="checkbox" name="remember"> Remember me
      </label>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
  </form>
</div>

</body>
</html>
```

### 9. HTML Bootstrap Code for Responsive Tables

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
<body>

<div class="container">
  <h2>Responsive Table</h2>
  <p>The .table-responsive class makes the table responsive:</p>            
  <div class="table-responsive">          
    <table class="table">
      <thead>
        <tr>
          <th>#</th>
          <th>First Name</th>
          <th>Last Name</th>
          <th>Username</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>John</td>
          <td>Doe</td>
          <td>john@example.com</td>
        </tr>
        <tr>
          <td>2</td>
          <td>Mary</td>
          <td>Moe</td>
          <td>mary@example.com</td>
        </tr>
        <tr>
          <td>3</td>
          <td>July</td>
          <td>Dooley</td>
          <td>july@example.com</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

</body>
</html>
```

1. **HTML Structure**:
    - The `container` class is used to center and add padding to the content.
    - The `table-responsive` class is used to make the table responsive, which means it will scroll horizontally on smaller screens.
    - The `table` class is the base class for all Bootstrap tables.
    - The `table-bordered` class adds borders to the table and its cells.
    - The `thead-dark` class makes the table header dark.

2. **Responsive Behavior**:
    - The `table-responsive` class is wrapped around the `<table>` element. This class creates a horizontal scrollbar when the table overflows horizontally, making it easier to view on smaller screens.

3. **Including Bootstrap**:
    - The Bootstrap CSS is included via a CDN for easy setup.
    - The optional JavaScript dependencies for Bootstrap (jQuery, Popper.js, and Bootstrap's JS) are also included for better functionality like tooltips, popovers, and modals.

By using the `table-responsive` class, the table will automatically adjust its layout to ensure that it is readable on all screen sizes, from large desktops to small mobile devices.

### 10. Design Nav Bar for a College Website

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>College Website</title>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
<body>

<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">CollegeName</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">About Us</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Departments</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Admissions</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Faculty</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Contact Us</a>
      </li>
    </ul>
  </div>
</nav>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>

</body>
</html>
```
# unit 2

## JQuery Features
jQuery simplifies various tasks of a programmer by writing less code. Here is the list of important core features supported by jQuery 
- DOM manipulation − the jQuery made it easy to select DOM elements, negotiate them 
and modifying their content by using cross-browser open source selector engine called Sizzle.
- Event handling − The jQuery offers an elegant way to capture a wide variety of events, such as a user clicking on a link, without the need to clutter the HTML code itself with event handlers.
- AJAX Support − The jQuery helps you a lot to develop a responsive and feature rich site using AJAX technology.
- Animations − The jQuery comes with plenty of built-in animation effects which you can use in your websites.
- Lightweight − The jQuery is very lightweight library - about 19KB in size (Minified and gripped).
- Cross Browser Support − The jQuery has cross-browser support, and works well in IE 
- Latest Technology − The jQuery supports CSS3 selectors and basic XPath syntax.
JQuery has been developed with the following principles:
- Separation of JavaScript and HTML, which encourages developers to completely 
separate JavaScript code from HTML markup.
- Brevity and clarity promotes features like chainable functions and shorthand function 
names.
- Eliminates of cross-browser incompatibilities, so developers does not need to worry 
about browser compatibility while writing code using jQuery library.
- Extensibility, which means new events, elements, and methods can be easily added in 
jQuery library and then reused as a plugin.

## **JQuery Selectors**
jQuery Selectors are used to select HTML element(s) from an HTML document. Consider an 
HTML document is given and you need to select all the <div> from this document. This is where 
jQuery Selectors will help.
jQuery Selectors can find HTML elements (ie. Select HTMLelements) based on the following:
- ID Selectors
- Class Selectors
- Element attribute name
- Element attribute value

#### 1. ID Selectors:
The element ID selector selects a single element with the given id attribute. This would be an 
element ID. If the id contains any special characters like periods or colons you have to escape 
those characters with backslashes.

Syntax:
```
$('#elementid')
```
Example:
```
<html>
<head>
 <script src ="https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
 <style>
 #myColor 
{
color: white; 
background: black; 
padding:30px; 
height: 90px; 
width: 400px;
 }
#newColor
{
background: pink; 
width: 650px; 
color: white; 
padding:30px; 
height: 90px;
 }
 </style>
</head>
<body>
<center>
 <div id="myColor"><p style="text-align:center;">Changing the Element ID</p>
</div>
<br>
 <button onclick = "myFuntion()"> Click here </button>
 <script>
 function myFuntion() {
 $("#mycolor").attr('id', 'newColor');
 }
 </script>
 </center>
</body>
</html>
```
#### 2. Class Selectors
The .class selector in jQuery is used to select all elements with the specific class.

Syntax:
```
$(".class")
```
Example:
```
<!DOCTYPE html>
<html>
<head>
<style>
.one {
background-color: blue;
color: white;
font-size: 18px;
border: 2px blue dashed;
}
</style>
<script src="https://code.jquery.com/jquery3.4.1.js"></script>
<script>
$(document).ready(function(){
$(".demo").addClass("one");
});
</script>
</head>
<body>
<h1>Heading One</h1>
<h2>Heading Two</h2>
<p class="demo">Demo text 1...</p>
<p>Demo text 2...</p>
<p class="demo">Demo text 3...</p>
<p>Demo text 4...</p>
</body>
</html>
```
#### 3. Attribute name
The [attribute|=value] selector selects each element with a specified attribute, with a value equal 
to a specified string (like "en") or starting with that string followed by a hyphen (like "en-us").

Syntax:
```
$("[attribute|='value']")
```

Example 
```
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
 $("p[title|='Tomorrow']").css("background-color", "red");}); 
</script>
</head>
<body>
<p title="Tomorrow">This is a paragraph.</p>
<p title="tomorrow">This is a paragraph.</p>
<p title="Tom">This is a paragraph.</p>
<p title="See You Tomorrow">This is a paragraph.</p>
<p title="Tomorrow-the day after today">This is a paragraph.</p>
</body>
</html>
```
#### 4. Attribute value:
The [attribute!=value] selector in jQuery is used to select each element that 
isn’t having the specified attribute and value.

Syntax:
```
$("[attribute!='value']")
```

Example:
```
<!DOCTYPE html>
<html>
<head>
<style>
.one {
color: white;
background-color: orange;
font-size: 16px;
border: 2px blue dashed;
}
</style>
<script
src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/j
query.min.js"></script>
<script>
$(document).ready(function(){
$("p[class!='demo']").addClass("one");
});
</script></head>
<body>
<h1>Car Details</h1>
<p>Car is XUV500</p>
<p class="demo">2179 cc</p>
<p>Independent Suspension</p>
<p>Fuel Tank Capacity: 70 litres</p>
</body>
</html>
```
## CSS selectors

CSS selectors are used to select the HTML elements you want to style. There are several types of selectors, each with different levels of specificity and purposes. Here’s an overview of the most common CSS selectors:

### 1. Universal Selector
- **`*`**
- Selects all elements in the document.
- Example:
  ```css
  * {
    margin: 0;
    padding: 0;
  }
  ```

### 2. Type Selector
- **`element`**
- Selects all elements of a given type.
- Example:
  ```css
  p {
    color: blue;
  }
  ```

### 3. Class Selector
- **`.classname`**
- Selects all elements with the specified class.
- Example:
  ```css
  .my-class {
    font-size: 20px;
  }
  ```

### 4. ID Selector
- **`#idname`**
- Selects the element with the specified ID. IDs should be unique within a page.
- Example:
  ```css
  #my-id {
    background-color: yellow;
  }
  ```

### 5. Attribute Selector
- Selects elements based on the presence or value of an attribute.
- Example:
  ```css
  /* Select elements with an attribute named data-role */
  [data-role] {
    border: 1px solid black;
  }
  
  /* Select elements with an attribute data-role equal to admin */
  [data-role="admin"] {
    color: red;
  }
  ```

### 6. Descendant Selector
- **`ancestor descendant`**
- Selects all elements that are descendants of a specified ancestor.
- Example:
  ```css
  div p {
    margin: 10px;
  }
  ```

### 7. Child Selector
- **`parent > child`**
- Selects all elements that are direct children of a specified element.
- Example:
  ```css
  ul > li {
    list-style: none;
  }
  ```

### 8. Sibling Selectors
- **Adjacent Sibling (`element1 + element2`)**: Selects the element that is immediately preceded by the first specified element.
  ```css
  h1 + p {
    margin-top: 0;
  }
  ```
- **General Sibling (`element1 ~ element2`)**: Selects all elements that are siblings of a specified element.
  ```css
  h1 ~ p {
    color: green;
  }
  ```

### 9. Pseudo-class Selector
- Selects elements based on their state or position.
- Example:
  ```css
  /* Selects the first child of its parent */
  :first-child {
    font-weight: bold;
  }

  /* Selects elements on hover */
  a:hover {
    text-decoration: underline;
  }
  ```

### 10. Pseudo-element Selector
- Selects and styles a part of an element.
- Example:
  ```css
  /* Selects the first letter of each paragraph */
  p::first-letter {
    font-size: 200%;
    color: red;
  }

  /* Selects the content before an element */
  p::before {
    content: "Note: ";
    color: blue;
  }
  ```

### 11. Grouping Selector
- **`selector1, selector2, ...`**
- Applies the same style to multiple elements.
- Example:
  ```css
  h1, h2, h3 {
    margin-bottom: 10px;
  }
  ```






# unit 3

## comparison between MongoDB and RDBMS in a tabular format: 

| Feature                     | MongoDB (NoSQL)                                             | RDBMS (Relational Database Management System)            |
|-----------------------------|-------------------------------------------------------------|---------------------------------------------------------|
| Data Model                  | Document-oriented (JSON-like documents)                     | Table-based (rows and columns)                           |
| Schema                      | Schema-less, flexible                                       | Fixed schema, rigid                                      |
| Transactions                | Supports ACID transactions with limitations                 | Full ACID support                                        |
| Scalability                 | Horizontally scalable (sharding)                            | Vertically scalable (scale-up)                           |
| Query Language              | MongoDB Query Language (MQL)                                | SQL (Structured Query Language)                          |
| Joins                       | Limited support for joins, often requires denormalization   | Extensive support for joins across multiple tables       |
| Storage                     | Binary JSON (BSON)                                          | Various storage formats (typically binary or text)       |
| Data Relationships          | Embedded documents, references                              | Foreign keys, join tables                                |
| Use Cases                   | Big data, real-time analytics, content management, IoT      | Financial transactions, ERP, CRM, data warehousing       |
| Indexing                    | Supports indexing on any field                              | Extensive indexing options (primary, unique, composite)  |
| Performance                 | Fast read/write for large volumes of data                   | Optimized for complex queries and transactions           |
| Flexibility                 | Highly flexible, adaptable to changes in data structure     | Less flexible, changes require schema modifications      |
| Backup and Restore          | Various tools available, typically more complex             | Mature and standardized tools available                  |
| Consistency Model           | Eventual consistency, strong consistency optional           | Strong consistency                                       |
| Licensing                   | Generally open-source, some enterprise versions             | Various licenses (open-source and commercial)            |
| Popular Examples            | MongoDB, CouchDB, Cassandra                                 | MySQL, PostgreSQL, Oracle, SQL Server                    |



![image](https://github.com/ace2884/3-2-shorts/assets/119153850/394d9b69-c774-4165-8ee0-b81b1f165de5)


# unit 4

## Difference between angularjs and angular

![image](https://github.com/ace2884/3-2-shorts/assets/119153850/003a8519-e46a-4e7d-9fca-728d9ce1904e)

Here's a comparison between Angular (versions 2 and above) and AngularJS (version 1.x) in a tabular format, highlighting their key differences:

| Feature                | Angular (versions 2 and above)          | AngularJS   (version 1.x)        |
|------------------------|----------------------------------------|----------------------------------------|
| **Architecture**       | Component-based architecture           | MVC (Model-View-Controller) architecture, but uses two-way data binding heavily |
| **Language**           | TypeScript                             | JavaScript                             |
| **Rendering**          | Uses Hierarchical Dependency Injection, Ahead-of-Time (AOT) compilation, and Reactive Extensions (RxJS) | Uses two-way data binding and digest cycle for rendering |
| **Performance**        | Improved performance due to AOT compilation, tree-shaking, and improved change detection | Slower performance due to digest cycle and two-way data binding |
| **Directives**         | Structural directives (`*ngIf`, `*ngFor`) and attribute directives (e.g., `[ngClass]`) | Directives for DOM manipulation are core to templates |
| **Dependency Injection** | Hierarchical Dependency Injection system | Global scope Dependency Injection |
| **Tooling**            | Advanced CLI (Command Line Interface) with features like scaffolding, testing, and build optimization | Limited CLI capabilities, more reliance on third-party tools |
| **Mobile Support**     | Built-in support for building progressive web apps (PWA) and mobile applications | Limited support, requires additional frameworks like Ionic for mobile development |
| **Community and Support** | Large active community and frequent updates from Google | Large legacy community, fewer updates |
| **Learning Curve**     | Steeper learning curve due to TypeScript and new concepts like RxJS | Easier learning curve, especially for developers familiar with JavaScript and HTML |
| **Backward Compatibility** | Breaking changes between major versions | Backward compatible within the 1.x series |
| **Development Speed**  | Faster development speed with improved tooling and performance optimizations | Slower development speed due to complex two-way data binding and digest cycle |
| **Flexibility**        | More flexibility with improved modular architecture and better separation of concerns | Less flexibility due to tightly coupled MVC architecture |
| **State Management**   | Uses services, RxJS for state management, and NgRx for reactive state management | Relies on `$scope` and event broadcasting for managing application state |
| **Support and Updates** | Regular updates and long-term support from Angular team | Minimal updates and community-driven support for older versions |



## AngularJS Mouse Events

AngularJS provides a way to handle mouse events within your application using directives. These events allow you to respond to user interactions with the mouse, such as clicks, double-clicks, mouseover, mouseleave, etc. Here are some common mouse events in AngularJS along with explanations and examples:


1. **ng-click**

   - **Description**: Executes an expression when an element is clicked.
   - **Usage**: Useful for handling click events on buttons, links, or any clickable element.
   - **Example**:
     ```html
     <button ng-click="doSomething()">Click Me</button>
     ```
     ```javascript
     // Controller code
     $scope.doSomething = function() {
         alert('Button clicked!');
     };
     ```

2. **ng-dblclick**

   - **Description**: Executes an expression when an element is double-clicked.
   - **Usage**: Useful for handling double-click events on elements.
   - **Example**:
     ```html
     <div ng-dblclick="openModal()">Double-click Me</div>
     ```
     ```javascript
     // Controller code
     $scope.openModal = function() {
         // Logic to open a modal
     };
     ```

3. **ng-mouseover**

   - **Description**: Executes an expression when the mouse cursor moves over an element.
   - **Usage**: Useful for triggering actions when the user hovers over an element.
   - **Example**:
     ```html
     <div ng-mouseover="showTooltip = true" ng-mouseleave="showTooltip = false">
         Hover over me
         <div ng-show="showTooltip" class="tooltip">Tooltip content</div>
     </div>
     ```

4. **ng-mouseleave**

   - **Description**: Executes an expression when the mouse cursor leaves an element.
   - **Usage**: Useful for hiding elements or resetting states when the user moves the mouse away.
   - **Example**: See the example above for `ng-mouseover`.

5. **ng-mousedown**

   - **Description**: Executes an expression when the mouse button is pressed down on an element.
   - **Usage**: Useful for triggering actions when the mouse button is pressed.
   - **Example**:
     ```html
     <div ng-mousedown="startDrawing()">Click and hold to draw</div>
     ```
     ```javascript
     // Controller code
     $scope.startDrawing = function() {
         // Logic to start drawing
     };
     ```

6. **ng-mouseup**

   - **Description**: Executes an expression when the mouse button is released over an element.
   - **Usage**: Useful for triggering actions when the mouse button is released.
   - **Example**:
     ```html
     <div ng-mousedown="startDrawing()" ng-mouseup="stopDrawing()">Click and drag to draw</div>
     ```
     ```javascript
     // Controller code
     $scope.stopDrawing = function() {
         // Logic to stop drawing
     };
     ```

   ## Routing in Angular

  - Routing in AngularJS is used when the user wants to navigate to different pages in an application but still wants it to be a single page application.
 AngularJS routes enable the user to create different URLs for different content in an application.

-The ngRoute module helps in accessing different pages of an application without reloading the entire application.

-$routeProvider is used to configure the routes. It helps to define what page to display when a user clicks a link. It accepts either when() or otherwise() method.
The ngRoute must be added as a dependency in the application module:
```
const app = angular.module("myApp", ["ngRoute"]); 
```

## Fetch Data From A Service

- Angular offers HttpClient to work on API and handle data easily. In this approach HttpClient along with subscribe() method will be used for fetching data.
  
**Step 1:** Create the necessary component and application.

**Step 2:** Do the necessary imports for HttpClient in module.ts file.
```
import { HttpClientModule } from '@angular/common/http'; 
imports: [
 HttpClientModule,
 ], 
 ```
**Step 3:** Do the necessary imports for HttpClient in component.ts file.
```
import { HttpClientModule } from '@angular/common/http';
```
**Step4:** We get Response from API by passing API url in get() method and then subscribing to the url. 
```
this.http.get('API url').subscribe(parameter)
```
- The Response of the API is stored in a variable from which data can be accessed.

**Step 5:** Now data array need to be showed using HTML. A Table is used in which rows are added dynamically by the size of data array. For this, rows are created using *ng For then data is showed from each row.

## Submit Data To Service

- The ngSubmit() method is called when the ‘submit’ event is triggered on the ngForm.
Syntax
```
<form (ngSubmit)='method($event)'></form>
```
- $event: the “submit” event object

**Approach:**

- Create an Angular app that to be used.
- In app.component.ts, make an array that takes the value from the form.
- In app.component.html, make a form and send the value using (ngSubmit) method.
- Serve the angular app using ng serve to see the output.




# unit 5

## Build the steps to create a new git local Repository and remote repository.


### Step-by-Step Guide to Create a New Git Local and Remote Repository

#### 1. Install Git
Ensure Git is installed on your system. You can verify by running:

```sh
git --version
```

If Git is not installed, download it from [git-scm.com](https://git-scm.com/) and follow the installation instructions.

#### 2. Configure Git
Set your username and email.

```sh
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

#### 3. Create a New Local Repository

1. **Navigate to your project directory**:
    ```sh
    cd /path/to/your/project
    ```

2. **Initialize a Git repository**:
    ```sh
    git init
    ```

3. **Add your project files**:
    ```sh
    git add .
    ```

4. **Commit the files**:
    ```sh
    git commit -m "Initial commit"
    ```

#### 4. Create a New Remote Repository on GitHub

1. **Log in to GitHub**.
2. **Click on the "+" icon** in the upper right corner and select "New repository".
3. **Fill in the repository details**:
   - Repository name: `your-repo-name`
   - Description: (optional)
   - Public or Private: Choose based on your preference
4. **Click "Create repository"**.

#### 5. Link Local Repository to Remote Repository

1. **Copy the remote repository URL** from GitHub. It looks like `https://github.com/yourusername/your-repo-name.git`.
2. **Add the remote URL to your local repository**:
    ```sh
    git remote add origin https://github.com/yourusername/your-repo-name.git
    ```

#### 6. Push Local Repository to Remote Repository

1. **Push the initial commit**:
    ```sh
    git push -u origin master
    ```

This will upload your local repository's contents to the remote repository on GitHub.

### Summary of Commands

Here’s a summary of the commands used in the steps above:

1. **Initialize a Git repository**:
    ```sh
    git init
    ```

2. **Add files to the repository**:
    ```sh
    git add .
    ```

3. **Commit the files**:
    ```sh
    git commit -m "Initial commit"
    ```

4. **Add a remote repository**:
    ```sh
    git remote add origin https://github.com/yourusername/your-repo-name.git
    ```

5. **Push to the remote repository**:
    ```sh
    git push -u origin master
    ```

### Additional Tips

- **Check the status of your repository**:
    ```sh
    git status
    ```

- **View the commit history**:
    ```sh
    git log
    ```

- **Create and switch to a new branch**:
    ```sh
    git checkout -b new-branch
    ```

- **Merge a branch**:
    ```sh
    git checkout master
    git merge new-branch
    ```

- **Push changes to the remote repository**:
    ```sh
    git push origin master
    ```

## How to deploy your website on heroku using github or git?


### Option 1: Deploying from GitHub

#### Step 1: Prepare Your Code

1. **Push your code to a GitHub repository**.
    ```sh
    cd /path/to/your/project
    git init
    git add .
    git commit -m "Initial commit"
    git remote add origin https://github.com/yourusername/your-repo-name.git
    git push -u origin master
    ```

#### Step 2: Create a Heroku App

1. **Log in to your Heroku account**.
2. **Click on "New"** in the top right corner and select "Create new app".
3. **Fill in the app details**:
   - App name: Choose a unique name
   - Region: Select your region
4. **Click "Create app"**.

#### Step 3: Connect GitHub to Heroku

1. **Navigate to the "Deploy" tab** in your newly created Heroku app.
2. **Select "GitHub" as the deployment method**.
3. **Connect your GitHub account** if you haven't already.
4. **Search for your repository** and connect it.

#### Step 4: Deploy the App

1. **Manual Deployment**: Under "Manual deploy", select the branch you want to deploy (usually `master` or `main`) and click "Deploy Branch".
2. **Automatic Deployment**: Enable automatic deployment if you want Heroku to automatically deploy new commits pushed to the selected branch.

Heroku will now build and deploy your app. You can view the progress and any build errors in the activity log.

### Option 2: Deploying from Git (Heroku CLI)

#### Step 1: Prepare Your Code

1. **Ensure your project is a Git repository**.
    ```sh
    cd /path/to/your/project
    git init
    git add .
    git commit -m "Initial commit"
    ```

#### Step 2: Log in to Heroku

1. **Open your terminal and log in to Heroku**.
    ```sh
    heroku login
    ```

#### Step 3: Create a Heroku App

1. **Create a new Heroku app**.
    ```sh
    heroku create your-app-name
    ```

This command creates a new app and sets up a remote named `heroku` in your Git repository.

#### Step 4: Deploy the App

1. **Push your code to Heroku**.
    ```sh
    git push heroku master
    ```

This command pushes your code to Heroku, and Heroku will automatically build and deploy your app.

### Verification

Once deployed, you can open your app in the browser:
```sh
heroku open
```

You can also view logs to debug any issues:
```sh
heroku logs --tail
```

## Distinguish between Git and GitHub.

![image](https://github.com/ace2884/3-2-shorts/assets/119153850/54da5a70-73c4-4d94-90e7-ea3bd6a23721)

## About git
Git is a distributed version control system used for tracking changes in source code during software development. It enables multiple developers to work on a project simultaneously without interfering with each other's work, ensuring that the complete history of changes is preserved. Here are some key features and concepts of Git:

### Key Features

1. **Version Control**: Git records changes to files over time, allowing you to revert to specific versions.
2. **Branching and Merging**: Git allows you to create branches to work on separate features or bug fixes in isolation. You can later merge these branches back into the main branch.
3. **Distributed Development**: Each developer has a local copy of the entire project history, enabling work offline and more robust backups.
4. **Collaboration**: Git facilitates collaboration by allowing multiple people to work on the same project simultaneously.

### Basic Concepts

- **Repository (Repo)**: A storage location where your project's history is tracked. It can be local (on your computer) or remote (on a server like GitHub).
- **Commit**: A snapshot of your repository at a specific point in time. Commits are used to save your progress.
- **Branch**: A separate line of development. The main branch in a Git repository is typically called `main` or `master`.
- **Merge**: The process of combining changes from different branches.
- **Clone**: Creating a copy of a repository from a remote source.
- **Pull**: Fetching changes from a remote repository and merging them into your local repository.
- **Push**: Sending your local changes to a remote repository.

### Common Commands

- `git init`: Initializes a new Git repository.
- `git clone [url]`: Clones a repository from a remote source.
- `git add [file]`: Stages changes to be committed.
- `git commit -m "message"`: Commits staged changes with a descriptive message.
- `git status`: Shows the current status of your repository.
- `git branch`: Lists all branches in the repository.
- `git checkout [branch]`: Switches to a different branch.
- `git merge [branch]`: Merges a specified branch into the current branch.
- `git pull`: Fetches and merges changes from a remote repository.
- `git push`: Pushes local changes to a remote repository.

Git is widely used in the software development industry due to its robustness, flexibility, and widespread adoption in platforms like GitHub, GitLab, and Bitbucket.
## features and benefits of using Git? 

it is easy to contribute to open source projects via GitHub.

It helps to create an excellent document.

We can attract recruiter by showing off your work. If you have a profile on GitHub, you will have a higher chance of being recruited.

It allows your work to get out there in front of the public.

We can track changes in your code across versions.

## Features of GitHub

GitHub is a place where programmers and designers work together. They collaborate, contribute, and fix bugs together. It hosts plenty of open source projects and codes of various programming languages.

**Some of its significant features are as follows.**

 Collaboration

Integrated issue and bug tracking

Graphical representation of branches

Git repositories hosting

Project management

Team management

Code hosting

Track and assign tasks

Conversations

Wikisc


 ## Version Control System (VCS)

A Version Control System (VCS) is a software tool that helps manage changes to files and directories over time. It keeps track of every modification made to the files, allowing multiple people to collaborate on a project, and provides the ability to revert to previous versions of the files. VCS is essential in software development but can also be used for any set of files that change over time.

### Key Features of Version Control Systems

1. **Tracking Changes**: VCS records changes to files, capturing a history of who changed what and when.
2. **Collaboration**: Multiple users can work on the same project simultaneously without overwriting each other's work.
3. **Branching and Merging**: Users can create branches to work on different tasks independently, which can later be merged back into the main project.
4. **Reversion**: VCS allows users to revert files or entire projects back to previous states, useful for undoing mistakes.
5. **Conflict Resolution**: When changes from different users overlap, VCS provides tools to resolve these conflicts.
6. **Backup and Restore**: VCS serves as a backup mechanism, ensuring that no work is lost and providing the ability to restore previous versions.

### Types of Version Control Systems

1. **Local Version Control Systems**: These keep the version database on a local machine. An example is RCS (Revision Control System).
2. **Centralized Version Control Systems (CVCS)**: These have a single server that contains all the versioned files, and clients check out files from this central place. Examples include Subversion (SVN) and CVS.
3. **Distributed Version Control Systems (DVCS)**: Every user has a complete copy of the repository data. This allows for greater flexibility and reliability. Examples include Git and Mercurial.

### Benefits of Using a Version Control System

- **History and Audit**: Keeps a detailed history of changes, which is useful for auditing and understanding the evolution of a project.
- **Collaboration**: Facilitates collaboration among team members, allowing multiple people to work on different parts of the project simultaneously.
- **Backup**: Provides a built-in backup system, ensuring that changes are not lost and can be recovered.
- **Branching and Experimentation**: Encourages experimentation by allowing developers to create branches, test new features, and merge them if they are successful.

### Common Use Cases

- **Software Development**: Managing source code for software projects, tracking changes, and facilitating collaboration among developers.
- **Document Management**: Keeping track of changes in documents, especially in collaborative environments.
- **Configuration Files**: Managing configuration files for systems, ensuring changes can be tracked and reverted if necessary.

# definitions




### AJAX (Asynchronous JavaScript and XML)
AJAX is a technique for creating fast and dynamic web pages. It allows web pages to be updated asynchronously by exchanging small amounts of data with the server behind the scenes. This means that parts of a web page can be updated without reloading the whole page. AJAX is commonly used with JavaScript and XML, though JSON is more popular for data interchange.

### Node.js
Node.js is a runtime environment that allows you to run JavaScript code on the server side. It is built on the V8 JavaScript engine (the same engine that powers Google Chrome) and enables developers to use JavaScript for server-side scripting to produce dynamic web page content before the page is sent to the user's web browser. Node.js is known for its non-blocking, event-driven architecture, which makes it ideal for building scalable network applications.

### Template Engine
A template engine is used to separate the application’s logic from the presentation layer. It allows developers to use static template files in their applications. At runtime, the template engine replaces placeholders in a template file with actual data and transforms the template into a final HTML document. Popular template engines include EJS, Handlebars, and Pug (formerly Jade).

### AngularJS
AngularJS is a structural framework for dynamic web applications. It lets you use HTML as your template language and extend HTML's syntax to express your application's components clearly and succinctly. AngularJS's data binding and dependency injection eliminate much of the code you would otherwise have to write.

### Angular
Angular (often referred to as Angular 2+ to distinguish it from AngularJS) is a platform and framework for building single-page client applications using HTML and TypeScript. It is a complete rewrite from the same team that built AngularJS. Angular provides a more modular and efficient framework compared to its predecessor, with improved performance and tooling support.

### Bootstrap
Bootstrap is a popular front-end framework for developing responsive and mobile-first websites. It includes HTML, CSS, and JavaScript-based design templates for typography, forms, buttons, navigation, and other interface components. Bootstrap helps developers quickly design and customize responsive mobile-first sites.

### CSS (Cascading Style Sheets)
CSS is a style sheet language used for describing the presentation of a document written in HTML or XML. CSS describes how elements should be rendered on screen, on paper, in speech, or on other media. It is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

### HTML (HyperText Markup Language)
HTML is the standard markup language for creating web pages. It is used to describe the structure of web pages using markup. HTML elements are the building blocks of HTML pages and are represented by tags. HTML provides the basic structure of sites, which is enhanced and modified by other technologies like CSS and JavaScript.

### jQuery
jQuery is a fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, and animation much simpler with an easy-to-use API that works across a multitude of browsers. jQuery also simplifies AJAX calls and provides a lot of utility functions.

### Express
Express is a minimal and flexible Node.js web application framework that provides a robust set of features to develop web and mobile applications. It facilitates the rapid development of Node-based web applications, providing a thin layer of fundamental web application features without obscuring Node.js features.

### MongoDB
MongoDB is a NoSQL database program that uses JSON-like documents with optional schemas. It is designed for high availability and scalability, making it a popular choice for modern web applications that need to handle large amounts of data and diverse data types. MongoDB is known for its flexibility and performance in handling unstructured data.





