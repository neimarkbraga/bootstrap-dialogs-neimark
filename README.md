# bootstrap-dialogs-neimark.js v1.1.0
A js plugin that displays dialog similar to javascript's alert, confirm, and prompt.
Dialogs are displayed in form of modal of Bootsrap, which means this plugin is dependent to Bootsrap.
<br /><br />
download the latest commit of bootstrap-dialogs-neimark.js (https://github.com/neimarkbraga/bootstrap-dialogs-neimark/archive/master.zip)
<br /><br />
Dependencies: 
* jquery@^3.2.1
* popper.js@^1.11.0
* bootstrap@^4.0.0-beta

<br /><br />
Demo: (demo.html)

***

## Getting Started
Link the files that are required to run the plugin<br />
```html
<!--Dependencies-->
<link rel="stylesheet" type="text/css" href="assets/bootstrap/dist/css/bootstrap.min.css" />
<script type="application/javascript" src="assets/jquery/dist/jquery.min.js"></script>
<script type="application/javascript" src="assets/popper.js/dist/umd/popper.min.js"></script>
<script type="application/javascript" src="assets/bootstrap/dist/js/bootstrap.min.js"></script>

<!--Plugin-->
<script type="application/javascript" src="dist/bootstrap-dialogs-neimark.min.js"></script>
```

### Initialize
Put the new instance of plugin to a variable, in this example myDialog variable will be used.

```javascript
$(document).ready(function () {
    var myDialog = new BootstrapDialog();
});
```
You can set some options to dialogs
```javascript
$(document).ready(function () {
    var myDialog = new BootstrapDialog({ //values below are the default values.
        buttonClass: 'btn-default', //the button to be used on dialogs
        dialogTitleTag: 'h4', //the tag name of dialogs' title
        dialogSize: '', //class for modal-dialog ex. 'modal-lg' & 'modal-sm'. empty is medium.
        animation: true //turn on or off animation
    });
});
```

### Alert Function
Here is an example code to display an alert:<br />
```javascript
$(document).ready(function () {
    var myDialog = new BootstrapDialog();

    myDialog.alert('Title', 'Some message', function () {
        //callback
        console.log('alert callback!');
    });
});
```

### Parameters of alert function
* **title** (*String*) - your alert title
* **message** (*String*) - your alert message
* **callback** (*Function*) - callback function

### Confirm Function
Here is an example code to display a confirm dialog:<br />
```javascript
$(document).ready(function () {
    var myDialog = new BootstrapDialog();

    myDialog.confirm('Title', 'Some message', function (result) {
        console.log('confirm callback! result: ' + result); //displays result
    });      
});
```

### Parameters of confirm function
* **title** (*String*) - your confirm title
* **message** (*String*) - your confirm message
* **callback** (*Function*) - callback function. Parameters:
    * **result** (*Boolean*) - the result of dialog

### Prompt Function
Here is an example code to display a prompt dialog:<br />
```javascript
$(document).ready(function () {
    var myDialog = new BootstrapDialog();
   
    myDialog.prompt("Title", "Some message", function (result) {
        console.log(result); //displays the user's input
    });      
});
```
You can specify options for prompt dialog
```javascript
$(document).ready(function () {
    var myDialog = new BootstrapDialog();

   var promptOptions = {//values below are the default values.
        label: '', //label for input
        type: 'text', //html input type.
        placeholder: '', //placeholder for input
        value: '', //predefined value of input
        required: true //displays a cancel button if false
    };

    myDialog.prompt("Title", "Some message", function (result) {
        console.log(result); //displays the user's input
    }, promptOptions);      
});
```

### Parameters of prompt function
* **title** (*String*) - title for your message
* **message** (*String*) - your message
* **callback** (*Function*) - callback function. Parameters:
    * **result** (*String*) - the value of user's input
* **options** (*String*) - options to customize the prompt dialog. The code above is the example of options
