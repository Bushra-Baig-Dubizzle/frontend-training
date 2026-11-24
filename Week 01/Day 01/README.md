# What Happens When I Open Our App's URL?

When opening the  app's login URL, the browser first finds the server using DNS and creates a secure HTTPS connection.

- Browser resolves the domain using DNS.
- Establishes a secure HTTPS connection.
- Sends an HTTP request to the server.
- Downloads HTML, CSS, JavaScript, and other assets.
- Parses HTML (DOM) and CSS (CSSOM).
- Processes JavaScript and calculates layout.
- Paints and renders the page.
- Loads cookies and browser storage data.
- Performance trace records loading, scripting, and rendering.
- View Page Source vs. Elements reveals whether HTML is server-rendered or client-rendered.

---

## HTTP Request and Assets

Sends an HTTP request and downloads HTML, CSS, JavaScript, and other assets: 94 requests, 6.8 MB transferred.

![Network waterfall with request and response headers](Screenshots/01-network-headers.png)

## Render-Blocking CSS

Stylesheets linked from the HTML block rendering; the heaviest is `index-CIN-VJS1.css` (329 kB, 623 ms).

![Network tab filtered by .css](Screenshots/02-network-css-filter.png)

## Performance Trace

Records loading, scripting, and rendering: scripting 807 ms, painting 44 ms, rendering 33 ms, DOM of 3,180 elements.

![Performance trace with Optimize DOM size insight](Screenshots/03-performance-trace.png)

## Browser Storage

Loads browser storage data: local storage keeps `persist:root` (app state) and recent settings.

![Application tab showing local storage](Screenshots/04-application-local-storage.png)

## Cookies

Loads cookies: `JWT_Token`, `Refresh_Token`, `CF_Authorization` and analytics cookies.

![Application tab showing cookies](Screenshots/05-application-cookies.png)

## View Page Source vs. Elements

Reveals whether HTML is server-rendered or client-rendered. *(Screenshot to add.)*
