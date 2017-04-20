## Demo

<script async src="//jsfiddle.net/kutec/y97zcghz/embed/js,html,result/"></script>

## Angular Controller

```javascript
angular.module('myApp', [])
  .controller("Ctrl", function($scope) {
    $scope.searchResultFlag = false;
    $scope.searchMe = function(term) {
      $scope.searchResultFlag = true;
      $scope.
      alert("fired");
    }
    $scope.searchReset = function(term) {
      $scope.searchField = "";
      $scope.searchResultFlag = false;
    }
  });
```

## HTML Markup

```html
<div ng-app="myApp" ng-controller="Ctrl">
  <input id="search" type="text" placeholder="Search..." ng-model="searchField" ng-keyup="$event.which == 13 && searchField.length > 2 ? searchMe(searchField) : null">

  <label for="search">
    <button type="button" ng-if="!searchResultFlag || (searchField.length == 0 && !searchReset(searchField))" ng-click="searchMe(searchField)" ng-disabled="!(searchField.length > 2)">

      Search
      <!-- "Search" text should be replaced with icon -->
    </button>

    <button type="button" ng-click="searchReset(searchField)" ng-if="searchResultFlag && !searchField.length == 0">

      X
      <!-- "Search" text should be replaced with icon -->
    </button>
  </label>
  <br>
  <br> {{searchField}}
  {{searchMe}}
</div>
```

### Included Files
```html
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
```
