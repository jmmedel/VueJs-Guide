

VueJS - Template
Advertisements
 Previous Page Next Page  
We have learnt in the earlier chapters, how to get an output in the form of text content on the screen. In this chapter, we will learn how to get an output in the form of HTML template on the screen.

To understand this, let us consider an example and see the output in the browser.

<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "vue_det">
         <h1>Firstname : {{firstname}}</h1>
         <h1>Lastname : {{lastname}}</h1>
         <div>{{htmlcontent}}</div>
      </div>
      <script type = "text/javascript" src = "js/vue_template.js"></script>
   </body>
</html>
vue_template.js
var vm = new Vue({
   el: '#vue_det',
   data: {
      firstname : "Ria",
      lastname  : "Singh",
      htmlcontent : "<div><h1>Vue Js Template</h1></div>"
   }
})
Now, suppose we want to show the html content on the page. If we happen to use it with interpolation, i.e. with double curly brackets, this is what we will get in the browser.

Content
If we see the html content is displayed the same way we have given in the variable htmlcontent, this is not what we want, we want it to be displayed in a proper HTML content on the browser.

For this, we will have to use v-html directive. The moment we assign v-html directive to the html element, VueJS knows that it has to output it as HTML content. Let’s add v-html directive in the .html file and see the difference.

<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "vue_det">
         <h1>Firstname : {{firstname}}</h1>
         <h1>Lastname : {{lastname}}</h1>
         <div v-html = "htmlcontent"></div>
      </div>
      <script type = "text/javascript" src = "js/vue_template.js"></script>
   </body>
</html>
Now, we don’t need the double curly brackets to show the HTML content, instead we have used v-html = ”htmlcontent” where htmlcontent is defined inside the js file as follows −

var vm = new Vue({
   el: '#vue_det',
   data: {
      firstname : "Ria",
      lastname  : "Singh",
      htmlcontent : "<div><h1>Vue Js Template</h1></div>"
   }
})
The output in the browser is as follows −

HTMLContent
If we inspect the browser, we will see the content is added in the same way as it is defined in the .js file to the variable htmlcontent : "<div><h1>Vue Js Template</h1></div>".

Let’s take a look at the inspect element in the browser.

Template
We have seen how to add HTML template to the DOM. Now, we will see how to add attributes to the exiting HTML elements.

Consider, we have an image tag in the HTML file and we want to assign src, which is a part of Vue.

Example
<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "vue_det">
         <h1>Firstname : {{firstname}}</h1>
         <h1>Lastname : {{lastname}}</h1>
         <div v-html = "htmlcontent"></div>
         <img src = "" width = "300" height = "250" />
      </div>
      <script type = "text/javascript" src = "js/vue_template1.js"></script>
   </body>
</html>
Look at the img tag above, the src is blank. We need to add the src to it from vue js. Let us take a look at how to do it. We will store the img src in the data object in the .js file as follows −

var vm = new Vue({
   el: '#vue_det',
   data: {
      firstname : "Ria",
      lastname  : "Singh",
      htmlcontent : "<div><h1>Vue Js Template</h1></div>",
      imgsrc : "images/img.jpg"
   }
})
If we assign the src as follows, the output in the browser will be as shown in the following screenshot.

<img src = "{{imgsrc}}" width = "300" height = "250" />Imgsrc
We get a broken image. To assign any attribute to HMTL tag, we need to use v-bind directive. Let’s add the src to the image with v-bind directive.

This is how it is assigned in .html file.

<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "vue_det">
         <h1>Firstname : {{firstname}}</h1>
         <h1>Lastname : {{lastname}}</h1>
         <div v-html = "htmlcontent"></div>
         <img v-bind:src = "imgsrc" width = "300" height = "250" />
      </div>
      <script type = "text/javascript" src = "js/vue_template1.js"></script>
   </body>
</html>
We need to prefix the src with v-bind:src = ”imgsrc” and the name of the variable with src.

Following is the output in the browser.

Img Display
Let us inspect and check how the src looks like with v-bind.

Inspect
As seen in the above screenshot, the src is assigned without any vuejs properties to it.

