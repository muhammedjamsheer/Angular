
### ng-template
---------------
The ng-template is an Angular element, which contains the template.and The template does not render itself on DOM.
These template elements only work in the presence of structural directives.

#### Using ng-template with *ngIf
```html
  <div class="mt-3">
    <div class="userlog" *ngIf="userlogged else loading">
      {{username}}
    </div>

    <ng-template #loading>
      <div>Sign In</div>
    </ng-template>
  </div>
```

```html
  <ng-container *ngIf="isLoggedIn; then userloggedIn; else userloggedOut"></ng-container>
    <ng-template #userloggedIn>
      <div>Hello User </div>
    </ng-template>
    <ng-template #userloggedOut>
      <div> Please Login</div>
  </ng-template>
```

### ngTemplateOutlet
-------------------
The ngTemplateOutlet, is a structural directive, which renders the template.                      
To use this directive, first, we need to create the template and assign it to a template reference variable (sayHelloTemplate in the following template).  
```html
  <div class="mt-3">
    <ng-container *ngTemplateOutlet="sayHelloTemplate">
      This text is not displayed
    </ng-container>

    <ng-template #sayHelloTemplate>
      <p> Say Hello</p>
    </ng-template>
  </div>
```
The content inside the ngTemplateOutlet directive is not displayed. It replaces it with content it gets from the sayHelloTemplate.

#### ngTemplateOutlet with terenary operater

```html
  templateType:string="user";

  <div class="mt-3">
    <ng-container *ngTemplateOutlet="templateType=='user' ? userTemplate: adminTemplate">
      This text is not displayed
    </ng-container>

    <ng-template #userTemplate>
      <p> User Template</p>
    </ng-template>

    <ng-template #adminTemplate>
      <p> Admin Template</p>
    </ng-template>
  </div>
```

### TemplateRef & ViewContainerRef
-----------------------------------
TemplateRef is a class and the way to reference the ng-template in the component or directive class.              
Using the TemplateRef we can manipulate the template from component code.

```html
<ng-template #sayHelloTemplate>
  <p> Say Hello</p>
</ng-template>
```

Now, we can use the ViewChild query to inject the sayHelloTemplate into our component as an instance of the class TemplateRef
```javascript
@ViewChild('sayHelloTemplate', { read: TemplateRef }) sayHelloTemplate:TemplateRef<any>
```
