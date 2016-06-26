# obTextarea
An angular module to extract textarea's caret position in pixels. This is useful for textarea autocompletes like GitHub or Twitter.

##Get Started
1. Clone [this](https://github.com/obAngular/obTextarea.git) repository</br>
2. Add obTextarea to your project</br>
```html
<!doctype html>
<html ng-app="myApp">
<head>

</head>
<body>
    ...
    <script src="//ajax.googleapis.com/ajax/libs/angularjs/1.1.5/angular.min.js"></script>
    <script src="modules/obTextarea/obTextarea.js"></script>
    <script src="modules/obTextarea/directives/obTextarea.directive.js"></script>
    ...
    <script>
        var myApp = angular.module('myApp', ['obTextareaModule']);

    </script>
    ...
</body>
</html>
```
</br>
3. Add to your textarea the attribute 'data-ob-textarea'. you may supply one of the values rtl / ltr (defaults to ltr)</br>
```html
<textarea data-ob-textarea></textarea>
```
</br>
4. On every key press / click / focus / ng-model change event the directive will emit to its parent scope an event with the new caret pixel position (one line under the caret). to capture it do the following in your controller </br>
```js
...
$scope.$on('obTextarea:caretChange', function (event, data) {
  console.log(data.caret);    //an object that holds the xy position of the caret {x, y}
});
...
```

