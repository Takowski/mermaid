```mermaid
sequenceDiagram
autonumber
    participant browser
    participant server

    Note over browser: User opens the home page
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/
    activate server
    server-->>browser: HTML document
    deactivate server

    Note over browser: User navigates to Notes page
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document, JavaScript code
    deactivate server

    Note over browser: Browser executes JavaScript code
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: JSON data (notes)
    deactivate server

    Note over browser: Browser generates HTML for notes using DOM-API

    