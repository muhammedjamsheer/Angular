
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
