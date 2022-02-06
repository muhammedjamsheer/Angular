### Reactive Forms
Reactive forms are forms where we define the structure of the form in the component class. I,e we create the form model with Form Groups, Form Controls, and Form Arrays. We also define the validation rules in the component class. Then, we bind it to the HTML form in the template. This is different from the template-driven forms, where we define the logic and controls in the HTML template.  To build reactive forms, first, we need to import ReactiveFormsModule



#### FormBuilder
The FormBuilder is the helper API to build forms in Angular.  It provides shortcuts to create the instance of the FormControl, FormGroup or FormArray. It reduces the code required to write the complex forms.
To use the FormBuilder, first, we need to import it in our component.Next, we need to inject it into our component class.

 ```javascript
import { FormBuilder } from '@angular/forms'
constructor(private formBuilder: FormBuilder) {}
 ```
 
 #### FormGroup
 We use the group method to build the Form Group. We pass the list of Form Controls, Form Array, or another Form Group to the group method as key-value pair. Where the key is the name of the FormControl, FormGroup or FormArray. The value is the configuration of the control.   

A FormControl takes 3 arguments. a default value, a validator and an asynchronous validator. All of them are optional.
 
  The FormGroup is created with the following syntax
 ```javascript
import { FormBuilder, FormGroup, Validators } from '@angular/forms';
contactForm: FormGroup;
 ```
 
  ```javascript
this.contactForm = this.formBuilder.group({
  firstname: [''],
  lastname: ['']
});
 ```
 

 #### Binding the template to the model
 This is done using the formGroup directive as shown below.              
 Next, we need to bind form fields to the FormControl models. We use the FormControlName directive for this.           
 We submit the form data to the component using the Angular directive named ngSubmit            
  ```html
  <form [formGroup]="contactForm" (ngSubmit)="onSubmit()">
  <input type="text" id="firstname" name="firstname" formControlName="firstname">
  <input type="text" id="lastname" name="lastname" formControlName="lastname">
</form>
  ```
  
  #### Receive the data in the Component class
```javascript
onSubmit() {
  console.log(this.contactForm.value);
}  
```
#### Default Value
 
 ```javascript
this.contactForm = this.formBuilder.group({
  firstname: ['muhammed'],
  lastname: ['jamsheer']
});
```

#### Nested FormGroup
 ```javascript

this.contactForm = this.formBuilder.group({
  firstname: [''],
  lastname: [''],
  address: this.formBuilder.group({
    city: [''],
    street: [''],
    pincode: ['']
  })
})
```
 
 
