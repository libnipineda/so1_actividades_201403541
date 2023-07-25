# Actividad 1

## Descripcion de la actividad
Investigar sobre los siguientes conceptos de Sistemas Operativos:

* Tipos de Kernel y sus diferencias
* User vs Kernel mode

## Detalles de entrega
* Fecha limite de entrega: 25/07/2023 23:59
* Modo de entrega: Link a repositorio de GitHub con el archivo .md
* Lenguaje de entrega: Markdown
* Nombre del archivo: actividad1.md
* Nombre de repositorio: so1_actividades_201403541

## Desarrollo de la actividad

Antes de comenzar a investigar sobre los conceptos, es importante saber o tener una breve nocion de lo que es un kernel.El kernel de un sistema operativo es una parte fundamental y esencial del mismo, debido a que es el nucleo del sistema operativo y actua como una capa de software que interactua directamente con el hardware del ordenador.

Su funcion principal es la de gestionar los recursos de la computadora, como la memoria y los procesos, asi como tambien es el encargado de facilitar la comunicacion entre el hardware y el software.

El kernel opera en modo privilegiado, esto quiere decir que tiene acceso directo al hardware y a recursos criticos del sistema, lo que le permite realizar tareas que las aplicaciones normales no pueden realizar. Esto tambien implica que el kernel debe ser robusto y confiable, ya que un error en el kernel puede causar que el sistema operativo se bloquee o se vuelva inestable.

Es importante destacar que existen diferentes tipos de kernel, los cuales se diferencian por la forma en que se comunican con el hardware y los procesos que se ejecutan en el sistema.

### Tipos de Kernel
Existen principalmente tres tipos de kernel en funcion de su diseño y arquitectura, los cuales son:
* Kernel Monolitico.
* Kernel en Microkernel.
* Kernel Híbrido.

Cada tipo de kernel tiene sus pros y contras, la eleccion del diseño dependera de las necesidades y prioridades del sistema operativo en cuestion.

| Tipo Kernel | Descripcion | Ventajas | Desventajas |
| ----------- | ----------- | -------- | ----------- |
| Monolitico | Todas las funciones del sistema operativo, como la gestion de procesos, memoria, archivos, dispositivos, entre otros, se implementan en un solo y gran nucleo. | * Es mas rapido que otros tipos de kernel, ya que no necesita realizar llamadas al sistema para comunicarse con otros componentes del sistema operativo. * Es mas facil de implementar y depurar. | * Es mas propenso a errores, ya que un error en el kernel puede causar que el sistema operativo se bloquee o se vuelva inestable. * Es mas dificil de mantener y actualizar. |
| Microkernel | Sigue un enfoque mas modular. Se minimiza el nucleo, moviendo la mayoria de las funciones del sistema fuera del kernel y ejecutandolas como procesos del usuario, generalmente proporciona un conjunto reducido de servicios esenciales, como la comunicacion entre procesos y la gestion basica de memoria y procesos. | La ventaja es la mejora en la estabilidad y seguridad, ya que los servicios se ejecutan en espacios de memoria protegidos, y los fallos en ellos no afectan directamente al nucleo. | Debido a las transiciones entre el espacio del usuario y el espacio del kernel, las llamadas al sistema pueden ser mas lentas, lo que podria afectar al rendimiento en comparacion con el kernel monolitico. |
| Hibrido | * Es una combinacion de los dos tipos anteriores, por lo cual, intenta aprovechar las ventajas de ambos enfoques. * Parte del sistema operativo se ejecuta en el espacio del kernel, mientras que algunos servicios se ejecutan en el espacio del usuario. | * Es mas flexible, ya que permite que los servicios se ejecuten en el espacio del kernel o en el espacio del usuario. * Es mas seguro y estable que el kernel monolitico. | Es mas complejo que el kernel monolitico, lo que puede afectar al rendimiento. |

