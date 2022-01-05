
### Table of Contents

| No. | Questions |
|---- | ---------
|1 | [What is Angular Framework?](#what-is-angular-framework)|
|2 | [Why we use Angular ?](#why-we-use-angular )|
|3 | [Angular Decorators](#Angular-Decorators )|
|4 | [Angular Components](#Angular-Components )|
|5 | [Data Bindings in Angular](#Data-Bindings-in-Angular )|
|6 | [Angular Component Cammunication](#Angular-Component-Cammunication)|
|7 | [Angular Directives](#Angular-Directives )|
|8 | [Angular Pipes](#Angular-Pipes)|
|9 | [Component Life Cycle Hook](#Component-Life-Cycle-Hook)|



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
  
8. ### Angular Decorators
  Decorators are design patterns used to isolate the modification or decoration of a class without modifying the source code. 
  Decorators are the features of Typescript and are implemented as functions. The name of the decorator starts with @ symbol following by brackets and arguments.    
  
__1.Class Decorators__
Class Decorators are the top-level decorators that are used to define the purpose for the classes. 
They provide information to Angular that a particular class is a component, or module

__@NgModule Decorator__       
It defines the class is an Angular Module and  provides metadata about the module.

__@Component Decorator__      
It defines the class is an Angular Component and  provides metadata about the component.  

__@Injectable Decorator___
It Declares that a class has dependencies that should be injected into the constructor when the dependency injector is creating an instance of this class.       

__@Directive Decorator___   
It defines the class as an Angular directive. The directives help us to change the appearance, behavior, or layout of a DOM element.

__@Pipe Decorator___     
It defines the class as an  Angular Pipe  and provides metadata about the pipe.

__2.Property Decorators__
Property Decorators are applied to the properties of the class.

__@Input__          
Input decorator marks the property as the input property. I.e it can receive data from the parent component.     
The parent component uses the property binding to bind it to a component property. Whenever the value in the parent component changes angular updates the value in the child component. 

__@Output__    
It Declares an output property that fires events that you can subscribe to with an event binding      
We initialize it as an EventEmitter. The child component raises the event and passes the data as the argument to the event. The parent component listens to events using event binding and reads the data. 

__@ContentChild & @ContentChildren__      
The ContentChild & ContentChildren are decorators, which we use to Query and get the reference to the Projected Content in the DOM. Projected content is the content that this component receives from a parent component.  

__@ViewChild & @ViewChildren__       
The ViewChild or ViewChildren decorators are used to Query and get the reference of the DOM element in the Component. ViewChild returns the first matching element and ViewChildren returns all the matching elements as QueryList of items. We can use these references to manipulate element properties in the component. 

__@HostBinding__           
The HostBinding allows us to bind to a property of the host element. The host is an element on which we attach our component or directive. This feature allows us to manipulate the host styles.   


__3.Method Decorators__
Method Decorators are applied to the methods of the class.

__@HostListener__          
The HostListener listens to host events. The host is an element on which we attach our component or directive. Using HostListener we can respond whenever the user performs some action on the host element.  

__4.Parameter Decorators__
Parameter Decorators are applied to the constructor parameter of the class.
@Inject  @Host @Self @SkipSelf


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
2. template /  templayeUrl - To provide an inline template, we need to use template (Here we write Html tags directly), and to provide an external file path or URL, we need to use templayeUrl (Here we write URL of an external file that contains a template for the view) . 
3. styles / stylesUrls - To provide an inline style, we need to use styles, and to provide an external file path or URL, we need to use styleUrls. 
4. providers – it is an array and it is used to inject different types of custom services within the component
5. Directives - The directives that this component going to use are listed here.

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
1. __Interpolation__    - In interpolation data flows from the component class to the template and it uses the double curly braces expression {{}} to display  data. 
2. __Property Binding__ -  In Property binding data flows from thecomponent class to the the DOM properties of an HTML element.Property binding uses the square brackets [ ] for data binding.
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
  status:string='error';
  cssStringVar: string= 'red size20';
  hasError:boolean=false
  getColor() {
    return 'yellow';
  }
}
 ```
 
 ```html

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

  ```
   __Event Binding__

 ```javascript
 import { Component } from '@angular/core';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  clickCount=0
  clickMe() {
     this.clickCount++;
  }
}
 ```
 
 ```html
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
  
  
 **[⬆ Back to Top](#table-of-contents)**


### Angular Component Cammunication

we can share data between component in many ways.          
__1.Parent to Child Cammunication__                        
 If the Components have a parent-child relationship,then we  can pass the data from the parent component to the child using the __@input__ Property.   
 In parent component we are using property binding. here we bind the transfering  data .Whenever the value in the parent component changes angular updates the value in the     child component. In the child component, we are using @Input decorator to capture data coming from a parent component 
 
 __2.Child to Parent Communication__            
  we can pass data from child component to parent component in two ways.     

   1.using @ViewChild decorator.     
   * ViewChild allows the child component to be injected in to the  parent component.In this way  the parent component can  access  attributes and functions of child component.
   * To receive the data from the child we need to implement the AfterViewInit lifecycle hook.
   * It is used to reference the child component as “child” property.

   2.using @Output and EventEmitter.
   
   * This method is used when we  want to share data changes when an event occurs  like button clicks, form entires etc.
   * This is done by using a combination of @Output() decorator and EventEmitter() interface.
   * The child component raises the event and passes the data as the argument to the event. The parent component listens to events using event binding and reads the data

__3.Between Non-relational Components__   
   * If the two components doesn't have a relation, We can Passing Data Through a Service Using Observables.                            
   * We will use a shared service, subject variable, and subscription variable to share data between unrelated components.              
   * We have added a subject variable inside the service.           
   * We will emit the data from first component using this subject variable.We can emit any type of data from subject variable.                                                 
   * We will subscribe this subject variable in another component and receive the data, which is sent by the first component.


https://www.freakyjolly.com/how-angular-components-communicate-pass-emit-or-broadcast-data-4-ways-with-examples/


__Example of parent to child cammunication__      
parentcomponent.html    
 ```html
<div>
    <p>Parent component</p>
    <app-child [name]="'jamsheer'"></app-child>
</div>
 ```
 
 childcomponent.ts       
  ```javascript
import { Component, OnInit, Input } from '@angular/core';
@Component({
     selector: 'app-child',
     templateUrl: './child.component.html',
     styleUrls: ['./child.component.scss']
})
export class ChildComponent implements OnInit {
     @Input() name: string
     constructor() { }
     ngOnInit(): void { }
}
 ```
 
 
__Example of child to parent cammunication using @Output and EventEmitter__

on click button ths player name is transfered to parent     
 childcomponent.ts                         
  ```javascript
import { Component, OnInit, Output,EventEmitter } from '@angular/core';
@Component({
     selector: 'app-child',
     templateUrl: './child.component.html',
     styleUrls: ['./child.component.scss']
})
export class ChildComponent implements OnInit {
     @Output() selectedPlayer = new EventEmitter();
     Players=["Messi","Ronoldo","Salah","Neymar"];
     constructor() { }
     ngOnInit(): void { }
     OnSelectPlayer(player:string) {
       this.selectedPlayer.emit(player);
     }
}
  ```   
  
   childcomponent.html                    
  ```html
  <button style="margin-left: 10px" class="btn btn-primary" *ngFor="let player of Players"
    (click)="OnSelectPlayer(player)">{{player}}</button>
  ```
  
  parentcomponent.html                                    
  ```html
<div>
    <p>Parent component</p>
    <div>{{selectedPlayer}}</div>
    <app-child (selectedPlayer)="onPlayerSelection($event)"></app-child>
</div>  
  ```
   parentcomponent.ts                                              
 ```javascript
import { Component, OnInit, Input } from '@angular/core';
@Component({
     selector: 'app-parent',
     templateUrl: './parent.component.html',
     styleUrls: ['./parent.component.scss']
})
export class ParentComponent implements OnInit {
     ngOnInit(): void {}
     selectedPlayer: string;
     onPlayerSelection(player: string) {
     this.selectedPlayer = player;
  }
}
```

### Angular Directives
The Angular directive helps us to manipulate the DOM. You can change the appearance, behavior, or layout of a DOM element using the directives. They help you to extend HTML.                
The Angular directives are classified into three categories based on how they behave.  They are Component, Structural and Attribute Directives.   
__1.Component Directive__                 
 Components are the directives  with a template.                
 __2.Structural  Directive__              
 Structural directives can change the DOM layout by adding and removing DOM elements. All structural Directives are preceded by Asterix symbol.
 
 Commonly used structural directives are ngIf ,ngFor,ngSwitch,
 * __ngIf__                  
 The ngIf Directives is used to add or remove HTML elements based on an expression. The expression must return a boolean value. If the expression is false then the element is removed, else the element is inserted
 
  * __ngFor__               
  The ngFor is an Angular structural directive, which repeats a portion of the HTML template once per each item from an iterable list.                
  
  * __ngSwitch__  
  The ngSwitch directive lets you add/remove HTML elements depending on a match expression. ngSwitch directive used along with ngSwitchCase and ngSwitchDefault. 
  
   __3.Attribute  Directive__                      
   An Attribute or style directive can change the appearance or behavior of an element.             
   
   Commonly used Attribute directives are ngModel, ngClass ,ngStyle        
   
  * __ngModel__                     
  The ngModel directive is used the achieve the two-way data binding.           
    
  * __ngClass__         
  The ngClass directive is used to add or remove the CSS classes from an HTML element. Using the ngClass we can create dynamic styles in HTML pages.                  
  
  * __ngStyle__         
  The ngStyle directive is used  to modify the style of an HTML element using the expression.  Using the ngStyle we can dynamically change the style of your HTML element.       
  
  
  ### Angular Pipes
 
Pipes are simple functions designed to accept an input value and return a transformed value as the output.             
Angular Pipes are the class with @Pipe decorator.            
syntax  :-  {{ input| pipeName : param1: param2: ...}}             

Angular supports many built-in pipes. we can also create custom pipes based on our requirements.  

Some commonly used predefined Angular pipes are:                              
* __UpperCasePipe__   -It transforms text to uppercase.      eg:-  {{name|uppercase}}      
* __LowerCasePipe__   -It transforms text to lowercase.      eg:-  {{name|lowercase}}    
* __TitleCasePipe__   -It transforms text to titlecase.      eg:-  {{name|titlecase}} 
* __DatePipe__        -It is used to format dates.           eg:-  {{today|date}}  ,  {{today|date:'short'}}  ,  {{today|date:'dd-mm-yy'}} 
        
    
