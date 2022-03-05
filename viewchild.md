### Understanding ViewChild, ViewChildren & Querylist in Angular
The ViewChild or ViewChildren decorators are used to Query and get the reference of the DOM element in the Component.                 
ViewChild returns the first matching element and ViewChildren returns all the matching elements as a QueryList of items.             
We can use these references to manipulate element properties in the component.
 we can use the ngAfterViewInit to access the  variable.
### ViewChild

 The decorator takes the following meta information:
 selector - the selector of the element to query. This can be a directive type or a name.
 read - read a different token from the queried elements.
 static - This is new in Angular 8 and indicates whether or not to resolve query results before change detection runs.
 
 
 #### Using Static Option in ViewChild
 The static option determines the timing of the ViewChild query resolution.          
 The static option in ViewChild is used to resolve query results before change detection runs and also after change detection runs.           
 To resolve query results before the change detection runs, you need to set static option value as true.            
 To resolve query results after the change detection runs, you need to set static option value as false. The default value of static option is false.            
 The value of the static becomes important when the child is rendered dynamically. For Example inside a ngIf or ngSwitch etc.              
 
 #### 1.Injecting Component
 ```Javascript
 import { Component, ViewChild, AfterViewInit } from '@angular/core';

import { HelloComponent } from './hello.component';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent implements AfterViewInit {
  name = 'Angular';
  @ViewChild(HelloComponent, {static: false}) hello: HelloComponent;

  ngAfterViewInit() {
    console.log('Hello ', this.hello.name); 
  }
}
 ```
 

 #### 2.Injecting HTML Element Using ElementRef 
The Viewchild can also be used to query HTML elements.
First, assign a Template variable (#para in the example below) to the HTML element. You can then use the ViewChild to query the element.
 ```Javascript
 template
 --------
<p #para>Some text</p>
<button type="button" class="btn btn-primary" #myButton>My Button</button> 
 
 component
 --------
 import { Component, OnInit ,ElementRef, ViewChild} from '@angular/core';
@Component({
  selector: 'app-viewchild',
  templateUrl: './viewchild.component.html',
  styleUrls: ['./viewchild.component.scss']
})
export class ViewchildComponent implements OnInit {
  @ViewChild('para',{static:false}) para: ElementRef;
  @ViewChild("myButton") myValue:ElementRef; 
  constructor() { }

  ngOnInit(): void {
  }
  ngAfterViewInit() {
    console.log(this.para.nativeElement.innerHTML);
    this.para.nativeElement.innerHTML="new text";
    console.log(this.myValue);  
  }
}
 ```
 
 ### ViewChildren         
ViewChildren is another property decorator which is used to query the DOM for multiple elements and return a QueryList.      
 
  #### 1.Injecting Component
 ```Javascript
 template
 --------
 <app-child name="Angular 6"></app-child>
 <app-child name="Angular 7"></app-child>
 <app-child name="Angular 8"></app-child>

component
---------
import { Component, OnInit, ViewChildren, QueryList } from '@angular/core';
import { ChildComponent } from '../child/child.component';

@Component({
  selector: 'app-parent',
  templateUrl: './parent.component.html',
  styleUrls: ['./parent.component.scss']
})
export class ParentComponent implements OnInit {
  @ViewChildren(ChildComponent) child: QueryList<any>;
  constructor() { }
  ngOnInit(): void {}

  ngAfterViewInit() {
    this.child.forEach(child => console.log(child));
  }
}
```

 #### 2.Injecting HTML Element Using ElementRef 
 ```Javascript
 template
 --------
<ul *ngFor="let category of categories;let i = index" #myItemLists>
    <li (click)="getCategory($event, category, i)">{{ category.value }}</li>
</ul>
{{name}}

component
---------


import { Component, OnInit, VERSION, ViewChildren, QueryList } from "@angular/core";

@Component({
  selector: 'app-parent',
  templateUrl: './parent.component.html',
  styleUrls: ['./parent.component.scss']
})
export class ParentComponent implements OnInit {
  name = "Angular " + VERSION.major;
  categories: any[] = [];
  @ViewChildren('myItemLists') items: QueryList<any>;
  constructor() { }

  ngOnInit(): void {
    this.categories = [
      {
        value: "Angular 8",
      }, {
        value: "Angular 9",
      }, {
        value: "Angular 10",
      }
    ];
  }
  getCategory(event:any, category:any, i:any) {
    console.log('category clicked : ', category);
    console.log('event : ', event);
    console.log('index of category : ', i);
    console.log('all items : ', this.items)
  }
}
```
 
 
