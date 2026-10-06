# Ingesta EL desde Cosmos DB

---

# **Ejercicio 2: Azure Cosmos DB for NoSQL hacia Azure Data Lake Storage Gen2**


---

# **¿Qué representa Azure Cosmos DB?**

![image.png](image.png)

# **Decisión de arquitectura**

![image.png](b7b93e9d-e561-4200-b46e-43edb27ea21b.png)

# **Fase 1. Crear Azure Cosmos DB for NoSQL**

## **Paso 1. Crear el grupo de recursos**





---

## **Paso 2. Crear la cuenta de Azure Cosmos DB**

---

## **Paso 3. Configurar la cuenta**



---

# **Fase 2. Crear el modelo documental**

## **2.1 Modelo lógico**



## **2.2 Granularidad**


---

## **2.3 Diseño de la clave de partición**


---

## **2.4 Esquema flexible**


---

## **Paso 1. Crear la base de datos y el contenedor**



    

---

## **Paso 2. Preparar los documentos de ejemplo**


---

## **Paso 3. Cargar los documentos**

### **Ruta recomendada: Upload Item**


---

## **Paso 4. Validar la carga de documentos**



### **Comprobación 1. Número total de documentos**


### **Comprobación 2. Mostrar documentos**


### **Comprobación 3. Consultar un usuario**

---

### **Comprobación 4. Consultar clics**


---

### **Comprobación 5. Contar por tipo de evento**

---

### **Comprobación 6. Revisar campos opcionales**

---

### **Comprobación 7. Validar fechas**


# **Fase 3. Crear Azure Data Lake Storage Gen2**

---

## **Paso 1. Crear la cuenta de almacenamiento**


---

## **Paso 2. Crear el contenedor**

---

## **Paso 3. Crear la estructura inicial**

---
# **Fase 4. Crear Azure Data Factory**

---

## **Paso 1. Crear Data Factory**


# **Fase 5. Autorizar a Data Factory sobre ADLS Gen2**



---

## **Asignar el rol Storage Blob Data Contributor**



# **Fase 6. Crear el Linked Service de Azure Cosmos DB**



---

## **Paso 1. Abrir Linked Services**

---

## **Paso 2. Obtener la clave de Cosmos DB**

---

## **Paso 3. Configurar el Linked Service**

---
# **Fase 7. Crear el Linked Service de ADLS Gen2**

---
# **Fase 8. Crear el dataset de origen**


---

## **Paso 1. Crear el dataset**

---

# **Fase 9. Crear el dataset de destino**

---

## **Paso 1. Crear el dataset JSON**

---

## **Paso 2. Crear los parámetros del dataset**


---

## **Paso 3. Parametrizar la ruta**

----
# **Fase 10. Crear el pipeline**

## **Paso 1. Crear el pipeline**

---

## **Paso 2. Añadir la actividad Copy**


---

## **Paso 3. Configurar el origen**


---

## **Paso 4. Configurar el destino**


---

## **Paso 5. Revisar el mapeo**


---

## **Paso 6. Configurar el formato de escritura**




---

## **Paso 7. Validar el pipeline**



---

## **Paso 8. Ejecutar con Debug**



---

## **Paso 9. Publicar**

----

# **Fase 11. Verificar el archivo en ADLS Gen2**



---

## **Validación entre origen y destino**

### **Recuento en Cosmos DB**

----

### **Validación en Data Factory**

---

# **Crear un trigger programado**


---

# **Monitorización de ejecuciones automáticas**




## **Revisar Pipeline runs**

----
### **Interpretación**


---

## **Revisar el detalle de Copy**

---
   ``
    

---

## **Revisar Trigger runs**


# **Consideración importante sobre la zona raw**

![image.png](image%20129.png)

---

# **Esquema flexible y evolución**

![image.png](image%20130.png)

---

---

---

# **Diferencias con el Ejercicio 1**



---

# **Arquitectura final implementada**

---
