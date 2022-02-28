1.Parent to Child Cammunication
----------------------------------
If the Components have a parent-child relationship,then we can pass the data from the parent component to the child using the @input Property.                
In parent component we are using property binding. here we bind the transfering data .Whenever the value in the parent component changes angular updates the value in the child component.                  
In the child component, we are using __@Input decorator__ to capture data coming from a parent component

```javscript
parent.component.html
-----------------------
 <app-child [studentname]="studentname" [actors]="myFavoriteActors"></app-child>

parent.component.ts
----------------------
export class ParentComponent implements OnInit {
  studentname: string = "muhammed jamsheer";
  myFavoriteActors = ['Mammootty', 'Mohan Lal',"FahaD Fasil"];
}

child.component.html
--------------------
<p>Student name:{{studentname}}</p>
<h6>Favorite Actors</h6>
<ul>
    <li *ngFor="let actor of actors">{{actor}}</li>
</ul>

child.component.ts
-----------------
import { Component, OnInit,Input } from '@angular/core';

export class ChildComponent implements OnInit {
  @Input() studentname:string;
  @Input() actors: Array<string> = [];

}
```

__Aliasing input Property__              
You can Alias the input property and use the aliased name the parent component as shown below

```javscript
parent.component.html
-----------------------
 <app-child [student]="studentname"></app-child>

parent.component.ts
----------------------
export class ParentComponent implements OnInit {
  studentname: string = "muhammed jamsheer";
}

child.component.ts
-----------------
import { Component, OnInit,Input } from '@angular/core';

export class ChildComponent implements OnInit {
  @Input('student') studentfirstname: string;
}

child.component.html
--------------------
<p>Student name:{{studentfirstname}}</p>
```

__Detecting the Input changes__   

ngOnChanges is a lifecycle hook, which angular fires when it detects changes to data-bound input property. 
This method receives a SimpeChanges object, which contains the current and previous property values.
We can Intercept input property changes in the child component using this hook.


```javscript
parent.component.html
-----------------------

<button class="btn btn-danger" (click)="Increment()">Increment</button>
<app-child [MyCount]="counts"></app-child>
<button class="btn btn-danger" (click)="Decrement()">Decrement</button>

parent.component.ts
----------------------
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-parent',
  templateUrl: './parent.component.html',
  styleUrls: ['./parent.component.scss']
})
export class ParentComponent implements OnInit {
  counts: number = 5;
  constructor() { }
  ngOnInit(): void {}
  
  Increment() {
    this.counts++;
  }
  Decrement() {
    this.counts--;
  }
}


child.component.ts
-----------------
import { Component, Input,OnInit, OnChanges, SimpleChanges, SimpleChange  } from '@angular/core';

@Component({
  selector: 'app-child',
  templateUrl: './child.component.html',
  styleUrls: ['./child.component.scss']
})
export class ChildComponent implements OnInit {

  @Input('MyCount') count: number;

  constructor() { }

  ngOnInit(): void {}

  ngOnChanges(changes: SimpleChanges) {
 
    for (let property in changes) {
        if (property === 'count') {
          console.log('Previous:', changes[property].previousValue);
          console.log('Current:', changes[property].currentValue);
          console.log('firstChange:', changes[property].firstChange);
        } 
    }
  }
}


child.component.html
--------------------
<p> current count is {{ count }}</p>
```



 
