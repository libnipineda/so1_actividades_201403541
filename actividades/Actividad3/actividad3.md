# Actividad 3

## Descripcion de la actividad
* **Objetivo** - Familiarizar a los estudiantes con la administración de usuarios, grupos y permisos en un sistema operativo Linux.
* **Requisito previo** - Tener instalado un sistema Linux y acceso al terminal.

Crear un md file y resolver cada uno de los items solicitados a continución. Debe de colocar el comando utilizado asi como el resultado de este si es necesario. 

**1. Gestion de usuarios**
---
    _1. Creacion de Usuarios_ Crear tres usuarios siendo esos 'usuario1', 'usuario2' y 'usuario3'.
    _2. Asignacion de contraseñas_ Asignar una contraseña a cada uno de los usuarios creados.
    _3. Informacion de usuarios_ Mostrar la información de usuario1 usando el comando 'id'.
    _4. Eliminacion de usuarios_ Eliminar el usuario3, pero conservar su directorio principal.

**2. Gestion de grupos**
---
    _1. Creacion de Grupos_ Crear dos grupos llamados 'grupo1' y 'grupo2'.
    _2. Agregar Usuarios a Grupos_ Agregar 'usuario1' a 'grupo1' y 'usuario2' a 'grupo2'.
    _3. Verificar Membresia_ Verificar que los usuarios han sido agregados a los grupos utilizando el comando 'groups'.
    _4. Eliminar Grupos_ Eliminar 'grupo2'.

**3. Gestion de permisos**
---
    _1. Creacion de Archivos y Directorios_
        * Como 'usuario1', crea un archivo llamado 'archivo1.txt' en su directorio principal y escribe algo en él.

        * Crea un directorio llamado 'directorio1' y dentro de ese directorio, un archivo llamado 'archivo2.txt'.

    _2. Verificar permisos_ Verifica los permisos del archivo y directorio usando el comando `ls -l` y `ls -ld` respectivamente.

    _3. Modificar Permisos usando 'CHMOD' con modo numerico_ Cambia los permisos del `archivo1.txt` para que sólo `usuario1` pueda leer y escribir (permisos `rw-`), el grupo pueda leer (permisos `r--`) y nadie más pueda hacer nada.

    _4. Modificar permisos usando 'CHMOD' con modo simbolico_ Agrega permiso de ejecución al propietario del `archivo2.txt`.

    _5. Cambiar el grupo propietario_ Cambia el grupo propietario de `archivo2.txt` a `grupo1`. 

    _6. Configurar permisos de directorio_ Cambia los permisos del `directorio1` para que sólo el propietario pueda entrar (permisos `rwx`), el grupo pueda listar contenidos pero no entrar (permisos `r--`), y otros no puedan hacer nada.

    _7. Comprobacion de acceso_ Intenta acceder al `archivo1.txt` y `directorio1/archivo2.txt` como `usuario2`. Nota cómo el permiso de directorio afecta el acceso a los archivos dentro de él.

    _8. Verificacion final_ Verifica los permisos y propietario de los archivos y directorio nuevamente con `ls -l` y `ls -ld`.

## Detalles de entrega
* Fecha limite de entrega: 09/08/2023 23:59
* Modo de entrega: Link a repositorio de GitHub con el archivo .md
* Lenguaje de entrega: Markdown
* Nombre del archivo: actividad3.md
* Nombre de repositorio: so1_actividades_201403541

## Desarrollo de la actividad

### 1. Gestion de usuarios
---
1. Creacion de Usuarios
    + Crear tres usuarios siendo esos 'usuario1', 'usuario2' y 'usuario3'.
    ```
    sudo useradd usuario1
    sudo useradd usuario2
    sudo useradd usuario3
    ```

2. Asignacion de contraseñas
    + Asignar una contraseña a cada uno de los usuarios creados.
    ```
    sudo passwd usuario1
    sudo passwd usuario2
    sudo passwd usuario3
    ```

3. Informacion de usuarios
    + Mostrar la información de usuario1 usando el comando 'id'.
    ```
    id usuario1
    ```

4. Eliminacion de usuarios
    + Eliminar el usuario3, pero conservar su directorio principal.
    ```
    sudo userdel usuario3
    ```
    + Para conservar el directorio principal se debe de agregar el parametro -r
    ```
    sudo userdel -r usuario3
    ```

### 2. Gestion de grupos
---
1. Creacion de Grupos
    + Crear dos grupos llamados 'grupo1' y 'grupo2'.
    ```
    sudo groupadd grupo1
    sudo groupadd grupo2
    ```

