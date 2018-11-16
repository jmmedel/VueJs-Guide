

VueJS - Reactive Interface
Advertisements
 Previous Page Next Page  
VueJS provides options to add reactivity to properties, which are added dynamically. Consider that we have already created vue instance and need to add the watch property. It can be done as follows −

Example
<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "app">
         <p style = "font-size:25px;">Counter: {{ counter }}</p>
         <button @click = "counter++" style = "font-size:25px;">Click Me</button>
      </div>
      <script type = "text/javascript">
         var vm = new Vue({
            el: '#app',
            data: {
               counter: 1
            }
         });
         vm.$watch('counter', function(nval, oval) {
            alert('Counter is incremented :' + oval + ' to ' + nval + '!');
         });
         setTimeout(
            function(){
               vm.counter = 20;
            },2000
         );
      </script>
   </body>
</html>
There is a property counter defined as 1 in data object. The counter is incremented when we click the button.

Vue instance is already created. To add watch to it, we need to do it as follows −

vm.$watch('counter', function(nval, oval) {
   alert('Counter is incremented :' + oval + ' to ' + nval + '!');
});
We need to use $watch to add watch outside the vue instance. There is an alert added, which shows the value change for the counter property. There is also a timer function added, i.e. setTimeout, which sets the counter value to 20.

setTimeout(
   function(){
      vm.counter = 20;
   },2000
);
Whenever the counter is changed, the alert from the watch method will get fired as shown in the following screenshot.

Counter
VueJS cannot detect property addition and deletion. The best way is to always declare the properties, which needs to be reactive upfront in the Vue instance. In case we need to add properties at run time, we can make use of Vue global, Vue.set, and Vue.delete methods.

Vue.set
This method helps to set a property on an object. It is used to get around the limitation that Vue cannot detect property additions.

Syntax
Vue.set( target, key, value )
Where,

target: Can be an object or an array

key : Can be a string or number

value: Can be any type

Let’s take a look at an example.

Example
<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "app">
         <p style = "font-size:25px;">Counter: {{ products.id }}</p>
         <button @click = "products.id++" style = "font-size:25px;">Click Me</button>
      </div>
      <script type = "text/javascript">
         var myproduct = {"id":1, name:"book", "price":"20.00"};
         var vm = new Vue({
            el: '#app',
            data: {
               counter: 1,
               products: myproduct
            }
         });
         vm.products.qty = "1";
         console.log(vm);
         vm.$watch('counter', function(nval, oval) {
            alert('Counter is incremented :' + oval + ' to ' + nval + '!');
         });
      </script>
   </body>
</html>
In the above example, there is a variable myproduct created at the start using the following piece of code.

var myproduct = {"id":1, name:"book", "price":"20.00"};
It is given to the data object in Vue instance as follows −

var vm = new Vue({
   el: '#app',
   data: {
      counter: 1,
      products: myproduct
   }
});
Consider, we want to add one more property to the myproduct array, after the Vue instance is created. It can be done as follows −

vm.products.qty = "1";
Let’s see the output in the console.

MyProduct Array
As seen above, in products the quantity is added. The get/set methods, which basically adds reactivity is available for the id, name, and price, and not available for qty.

We cannot achieve the reactivity by just adding vue object. VueJS mostly wants all its properties to be created at the start. However, in case we need to add it later, we can use Vue.set. For this, we need to set it using vue global, i.e. Vue.set.

Example
<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "app">
         <p style = "font-size:25px;">Counter: {{ products.id }}</p>
         <button @click = "products.id++" style = "font-size:25px;">Click Me</button>
      </div>
      <script type = "text/javascript">
         var myproduct = {"id":1, name:"book", "price":"20.00"};
         var vm = new Vue({
            el: '#app',
            data: {
               counter: 1,
               products: myproduct
            }
         });
         Vue.set(myproduct, 'qty', 1);
         console.log(vm);
         vm.$watch('counter', function(nval, oval) {
            alert('Counter is incremented :' + oval + ' to ' + nval + '!');
         });
      </script>
   </body>
</html>
We have used Vue.set to add the qty to the array using the following piece of code.

Vue.set(myproduct, 'qty', 1);
We have consoled the vue object and following is the output.

Products
Now, we can see the get/set for qty added using Vue.set.

Vue.delete
This function is used to delete the property dynamically.

Example
Vue.delete( target, key )
Where,

target: Can be an object or an array

key: Can be a string or a number

To delete any property, we can use Vue.delete as in the following code.

Example
<html>
   <head>
      <title>VueJs Instance</title>
      <script type = "text/javascript" src = "js/vue.js"></script>
   </head>
   <body>
      <div id = "app">
         <p style = "font-size:25px;">Counter: {{ products.id }}</p>
         <button @click = "products.id++" style = "font-size:25px;">Click Me</button>
      </div>
      <script type = "text/javascript">
         var myproduct = {"id":1, name:"book", "price":"20.00"};
         var vm = new Vue({
            el: '#app',
            data: {
               counter: 1,
               products: myproduct
            }
         });
         Vue.delete(myproduct, 'price');
         console.log(vm);
         vm.$watch('counter', function(nval, oval) {
            alert('Counter is incremented :' + oval + ' to ' + nval + '!');
         });
      </script>
   </body>
</html>
In the above example, we have used Vue.delete to delete the price from the array using the following piece of code.

Vue.delete(myproduct, 'price');
Following is the output, we see in the console.

Delete
After deletion, we can see only the id and name as the price is deleted. We can also notice that the get/set methods are deleted.
