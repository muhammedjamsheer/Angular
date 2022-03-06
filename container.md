### ng-container   
ng-container allows us to create a division or section in a template without introducing a new HTML element. 
The ng-container does not render in the DOM, but content inside it is rendered.
ng-container is not a directive, component, class, or interface, but just a syntax element.           

#### Uses of ng-container            
It is a very useful directive. Especially when working with structural directives like ngIf, ngFor, etc. 
#### 1.ng-Container with ngIf
For Example, to show a list of items when length graterthan zero.

```html
 items= [
   { name:'Angular', active:true},
   { name:'Typescript', active:true},
   { name:'FoxPro', active:false},
   { name:'Javascript', active:true},
   { name:'DBase', active:false}
 ]

<ng-container *ngIf="items.length>0">
  <ul>
   <li *ngFor="let item of items;">
     {{item.name}}
   </li>
  </ul>
</ng-container>
```

#### 2.ng-Container with ngFor
For Example, consider the following items. We want to display the items as a list, but only the active items.          
This requires two directives ngFor to loop through the items and ngIf to check if the items are active                 
```html
<ul>
 <ng-container *ngFor="let item of items;">
   <li *ngIf="item.active">
     {{item.name}}
   </li>
 </ng-container>
</ul>
```

#### 3.ng-Container with ngSwitch               
```html
<div [ngSwitch]="value">
 <ng-container *ngSwitchCase="0">Text one</ng-container>
 <ng-container *ngSwitchCase="1">Text two</ng-container>
</div>
```
