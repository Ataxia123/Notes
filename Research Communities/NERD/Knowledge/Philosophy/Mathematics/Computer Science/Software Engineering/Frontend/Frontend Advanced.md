# Advanced Frontend Concepts
The following document will outline popular techniques for creating a modern webpage. You must first understand the [[Frontend Basics]] before understanding these concepts.
## Text Content
Each section of the website should have a decent amount of text to fill in the space. One or two sentence is not enough for most sections to feel complete. Adding marketing language can be useful to fill in space (e.g. "Blazingly fast") but it should not be overused.
## Dark Mode
In 2023, "dark mode" is a wide-spread design trope. This typically includes dark backgrounds and light text. More websites use a darker color scheme now than ever. When a website is in "dark mode" the HTML tag or any of the sections on the page should not ever have a `background-color` of white. Instead they should be a dark gray or (preferably) black. Black often looks better than gray as a background color.
## Hover Effects
Hover effects should (mostly) always have a transition class setup so that there's an animation for certain hover effects.
## Border Radius
It is common to avoid a border radius between 1px and 7px. These border radius values are awkward and should be avoided. It can be either 0px or 8px+ depending on the design style. Neobrutalism has a higher-than-average border radius for most elements (especially buttons.)
## Glass
[[What is Glassmorphism|Glassmorphism]] is a fine art. Overusing the glass element or using it poorly can detract from a website's overall design. When glass is used, it should be floating above an interesting background (like an image or a gradient) so that the frosted glass effect doesn't look like a static color.
## Image Placeholders
Use Unsplash's API for placeholder images. These can be placed in the background or inline with the content depending on your webpage. To use Unsplash's API, in the `<img />` src attribute, add `https://unsplash.it/w/h` replacing `w` with the width of the placeholder and `h` with the height.
## Background Textures
There are SVGs available that make for good background textures. These should be used very sparingly and should complement the colors specified. Grid-like textures work best.