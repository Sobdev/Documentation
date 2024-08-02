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
To stop it just press the shortcut contol+c inside the terminal.

This starts the React application on a local server. With Vite, it would be:
```bash
npm run dev
```
It usually opens by default at http://localhost:3000/

### BASIC CONCEPTS OF PROJECT STRUCTURE
#### SRC Folder (Functional Component)
Usually, the src/App.js folder is where the entire project will run. It is known that App.js is the main component that runs because in index.js, within strict mode, <App /> is executed.

```bash
import React from 'react';
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
