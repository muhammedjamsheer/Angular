
### Table of Contents

| No. | Questions |
|---- | ---------
|1 | [What is Angular Framework?](#what-is-angular-framework)|
|2 | [Why we use Angular ?](#why-we-use-angular )|
|3 | [Angular Components?](#Angular-Components )|
|4 | [Data Bindings in Angular?](#Data-Bindings-in-Angular )|



1.### what is angular framework? 

* Angular is basically is an open-source, JavaScript-based client-side framework that helps us to develop a web-based application
* Angular is one of the best frameworks for developing any Single Page Application

2.### why we use angular?
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


**[⬆ Back to Top](#table-of-contents)**
  
8. ### Angular Components
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

 ```javascript
1. Using element name
    @Component({ selector: 'app-element'})
    <app-element></app-element>

2. Using the CSS class name
    @Component({selector: '.app-root'})
    <div class="app-root"></div>
 
3. Using attribute name
    @Component({ selector: '[app-root]'})
    <div app-root></div>
 ```

  **[⬆ Back to Top](#table-of-contents)**



### Data Bindings in Angular
The data binding in Angular can be broadly classified into two groups. One way binding or two-way binding.

 
In __One way data binding__ data flows from one direction. Either from view to component or from component to view.
examples of one way data bindings are
1. __Interpolation__    - Interpolation uses the double curly braces expression {{}} to display  data from the component class to the template. 
2. __Property Binding__ - In Property binding we can bind data from component class to the the DOM properties of an HTML element.Property binding uses the square brackets [ ] syntax.
3. __Event Binding__ Data flows from the DOM to the component.When a DOM event occurs such as click, hover etc.


 In  __Two way data binding__ Data flows both ways ie, changes made in the HTML template is automatically reflect in the component class and vice versa.
The Angular uses the ngModel directive to achieve the two-way binding.
Two-way data binding = property binding + event binding.

__Interpolation__ 
```javascript
 import { Component } from '@angular/core';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
title = 'Angular Interpolation Example';
getTitle(): string {
     return this.title;
 }
 max(first: number, second: number): number {
  return Math.max(first, second);
 }
}
 ```
 
 ```html
1.Invoke a method in the component
{{getTitle()}}

2.Concatenate two string
<p>Welcome to {{title}}</p>
<p>Welcome {{firstName}}, {{lastName}}</p>
<p>Welcome {{getFirstName()}}, {{getLastName()}}</p>

3.Perform some mathematical operations
<p>100x80 = {{100*80}}</p>
<p>Largest: {{max(100, 200)}}</p>

4.Bind to an element property
 <p>Show me <span class = "{{giveMeRed}}">red</span></p>
 <p style.color={{giveMeRed}}>This is red</p>
 <img src="{{itemImageUrl}}">
 <a href="/product/{{productID}}">{{productName}}</a>

5.Use a template reference variable
 <label>Enter Your Name</label>
 <input (keyup)="0" #name>
 <p>Welcome {{name.value}} </p>

  ```
  
   __Property Binding__

 ```javascript
 import { Component } from '@angular/core';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title="Angular Binding Example"
  isDisabled:boolean== true;
  clickCount=0
  status:string='error';
  cssStringVar: string= 'red size20';
  hasError:boolean=false
  clickMe() {
     this.clickCount++;
  }
  getColor() {
    return 'yellow';
  }
}
 ```
 
 ```html
<h1 [innerText]="title"></h1>
<h2>{{title}}</h2>

Property Binding
--------------------------------------------------------------------------------------------
<button [disabled]="isDisabled">I am disabled</button>

Class Binding in Angular
------------------------
The Angular Class binding is used to add or remove css classes to and from the HTML elements
The Angular provides the three ways to add/remove classes to and from the element. One using the DOM ClassName Property.
The second option is to use the Class shorthand. The third option is to use the NgClass directive,

1.Class binding with ClassName
 <div [className]="'red'">Test</div>
 <div [className]="'red size20'">Test</div>

Conditionally apply Classes
<div [className]="cssStringVar">Test</div>
<div [className]="getClass()">getClass</div>
<div [className]="hasError() ? 'red' : 'size20'"> conditonal operator </div>

2.Class binding with Class
<div [class.<className>]="condition"></div>
className is name of the class, which you want to bind to.
condition must return true or false. A return value of true adds the class and a false removes the class.
<div [class.red]="hasError" [class.size20]="hasError">Test</div>

Style binding in Angular
------------------------
Syntax -> [style.style-property] = "style-value"

<p [style.color]="'red'">Give me red</p>
<p [style.background-color]="'grey'">some paragraph with grey background</p>
<button [style.border]="'5px solid yellow'">Save</button>
<button [style.font-size.px]="'20'" >Big Button</button>

Conditionally setting the styles
<button [style.color]="status=='error' ? 'red': 'blue'">Button 1</button>
<button [style.color]="getColor()">Button 2</button> 

Setting Multiple styles
<p [style.color]="getColor()" [style.font-size.px]="'20'"   [style.background-color]="status=='error' ? 'red': 'blue'">
   paragraph with multiple styles </p>

Event Binding
------------------------------------------------------------------------------------------------
<button (click)="clickMe()">Save</button>

Instead of parentheses, you can also use the on- syntax as shown below.
<button on-click="clickMe()">Click Me</button>

We can also bind an unlimited number of event handlers on the same event by separating them with a semicolon ;
<button (click)="clickMe() ; clickCount1=clickCount">Click Me</button>

DOM Events carries  the information about the event.
<input (input)="handleInput($event)">

We can also make use of the template reference variable to pass the value instead of $event.
<input #el (input)="handleInput(el)">


  ```
 
 

        
    
