
### Table of Contents

| No. | Questions |
|---- | ---------
|1 | [What is Angular Framework?](#what-is-angular-framework)|
|2 | [Why we use Angular ?](#why-we-use-angular )|
|3 | [Angular Components?](#Angular-Components )|



### what is angular framework? 

* Angular is basically is an open-source, JavaScript-based client-side framework that helps us to develop a web-based application
* Angular is one of the best frameworks for developing any Single Page Application

### why we use angular?
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
* Lazy Loading: Lazy loading is based on the concepts of Angular Routing and it helps bring down the size of large files by lazily loading the data that are required.

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

### Angular Components
* Components are the basic building blocks, which control a part of the UI for any application.
* The Component contains the data & user interaction logic that defines how the View looks and behaves. 
* A component is defined using the @Component decorator.
* Every component consists of three parts,
   *  Template which loads the view for the component. There are two ways you can specify the Template in Angular. ie,Inline Template and External Template
   *  The Class provides the data & logic to the View. It contains Properties & Methods associated with Template.
   *  Metadata Provides additional information about the component to the Angular. Angular uses this information to process the class. We use the @Component decorator to       provide the Metadata to the Component.
 
#### Important Component metadata properties
1. selector – It is used to render the components view in the DOM inside the CSS selector,.
2. template- In this property, we can pass the HTML tags or code directly as inline code. 
3. templayeUrl  - This property always accepts the HTML file name with its related file path.
4. styles / stylesUrls - To provide an inline style, we need to use styles, and to provide an external file path or URL, we need to use styleUrls.
5. providers – it is an array and it is used to inject different types of custom services within the component
6. Directives - The directives that this component going to use are listed here.

#### There are several ways we can specify the Component selector
 1. Using element name
   ```javascript
     @Component({ selector: 'app-element'})

    <app-element></app-element>
    ```
    
2. Using the CSS class name
   ```javascript
      @Component({selector: '.app-root'})
    ```
    
    
    ```html
    <div class="app-root"></div>
    ```
    
 3. Using attribute name
   ```javascript
     @Component({ selector: '[app-root]'})
    ```
    
    
    ```html
    <div app-root></div>
    ```




#### Data bindings in Angular

In one-way binding, any changes in the component will directly reflect inside the HTML template but, vice-versa is not possible. Whereas, it is possible in two-way binding
1. __Interpolation__  - Interpolation uses the braces expression {{}} to display  data from the component class to the template. 
1. __Property binding__ - Property binding uses the square brackets [ ] syntax. In Property binding we can bind data from component class to the the DOM properties of an HTML element.
1. __Event Binding__ it works with the event activities of the UI elements like click-event, blur-event.Here data is passing from html template to component class

   28. ### What are pipes?
    A pipe takes in data as input and transforms it to a desired output. For example, let us take a pipe to transform a component's birthday property into a human-friendly date using **date** pipe.

    ```javascript
    import { Component } from '@angular/core';

    @Component({
      selector: 'app-birthday',
      template: `<p>Birthday is {{ birthday | date }}</p>`
    })
    export class BirthdayComponent {
      birthday = new Date(1987, 6, 18); // June 18, 1987
    }
    ```

  **[⬆ Back to Top](#table-of-contents)**
        
    
