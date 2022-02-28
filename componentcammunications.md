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
 
