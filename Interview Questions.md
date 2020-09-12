### Table of Contents

| No. | Questions |
|---- | ---------
|1 | [What is Angular Framework?](#what-is-angular-framework)|
|2 | [Why we use angular?](#Why-we-use-angular)|
|3 | [What is Angular Component?](#What-is-Angular-Component)|
|3 | [What are lifecycle hooks available?](#What-are-lifecycle-hooks-available)|



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
    1. **ngOnChanges:** When the value of a data bound property changes, then this method is called.
    2. **ngOnInit:** This is called whenever the initialization of the directive/component after Angular first displays the data-bound properties happens.
    3. **ngDoCheck:** This is for the detection and to act on changes that Angular can't or won't detect on its own.
    4. **ngAfterContentInit:** This is called in response after Angular projects external content into the component's view.
    5. **ngAfterContentChecked:** This is called in response after Angular checks the content projected into the component.
    6. **ngAfterViewInit:** This is called in response after Angular initializes the component's views and child views.
    7. **ngAfterViewChecked:** This is called in response after Angular checks the component's views and child views.
    8. **ngOnDestroy:** This is the cleanup phase just before Angular destroys the directive/component.

**[⬆ Back to Top](#table-of-contents)**







