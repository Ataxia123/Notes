---
id: "Generate Images With JavaScript"
aliases:
  - "Generate Images With JavaScript"
tags: ["images", "javascript"]
---
# Generate Images With JavaScript
JavaScript appears to have the largest collection of image manipulation libraries. There are options for generating GIFs, SVGs, PNGs, PDF, etc. There are solutions for merging images into one (like layering) or adding blur, color corrections, and more.
## gifwrap
Generate GIFs from frames. This integrates nicely with [[#Jimp]].
- https://github.com/jimp-dev/gifwrap
## Jimp
> An image processing library written entirely in JavaScript for Node, with zero external or native dependencies.

The benefits are that it's a cheaper solution compared to [[#Playwright and Puppeteer]] but creating complex images requires more Jimp specific code.
- https://github.com/jimp-dev/jimp
## Playwright and Puppeteer
Playwright and Puppeteer are both used for browser automation. These libraries provide functions for saving HTML elements as PNGs or even saving full pages as PDFs. The benefits are that you can generate images as easily as you can write HTML/CSS. But this comes at a cost, these are rather expensive operations if you're generating tons of images.
## Satori
> Enlightened library to convert HTML and CSS to SVG.

Satori is typically used to generate OG (Open Graph) images for websites. This can be used with or without JSX but most people use the React syntax. There may be opportunities to be creative with Satori but Vercel (the maintainer) has expressed it is limited in what it can render and it may not match what the browser displays 1:1 when rendering the SVG.