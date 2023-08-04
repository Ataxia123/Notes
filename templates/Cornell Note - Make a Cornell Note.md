<%*
/* 
Author: TfTHacker - more info  https://tfthacker.com/
Date:   2023-06-25
Description: Adds a Cornell Note to the vault with proper frontmatter. 
             Part of the Cornell Notes Learning Vault https://tfthacker.com/cornell-notes.
LICENSE: Copyright © 2023 TfThacker (https://tfthacker.com/)  You are granted a non-exclusive, non-transferable, 
and non-sublicensable license to use and modify this file for your personal use only, and are prohibited from 
distributing, sublicensing, using for commercial purposes. This file remain the property of TfTHacker, and any unauthorized 
use or infringement will result in termination of this License. This file are provided "AS IS" without warranty of any kind, 
and the Licensor shall not be liable for any damages arising from the use or distribution of this file. By using this file, 
you acknowledge that you have read, understand, and agree to be bound by this License Agreement. 
*/

const columnSide   = await tp.system.suggester(["left", "right"], ["left", "right"], false, "Select a side for the Cornell Note");
if(columnSide===null) return;

const columnBorder = await tp.system.suggester(["Yes", "No"], [true, false], false, "Should a border be displayed between the cues, summaries and notes?");
if(columnBorder===null) return;
    
if(tp.file.content==="") { //file is empty - add frontmatter
    let frontmatterText = "---\n";
    frontmatterText += `cssclass: cornell-${columnSide}`;
    if(columnBorder===true) frontmatterText += " cornell-border";
    frontmatterText += "\n---\n";
    return frontmatterText; 
} else { // file has text already
    // Add css class name to frontmatter
    const currentFile = tp.file.find_tfile(tp.file.folder(true) + "/" + tp.file.title);
    app.fileManager.processFrontMatter(currentFile, (frontmatter) => {
        if(frontmatter["cssclass"]===undefined) 
            frontmatter["cssclass"] = "cornell-"+columnSide;
        else {
            frontmatter["cssclass"] = frontmatter["cssclass"].replace("cornell-left", "").replace("cornell-right", "").replace("cornell-border", "").trim();
            if(!frontmatter["cssclass"].includes("cornell-"+columnSide)) 
                frontmatter["cssclass"] = frontmatter["cssclass"] + " cornell-"+columnSide;
        }

        if(columnBorder===true && !frontmatter["cssclass"].includes("cornell-border"))
            frontmatter["cssclass"] = frontmatter["cssclass"] + " cornell-border";
    });
    return;
}
%>