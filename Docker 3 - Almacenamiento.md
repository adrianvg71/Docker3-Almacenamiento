# Docker 3 - Almacenamiento

> Realizado por Adrián Vega González y Ángel Durantez Garcia

1. Crea un volumen docker que se llame miweb .

![image-20240131104011058](C:\Users\alumno\AppData\Roaming\Typora\typora-user-images\image-20240131104011058.png)

2. Crea un contenedor desde la imagen php:7.4-apache donde montes en el directorio /var/www/html (que sabemos que es el DocumentRoot del servidor que nos ofrece esa imagen) el volumen docker que has creado

![image-20240131104211949](C:\Users\alumno\AppData\Roaming\Typora\typora-user-images\image-20240131104211949.png)

3. Utiliza el comando docker cp para copiar un fichero index.html en el directorio /var/www/html .

![image-20240131104520253](C:\Users\alumno\AppData\Roaming\Typora\typora-user-images\image-20240131104520253.png)

4. Accede al contenedor desde el navegador para ver la información ofrecida por el fichero index.html 

![image-20240131105921916](C:\Users\alumno\OneDrive - Consejería de Educación\2- DAW\Despligue\Docker 3 - Almacenamiento.assets\image-20240131105921916.png)

5. Borra el contenedor

![image-20240131110001164](C:\Users\alumno\OneDrive - Consejería de Educación\2- DAW\Despligue\Docker 3 - Almacenamiento.assets\image-20240131110001164.png)

6. Crea un nuevo contenedor y monta el mismo volumen como en el ejercicio anterior.

![image-20240131110032612](C:\Users\alumno\OneDrive - Consejería de Educación\2- DAW\Despligue\Docker 3 - Almacenamiento.assets\image-20240131110032612.png)

7. Accede al contenedor desde el navegador para ver la información ofrecida por el fichero index.html . ¿Seguía existiendo ese fichero?

![image-20240131110245204](C:\Users\alumno\OneDrive - Consejería de Educación\2- DAW\Despligue\Docker 3 - Almacenamiento.assets\image-20240131110245204.png)

`Si, el fichero sigue existiendo a pesar de haber borrado el contenedor`
# Docker 3 - Bind Mount

> Hecho por Ángel Durántez,  Adrián Vega y Sergio Álvarez

1. Crea un directorio en tu host y dentro crea un fichero index.html . 

   La carpeta la cree manualmente.

   ```bash
   $nano index.html
   ```

   ![image-20240131110215899](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240131110215899.png)

2. Crea un contenedor desde la imagen php:7.4-apache donde montes en el directorio /var/www/html el directorio que has creado por medio de bind mount . 

   ```bash
   $docker run -d -p 8080:80 -v carpetadocker:/var/www/html --name dockerphp php:7.4-apache
   ```

   ![image-20240131110922407](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240131110922407.png)

3. Accede al contenedor desde el navegador para ver la información ofrecida por el fichero index.html . 

   ![imagen](C:\Users\Angel\Downloads\imagen.png)

4. Modifica el contenido del fichero index.html en tu host y comprueba que al refrescar la página ofrecida por el contenedor, el contenido ha cambiado. 

   ![imagen (1)](C:\Users\Angel\Downloads\imagen (1).png)

   ```bash
   $nano index.html
   $docker restart dockerphp
   ```

   ![imagen (2)](C:\Users\Angel\Downloads\imagen (2).png)

   ![imagen (3)](C:\Users\Angel\Downloads\imagen (3).png)

5. Borra el contenedor 

   ```bash
   $docker stop dockerphp
   $docker rm dockerphp
   ```

   ![imagen (5)](C:\Users\Angel\Downloads\imagen (5).png)

6. Crea un nuevo contenedor y monta el mismo directorio como en el ejercicio anterior. 

   ```bash
   $docker run -d -p 8080:80 -v carpetadocker:/var/www/html --name dockerphp php:7.4-apache 
   ```

   ![imagen (6)](C:\Users\Angel\Downloads\imagen (6).png)

7. Accede al contenedor desde el navegador para ver la información ofrecida por el fichero index.html . ¿Se sigue viendo el mismo contenido?

   ![imagen (7)](C:\Users\Angel\Downloads\imagen (7).png)