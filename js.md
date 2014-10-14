JavaScript coding convention
============================

Strict mode should be used (`'use strict';`). Semicolons should never be omitted.

In object definitions, trailing commas should always be used. For example:

```js
obj = {
	foo: 'bar',
	baz: 'quux',
}
```

Indentation
-----------

Indentation should be done with tabs up to the indent level, and then spaces for lining up multi-line statements. For example (where a `>` is a tab and a `.` is a space):

```js
function foo() {
>   if (bar === 4) {
>   >   baz("Some really ridiculously long string that should have been "
>   >   ....+ "avoided, maybe even mentioned in the coding conventions.");
>   }
}
```

This allows other developers to choose indent sizes without messing up neatly lined-up parts.

Naming
------

Names should be camel case. The first letter should be lower-case, except for class names or constructors:

```js
LightBulb = (function() {
	function LightBulb() {
		// ...
	}

	return LightBulb;
})();

var numberOfEngineers = 5;
function changeLightBulb(bulb) {
	// ...
}
```

File names should still be in Unix form (e.g. `light-bulb.js`). Unit test files should have the same name as the file which they test, followed by `_test` (e.g. `light-bulb_test.js`).

Types
-----

The [section of JavaScript Garden on Types](https://bonsaiden.github.io/JavaScript-Garden/#types) gives a number of guidelines (in the conclusion paragraphs) which should be followed.

AngularJS
---------

### Dependency injection ###

When defining a directive, service, view, controller, etc., and dynamically injecting dependencies, make sure to pass the parameter name as a string into the array. For example:

```js
angular.module("com.example.foobar", [])
	.directive(
	"ngFooBar",
	["$window", "VG_STATES", function($window, VG_STATES) {
		...
	}])
```

This stops minifiers from breaking the dependency information when they rename parameters.
