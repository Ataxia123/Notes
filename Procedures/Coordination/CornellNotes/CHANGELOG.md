### Update 3

**NEW**
- **Tufte sidenotes**: Some users have asked for Tufte-style sidenotes. Therefore, a new "experimental" and mostly reliable feature is added to the Cornell Notes Learning Vault to enable Tufte sidenotes. Learn more about this feature at [[01 Introduction to Tufte Sidenotes|Introduction to Tufte Sidenotes]].
	- Please note this is an experimental feature and doesn't work with all of Obsidian's document features.
	- Additionally, the vault configuration of this feature is for advanced users. You will need to be comfortable with installing and configuring the Templater plugin. 
	- You can use the **Tufte - Add support to document for sidenotes** template to quickly make a note support Tufte sidenotes.
- A new **[[CSS Snippet Hacks]]** document has been added to the vault. This contains various hacks from the community for enhancing  Cornell Notes in Obsidian.

**FIXES**
- Updated files theme-default-and-others.css and theme-minimal - fixed issue when using the banner.css and border lines together
- The template: "Cornell Note - Make a Cornell Note" was updated.

==**What do you need to do?**==
- These updates include updates to important files that you will likely want to copy to your personal vault. You should update any CSS Snippets from this vault you are using in your personal vault to your personal vault. Also, if you are using the Templates provided by this vault, they have been updated and should be copied to your personal vault.

### Update 2

>Note: Both banner.css and cornell.css have numerous updates. I recommend updating these documents in your personal vaults with the files included in this updated vault to get all the new features and tweaks. The templates were not changed, so they do not need to be updated.

**NEW**

- **Summary at the top of the page**.
	- A [Nick Milo](https://twitter.com/NickMilo) inspired feature! This is a great "modern" take on Cornell Notes. There is now an option to have the document summary appear at the top of a page. 
	- Check out the new document sample [[New Product - Quarterly Goals]]  that demonstrates this new type of summary.
	- The document [[04 SUMMARY Callouts]] has been updated with information on how to use this "Summary at the top"
	- The height of the summary at the top can be adjusted with: --cornell-summary-callout-top-height. See [[Customizing the CSS]] for more information.

- **Printing - Export to PDF**
	- Improvements to the cornell.css file for supporting Export to PDF. For more information, see the new document: [[Printing - Export to PDF]]. 
	- Updated the banner.css file to better handle when using the Export to PDF feature of Obsidian. Also added a frontmatter value for `cssclass` called `banner-no-print` to prevent the banner from showing when using Export to PDF.  More information is available at: https://tfthacker.com/banner-image
 
- **New sample documents**
	- [[New Product - Quarterly Goals]] -  Demonstrates use of cues for goals
	- [[Simple Example]] - This is a barebones example document, so you can see the cues and frontmatter needed for different effects without too much text around it.

- **New support options**
	- You can find me on Discord at: https://discord.gg/6HfUwK8gxC in the cornell-notes channel for real-time discussion and support.

**FIXES**
- Fixed bugs in templates 
	- [[3-Resources/_Systems/Templates/CNLV/Cornell Note - Make a Cornell Note|Cornell Note - Make a Cornell Note]]
	- [[3-Resources/_Systems/Templates/CNLV/Cornell Note -- Add Banner Image|Cornell Note -- Add Banner Image]]
- Fixes to all CSS Snippets - based on community feedback, many improvements were made.

---

### Update 1
**NEW**
- **TEMPLATES:** Added "BONUS" Templater templates. These are not enabled by default because they require the [Templater Plugin](https://obsidian.md/plugins?id=templater-obsidian). The following documents were added to the vault:
	- [[Using Templates]]
	- [[Install and Config Templater]]
	- Templated added:
		- [[Cornell Note - Make a Cornell Note]]
		- [[Cornell Note -- Add Banner Image]]
		- [[Cornell Note -- Add cue to document]]
		- [[Cornell Note -- Add summary to document]]
- Added Files/**CHANGELOG** to the vault for recording all updates

**FIXES** 
- Shortened file names to be compatible with most operating systems.

#### Initial Release
- First release of the vault