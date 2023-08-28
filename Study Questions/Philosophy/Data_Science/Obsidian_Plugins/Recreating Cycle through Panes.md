# Recreating Cycle through Panes

In our Case we don’t need most of this. Our Plugin won’t even have configurable Settings. But what does it need to do? If you are reading this you are most likely using a Browser, to switch between your open Tabs you can press Ctrl + Tab. Cycle through Panes replicates that behavior with Panes in Obsidian. So, what we need to do is the following:

- Add a Command to go to the next Pane, triggered by Ctrl + Tab
- Add a Command to go to the previous Pane, triggered by Ctrl + Shift + Tab

Lets use the following as our Starting Point:

This is almost the bare minimum you will need for any Plugin. Inside the onload() method we will be adding the two Commands. The Obsidian API exposes a method on the Plugin Class to add Commands, if you add them using this official way the User will also be able to change Hotkeys, just like with every other Command! If you want to read up on it, see the official Type Definition [here](https://github.com/obsidianmd/obsidian-api/blob/5af3ef982328a2dd0a2f5242f3c74e2f45e07896/obsidian.d.ts#L2195).

The addCommand() method takes a [Command Object](https://github.com/obsidianmd/obsidian-api/blob/5af3ef982328a2dd0a2f5242f3c74e2f45e07896/obsidian.d.ts#L410) as a parameter, which has fields for a name, which is going to be the display Text, a id, which is basically the internal name, and a callback, which is a function that will be executed every time the command is invoked.  
Instead of using a regular callback, one can use a checkCallback, editorCallback or editorCheckCallback. A regular callback can be invoked from everywhere in Obsidian, while any of the two editorCallback’s only work while a Editor is active, the Editor instance will also be available inside the function as a parameter. The checkCallback’s are used if you need to implement your own Logic on when the Callback can be invoked. As an example, the sample implementation for that only works when there is an active Leaf.  
Other optional fields are mobileOnly, icon (mainly for Obsidian Mobile’s Toolbar) and hotkeys.

Let’s just create the forward cycle first: Add an ID, Name and a checkCallback, for now you can use an empty arrow Function here. If you want to, you can also set default Values for the Hotkeys already, but it is generally advised to not do that to avoid conflicts between Plugins. It should look something like this:

Now that we have that, how do we implement the rest?

In Line 12 we store the currently active leaf inside a variable called “active”. If there is no active Leaf this will be null and thus the callback will return false and not work nor show up in the Command Palette. If the User invoked the Command the passed checking variable will be false and thus our Logic will run.

In Line 15 we first get all Markdown Leaves and right after get the Index of the currently active Leaf.

Now we need to handle an interesting Case. If the active Pane is the last one and the User switches to the next one we want to set the first Pane as active. This is handled by the if statement. If this is not the case we can simply increment the index by one.

Now the only thing thats missing is the same Command, but to go in reverse, from right to left. We can copy almost all of the Code, except that we need to change the id, name and callback a little bit. In the next Gist you will see the complete Code:

The full Plugin
