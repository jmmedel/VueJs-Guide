

VueJS - Mixins
Advertisements
 Previous Page Next Page  
Mixins are basically to be used with components. They share reusable code among components. When a component uses mixin, all options of mixin become a part of the component options.

Example
<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "databinding"></div>
      <script type = "text/javascript">
         var vm = new Vue({
            el: '#databinding',
            data: {
            },
            methods : {
            },
         });
         var myMixin = {
            created: function () {
               this.startmixin()
            },
            methods: {
               startmixin: function () {
                  alert("Welcome  to mixin example");
               }
            }
         };
         var Component = Vue.extend({
            mixins: [myMixin]
         })
         var component = new Component();
      </script>
   </body>
</html>
Output
Mixins
When a mixin and a component contain overlapping options, they are merged as shown in the following example.

<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "databinding"></div>
      <script type = "text/javascript">
         var mixin = {
            created: function () {
               console.log('mixin called')
            }
         }
         new Vue({
            mixins: [mixin],
            created: function () {
               console.log('component called')
            }
         });
      </script>
   </body>
</html>
Now the mixin and the vue instance has the same method created. This is the output we see in the console. As seen, the option of the vue and the mixin will be merged.

Mixin Overlapping
If we happen to have the same function name in methods, then the main vue instance will take priority.

Example

<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "databinding"></div>
      <script type = "text/javascript">
         var mixin = {
            methods: {
               hellworld: function () {
                  console.log('In HelloWorld');
               },
               samemethod: function () {
                  console.log('Mixin:Same Method');
               }
            }
         };
         var vm = new Vue({
            mixins: [mixin],
            methods: {
               start: function () {
                  console.log('start method');
               },
               samemethod: function () {
                  console.log('Main: same method');
               }
            }
         });
         vm.hellworld();
         vm.start();
         vm.samemethod();
      </script>
   </body>
</html>
We will see mixin has a method property in which helloworld and samemethod functions are defined. Similarly, vue instance has a methods property in which again two methods are defined start and samemethod.

Each of the following methods are called.

vm.hellworld(); // In HelloWorld
vm.start(); // start method
vm.samemethod(); // Main: same method
As seen above, we have called helloworld, start, and samemethod function. samemethod is also present in mixin, however, priority will be given to the main instance, as seen in the following console.