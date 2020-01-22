# EnvironmentInstall
Repo para la instalacion del ambiente mediante docker file

La idea de este repo es poder unificar pasos para la instalación y configuración de todo el ambiente de magente, 
con su base de datos MySql y el reverse proxy con modsecurity.

Para esto se deben seguir los pasos indicados en los archivos README en los directorios mysql, megento y modsecurity 
(nen ese orden) El orden es importante para forzar a que el contenedor MySql quede con la IP 172.17.0.2, magento en 172.17.0.3 y 
modsecurity en 172.17.0.4, ya que estas IP se utilizan en los dockerfile al hacer el build de algunas de las imñagenes
