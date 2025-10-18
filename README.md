Proyecto desarrollado como parte de la **Sumativa II**: Construcción de un CRUD Monolítico con Django.  
Este sistema permite la **gestión completa de productos (Crear, Leer, Actualizar y Eliminar)**, utilizando exclusivamente Django tanto para el backend como para la renderización de plantillas HTML.


##  **Objetivo**
Desarrollar una aplicación web funcional para administrar productos, aplicando el modelo MVC de Django, vistas basadas en clases (CBV) y el lenguaje de plantillas para renderizar formularios y listas dinámicamente.

## 🚀 Funcionalidades
- Crear, ver, editar y eliminar productos.
- Renderizado con vistas basadas en clases (CBV).
- Plantillas con Bootstrap 5.
- Validación CSRF.
- Base de datos SQLite integrada.


##  **Modelo de datos**
**Archivo:** `productos/models.py`

```python
class Producto(models.Model):
    nombre = models.CharField(max_length=100)
    descripcion = models.TextField()
    precio = models.DecimalField(max_digits=10, decimal_places=2)
    stock = models.IntegerField()

    def __str__(self):
        return self.nombre

# 1. Crear entorno virtual
python -m venv venv

# 2. Activarlo
venv\Scripts\activate   # En Windows
# o
source venv/bin/activate   # En macOS / Linux

# 3. Instalar dependencias
pip install django

# 4. Migrar base de datos
python manage.py makemigrations
python manage.py migrate

# 5. Ejecutar el servidor
python manage.py runserver
