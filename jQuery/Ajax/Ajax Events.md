Ajax requests produce a number of different events that you can subscribe to. Here's a full list of the events and in what order they are triggered.
There are two types of events:
## Local Events
These are callbacks that you can subscribe to within the Ajax request object, like so:
```javascript
 $.ajax({
   beforeSend: function(){
     // Handle the beforeSend event
   },
   complete: function(){
     // Handle the complete event
   }
   // ......
 });
```
## Global Events
These events are triggered on the document, calling any handlers which may be listening. You can listen for these events like so:
```javascript
 $(document).bind("ajaxSend", function(){
   $("#loading").show();
 }).bind("ajaxComplete", function(){
   $("#loading").hide();
 });
```
Global events can be disabled for a particular Ajax request by passing in the global option, like so:
```javascript
 $.ajax({
   url: "test.html",
   global: false,
   // ...
 });
```
## Events
This is the full list of Ajax events, and in the order in which they are triggered. The indented events are triggered for each and every Ajax request (unless a global option has been set). The ajaxStart and ajaxStop events are events that relate to all Ajax requests together.

### ajaxStart (Global Event)
This event is triggered if an Ajax request is started and no other Ajax requests are currently running.
* **beforeSend** (Local Event): This event, which is triggered before an Ajax request is started, allows you to modify the XMLHttpRequest object (setting additional headers, if need be.)
* **ajaxSend** (Global Event): This global event is also triggered before the request is run.
* **success** (Local Event): This event is only called if the request was successful (no errors from the server, no errors with the data).
* **ajaxSuccess** (Global Event): This event is also only called if the request was successful.
* **error** (Local Event): This event is only called if an error occurred with the request (you can never have both an error and a success callback with a request).
* **ajaxError** (Global Event): This global event behaves the same as the local error event.
* **complete** (Local Event): This event is called regardless of if the request was successful, or not. You will always receive a complete callback, even for synchronous requests.
* **ajaxComplete** (Global Event): This event behaves the same as the complete event and will be triggered every time an Ajax request finishes.
### ajaxStop (Global Event)
This global event is triggered if there are no more Ajax requests being processed.
