
- **LinkendIn:** https://www.linkedin.com/in/leandro-carriego/
- **Portafolio:** https://portfolio-leandro-carriego.vercel.app/
- **Otro proyecto de ejemplo:** https://github.com/leandrocarriego/chatbot-api-elige-tu-aventura

# Uteam Project

Este es un proyecto basado en microservicios que incluye un frontend en Next.js (React.js) y dos servicios backend para la gestión de personas y películas. El proyecto está desarrollado en Node.js, Django, y FastAPI, y está pensado para ejecutarse en un entorno de desarrollo local.

## Tecnologías

- **Frontend**: Next.js / React.js / TypeScript / JavaScript / Tailwind CSS
- **Backend**:
  - **People Service**: Django (Python) / Django Rest Framework
  - **Movies Service**: FastAPI (Python) / SQLAchemy / Pydantic
- **Base de Datos**: SQLite (para Django y FastAPI)
- **Lenguajes**: Python, JavaScript (TypeScript)

## Estructura del Proyecto

El proyecto se organiza de la siguiente manera:

- `/frontend`: Aplicación frontend desarrollada con Next.js.
- `/people_service`: Servicio de backend en Django para gestionar personas.
- `/movies_service`: Servicio de backend en FastAPI para gestionar películas.

## Que hubiese agregado si tuviera mas tiempo

- Test unitarios
- Terminar de configurar docker-compose
- CI/CD con GitHub actions
- precommit y linting
- Terminar las funcionalidades de frontend y mejorar la UI

## Requisitos

Asegúrate de tener instalados los siguientes programas:

- **Node.js**: [Descargar e instalar](https://nodejs.org/)
- **Python**: [Descargar e instalar](https://www.python.org/)

## Instalación y Ejecución

### 1. Frontend

Desde el directorio raiz ejecuta los siguientes comandos:

```bash
cd frontend
npm install
npm run dev
```

Esto levantará el servidor de desarrollo en `http://127.0.0.1:3000`.

### 2. People Service (Django)

Desde el directorio raiz sigue estos pasos:

```bash
cd people_service
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python manage.py runserver 0.0.0.0:8001
```

El servicio estará disponible en `http://localhost:8001`.
La documentación estará disponible en `http://localhost:8000/api`.

### 3. Movies Service (FastAPI)

Desde el directorio raiz sigue estos pasos:

```bash
cd movies_service
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python main.py
```

El servicio estará disponible en `http://localhost:8000`.
La documentación estará disponible en `http://localhost:8000/docs`.

## Endpoints

### People Service

- `GET /api/people/`: Lista todas las personas.
- `POST /api/people/`: Crea una nueva persona. Ejemplo del body:
`{
  "first_name": "John",
  "last_name": "Doe",
  "birth_date": "1990-01-02",
  "has_insurance": false
}`
- `GET /api/people/{person_id}/`: Retorna una persona segun su ID.
- `GET /api/people/get-by-name/?name={person_name}/`: Retorna una persona segun su ID.
- `POST /api/people/{person_id}/favorite-movies/`: Agrega una pelicula favorita a la persona. Ejemplo del body:
`{
  "movie_id": 10
}`
- `DELETE /api/people/{person_id}/favorite-movies/`: Elimina una pelicula favorita a la persona.

En este servicio solo se almacenan los ids de las peliculas, no los modelos

### Movies Service

- `GET /api/v1/movies/`: Lista todas las películas.
- `POST /api/v1/movies/`: Crea una nueva película. Ejemplo del body:
`{
  "title": "Batman"
}`
- `DELETE /api/v1/movies/{movie_id}/`: Elimina una película.
