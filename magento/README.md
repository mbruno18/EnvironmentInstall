### Contenedor de Docker para Magento

1) Generar la imagen de docker
````
docker build -t magento .
````

2) Ejecutar el contenedor
````
docker run -d --name magento magento
````

**Importante** que este contenedor siempre corra en la IP 172.17.0.3
El contenedor con modsecurity va a configurar un reverse proxy a esta IP

Se puede comprobar la correcta instalación ingresando a http://172.17.0.3/
