FROM teid/apache-modsecurity

MAINTAINER "PRGrado"

RUN apt-get update && apt-get install -y vim

RUN a2enmod proxy_http && a2enmod substitute.load

COPY proxy.conf /etc/apache2/mods-enabled

COPY modsecurity.conf /etc/modsecurity

#Exception rules
COPY RESPONSE-999-EXCLUSION-RULES-AFTER-CRS.conf /etc/modsecurity/crs

RUN cd /opt && mkdir modsecurity && cd /opt/modsecurity && mkdir var && cd /opt/modsecurity/var && mkdir audit       

RUN chmod 777 -R /opt/modsecurity/var/audit/

