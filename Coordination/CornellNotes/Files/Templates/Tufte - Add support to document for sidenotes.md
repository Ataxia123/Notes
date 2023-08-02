<%*
/* 
Author: TfTHacker - more info  https://tfthacker.com/
Date:   2023-07-18
Description: Adds a Cornell Note to the vault with proper frontmatter. 
             Part of the Cornell Notes Learning Vault https://tfthacker.com/cornell-notes.
LICENSE: Copyright © 2023 TfThacker (https://tfthacker.com/)  You are granted a non-exclusive, non-transferable, 
and non-sublicensable license to use and modify this file for your personal use only, and are prohibited from 
distributing, sublicensing, using for commercial purposes. This file remain the property of TfTHacker, and any unauthorized 
use or infringement will result in termination of this License. This file are provided "AS IS" without warranty of any kind, 
and the Licensor shall not be liable for any damages arising from the use or distribution of this file. By using this file, 
you acknowledge that you have read, understand, and agree to be bound by this License Agreement. 
*/


if(tp.file.content==="") { //file is empty - add frontmatter 
    let frontmatterText = "---\n";
    frontmatterText +=    "cssclass: tufte-sidenotes cornell-right";
    frontmatterText +=    "\n---\n";
    return frontmatterText; 
} else { // file has text already
    // Add css class name to frontmatter
    const currentFile = tp.file.find_tfile(tp.file.folder(true) + "/" + tp.file.title);
    app.fileManager.processFrontMatter(currentFile, (frontmatter) => {
        if(frontmatter["cssclass"]===undefined) 
            frontmatter["cssclass"] = "tufte-sidenotes";
        else if(!frontmatter["cssclass"].includes("tufte-sidenotes")) 
            frontmatter["cssclass"] = frontmatter["cssclass"] + " tufte-sidenotes";
            
        if(!frontmatter["cssclass"].includes("cornell-"))
            frontmatter["cssclass"] = frontmatter["cssclass"] + " cornell-right";
    });
    return;
}
%>