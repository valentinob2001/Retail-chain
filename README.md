# Retail-chain
Practica M5 UNION y UNION ALL

¿Cuántas filas devuelve cada consulta y por qué son distintas? Explicá con ejemplos concretos de los datos qué filas se eliminaron con UNION.
La consulta con UNION devuelve 10 filas y la consulta con UNION ALL 14. Las filas que se eliminan con UNION al seleccionar las columnas nombre_producto y categoría por ser duplicadas son las contienen el valor 'Monitor 4K 27"', 'SSD Externo 1TB', 'Teclado Mecánico' y 'Webcam HD 1080p'. Es decir, UNION elimina 4 filas del total que es 14.

¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?
La diferencia yace en que UNION ALL apila todas las filas de las tablas unidas sin ninguna distinción, mientras que UNION elimina duplicados siempre y cuando las filas contengan los mismos valores en cada columna seleccionada.

¿En qué casos de negocio usarías cada uno? Dá al menos dos ejemplos reales distintos a los del ejercicio.
El primer ejemplo que se me ocurre sería con una base de datos de un hospital con varias sedes y puntualmente con tablas de pacientes. Podríamos pensar que UNION ALL sería útil a la hora de analizar los registros de visitas de pacientes de todas las sedes, al contrario que UNION que se adaptaría en mayor medida a una consulta relacionada con los pacientes totales activos que posee la institución sin diferenciar sucursales al eliminar duplicados.
A su vez, otro caso posible puede ser el de la base de datos de una empresa gasolinera que maneja estaciones de servicio. Si tendríamos varias tablas de empleados, UNION nos serviría para comprobar el número o los datos de los empleados diferencias que tiene la empresa en total, a la par que UNION ALL se ajustaría a una consulta relacionada con los empleados que trabajan en cada sucursal, suponiendo que hay rotación entre sucursales y un mismo empleado podría trabajar en un sitio y después en otro.


¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?
