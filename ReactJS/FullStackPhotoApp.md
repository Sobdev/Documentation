### **1. Estructura del Proyecto**
Vamos a dividir el proyecto en dos grandes carpetas: `frontend` y `backend`.

```
my-fullstack-app/
│
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── app.js
│   ├── server.js
│   └── package.json
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   ├── styles/
│   │   └── index.css
│   └── package.json
│
└── README.md
```

### **2. Backend (Node.js + Express + MongoDB)**

El backend será responsable de gestionar la lógica del servidor, manejar las peticiones y respuestas, y conectarse a la base de datos. Usaremos **Node.js** con **Express** para el servidor y **MongoDB** con **Mongoose** para la base de datos.

#### **Pasos para Configurar el Backend**

1. **Inicializa el proyecto**

   ```bash
   mkdir backend
   cd backend
   npm init -y
   ```

2. **Instala las dependencias necesarias**

   ```bash
   npm install express mongoose dotenv cors
   ```

3. **Crea un archivo `.env`** para almacenar las variables de entorno como la URI de la base de datos.

   ```env
   MONGODB_URI=mongodb://localhost:27017/myapp
   PORT=5000
   ```

4. **Configura la conexión a la base de datos** (`config/db.js`):

   ```javascript
   const mongoose = require('mongoose');
   const MONGODB_URI = process.env.MONGODB_URI;

   const connectDB = async () => {
       try {
           await mongoose.connect(MONGODB_URI, { useNewUrlParser: true, useUnifiedTopology: true });
           console.log('Connected to MongoDB');
       } catch (error) {
           console.error('Error connecting to MongoDB:', error);
           process.exit(1);
       }
   };

   module.exports = connectDB;
   ```

5. **Configura el servidor de Express** (`server.js`):

   ```javascript
   require('dotenv').config();
   const express = require('express');
   const cors = require('cors');
   const connectDB = require('./config/db');
   const app = express();

   // Middleware
   app.use(cors());
   app.use(express.json());

   // Rutas
   app.use('/api/photos', require('./routes/photoRoutes'));

   // Conectar a la base de datos y levantar el servidor
   connectDB();
   const PORT = process.env.PORT || 5000;
   app.listen(PORT, () => {
       console.log(`Server running on http://localhost:${PORT}`);
   });
   ```

6. **Define el modelo de la base de datos** (`models/Photo.js`):

   ```javascript
   const mongoose = require('mongoose');

   const PhotoSchema = new mongoose.Schema({
       title: { type: String, required: true },
       description: { type: String },
       url: { type: String, required: true },
   });

   module.exports = mongoose.model('Photo', PhotoSchema);
   ```

7. **Configura las rutas** (`routes/photoRoutes.js`):

   ```javascript
   const express = require('express');
   const router = express.Router();
   const Photo = require('../models/Photo');

   // Obtener todas las fotos
   router.get('/', async (req, res) => {
       try {
           const photos = await Photo.find();
           res.json(photos);
       } catch (error) {
           res.status(500).json({ message: error.message });
       }
   });

   // Crear una nueva foto
   router.post('/', async (req, res) => {
       const photo = new Photo(req.body);
       try {
           const newPhoto = await photo.save();
           res.status(201).json(newPhoto);
       } catch (error) {
           res.status(400).json({ message: error.message });
       }
   });

   module.exports = router;
   ```

### **3. Frontend (React + Vite)**

El frontend se encargará de mostrar la interfaz de usuario y hacer las peticiones al backend.

#### **Pasos para Configurar el Frontend**

1. **Inicializa el proyecto de React con Vite**

   ```bash
   mkdir frontend
   cd frontend
   npm create vite@latest . --template react
   npm install
   ```

2. **Instala las dependencias necesarias**

   ```bash
   npm install react-router-dom axios
   ```

3. **Configura el archivo `App.jsx` para definir las rutas:**

   ```javascript
   import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
   import HomePage from './pages/HomePage';
   import PhotoPage from './pages/PhotoPage';

   const App = () => {
       return (
           <Router>
               <Routes>
                   <Route path="/" element={<HomePage />} />
                   <Route path="/photos/:id" element={<PhotoPage />} />
               </Routes>
           </Router>
       );
   };

   export default App;
   ```

4. **Configura la conexión con el backend en `HomePage.jsx`**

   ```javascript
   import { useEffect, useState } from 'react';
   import axios from 'axios';

   const HomePage = () => {
       const [photos, setPhotos] = useState([]);

       useEffect(() => {
           const fetchPhotos = async () => {
               try {
                   const response = await axios.get('http://localhost:5000/api/photos');
                   setPhotos(response.data);
               } catch (error) {
                   console.error('Error fetching photos:', error);
               }
           };
           fetchPhotos();
       }, []);

       return (
           <div>
               <h1>Photo Gallery</h1>
               {photos.map(photo => (
                   <div key={photo._id}>
                       <h2>{photo.title}</h2>
                       <img src={photo.url} alt={photo.title} />
                       <p>{photo.description}</p>
                   </div>
               ))}
           </div>
       );
   };

   export default HomePage;
   ```

5. **Configura el archivo `main.jsx` para renderizar la aplicación:**

   ```javascript
   import React from 'react';
   import ReactDOM from 'react-dom/client';
   import App from './App';
   import './index.css';

   ReactDOM.createRoot(document.getElementById('root')).render(
       <React.StrictMode>
           <App />
       </React.StrictMode>
   );
   ```

### **4. Integración y Ejecución del Proyecto**

- **Ejecuta el backend**:

  ```bash
  cd backend
  node server.js
  ```

- **Ejecuta el frontend**:

  ```bash
  cd frontend
  npm run dev
  ```

Listo.