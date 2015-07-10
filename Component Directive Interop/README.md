# Component Directive Interop Strategy

One basic strategy of migration is to make it easy to bootstrap Angular 2 components inside AngularJS 1 application (and also AngularJS 1 components inside Angular 2 application). This means that an AngularJS 1 application can be migrated to Angular 2 application piecemeal over many commits one component at a time.

It is important to understand that at any given time any one  DOM element can be owned by only one framework at a time. For this reason it is not possible to mix directives between Angular JS 1 and Angular 2. (Example: <ng2-comp ng1-click="exp">) Further more the expression evaluation semantics are slightly different between the two frameworks which further prevents mixing on per element basis.

Components provide a natural boundary for mixing AngularJS 1 and Angular 2. Each component has an associated template which can be then be compiled be either Angular JS 1 or Angular 2. Within each component template particular semantics apply and is fully managed by the appropriate framework version.

## Transclusion / Projection

Transclusion (AngularJS 1 terminology) and Projection (Angular 2 terminology) is an important part of the Angular components. This proposal allows for a component in Angular 2 to transclude / project elements from Angular JS 1 and vice-versa.


## Testability

Both Angular 1 and Angular 2 components can be unit tested using strategies available for each version. The complications arise when there are interdependencies between the components.
For end to end testing, we need protractor to be able to know when both Angular 1 and Angular 2 contexts are stable as well as how to find bindings on the page for a given context. Exposing a single testability service similar to the one available in Angular 1 could be used to make Protractor understand the hybrid application.


## Non-component code

This strategy is based on using component boundaries as the boundaries between the Angular 1 and Angular 2 code. However there is a lot of Angular 1 code that is not component based, this code needs to be migrated using different strategies described in other sections of this document.