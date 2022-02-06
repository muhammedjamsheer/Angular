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
 
 ### Setting Value
 #### 1.Default Value
```javascript
this.contactForm = this.formBuilder.group({
  firstname: ['muhammed'],
  lastname: ['jamsheer']
});
```
 We use setValue or patchValue method of the FormGroup to set a new value for the entire FormGroup.
 #### 2.SetValue
 Sets the value of the FormGroup. It accepts an object that matches the structure of the group, with control names as keys.              
 The structure must match exactly, otherwise, it will result in an error.
 
 ```javascript
setValue() {
  this.contactForm.setValue({
    firstname: "Sachin",
    lastname: "Tendulakr",
    email: "sachin@gmail.com",
    address: {
      city: "19-A, Perry Cross Road, Bandra (West)",
      street: "Mumbai",
      pincode: "Maharatsra",
    }
  })
}

//You can also update the nested FormGroup separately,

setAddress() {
  this.reactiveForm.get("address").setValue({
      city: "19-A, Perry Cross Road, Bandra (West)",
      street: "Mumbai",
      pincode: "Maharatsra",
  })
}


//You can also update the single feild,

setFirstName() {
  this.reactiveForm.get("firstname").setValue('jamsheer');
}
```



 #### 3.PatchValue
 It will only update the matching objects and ignores the rest.
  ```javascript
patchValue() {
  this.contactForm.patchValue({
    firstname: "Sachin",
    address: {
      city: "19-A, Perry Cross Road, Bandra (West)",
    }
  })
 ```
 The difference is that with setValue we must include all the controls, while with the patchValue you can exclude some controls.
 
 
 ### Finding the Value
 
 
 #### 1.value
 The  the current value of FormControl.
 ```javascript

 // to get value of a  form control
 var firstname = this.contactForm.get("firstname").value
 
 //to get value of a form group
  var contactform =this.contactForm.value;

 ```
 
 #### 2.valueChanges
 The angular emits the valueChanges event whenever the value of the control changes. The value may change when the user updates the element in the UI or programmatically through the setValue/patchValue method. We can subscribe to it as shown below
```javascript
  // to get value of a formcontrol
  this.fNameChange = this.contactForm.get("firstname").valueChanges.subscribe(x => {
   console.log(x);
  })

  // to get value of a formgroup
  this.contactForm.get("address").valueChanges.subscribe(x => {
    console.log(x);
  })
  
   this.contactForm.valueChanges.subscribe(x => {
    console.log(x);
  })
 ```
 
 #### EmitEvent & ValueChanges
 
 The ValueChanges event is fired even when the values of the control are changed programmatically. In some circumstances, you might not want to raise the ValueChanges event. To do that we can use the emitEvent: false     
 
In the following example, the ValueChanges event is not fired at all, even though the value of the firstname is changed.
```javascript
this.reactiveForm.get("firstname").setValue("", { emitEvent: false }); 
```
 #### OnlySelf & ValueChanges
When onlySelf: true the changes will only affect only this FormControl and change is not bubbled up to its parent.   
Hence the ValueChanges event of the parent FormGroup does not fire.
```javascript
this.reactiveForm.get("firstname").setValue("", { onlySelf: true }); 
```
 
 ### Reset
 Resets the control. We can also pass the default value.
 
 ```javascript
this.contactForm.get("firstname").reset('');
this.contactForm.get("firstname").reset()('test');

to reset all feilds in a formgroup
this.contactForm.reset()
  ```
  
  ### Validation
  The validators can be added to FormControl, FormGroup or to the FormArray.
  
  #### 1.Built-in Validators
 ```javascript
 Required Validator
 -----------------
 The required validator returns true only if the formcontrol has a non-empty value entered.      
 The second argument of the FormControl takes the Sync Validator.
 
  this.contactForm = this.formBuilder.group({
  firstname: ['',[Validators.required]],  
 });
 
  Minlength Validator
  -------------------
  Minlength validator requires the control value must not have less number of characters than the value specified in the validator.
  
 this.contactForm = this.formBuilder.group({
  firstname: ['',[Validators.required,Validators.minLength(10)]],  
 }); 
 
 Maxlength Validator
 -------------------
This Validator requires that the number of characters must not exceed the value specified in the validator.
  
 this.contactForm = this.formBuilder.group({
  firstname: ['',[Validators.required,Validators.maxLength(10)]],  
 });
 
 Pattern Validator
 -----------------
This Validator requires that the control value must match the regex pattern provided in the attribute.
For example, the pattern ^[a-zA-Z]+$ ensures that the only letters are allowed (even spaces are not allowed).
  
 this.contactForm = this.formBuilder.group({
  firstname: ['',[Validators.maxLength(15), Validators.pattern("^[a-zA-Z]+$")],  
 });
 
 Email Validator
 ----------------
This Validator requires that the control value must be a valid email address.
  
 this.contactForm = this.formBuilder.group({
  firstname: ['',[Validators.maxLength(15), Validators.pattern("^[a-zA-Z]+$")],  
 });

```
#### Disable Submit button
```html
<button type="submit" [disabled]="!contactForm.valid">Submit</button>
 ```
 
 
  

 
