---
cssclass: cornell-left, cornell-border, banner-image
---

>[!banner-image] ![[banner-data.jpg]]

# Frontmatter 
As explained in the [[Cornell Notes in Obsidian#Frontmatter to mark your note as a Cornell Note|Frontmatter to mark your note as a Cornell Note]] section of this vault, you need to include specific instructions in the frontmatter of each file that should use the Cornell Notes formatting. This is done by adding one of the following values to the *cssclass* key in the frontmatter of your file.

>[!cue] cssclass key values

|Value| Purpose|
|-|-|
|cornell-left|Add a cue column to the left of the document (Do not use this with cornell-right)|
|cornell-right|Add a cue column to the right of the document (Do not use this with cornell-left)|
|cornell-border|Add a border line that marks the separation between the cue column and the summary footer. Note: the border line only extends for the length of the content, not the screen.|
|cornell-livepreview|(Experimental) enable the Cornell Notes formatting while editing in Live Preview. This doesn't work so well.|

---

## Examples
The following are examples of frontmatter that can be added to a file and their various effects.

##### Example 1: left cue column with borders
```
---
cssclass: cornell-left, cornell-border
---
```

##### Example 2: left cue column with no borders
- Notice in this example, we don't include the cornell-border value. 

```
---
cssclass: cornell-left
---
```


##### Example 3: right cue column with borders
```
---
cssclass: cornell-right, cornell-border
---
```

##### Example 4: right cue column with no borders
```
---
cssclass: cornell-right
---
```
