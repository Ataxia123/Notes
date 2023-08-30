# The Sample Plugin

Now that everything is set up, let’s look at the Plugins Code. Note that I stripped the SampleModal and SampleSettingTab at the End of the File.

Line 1: Import premade Functions and Components from Obsidian, so you can use them in your Plugin

Line 3–9: The Settings the Plugin can store and the default Values

Line 11: A class extending “Plugin” is exported. This is always necessary for a Plugin

Line 14: The onload() Function. This is called every time a Plugin is loaded in Obsidian. In the Sample Plugin it adds a lot of Stuff, but that's just to explain how it works. You can ignore most of them.

Line 17: The Settings are loaded into Obsidian. They are stored on the Disk to persist even when Obsidian is closed. You can see the corresponding Function at the bottom (Line 51).

Line 47: The onunload() Function does the same thing as onload(), but when the Plugin is disabled. Note that this isn’t called when Obsidian closes.

There will also be two more Classes. One extends the “Modal” Component and another one which extends “SettingTab”. These are used to create a dedicated Tab in the Settings or to show these nifty pop up Modals.