2. Agregar Usuarios a Grupos
    + Agregar 'usuario1' a 'grupo1' y 'usuario2' a 'grupo2'.
    ```
    sudo usermod -a -G grupo1 usuario1
    sudo usermod -a -G grupo2 usuario2
    ``` 

3. Verificar Membresia
    + Verificar que los usuarios han sido agregados a los grupos utilizando el comando 'groups'.
    ```
    groups usuario1
    groups usuario2
    ```

4. Eliminar Grupos
    + Eliminar 'grupo2'.
    ```
    sudo groupdel grupo2
    ```

### 3. Gestion de permisos
---
1. Creacion de Archivos y Directorios
    + Como 'usuario1', crea un archivo llamado 'archivo1.txt' en su directorio principal y escribe algo en él.
    ```
    touch archivo1.txt
    echo "Hola mundo" > archivo1.txt
    ```
    + Crea un directorio llamado 'directorio1' y dentro de ese directorio, un archivo llamado 'archivo2.txt'.
    ```
    mkdir directorio1
    cd directorio1
    touch archivo2.txt
    ```

2. Verificar permisos
    + Verifica los permisos del archivo y directorio usando el comando `ls -l` y `ls -ld` respectivamente.
    ```
    ls -l archivo1.txt
    ls -ld directorio1
    ```

3. Modificar Permisos usando 'CHMOD' con modo numerico
    + Cambia los permisos del `archivo1.txt` para que sólo `usuario1` pueda leer y escribir (permisos `rw-`), el grupo pueda leer (permisos `r--`) y nadie más pueda hacer nada.
    ```
    chmod 640 archivo1.txt
    ```
    + Para verificar los permisos se utiliza el comando `ls -l`
    ```
    ls -l archivo1.txt
    ```
    + El resultado debe de ser el siguiente:
    ```
    -rw-r-----
    ```

4. Modificar permisos usando 'CHMOD' con modo simbolico
       + Agrega permiso de ejecución al propietario del `archivo2.txt`.
        ```
        chmod u+x archivo2.txt
        ```
        + Para verificar los permisos se utiliza el comando `ls -l`
        ```
        ls -l archivo2.txt
        ```
        + El resultado debe de ser el siguiente:
        ```
        -rwxr-----
        ```

5. Cambiar el grupo propietario
    + Cambia el grupo propietario de `archivo2.txt` a `grupo1`.
    ```
    chgrp grupo1 archivo2.txt
    ```
    + Para verificar los permisos se utiliza el comando `ls -l`
    ```
    ls -l archivo2.txt
    ```
    + El resultado debe de ser el siguiente:
    ```
    -rwxr----- 1 usuario1 grupo1
    ```

6. Configurar permisos de directorio
    + Cambia los permisos del `directorio1` para que sólo el propietario pueda entrar (permisos `rwx`), el grupo pueda listar contenidos pero no entrar (permisos `r--`), y otros no puedan hacer nada.
    ```
    chmod 750 directorio1
    ```
    + Para verificar los permisos se utiliza el comando `ls -ld`
    ```
    ls -ld directorio1
    ```
    + El resultado debe de ser el siguiente:
    ```
    drwxr-x---
    ```

7. Comprobacion de acceso
    + Intenta acceder al `archivo1.txt` y `directorio1/archivo2.txt` como `usuario2`. Nota cómo el permiso de directorio afecta el acceso a los archivos dentro de él.
    ```
    cd ..
    su usuario2
    cd directorio1
    cat archivo2.txt
    ```
    + El resultado debe de ser el siguiente:
    ```
    cat: archivo2.txt: Permiso denegado
    ```
    + Para verificar los permisos se utiliza el comando `ls -l`
    ```
    ls -l archivo1.txt
    ls -l directorio1/archivo2.txt
    ```
    + El resultado debe de ser el siguiente:
    ```
    -rw-r-----
    -rwxr-----
    ```
    + Para verificar los permisos se utiliza el comando `ls -ld`
    ```
    ls -ld directorio1
    ```
    + El resultado debe de ser el siguiente:
    ```
    drwxr-x---
    ```

8. Verificacion final
    + Verifica los permisos y propietario de los archivos y directorio nuevamente con `ls -l` y `ls -ld`.
    ```
    ls -l archivo1.txt
    ls -l directorio1/archivo2.txt
    ls -ld directorio1
    ```
    + El resultado debe de ser el siguiente:
    ```
    -rw-r-----
    -rwxr-----
    drwxr-x---
    ```
