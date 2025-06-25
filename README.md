# -Resoluci-n-de-Listas-de-Proveedores-en-Google-Sheets
Este repositorio contiene las listas de artículos de proveedores resueltas y formateadas según los criterios específicos. El objetivo principal es lograr que la "Lista a trabajar" de cada proveedor coincida con el "Modelo/captura" proporcionado, aplicando lógica y las herramientas adecuadas en Google Sheets.
## Criterios de Archivos Finales

Los archivos finales para cada proveedor cumplen con las siguientes especificaciones:

* **Cabeceras:** Deben tener las cabeceras `Código`, `Descripción` y `Precio` para su correcta identificación.
* **Configuración Regional:** La hoja de cálculo está configurada con la región **Argentina**.
* **Orden de Precios:** Los precios están ordenados de **mayor a menor**.
* **Información Pertinente:** Solo contienen información de los artículos; cualquier dato adicional ha sido eliminado.
* **Archivos Separados:** Cada proveedor tiene su propio archivo final formateado.
* **Solo Valores:** Todas las fórmulas utilizadas han sido eliminadas, quedando únicamente los valores finales.

---

## Proceso de Resolución y Herramientas Utilizadas

Para cada lista de proveedor, se siguieron los siguientes pasos generales:

### 1. Preparación Inicial en Google Sheets

* **Creación de Hoja:** Se creó una nueva hoja de cálculo para cada proveedor.
* **Importación de Datos:** La "Lista a trabajar" fue importada a la hoja de cálculo.

### 2. Configuración Regional

* Se estableció la configuración regional de la hoja de cálculo a **Argentina** (`Archivo > Configuración de la hoja de cálculo > Configuración regional`).

### 3. Limpieza y Formateo de Datos

* **Identificación de Cabeceras:** Se aseguraron las cabeceras `Código`, `Descripción` y `Precio`.
* **Eliminación de Datos No Pertinentes:** Se eliminaron filas y columnas irrelevantes, dejando solo la información de los artículos.

### 4. Normalización de Códigos

* **Eliminación de Espacios:** Se eliminaron todos los espacios en blanco de los códigos.
    * **Herramienta:** `Editar > Buscar y reemplazar` (buscando " " y reemplazando con "").
    * *(Alternativa con fórmula: `SUSTITUIR(Celda;" ";"")` seguido de un pegado especial de valores).*

### 5. Normalización y Formato de Precios

* **Conversión a Número:** Se aseguró que la columna de `Precio` estuviera formateada como número.
* **Ajuste de Ceros (si aplicaba):**
    * Se eliminaron los últimos 4 ceros si el precio original los contenía en exceso (`12340000` -> `1234`).
    * **Herramienta:** División por `10000` (ej. `Celda/10000`) y posterior pegado de valores.
* **Formato Decimal:** Se agregó una coma como separador decimal antes de los últimos dos dígitos (ej. `1234` -> `12,34`), aprovechando la configuración regional Argentina.
    * **Herramienta:** `Formato > Número > Número` (con dos decimales).

### 6. Eliminación de Símbolos

* Se eliminaron los siguientes símbolos de las listas (principalmente de las descripciones):
    * `╝`
    * `┤`
    * `\xE2\x96\x84` (símbolo codificado)
    * `\xE2\x96\x92` (símbolo codificado)
    * **Herramienta:** `Editar > Buscar y reemplazar` para cada símbolo, reemplazando con vacío.

### 7. Ordenamiento Final

* **Ordenamiento por Precio:** Los datos fueron ordenados por la columna `Precio` de mayor a menor.
    * **Herramienta:** `Datos > Ordenar intervalo > Opciones avanzadas de ordenación de intervalo` (orden descendente por la columna Precio).

### 8. Finalización

* **Eliminación de Fórmulas:** Se copiaron y pegaron solo los valores (`Editar > Pegado especial > Pegar solo valores`) para eliminar cualquier fórmula restante.
* **Archivo Final:** Cada archivo `.xlsx` final fue guardado y está listo para ser utilizado.

---

**Nota:** La flexibilidad y el uso de las herramientas de Google Sheets, junto con un razonamiento lógico, fueron clave para adaptar estos pasos a las particularidades de cada lista y lograr la coincidencia con el modelo final.
