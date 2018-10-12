

VueJS - Introduction
Advertisements
 Previous Page Next Page  
Vue is a JavaScript framework for building user interfaces. Its core part is focused mainly on the view layer and it is very easy to understand. The version of Vue that we are going to use in this tutorial is 2.0.

As Vue is basically built for frontend development, we are going to deal with lot of HTML, JavaScript and CSS files in the upcoming chapters. To understand the details, let us start with a simple example.

In this example, we are going to use the development verison of vuejs.

Example
<html>
   <head>
      <title>VueJs Introduction</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "intro" style = "text-align:center;">
         <h1>{{ message }}</h1>
      </div>
      <script type = "text/javascript">
         var vue_det = new Vue({
            el: '#intro',
            data: {
               message: 'My first VueJS Task'
            }
         });
      </script>
   </body>
</html>
Output
First VueJS
This is the first app we have created using VueJS. As seen in the above code, we have included vue.js at the start of the .html file.

<script type = "text/javascript" src = "js/vue.js"></script>
There is a div which is added in the body that prints “My first VueJS Task” in the browser.

<div id = "intro" style = "text-align:center;">
   <h1>{{ message }}</h1>
</div>
We have also added a message in a interpolation, i.e. {{}}. This interacts with VueJS and prints the data in the browser. To get the value of the message in the DOM, we are creating an instance of vuejs as follows −

var vue_det = new Vue({
   el: '#intro',
   data: {
      message: 'My first VueJS Task'
   }
})
In the above code snippet, we are calling Vue instance, which takes the id of the DOM element i.e. e1:’#intro’, it is the id of the div. There is data with the message which is assigned the value ‘My first VueJS Task’. VueJS interacts with DOM and changes the value in the DOM {{message}} with ’My first VueJS Task’.

If we happen to change the value of the message in the console, the same will be reflected in the browser. For example −

VueJS Interesting
Console Details
VueJS is Interesting
In the above console, we have printed the vue_det object, which is an instance of Vue. We are updating the message with “VueJs is interesting” and the same is changed in the browser immediately as seen in the above screenshot.

This is just a basic example showing the linking of VueJS with DOM, and how we can manipulate it. In the next few chapters, we will learn about directives, components, conditional loops, etc.

