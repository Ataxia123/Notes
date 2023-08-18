# Specific Design Recommendations
## Components
### Buttons
Buttons should have vertical and horizontal padding. Typically the horizontal padding is greater than the vertical padding on buttons by a small amount. Buttons should always have text that contrasts with the background color. The background color of a button should never be transparent.

Buttons can have borders, shadows, and hover effects, but it should be done with intention rather than adding all of these features to every button. Professional and enterprise websites typically have less rounded buttons and opt for `border-radius: 0px` more often.
### Inputs
`<input />` elements should always either have a border or a background color. This gives it enough contrast to separate the field from the background color. Modern input fields are typically designed with slightly more horizontal and vertical padding than the default browser input boxes.
### Images
Images typically have rounded corners. A drop shadow is optional and should be used sparingly.
### Icons
- [[Heroicons]]

## Colors
Text should always contrast the background color. If the background color is dark, the text should be light and vise versa. If the text is wrapped in an element that has a custom background color, the text color should contrast the parent element; this is especially important for buttons but also applies to cards, etc.

I will explicitly add text color classes to text elements as they may be overwritten by parent styles.
I will use TailwindCSS colors and custom hex colors (when appropriate) to specify colors. I will avoid medium shades of gray for the background color.

## Typography
### Heading/Headers or Titles
Headings (`<h*>` tags) should have a font set. The default browser fonts are not pretty. Paragraph tags should also have a font set that pairs with the header's font appropriately.

### Line Height and Kerning
For text that is very large, it's often appropriate to reduce the line height. This makes line breaks take up less space. For text that is very long, it's also common to see kerning added to reduce the width of the text. Adding kerning can also make certain fonts look better as titles.
## Layout
### Padding
All webpages should have horizontal padding that pads the content from the edges of the screen. It should be at least 12px from the edges on mobile, and for desktop the horizontal padding should be larger. TailwindCSS comes with a `container` class that makes this easier to implement by setting a `max-width`.

Heros should have horizontal padding that is greater than horizontal padding used in the header or footer.

Tailwind provides classes like `mt-4` or `px-8` to add padding easily. To add padding to multiple elements, it's recommended to try and add the padding or margin to the parent element so that its children can benefit from the same spacing.

Spacing numbers (the 4 in `mt-4`) should be divisible by 2 when possible. This often looks better than odd numbers.

### Cards
All cards will have vertical and horizontal padding. It should have at least 8px in padding to keep the inner content separate from the card edges.

Cards rarely take up the full screen-width. Cards are often used with flex layouts to layout multiple cards that are related to each other inline. Cards are also placed at minimum 8px apart, oftentimes more.

### Heros
Heros can be vertically centered and laid out vertically. It's also common to see heros that are divided into 2 with a section on the left and an image or other content on the right. Heros often have a `container` class and a `mx-auto` class to center it and set `max-width`.

Heros should have a background color that is different than the following section's background color.

### Footer
The footer of a webpage should always be pushed to the bottom of the page. This often is done by setting the `min-height` of `html` to `100vh`.

Footers will have the same horizontal padding as the header. Often this padding is more than 16px. The footer also has `py` (vertical padding) and this padding should be at least 12px for web design.

## Design Styles
### Glassmorphism
Glass should not be used in the footer. It is most often used for cards, heros, and navbars. Glass should always have a subtle border to add separation.

Glass components should have a `border-radius` of **at least** 8px. Anything less does not accomplish the glass effect.