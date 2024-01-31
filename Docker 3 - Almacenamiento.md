# Docker 3 - Almacenamiento

> Realizado por Adrián Vega González y Ángel Durantez Garcia

1. Crea un volumen docker que se llame miweb .

![image-20240131104011058](.\Docker 3 - Almacenamiento.assets\image-20240131104011058.png)

2. Crea un contenedor desde la imagen php:7.4-apache donde montes en el directorio /var/www/html (que sabemos que es el DocumentRoot del servidor que nos ofrece esa imagen) el volumen docker que has creado

![image-20240131104211949](.\Docker 3 - Almacenamiento.assets\image-20240131104211949.png)

3. Utiliza el comando docker cp para copiar un fichero index.html en el directorio /var/www/html .

![image-20240131104520253](.\Docker 3 - Almacenamiento.assets\image-20240131104520253.png)

4. Accede al contenedor desde el navegador para ver la información ofrecida por el fichero index.html 

![image-20240131105921916](.\Docker 3 - Almacenamiento.assets\image-20240131105921916.png)

5. Borra el contenedor

![image-20240131110001164](.\Docker 3 - Almacenamiento.assets\image-20240131110001164.png)

6. Crea un nuevo contenedor y monta el mismo volumen como en el ejercicio anterior.

![image-20240131110032612](.\Docker 3 - Almacenamiento.assets\image-20240131110032612.png)

7. Accede al contenedor desde el navegador para ver la información ofrecida por el fichero index.html . ¿Seguía existiendo ese fichero?

![image-20240131110245204](.\Docker 3 - Almacenamiento.assets\image-20240131110245204.png)

`Si, el fichero sigue existiendo a pesar de haber borrado el contenedor`