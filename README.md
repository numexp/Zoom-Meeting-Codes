# Zoom-Meeting-Codes
Simply generate codes representing Zoom format to snipe meetings.

# Setting It Up
Create a folder, call it anything.
 > Run `CMD`
 
 > Type `cd <PATH>`
 
 > Type `npm install nodejs`
 
 Create a file called `<anything>.js`, Paste the source code or download the JS file.
 
 ```js
 // We import fs for our file handling.
const Task = require('fs');

// Clear console+display copyright.
console.clear();
console.log("\n \n [i] => Zoom Code Generator By ro0ti \n \n")

// Timer that ticks per 1000ms = 1 second.
var interval = setInterval (function ()
{
	runSniper();
}, 1000);

// Writes out log file, ouputs an error if there is one.
function writeLog(data) {
    Task.appendFile('log.txt', data, function (error) {
        if (error) {
            console.log('[ERROR] => ' + error);
        } else {
            console.log('[ENTRIES] => ' + ID);
        }
    });
}

// Global ID for entries created on session.
var ID = 0;

// Formats everything per tick.
function runSniper() {
    var Code_1 = GenerateCode(3);
    var Code_2 = GenerateCode(3);
    var Code_3 = GenerateCode(4);
    var Code_Combined = Code_1 + Code_2 + Code_3;
    var ZoomLink = 'https://zoom.us/j/';
    var ZoomFormat = Code_1 + '-' + Code_2 + '-' + Code_3;
    if (ID == 0) {
        ID = 1;
    } else {
        ID = ID + 1;
    }
    writeLog(ZoomLink + Code_Combined + '\n' + ZoomFormat + '\n \n');
    // Generates each code per tick.
    function GenerateCode(length) {
        var result           = '';
        var characters       = '0123456789';
        var charactersLength = characters.length;
        for ( var i = 0; i < length; i++ ) {
        result += characters.charAt(Math.floor(Math.random() * charactersLength));
        }
        return result;
    }
}
// Created By ro0ti
 ```
 
 Now you can run it by typing `node <filename>.js` and hitting `ENTER`.
