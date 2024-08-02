sequenceDiagram
    title Sequence Diagram Notes SPA
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML SPA document
    deactivate server

    Note right of browser: The browser execute and shoe the html document

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: Execute the css file
    deactivate server

    Note right of browser: The browser execute CSS file

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: Execute the JavaScript file
    deactivate server   

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "This is a notes list", "date": "2024-07-26" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
