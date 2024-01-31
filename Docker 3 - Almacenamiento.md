# Docker 3 - Bind Mount

> Hecho por Ángel Durántez y Adrián Vega

1. Crea un directorio en tu host y dentro crea un fichero index.html . 

   La carpeta la cree manualmente.

   ```bash
   $nano index.html
   ```

   ![image-20240131110215899](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240131110215899.png)

2.  Crea un contenedor desde la imagen php:7.4-apache donde montes en el directorio /var/www/html el directorio que has creado por medio de bind mount . 

   ```
   $docker run -d -d 8080:80 -v carpetadocker:/var/www/html --name dockerphp php:7.4-apache
   ```

   ![image-20240131110922407](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240131110922407.png)

3.  Accede al contenedor desde el navegador para ver la información ofrecida por el fichero index.html . 

4. Modifica el contenido del fichero index.html en tu host y comprueba que al refrescar la página ofrecida por el contenedor, el contenido ha cambiado. 

5. Borra el contenedor 

6. Crea un nuevo contenedor y monta el mismo directorio como en el ejercicio anterior. 

7. Accede al contenedor desde el navegador para ver la información ofrecida por el fichero index.html . ¿Se sigue viendo el mismo contenido?