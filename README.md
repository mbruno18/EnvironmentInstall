# Instalación del ambiente Magento-Modsecurity
Estructura de directorios para la instalación del ambiente con Magento y ModSecurity mediante Dockerfile.

El objetivo es poder unificar pasos para la instalación y configuración de todo el ambiente utilizado en la aplicación práctica en el contexto del Proyecto de Grado.

Para la instalación se deben seguir los pasos indicados en los archivos README.md en los directorios mysql, megento y modsecurity (en ese orden) El orden es importante para forzar a que el contenedor MySql quede con la IP 172.17.0.2, Magento en 172.17.0.3 y Modsecurity en 172.17.0.4, ya que estas IP se utilizan en los dockerfile al hacer el build de algunas de las imágenes.