**Resumen:** Los kernels monoliticos suelen ser mas adecuados para sistemas con alto rendimiento  eficiencia mientras los kernels en microkernel se centran en la estabilidad y seguridad. Los kernels hibridos intentan combinar las ventajas de ambos enfoques.

## Modos de operacion
Los modos de operacion son diferentes niveles o estados en los que un sistema computacional o procesador puede funcionar, y cada modo tiene su propio conjunto de privilegios y restricciones para acceder a los recursos del sistema.

Estos modos estan diseñados para garantizar la seguridad, proteccion y eficiencia en el funcionamiento del sistema. los dos modos principales de operacion son:
* Modo Usuario.
* Modo Kernel.

Por ejemplo: un bit, denominado bit de modo, se añade al hardware de la computadora para indicar el modo actual kernel (0) o usuario (1). Cuando el bit de modo es 0, el sistema esta en modo kernel, y cuando el bit de modo es 1, el sistema esta en modo usuario.

| Tipo de modo | Descripcion | Ventajas | Desventajas |
| ------------ | ----------- | -------- | ----------- |
| Modo Usuario o User Mode | * Tambien conocido como modo usuario o modo no privilegiado. * En este modo, las aplicaciones y programas de usuario se ejecutan. * Los programas en modo usuario tiene acceso restringido a los recursos del sistema y no pueden realizar operaciones criticas, como interactuar directamente con el hardware o modificar areas de memoria protegidas esto permite que las instrucciones y operaciones que pueden ejecutarse en modo usuario sean limitadas y esten diseñadas para garantizar la seguridad y estabilidad del sistema. * Si un programa en modo usuario necesita acceder a servicios del sistema o recursos que requieran niveles mas altos de privilegio, debe hacerlo a traves de llamadas al sistema (system calls), que permiten al programa solicitar que el sistema operativo realice operaciones en su nombre.| * Es mas seguro y estable, ya que los programas en modo usuario no pueden realizar operaciones criticas. * Es mas eficiente, ya que los programas en modo usuario no pueden realizar operaciones criticas. | * No puede acceder directamente al hardware o a los recursos del sistema. * No puede realizar operaciones criticas. |
| Modo Kernel o Kernel Mode | * Tambien conocido como modo supervisor o modo privilegiado. * En este modo se ejecuta el kernel del sistema operativo. * El kernel tiene acceso completo a todos los recursos del sistema, incluidos el hardware y las areas de memoria protegidas. * Debido a que el kernel tiene acceso directo al hardware y recursos del sistema, es una parte critca y potencialmente peligrosa del sistema, por lo que debe ser robusto y seguro para evitar fallos y vulnerabilidades. | * Tiene acceso directo a los recursos del sistema, lo que permite realizar operaciones criticas. * Puede ejecutar instrucciones y operaciones que no estan permitidas en modo usuario. | * Es menos seguro y estable, ya que un error en el kernel puede causar que el sistema operativo se bloquee o se vuelva inestable. * Es menos eficiente, ya que el kernel tiene acceso directo a los recursos del sistema. |

**Nota:** El cambio entre el modo usuario y el modo kernel ocurre a traves de mecanismos de cambio de contexto que se gestionana en el hardware del procesador. Estos mecanismos garantizan que el sistema sea seguro y protegido, ya que las aplicaciones en modo usuario no pueden acceder directamente al hardware ni realizar operaciones critcas, lo que ayuda a evitar fallos y conflictos que podrian afectar a todo el sistema operativo.

**Resumen:** El modo usuario y el modo kernel son dos niveles de privilegios diferentes en un sistema operativo. El modo usuario es donde se ejecuta las aplicaciones y programas de usuario, con accesos restringido a recursos del sistema mientras el modo kernes es el nivel de privilegio mas alto, donde se ejecuta el nucleo del sistema operativo y tiene accesos completo a todos los recursos del sistema y la comunicacion entre estos dos modos se realiza mediante llamadas al sistema para garantizar la seguridad y proteccion del sistema.