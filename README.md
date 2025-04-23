# Basic Arquitecure Template

**Template para poder levantar una aplicacion web completa.**

Este proyecto está dividido en frontend (React), backend (FastAPI + GraphQL) y base de datos (PostgreSQL), usando Docker para un entorno de desarrollo uniforme.

---

## 🧱 Stack Tecnológico

| Componente         | Tecnología                             |
| ------------------ | -------------------------------------- |
| Frontend           | Vite + React + Tailwind CSS            |
| Backend            | FastAPI + Strawberry GraphQL           |
| Base de Datos      | PostgreSQL                             |
| Autenticación (F1) | Supabase Auth                          |
| Autenticación (F2) | JWT + Argon2                           |
| Almacenamiento     | Supabase Storage (o compatible con S3) |
| Tiempo real (F2)   | FastAPI WebSocket + Redis PubSub       |
| CI/CD              | GitHub Actions                         |
| Infraestructura    | Railway (F1), luego Fly.io o VPS       |

---

## 📁 Estructura del Proyecto

```bash
├language-game-app/
├── frontend/ # Vite + React + Tailwind
├── backend/ # FastAPI + Strawberry GraphQL
├── db/ # PostgreSQL config / seeds (opcional)
├── .env # Variables compartidas (ej. claves API, DB)
├── docker-compose.yml # Orquestación de servicios
└── README.md
```

---

## 🚀 Cómo levantar el proyecto localmente

### 🔧 Requisitos

- Docker + Docker Compose
- Node.js + npm (para desarrollo local sin Docker)
- Python 3.10+ (si no usás Docker)
- `poetry` (para el entorno virtual de backend, si vas sin Docker)

### ▶️ Comandos

```bash
# 1. Clonar el repositorio
git clone https://github.com/FranJavCS/template-app-react-fastApi-pg.git
cd template-app-react-fastApi-pg

# 2. Levantar todo con Docker
docker-compose up --build

Frontend: http://localhost:5173

Backend (GraphQL): http://localhost:8000/graphql

Base de datos (PostgreSQL): localhost:5432 (usuario: postgres, clave: postgres)
```

## 🧪 Desarrollo por separado (sin Docker)

Frontend

```bash
cd frontend
npm install
npm run dev
```

Backend

```bash
cd backend
poetry install
poetry run uvicorn main:app --reload --host 0.0.0.0 --port 8000
```
