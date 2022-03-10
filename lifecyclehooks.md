Angular lifecycle hooks
----------------------
1.ngOnChanges
2.ngOnInit
3.ngDoCheck
4.ngAfterContentInit
5.ngAfterContentChecked
6.ngAfterViewInit
7.ngAfterViewChecked
8.ngOnDestroy

https://www.stackchief.com/blog/ngOnChanges%20Example%20%7C%20Angular

### 1.ngOnChanges
The Angular invokes ngOnChanges life cycle hook whenever any data-bound input property of the component or directive changes.                  
This method receives a SimpeChanges object, which contains the current and previous property values.    
Remember that only changes from the parent component will trigger the ngOnChanges() function.             
Also, remember that changes from the parent still update the child value even without implementing ngOnChanges.            
The ngOnChanges adds the benefit of tracking those changes with the previous and current value

parentComponent.ts
```javascript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-parent',
  template: `
    <a (click)="changeFromParent()">Change from parent</a>
    <br/>
    <app-child [parentData]=data></app-child>
  `
})
export class ParentComponent implements OnInit {
  data = 0
  constructor() {
  }

  ngOnInit() {
  }

  changeFromParent(){
    this.data += 1;
  }
}
```
childComponent.ts
```javascript
import { Component, OnInit, Input, SimpleChanges } from '@angular/core';

@Component({
  selector: 'app-child',
  template: `
    <a (click)="changeFromChild()">Change from child</a>
    <br/>
    {{parentData}}
  `	
})
export class ChildComponent implements OnInit {
  @Input() parentData: any;
  constructor() {
  }

  ngOnInit() {
  }

  changeFromChild(){
    this.parentData -= 1;
  }

  ngOnChanges(changes: SimpleChanges) {
    console.log(changes)
  }
}
```

### ngOnInit
The ngOnInit or OnInit hook is called when the component is created for the first time.       
This hook is fired only once and This hook is called after the constructor and first ngOnChanges hook is fired.             
This hook is fired before any of the child directive properties are initialized.            
This is a perfect place where you want to add any initialization logic for your component.              

```javascript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})

export class HomeComponent implements OnInit {
  constructor() { }
  ngOnInit() {
    console.log("component has been initialized!")
  }
}
```

### ngDoCheck
OnChanges triggered every time when the Angular detected a change to the data-bound input property.    
OnChanges does not fire when the input property is an array/object because Angular uses dirty checking to compare the properties.
In such a scenario, where Angular fails to detect the changes to the input property, the DoCheck allows us to implement our custom change detection.

ngDoCheck() is called whenever change detection is run.
ngDoCheck() is called immediately after ngOnChanges() and ngOnInit()

parentComponent.ts
```javascript
import { Component, OnInit } from "@angular/core";
export class customerData {
  name: string;
  address: string;
}
@Component({
  selector: 'app-parent',
  templateUrl: './parent.component.html',
  styleUrls: ['./parent.component.scss']
})

export class ParentComponent implements OnInit {
  customerDetails: customerData = new customerData();
  constructor() { }
  ngOnInit(): void {
    this.customerDetails.name = "Jamsheer";
    this.customerDetails.address = "Pattambi";
  }
  changeDetails() {
    // this.customerDetails = new customerData();
    this.customerDetails.name = "thafseer";
    this.customerDetails.address = "Kannur";
  }
}
```
parentComponent.html
```html
<button class="btn btn-danger" (click)="changeDetails()">Click</button>
<app-child [customerData]="customerDetails"></app-child>
```

childComponent.ts
```javascript
import { Component, OnInit, Input, SimpleChanges } from '@angular/core';
@Component({
  selector: 'app-child',
  templateUrl: './child.component.html',
  styleUrls: ['./child.component.scss'],

})
export class ChildComponent implements OnInit {
  @Input() customerData: any;
  name:string;
  address:string;
  constructor() { }

  ngOnInit(): void { }

  ngOnChanges(changes: SimpleChanges) {
    this.name=this.customerData.name;
    this.address=this.customerData.address;
  }
  ngDoCheck() {
    this.name=this.customerData.name;
    this.address=this.customerData.address;
  }
}
```
childComponent.html
```html
<p>Customer Name : {{name}}</p>
<p>Customer Address : {{address}}</p>
```

