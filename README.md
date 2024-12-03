# Notebookapp
It's a notebookapp for notes.
HTML
The HTML structure defines the page layout:

Title and Button: The <div class="btn"> contains the app's title and a button to add new notes. Clicking the "Add Note" button triggers JavaScript functionality to create a new note.
Main Container: <div id="main"> is where all the notes appear.


CSS
The CSS styles the app:

Main Layout: Styles such as flexbox for the note container (#main) ensure the notes wrap and align neatly.
Note Cards: Each note has a white background, rounded corners, and separate sections for the title and content.
Buttons and Icons: The "Add Note" button and icons (save and delete) are styled for visibility and usability.


JavaScript
The JavaScript adds functionality to the app.

1. Event Listener for Add Note Button
javascript
Copy code
addBtn.addEventListener("click", function () {
    addNote();
});
Adds a new note when the "Add Note" button is clicked by calling addNote.
2. Add Note Function
javascript
Copy code
const addNote = (text = "", title = "") => { ... }
This function:

Creates a new div with the class note.
Adds:
Save (.save) and Delete (.trash) icons in a header section (.icons).
Two <textarea> elements:
One for the title (.title).
One for the content (.content).
Event listeners:
Save Button: Calls saveNotes to save all notes to localStorage.
Trash Button: Removes the note and updates localStorage.
3. Save Notes Function
javascript
Copy code
const saveNotes = () => { ... }
This function:

Gathers all the text in .title and .content textareas.
Ensures only non-empty notes are saved.
Stores titles and contents as JSON in localStorage under the keys titles and notes.
4. Load Notes Function
javascript
Copy code
function loadNotes() { ... }
This function:

Fetches the stored titles and notes from localStorage.
Loops through the data and calls addNote to recreate each saved note on the page.
5. Save and Delete Buttons
The saveNotes and delBtn functionalities:

Save Button: Updates the localStorage with current note data.
Trash Button: Deletes the note from the DOM and localStorage.
Key Features
Dynamic Note Addition: Clicking "Add Note" creates a new editable note.
Save to LocalStorage: Notes persist across page reloads by storing them in localStorage.
Delete Notes: Users can remove notes using the trash icon.
Title and Content Handling: Notes are split into a title and content, making them more organized.
Execution Flow
Initial Load:
loadNotes() fetches saved notes from localStorage and displays them.
Adding a Note:
The "Add Note" button creates a blank note with placeholders for title and content.
A newly added note is saved automatically.
Saving Notes:
Clicking the save icon stores all notes in localStorage.
Deleting Notes:
Clicking the trash icon removes a note and updates localStorage.
