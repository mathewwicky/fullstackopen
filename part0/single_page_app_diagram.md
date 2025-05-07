## A diagram depicting the situation where the user goes to the single-page app version of the notes app at https://studies.cs.helsinki.fi/exampleapp/spa 

![picture](./pics/2.png)

```mermaid

sequenceDiagram
    participant browser
    participant server

    browser ->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server -->>browser: HTML document
    deactivate server

    Note right of browser: The browser starts to generate the HTML code for existing code. Then it starts to fetch the .css, .js and .json file

   browser ->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
   activate server
   server -->>browser: css file
   deactivate server

   browser ->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
   activate server
   server -->>browser: JavaScript file (spa.js)
   deactivate server

   Note right of browser: The browser begins to execute the JavaScript code that manages the spa

   browser ->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
   activate server
   server -->>browser: [{"content": "", "date": "2025-05-06T20:21:58.261Z"},…]
   deactivate server

   Note right of browser: The browser dynamically renders the notes on the page
```
