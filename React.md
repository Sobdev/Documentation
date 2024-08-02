# ⚛️ REACT LATE SUMMER REVIEW ⚛️

## FIRST STEPS

### CREATE A PROJECT

#### Using create-react-app  
[https://create-react-app.dev/](https://create-react-app.dev/)

```bash
mkdir "project-name"
npx create-react-app "project-name"

npx create-react-app my-app
cd my-app
npm start
```
For example:
```bash
npx create-react-app first-project
```
To start the projet just run:
```bash
npm start
```
This command launches a development server and opens your React application in your default web browser, typically at http://localhost:3000/.

To stop the server, simply press Ctrl + C in the terminal where the server is running.

In case you are using Vite, the command to start the server is:
```bash
npm run dev
```
This command launches a development server and opens your React application in your default web browser, typically at http://localhost:3000/.

### BASIC CONCEPTS OF PROJECT STRUCTURE
A typical React project created with create-react-app comes with a certain directory structure. Here is a breakdown of the important folders and files:

#### node_modules
The `node_modules` directory contains all the dependencies and packages installed for your React project. These dependencies are listed in the `package.json` file. Whenever you run commands like `npm install react-router-dom` or just `npm i`, the packages get installed or updated in this directory.

#### public Directory
The `public` directory is where static files reside. The most crucial file here is `index.html`, which serves as the main HTML file for your application. Inside this file, you'll find a `<div id="root"></div>`, which is where your React components are rendered.

Here's a bit more detail about some files within the public directory:

*index.html*: This file is the template HTML file that your React components will be injected into. The id="root" div is where the React application mounts, and it is configured in the src/index.js file.

*manifest.json*: This file is primarily used for Progressive Web Apps (PWAs). It contains metadata that allows your app to be installed on a user's device like a native app, providing offline capabilities, among other features. You can learn more about PWAs here.

Other files: Files like favicon.ico, robots.txt, and images like logo192.png and logo512.png are also stored in the public directory. These are typically used for setting up branding (e.g., the favicon) and controlling web crawler behavior (e.g., robots.txt).

#### src Folder (Functional Component)
The `src` folder is where the core of your React application resides. The main entry point for your application is `src/index.js`, and the main component that gets rendered is typically `src/App.js`.

Here's a sample `index.js` file, which is the entry point for your React application:

```import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```
*App.js*: This is the main component of your application. It is rendered by index.js and typically contains other components that make up your application.

*reportWebVitals.js*: This file is used for measuring the performance of your React app. It's optional and can be configured to log results or send them to an analytics endpoint.

*index.css*: This file contains global CSS styles for your application. It is imported into index.js.