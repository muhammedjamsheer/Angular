
### Directives
The Angular directive helps us to manipulate the DOM. You can change the appearance, behavior, or layout of a DOM element using the directives. They help you to extend HTML.
The Angular directives are classified into three categories based on how they behave. They are Component, Structural and Attribute Directives.

#### 2.Structural Directive
Structural directives can change the DOM layout by adding and removing DOM elements. All structural Directives are preceded by Asterix symbol.    
Commonly used structural directives are ngIf ,ngFor,ngSwitch.               

__ngIf Directive__   
The NgIf directive is used when you want to display or remove an element based on a condition.
The expression must return a boolean value.        
If the expression is false then the element is removed, else the element is inserted        

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

__ngFor Directive__          
The ngFor is an Angular structural directive, which repeats a portion of the HTML template once per each item from an iterable list.     
```html
items = [1,2,3,4,5];

<div *ngFor="let item of items">
 <p >  {{item}} </p>
</div>

with indexes
------------
<div *ngFor="let item of items;let i=index">
 <p >  {{item}} {{i}} </p>
</div>

with even and odd indexes
-------------------------
<tr *ngFor="let hero of heroes; let even = even; let odd = odd" 
    [ngClass]="{ odd: odd, even: even }">
    <td>{{hero.name}}</td>
</tr>

Identifying the first and the last element of a list
---------------------------------------------------
<tr *ngFor="let hero of heroes; let first = first; let last = last" 
    [ngClass]="{ first: first, last: last }">
    <td>{{hero.name}}</td>
</tr>

```
__trackBy__            
Sometimes, ngFor performance is low with large lists. For example, when adding new item or remove any item in the list may trigger several DOM manipulations. To iterate over large objects collection, we use trackBy.

It is used to track when elements are added or removed. It is performed by trackBy method. It has two arguments index and element. Index is used to identity each element uniquely. Simple example is defined below.
```javascript
export class TestComponent { 
   studentArr: any[] = [ { 
      "id": 1, 
      "name": "student1" 
   }, 
   { 
      "id": 2,
      "name": "student2" 
   }, 
   { 
      "id": 3, "name": "student3"
   },
   { 
      "id": 4, 
      "name": "student4" 
   } 
   ]; 
   trackByData(index:number, studentArr:any): number { 
      return studentArr.id; 
   }
```
trackByData() method to access each student element in a unique way based on the id.
```html
<ul> 
   <li *ngFor="let std of studentArr; trackBy: trackByData">
      {{std.name}} 
   </li>
</ul>

```
__ngSwitch directive__    
The ngSwitch directive lets you add/remove HTML elements depending on a match expression.         
ngSwitch directive used along with ngSwitchCase and ngSwitchDefault.   

```javascript
<ul [ngSwitch]="logInName"> 
   <li *ngSwitchCase="'user'"> 
      <p>User is logged in..</p> 
   </li> 
   <li *ngSwitchCase="'admin'"> 
      <p>admin is logged in</p> 
   </li> 
   <li *ngSwitchDefault> 
      <p>Please choose login name</p> 
   </li> 
</ul>

export class TestComponent implements OnInit {  
   logInName = 'admin'; 
}

```

### Attribute Directive     
An Attribute or style directive can change the appearance or behavior of an element.
Commonly used Attribute directives are ngModel, ngClass ,ngStyle

__ngClass__           
The ngClass directive is used to add or remove the CSS classes from an HTML element. Using the ngClass we can create dynamic styles in HTML pages.   

```html
//single condition
<div [ngClass]="{'text-success':person.country === 'UK'}"></div>
<div [ngClass]="{'text-success': person.country === 'UK' && person.country === 'INDIA'}"></div>
<div [ngClass]="{ 'activeClass': condition,'inactiveClass': !condition, 'focusClass': condition && otherCondition}"> 

//multiple condition
<div [ngClass]="{'text-success':person.country === 'UK', 'text-danger':person.country === 'INDIA' }"></div>

//terenary
<div [ngClass]="val > 10 ? 'text-success' : 'text-danger'"></div>

//Method expression
<div [ngClass]="getSomeClass()"></div>
getSomeClass(){
   const isValid=this.property1 && this.property2;
   return {someClass1:isValid , someClass2:isValid};
 }
```

__ngStyle__         
ngStyle directive is used to add dynamic styles.
```html
//terenary
<div [ngStyle]="{'background-color':person.country === 'UK' ? 'green' : 'red' }"></<div>
<div [ngStyle]="styleOne?{'background-color': 'red'} : {'background-color': 'blue'}"></<div>
    
//Metod expression
<div [ngStyle]="{'color':getColor(country)}"></div>
    
  getColor(country) { 
    switch (country) {
      case 'UK':
        return 'green';
      case 'USA':
        return 'blue';
      case 'HK':
        return 'red';
    }
  }   
```


