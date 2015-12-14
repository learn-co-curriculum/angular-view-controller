# An Angular Controller and its Template

## Objectives

1. Understand the controller and view pair

## From MyApp

Previously we loaded Angular's libraries and initialized our
own Angular app.

```
<body ng-app="MyApp">
  <div ng-view></div>
  <script>
    window.MyApp = angular.module('MyApp', ['ngRoute'])
  </script>
</body>
```

We're going to extend from our initialized application and 
write a single controller and template.
