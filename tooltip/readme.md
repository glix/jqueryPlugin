# jQuery clueTip Plugin

## License

Dual licensed under the MIT license:

* http://www.opensource.org/licenses/mit-license.php

Copyright Karl Swedberg

## Requirements

* jQuery v1.3+

## Description

Displays a highly customizable tooltip when the user interacts with the matched element. As of clueTip version 1.1, this plugin is [ThemeRoller Ready][1].

* **Full documentation**: [http://plugins.learningjquery.com/cluetip/]
* **Demos**: [http://plugins.learningjquery.com/cluetip/demo/]

## Known Issues

* When `.cluetip()` is invoked from an image map `<area>` element, the plugin ignores the `postionBy` option. Positioning the tooltip by the `coords` is beyond the scope of the plugin, so it instead falls back to positioning according to the mouse's position (`event.pageX` and `event.pageY`) when it enters the `<area>`.

## Important clueTip 1.2 Change

Version 1.2 of the clueTip plugin changes the HTML structure of the tooltip. It uses classes instead of IDs for the elements within the clueTip. This allows multiple tooltips to be visible at the same time (one per call to the .cluetip() method) if the `multiple` option is set to `true`.

The plugin may not work as expected if you update jquery.cluetip.js to version 1.2+ and you don't also update the jquery.cluetip.css stylesheet.

If you have a lot invested in the old clueTip's structure with the IDs, you can get it back by:

1. adding the lib/jquery.compat.cluetip.js file immediately after jquery.cluetip.js, AND
2. replacing lib/jquery.cluetip.css with jquery.compat.cluetip.css.

## Features

### Options

The clueTip plugin allows for (too?) many options. For a complete list, check out the [plugin's homepage][2]

### Content via ajax

By default, the clueTip plugin loads a page indicated by the "rel" attribute via ajax and displays its contents. However, *the attribute to be used for both the body and the heading of the clueTip is user-configurable*.
If a "title" attribute is specified, its value is used as the clueTip's heading.

### Content from HTML element

Optionally, the clueTip's body can display content from an element on the same page.

Just indicate the element's id (e.g. "#some-id") in the rel attribute.

### Content from title attribute

Optionally, the clueTip's body can display content from the title attribute, when a delimiter is indicated.

* The string before the first instance of the delimiter is set as the clueTip's heading.
* All subsequent strings are wrapped in separate DIVs and placed in the clueTip's body.

## Examples

### Basic

This is the most basic clueTip. It displays a 275px-wide clueTip on mouseover of the element with an ID of "tip." On mouseout of the element, the clueTip is hidden.

```javascript
$('#tip').cluetip();
```



```javascript
$('a.clue').cluetip({
  hoverClass: 'highlight',
  sticky: true,
  closePosition: 'bottom',
  closeText: '<img src="cross.png" alt="close" />',
  truncate: 60,
  ajaxSettings: {
    type: 'POST'
  }
});
```


More examples can be found at [http://plugins.learningjquery.com/cluetip/demo/](http://plugins.learningjquery.com/cluetip/demo/)


## Credits

* Originally inspired by Cody Lindley's jTip (http://www.codylindley.com)
* Huge thanks to Jonathan Chaffer, Glen Lipka, Shelane Enos, Hector Santos, Torben Schreiter, Dan G. Switzer, Jörn Zaefferer, and the many others who helped report and fix bugs and suggest features.

[1]: http://jqueryui.com/themeroller/
[2]: http://plugins.learningjquery.com/cluetip/