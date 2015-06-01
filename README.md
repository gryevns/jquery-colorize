jquery-colorize
========

jQuery plugin for generating heat maps. Inspired by [jquery-hottie](https://github.com/DLarsen/jquery-hottie).

#### Usage
```
$("table tbody td").colorize({});
```

#### Options
* min - explicity set a minimum cap on the most negative color
* max - explicity set a maximum cap on the most positive color
* center - explicitly define the neutral value, defaults to mean of values
* readable - invert text color if background color too dark
* parse - function to parse numerical value from each element
* themes - object defining multiple themes
* theme.x.color_min - Most negative color
* theme.x.color_mid - Neutral color
* theme.x.color_max - Most positive color
* theme - theme to use
* percent - set to true if min/max are percent values, defaults to false

###### Examples

```
// All columns of a table apart from the first and second columns
$("table tbody td").not(":nth-child(1),:nth-child(2)").colorize();

// Provide custom parse function for values
// <li xzy="5">data</li>
$("li").colorize({
	parse: function(e) { 
		return $(e).attr("xyz");
	}
});

// Custom theme
var themes = { 
	my_custom_theme: { 
		min_color: "#000000", 
		mid_color:"#DDDDDD", 
		max_color: "#FFFFFF"
	}
};
$("table tbody td").colorize({ 
	themes: themes, 
	theme:"my_custom_theme"
});

```
