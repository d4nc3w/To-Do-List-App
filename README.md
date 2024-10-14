# To-Do-List-App Documentation

Table of Contents

* Overview
* Project Structure
* HTML Explanation
* CSS Explanation
* JavaScript Explanation
* How to Use the App

---------------------------------------------------------------------------------------------------------------------------------------------------------

1. Overview
   
* This is a simple web-based To-Do List application that allows users to add tasks, mark them as complete, or delete them. The tasks are saved in the browser’s localStorage, so they persist even after the page is reloaded.

2. Project Structure

- index.html
- style.css
- script.js
- images/
  - list.png
  - uncheck.png
  - check.png

3. HTML Explanation

Key Sections:

* DOCTYPE and Metadata:
  * Declares the HTML5 doctype.
  * lang="en": Specifies English as the document's language.
  * meta charset="UTF-8": Supports special characters.
  * meta name="viewport": Makes the app responsive.
 
* Main Body:
  * The container div contains the app structure.
  * todo-app: A centered box that contains the To-Do List functionality.
  * Inside todo-app, there is:
    * A heading with a logo.
    * An input field to type tasks (input-box).
    * A button to add tasks, calling addTask() on click.
    * An unordered list (list-container) that dynamically displays tasks.
* Script Tag:
  * The JavaScript file script.js is linked at the end of the body to manage the task operations.

4. CSS Explanation

       {
            margin: 0;
            padding: 0;
            font-family: 'Poppins', sans-serif;
            box-sizing: border-box;
        }
        
        .container {
            width: 100%;
            min-height: 100vh;
            background: linear-gradient(135deg, #18c908, #aa1c06);
            padding: 10px;
        }
        
        .todo-app {
            width: 100%;
            max-width: 540px;
            background: #fff;
            margin: 100px auto 20px;
            padding: 40px 30px 70px;
            border-radius: 10px;
        }


* Global Styling:
  * Removes default margins and paddings, sets the Poppins font for all text, and uses box-sizing: border-box to include padding and border in element's total width/height.
* Container:
  * A full-height background with a gradient color.
  * Centers the app within the viewport.
* To-Do App Styling:
  * The .todo-app class applies width constraints, background color, padding, and rounded corners for a card-like appearance.
* Input and Button Styling:
  * .row creates a flexbox layout for aligning the input field and button.
  * The button is styled to be rounded, with a distinctive color to stand out.

5. JavaScript Explanation

Main Functions:
* addTask():
  * Retrieves the text from the input box (inputBox.value).
  * If the input is empty, an alert is triggered.
  * If the input has text, a new li element is created and appended to the list-container (ul).
  * A span element (close/delete button) is added to each li for task removal.

        listContainer.addEventListener("click", function(e){
            if(e.target.tagName === "LI"){
                e.target.classList.toggle("checked");
                saveData();
            } 
            else if(e.target.tagName === "SPAN"){
                e.target.parentElement.remove();
                saveData();
            }
        }, false);

* This listener checks if a li or span was clicked:
  * If a li is clicked, it toggles the checked class (marking the task as completed).
  * If a span is clicked, the task is deleted.
* Local Storage Functions:
  * saveData(): Saves the current list of tasks in localStorage.
  * showTask(): Loads tasks from localStorage when the app is opened or refreshed.


6. How to Use the App

* Open the webpage.
* Type a task in the input box and click "Add" to insert it into the list.
* Click on any task to mark it as completed (it will be crossed out).
* Click the '×' icon next to a task to delete it.
* Tasks are saved automatically and persist between sessions due to browser storage.
* This simple To-Do List app is a great starting point for creating dynamic, interactive web applications.
