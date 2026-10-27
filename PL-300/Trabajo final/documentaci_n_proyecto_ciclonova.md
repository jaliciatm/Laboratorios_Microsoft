# CicloNova: Proyecto Completo
**Desde la Ingesta en SQL Server hasta el Dashboard en Power BI**

---

### 🎥 Video Adjunto de Presentación
<video width="100%" controls>
  <source src=""C:\Users\jalic\Pictures\video_final.mp4"" type="video/mp4">
  
</video>

---

## FASE 1: Laboratorio Data Warehouse
**Construcción de la Arquitectura Medallón y Modelo en Estrella en SSMS**

### Paso 1: Creación de la Base de Datos y Esquemas
* **Resumen:** Ejecución del script inicial para crear la base de datos `DataWarehouse` y los esquemas `bronze`, `silver` y `gold`, estableciendo la estructura base de la Arquitectura Medallón.

### Paso 1.1: Verificación de la Estructura en SSMS
* **Resumen:** Comprobación visual en el Explorador de Objetos de SSMS confirmando la creación exitosa de la base de datos y la correcta jerarquía de los esquemas de seguridad.

### Paso 2: Creación de Tablas en Capa Bronze
* **Resumen:** Ejecución del script DDL para definir las seis tablas origen (CRM y ERP) dentro del esquema `bronze`, preparándolas para recibir los datos en crudo.

### Paso 2.1: Ingesta Manual y Validación (Capa Bronze)
* **Resumen:** Uso de `BULK INSERT` para cargar los archivos CSV en las tablas Bronze. Validación posterior confirmando la carga de registros (ej. 18.494 clientes).

### Paso 2.2: Verificación de Tablas Bronze Creadas
* **Resumen:** Confirmación en el Explorador de Objetos de la existencia de todas las tablas necesarias (`crm_cust_info`, `erp_loc_a101`, etc.) bajo el esquema Bronze.

### Paso 3: Creación de Tablas en Capa Silver
* **Resumen:** Ejecución del script para crear las tablas destino en la capa Silver, preparadas para almacenar los datos limpios, estandarizados y con metadatos técnicos (`dwh_create_date`).

### Paso 4: Creación y verificación de Tabla Gold
* **Resumen:** Ejecución del script para crear las tablas destino en la capa Gold, preparadas para almacenar los datos limpios, estandarizados y con metadatos técnicos (verificado con consulta de TOP 5 ventas).

---

## FASE 2: Conexión y Modelado en Power BI
**De SQL Server a un modelo analítico funcional.**

### PASO 1: Importación (Capa Gold)
* Conexión directa a SQL Server.
* Carga de vistas Gold en Power Query.
* Cero transformaciones adicionales.

### PASO 2: Modelado de Datos y Cardinalidad
* Reconocimiento de claves subrogadas.
* Detección automática y bloqueo de relaciones duplicadas.

### PASO 3: Consolidación del Modelo
* Esquema en estrella validado.
* Relaciones activas de uno a varios (1:*).
* Modelo listo para la tabla de calendario.

### PASO 4: Lienzo en Blanco para el Reporte
* Transición a la Vista de Informe.
* Paneles de Datos y Visualizaciones desplegados y listos para usar.

### PASO 5: Medidas DAX
* Creación de cálculos explícitos en el modelo.
* Ventas Totales integradas.
* Pedidos y Clientes contabilizados.

### PASO 6: Dashboard y KPIs
* Tarjetas de indicadores creadas con éxito.
* **29M** Ventas Totales validadas.
* **28K** Pedidos validados.
* **18K** Clientes totales.
* *Laboratorio Completado: De datos crudos a inteligencia visual.*

---

## FASE 3: Visualización e Interactividad
**Construcción del Dashboard de CicloNova en Power BI**

### Paso 1: Gráfico de Ventas por País
* **Resumen:** Inserción del gráfico de barras horizontales (Clustered bar chart) cruzando la dimensión de país (`country`) con la métrica de Ventas Totales.
* Selección de barras horizontales.
* Dimensión país asignada al eje Y.
* Ventas Totales asignadas al eje X.
* Resultado: Estados Unidos liderando ingresos.

### Paso 2: Matriz de Categorías
* **Resumen:** Inserción de la visualización de Matriz (Matrix), permitiendo desglosar los ingresos a nivel de categoría y subcategoría de producto.
* Selección de visual de matriz.
* Categorías asignadas a filas.
* Ventas asignadas a valores.
* Resultado: Desglose jerárquico interactivo de productos.

### Paso 3: Evolución Temporal
* **Resumen:** Configuración del gráfico de líneas cruzando la tabla calendario (`Año-Mes`) con las Ventas Totales para observar la tendencia a lo largo del tiempo.
* Gráfico de líneas seleccionado.
* `Año-Mes` asignado al eje X.
* Ventas Totales asignadas al eje Y.
* Resultado: Visualización clara de tendencias históricas de facturación.

### Prueba Final: Interactividad del Modelo
* Filtros cruzados automáticos activados.
* Actualización dinámica visual al interactuar con cualquier elemento del lienzo (ej. seleccionar un país o un mes específico).

### Proyecto PBIX Finalizado
* Tema oscuro aplicado para mejorar el contraste visual.
* Modelo analítico interactivo validado y guardado.
