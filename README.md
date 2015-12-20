# Angular Controllers & Templates

## Objectives

1. Create a controller and its attributes
2. Making views and understand basic Angular HTML tags

## Introduction

Now we have this shiny new Angular app and now we want to
add some functionality to it. But first, here's what we have
built currently. We're going to need to extend from it.

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <body ng-app="MyApp">
      <div ng-view></div>
    </body>
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.15/angular.min.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.15/angular-route.min.js"></script>
    <script>
      window.MyApp = angular.module('MyApp', ['ngRoute'])
    </script>
  </body>
</html>
```

## Creating a Controller

To create a controller, it's as easy as just calling the 
`.controller` method on our global MyApp object.

```javascript
MyApp.controller('BigBoss', function($scope) {})
```

* `BigBoss` here is just an example, it can be changed
* Parameters inside the function call are Angular specific
  imports. We can import things like AJAX helpers or timeout
  helpers. We can even import open source libraries! `$scope`
  is our ViewModel, but we'll go over that in later lessons

If you remember from our secretary example, the big boss was
the controller. He essentially determines what to do based on
the information he's been given. All of our logic should live
here.

## Views

A controller isn't useful without its trusty companion, the View.
This example will mimick the telephone that our secretary uses.

```html
<script type="text/ng-template" id="telephone.html">
  <form class="telephone">
    <input type="text" name="notes" />
  </form>
</script>
```

* The script's ID is "Telephone", it is important to remember
  the name of the template because this is how we reference
  a template

## Routing

Now you're probably furiously refreshing the page, wondering why
you're form isn't showing up. This is because we haven't told 
Angular what to load just yet! To do so, we need to set the 
root route to use our new controller and our view.

```javascript
MyApp.config(['$routeProvider', function($routeProvider) {

  $routeProvider.when('/', {
    templateUrl: 'telephone.html',
    controller: 'BigBoss'
  })

}])
```



