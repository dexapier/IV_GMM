# Ejercicios 7:
### Almacenar objetos y ver la forma de almacenar directorios completos usando ceph y rados. 

Para almacenar los objetos en **rados** lo primero que deberemos es crear una piscina (`sudo rados mkpool prueba-piscina`) y comprobar que se ha creado (`rados lspools`):

![eje06_img01](imagenes/eje06_img01.png)

Como todavía no hemos almacenado nada en la piscina, podemos ver que su contenido es vacío (`sudo rados df`):

![eje06_img02](imagenes/eje06_img02.png)

Ahora introducimos cualquier archivo que tengamos en nuestro sistema (ejemplo: `sudo rados put -p prueba-piscina objeto archivo.img`). Ahora vemos que el tamaño ocupado de nuestra piscina ha aumentado (`sudo rados df`) y listando el contenido de la piscina, aparece el archivo que hemos almacenado (`sudo rados ls -p prueba-piscina`):

![eje06_img03](imagenes/eje06_img03.png)

Para almacenar ficheros seguramente esté relacionado con los metadatos y mapear llaves a valores, pero...