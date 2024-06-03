# VOLUMEN TIPO HOST
Un volumen host (o bind mount) es un tipo de volumen donde se monta un directorio o archivo específico del sistema de archivos del host en un contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```

### Crear un volumen tipo host con la imagen nginx:alpine, para la ruta carpeta host: directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html esta ruta se obtiene al revisar la se obtiene desde la documentación

![Volúmenes](imagenes/volumen-host.PNG)
```
docker run -d -v C:\Users\DELL3\Desktop\Html:/usr/share/nginx/html -p 8080:80 --name mi-nginx nginx:alpine
```

### ¿Qué sucede al ingresar al servidor de nginx?
Un error 403 en nginx generalmente significa que el servidor web no tiene permisos para acceder a los archivos en la carpeta especificada.

### ¿Qué pasa con el archivo index.html del contenedor?
Al inicio no habia archivo, por lo que arrojaba el error 403, al agregar un "index.html", ya lo reconoce y lo presenta normalmente

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de nginx/html
### ¿Qué sucede al ingresar al servidor de nginx?
Se visualiza el template anteriormente descargado, al ya tener un "index.html" no sucede el error anteriormente mencionado

### Eliminar el contenedor
```
docker rm mi-nginx
```

### ¿Qué sucede al crear nuevamente el mismo contenedor con volumen de tipo host a los directorios definidos anteriormente?
Sigue estando intacto el contenedor y su contenido ya que dentro de la carpeta en donde están los archivos no se realizó cambios, al volverlo a crear lo referencio

### ¿Qué hace el comando pwd?
El comando pwd (print working directory) se utiliza en sistemas como Linux para mostrar la ruta completa del directorio de trabajo actual en la línea de comandos.

Si quieres incluir el comando pwd dentro de un comando de Docker, lo puedes hacer de diferentes maneras dependiendo del shell que estés utilizando.


### Volumen tipo host usando PWD y PowerShell
```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v ${PWD}/<ruta relativa>:<ruta absoluta> <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (Git Bash)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd -W)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (en Linux)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

