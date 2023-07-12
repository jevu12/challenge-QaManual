De la base de datos de clientes, generar una consulta que permita
visualizar las edades de las personas naturales y la fecha de creación
de las personas jurídicas.

```sql
SELECT
    CASE
        WHEN tipo_persona = 'Natural' THEN TIMESTAMPDIFF(YEAR, fecha_nacimiento, CURDATE())
        WHEN tipo_persona = 'Jurídica' THEN fecha_creacion
        END AS edad_o_fecha
FROM clientes;
```
