# API Backend Django Basic

Un proyecto básico de API REST construido con Django y Django REST Framework, diseñado como plantilla base para aplicaciones web escalables.

## 🚀 Características

- **Django 4.x** - Framework web de Python de alto nivel
- **Django REST Framework** - Toolkit potente y flexible para construir APIs web
- **SQLite** - Base de datos ligera incluida (fácil migración a PostgreSQL/MySQL)
- **Estructura modular** - Organización clara de aplicaciones y componentes
- **Sistema de migraciones** - Control de versiones de la base de datos
- **Tests incluidos** - Suite básica de pruebas unitarias

## 📁 Estructura del Proyecto

```
api_backend_django_basic/
├── my_project/                 # Configuración principal del proyecto
│   ├── __pycache__/
│   ├── __init__.py
│   ├── asgi.py                # Configuración ASGI
│   ├── settings.py            # Configuración de Django
│   ├── urls.py                # URLs principales
│   └── wsgi.py                # Configuración WSGI
├── my_app/                     # Aplicación principal
│   ├── migrations/            # Migraciones de la base de datos
│   ├── __init__.py
│   ├── admin.py               # Configuración del panel de administración
│   ├── apps.py                # Configuración de la aplicación
│   ├── models.py              # Modelos de datos
│   ├── serializers.py         # Serializadores para la API
│   ├── tests.py               # Pruebas unitarias
│   ├── urls.py                # URLs específicas de la aplicación
│   └── views.py               # Vistas y lógica de la API
├── db.sqlite3                 # Base de datos SQLite
├── manage.py                  # Utilidad de gestión de Django
└── README.md                  # Este archivo
```

## 🛠️ Instalación

### Prerrequisitos

- Python 3.8 o superior
- pip (gestor de paquetes de Python)
- Git

### Pasos de instalación

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/Jaime-D-Z/api_backend_django_basic.git
   cd api_backend_django_basic
   ```

2. **Crear un entorno virtual**
   ```bash
   python -m venv venv
   
   # En Windows
   venv\Scripts\activate
   
   # En macOS/Linux
   source venv/bin/activate
   ```

3. **Instalar dependencias**
   ```bash
   pip install django djangorestframework
   ```

4. **Ejecutar migraciones**
   ```bash
   python manage.py migrate
   ```

5. **Crear un superusuario (opcional)**
   ```bash
   python manage.py createsuperuser
   ```

6. **Ejecutar el servidor de desarrollo**
   ```bash
   python manage.py runserver
   ```

El proyecto estará disponible en `http://127.0.0.1:8000/`

## 🔧 Configuración

### Variables de entorno (recomendado para producción)

Crea un archivo `.env` en la raíz del proyecto:

```env
DEBUG=True
SECRET_KEY=tu-clave-secreta-aqui
DATABASE_URL=sqlite:///db.sqlite3
```

### Configuración de la base de datos

Por defecto, el proyecto usa SQLite. Para cambiar a PostgreSQL o MySQL, modifica la configuración en `my_project/settings.py`:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'tu_base_de_datos',
        'USER': 'tu_usuario',
        'PASSWORD': 'tu_contraseña',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

## 🧪 Ejecutar pruebas

```bash
python manage.py test
```

## 📖 Uso de la API

### Endpoints disponibles

- `GET /api/` - Lista todos los recursos
- `POST /api/` - Crear un nuevo recurso
- `GET /api/{id}/` - Obtener un recurso específico
- `PUT /api/{id}/` - Actualizar un recurso completo
- `PATCH /api/{id}/` - Actualizar parcialmente un recurso
- `DELETE /api/{id}/` - Eliminar un recurso

### Ejemplo de uso con curl

```bash
# Obtener todos los recursos
curl -X GET http://127.0.0.1:8000/api/

# Crear un nuevo recurso
curl -X POST http://127.0.0.1:8000/api/ \
  -H "Content-Type: application/json" \
  -d '{"campo1": "valor1", "campo2": "valor2"}'
```

## 🚀 Despliegue

### Preparación para producción

1. **Configurar variables de entorno**
   ```bash
   export DEBUG=False
   export SECRET_KEY='tu-clave-secreta-muy-segura'
   ```

2. **Instalar dependencias de producción**
   ```bash
   pip install gunicorn psycopg2-binary
   ```

3. **Ejecutar migraciones en producción**
   ```bash
   python manage.py migrate --settings=my_project.settings
   ```

4. **Recopilar archivos estáticos**
   ```bash
   python manage.py collectstatic --noinput
   ```

### Opciones de despliegue

- **Heroku**: Fácil despliegue con git
- **AWS EC2**: Control completo del servidor
- **DigitalOcean**: Droplets simples y económicos
- **Docker**: Containerización para cualquier plataforma

## 🤝 Contribuir

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📝 Roadmap

- [ ] Autenticación JWT
- [ ] Documentación automática con Swagger
- [ ] Paginación mejorada
- [ ] Rate limiting
- [ ] Logging centralizado
- [ ] Docker containerization
- [ ] CI/CD pipeline

## 🐛 Problemas conocidos

- La base de datos SQLite no es recomendada para producción
- Configuración de CORS pendiente para aplicaciones frontend

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

## 👨‍💻 Autor

**Jaime D-Z** - [GitHub](https://github.com/Jaime-D-Z)

## 🙏 Agradecimientos

- Django Team por el excelente framework
- Django REST Framework por simplificar la creación de APIs
- La comunidad open source por su apoyo continuo

---

⭐ Si este proyecto te fue útil, ¡no olvides darle una estrella!
