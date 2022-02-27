
### Directives
The Angular directive helps us to manipulate the DOM. You can change the appearance, behavior, or layout of a DOM element using the directives. They help you to extend HTML.
The Angular directives are classified into three categories based on how they behave. They are Component, Structural and Attribute Directives.

#### 2.Structural Directive
Structural directives can change the DOM layout by adding and removing DOM elements. All structural Directives are preceded by Asterix symbol.    
Commonly used structural directives are ngIf ,ngFor,ngSwitch.               

__ngIf__    
The NgIf directive is used when you want to display or remove an element based on a condition.

ngIf Syntax
``` html
<p *ngIf="condition">  
    condition is true and ngIf is true.  
</p>  
<p *ngIf="!condition">  
    condition is false and ngIf is false.  
</p>  
````
The *ngIf directive  with  "else" block   
``` html
<div *ngIf="condition; else elseBlock">  
   Content to render when condition is true.  
</div>  
<ng-template #elseBlock>  
    Content to render when condition is false.  
</ng-template>   
````

The *ngIf directive  with  "then" and "else" block
``` html
<ng-container
  *ngIf="isLoggedIn; then loggedIn; else loggedOut">
</ng-container>

<ng-template #loggedIn>
  <div>
    Welcome back, friend.
  </div>
</ng-template>
<ng-template #loggedOut>
  <div>
    Please friend, login.
  </div>
</ng-template> 
````

