### Angular Pipes
Pipes are simple functions designed to accept an input value and return a transformed value as the output.     
Angular Pipes are the class with @Pipe decorator.
```html
 {{ input| pipeName : param1: param2: ...}}
```

__Pipes Example__    
```javascript 
<p> Unformatted date : {{toDate }} </p>
<p> Formatted date : {{toDate | date}} </p>

export class AppComponent 
{  
    toDate: Date = new Date(); 
}
```

__Passing arguments to pipes__     
We can also pass optional arguments to the pipe. The arguments are added to the pipe using a colon (:) sign followed by the value of the argument.     
If there are multiple arguments separate each of them with the colon (:)
```html 
{{toDate | date:'medium'}}
```

__Chaining Pipes__
Pipes can be chained together to make use of multiple pipes in one expression
```html 
{{toDate | date | uppercase}}
```

### The Angular Built-in pipes


| Option |   Result|
|----       |---------------|
|  short    |11/5/21, 11:41 AM     |
|  medium    |Nov 5, 2021, 11:41:16 AM     |
|  long    |  June 15, 2015 at 9:03:01 AM GMT+1    |
|  full    |  November 5, 2021 at 11:41:16 AM GMT+5    |
|  shortDate    |11/5/21     |
|  mediumDate    |Nov 5, 2021   |
|  longDate    |  November 5, 2021   |
|  fullDate    |  Friday, November 5, 2021    |
|  shortTime    |11:46 AM   |
|  mediumTime    |11:46:39 AM  |
|  longTime    |  11:47:07 AM GMT+5   |
|  fullTime    |  11:47:48 AM GMT+05:30    |



|Component	|format	| Example |
|Year|	y|	2016
|Year|	yy|	16
|Month|	M|	9
|Month|	M|	99
|Month|	MMM|	Nov
|Month|	MMMM|	November
|Day|	d|	9
|Day|	dd|	09
|hour|	j|	9
|hour|	jj|	09
|hour|	h|	9 AM
|hour	|hh|	09 AM
|hour24|	H|	13
|hour24|	HH|	13
|minute|	m|	9
|minute|	mm|	09
|second|	s|	9|
|second|	ss|	99
|Time| zone	z|	Pacific Standard time
|Time| zone	Z|	GMT-8:00
|Time| zone	a|	PM


