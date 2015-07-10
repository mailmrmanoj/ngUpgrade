# Angular 1 Annotation Support

There are a number of 3rd party projects with broadly similar goals to this:

* https://github.com/hannahhoward/a1atscript

* https://github.com/pbastowski/angular2-now

* https://github.com/mikeryan52/angular-decorators

* https://github.com/eaze/ng-classy

The aim is to get some convergence here, either into a single project, or at least to a single API specification.


## API Considerations

If we are going to converge on a single API then these are the areas where we need agreement.

### Angular 2 Shims

These are annotations that map in some way to those used in Angular 2. There is not an exact semantic relationship so we need to discuss whether they create more confusion than good by being nearly but not exactly what will be used in Angular 2. An alternative way of thinking about this is whether they allow us to write code for Angular 1 that will require minimal changes when upgrading to Angular 2.

* @Inject

* @Directive

* @Component

* @View

* @RouteConfig (for ComponentRouter)


### Angular 1 Specific Features

These are annotations and functions that have no meaning in Angular 2. In this sense they are purely to improve the development experience in Angular 1 and are not related to upgrading

* @Controller

* @Service

* @Factory

* @Provider

* @Value

* @Constant

* @Filter

* @Animation

* Module (a1atscript + angular-decorators) / SetModule (angular2-now)

* @Module + @AsModule (a1atscript)

* @Config

* @Run

* bootstrap

* @Require (angular-decorators)

* @Transclude (angular-decorators)

* @DirectiveObject (a1atscript) DDO??

In addition some of the libraries offer automatic namespacing of directives and services.


### 3rd Party Library Features

These are annotations that are related to libraries that are not part of the core Angular project.

* @State (for ui-router)

* @MeteorMethod (for Meteor)

