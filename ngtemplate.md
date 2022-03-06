
### ng-template
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
