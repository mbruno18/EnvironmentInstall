### Contenedor de Docker para Modsecurity

1) Generar la imagen de docker
````
docker build -t modsecurity .
````

2) Configurar el archivo hosts
````
sudo vim /etc/hosts y agregar la siguiente linea
172.17.0.4 modsecurity-magento
````

3) Correr un contenedor
````
docker run -d --name modsecurity --hostname modsecurity-magento modsecurity
````

Para comprobar la correcta instalación ingresar a http://modsecurity-magento/
o directamente por IP http://172.17.0.4/

Para entrar al contendor
````
docker exec -it modsecurity /bin/bash
````

Para copiar los logs al host
````
docker cp modsecurity:/opt/modsecurity/var/audit logs
````
