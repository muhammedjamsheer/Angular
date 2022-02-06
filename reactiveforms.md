### Reactive Forms
Reactive forms are forms where we define the structure of the form in the component class. I,e we create the form model with Form Groups, Form Controls, and Form Arrays. We also define the validation rules in the component class. Then, we bind it to the HTML form in the template. This is different from the template-driven forms, where we define the logic and controls in the HTML template.  To build reactive forms, first, we need to import ReactiveFormsModule



#### FormBuilder
The FormBuilder is the helper API to build forms in Angular.  It provides shortcuts to create the instance of the FormControl, FormGroup or FormArray. It reduces the code required to write the complex forms.
To use the FormBuilder, first, we need to import it in our component.Next, we need to inject it into our component class.

 ```javascript
import { FormBuilder } from '@angular/forms'
constructor(private formBuilder: FormBuilder) {}
 ```

