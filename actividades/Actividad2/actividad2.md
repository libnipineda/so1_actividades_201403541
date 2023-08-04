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

1. Crear el folder de la actividad en el repositorio local.
2. Crear el archivo `saludos.log` en `/tmp/<fecha>/`.

![Crear_Archivo](/actividades/Actividad2/img/parte1.png)

3. Ingresar el siguiente codigo en el archivo `saludos.log`:

``` 
echo "Hola ${GITHUB_USER} User id: ${id}. Cuenta fue creada el: ${created_at}"
```
Donde:
   * `${GITHUB_USER}` es el valor de la variable `GITHUB_USER`.
   * `${id}` es el valor del atributo `id` del JSON obtenido en el paso 2.
   * `${created_at}` es el valor del atributo `created_at` del JSON obtenido en el paso 2.

![Mensaje_Archivo](/actividades/Actividad2/img/parte2.png)

4. Ejecutar el comando en terminal:

``` 
sudo systemctl enable cron
```
![Cron](/actividades/Actividad2/img/parte3.png)

5. Estructura de Corn:
```
minute hour day_of_month month day_of_week command_to_execute
```

6. Comando para editar su contrab con el siguiente comando:
```
crontab -e
```
![Editar](/actividades/Actividad2/img/parte4.png)

7. Ingresar la siguiente linea en el archivo:
```
5 0 * * * bash /tmp/3-8-2023/saludos.log
```

8. Comando para ver el contenido de su contrab:
```
crontab -l
```
![Ver](/actividades/Actividad2/img/parte5.png)

8. Comando para ver el log de su contrab:
```
bash /tmp/3-8-2023/saludos.log
```
