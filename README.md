#  Sistema de Registro de Empleados (Tkinter + MySQL)

Este proyecto es una aplicación de escritorio creada en **Python** utilizando **Tkinter** para la interfaz gráfica y **MySQL** como base de datos.  
Permite **registrar, listar y eliminar empleados** de manera sencilla.

---

## Características principales

- Interfaz gráfica amigable con **Tkinter**
- Gestión de empleados: agregar, ver y eliminar
- Conexión segura con MySQL usando consultas parametrizadas
- Código modular con clases separadas:
  - `Database`: conexión y operaciones SQL
  - `EmployeeModel`: lógica del negocio
  - `App`: interfaz gráfica (vista + controlador)

---

##  Requisitos previos

Antes de ejecutar el programa, asegúrate de tener instalado:

- **Python 3.8 o superior**
- **MySQL Server**
- Librerías necesarias:

```bash
pip install mysql-connector-python
```

--- 

> En este caso, todo el código está contenido en un solo archivo para facilidad de uso, pero puede separarse según las clases indicadas.

---

## Configuración de la base de datos

1. Crea una base de datos llamada `company_db` en MySQL:

```sql
CREATE DATABASE company_db;
USE company_db;

CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    sex ENUM('Masculino', 'Femenino', 'Otro') NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL
);
```

2. Edita las credenciales en la sección `DB_CONFIG` del código:

```python
DB_CONFIG = {
    'host': 'localhost',
    'user': 'root',
    'password': 'tu_contraseña',  # Cambia esto a tu contraseña
    'database': 'company_db'
}
```

---

## Ejecución

1. Guarda el archivo `.py` en una carpeta.
2. Ejecuta desde tu terminal o IDE favorito:

```bash
python app.py
```

3. Se abrirá una ventana gráfica donde podrás:
   - Añadir empleados (nombre, sexo, correo)
   - Ver la lista actualizada en una tabla
   - Eliminar empleados seleccionados

---
## IMAGEN
![Imagen(Cap2/Interfaz.png)]
## Conceptos aplicados

- **Patrón MVC (Modelo-Vista-Controlador)**
- **Programación Orientada a Objetos (POO)**
- **Consultas SQL parametrizadas** (prevención de inyecciones)
- **Manejo de excepciones** y validaciones básicas

---
