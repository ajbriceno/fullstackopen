sequenceDiagram
    title Sequence Diagram New Notes SPA
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML SPA document
    deactivate server

    note right of browser: The browser show the HTML SPA document

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: Execute the CSS file
    deactivate server

    note right of browser: The browser execute de main.css file

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: Execute the JavaScript file
    deactivate server   

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "This is a Notes list", "date": "2024-07-26" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
    
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa.json
    activate server
    server-->>browser: {"message":"note created"}
    deactivate server

    Note left of server: The server send a responses message in json format then note has been saved