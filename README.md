# 🛒 Proyecto de Análisis de Datos: Instacart

## 📖 Introducción

Instacart es una plataforma de entregas de comestibles donde los usuarios pueden realizar pedidos y recibirlos directamente en casa, similar a Uber Eats o DoorDash.

El objetivo de este proyecto fue **analizar los patrones de compra de los clientes** a partir de un conjunto de datos modificado de Instacart, en el que se introdujeron valores ausentes y duplicados para practicar técnicas de **limpieza, preprocesamiento y análisis exploratorio de datos (EDA)**.

---

## 🗂️ Diccionario de Datos

El proyecto utiliza **cinco archivos CSV**, que contienen información relacionada con los pedidos, productos, categorías y departamentos:

### `instacart_orders.csv`

| Columna                  | Descripción                               |
| ------------------------ | ----------------------------------------- |
| `order_id`               | ID único del pedido                       |
| `user_id`                | ID único del cliente                      |
| `order_number`           | Número de pedido por cliente              |
| `order_dow`              | Día de la semana del pedido (0 = domingo) |
| `order_hour_of_day`      | Hora del pedido                           |
| `days_since_prior_order` | Días desde el pedido anterior             |

### `products.csv`

| Columna         | Descripción           |
| --------------- | --------------------- |
| `product_id`    | ID único del producto |
| `product_name`  | Nombre del producto   |
| `aisle_id`      | ID del pasillo        |
| `department_id` | ID del departamento   |

### `order_products.csv`

| Columna             | Descripción                             |
| ------------------- | --------------------------------------- |
| `order_id`          | ID del pedido                           |
| `product_id`        | ID del producto                         |
| `add_to_cart_order` | Orden en que se añadió al carrito       |
| `reordered`         | 0 = primera vez / 1 = producto repetido |

### `aisles.csv`

| Columna    | Descripción        |
| ---------- | ------------------ |
| `aisle_id` | ID del pasillo     |
| `aisle`    | Nombre del pasillo |

### `departments.csv`

| Columna         | Descripción             |
| --------------- | ----------------------- |
| `department_id` | ID del departamento     |
| `department`    | Nombre del departamento |

---

## 🧭 Paso 1. Descripción de los Datos

El primer paso consistió en **importar correctamente los archivos CSV** usando `pandas.read_csv()` y verificar que los separadores, nombres de columnas y tipos de datos fueran los adecuados.

Se creó un **DataFrame por archivo** y se inspeccionaron con métodos como `info()`, `head()` y `describe()` para asegurar su correcta lectura.

### ✅ Resultados

* Todos los archivos fueron cargados exitosamente.
* Los tipos de datos se ajustaron (IDs a enteros, fechas a formato adecuado).
* Se identificaron valores ausentes en `days_since_prior_order`, correspondientes principalmente a **nuevos clientes**.
* Se verificó la ausencia de duplicados por combinación (`order_id`, `product_id`).

---

## 🧹 Paso 2. Preprocesamiento de Datos

El preprocesamiento incluyó:

* **Corrección de tipos de datos** en columnas de identificación.
* **Eliminación de duplicados** y control de integridad entre tablas.
* **Tratamiento de valores nulos**, con imputación o exclusión según el contexto.
* **Unión de tablas** (`merge`) para enriquecer la información disponible.

Esto garantizó una base de datos limpia y coherente para el análisis posterior.

---

## 📊 Paso 3. Análisis Exploratorio de Datos (EDA)

Durante el EDA se exploraron los **patrones de comportamiento de los usuarios** y **tendencias de compra**:

### Principales hallazgos:

* Los pedidos se concentran entre las **10 a.m. y 3 p.m.**
* Los **domingos** son el día con más pedidos.
* El promedio de **días entre pedidos** está entre **5 y 7 días**, indicando frecuencia semanal.
* Los **productos orgánicos** y las **bananas** fueron los más pedidos.
* Los productos más añadidos primero al carrito también son en su mayoría **orgánicos**.
* Los clientes suelen comprar entre **1 y 10 artículos por pedido**.

El análisis permitió **identificar hábitos recurrentes**, lo que sugiere oportunidades para personalizar recomendaciones de productos y mejorar la experiencia del usuario.

---

## 🧠 Conclusiones

El proyecto de análisis de datos de Instacart permitió obtener una **visión integral del comportamiento de compra de los clientes**.

### Conclusiones clave:

* Existen **patrones predecibles de compra**, tanto en productos como en horarios.
* Los **productos básicos y orgánicos** tienen una alta tasa de recompra.
* La **limpieza y validación de datos** fueron esenciales para obtener resultados confiables.

En general, el proyecto demostró cómo un enfoque sistemático de **carga, limpieza, análisis y visualización de datos** puede transformar grandes volúmenes de información en **insights valiosos** para la toma de decisiones estratégicas.

---

## 🛠️ Tecnologías Utilizadas

* **Python 3.x**
* **pandas**, **NumPy**, **Matplotlib**, **Seaborn**
* **Jupyter Notebook**

---

## 🚀 Autor

Proyecto desarrollado por **Carlos Esteban Ortiz Espitia** como parte del módulo de Análisis de Datos.
Si deseas replicar este proyecto, asegúrate de tener instaladas las librerías necesarias y contar con los cinco archivos CSV originales.

---
