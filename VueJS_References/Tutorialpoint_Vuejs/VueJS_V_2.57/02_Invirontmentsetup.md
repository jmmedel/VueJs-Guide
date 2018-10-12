
VueJS - Environment Setup
Advertisements
 Previous Page Next Page  
There are many ways to install VueJS. Some of the ways on how to carry out the installation are discussed ahead.

Using the <script> tag directly in HTML file
<html>
   <head>
      <script type = "text/javascript" src = "vue.min.js"></script>
   </head>
   <body></body>
</html>
Go to the home site https://vuejs.org/v2/guide/installation.html of VueJS and download the vue.js as per need. There are two versions for use - production version and development version. The development version is not minimized, whereas the production version is minimized as shown in the following screenshot. Development version will help with the warnings and debug mode during the development of the project.

Installation
Using CDN
We can also start using VueJS file from the CDN library. The link https://unpkg.com/vue will give the latest version of VueJS. VueJS is also available on jsDelivr (https://cdn.jsdelivr.net/npm/vue/dist/vue.js) and cdnjs (https://cdnjs.cloudflare.com/ajax/libs/vue/2.4.0/vue.js).

We can host the files at our end, if required and get started with VueJS development.

Using NPM
For large scale applications with VueJS, it is recommended to install using the npm package. It comes with Browserify and Webpack along with other necessary tools, which help with the development. Following is the command to install using npm.

npm  install vue
Using CLI Command Line
VueJS also provides CLI to install the vue and get started with the server activation. To install using CLI, we need to have CLI installed which is done using the following command.

npm install --global vue-cli
CLI Command Line
Once done, it shows the CLI version for VueJS. It takes a few minutes for the installation.

+ vue-cli@2.8.2
added 965 packages in 355.414s
Following is the command to create the project using Webpack.

vue init webpack myproject
Select Command Prompt
To get started, use the following command.

cd myproject
npm install
npm run dev
Command Prompt
NPM
Once we execute npm run dev, it starts the server and provides the url for display to be seen in the browser which is as shown in the following screenshot.

Welcome to VueJS
The project structure using CLI looks like the following.
