## Compiling and running the Plugin

You will see, there are a lot of files already. But don’t worry, only three of them matter at the moment:

- The `main.ts` File, which contains the Code of your Plugin
- The `styles.css` File, which contains a corresponding Style Sheet
- And the `manifest.json` File, which contains important Information, like the Version and Name of your Plugin

If you want to, you can already go ahead and look at these Files, you could for example edit the `manifest.json` to your liking.

Obsidian cannot execute TypeScript files directly, you will need to compile them to JavaScript first. Luckily, everything, including bundling, is already set up correctly in the Sample Plugin, so you don’t have to worry too much about it 🥳.

Most Code Editors, like Visual Studio Code, already have a Terminal Window built in. You can use it to run the following two commands after one another:

The First one will download and cache all dependencies, and the second one will compile your Typescript Files to a single JavaScript File.

Once that’s done, go ahead and copy the `styles.css`, `manifest.json` and `main.js` into a newly created Folder inside your Vault under `<your-vault>/.obsidian/plugins/sample-plugin/`. Now go into Obsidian and enable your Plugin in the Community Plugins Settings:

![](https://miro.medium.com/v2/resize:fit:700/1*NQO9j-nTKciyfcRwO6Y22Q.png)

You will notice, that most Text turned red. This is because of the following CSS inside the `styles.css` you just copied:

This is just a demo to help you get started, you can delete it without consequences.