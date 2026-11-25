
FROM php:8.3-apache

# Installation de l'extension MySQL
RUN docker-php-ext-install mysqli

# Activation de la reecriture des URL
RUN a2enmod rewrite

# Installation de WordPress
RUN curl -fsSL https://wordpress.org/latest.tar.gz \
    | tar -xz --strip-components=1 -C /var/www/html \
    && chown -R www-data:www-data /var/www/html

EXPOSE 80

