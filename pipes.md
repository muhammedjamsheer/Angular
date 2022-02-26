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


Option	Equivalent to	Result
'short'	'M/d/yy, h:mm a'	11/5/21, 11:41 AM
'medium'	'MMM d, y, h:mm:ss a'	Nov 5, 2021, 11:41:16 AM
'long'	'MMMM d, y, h:mm:ss a z'	June 15, 2015 at 9:03:01 AM GMT+1
'full'	'EEEE, MMMM d, y, h:mm:ss a zzzz'	November 5, 2021 at 11:41:16 AM GMT+5
'shortDate'	'M/d/yy'	11/5/21
'mediumDate'	'MMM d, y'	Nov 5, 2021
'longDate'	'MMMM d, y'	November 5, 2021
'fullDate'	'EEEE, MMMM d, y'	Friday, November 5, 2021
'shortTime'	'h:mm a'	11:46 AM
'mediumTime'	'h:mm:ss a'	11:46:39 AM
'longTime'	'h:mm:ss a z'	11:47:07 AM GMT+5
'fullTime'	'h:mm:ss a zzzz'	11:47:48 AM GMT+05:30


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


