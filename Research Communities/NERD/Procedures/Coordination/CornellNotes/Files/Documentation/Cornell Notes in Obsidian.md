---
cssclass: cornell-left, cornell-border, banner-image
---
>[!banner-image] ![[banner-learn.jpg]]

# How to take Cornell Notes in Obsidian

>[!summary] How to use?
>- Make a document a Cornell Note - add the following to the frontmatter `cssclass: cornell-left, cornell-border`
>- For cues - use a cue callout `>[!cue]`
>- For a summary - use a summary callout `>[!summary]`


The Cornell Note-Taking System is a methodology for note-taking where you have 3 types of elements in your notes:

1. Notes
2. Cues
3. Summary

This vault contains all you need to do this.

## Install the cornell.css snippet
The solution presented in this learning vault does not require installing any plugins. However, it does require the installation of a CSS snippet. The instructions for doing this in your personal vault can be found here: [[Installing the snippet]]. This step must be completed before proceeding.

>[!cue] Frontmatter

## Frontmatter to mark your note as a Cornell Note
Your notes will not display the unique Cornell Note format unless you add the necessary frontmatter to the beginning of the note. This allows you to control which notes will be Cornell Notes.

>[!Question] What is frontmatter? 
>If you are not familiar with frontmatter, I encourage you to learn about this feature of Obsidian before going further. You can read about htis feature in Obsidian's online help at this [link](https://help.obsidian.md/Editing+and+formatting/Metadata).

To use the Cornell Notes formatting, you need to add a *cssname* key to the frontmatter for the note. This will look like the following:

```
---
cssclass: cornell-left, cornell-border
---
```
This frontmatter tells Obsidian to make a Cornell Notes cue column to the left side of the page, and also to add the border. To learn about all the cssclass options, reference the [[02 Frontmatter Values]] document.

>[!cue] Cues
## Add Cues to your notes
You add a cue to your notes by using Obsidian's callout feature and identify the callout as a `cue`.

>[!question] What is a callout?
> If you have not used Obsidian's callout feature, you can learn more about it at this [link](https://help.obsidian.md/Editing+and+formatting/Callouts)

Here is a simple example of a cue callout:
>[!cue] This is a cue
```
>[!cue] This is a cue
```
If you look at the left column, you are seeing how this cue callout renders in Obsidian.
>[!cue] This is another cue
```
>[!cue] This is another cue
```

This is another cue. You can have as many cues as you want, just keep adding cue callouts to your document. To learn more about how to use cues, check out [[03 CUE Callouts]].


>[!cue] Summary 
# Adding a Summary to your notes

Just as with cues, the Summary section is built on Obsidian callouts. Here is a simple summary of this page:
```
>[!summary] How to use?
>- Make a document a Cornell Note - add the following to the frontmatter `cssclass: cornell-left, cornell-border`
>- For cues - use a cue callout `>[!cue]`
>- For a summary - use a summary callout `>[!summary]`
```

Learn more about summaries in [[04 SUMMARY Callouts]].