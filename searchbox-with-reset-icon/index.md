---
title: Searchbox with Reset Icon
description: Search textbox that enables after 3 charaters. Plus it has icons to search and clear the textbox.
---

# Searchbox with Reset Icon

**Requirements**:
1. To enable the *search button*, textbox must have more than 3 charaters
2. Once you passed #1, search button will be enabled to search
3. Once you click on *search button*, the same will be replaced with *reset button/icon*
4. You can reset/clear the textbox by clicking on *reset button/icon*
5. After clicking on search by following #1, you can see *reset button/icon*. Now if you start deleting charaters, until reaching the charater length to *0*, the reset icon will be visible.
6. By following #5, now if you delete all the charaters from the textbox, again the *search button/icon* will be displayed.


## Demo

<script async src="//jsfiddle.net/kutec/y97zcghz/embed/result/"></script>


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
