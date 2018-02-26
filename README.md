# [<img src="http://maketintsandshades.com/images/favicon.png" width="25px" />](http://maketintsandshades.com) &nbsp;[Tint & Shade Generator](http://maketintsandshades.com)

## What is the Tint & Shade Generator?
The purpose of this tool is to accurately produce tints (lighter variants) and shades (darker variants) of a given hex color in 10% increments.

Testing shows that it matches the calculations of Chrome DevTools, the [W3Schools color picker](http://www.w3schools.com/colors/colors_picker.asp), and the [standard Sass functions](https://sindresorhus.com/sass-extras/#color-function-tint) that mix colors with percentages of pure white or black.

## When would I use this?
It's best used when you already have a base color palette but would like to grab or preview complimentary colors for gradients, borders, backgrounds, shadows or other elements.

This of course can be done [using Sass these days](https://sindresorhus.com/sass-extras/#color-function-tint), but this tool is still very useful for designers or those not comfortable with Sass functions.

## Why 10% increments?
That’s the standard I developed for [my design process at Texas State University](http://www.styleguide.txstate.edu/colors/template.html) and in other projects. I think choosing tints and shades based on a flat percentage is a clean, reproducible way to augment brand palettes and produce designs with depth.

## Calculation Method
The given hex color is first converted to RGB. Then each component of the RGB color has the following calculation performed on it, respectively.

* **Tints:** New value = current value + ((255 - current value) x tint factor)
* **Shades:** New value = current value x shade factor

The new value is rounded if necessary, and then converted back to hex for display.

## Example Calculation
Let's say we want tints and shades of [Rebecca Purple](https://meyerweb.com/eric/thoughts/2014/06/19/rebeccapurple/), #663399.

#### 10% Tint
1. #663399 is converted to the RGB equivalent of 102, 51, 153
1. **R:** 102 + ((255 - 102) x .1) = 117.3, rounded to 117
1. **G:** 51 + ((255 - 51) x .1) = 71.4, rounded to 71
1. **B:** 153 + ((255 - 153) x .1) = 163.2, rounded to 163
1. RGB 117, 71, 163 is converted to the hex equivalent of #7547a3

#### 10% Shade
1. #663399 is converted to the RGB equivalent of 102, 51, 153
1. **R:** 102 x .9 = 91.8, rounded to 92
1. **G:** 51 x .9 = 45.9, rounded to 46
1. **B:** 153 x .9 = 137.7, rounded to 138
1. RGB 92, 46, 138 is converted to the hex equivalent of #5c2e8a

## Attribution
This application is inspired by a similar app once maintained by [North Krimsly](http://highintegritydesign.com/), with significant modifications made to the calculation method and design.

## Credits
[Michael Edelstone](http://michaeledelstone.com) designed and organized it. Nick Wing helped with the JavaScript.

## License
Open source; please use. [CC BY-SA 3.0 US](http://creativecommons.org/licenses/by-sa/3.0/us/)

## Resources
* [Convert other color formats to hex](http://rgb.to)
* [Stack Overflow discussion about the calculation method](https://stackoverflow.com/questions/6615002)
* [W3Schools Color Picker](https://w3schools.com/colors/colors_picker.asp)
