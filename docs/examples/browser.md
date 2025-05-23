```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Extreme Router Browser Example</title>
    <script type="module">
      // Dynamically determine the latest version or use a specific one
      const version = 'latest'; // Or specify a version like '1.0.0'
      const importUrl = `https://cdn.jsdelivr.net/npm/extreme-router@${version}/dist/index.js`;

      // Ensure the output div exists before trying to set its text content
      window.addEventListener('DOMContentLoaded', () => {
        const outputDiv = document.getElementById('output');
        if (outputDiv) {
          outputDiv.textContent = `Loading Extreme Router from ${importUrl}...`;
        } else {
          console.error('Output div not found on DOMContentLoaded');
        }
        initializeRouter();
      });

      async function initializeRouter() {
        const outputDiv = document.getElementById('output');

        try {
          const extremeRouterModule = await import(importUrl);

          const Extreme = extremeRouterModule.default;
          const param = extremeRouterModule.param;
          const wildcard = extremeRouterModule.wildcard;

          // 1. Initialize the router
          const router = new Extreme();

          // 2. Register plugins
          router.use(param).use(wildcard);

          // 3. Define handlers
          const homeHandler = () => {
            if (outputDiv) outputDiv.textContent = 'Welcome Home!';
          };

          const userHandler = (params) => {
            if (outputDiv) outputDiv.textContent = `User ID: ${params.userId}`;
          };

          const fileHandler = (params) => {
            if (outputDiv) outputDiv.textContent = `File path: ${params['*']}`;
          };

          const notFoundHandler = () => {
            if (outputDiv) outputDiv.textContent = '404 - Page Not Found';
          };

          // 4. Register routes
          router.register('/').handler = homeHandler;
          router.register('/users/:userId').handler = userHandler;
          router.register('/files/*').handler = fileHandler;

          // 5. Function to match and execute handler
          function handleRouteChange() {
            const path = window.location.hash.substring(1) || '/';
            console.log(`Hash changed. Attempting to match route: ${path}`);
            const match = router.match(path);

            if (match && match.handler) {
              if (match.params) {
                match.handler(match.params);
              } else {
                match.handler();
              }
            } else {
              notFoundHandler();
            }
          }

          // 6. Listen to hash changes and initial load
          window.addEventListener('hashchange', handleRouteChange);
          // The 'load' event for the window might have already fired if script is deferred or DOMContentLoaded is used.
          // We call handleRouteChange directly after setup.
          handleRouteChange(); // Initial route handling

          document.getElementById('goHome').addEventListener('click', () => (window.location.hash = '#/'));
          document.getElementById('goUser123').addEventListener('click', () => (window.location.hash = '#/users/123'));
          document
            .getElementById('goFile')
            .addEventListener('click', () => (window.location.hash = '#/files/docs/report.pdf'));
          document
            .getElementById('goNonExistent')
            .addEventListener('click', () => (window.location.hash = '#/nonexistent'));
          console.log('Event listeners for navigation buttons set up.');
          if (outputDiv && !outputDiv.textContent.startsWith('Error:')) {
            outputDiv.textContent = 'Extreme Router initialized. Navigate using buttons or by changing the URL hash.';
          }
        } catch (error) {
          const errorMsg = `Failed to load or initialize Extreme Router: ${error.message}. See console for more details.`;
          console.error(errorMsg, error);
          if (outputDiv) outputDiv.textContent = errorMsg;
        }
      }
    </script>
  </head>
  <body>
    <h1>Extreme Router Browser Example</h1>
    <p>
      Navigate using the links below (changes URL hash) or type directly into the address bar (e.g.,
      <code>#/users/456</code>).
    </p>
    <nav>
      <button id="goHome">Home (/)</button>
      <button id="goUser123">User 123 (/users/123)</button>
      <button id="goFile">File (/files/docs/report.pdf)</button>
      <button id="goNonExistent">Non Existent (/nonexistent)</button>
    </nav>
    <hr />
    <h2>Current Route Output:</h2>
    <div id="output" style="font-family: monospace; background-color: #f0f0f0; padding: 10px; border: 1px solid #ccc;">
      Loading...
    </div>

    <p>Check the browser console for more detailed logs.</p>
    <p>
      This example loads Extreme Router from JSDelivr:
      <code>https://cdn.jsdelivr.net/npm/extreme-router@latest/dist/index.js</code>
    </p>
  </body>
</html>
```
