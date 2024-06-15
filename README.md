# Object Oriented Programing

You have a function called showAlert that opens a popup window with the text "Hello."
# First Task
```
    <button id="alertBtn">alert</button>
    <script>

        function showAlert(message) {
            if (!document.getElementById('dialog')) {

                // Create the dialog
                const dialog = document.createElement('div');
                dialog.id = "dialog";
                dialog.innerHTML = `    
                    <div class="message">
                        ${message}
                    </div>
                    <div class="buttons">
                        <button id="okBtn">OK</button>
                    </div>
                `;

                // Append the dialog to the body
                document.body.appendChild(dialog);

                // Attach a click event listener to the "OK" button
                const okBtn = document.getElementById('okBtn');
                okBtn.addEventListener('click', () => {
                    dialog.remove();  // Remove the dialog from the DOM
                });
            }
        }
        window.alertBtn.addEventListener('click', () =>showAlert('Hello'));
```
        
## Create a class file named dialog.js that contains the Dialog class with the following methods:
* constructor(message): To store the parameters in context.
* render(): To render the HTML to the document.
* onOk(): Triggered when the user clicks the OK button on the popup window.

The ultimate goal of the task is for the HTML to appear as specified and to implement the same functionality.
```
 window.alertBtn.addEventListener('click', ()=>{
            let dialog = new Dialog("my uniq message");
            dialog.render()            
        })
```




# Second Task
* Create another file with a class named Confirm that inherits from the previous Dialog class. 
* In the new class, create a method named render 
* use super to render the HTML from the inherited method. 
* use the DOM to add a button with the text "Cancel." 
* add a method to the class that prints "Cancel" to the console and link it to the button.

The ultimate goal of the task is for the HTML to appear as specified and to implement the same functionality.
```
 window.alertBtn.addEventListener('click', ()=>{
            let dialog = new Confirm("my Confirm message");
            dialog.render()            
        })
```

# Third Task
* Make all methods in the class private. 
* Call render from within the constructor. 
* Pass onCancel and onOK callbacks to the constructor:

```
constructor(message, onCancel, onOK)
```
Store these callbacks in the object's context and execute them within the appropriate methods.
At the end, the code should look something like this:

```
window.alertBtn.addEventListener('click', () => {
  let dialog = new Confirm("my Confirm message", () => console.log('cancel'), () => console.log('OK'));
})

```
