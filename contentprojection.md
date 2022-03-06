### Ng-Content & Content Projection in Angular
----------------------------------------------                          
Content projection is a way to pass the HTML content from the parent component to the child component.
The child component will display the template in a designated spot. We use the ng-content element to designate a spot in the template of the child component.
The ng-content also allows us to create multiple slots using the selector attribute. The parent can send different content to each slot.

#### ng-content
The ng-content tag acts as a placeholder for inserting external or dynamic content.         
The Parent component passes the external content to the child component.     
When Angular parses the template, it inserts the external content where ng-content appears in the child component’s template

parentComponent.html
```html
<div class="container">
    <app-child>
        <div class="card-header">
            <h4>Header Content</h4>
        </div>
        <div class="card-body">
            <h4>Body Content</h4>
        </div>
    </app-child>
</div>
```
childComponent.html
```html
<div class="card">
    <ng-content></ng-content>
</div>
```
