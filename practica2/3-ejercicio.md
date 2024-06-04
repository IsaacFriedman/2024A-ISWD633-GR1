### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:11.21-alpine3.17
```
docker run -d --name postgres -e POSTGRES_PASSWORD=123456 postgres:11.21-alpine3.17
```

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4
```
docker run -d --name pgadmin -e PGADMIN_DEFAULT_EMAIL=admin@mail.com -e PGADMIN_DEFAULT_PASSWORD=admin -p 8080:80 dpage/pgadmin4
```
La figura presenta el esquema creado en donde los puertos son:
- a: 8080
- b: 80
- c: 5432

![Imagen](imagenes/esquema-ejercicio3.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
![Imagen](imagenes/cap9-login.png)

### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.

## Desde el servidor postgres
### Acceder al servidor
![Imagen](imagenes/cap10.png)
### Conectarse a la base de datos info
```
\c info
```
### Realizar un select *from personas
![Imagen](imagenes/cap11.png)
