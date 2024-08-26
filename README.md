# app2
# Mi Flask App

## Descripción

Este proyecto es una aplicación web simple construida con Flask y conectada a una base de datos PostgreSQL. La aplicación permite agregar usuarios y ver una lista de todos los usuarios registrados.

## Estructura del Proyecto

- **`app.py`**: Archivo principal que inicializa la aplicación Flask y sus dependencias.
- **`models.py`**: Define los modelos de base de datos utilizando SQLAlchemy.
- **`routes.py`**: Define las rutas y la lógica de negocio.
- **`config.py`**: Configuración de la aplicación, incluyendo la cadena de conexión a la base de datos.
- **`templates/usuarios.html`**: Plantilla HTML para mostrar la lista de usuarios.
- **`static/`**: Carpeta para archivos estáticos como CSS, JavaScript e imágenes.

## Instalación

1. **Clona el Repositorio**

   git clone https://github.com/tu_usuario/mi_flask_app.git
   cd mi_flask_app
2.Crea un entorno virtual(opcional pero recomendado)
python -m venv venv
source venv/bin/activate  # En Windows usa `venv\Scripts\activate`
3.Instala las dependencias
pip install Flask flask_sqlalchemy psycopg2-binary
4.Configura PostgreSQL
CREATE DATABASE mi_flask_app;
5.Crea la tabla de usuarios
CREATE TABLE usuarios (
  id SERIAL PRIMARY KEY,
  nombre VARCHAR(50) NOT NULL,
  email VARCHAR(120) NOT NULL
);
6.Actualiza el archivo config.py con tus credenciales de PostgreSQL
class Config:
    SQLALCHEMY_DATABASE_URI = 'postgresql://username:password@localhost/mi_flask_app'
    SQLALCHEMY_TRACK_MODIFICATIONS = False

   #Ejecución de la Aplicación
Inicializa la Base de Datos

Ejecuta el script para crear las tablas (esto se hace automáticamente al iniciar la aplicación por primera vez):
2.Inicia la aplicacion
python app.py

Acciones Disponibles

Agregar Usuario: Visita http://127.0.0.1:5000/add_user/<nombre>/<email> para agregar un nuevo usuario.
Ver Usuarios: Visita http://127.0.0.1:5000/usuarios para ver la lista de usuarios.

