# Manual de Esquemas de Validación - Proyecto MongoDB

Este documento describe los esquemas de validación utilizados en las colecciones del proyecto MongoDB. Cada esquema define los campos requeridos, sus tipos de datos y su propósito dentro del sistema.

---

## 1. Colección: productos

**Descripción:** Almacena información sobre los productos disponibles en el inventario.

**Campos:**
- `_id`: Identificador único del producto (`objectId`)
- `cantidad`: Cantidad disponible en inventario (`int`)
- `categoria_id`: Referencia a la categoría del producto (`objectId`)
- `nombre`: Nombre del producto (`string`)
- `precio`: Precio del producto (`double`)
- `proveedor_id`: Referencia al proveedor del producto (`objectId`)

---

## 2. Colección: categorias

**Descripción:** Contiene las categorías a las que pertenecen los productos.

**Campos:**
- `_id`: Identificador único de la categoría (`objectId`)
- `nombre`: Nombre de la categoría (`string`)

---

## 3. Colección: movimientos

**Descripción:** Registra los movimientos de inventario, ya sean entradas o salidas.

**Campos:**
- `producto_id`: Referencia al producto afectado (`objectId`)
- `usuario_id`: Referencia al usuario que realizó el movimiento (`objectId`)
- `tipo`: Tipo de movimiento (`enum`: `"entrada"` o `"salida"`)
- `cantidad`: Cantidad de productos movidos (`int`)
- `fecha`: Fecha del movimiento (`date`)

---

## 4. Colección: proveedores

**Descripción:** Contiene información sobre los proveedores de productos.

**Campos:**
- `_id`: Identificador único del proveedor (`objectId`)
- `nombre`: Nombre del proveedor (`string`)

---

## 5. Colección: usuarios

**Descripción:** Almacena los usuarios del sistema y sus roles.

**Campos:**
- `nombre`: Nombre del usuario (`string`)
- `rol`: Rol asignado al usuario (`string`)

---

Cada uno de estos esquemas puede ser utilizado para validar la estructura de los documentos insertados en sus respectivas colecciones, asegurando la integridad de los datos en la base de datos MongoDB.
