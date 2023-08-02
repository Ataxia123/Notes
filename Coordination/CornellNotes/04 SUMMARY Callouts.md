---
cssclass: cornell-left, cornell-border, banner-image
---
>[!banner-image] ![[banner-stars.jpg]]

# Summary Callouts

The Cornell Notes formatting for a summary is trigged with an [Obsidian callout](https://help.obsidian.md/Editing+and+formatting/Callouts#Customize%20callouts) using a type identifier of **summary**. 

As defined in [02 Frontmatter Values](app://obsidian.md/02%20Frontmatter%20Values), a summary cue is enabled for a document when either cornell-left or cornell-right is defined in the frontmatter.

>[!summary] Title for summary
>- information 
>- more information
>- even more information

>[!cue] Sample of a Summary

A summary callout looks like this:
```
>[!summary] Title for summary
>- information 
>- more information
>- even more information
```
In Preview mode, this will appear in the lower section of the pane.
![[Summary-callout-example.png|250]]

>[!cue] Tips for summaries


>I recommend putting your summary at the top of a document. This way it is visible when the document is opened in Live Preview mode. Summaries are intended to be one of the first things seen when opening a document to remind you of the main ideas of the document.
>- In Preview mode, the summary will render in the lower part of the pane. However, the summary is only visible when the part of the document that contains the summary is being rendered by Obsidian. This means as you scroll longer documents, Obsidian doesn't render the Summary callout and thus it disappears.
>Obsidian also has a Summary type callout. The **cornell.css** CSS snippet overrides the built-in summary type callout. If you want, the cornell.css file can be modified to use a different identifier. However, from experience, I don't think this will create a conflict for most users and it allows us to continue to use the Cornell Notes terminology of "Summary" to be a summary.


## Summary at the top of a page
While Cornell Notes typically show a summary at the bottom of the page, this vault demonstrates a "modern" take on Summaries by allowing you to define a summary that positions itself at the top of the screen. To use this summary type, define the type of the callout as a `summary-top` . A summary that appears at the top would be formatted as follows:

>[!cue] Sample of a Summary at the top


```
>[!summary-top] Summary at the top
>- information 
>- more information
>- even more information
```

> It is possible to have two summaries on a page. See the [[Simple Example]] to see this in action. Though we don't really recommend it since the goal of a Summary is to summarize the document in one brief description. However, you might have scenarios where two summaries are useful. We encourage you to experiment with combining these two summary types.


