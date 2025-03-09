# Db_Museos
# Creación de la Base de Datos Museo

```sql
# Crear la base de datos
CREATE DATABASE museo_db;
USE museo_db;

# Tabla de Tipos de Museo
CREATE TABLE cat_tipo (
    id_tipo INT PRIMARY KEY,
    tipo VARCHAR(100),
    estado BOOLEAN
);

# Tabla de Ubicación
CREATE TABLE tbl_ubicacion (
    id_ubicacion INT PRIMARY KEY,
    id_pais INT,
    ciudad VARCHAR(100),
    colonia VARCHAR(100),
    cp VARCHAR(10),
    calle VARCHAR(100),
    numero VARCHAR(10)
);

# Tabla de Países
CREATE TABLE cat_pais (
    id_pais INT PRIMARY KEY,
    codigo VARCHAR(10),
    pais VARCHAR(100),
    estado BOOLEAN
);

# Tabla de Entradas
CREATE TABLE tbl_entrada (
    id_entrada INT PRIMARY KEY,
    tipo VARCHAR(100),
    precio FLOAT
);

# Tabla de Museos
CREATE TABLE tbl_museo (
    id_museo INT PRIMARY KEY,
    id_tipo INT,
    id_entrada INT,
    nombre VARCHAR(100),
    id_ubicacion INT,
    id_categoria INT,
    FOREIGN KEY (id_tipo) REFERENCES cat_tipo(id_tipo),
    FOREIGN KEY (id_entrada) REFERENCES tbl_entrada(id_entrada),
    FOREIGN KEY (id_ubicacion) REFERENCES tbl_ubicacion(id_ubicacion)
);



