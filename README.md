# 🛍️ SUMATIVAIICRUD_LUISQUILELLI

> **Proyecto Sumativa II - CRUD Monolítico con Django**  
> Desarrollado por **Luis Quilelli**  
> Octubre 2025 | Universidad Bicentenaria de Aragua 🇻🇪

---

## **Objetivo del proyecto**
Construir una aplicación web completa para la **gestión de productos**, implementando un **CRUD (Create, Read, Update, Delete)** con **Django 5** de manera monolítica.  
El sistema utiliza **vistas basadas en clases (CBV)** y el **lenguaje de plantillas de Django** para mostrar, crear, editar y eliminar productos desde una interfaz web atractiva con **Bootstrap 5**.

---

##  **Tecnologías utilizadas**

| Tecnología | Descripción |
|-------------|--------------|
|  **Python ** | Lenguaje principal |
|  **Django 5.2.7** | Framework web backend |
|  **SQLite3** | Base de datos por defecto |
|  **Bootstrap 5** | Estilos y diseño responsive |
|🧠 **Vistas basadas en clases (CBV)** | ListView, DetailView, CreateView, UpdateView, DeleteView |

---

## 🧩 **Estructura del proyecto**
SUMATIVAIICRUD_LUISQUILELLI/
│
├── mi_tienda/ # Configuración global del proyecto Django
│ ├── settings.py # Configuración general y registro de la app 'productos'
│ ├── urls.py # Enrutamiento principal del proyecto
│ └── ...
│
├── productos/ # Aplicación principal del CRUD
│ ├── models.py # Modelo 'Producto'
│ ├── views.py # Lógica del CRUD con vistas genéricas
│ ├── urls.py # Rutas específicas de productos
│ ├── templates/
│ │ └── productos/
│ │ ├── producto_list.html
│ │ ├── producto_detail.html
│ │ ├── producto_form.html
│ │ └── producto_confirm_delete.html
│ └── ...
│
├── templates/ # Plantilla base con Bootstrap (base.html)
│
├── venv/ # Entorno virtual del proyecto
│
├── db.sqlite3 # Base de datos local
│
├── manage.py # Herramienta principal de Django
│
├── requirements.txt # Dependencias del proyecto
│
└── README.md # Documentación del proyecto

---

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
🌐 Rutas principales
Archivo: productos/urls.py

URL	Vista	Descripción
/productos/	ProductoListView	Lista todos los productos
/productos/nuevo/	ProductoCreateView	Crea un nuevo producto
/productos/<int:pk>/	ProductoDetailView	Muestra detalles del producto
/productos/<int:pk>/editar/	ProductoUpdateView	Edita un producto existente
/productos/<int:pk>/eliminar/	ProductoDeleteView	Confirma y elimina un producto

🎨 Diseño visual (Bootstrap 5)
El sistema utiliza una plantilla base (base.html) con un diseño moderno y profesional, incluyendo una imagen de fondo tipo tienda, navbar oscura y estructura responsive.


💻 Ejecución del proyecto
🔹 1. Crear y activar entorno virtual

python -m venv venv
venv\Scripts\activate  # En Windows
# o
source venv/bin/activate  # En macOS / Linux
🔹 2. Instalar dependencias

pip install -r requirements.txt
🔹 3. Ejecutar migraciones

python manage.py makemigrations
python manage.py migrate
🔹 4. Iniciar el servidor

python manage.py runserver
Luego abre en tu navegador:
 http://127.0.0.1:8000/productos/

 Pruebas en Postman (opcional)
Puedes probar las rutas HTTP básicas del CRUD:

Método	URL	Acción
GET	/productos/	Listar productos
GET	/productos/1/	Ver producto específico
POST	/productos/nuevo/	Crear nuevo producto
POST	/productos/1/editar/	Editar producto existente
POST	/productos/1/eliminar/	Eliminar producto existente

 Archivo de dependencias
requirements.txt



 Resultado final
Un sistema web de gestión de productos con interfaz moderna, diseño responsive y funcionamiento completo del ciclo CRUD, implementado totalmente en Django con vistas basadas en clases y plantillas HTML profesionales.

