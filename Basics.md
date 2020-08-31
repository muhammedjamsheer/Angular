
### What is Angular?

* Angular is basically is an open-source, JavaScript-based client-side framework that helps us to develop a web-based application
* Angular is one of the best frameworks for developing any Single Page Application

### Why we use Angular ?
* Angular is supported by google (saftey and updated)
* Typescript used in angular is a product of microsoft. So both are  open source and freely available
* Angular is based on modular approch.
* Angular is following component structure.By using components we can reuse codes and make testing easy
* Dependency injection- it  allows a class to receive dependencies from another class.
* Command Line Interface (CLI) –The Angular CLI is a command-line interface tool that you use to initialize, develop, and maintain Angular applications directly from a command       shell.This way, development and testing processes both become faster.

### Advantages of Using Angular
* Supports two-way data binding.
* Supports validations and template syntax (both angular and static).
* We can add custom animations, directives, and services.
* Hierarchical Dependency Injection structure (Parent-child).
* Provision to facilitate RESTful services and client-server communication.

### Project Folder Structure
1. e2e - This folder is for an end to end testing purposes. It contains the configuration files related to performing the unit test of the projects.
1. node_modules - This folder contains the downloaded packages as per the configuration.
1. src - This folder contains the actual source code. It contains 3 subfolders as – 
   1. app - App folder contains the Angular project-related files like components, HTML files, etc.
   1. assets - Assets folder contains any static files like images, stylesheets, custom javascript library files.
   1. environments - Environments folder contains the environment-related files which are required during  build of the projects.
#### Different Config Files   
1. package.json-it is basically a JSON file that contains all information related to the required packages for the project.
1. angular.json – angular.json file is an Angular Application Environment based JSON file which contains all the information related to the project build and deployment. It tells the system which files need to change when we use ng build or ng serve command. 

### Components
* components are the basic building blocks, which control a part of the UI for any application.
* A component is defined using the @Component decorator.
* Every component consists of three parts,
   *  Template which loads the view for the component, 
   *  class that  contains properties and methods that supports the view.
   *  metadata (defined using decorator).
   
#### @Component Metadata
1. selector – A component can be used by the selector expression. 
2. templayeUrl  - This property always accepts the HTML file name with its related file path.
3. styles / stylesUrls - To provide an inline style, we need to use styles, and to provide an external file path or URL, we need to use styleUrls.
4. providers – it is used to inject different types of custom services within the component

   
        
    
