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
//Template
 {{title}}

//Component
export class AppComponent {
  title = 'Angular Interpolation Example';
}
 ```
 
 __Invoke a method in the component__
 ```javascript

//Template
{{getTitle()}}
 
//Component
export class AppComponent {
title = 'Angular Interpolation Example';
getTitle(): string {
     return this.title;
 }
}
 ```
 
  __Concatenate two string__
 ```html
<p>Welcome to {{title}}</p>
<p>{{ 'Hello & Welcome to '+ ' Angular Interpolation '}}</p>
<p>Welcome {{firstName}}, {{lastName}}</p>
<p>Welcome {{getFirstName()}}, {{getLastName()}}</p>
 ```

  __Perform some mathematical operations__
 ```javascript

//Template
<p>100x80 = {{100*80}}</p>
<p>Largest: {{max(100, 200)}}</p>
 
//Component
export class AppComponent {
max(first: number, second: number): number {
  return Math.max(first, second);
}
}
 ```
 
   __Bind to an element property__
 ```html
<p>Show me <span class = "{{giveMeRed}}">red</span></p>
<p style.color={{giveMeRed}}>This is red</p>

// Bind to an image source
<img src="{{itemImageUrl}}">

//href
<a href="/product/{{productID}}">{{productName}}</a>
 ```
 
   __Use a template reference variabley__
 ```html
 
<label>Enter Your Name</label>
<input (keyup)="0" #name>
<p>Welcome {{name.value}} </p
 ```
 
 
 
