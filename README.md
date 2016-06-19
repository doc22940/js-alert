[![Build Status](https://travis-ci.org/jjv360/js-alert.svg?branch=master)](https://travis-ci.org/jjv360/js-alert)

# js-alert
A simple JavaScript alert manager.


## Usage examples

See all tests [here](https://rawgit.com/jjv360/js-alert/master/tests.html).

``` javascript
// Show a plain alert
JSAlert.alert("This is an alert.");

// Show an alert with a title and custom dismiss button
JSAlert.alert("Your files have been saved successfully.", "Files Saved", "Got it");

// Show multiple alerts (alerts are automatically queued)
JSAlert.alert("This is the first alert.");
JSAlert.alert("This is the second alert.");
JSAlert.alert("This is the third and final alert.");

// Automatically dismiss alert
JSAlert.alert("This will only last 10 seconds").dismissIn(1000 * 10);

// Event when dismissed
JSAlert.alert("This one has an event listener!").then(function() {
	console.log("Alert dismissed!");
});

// Show a confirm alert
JSAlert.confirm("Are you sure you want to delete this file?").then(function(result) {
	
	// Check if pressed yes
	if (!result)
		return;
	
	// User pressed yes!
	JSAlert.alert("File deleted!");

});

// Create an alert with custom buttons
var alert = new JSAlert("My text", "My title");
alert.addButton("Yes").then(function() {
	console.log("Alert button Yes pressed");
});
alert.addButton("No").then(function() {
	console.log("Alert button No pressed");
});
alert.show();
```