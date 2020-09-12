### Table of Contents

| No. | Questions |
|---- | ---------
|1 | [What is Angular Framework?](#what-is-angular-framework)|
|2 | [Why we use angular?](#Why-we-use-angular)|
|3 | [What is Angular Component?](#What-is-Angular-Component)|
|4 | [What are lifecycle hooks available?](#What-are-lifecycle-hooks-available)|
|5 | [What is the difference between constructor and ngOnInit?](#what-is-the-difference-between-constructor-and-ngoninit)|
|6 | [What is Modules?](#What-is-Modules)|
|7 | [What is a template?](#What-is-Modules)|
|8 | [What is ViewEncapsulation?](#What-is-ViewEncapsulation)|
|9 | [What is  data binding?](#What-is-ViewEncapsulation)|
|10 | [What is  one way and two way data binding?](#What-is-ViewEncapsulation)|
|11 | [What is  Directives?](#What-is-ViewEncapsulation)|
|12 | [What are different types of compilation in Angular?](#What-is-ViewEncapsulation)|
|13 | [What is a service?](#What-is-ViewEncapsulation)|
|14 | [What is pipes?](#What-is-ViewEncapsulation)|
|15 | [What is metadata?](#What-is-ViewEncapsulation)|
|16 | [What is the Difference between Promise and Observable in Angular.?](#What-is-ViewEncapsulation)|
|16 | [What is RxJS.?](#What-is-ViewEncapsulation)|





###  1. What is Angular Framework?
Angular is basically is an open-source,client-side typescript-based  framework  for developing web applications.
Angular is one of the best frameworks for developing any Single Page Application

**[⬆ Back to Top](#table-of-contents)**


### 2.  Why we use angular?
1. Angular is supported by google ,thus making the platform user-friendly
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


###  1. What is  data binding?
Data binding is a concept in Angular and allows to define communication between a component and the DOM.
There are four forms of data binding

1.**From the Component to the DOM:**

**Interpolation:** {{ value }}: String interpolation uses the double curly braces {{ }} to display data from the component
```html
<li>Name: {{ user.name }}</li>
<li>Address: {{ user.address }}</li>
```
**Property binding:** [property]=”value”: Property binding uses the square brackets [ ] syntax. In Property binding we can bind data from component class to the the DOM properties of an HTML element.
```html
<input type="email" [value]="user.email">
```
2.**From the DOM to the Component:**\
**Event binding: (event)=”function”:** Event Binding is works with the DOM event activities of the UI elements like click-event, blur-event 
```html
<button (click)="logout()"></button>
```
3.**Two-way binding:**\
   [(ngModel)]=”value”: Two-way data binding allows to have the data flow both ways. For example, in the below code snippet, both the email DOM input and component email property are in sync
```html
<input type="email" [(ngModel)]="user.email">
```

**[⬆ Back to Top](#table-of-contents)**

###  1. What is  one way and two way data binding?
In one-way binding, any changes in the component class will directly reflect inside the HTML template but, vice-versa is not possible. Whereas, it is possible in two-way binding

**[⬆ Back to Top](#table-of-contents)**

###  1. What is  directives?
A directive is a class in Angular that is declared with a @Directive decorator.\

**[⬆ Back to Top](#table-of-contents)**

###  1. What is  templates?
A template is a HTML view where you can display data by binding controls to properties of an Angular component.

**[⬆ Back to Top](#table-of-contents)**

###### When to use a directive?
Consider an application, where multiple components need to have similar functionalities. The norm thing to do is by adding this functionality individually to every component but, this task is tedious to perform. In such a situation, one can create a directive having the required functionality and then, import the directive to components which require this functionality.

There are three types of directives
1. **Structural directives** 
These directives change the DOM layout by adding and removing DOM elements.\
Every structural directive has a ‘ * ’ sign before them.\
Examples are *ngIf ,*ngFor ,*ngSwitch

1. **Attribute directives** 
These directives change the appearance or behavior of an element, component, or another directive.\
Examples are *ngClass ,*ngStye 

1. **Attribute directives** 
These are directives with a template.

**[⬆ Back to Top](#table-of-contents)**

### 1. What are different types of compilation in Angular?
Every Angular application consists of components and templates which the browser cannot understand. Therefore, all the Angular applications need to be compiled first before running inside the browser. For example, In AOT compilation, both Angular HTML and TypeScript code converted into efficient JavaScript code during the build phase before browser runs it.

Angular provides two types of compilation:**JIT(Just-in-Time) compilation** and **AOT(Ahead-of-Time) compilation**

1.**JIT(Just-in-Time) compilation**  is a type of compilation that compiles your app in the browser at runtime It is the default way used by Angular.\
 The commands used for JIT compilation are –ng build ng serve

2.**AOT(Ahead-of-Time) compilation** is a type of compilation that compiles your app at build time\
The CLI command for aot compilation is -ng build --aot ng server –aot

**AOT** is more suitable for the production environment whereas **JIT** is much suited for local development.

###### Which One Is Better out of AOT and JIT?
Answer: AOT reduces the load and bootstrap time of the application. The pages also load faster. Any errors are also shown during the time of application build itself. Hence, AOT is a better option

**[⬆ Back to Top](#table-of-contents)**

###  1. What is  service?
A service is used when a common functionality needs to be provided to various modules.\
The main objective of a service is to share data, functions with different components of an Angular application.\
A service is defined using a @Injectable decorator. A function defined inside a service can be invoked from any component or directive.

**[⬆ Back to Top](#table-of-contents)**


###  1. What is  pipes?
**Pipes** - The pipes are used to transform data into desired format
```html
{{ birthday | date }}
```
**Parameterized pipe** - The parameterized pipe can be created by declaring the pipe name with a colon ( : ) and then the parameter value.
```html
{{ birthday | date:'dd/MM/yyyy'}}
```

**Custom pipe** - Apart from built-inn pipes, we can write we own custom pipe.\
  A pipe is a class decorated with pipe metadata @Pipe decorator, which you import from the core Angular library For example,
```html
{{ birthday | date:'dd/MM/yyyy'}}
```

**Async pipe** - The AsyncPipe subscribes to an observable or promise and returns the latest value it has emitted.
```html
{{ time | async }}
```

**[⬆ Back to Top](#table-of-contents)**

###  1. What is  Metadata?
Metadata is used to decorate a class so that it can configure the expected behavior of the class.\

###  1.What is the Difference between Promise and Observable in Angular.?

Promise can handle a single response for the same request\
Observable can handle multiple responses for the same request.

Promise is not cancellable in nature\
Observable can be cancelled by using the unsubscribe() method.  

Promise is not lazy and is executed immediately after creation.\
Observable is lazy in nature and does not return any value until we subscribe using the subscribe() method.

###  1.What is RxJS.?
RxJS is Reactive Extensions for Javascript. It is a library that allows us to work with observables in an Angular application.
