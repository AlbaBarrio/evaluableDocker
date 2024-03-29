# Ejercicio 2 - Portainer

> Pelayo Álvarez Rodríguez 

[TOC] 

Utiliza una imagen de 'Portainer' para gestionar Docker.

```bash
docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```

![image-20240226214056869](./Ejercicio2.assets/image-20240226214056869.png)

Pruebo que funcione:

<img src="./Ejercicio2.assets/image-20240226214140159.png" alt="image-20240226214140159" style="zoom:80%;" />

## Actividad portainer

Documenta la aplicación, su puesta en funcionamiento y realiza capturas de varias operaciones,
por ejemplo:

- Muestra contenedores activos, para un contenedor, borra un contenedor

  Contenedores activos:

  <img src="./Ejercicio2.assets/image-20240226214723835.png" alt="image-20240226214723835" style="zoom:80%;" />

  Un contenedor:

  <img src="./Ejercicio2.assets/image-20240226215100107.png" alt="image-20240226215100107" style="zoom:80%;" />

​	Borrar un contenedor:

<img src="./Ejercicio2.assets/image-20240226215315489.png" alt="image-20240226215315489" style="zoom:80%;" />	<img src="./Ejercicio2.assets/image-20240226215349496.png" alt="image-20240226215349496" style="zoom:80%;" />

- Muestra alguna operación con redes Docker

  Muestro las redes:

  <img src="./Ejercicio2.assets/image-20240226215624236.png" alt="image-20240226215624236" style="zoom:80%;" />

  Muestro detalles de una red:

  <img src="./Ejercicio2.assets/image-20240226215803466.png" alt="image-20240226215803466" style="zoom:80%;" />

  Creo una red:

  <img src="./Ejercicio2.assets/image-20240226215940795.png" alt="image-20240226215940795" style="zoom:80%;" />

  <img src="./Ejercicio2.assets/image-20240227181116747.png" alt="image-20240227181116747" style="zoom:80%;" />

- Muestra alguna operación con volúmenes Docker

​	Listado de volúmenes:	<img src="./Ejercicio2.assets/image-20240227181314150.png" alt="image-20240227181314150" style="zoom:80%;" />	

​	Muestro detalles de un volumen: 

<img src="./Ejercicio2.assets/image-20240227181549184.png" alt="image-20240227181549184" style="zoom:80%;" />

​	Creo un volumen: 	<img src="./Ejercicio2.assets/image-20240227181818933.png" alt="image-20240227181818933" style="zoom:80%;" />

<img src="./Ejercicio2.assets/image-20240227181840833.png" alt="image-20240227181840833" style="zoom:80%;" />