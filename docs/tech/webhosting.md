# Webhosting
```query
children:.
```
---

## Hosting a Webpage
At the highest level, these are the components needed to have a web browser display a webpage from a server:

###### **The browser must be able to send a standardised request to the server for the webpage.**
This is done using the HTTP application layer protocol. See [[http]]#.

###### **The server must be able to parse the request and send back the required files.**
This is done using an HTTP web server. See [[web-servers]]#

###### **The browser must be able to parse said files to display the content on screen.**
Most browsers have very similar ways of representing things and abilities to represent things on screen. Browsers expect an HTML file to render, which may refer to stylesheets (css) and scripts (javascript).

Stylesheets and scripts called out within the HTML file are requested by HTTP using the endpoint provided.

### The Server
Usually, the server used will be a linux server. See [[linux]]# for more.

## Creating a Webpage
### Module bundlers
Writing all the scripting for a webpage in one javascript file is absolute hell for any decently sized page. As such, module bundlers exist to allow you to write your code in a modular fashion, that is then bundled into one file. See [[vite]]# for an example of how a module bundler works.

### Javascript Frameworks
A javascript framework provides a huge amount of prewritten code that, by developing in the way the framework instructs you to, allows the following benefits:

* **DOM Abstraction:** Having to structure an HTML file to then edit specific components based only on string references is very limiting. Instead, a framework will abstract this away and allow you to build the website directly through code, allowing for: 
    * better control over components;
    * reusing components; and
    * binding components to the underlying data so they update when the data does.
* **Routing Management:** The framework can handle routing logic, allowing for common content between pages that doesn't reload, or routing in single page applications.
* **Structure and Organisation:** The framework provides as specific way of structuring and organising your project.

The most common javascript framework is call React. See [[react]]# for more.

### Syncing Server with a Repository
Generally, development will occur off of the actual server that hosts the webpage, and instead it should be kept up to date with a repository's main branch. This can be done using webhooks to notify the server whenever the repository updates. See [[webhooks]]# for more.

### Monoliths vs Microservices
Monolith applications use one service to run the entire application. However, this has a numnber of drawbacks:
* Simultaneous development on different parts of the monolith is more difficult and slower.
* Different components within the application can become unnecessarily entangled.
* Different parts of the application cannot be scaled separately.
* Any error can take down the entire application.
* The one programming language used may not be suited for all tasks the application must perform.

To solve this, the microservices architecture can be used. This means that separate components are separate services. The main downside is they have to use some sort of application layer protocol to communicate with each other. See [[application-layer-communication]]# for more.

For websites, I personally think the best split is to have three services: frontend, backend, database.

### Docker
Whether it be for a web server or a specific service in a microservice architecture application, a docker image can be used to run a service the same way on any machine. See [[docker]] for more.
