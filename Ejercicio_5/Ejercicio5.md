# Ejercicio 5 - imagen con Dockerfile - Aplicación web

> Pelayo Álvarez Rodríguez 

Para la realización de este ejercicio es necesario tener una cuenta en Docker Hub.

Usuario: pelayoar79

- Arranca un contenedor que ejecute una instancia de la imagen php:7.4-apache , que se llame web y que sea accesible desde un navegador en el puerto 8000.

```bash
docker run -d --name web -p 8000:80 php:7.4-apache
```

​	<img src="./Ejercicio5.assets/image-20240227205250616.png" alt="image-20240227205250616"  />

- Coloca en el directorio raíz del servicio web ( /var/www/html ) un sitio web donde figure el nombre de los componentes del grupo - el sitio deberá tener al menos un archivo index.html y un archivo .css

​	Creo un directorio para almacenar el sitio web:

```bash
sudo mkdir -p /var/www/html/sitio_alba_y_pelayo
```

​	![image-20240227210402732](./Ejercicio5.assets/image-20240227210402732.png)

​	Acceder al repositorio:

```bash
docker exec web mkdir /var/www/html/sitio_alba_y_pelayo

```

​	![image-20240301090926043](./Ejercicio5.assets/image-20240301090926043.png)

​	Creacion de ficheros:

```bash
sudo nano index.html
```

index.html:

<img src="./Ejercicio5.assets/image-20240301085706155.png" alt="image-20240301085706155" style="zoom:80%;" />

```bash
sudo nano index.css
```

​	index.css:

<img src="./Ejercicio5.assets/image-20240301085744913.png" alt="image-20240301085744913" style="zoom:80%;" />

```bash
docker cp /home/cliente/Documentos/index.html web:/var/www/html/sitio_alba_y_pelayo/index.html
```

![image-20240301091009075](./Ejercicio5.assets/image-20240301091009075.png)

```bash
docker cp /home/cliente/Documentos/index.css web:/var/www/html/sitio_alba_y_pelayo/index.css
```

![image-20240301091031842](./Ejercicio5.assets/image-20240301091031842.png)

​	<img src="./Ejercicio5.assets/image-20240301091454566.png" alt="image-20240301091454566" style="zoom:80%;" />



- Coloca en ese mismo directorio raíz un archivo llamado `mes.php` que muestre el nombre del mes actual. Ver la salida del script en el navegador

```bash
docker cp /home/cliente/Documentos/mes.php web:/var/www/html/sitio_alba_y_pelayo/mes.php
```

![image-20240301092428265](./Ejercicio5.assets/image-20240301092428265.png)

mes.php:

<img src="./Ejercicio5.assets/image-20240301092114492.png" alt="image-20240301092114492" style="zoom:80%;" />

<img src="./Ejercicio5.assets/image-20240301092405620.png" alt="image-20240301092405620" style="zoom:80%;" />

- ​	Borrar el contenedor

```bash
docker stop web
docker rm web
```

![image-20240301092824037](./Ejercicio5.assets/image-20240301092824037.png)

- ​	Automatizar estas operaciones creando un fichero `Dockerfile`

![image-20240301095329339](./Ejercicio5.assets/image-20240301095329339.png)

Construir imagen Docker:

```bash
docker build -t web .
```

<img src="./Ejercicio5.assets/image-20240301095821557.png" alt="image-20240301095821557"  />

```bash
docker run -d --name web -p 8000:80 web
```

![image-20240301100038184](./Ejercicio5.assets/image-20240301100038184.png)

Comprobacion:

![image-20240301100158883](./Ejercicio5.assets/image-20240301100158883.png)

- ​	Subir la imagen a la cuenta de Docker Hub

```bash
docker login
docker tag web pelayoar79/web
docker push pelayoar79/web
```

![image-20240301101713673](./Ejercicio5.assets/image-20240301101713673.png)

![image-20240301102013850](./Ejercicio5.assets/image-20240301102013850.png)

<img src="./Ejercicio5.assets/image-20240301102040988.png" alt="image-20240301102040988" style="zoom:80%;" />

<img src="./Ejercicio5.assets/image-20240301102113034.png" alt="image-20240301102113034" style="zoom:80%;" />

Comprobación en buscador:

<img src="./Ejercicio5.assets/image-20240301102415540.png" alt="image-20240301102415540" style="zoom:80%;" />

<img src="./Ejercicio5.assets/image-20240301102440913.png" alt="image-20240301102440913" style="zoom:80%;" />



Descargo yo (Alba) de la imagen subida por Pelayo a DockerHub:

![image-20240301103247674](./Ejercicio5.assets/image-20240301103247674.png)

![image-20240301103435970](./Ejercicio5.assets/image-20240301103435970.png)

Acceso al navegador con el sitio servido

![image-20240301103640975](./Ejercicio5.assets/image-20240301103640975.png)