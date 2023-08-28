# Publishing a Plugin

Now everything that’s left to do is publish the Plugin. This involves 4 Steps, filling out the manifest.json, pushing the Code to GitHub, creating a Release on GitHub and finally making a Pull Request to the obsidian-releases Repository with your Plugin’s information.

## Filling out the manifest

The Manifest has 8 fields, the _id_ and _name_, which is almost the same as in a Command, the _version_, which needs to follow [Semantic Versioning](https://semver.org/), the _minAppVersion_, which is the minimal Obsidian Version that your Plugin depends on, this might change if Obsidian’s API changes. A _description_ which is used for the search in the Plugin Browser, the _author_ and _authorUrl_, which should be you and your website or GitHub Profile and lastly the _isDesktopOnly_ field, which needs to be set to true if your Plugin interacts with NodeJS or you are are relying on CodeMirror 5.

## Pushing to GitHub

This Step is super easy if you already created a Repository in the first Step of this Article. Just run the following Commands:

## Creating a Release on GitHub

![](https://miro.medium.com/v2/resize:fit:327/1*135gCoRH8GSeOzHR9JX4qA.png)

On the right hand side, click on “Create new Release”. Inside the “Choose a Tag” field add the current version of your Plugin without a v at the front. This needs to match your manifest.json. If you want you can add a description and a Title, but thats optional. What you will need to do, is adding the main.js (run _npm run build_ to compile it) , manifest.json and if you have one styles.css at the bottom. Once you are ready, hit “Publish Release”.

## Adding the Plugin to the Community Plugins

Go to the official Obsdian-Releases Repository and [open the Community Plugins File](https://github.com/obsidianmd/obsidian-releases/blob/master/community-plugins.json). On the top right hit Edit and add your Plugin to the end of the List like so:

![](https://miro.medium.com/v2/resize:fit:410/1*8VzDSAOeyjCGP_KQsf1Jfw.png)

Editing the File

![](https://miro.medium.com/v2/resize:fit:431/1*0BMB4c9k9fJzOfg0bQeqHw.png)

Adding your Plugin to the File

You just need to make sure to not miss any commas and double check the Repository Name. After that you can click on “Propose Changes” and simply follow the Instructions given by the Obsidian Developers. You are done 🥳!
