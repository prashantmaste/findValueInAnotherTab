# findValueInAnotherTab
I want to create a google app script which can read a database and produce the result in another tab. I found a script on google which is written below however this script is returning an error message "TypeError: Cannot read properties of null (reading 'createTextFinder')". 
function findValueInAnotherTab(value, sheetName) {
// Get the spreadsheet and the sheet by name
var ss = SpreadsheetApp.getActiveSpreadsheet();
var sheet = ss.getSheetByName(sheetName);

// Use TextFinder to search for the value
var textFinder = sheet.createTextFinder(value);

// Get the first occurrence of the value
var range = textFinder.findNext();

// If the value is found, return the cell reference
if (range) {
return range.getA1Notation();
} else {
// If the value is not found, return an error message
return "Value not found";
}
}
