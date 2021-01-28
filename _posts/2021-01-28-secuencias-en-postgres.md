---
layout: post
title: Secuencias en Postgres
date: 2021-01-28 11:55 -0300
tags:   [postgres, database]
categories: postgres, database
image: postgres.png
---


En este post aprenderemos sobre secuencias.

Una secuencia (sequence) se emplea para generar valores enteros secuenciales únicos y asignárselos a campos numéricos; se utilizan generalmente para las claves primarias de las tablas garantizando que sus valores no se repitan (normalmente utilizamos la definición de un campo serial, este tiene asociado una secuencia en forma automática).

Una secuencia es una tabla con un campo numérico en el cual se almacena un valor y cada vez que se consulta, se incrementa tal valor para la próxima consulta.

## Crear una secuencia
```pgsql
CREATE SEQUENCE table_id_seq
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;
```
## Función que nos retorna el próximo valor de la secuencia
```pgsql
SELECT nextval('table_id_seq');
```
## Modificar secuencia
```pgsql
ALTER SEQUENCE table_id_seq RESTART WITH 10;
```