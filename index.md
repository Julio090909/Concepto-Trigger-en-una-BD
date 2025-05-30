<p align="center">
  <img src=""cafam-logo2.webp"" alt="Colegio APEC CAFAM" width="500"/>
</p>

<p align="center"><strong>Estudiante:</strong> Julio Núñez</p>
<p align="center"><strong>Materia:</strong> Administración y Diseño de Bases de Datos</p>
<p align="center"><strong>Profesor:</strong> Víctor Vladimir Recio Rojas</p>
<p align="center"><strong>Año escolar:</strong> 2024-2025</p>
<p align="center"><strong>Colegio:</strong> Fernando Arturo de Meriño - CAFAM</p>

---

### **1. ¿Qué es un Trigger?**
Es un objeto de base de datos que se ejecuta automáticamente cuando se produce un evento específico en una tabla, como una inserción, actualización o eliminación.

### **2. ¿Para qué sirve un Trigger?**
Sirve para mantener la integridad de los datos, realizar auditorías, validar información o ejecutar acciones automáticas como actualizaciones en otras tablas.

### **3. ¿Cuándo se puede usar un Trigger?**
Se puede usar antes o después de una acción `INSERT`, `UPDATE` o `DELETE`, según lo que se desee controlar o ejecutar.

### **4. Estructura de un Trigger**
```sql
CREATE TRIGGER nombre_del_trigger
{BEFORE | AFTER} {INSERT | UPDATE | DELETE}
ON nombre_tabla
FOR EACH ROW
BEGIN
END;
```

### **5. Tipos de Trigger:**
AFTER Trigger: Se ejecuta después de la acción (INSERT, UPDATE, DELETE).

INSTEAD OF Trigger: Reemplaza la acción original.

BEFORE Trigger (en algunos SGBD como MySQL): Se ejecuta antes de la acción.

## **6. ¿Cuándo ejecuta su acción un Trigger?**
El trigger se ejecuta automáticamente cuando se produce el evento definido (ej. un INSERT en la tabla), sin necesidad de llamar manualmente.

7. Ejemplo de un Trigger:
```sql
CREATE TRIGGER trg_Auditoria_Producto
ON Productos
AFTER INSERT
AS
BEGIN
   INSERT INTO Auditoria (Accion, Fecha)
   VALUES ('Se insertó un producto', GETDATE());
END;
```

### **8. Trigger Marketing:**
En marketing digital, un "trigger" es un disparador automático de una acción de marketing (ej. envío de correo cuando un cliente abandona un carrito). No es lo mismo que un trigger de base de datos, pero comparte la idea de automatizar respuestas ante ciertos eventos.

### **9. ¿Cómo hacer un Trigger?**
Define el evento (INSERT, UPDATE, DELETE).

Usa la sentencia CREATE TRIGGER.

Indica cuándo se ejecuta (AFTER, BEFORE, INSTEAD OF).

Escribe el bloque de instrucciones que deseas ejecutar automáticamente.

### **10. Características de un Trigger:**
Se ejecuta automáticamente.

No requiere ser llamado manualmente.

Puede mantener integridad de datos.

Se aplica a tablas o vistas.

Puede tener múltiples triggers por tabla.

### **11. Desventajas de un Trigger:**
Difícil de depurar.

Puede afectar el rendimiento.

Esconde lógica de negocio dentro de la base de datos.

Puede generar dependencias difíciles de mantener.

### **12. Sustituto de los Trigger en otras bases de datos:**
Procedimientos almacenados llamados desde la aplicación.

Middleware o lógica en backend (por ejemplo, en C#, Java, PHP).

Herramientas ETL o de integración que monitorean cambios en datos.

Funciones de Change Data Capture (CDC).

