### Table of Contents

| No. | Questions |
|---- | ---------
|1 | [What is Angular Framework?](#what-is-angular-framework)|
|2 | [Why we use angular?](#Why-we-use-angular)|
|3 | [What is Angular Component?](#What-is-Angular-Component)|
|3 | [What are lifecycle hooks available?](#What-are-lifecycle-hooks-available)|
|4 | [What is the difference between constructor and ngOnInit?](#what-is-the-difference-between-constructor-and-ngoninit)|
|4 | [What is Modules?](#What-is-Modules)|
|4 | [What is ViewEncapsulation?](#What-is-ViewEncapsulation)|
|4 | [What is  data binding?](#What-is-ViewEncapsulation)|




###  1. What is Angular Framework?
Angular is basically is an open-source,client-side typescript-based  framework  for developing web applications.
Angular is one of the best frameworks for developing any Single Page Application

**[⬆ Back to Top](#table-of-contents)**


### 2.  Why we use angular?
1. Angular is supported by google
1. Typescript used in angular is a product of microsoft ,typescript  helps make our code easier to read and avoid errors
1. Angular is based on modular approch.The modules consits of components, directives, pipes, or services.Modules make application functionality organization easy and reusable      and  Modules also allow for lazy loading,
1. Declarative UI - Angular uses HTML to render the UI of an application. HTML isa declarative language and is much easier to use than JavaScript.
1. Support for two-way data-binding
1. Supports dependency injection, RESTful services, and validations
1. Command Line Interface (CLI) –The Angular CLI is a command-line interface tool that you use to initialize, develop, and maintain Angular applications directly from a command      shell.by This way, development and testing processes both become faster.

**[⬆ Back to Top](#table-of-contents)**

###  1. What is Angular Component?
* In Angular, components are the basic building blocks, which control a part of the UI for any application.
* A component is defined using the @Component decorator.
*  Every component consists of three parts, the template which loads the view for the component, a stylesheet which defines the look and feel for the component, and a class that    contains the business logic for the component.

**[⬆ Back to Top](#table-of-contents)**


###  1. What are lifecycle hooks available?
1. **constructor:** constructor is called when a component or directive is created by calling new on the class.
1. **ngOnChanges:** This event executes every time, when the value of an input control within the component has been changed.
1. **ngOnInit:** This event executed at the time of Component initialization. This event is called only once, just after the ngOnChanges() events.
1. **ngDoCheck:** This event is executed every time when the input properties of a component are checked.
1. **ngAfterViewInit:** TThis life cycle method executes when the component completes the rendering of its view full.
1. **ngOnDestroy:** This method will be executed when we want to destroy the Angular components.  This method is very useful for unsubscribing the observables and detaching the     event handlers to avoid memory leaks..

**[⬆ Back to Top](#table-of-contents)**

### 1. What is the difference between constructor and ngOnInit?
* constructor is a default method in TypeScript classes which is normally used for the initialization purpose.
* ngOnInit is a life cycle hook method in  Angular, especially used to define Angular bindings.
* The constructor getting called first before ngOnInit method. 


###  1. What is ViewEncapsulation?
ViewEncapsulation determines whether the styles defined in a particular component will affect the entire application or not.
Angular supports 3 types of ViewEncapsulation:
1. **Emulated**  – Styles used in other HTML spread to the component
1. **Native** – Styles used in other HTML doesn’t spread to the component
1. **None** – Styles defined in a component are visible to all components of the application

**[⬆ Back to Top](#table-of-contents)**


###  1. What is Modules?
A module is a place where we can group components, directives, services, and pipes.
module is defined with a @NgModule decorator.

By default, modules are of two types:
* Root Module
* Feature Module

Every application can have only one root module whereas, it can have one or more feature modules.
A root module imports BrowserModule, whereas a feature module imports CommonModule.

**[⬆ Back to Top](#table-of-contents)**


###  1. What is  data binding??
Data binding is a concept in Angular and allows to define communication between a component and the DOM.
There are four forms of data binding

1. **From the Component to the DOM:**
       **Interpolation:** {{ value }}: Adds the value of a property from the component
        ```html
        <li>Name: {{ user.name }}</li>
        <li>Address: {{ user.address }}</li>
        ```
        **Property binding:** [property]=”value”: The value is passed from the component to the specified property or simple HTML attribute
        ```html
        <input type="email" [value]="user.email">
        ```
    2. **From the DOM to the Component:**
        **Event binding: (event)=”function”:** When a specific DOM event happens (eg.: click, change, keyup), call the specified method in the component
        ```html
        <button (click)="logout()"></button>
        ```
    3. **Two-way binding:**
        **Two-way data binding:** [(ngModel)]=”value”: Two-way data binding allows to have the data flow both ways. For example, in the below code snippet, both the email DOM            input and component email property are in sync
        ```html
        <input type="email" [(ngModel)]="user.email">

        ```

