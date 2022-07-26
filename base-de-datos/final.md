# Preguntas

## Vanina

Todo salvo la parte de arquitecturas de datos y data warehousing.

1. ¿Qué implica un proceso de normalización de una base de datos y por que es importante?
2. ¿cómo funcionan los mecanismos de control de concurrencia X e Y? ¿Qué ventajas tiene cada uno sobre el otro?
3. ¿Puede el equipo de IT, en particular el DBA, encargarse de la definición de estrategia de gobernanza de los datos? ¿por qué no o por qué si?
4. ¿Qué implica tener una estrategia de gobernanza?
5. Definiciones:
  * normalidad
  * dependencias funcionales
  * llaves
  * formas normales
  * transacciones
  * historias
  * seriabilidad
  * anomalías producto de la concurrencia
  * bases de datos distribuidas
  * protocolos, etc.

## Base de datos

6. Diferencia entre administrador de datos y DBA. Relacionar con concepto de independencia física y transparencia.
7. ¿Qué es fragmentación mixta? Dar un ejemplo, con una query en álgebra relacional para reconstruir las tablas originales
8. ¿Cuáles son las dos formas de interrelación de datos? (creo que era integración e intercambio).
9. Dar 2 heuristicas que use el optimizador de consultas. Ejemplifique.
10. Explicar independencia física.


## Formas normales

11. Definir superclave, clave candidata y clave primaria.y dependencia funcional. ¿Cúando es que un esquema está en 3FN?
12. ¿Qué son las propiedades BASE? ¿Qué relación tienen con las ACID?
13. ¿Qué es el proceso de normalización y para qué sirve? ¿Cómo está relacionado con la calidad de un diseño de bases de datos?
14. ¿Qué es una dependencia funcional? Dado el esquema R = {idMascota, nombreMascota, vacuna, fecha, idDueño} y
15. TU conocimiento del dominio (o sea, asumí lo que tu querai), proponé dependencias funcionales para la misma.
16. ¿En qué forma normal está el esquema? Proponé una descomposición que mejore el diseño.
17. ¿Para que sirve la normalización de una BD? Relacionarlo con la calidad de datos.
18. ¿Qué incovenientes trae una BD desnormalizada? ¿Cómo ayuda la normalización? Ejemplifique.
19. Dar un esquema que esté en 2FN pero no en 3FN. Dar una descomposición del mismo en 3FN.
20. ¿Cuáles son los objetivos de la normalización? Relacionar con la calidad de diseño.
Se tienen los siguientes esquemas
  * E = {IDEstudiante, nombreEstudiante, IDDepartamento, fechaInscripción}
  * D = {IDDepartamento, nombreDepartamento, Facultad}
  * a) Dar las dependencias funcionales que reflejen: i) un estudiante se pudo inscribir a más de un departamento pero no en la misma fecha ii) cada departamento pertenece solo a una facultad.
  * b) Suponga una base de datos distribuida de 3 nodos donde N1 tiene a E, N2 tiene a D y en N3 se dispara la consulta "ID de los estudiantes que pertenecen a un departamento de 'FCEyN' junto con el nombre de su Facultad". Asumir que E tiene 10.000 registros de 30B cada uno, D tiene 100 registros de 20B cada uno y el 30% de los estudiantes pertenecen a 'FCEyN'.
21. Definir dependencia funcional. ¿Para qué sirve que la normalización? ¿Cómo esta relacionado con la calidad de un diseño de bases de datos? ¿Qué problemas puede presentar una base desnormalizada? Ejemplifique

## AR y CRT

22. Dar dos propiedades del álgebra relacional que se puedan usar para optimizar consultas y ejemplificar.
23. Explicar fragmentación. Explicar cómo se recupera la tabla original con álgebra relacional.
24. Dar dos ejemplos de optimizaciones algebraicas. Ejemplificar.
25. Expresar en álgebra relacional la consulta: “devolver id de estudiante y nombre de la facultad para los estudiantes que hayan nacido despues de 1980”

Tenés 2 relaciones E = {idEstudiante, nombreEstudiante, idFacultad, fechaInscripción} y F = {idFacultad, nombreFacultad}.
Los registros de E miden 30 B, y hay 10.000 de ellos. Los registros de F miden 20 B y hay 500 de ellos. Hay 3 nodos N1, N2 y N3.
N1 tiene a E, N2 tiene a F, y N3 hace la query 'Devolver id de estudiante y nombre de la facultad de los estudiantes que se inscribieron después de 1980'.

i) ¿Que agregarías a la BD para capturar la siguiente situación: 'un estudiante puede inscribirse a varias facultades, pero en fechas distintas'?
ii) Escribir la query en AR y en CR
iii) Describir una estrategia de resolución de la query, junto con cuantos bytes son transferidos. Reemplace por variables las cantidades desconocidas (con eso se refiere a que no sabés cuantos estudiantes se inscribieron después de 1980, y que tendrías que reemplazar dicha cantidad por una variable).

Supongamos que hay 4 facultades f1, f2, f3 y f4; y 4 nodos correspondientes N1, N2, N3 y N4. Se quiere fragmentar la información de E y F del anterior punto, para que tanto la información de las facultades, como la de estudiantes esten solo en el nodo de su facultad correspondiente.

i) Definir qué queries en AR hacen falta para definir la fragmentación, y definir un esquema de asignación para obtener lo requerido.
ii) Decir qué tipo de fragmentación se usó en el anterior punto. ¿Cómo obtendría las relaciones originales luego de la fragmentación?

## NOSQL

26. ¿Qué diferencia hay entre bases distribuídas de sistio primario y de copia primaria? Dar ventajas y desventajas de ambas.
27. Explicar bases NoSQL por documentos, explicando el concepto de documento. Mostrar cómo sería una base por documentos para el ejercicio anterior (no sé si había que hacer el DID, poner los jsons o ambos).
28. Qué es un DID? Dar un ejemplo de un sistema de base de datos por documentos.

## Concurrencia y  recuperabilidad

29. ¿Que significa que un conjunto de transacciones (historia?) sea serializable? Relacionarlo con una propiedad ACID.
30. ¿Qué es una transacción? ¿Qué significa que una transacción lea de otra? Definir dirty read y dar ejemplo.
31. ¿Qué es una historia y cuándo dos historias son equivalentes en conflicto?
32. ¿Qué es una transacción? Describir las propiedades ACID.
33. Definir transacciones y dar y explicar las propiedades ACID.

## ?

34. Qué es una base de datos distribuida. Describir el protocolo 3FN.
35. ¿Qué es gobierno de datos? Diferencias entre datos, información y conocimiento.
36. Defina bases de datos distribuida. ¿Qué nuevos niveles de transparencia aparecen junto a estas bases?
37. ¿Qué es Data Mining? Describir las distintas técnicas.
38. ¿Qué es la interoperabilidad de datos? Describir los dos enfoques que se mencionan en la bibliografía.
39. Dar dos estrategias de ejecución para esa query junto con la cantidad de datos que deben transmitirse en cada caso. ¿Cuál es la mejor en términos de transferencia de datos?



