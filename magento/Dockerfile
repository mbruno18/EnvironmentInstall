FROM magento/magento2devbox-web

MAINTAINER "PRGrado"

USER magento2
RUN cd /home/magento2/ && mkdir .composer

USER magento2
COPY auth.json /home/magento2/.composer

USER magento2
RUN cd /var/www/magento2 && composer create-project --repository=https://repo.magento.com/ magento/project-community-edition:2.2.0 . && chmod +x bin/magento

USER magento2
RUN magento setup:install --base-url=http://172.17.0.3/ --db-host=172.17.0.2 --db-name=magento --db-user=root --db-password=password --admin-firstname=Marcelo --admin-lastname=Bruno --admin-email=marcelobruno218@gmail.com --admin-user=admin --admin-password=SaPe19!! --language=en_US --currency=USD --timezone=America/Chicago --use-rewrites=1

USER magento2
COPY auth.json /var/www/magento2/var/composer_home/

USER magento2
RUN magento sampledata:deploy

USER magento2
RUN magento setup:upgrade
 
USER root
