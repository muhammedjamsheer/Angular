### Angular Data Binding
The data binding in Angular can be broadly classified into two groups. One way binding or two-way binding

#### One way binding
In one way binding data flows from one direction. Either from view to component or from component to view.

### Interpolation
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
 
 ### Property Binding in Angular
 Property binding-Data flows from the component to a property of an element in the DOM.  
 You can set the properties such as class, href, src, textContent, etc using property binding.   
 You can also use it to set the properties of custom components or directives (properties decorated with @Input).      
 We use brackets for property binding.
 
 __Property Binding Syntax__
  ```html
[binding-target]=”binding-source”
 ```
  __Property Binding Example__
  ```javascript
  
 //Template
<h1 [innerText]="title"></h1>
<h2>Example 1</h2>
<button [disabled]="isDisabled">I am disabled</button>

//Component
export class AppComponent {
  title="Angular Property Binding Example"
  isDisabled= true;
}
 ```
   __Class binding__
   
   1.Class binding with ClassName.              
   The ClassName is the property name of HTML Element. Hence we can make use of Property binding to assign the class name to any HTML element.
   
 ```html
    //The following example assigns CSS Class red to the div element.
    <div [className]="'red'">Test</div>
    
    //You can also add more than one class by separating them using the
    <div [className]="'red size20'">Test</div>
    
    //mixing both class and [className] results in removal of class attribute. You cannot use both.
    <div class="red" [className]="'size20'">red</div>

  ```
 Conditionally apply Classes
 ```javascript
  
 //Template
<div [className]="cssStringVar">Test</div>
<div [className]="getClass()">getClass</div>

//The following example uses the Conditional (Ternary) Operator.
<div [className]="hasError() ? 'red' : 'size20'"> conditonal operator </div>

//Component
export class AppComponent {
  cssStringVar: string= 'red size20';
  getClass() {
    return 'red';
  }
  hasError(){
    return true
  }
}
 ```
 
 2.Class binding with Class
  ```html
   <div [class.<className>]="condition"></div>
 ```
className is name of the class, which you want to bind to.
condition must return true or false. A return value of true adds the class and a false removes the class.

 ```javascript
 //Template
<div [class.red]="hasError" [class.size20]="hasError">Test</div>
<div [class.red]="hasError()" [class.size20]="hasError()">Test</div>

//The following example uses the Conditional (Ternary) Operator.
<div [className]="hasError() ? 'red' : 'size20'"> conditonal operator </div>

//Component
export class AppComponent {
 hasError:false;
 hasError(){
    return true
 }
}
 ```
 
   __Style binding__
 ```html
 [style.style-property] = "style-value"
 <p [style.color]="'red'">Give me red</p>

 //Setting the background color of a paragraph
 <p [style.background-color]="'grey'">some paragraph with grey background</p>

//Setting the border style of a button.
<button [style.border]="'5px solid yellow'">Save</button>

//Setting the units
<button [style.fontSize.px]="'20'" >Big Button</button>

//Setting Multiple styles
<p [style.color]="getColor()" 
   [style.font-size.px]="'20'"      
   [style.background-color]="status=='error' ? 'red': 'blue'">
   paragraph with multiple styles
</p>

//Conditionally setting the styles

<button [style.color]="status=='error' ? 'red': 'blue'">Button 1</button> 
<button [style.color]="getColor()">Button 2</button> 

export class AppComponent {
 status:string='error';
 getColor() {
  return 'yellow';
 }
}
 ```
 
 ### Event Binding
 Data flows from the DOM to the component.When a DOM event occurs such as click etc.
 
 ```html
<button (click)="onSave()">Save</button>

Instead of parentheses, you can also use the on- syntax as shown below
<button on-click="clickMe()">Click Me</button>

Multiple event handlers
<button (click)="clickMe() ; clickCount1=clickCount">Click Me</button>

DOM Events carries the event payload. I.e the information about the event.
We can access the event payload by using $event as an argument to the handler function.
<input (input)="handleInput($event)">

We can also make use of the template reference variable to pass the value instead of $event.
<input #el (input)="handleInput1(el)">

export class AppComponent {
 value="";
 val="";
 handleInput(event) {
   this.value = (event.target as HTMLInputElement).value;
 }
 handleInput1(element) {
   this.val=element.value;
 }
}

```



 
   
