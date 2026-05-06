sequenceDiagram
participant browser
participant server

browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
activate server
server-->>browser: 302 Found (/exampleapp/notes)
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes.css
activate server
server-->>browser: 200 Ok html document
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server-->>browser: 200 OK the css file
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
activate server
server-->>browser: 200 OK the javascript file
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server-->>browser: [{ "content": "morning","date": "2026-05-06T03:41:08.960Z"}, ... ]
deactivate server
