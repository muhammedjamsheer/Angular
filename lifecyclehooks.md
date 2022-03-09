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
