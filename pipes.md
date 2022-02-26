#### Angular Pipes
Pipes are simple functions designed to accept an input value and return a transformed value as the output.     
Angular Pipes are the class with @Pipe decorator.
```html
 {{ input| pipeName : param1: param2: ...}}
```

Pipes Example
```javascript 
<p> Unformatted date : {{toDate }} </p>
<p> Formatted date : {{toDate | date}} </p>

export class AppComponent 
{  
    toDate: Date = new Date(); 
}
```

Passing arguments to pipes
We can also pass optional arguments to the pipe. The arguments are added to the pipe using a colon (:) sign followed by the value of the argument.     
If there are multiple arguments separate each of them with the colon (:)
```html 
{{toDate | date:'medium'}}
```

Chaining Pipes
Pipes can be chained together to make use of multiple pipes in one expression
```html 
{{toDate | date | uppercase}}
```
