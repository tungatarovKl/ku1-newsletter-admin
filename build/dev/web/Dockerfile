FROM php:8.1-apache
WORKDIR /usr/src/newsletter
# Configure Apache to serve project folder
ENV APACHE_DOCUMENT_ROOT /usr/src/newsletter/public
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
RUN a2enmod rewrite
# Remove unnecessary logs
RUN rm /var/log/apache2/access.log
#Install driver for mysql
RUN docker-php-ext-install pdo pdo_mysql
