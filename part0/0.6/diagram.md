ADD A NEW NOTE SEQUENCE IN SPA
```mermaid
sequenceDiagram
    participant browser
    participant server
    participant user

    user->>browser: fills the input with a new note
    activate browser
    browser->>user: shows the new note text inside the html Input
    deactivate browser

    user->>browser: clicks the save button
    activate browser
    Note right of browser: The browser executes the onsubmit event handler which invoke a callback function that add and re-renders the recently added note by user.
    browser->>user: show the recently added note. clear the input text
    browser->>server: POST the form data {content:Hellow!, date:...} to https://studies.cs.helsinki.fi/exampleapp/new_note_s
    activate server
    server->>browser:  {"message":"note created"}
    deactivate server
    deactivate browser
```