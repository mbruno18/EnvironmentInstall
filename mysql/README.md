Muchos de los pasos fueron tomados de tomados de
https://platzi.com/tutoriales/1432-docker/3268-como-crear-un-contenedor-con-docker-mysql-y-persistir-la-informacion/

1) Generar la imagen de docker
````
docker build -t mysql-magento .
````


2) Asegurarse que no existan volumenes creados con el nombre
````
docker volume ls
docker volume rm mysql-magento-data
docker volume prune
````

3) Crear el volumen de datos
````
docker volume create mysql-magento-data
````

4) Ejecutar el contenedor
````
docker run -d -p 33060:3306 --name mysql -e MYSQL_ROOT_PASSWORD=password --mount src=mysql-magento-data,dst=/var/lib/mysql mysql-magento
````

5) Entrar al contenedor creado y crear el esquema para la base de datos
````
docker exec -it mysql mysql -p password
create database magento;
````

**Importante** que este contenedor siempre corra en la IP 172.17.0.2, magento precisa esta direcccion para conectarse e instalarse

Si es necesario ingresar al contenedor ejecutar
````
docker exec --user=root -it mysql /bin/bash
````
