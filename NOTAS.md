# NOTAS

### Pregunta: ¿Por qué usamos LEFT JOIN en lugar de INNER JOIN? ¿Qué filas se perderían con INNER JOIN?

> "INNER JOIN" Excluiria completamente el resultado mietras que el "LEFT JOIN" todavía mostrará esas películas, pero con NULL en los campos del director o género

### Pregunta: ¿Qué películas tienen usuarios más entusiastas que la crítica? ¿Y al revés?

> The Dark Knight, Roma | Menos -> Barbie, Blade Runner 2049

### Pregunta: ¿Qué directores tienen una trayectoria ascendente (cada película mejor que la anterior)?

> Si esta ordenado por Director y sus pelis en ordende Desendente de año ariba abajo

### ¿Cuándo es contraproducente crear un índice? (pista: piensa en tablas con muchas escrituras)

> Aunque los índices aceleran las consultas (SELECT), son un lastre en tablas con muchas escrituras (INSERT, UPDATE, DELETE).

* Sobrecarga en cada escritura: Cada vez que insertas o modificas una fila, la base de datos tiene que actualizar también el índice. Si tienes muchos índices, la base de datos se vuelve lenta.

* Espacio en disco: Los índices ocupan espacio extra. En tablas gigantes, esto puede ser un problema de almacenamiento.

* Baja cardinalidad: No sirve de nada crear un índice en una columna que solo tiene dos valores (ej. "Activo/Inactivo").

### ¿Qué diferencia hay entre RANK() y DENSE_RANK()? Pon un ejemplo con los datos de la base de datos.
> Ambos sirven para numerar filas según un orden, pero gestionan los empates de forma distinta:

* RANK(): Si hay un empate, deja un hueco en la numeración.

* DENSE_RANK(): Si hay un empate, no deja huecos; el siguiente número es el consecutivo.

### ¿Por qué el trigger usa AFTER INSERT OR UPDATE OR DELETE en lugar de BEFORE?

> Ambos sirven para numerar filas según un orden, pero gestionan los empates de forma distinta:

* RANK(): Si hay un empate, deja un hueco en la numeración.

* DENSE_RANK(): Si hay un empate, no deja huecos; el siguiente número es el consecutivo.