sequenceDiagram
    participant browser
    participant server

    Note left of browser: Browser executes function that adds the new note on the page, then sends the new note to the server
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Note right of browser: Payload with the content of the note & timestamp (ex. {"content": "New note", "date": "2023-10-21T14:33:34.053Z"})
    activate server
    server-->>browser: JSON {message: "note created"}
    deactivate server