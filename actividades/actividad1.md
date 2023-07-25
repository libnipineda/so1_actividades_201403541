# Actividad 1

## Descripcion de la actividad
Investigar sobre los siguientes conceptos de Sistemas Operativos:

* Tipos de Kernel y sus diferencias
* User vs Kernel mode

## Detalles de entrega
* Fecha limite de entrega: 25/07/2023 23:59:59
* Modo de entrega: Link a repositorio de GitHub con el archivo .md
* Lenguaje de entrega: Markdown
* Nombre del archivo: actividad1.md
* Nombre de repositorio: so1_actividades_201403541

## Desarrollo de la actividad

Antes de comenzar a investigar sobre lso conceptos, es importante saber o tener una breve nocion de lo que es un kernel.

El kernel de un sistema operativo es una parte fundamental y esencial del mismo, debido a que es el nucleo del sistema operativo y actua como una capa de software que interactua directamente con el hardware del ordenador.

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
| Monolitico | * Es el tipo mas tradicional y comunmente utilizado en muchos sistemas operativos, incluyendo Linux y Windows.  *Todas las funciones del sistema operativo, como la gestion de procesos, memoria, archivos, dispositivos, entre otros, se implementan en un solo y gran nucleo. | * Es mas rapido que otros tipos de kernel, ya que no necesita realizar llamadas al sistema para comunicarse con otros componentes del sistema operativo. * Es mas facil de implementar y depurar. | * Es mas propenso a errores, ya que un error en el kernel puede causar que el sistema operativo se bloquee o se vuelva inestable. * Es mas dificil de mantener y actualizar. |
| Microkernel | * Sigue un enfoque mas modular. Se minimiza el nucleo, moviendo la mayoria de las funciones del sistema fuera del kernel y ejecutandolas como procesos del usuario. * Generalmente proporciona un conjunto reducido de servicios esenciales, como la comunicacion entre procesos y la gestion basica de memoria y procesos. | * La ventaja es la mejora en la estabilidad y seguridad, ya que los servicios se ejecutan en espacios de memoria protegidos, y los fallos en ellos no afectan directamente al nucleo. | * Debido a las transiciones entre el espacio del usuario y el espacio del kernel, las llamadas al sistema pueden ser mas lentas, lo que podria afectar al rendimiento en comparacion con el kernel monolitico. |
| Hibrido | * Es una combinacion de los dos tipos anteriores, por lo cual, intenta aprovechar las ventajas de ambos enfoques. * Parte del sistema operativo se ejecuta en el espacio del kernel, mientras que algunos servicios se ejecutan en el espacio del usuario. | * Es mas flexible, ya que permite que los servicios se ejecuten en el espacio del kernel o en el espacio del usuario. * Es mas seguro y estable que el kernel monolitico. | * Es mas complejo que el kernel monolitico, lo que puede afectar al rendimiento. |

**Resumen:** Los kernels monoliticos suelen ser mas adecuados para sistemas con alto rendimiento  eficiencia mientras los kernels en microkernel se centran en la estabilidad y seguridad. Los kernels hibridos intentan combinar las ventajas de ambos enfoques.

