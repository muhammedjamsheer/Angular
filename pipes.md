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

__1. Date Pipe__

Date Pipe Example
```javascript 
<p> Unformatted date : {{toDate }} </p>
<p> Formatted date : {{toDate | date}} </p>
// output   Feb 26, 2022

export class AppComponent 
{  
    toDate: Date = new Date(); 
}
```

Date Expression
The Date Expression can be anything that evaluates to date. For example it can be a Date object, a number (milliseconds since UTC epoch), or an ISO string

```javascript 
<h3>Date Expression </h3>
<p>Date Object : {{toDate | date}} </p>       //May 24, 2020
<p>Number Date : {{numDate | date}} </p>      //May 24, 2020
<p>ISO Date : {{strDate | date}} </p>         //May 24, 2020
 
export class AppComponent 
{  
  toDate: Date = new Date();
  numDate=1590319189931;
  strDate="Sun May 24 2020 19:16:23";
}
```

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

![Screenshot (511)](https://user-images.githubusercontent.com/29747486/155829202-a2089d70-fb64-4562-ba33-200242f8c18f.png)



