---
cssclass: banner-image
---
>[!banner-image] ![[banner-code.jpg]]
# Customizing the cornell.css file 
The cornell.css file included with this vault can be customized for your needs. Often times you may find you need to make adjustments so that the Cornell Note formatting works well in your vault. Specifically, the colors used along with the column widths may need adjustment.

However, changing the CSS file can easily break the styling. So it is good to always have a backup of the cornell.css file on hand.

This document will highlight some of the key settings you may want to adjust. The good news, most of the values you want to adjust are at the top of the cornell.css file.

#### Colors
The cornell.css contains the following variables that affect the coloring of borders and summaries:
```css
.theme-light {
  --cornell-summary-callout-background-color: aliceblue;
  --cornell-border-color: grey;
}

.theme-dark {
  --cornell-summary-callout-background-color: rgb(46, 42, 42);
  --cornell-border-color: rgb(55, 53, 53);
}
```
There are variables for dark mode and light mode. The summary color can be changed, along with the border color. You'll want to modify the color values here to match the theme you are using.

The default colors included in this script work well with the default theme included with Obsidian.

Consult with this online resource for more color options: https://www.w3schools.com/cssref/css_colors.php

#### Cues
The width of the cue and the column where the cue is displayed (either in the left or right margin) is controlled by these variables:
```css
--cornell-cue-column-width: 150px;
--cornell-cue-column-width-readable-line: 150px;

--cornell-cue-callout-width: 160px;
--cornell-cue-callout-width-readable-line: 160px;
```
`--cornell-cue-column-width` controls the margin that appears to the left or right of the document. This margin width is used when the user uses cornell-left or cornell-right in the [[02 Frontmatter Values|frontmatter]].

`--cornell-cue-callout-width: 160px` controls the width of the callout itself. You'll notice for the default theme it is a little wider than the margin. This has to do with the way the default theme formats callouts. 

You'll also notice that there are separate settings for when the user is using **readable line length**. If you are using readable line length, you'll want to adjust the variables with `-readable-line` at the end.

#### Summary
The height of the summary callout that appears at the bottom of the screen is controlled with this variable and can be adjusted:
```css
--cornell-summary-callout-max-height: 150px !important;
```

The height of the summary that appears at the top of a screen can also be customized by changing this variable:
```css
--cornell-summary-callout-top-height: 150px !important;
```

#### Screen width for mobile devices

The following line determines the minimal width of a screen for the Cornell Notes styling to take effect. 
```css
@media (min-width: 400px) {
```
If the screen is less than 400px, a column for the cues is not created. You can adjust this minimum width to better match your personal mobile devices.


## More Information
Please see [[Theme specific customizations]] for more information about fine-tuning cornell.css for other themes.