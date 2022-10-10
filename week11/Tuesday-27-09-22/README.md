## Tuesday 27/09/22

### Node.JS Core Understanding Learning Exercise

**1. What is Node.JS?**

Node.JS is a JavaScript runtime enviroment, it means the enviroment in which a program is executed.


**2. What problem does Node.JS solve?**

Node.JS allows to execute programs outside a web browser.

**3. What is the V8 Javascript Engine?**

Is a javascript engine developed by google and is used in the google chrome web browser.

**4. Is Node.JS really necessary in the Development ecosystem?**

Is really necessary because it allows to use JavaScript code in the Server side of project developing and not just in the front-end.

**5. What is the difference between Node.JS and any other browser?**

in Node.JS you can interact with the file system and have unrestricted access. In browsers you can interact only with DOM elements inside the browser.

**6. What is NVM and Why is it useful for Node.JS developers?**

NVM stands for Node Version Manager. It allows you to quickly install and use different versions of Node.JS via command line. Its useful for developers when they need to switch between node versions based on the project they are working.


### Node.JS Module System Core Understanding Learning Exercise

**1. What is a Javascript Module?**

Modules are groups of functions that executes specific tasks and can be integrated in different applications.

**2. Why are Javascript Modules necessary?**

They are neccessary to structure a larger program into smaller components, and also to allow the reusability of code.

**3. What module standards are available in Node.JS?**

The module standards are ES modules and CommonJS modules.

**4. What are the differences between ESModules and CommonJS modules?**

ES modules are the standard for JavaScript used in browsers, and CommonJS are the ones used as default in Node.JS.

**5. Which types of modules exist in Node.JS?**

Node.js includes three types of modules:

- Core Modules

  Modules loaded at the Node.JS start.

- Local Modules

  Modules created locally in a Node.JS app.

- Third Party Modules

  Modules developed and manitained by 3rd parties. Can be downloaded and installed using npm.

## Node.JS Module System - Practice

### Description

Time to put into practice what you learned about Node.JS modules 😁.

1. Create a new Node.JS project, name it: `<your-nickname>/modules`
2. Create a new module, name it: `operations.js`
3. Inside `operations.js` implement two functions, one for the sum operation
   and one for the subtract operation.
4. Create a new module, name it: `main.js`
5. Import the functions implemented in `operations.js` and use them in any
   way in `main.js`.

[**Solution**](https://github.com/kennethpHN/core-code-from-scratch/tree/main/week11/Tuesday-27-09-22/kennethpHN)

### Client-Server Model Learning Exercise

**1. What is a Server?**

A server is a program or device that manages resources in a network and offers services requested by other devices or programs.

**2. What is a client?**

its a device or program that sends requests to a server and uses its resources.

**3. Is a server just another physical computer?**

A Server can be a software located in the same device as the client or in a dedicated device for itself.

  - Why do we refer to a certain class of applications as Servers?
  
  Because those applications are designed to manage requests from another application on the client side

**4. Is there any similarity between human communication and the client-server model?**

It is, since one side can request something and the other side sends a response to that request.

**5. Is the client-server model applicable only to the Web?**

No, one example can be a computer and a printer in an office, the client computer sends a print request to the office server, and then the server sends the printing task to the printer.


  

  
