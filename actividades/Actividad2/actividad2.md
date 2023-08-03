# Actividad 2

## Descripcion de la actividad
Crear un script Bash que realice los siguiente:

* Lea la variable `GITHUB_USER`.
* Consulte la URL https://api.github.com/users/${GITHUB_USER} concatenando el valor de la variable `GITHUB_USER` con la URL.
* Imprimir el mensaje:
    * "Hola <GITHUB_USER> User id: <id>. Cuenta fue creada el: <created_at>"
    * Donde `<GITHUB_USER>` es el valor de la variable `GITHUB_USER`.
    * Donde `<id>` es el valor del atributo `id` del JSON obtenido en el paso 2.
    * Donde `<created_at>` es el valor del atributo `created_at` del JSON obtenido en el paso 2.
* Crear un log file en /tmp/<fecha>/saludos.log con la salida del mensaje anterior. Donde <fecha> corresponde a la fecha del dia de ejecucion del script.

## Detalle de entrega
* Fecha limite de entrega: 04/08/2023 23:59
* Entrega: Link al folder de GitHub
* Nombre del folder: actividades/Actividad2

## Desarrollo de la actividad

