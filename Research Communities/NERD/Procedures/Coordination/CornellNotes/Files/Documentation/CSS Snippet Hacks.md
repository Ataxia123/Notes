---
cssclass: border-around-images
---
# CSS Snippet Hacks
This document includes a number of interesting solutions to the needs of users of the Cornell Notes Learning Learning Vault. These "hacks" are not supported, but are provided as insights into how Cornell Notes can be adapted for use in various environments.

This file is a consolidation of those hacks and is intended for users that are comfortable working with CSS Snippets and modifying CSS.

>**Note:** there is no support for these hacks, they are provided as learning tools for the community to build on. They are not thoroughly tested either, so they may not work in every usage scenario. But since they are so interesting, they are provided to you for your own personal experimentation. Feel free to drop into the [[SUPPORT|Discord server]] to discuss these hacks if you like.


## Adding a borderline across the top of a cue till the end of the document
This hack will draw a line across the top of the cue and that line will extend from the far left-hand margin of the document to the right-hand margin as shown in this image:
![[Hack-cue-top-borderline.png|500]]
###### CSS Snippet
```css
.markdown-preview-view.cornell-cue-top-border:is(.cornell-left, .cornell-right) .markdown-preview-section [data-callout="cue"] {
    width: 100% !important;
    border-top: 1px solid var(--background-modifier-border) !important;
    .callout-title,
    .callout-content {
        width: var(--cornell-cue-callout-width) !important;  
        padding-bottom: 0px;
    }
    .callout-content {
        padding-top: 0px !important;
        margin-top: 0px !important;
    }
}

.markdown-preview-view.cornell-right.cornell-cue-top-border .markdown-preview-section [data-callout="cue"] {
    .callout-title,
    .callout-content {
        position: fixed !important;
        right: 0px !important;
    }
    .callout-content {
        margin-top: 25px !important;
    }
}
```

###### Using this snippet
Add the following value to the cssclass in the frontmatter: `cornell-cue-top-border`.

This snippet will likely need to be fine-tuned for your theme. A few things to look for are the width of the cue. This can be changed by replacing the value for width. For example, change:

`width: var(--cornell-cue-callout-width) !important;`

to some other value, like 140px:

`width: 140px;`

