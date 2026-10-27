# CicloNova: Proyecto Completo
**Desde la Ingesta en SQL Server hasta el Dashboard en Power BI**

---

### Presentación PPTX
[Descargar o Ver Presentación PPTX](./CicloNova_Proyecto_Completo.pptx)

---

## FASE 1: Laboratorio Data Warehouse
**Construcción de la Arquitectura Medallón y Modelo en Estrella en SSMS**

### Paso 1: Creación de la Base de Datos y Esquemas
* **Resumen:** Ejecución del script inicial para crear la base de datos `DataWarehouse` y los esquemas `bronze`, `silver` y `gold`, estableciendo la estructura base de la Arquitectura Medallón.
![](images/153528.png)
  

### Paso 1.1: Verificación de la Estructura en SSMS
* **Resumen:** Comprobación visual en el Explorador de Objetos de SSMS confirmando la creación exitosa de la base de datos y la correcta jerarquía de los esquemas de seguridad.

![](images/153617.png)

### Paso 2: Creación de Tablas en Capa Bronze
* **Resumen:** Ejecución del script DDL para definir las seis tablas origen (CRM y ERP) dentro del esquema `bronze`, preparándolas para recibir los datos en crudo.
![](images/153748.png)

![](images/153923.png)

![](images/154219.png)

### Paso 2.1: Ingesta Manual y Validación (Capa Bronze)
* **Resumen:** Uso de `BULK INSERT` para cargar los archivos CSV en las tablas Bronze. Validación posterior confirmando la carga de registros (ej. 18.494 clientes).

![](images/154247.png)

![](images/154336.png)

![](images/154850.png)


### Paso 2.2: Verificación de Tablas Bronze Creadas
* **Resumen:** Confirmación en el Explorador de Objetos de la existencia de todas las tablas necesarias (`crm_cust_info`, `erp_loc_a101`, etc.) bajo el esquema Bronze.

![](images/155031.png)

### Paso 3: Creación de Tablas en Capa Silver
* **Resumen:** Ejecución del script para crear las tablas destino en la capa Silver, preparadas para almacenar los datos limpios, estandarizados y con metadatos técnicos (`dwh_create_date`).

![](images/155420.png)

![](images/155511.png)

![](images/155644.png)

![](images/155804.png)

![](images/155929.png)

![](images/160143.png)

![](images/160222.png)

![](images/160341.png)

![](images/160410.png)

![](images/160438.png)

![](images/160620.png)


### Paso 4: Creación y verificación de Tabla Gold
* **Resumen:** Ejecución del script para crear las tablas destino en la capa Gold, preparadas para almacenar los datos limpios, estandarizados y con metadatos técnicos (verificado con consulta de TOP 5 ventas).

![](images/1160659.png)

![](images/161134.png)

![](images/161447.png)

![](images/162141.png)

![](images/163420.png)

![](images/163733.png)

![](images/164128.png)


---

## FASE 2: Conexión y Modelado en Power BI
**De SQL Server a un modelo analítico funcional.**

### PASO 1: Importación (Capa Gold)
* Conexión directa a SQL Server.
* Carga de vistas Gold en Power Query.
* Cero transformaciones adicionales.

![](images/165605.png)

**Quitamos estas tablas que no vamos a usar por ahora:**

![](images/170001.png)

![](images/170009.png)

![](images/170037.png)

**Y trabajamos sólo con estas de GOLD:**

![](images/170742.png)

![](images/170901.png)

### PASO 2: Modelado de Datos y Cardinalidad
* Reconocimiento de claves subrogadas.
* Detección automática y bloqueo de relaciones duplicadas.
  
![](images/171200.png)

![](images/181134.png)

![](images/181648.png)

![](images/182611.png)

![](images/182703.png)

![](images/183723.png)

![](images/183838.png)

![](images/185339.png)

### PASO 3: Consolidación del Modelo
* Esquema en estrella validado.
* Relaciones activas de uno a varios (1:*).
* Modelo listo para la tabla de calendario, creación de la nueva tabla "Dim_DATE".

![](images/190041.png)

![](images/190256.png)

![](images/190527.png)

![](images/190637.png)

![](images/190805.png)

![](images/191249.png)

![](images/191349.png)

![](images/191549.png)

![](images/191638.png)

### PASO 4: Lienzo en Blanco para el Reporte
* Transición a la Vista de Informe.
* Paneles de Datos y Visualizaciones desplegados y listos para usar.

![](images/193210.png)

### PASO 5: Medidas DAX
* Creación de cálculos explícitos en el modelo.
* Ventas Totales integradas.
* Pedidos y Clientes contabilizados.
  
![](images/193802.png)

![](images/194030.png)

![](images/194955.png)

### PASO 6: Dashboard y KPIs
* Tarjetas de indicadores creadas con éxito.
* **29M** Ventas Totales validadas.
* **28K** Pedidos validados.
* **18K** Clientes totales.
* *Laboratorio Completado: De datos crudos a inteligencia visual.*

![](images/111213.png)

![](images/111233.png)



---

## FASE 3: Visualización e Interactividad
**Construcción del Dashboard de CicloNova en Power BI**

### Paso 1: Gráfico de Ventas por País
* **Resumen:** Inserción del gráfico de barras horizontales (Clustered bar chart) cruzando la dimensión de país (`country`) con la métrica de Ventas Totales.
* Selección de barras horizontales.
* Dimensión país asignada al eje Y.
* Ventas Totales asignadas al eje X.
* Resultado: Estados Unidos liderando ingresos.
![](images/112038.png)


### Paso 2: Matriz de Categorías
* **Resumen:** Inserción de la visualización de Matriz (Matrix), permitiendo desglosar los ingresos a nivel de categoría y subcategoría de producto.
* Selección de visual de matriz.
* Categorías asignadas a filas.
* Ventas asignadas a valores.
* Resultado: Desglose jerárquico interactivo de productos.

![](images/112106.png)


### Paso 3: Evolución Temporal
* **Resumen:** Configuración del gráfico de líneas cruzando la tabla calendario (`Año-Mes`) con las Ventas Totales para observar la tendencia a lo largo del tiempo.
* Gráfico de líneas seleccionado.
* `Año-Mes` asignado al eje X.
* Ventas Totales asignadas al eje Y.
* Resultado: Visualización clara de tendencias históricas de facturación.

![](images/112831.png)

### Prueba Final: Interactividad del Modelo
* Filtros cruzados automáticos activados.
* Actualización dinámica visual al interactuar con cualquier elemento del lienzo (ej. seleccionar un país o un mes específico).

### 🎥 Video
<video width="100%" controls>
  <source src="video%20final.mp4" type="video/mp4">
</video>

### Proyecto PBIX Finalizado
* Tema oscuro aplicado para mejorar el contraste visual.
* Modelo analítico interactivo validado y guardado.

![](images/113517.png)
