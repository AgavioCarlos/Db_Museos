# Consultas 
```sql
# Cantidad de museos por país
SELECT p.pais, COUNT(m.id_museo) AS cantidad_museos 
FROM tbl_museo m
JOIN tbl_ubicacion u ON m.id_ubicacion = u.id_ubicacion
JOIN cat_pais p ON u.id_pais = p.id_pais
GROUP BY p.pais;

#Listar los museos con su tipo y precio de entrada
SELECT m.nombre, t.tipo, e.precio 
FROM tbl_museo m
JOIN cat_tipo t ON m.id_tipo = t.id_tipo
JOIN tbl_entrada e ON m.id_entrada = e.id_entrada;

#. Mostrar los museos ubicados en una ciudad específica
SELECT nombre 
FROM tbl_museo m
JOIN tbl_ubicacion u ON m.id_ubicacion = u.id_ubicacion
WHERE u.ciudad = 'Madrid';

#Museo con la entrada más costosa
SELECT m.nombre, e.precio 
FROM tbl_museo m
JOIN tbl_entrada e ON m.id_entrada = e.id_entrada
ORDER BY e.precio DESC LIMIT 1;

#Cuántos museos tienen entradas con precio menor a 10
SELECT COUNT(*) AS museos_baratos 
FROM tbl_museo m
JOIN tbl_entrada e ON m.id_entrada = e.id_entrada
WHERE e.precio < 10;


