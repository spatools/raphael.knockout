Raphael.Knockout
================

KnockoutJS integration in RaphaelJS.

## Getting Started

Add libraries to your HTML Page

```html
<script type="text/javascript" src="path/to/knockout.js"></script>
<script type="text/javascript" src="path/to/raphael.js"></script>
<script type="text/javascript" src="path/to/raphael.knockout.js"></script>
```

Create your Knockout ViewModel

```javascript

var vm = {
	x: ko.observable(0),
	y: ko.observable(0),
	width: ko.observable(150),
	height: ko.observable(150,
	fill: ko.observable("#f00")
};

```
Create your Raphael paper, elements, ...

```javascript

var paper = Raphael(0, 0, 350, 350);
var rect = paper.rect();
rect.bind({
	x: vm.x,
	y: vm.y,
	width: vm.width,
	height: vm.height,
	fill: vm.fill
});

// -- or --
rect.bind("x", vm.x);
rect.bind("y", vm.y);
//...

```

Let the magic work !