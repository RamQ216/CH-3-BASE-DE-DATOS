Sistema de Gestión de Datos E-commerce (Hendyla)
Este proyecto implementa una infraestructura de persistencia de datos utilizando SQLite3 y Pandas para la gestión de un ecosistema de comercio electrónico. El sistema automatiza la creación de esquemas, la carga masiva de datos y la auditoría de integridad.

1. Arquitectura de Datos
El diseño se basa en un modelo relacional con las siguientes entidades principales:

Clientes (customers): Registro de perfiles, segmentos y datos de contacto.

Productos (products): Catálogo con control de precios, costos y SKUs únicos.

Ventas (orders & order_items): Cabecera y detalle de transacciones vinculadas a clientes.

Auditoría (order_audit & status_history): Trazabilidad de cambios y estados de pedidos.

2. Funcionalidades Core
Automatización de Carga
Reinicio de Base de Datos: Detecta y elimina versiones previas de hendyla.db para asegurar una carga limpia.

Ingesta Masiva: Procesa automáticamente múltiples archivos CSV vinculándolos a sus respectivas tablas.

Consultas de Negocio e Integridad
Relaciones Estructurales: Ejecuta JOINs complejos para rastrear pedidos de alto valor (>300) y desglosar productos por orden.

Auditoría de Errores: Identifica inconsistencias como pedidos sin productos, márgenes de ganancia negativos o datos de contacto faltantes.

Búsqueda Parametrizada: Consultas seguras mediante el uso de tuplas para filtrar por nombre, canal o estado.

3. Requisitos y Ejecución
Dependencias: sqlite3, pandas, os.

Preparación: Asegurar que los archivos .csv (customers, products, orders, etc.) estén en el directorio raíz.

Comando:
python base_datos.py
Bash

python base_datos.py
