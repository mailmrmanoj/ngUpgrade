# Service Interop Strategy

When mixing frameworks it is important that the frameworks can inject values from each other injectors. AngularJS 1 uses String tokens while Angular 2 uses types for references. Additionally Angular JS 1 has single injector, while Angular 2 has hierarchical injectors with visibility rules. Because of these differences the developers will have to explicitly list how to map injectables from Angular JS 1 into Angular 2 and vice-versa.
