<%*
/* 
Author: TfTHacker - more info  https://tfthacker.com/
Date:   2023-06-25
Description: Adds a banner to the current file. Part of the Cornell Notes Learning Vault https://tfthacker.com/cornell-notes.
LICENSE: Copyright © 2023 TfThacker (https://tfthacker.com/)  You are granted a non-exclusive, non-transferable, 
and non-sublicensable license to use and modify this file for your personal use only, and are prohibited from 
distributing, sublicensing, using for commercial purposes. This file remain the property of TfTHacker, and any unauthorized 
use or infringement will result in termination of this License. This file are provided "AS IS" without warranty of any kind, 
and the Licensor shall not be liable for any damages arising from the use or distribution of this file. By using this file, 
you acknowledge that you have read, understand, and agree to be bound by this License Agreement. 
*/

const cancelMessage = "-- Cancel adding a banner --";

// List all JPG and PNG files in the vault
const imageFiles = [cancelMessage,
                    ...(app.vault.getFiles())
                        .filter(f=>f?.extension.toLowerCase()==="jpg" || f.extension?.toLowerCase()==="png")
                        .map(f=>f.path)];

const bannerImage = await tp.system.suggester(imageFiles, imageFiles, false, "Select an image for the banner")

if(bannerImage===null || bannerImage===cancelMessage) return;

if(tp.file.content==="") {
    return `---\ncssclass: banner-image\n---\n>[!banner-image] ![[${bannerImage}]]`; //file is empty
} else { // file has text already
    // Add css class name to frontmatter
    const currentFile = tp.file.find_tfile(tp.file.folder(true) + "/" + tp.file.title);

    setTimeout(async () => { // Wait for templater to finish changing this file then add the class attribute
        app.fileManager.processFrontMatter(currentFile, async (frontmatter) => {
            if(frontmatter["cssclass"]===undefined)
                frontmatter["cssclass"] = "banner-image";
            else if(!frontmatter["cssclass"].includes("banner-image"))
                frontmatter["cssclass"] = frontmatter["cssclass"] + ", banner-image";
        });        
    }, 500);

    // Insert banner image
    return `>[!banner-image] ![[${bannerImage}]]`;
}
%>