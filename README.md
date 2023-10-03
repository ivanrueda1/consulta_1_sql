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
