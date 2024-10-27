# [#](#lrn) Learn SnoJS

> Based of SnoJS v2 Snostorm

### [##](#bsic) Basic Reactivity

> The Data and React tag

The Data tag __always__ is in single quotes ' ' with variable names in double quotes " ".<br/>
It is best practice to place the data tag on the `<body>` element.<br/>
Lets make a variable named `count` and set it to `1`

```html
<body data='{"count":1}'>
	<!-- More Here Later -->
</body>
```
How do we show this variable in the html?<br/>
With the `react` tag and double brackets

```html
<body data='{"count":1}'>
	<p react>
		Count is:{{count}}!!
    </p>
</body>
```
SnoJS will parse this and output `Count is: 1!!`. <br/>
You can use any valid JavaScript within the double brackets. For example...
```html
<p react>
	Pi+1: {{Math.PI+1}}
</p>
``` 
__Do not put a child element that uses sno attributes within a element with a react tag.__

### [##](#todo) Lets make a Todo app

>  The For, Bind, Click, Item, and Item-class tag

Start with the basic SnoJS scaffold and make two variables. an array and a string.  add a ordered list and a text input and submit button
```html
<body data='{"arr":[],"val":""}'>
	<input type="text"/>
	<button>Add Todo</button>
	<ol></ol>
</body>
```

Now we have to connect the users input to the variable val<br/>
To do this we do 
```html
<input type="text" bind="val"/>
```
Next push the value of val to the array on button click
```html
 <button click="arr.push(val);">Add Todo</button>
```
__The click attribute takes any valid JS__<br/>
Next cycle through the items in arr and output them as list items
```html
<ol for="arr" item="li" item-class="item"></ol>
```
Now the full code

```html
<body data='
	"arr":[],
	"val:""
'>
	<input type="text" bind="val"/>
	<button click="arr.push(val);">Add Todo</button>
	<ol for="arr" item="li" item-class="item"></ol>
</body>
```
