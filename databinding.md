### Angular Data Binding
The data binding in Angular can be broadly classified into two groups. One way binding or two-way binding

#### One way binding
In one way binding data flows from one direction. Either from view to component or from component to view.

#### Interpolation
Data flows from the component to the DOM.We use curly braces for interpolation.
__Interpolation syntax__
{{ templateExpression }}

__Interpolation Example__
 ```javascript
 import { Component } from '@angular/core';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Angular Interpolation Example';
}
 ```
 
 ```html
{{title}}
  ```
