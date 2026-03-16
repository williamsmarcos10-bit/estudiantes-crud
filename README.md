# 🎓 CRUD de Estudiantes — Estructura de Datos I

Aplicación web completa para gestión de estudiantes con **Angular + Node.js + MongoDB**.

---

## 🗂️ Estructura del Proyecto

```
estudiantes-crud/
├── backend/          # API REST con Node.js + Express + MongoDB
└── frontend/         # Aplicación Angular 17
```

---

## ✅ Requisitos Previos

- **Node.js** v18 o superior → [nodejs.org](https://nodejs.org)
- **npm** v9 o superior (viene con Node.js)
- **MongoDB** local o cuenta en [MongoDB Atlas](https://cloud.mongodb.com) (gratis)
- **Angular CLI** v17: `npm install -g @angular/cli`

---

## 🚀 Instalación y Ejecución

### 1. Backend

```bash
# Entrar a la carpeta del backend
cd backend

# Instalar dependencias
npm install

# Configurar variables de entorno
cp .env.example .env
# Editar .env con tu cadena de conexión MongoDB

# Iniciar servidor de desarrollo
npm run dev
# → Servidor corriendo en http://localhost:3000
```

#### Configurar MongoDB

**Opción A — Local:**
```
MONGODB_URI=mongodb://localhost:27017/estudiantes_db
```

**Opción B — MongoDB Atlas (recomendado para demostración):**
1. Crear cuenta en [cloud.mongodb.com](https://cloud.mongodb.com)
2. Crear un cluster gratuito (M0)
3. Obtener la cadena de conexión y colocarla en `.env`:
```
MONGODB_URI=mongodb+srv://<usuario>:<password>@cluster0.xxxxx.mongodb.net/estudiantes_db
```

---

### 2. Frontend

```bash
# Entrar a la carpeta del frontend
cd frontend

# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
ng serve
# → Aplicación disponible en http://localhost:4200
```

---

## 🌐 API Endpoints

| Método | Ruta | Descripción |
|--------|------|-------------|
| GET | `/api/estudiantes` | Listar con paginación y búsqueda |
| GET | `/api/estudiantes/:id` | Obtener por ID |
| POST | `/api/estudiantes` | Crear estudiante |
| PUT | `/api/estudiantes/:id` | Actualizar estudiante |
| DELETE | `/api/estudiantes/:id` | Eliminar estudiante |

### Query Params para GET /api/estudiantes

| Param | Descripción | Ejemplo |
|-------|-------------|---------|
| `search` | Filtrar por nombre, carné o email | `?search=maria` |
| `page` | Número de página | `?page=2` |
| `limit` | Registros por página | `?limit=10` |
| `sortField` | Campo de ordenamiento | `?sortField=nombre` |
| `sortOrder` | Dirección (asc/desc) | `?sortOrder=asc` |

---

## 📦 Datos de Prueba

Para insertar los datos de prueba del examen, ejecutar en MongoDB:

```javascript
db.estudiantes.insertMany([
  { nombre: "María García López",  carnet: "2024-001", email: "maria@correo.edu.gt", carrera: "Ing. en Sistemas",     semestre: 3,  estado: "Activo"   },
  { nombre: "Carlos Mendoza",       carnet: "2024-002", email: "carlos@correo.edu.gt",carrera: "Ing. Industrial",       semestre: 5,  estado: "Activo"   },
  { nombre: "Ana Sofía Ramírez",    carnet: "2023-015", email: "ana@correo.edu.gt",   carrera: "Ing. en Sistemas",     semestre: 7,  estado: "Inactivo" },
  { nombre: "Juan Pablo Herrera",   carnet: "2024-008", email: "juan@correo.edu.gt",  carrera: "Lic. en Informática",  semestre: 2,  estado: "Activo"   },
  { nombre: "Lucía Fernández",      carnet: "2023-042", email: "lucia@correo.edu.gt", carrera: "Ing. en Sistemas",     semestre: 9,  estado: "Activo"   }
])
```

---

## 🛠️ Tecnologías Utilizadas

### Backend
- **Node.js** + **Express.js** — Servidor HTTP y routing
- **Mongoose** — ODM para MongoDB
- **CORS** — Habilitación de peticiones cross-origin
- **dotenv** — Variables de entorno

### Frontend
- **Angular 17** (standalone components)
- **Bootstrap 5** — Estilos y diseño responsivo
- **Bootstrap Icons** — Iconografía
- **SweetAlert2** — Alertas y confirmaciones visuales
- **RxJS** — Programación reactiva y debounce en búsqueda

---

## ✨ Funcionalidades Implementadas

### Parte 1 — Backend (35 pts)
- [x] Modelo de Estudiante con todas las validaciones
- [x] Conexión a MongoDB con manejo de errores
- [x] 5 endpoints CRUD completos
- [x] Paginación (`?page`, `?limit`)
- [x] Búsqueda por nombre, carné y email (`?search`)
- [x] Ordenamiento por cualquier campo
- [x] Manejo de errores con códigos HTTP apropiados
- [x] CORS habilitado

### Parte 2 — Frontend (40 pts)
- [x] Tabla con columnas: Nombre, Carné, Email, Carrera, Semestre, Estado, Acciones
- [x] Búsqueda dinámica en tiempo real (debounce 500ms)
- [x] Paginación con controles Anterior/Siguiente/Primera/Última
- [x] Selector de registros por página (5, 10, 20)
- [x] Formulario reactivo reutilizable para crear y editar
- [x] Validaciones con mensajes de error en tiempo real
- [x] Confirmación antes de eliminar (SweetAlert2)
- [x] `EstudianteService` centralizado con `HttpClient`
- [x] Interfaz TypeScript `Estudiante`

### Parte 3 — Integración (15 pts)
- [x] CRUD completo funcional de extremo a extremo

### Bonificaciones (10 pts)
- [x] Diseño responsivo con Bootstrap 5 (+3 pts)
- [x] Notificaciones con SweetAlert2 (+2 pts)
- [x] Ordenamiento de columnas por click en encabezado (+3 pts)
- [x] Loading spinner mientras cargan datos (+2 pts)

---

## 👤 Autor

- **Nombre:** ___________________________
- **Carné:** ___________________________
- **Curso:** Estructura de Datos I
