# consulta_1_sql
# Introducción a las consultas en una base de datos en sql

## Base de datos: Ventas
## Tabla: Cliente

![Tabla Cliente](tabla_cliente.png "Tabla Cliente")

## Instruccion SELECT
- Permite seleccionar datos de una tabla.
- Su formato es: `SELECT campos_tabla FROM nombre_tabla``

### CONSULTA No. 1
1. Para visualizar toda la informacion que contiene la tabla Cliente se puede incluir con la instruccion SELECT el caracter **\*** o cada uno de los campos de la tabla.

- `SELECT * FROM Cliente`
![Tabla Cliente](cliente1_1.png "Tabla consulta1_2")
- `SELECT identificacion, nombre, apellidos,direccion, telefono, ciudad_nac, fecha_nac FROM Cliente`
![Tabla Cliente](consulta1_2.png "Tabla consulta 2")

### Consulta No. 2

2. Para visualizar solamente la identificacion del Cliente: `SELECT identificacion FROM Cliente`
![Tabla Cliente](consulta2.png "Tabla consulta 2")

### Consulta No. 3

3. Si se desea obtener los registros cuya identificacion sea mayor o igual a 150, se debe utilizar la clausula `WHERE` que especifica las condiciones que deben reunir los registros que se van a seleccionar: `SELECT * FROM Cliente WHERE Indetificación>=150
![Tabla Cliente](consulta3.png "Tabla consulta 3")


### Consulta No. 4 

4. Se desea obtener los registros cuyos apellidos sean Vanegas o Cetina, se debe utilizar el operador `IN` que especifica los registros que se quieren visualizar de una tabla.

`SELECT apellido,  FROM Cliente WHERE apellido IN('Vanegas', 'Cetina')`
![Tabla Cliente](consulta4_1.png "Tabla consulta 4_1")


o se puede utilizar el operador `OR`

`SELECT apellido,Nombre FROM Cliente WHERE apellido = 'Vanegas' OR apellido = 'Cetina'` 
![Tabla Cliente](consulta4.png "Tabla consulta 4_2")

### Consulta No.5

5. Se desea obtener los registros cuya identificacion sea menor de 110 y la ciudad sea Cali, se debe utilizar el operador `AND`

SELECT * FROM Cliente WHERE identificion<=110 AND ciudad = 'Cali'

![Consulta](consulta5.png "consulta 5")


### Consulta No. 6

6. Si se desea obtener los registros cuyos nombres empiezen con las letra A, se debe utilizar el operador `LIKE` que utiliza los patrones `%`(todos) y `_`(caracter).

SELECT * FROM Cliente WHERE Nombre LIKE 'A%'
![Consulta](consulta6.png "consulta 6")

### Consulta No. 7

7. Se desea obtener los registros cuyos nombres contengan la letra 'a'

SELECT * FROM Cliente WHER Nombre LIKE '%a%'

![Consulta](CONSULTA7.png "consulta 7")

### Consulta No.8

8. Se desea obtener los registros donde la cuarta letra del nombre del cliente sea 'a'

SELECT * FROM Cliente WHERE Nombre LIKE '____a'

![Consulta](consulta8.png "consulta 8")

### Consulta No 9

9. Si se desea obtener los registros cuya identificacion este entre 110 y 150, se debe utilizar la clausula BETWEEN, que sirve para especificar un intervalo de valores.

SELECT * FROM Cliente WHERE Indetificacion BETWEEN 110 AND 150

![Consulta](consulta9.png "consulta 9")

### Instruccion DELETE
-Permite borrar todos o un grupo especifico de registros de una tabla.
-Su formato es DELETE FROM Nombre-tabla

### Eliminacion No.1

1. Eliminar los registros cuya identificacion sea mayor a 160

DELETE FROM Cliente WHERE >160
![Consulta](consulta10.png "consulta 10")

2. Eliminar los registros cuya identificacion sea igual a 116

DELETE FROM Cliente WHERE identificacion = 116

### Instruccion UPDATE
-Permite actualizar un campo de una tabla.
-Su formato es UPDATE Nombre-tabla SET nombre_campo = valor

### Actualizacion No.1 

1. Para actualizar la ciudad de nacimiento de Cristian Vanegas, cuya Identificacion es 114

UPDATE usuario SET ciuda_nac = 'Pereira' WHERE Identidific='114'

![Actualizacion](consulta11.png "Actualizacion_1")

## Creacion Tabla Pedido

### Diccionario de datos
|Campo|Tipo de dato|Longitud|
|-----|------------|--------|
|***No_pedido**|varchar|15|
|iden_cliente|varchar|15|
|fecha_compra|date||
|fecha_vencimiento|date||
|observacion|varchar|30|

### Modelo Entidad - Relacion

![Modelo](modelo.png "Modelo")

### Tabla: pedido

![pedido](tabla_pedido.png "pedido")

## OPERADOR INNER JOIN
-Permite obtener datos de dos o mas tablas.
- Cuando se realiza la concatenacion de las tablas, no necesariamente se debe mostrar todos los datos de la tabla
- su formato es:
SELECT tabla1.campo, tabla2.campo,... FROM tabla_principal INNER JPOIN tabla_secundaria ON campo_comun_tabla1 = campo_comun_tabla2

1. Para visualizar los campos identificacion, nombre, apellidos de la tabla cliente y no_pedido, fecha_compra, fecha_vencimiento y observacion de la tabla pedido, se debe realizar la siguiente instruccion: 

SELECT Cliente.identificacion, Cliente.nombre, Cliente.Apellidos, pedido.no_pedido, pedido.fecha_compra, pedido.fecha_vencimiento, pedido.observacion FROM Cliente INNER JOIN pedido ON Cliente.identificacion = pedido.iden_cliente

![pedido](innerjoin1.png "pedido")

2. Para visualizar todos los campos de las tablas Cliente y Pedido donde identificacion sea mayor que 100, se debe realizar la siguiente instruccion:

SELECT Cliente.*, Pedido.*FROM Cliente INNER JOIN Pedido ON Cliente.Indetificación = Pedido.iden_cliente WHERE Cliente.Indetificación>100;

![INNERJOIN](ONNERJOIN2.png "INNERJOIN")


