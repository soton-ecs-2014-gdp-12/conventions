CSS coding conventions
======================

Tabs should be used for indentation.

Property ordering
-----------------

In general, properties further towards the top should affect layout, while properties towards the bottom should affect appearance.

Specifically, the most common properties should be in this order:

```css
.class {
	position
	display

	flex /* etc. */

	top
	bottom
	left
	right
	z-index

	width  /* also min-, max- */
	height /* also min-, max- */

	padding
	border
	margin

	font /* etc. */
	text-align
	background /* etc. */
	color
}
```
