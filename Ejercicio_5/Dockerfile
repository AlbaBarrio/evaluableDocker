# Usa la imagen base de PHP con Apache
FROM php:7.4-apache

# Crea un directorio para tu sitio dentro de /var/www/html
RUN mkdir /var/www/html/sitio_alba_y_pelayo

# Copia los archivos del directorio actual al directorio del contenedor
COPY index.html /var/www/html/sitio_alba_y_pelayo/ 
COPY styles.css /var/www/html/sitio_alba_y_pelayo/ 
COPY mes.php /var/www/html/sitio_alba_y_pelayo/

# Opcional: Exponer el puerto 8000 para acceder al servidor Apache
EXPOSE 8000
