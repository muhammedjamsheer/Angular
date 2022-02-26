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
<p> Unformatted date : {{toDate }} </p>       // output   Sat Feb 26 2022 09:53:41 GMT+0530 (India Standard Time)
<p> Formatted date : {{toDate | date}} </p>   // output   Feb 26, 2022

export class AppComponent 
{  
    toDate: Date = new Date(); 
}
```

Date Expression.          
The Date Expression can be anything that evaluates to date. For example it can be a Date object, a number (milliseconds since UTC epoch), or an ISO string

```javascript 
<h3>Date Expression </h3>
<p>Date Object : {{toDate | date}} </p>       //  May 24, 2020
<p>Number Date : {{numDate | date}} </p>      //  May 24, 2020
<p>ISO Date : {{strDate | date}} </p>         //  May 24, 2020
 
export class AppComponent 
{  
  toDate: Date = new Date();
  numDate=1590319189931;
  strDate="Sun May 24 2020 19:16:23";
}
```

Parameters to Date Pipe
------------------------
__1.Pre defined Format__
```html 
<p>{{toDate | date :"short"}} </p>       //  11/5/21, 11:41 AM
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

__2.Custom Format string__

```html 
<p>{{toDate | date:'dd/MM/y'}}           </p>       //   24/05/2020
<p>{{toDate | date:'dd/MM/yy HH:mm'}}    </p>       //   May 24, 2020, 7:17:26 PM
```
![Screenshot (511)](https://user-images.githubusercontent.com/29747486/155829202-a2089d70-fb64-4562-ba33-200242f8c18f.png)

__2.UpperCasePipe & LowerCasePipe &TitleCasePipe__  
these pipes transform the string to Uppercase or lowercase or titlecase
```javascript 
<p>{{msg | uppercase}} </p>  // WELCOME TO ANGULAR
<p>{{msg | lowercase}} </p>` // welcome to angular
<p>{{message | titlecase}} </p>` // welcome to angular
export class AppComponent 
{  
  msg: string= 'Welcome to Angular';
  message:string="welcome to angular"
}
```
__3.SlicePipe__          
Slice Pipe is used to slice some part of array or string.
```html 
array_or_string_expression | slice:start[:end]

start is the start position/index from where the slicing will start
end is the ending index/position in the array/string
````

```javascript 
<p>{{msg | slice:11:20}} </p>   //  Angular
<p>{{msg | slice:-10}} </p>    //  to Angular
export class AppComponent 
{  
    msg: string= 'Welcome to Angular ';
}
```
__4.Currency Pipe__        
It Transforms a number to the currency string
```javascript 
<p>{{amount | currency}}</p>                           //   $150.00
<p>{{amount | currency:'INR'}}</p>                     //   ₹150.00
<p>{{amount | currency:'INR':'code'}}</p>              //   INR150.00
<p>{{amount | currency:'INR':'Indian Rupee'}}</p>      //   Indian Rupee150.00

 display a number as two decimal rounded currency
 -----------------------------------------------
<div>{{price | currency:'USD':true:'1.2-2'}}</div>      //   $20.00
<div>{{price2 | currency:'USD':true:'1.2-2'}}</div>     //   $10.11
 
export class AppComponent 
{  
  amount:number=150;
  price:number = 20;
  price2:number=10.111
}
```
https://www.angularjswiki.com/angular/angular-currency-pipe-formatting-currency-in-angular/

__5.Decimal Pipe__   
It Transforms a number into a decimal point string
```javascript 
 <p>{{ decimal_value | number }}</p>     //   55.153
 by default it works as  3 fraction digits after decimal point.

 <p>{{ decimal_value | number:'3.4-5' }}</p>     //   055.15335
 In the above code we are instructing decimal pipe to show atleast 3 integer values before decimal points and minimum 1 fraction digit, maximum 5 fraction digits.

export class AppComponent 
{  
  decimal_value=55.15334533
}
```






