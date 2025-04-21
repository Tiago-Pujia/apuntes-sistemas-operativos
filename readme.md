# 📘 Introducción

> Material de cursada de la materia **Sistemas Operativos**  
> 📅 Inicio: 09/04/2025  
> 🎓 Alumno: Tiago Pujia | 👨‍🏫 Prof: Alexis Villamayor  
> 🕔 Comisión 3900 [3 = Miercoles, 9 = Turno noche]
> ▶️ [Clases Grabadas](https://www.youtube.com/)

## Indice

- [📘 Introducción](#-introducción)
  - [Indice](#indice)
- [Clase 1 y 2 - Modulo 1: Introducción a los Sistemas Operativos](#clase-1-y-2---modulo-1-introducción-a-los-sistemas-operativos)
  - [¿Que es un sistema operativo?](#que-es-un-sistema-operativo)
    - [¿Por qué estudiar los sistemas operatiovs?](#por-qué-estudiar-los-sistemas-operatiovs)
  - [Funciones y Objetivos](#funciones-y-objetivos)
    - [Inicialización (proceso de arranque)](#inicialización-proceso-de-arranque)
    - [Maquina Extendida (Interfaz)](#maquina-extendida-interfaz)
    - [Administración de recursos](#administración-de-recursos)
    - [Aislamiento](#aislamiento)
    - [Seguridad](#seguridad)
  - [Clasificaciones de Sistemas Operativos](#clasificaciones-de-sistemas-operativos)
    - [Segun la Cantidad de Usuarios](#segun-la-cantidad-de-usuarios)
    - [Segun la Cantidad de Procesadores que Soporta](#segun-la-cantidad-de-procesadores-que-soporta)
    - [Segun la Cantidad de Tareas que Sucesivas](#segun-la-cantidad-de-tareas-que-sucesivas)
    - [Segun sus Aplicaciones (Usos)](#segun-sus-aplicaciones-usos)
    - [Segun la Organización de su Arquitectura](#segun-la-organización-de-su-arquitectura)
  - [Interrupciones](#interrupciones)
    - [Definición](#definición)
    - [Clasificación](#clasificación)
      - [Segun prioridad](#segun-prioridad)
      - [Segun su origen](#segun-su-origen)
    - [Diferencia Interrupción y Excepción](#diferencia-interrupción-y-excepción)
    - [Funciones y Objetivos](#funciones-y-objetivos-1)
  - [Modos de Ejecucion de los Procesos](#modos-de-ejecucion-de-los-procesos)
  - [Definiciones Computo Distribuido](#definiciones-computo-distribuido)
- [Clase 3](#clase-3)
  - [Modulo 2: De Programas a Procesos](#modulo-2-de-programas-a-procesos)
    - [Conceptos Basicos](#conceptos-basicos)
    - [Entidad Pasiva y Activa](#entidad-pasiva-y-activa)
    - [Compilación y Carga de un Proceso](#compilación-y-carga-de-un-proceso)
    - [Procesos y Thread](#procesos-y-thread)
    - [Administración de Procesos](#administración-de-procesos)
      - [Estructura Memoria CPU](#estructura-memoria-cpu)
      - [Bloque de Control (PCB)](#bloque-de-control-pcb)
      - [Cambio de Contexto y Proceso](#cambio-de-contexto-y-proceso)
      - [Objetivos del PCB](#objetivos-del-pcb)
      - [Contenido del PCB](#contenido-del-pcb)
    - [Transición de Estados de un Proceso](#transición-de-estados-de-un-proceso)
      - [Tipos de Estados](#tipos-de-estados)
      - [Diagrama de Proceso](#diagrama-de-proceso)
        - [Modelo 7 Estados](#modelo-7-estados)
        - [Modelo 5 Estados](#modelo-5-estados)
      - [Colas](#colas)
      - [Clasificación Estados](#clasificación-estados)
      - [Razones de un Cambio de Estado de Proceso](#razones-de-un-cambio-de-estado-de-proceso)
    - [Creación de Procesos](#creación-de-procesos)
      - [Razones para crear un proceso](#razones-para-crear-un-proceso)
      - [Tipos de Creacion de Procesos](#tipos-de-creacion-de-procesos)
      - [Secuencia de creación de un proceso](#secuencia-de-creación-de-un-proceso)
      - [Finalizar de un proceso](#finalizar-de-un-proceso)
    - [Hilos](#hilos)
      - [Definición](#definición-1)
      - [Ventajas respecto a los Procesos](#ventajas-respecto-a-los-procesos)
      - [Implementación de Hilos](#implementación-de-hilos)
        - [Hilos a Nivel de Usuario (ULT)](#hilos-a-nivel-de-usuario-ult)
        - [Hilos a Nivel de Kernel](#hilos-a-nivel-de-kernel)
      - [Estado de los Hilos](#estado-de-los-hilos)
      - [Estructuras de Uso de los Hilos](#estructuras-de-uso-de-los-hilos)
  - [Modulo 3: Planificación de Procesos](#modulo-3-planificación-de-procesos)
    - [Concepto de Planificación](#concepto-de-planificación)
    - [Objetivos](#objetivos)
    - [Tipos](#tipos)
    - [Tipos de procesos](#tipos-de-procesos)

# Clase 1 y 2 - Modulo 1: Introducción a los Sistemas Operativos

## ¿Que es un sistema operativo?

Definiciones dadas por el profesor sobre s.o:

> Conjunto de módulos o funciones (software), que, instalados en la computadora, se ocupan de controlar y administrar la ejecución de los programas sobre los recursos que brinda el equipo (hardware), tales como: memoria, procesador, periféricos, etc.

> Conjunto de programas que ordenadamente relacionados entre sí, contribuyen a que la computadora lleve a cabo correctamente su trabajo para nosotros en un ambiente dado.

El **kernel** es el núcleo del sistema operativo. Es la parte más importante, encargada de: administrar hardware,

### ¿Por qué estudiar los sistemas operatiovs?

No sólo en comprender los mecanismos de los mismos. Si no, entenderlos para evitar los errores más comunes al programar o aumentar la seguridad del sistema operativo.

## Funciones y Objetivos

El sistema operativo es el único programa que interactua directamente con el hardware. Sus funciones primarias son:

### Inicialización (proceso de arranque)

![inicializacion](/imgs/clase-1/inicializador.png)

Al encender una computadora, se ejecuta un **chequeo inicial**, controlado por el firmware de la placa madre, ya sea **_BIOS_** o **_UEFI_**. Este proceso se encarga de inicializar y verificar el hardware esencial (como la memoria RAM, el procesador y los discos). Además, permite al usuario acceder a una interfaz de configuración, donde puede definir opciones como el orden de arranque.

Una vez completado este chequeo, el BIOS o UEFI busca un **dispositivo de almacenamiento** que contenga un **_MBR (Master Boot Record)_** válido. Este MBR se encuentra en el **primer sector físico del disco** (sector 0). En él se almacena una pequeña parte del **código de arranque**.

El BIOS transfiere el control al código ubicado en el MBR, el cual se encarga de identificar la **_partición activa_**, es decir, aquella que está marcada como booteable. Desde allí, el MBR accede al sector de arranque de dicha partición, donde se encuentra un puntero que lo dirige al **_gestor de arranque_** o **_bootloader_**.

El **_bootloader_** es un programa almacenado dentro del sistema de archivos del disco. Su función es **cargar el núcleo del sistema operativo (kernel)** en la **memoria RAM** y dar inicio a la ejecución del sistema, dejando el entorno preparado para que el usuario comience a trabajar.

### Maquina Extendida (Interfaz)

Procedimiento que permite la interacción del usuario con el ordenador. Sus principales funciones:

-   Facilita comunicación con el usuario
-   Aceptar entradas de nuevos trabajos
-   Abstracción: los programas no deben preocuparse de los detalles de acceso a hardware o de la configuración

Existen diferentes clasificación en las interfaces:

-   GUI (Grafica para Usuarios) -> KDE, Gnome, Aero
-   CLI (Linea de Comandos) -> Bash, cmd, powershell
-   NUI (Interfaz superior a la grafica) -> tactil, voz, gestos

### Administración de recursos

-   Mas del 70% del s.o esta dedicado a esta función
-   Gestiona politicas de asignación de recursos para que los programas no compitan por los ellos
-   Optimiza los recursos

### Aislamiento

En un sistema multiusuario y multitarea, cada proceso y cada usuario no tendra que preocuparse por otros que esten usando el mismo sistema.

### Seguridad

Garantizar la integridad de los recursos y procesos como, tambien validar los usuarios del sistema. Existen 2 modos para lograrlo:

-   Modo dual de ejecución del procesador - > separa en 2 tipos de instrucciones
    -   Modo usuario o no privilegiado
    -   Mood kernel o privilegiado (uso exclusivo para el s.o)
-   Juego de instrucciones diferenciadas del procesador

Si un usuario quiere usar instrucciones de kernel entra en un trap.

La seguridad se basa en 3 caracteristicas:

-   **Abstracción** -> Un usuario no puede escribir directo en el disco, su acceso debe estar limitado a la interfaz
-   **Administrar Recuersos** -> Politica de asignación de recursos
-   **Aislamiento** -> Si el S.O ofrece separación entre los datros, procesos y recursos de distintos usuarios. Ninguno debe tener acceso a la información del projimo.

## Clasificaciones de Sistemas Operativos

### Segun la Cantidad de Usuarios

-   **Monousuario** -> Un solo usuario
-   **Multiusuario** -> Varios usuarios (incluyendo remeto)

### Segun la Cantidad de Procesadores que Soporta

-   **Uniprocesador** -> Solo puede manejar un procesador de la computadora. Por lo que si tiene mas de un nucleo el cpu, es inutil.
-   **Multiprocesador** -> Sistemas capaces de manejar mas de un procesador

### Segun la Cantidad de Tareas que Sucesivas

-   **Monoprogramado o monotarea** -> Solo se puede ejecutar un proceso a la vez recien cuando finalize uno, arranca el siguiente.
-   **Multiprogramado(multitarea)** -> Mas de un proceso ejecutando el sistema

### Segun sus Aplicaciones (Usos)

-   **Proposito general** -> Propositos de amplia gama con cualquier fin
-   **Proposito especial** -> construccion a medida para un uso especifico. Se clasifica en:
    -   Tiempo real -> Tiempo de respuesta a eventos
        -   Tiempo Real No Crítico -> El tiempo de respuesta es importante, pero no vital
        -   Tiempo Real Crítico -> Requiere una respuesta inmediata
    -   Tolerante a fallas -> Se utilizan en aplicaciones donde es fundamental mantener un servicio continuo, incluso ante fallos de hardware o software. El mismo S.O detecta y corrige errores.
    -   Sistemas virtuales -> Los Sistemas Operativos Virtuales son capaces de administrar y gestionar otros sistemas operativos que se ejecutan de forma concurrente sobre el mismo hardware.

### Segun la Organización de su Arquitectura

Existen 2 formas principales de organización del núcleo de un sistema operativo, junto a un enfoque híbrido:

-   **Monoliticos**

Todo el sistema operativo corre como un único proceso privilegiado que opera como supervisor. Todas las funcionalidades (gestión de memoria, archivos, dispositivos, etc.) están integradas directamente en el núcleo.

Ventajas:

-   Simplifica gran cantidad de mecanismos -> mayor velocidad ejecución
-   Mayor flexibilidad

![monolitico](imgs/clase-1/monolitico.png)

-   **MicroKernel**

El núcleo se mantiene en el minimo posible de funcionalidad, descargando en procesos especiales sin privilegios las tareas que implementan el acceso a dispositivos y las diversas politicas de uso del sistema. Se limita a las funciones más básicas (como planificación y comunicación).

Ventajas:

-   Esquema logico mas limpio
-   Implementaciones mas elegantes y faciles de comprender
-   Puede auto-repararse

![microkernel](imgs/clase-1/microkernel.png)

-   **Hibridos**

Sistemas que son mayormente monolitocs pero que manejan algunos procesos que parecerian centrales mediante de procesos de nivel de usuario como microkernel.

La mayoría de los S.O. modernos, como Windows, adoptan este modelo por su equilibrio entre rendimiento y flexibilidad.

![hibrido](imgs/clase-1/hibrido.png)

## Interrupciones

### Definición

Cuando ocurra algún evento que requiere la atención del sistema operativo, el mismo levanta la solicitud y detiene el proceso que estaba siendo ejecutado. El S.O ejecuta su rutina de manejo de interrupciones y atiende la interrupción. Las mismas se pueden organizar por orden de prioridad y hay un numero limitado.

### Clasificación

#### Segun prioridad

-   **No Enmascarable (no postergar)** -> Debe ser atentido si o si en el momento
-   **Enmascarable (postergar)** -> No es urgente y se atiende cuando quiere

#### Segun su origen

-   **Software** -> llamadas del sistema (syscalls)
-   **Harware** -> llamadas por un componente fisico. Se subdivide en:
    -   Interno -> Dentro del procesador. Ejemplo: divisioon por cero, acceso no autorizado a memoria.
    -   Externo -> Fuera del procesador. Ejemplo: ingreso por teclado, un pendrive co

### Diferencia Interrupción y Excepción

-   **Interrupción** -> Causas externas a la computadora
-   **Excepción** -> Causado por un proceso interno

### Funciones y Objetivos

-   **Administrar el hawrdawre manejando interrupciones**
-   **Abstraer las Interrupciones** -> Oculta al programa de usuario que ocurren interrupociones de hardware. Pero, avisa al usuario mediante mensajes, señales o deteniendo el proceso.
-   **Atender Excepciones y Fallas** -> Durante la ejecución de un programa, ocurre situaciones anómales
-   **Punto de entrada al Sistema Operativo** -> Medio por el cual un proceso realiza una llamada al sistema (ecall de Assembly). Estas llamadas sirven para:
    -   **Control de Procesos** -> crear o finalizar proceso, asignar o liberar memoria, etc...
    -   **Manipular Archivos** -> Crear, borrar o renombrar un archivo
    -   **Manipulación de Dispositivos** -> Solicitar o liberar un dispositiovo
    -   **Manipular Información** -> Obtener o modificar la hora del sistema, pedir detalles acerca de procesos o archivos
    -   **Comunicaciones** -> Establecer una comunicación con determinado proceso (local o remoto)
    -   **Protección** -> Consultar o modificar la información relativa al acceso de objetos en el disco o sesión del usuario.

Las llamadas al sistema son expuestas al programador mediante las *interfaces de apliacación al programador*(API).

## Modos de Ejecucion de los Procesos

![](/imgs/clase-1/ejecucion-programacion.png)

-   **Procesos Secuenciales** -> Cada proceso se ejecuta a continuación del otro
-   **Multiprogramación** -> Ilusion que se ejecutan varios procesos al mismo tiempo, pero en realidad esta alternando entre los diversos procesos que compiten por su atención. Por lo que, atiende simultaneamente diversos procesos.
-   **Multiprocesamiento** -> Entorno donde hay mas de un procesador (CPU). Por lo que diferentes procesos independientes se ejecutan en paralelo.
    -   **Asimétrico** -> Procesadores con arquitecturas distintas. Tambien se pueden llamar como coprocesaodres o procesadores coadyuvantes.
    -   **Simétrico** -> Todos los CPU son iguales y pueden realizar en el mismo tiempo las operaciones
        -   Unifrm Memory Access(UMA) -> Ambos procesadores comparten la memoria, utilizan un BUS compartido
        -   Non-Uniform Memory Access(NUMA) -> Cada procesador tiene bancos de memoria. Da como ventajas que es mas rapido.
-   **Hibrido** -> Multiprogramación y Multiprocesamiento se combinan. Las mayorias de PC funcionan asi.

## Definiciones Computo Distribuido

Proceso de cómputo realizado entre computadoras independientes, o tambien dicho, entre procesadores que no comparten memoria. Hay diferentes implementaciones:

-   **Cúmulos(Clusters)** -> Computadoras conectadas por una red local. La red es administrado por un software.
-   **Mallas (Grids)** -> Computadoras distribuidas a nivel geografico e interconectadas a una red.
-   **Cómputo En la Nube** -> Tercerización de servicios; la implementación de servicios deja de ser relevante. Se aplica conceptos como:
    -   Servicios Web
    -   Software como Servicio
    -   Plataforma como Servicio
    -   Infraestructura como Servicio

# Clase 3

## Modulo 2: De Programas a Procesos

### Conceptos Basicos

- **¿Que es un Programa?**

> Conjunto de instrucciones que resuelven un problema

- **¿Que es una Instrucción?**

> Unidad de ejecución que dura un tiempo finito y se ejecuta sobre un procesador. No se descompone ni interrumpe

- **¿Que es un Proceso?**

> Porcion de un programa cargando en memoria central al cual se le asocia su contexto de ejecucion (run time environment) mediante una estructura de datos llamada vector de estado o **Bloque de Control del Proceso (PCB)**

### Entidad Pasiva y Activa

- **Entidad Pasiva**

No cambia por si mismo, no tiene actividad propia, solo es un conjunto de instrucciones a ser esperado. Ejemplo: Un programa almacenado en disco o memoria.

- **Entidad Activa**

Cambia de estado mientras se ejecuta, tiene actividad propia (consume CPU, E/S y memoria). Ejemplo: Un proceso en ejecucion

### Compilación y Carga de un Proceso

![](/imgs/clase-2/Compilación%20y%20Carga%20de%20un%20Proceso.png)

1. **Primer Paso: Traduccion de codigo fuente a maquina**
    1. Se parte de un programa fuente, donde escribimos el código en un lenguaje de alto nivel.
    2. Se compila y entrega:
           - Area de texto: Instrucciones traducidas a codigo maquina
           - Tabla de Simbolos: Asocia las variables del programa a direcciones de memoria relativas al origen. Guarda:
             - Nombre del simbolo o identificador (nombre variable)
             - Direccion inicio variable
             - Direccion fin Variable
    3. El **Programa Objeto** es el resultado. Archivo binario con instrucciones pero sin estar listo para ejecutarse.
2. **Segundo Paso: Link-Editor (enlazador) Resuelve referencias externas del programa objeto para transformarlo a programa ejecutable**
    1. El link-editor labura sobre el programa objeto:
       - Incluye librerias
       - Combina todos los programas objetos en uno solo
       - Ajusta las direcciones de memoria, asignando identificadores únicos a las variables y funciones.
    2. Da como resultado un programa ejecutable preparador para ser cargado a memoria.
3. **Tercer Paso: Ubica el programa ejecutable a memoria**
    1. Lee el archivo ejecutable
    2. Lo ubica en una posición libre de la memoria principal.
    3. Genera el PCB (Process Control Block); Estructura que almacenará toda la información necesaria para administrar el proceso(estado, registros, contador de programa, etc.).
4. **Cuarto Paso: Proceso en estado de ejecutarse**

### Procesos y Thread

- **Procesos**
Un proceso se define como la imagen de un programa en ejecucion; en memoria usando la CPU. A esta altura, un proceso tiene un espacio de direcciones de memoria, una pila, regitros y program counter (PC)

- **Hilo(thread) o Proceso Liviano**
Dentro de un proceso se puede tener secciones que tienen sus propios procesos, osea su propio espacio de memoria, registros, pila y program counter. Puede compartir memoria con el resto de thread que forman parte del mismo proceso.

### Administración de Procesos

#### Estructura Memoria CPU

![](/imgs/clase-2/memoria-cpu.png)

1. **Stack(pila):** Área utilizado para almacenar información asociada a la ejecución de funciones. Ejemplo: Variables locales, parametros funciones, direcciones retorno
2. **Dynamic Data(heap):** Almacena datos de tamaño variable o datos que se crean dinámicamente en tiempo de ejecución. Ejemplo: malloc, realloc, free
3. **Static Data:** Datos de longitud fija creador en tiempo de compilacion. Ejemplo: variables globales y constantes
4. **Literales:** Area de texto para datos constantes. Ejemplo: "Hola"
5. **Instrucciones:** Area de texto donde guarda instrucciones del programa. Solo de lectura

#### Bloque de Control (PCB)

Los datos de **cada** proceso se guardan en un PCB propio. Este, se almacena en la pila del procesador. Del stack se copia una imagen del proceso que se carga al CPU y se ejecuta.

En el PCB se guarda para cada proceso, la información necesaria para reanurlo en caso que sea suspendido o desalojado. A esto se le llama cambio de contexto.

#### Cambio de Contexto y Proceso

- **Cambio de Contexto**

Mecanismo mediante el cual el Sistema Operativo guarda el estado actual de la CPU (registros, contador de programa, etc.) asociado al proceso en ejecución, para luego cargar el estado de otro proceso que debe ejecutarse

El cambio de contexto permite interrumpir un proceso y continuarlo más adelante desde el mismo punto donde quedó.

- **Cambio de Proceso**

Ocurre cuando el Sistema Operativo decide suspender el proceso actual y darle la CPU a otro proceso diferenteo. El cambio se puede dar por distintos motivos, por ejemplo: Finalización de una tarea, Interrupciones del sistema.

Implica necesariamente hacer un cambio de contexto: primero se guarda el estado del proceso que se suspende y luego se carga el estado del nuevo proceso.

- **Diferencia**

| Concepto             | ¿Qué hace?                                             | ¿Cuándo ocurre?                             |
|-----------------------|---------------------------------------------------------|---------------------------------------------|
| **Cambio de Contexto** | Guarda el estado de un proceso y carga el de otro.      | Cada vez que se cambia el proceso en ejecución. |
| **Cambio de Proceso**  | Elige otro proceso para ejecutar.                      | Cuando el sistema operativo lo decide (fin de proceso, interrupción, planificación, etc.). |


#### Objetivos del PCB

- Localización de la información sobre el proceso por parte del S.O
- Mantener registrados los datos del proceso en caso de suspender la ejecución

#### Contenido del PCB

- Identificación (única en el sistema) 
- Identificadores varios del proceso (identificador del dueño, padre, hijos, etc)
- Estado (ejecutando, listo, bloqueado) 
- Program Counter 
- Registros de CPU 
- Información para planificación (p.ej., prioridad) 
- Información para administración de memoria (p.ej., registros base y límite) 
- Información de I/O: dispositivos y recursos asignados al proceso, archivos abiertos en uso, etc. 
- Estadísticas y otros: tiempo real y tiempo de CPU usado, etc. 
- Privilegios.
- Otros objetos vinculados al proceso.

### Transición de Estados de un Proceso

#### Tipos de Estados

Un proceso puede transitar por varios estados a lo largo de su vida dentro del sistema operativo:

- **Nuevo (New):** Se solicitó al sistema operativo la creación de un proceso, y sus recursos y estructuras están siendo creadas.

- **Listo (Ready):** El proceso ya está preparado para ejecutarse, pero todavía no se le ha asignado un procesador. Permanece en espera en la cola de procesos listos.

- **En Ejecución (Running):** El proceso está siendo ejecutado en este momento. 

- **Bloqueado (Blocked):** El proceso no puede avanzar porque está esperando a que ocurra algún evento (como la finalización de una operación de entrada/salida). Aunque haya un procesador disponible.

- **Zombie:** El proceso ha finalizado su ejecución, pero el sistema operativo debe realizar ciertas operaciones de limpieza para poder eliminarlo de la lista.

- **Terminado (Exit):** El proceso terminó de ejecutarse; sus estructuras están a la espera de ser limpiadas por el sistema operativo.

#### Diagrama de Proceso

Un proceso puede pasar varias etapas diferentes en el sistema operativo, y el modelo depende del mismo. Hay varios modelos

##### Modelo 7 Estados

![](/imgs/clase-2/Modelo%207%20estados.png)

Se crea un nuevo proceso que debe ser admitido, este se puede poner en listo o en listo/suspendido (esperando memoria). Cuando esta listo, esta esperando que el S.O le otorgue el CPU para ponerlo en ejecución. Cuando se encuentra en ejecución pueden pasar 2 cosas, finaliza o se bloquea por una interrupción

##### Modelo 5 Estados

![](/imgs/clase-2/Modelo%205%20Estados.png)

Modelo mas sencillo, no existe los estados de listo/suspendido o bloqueado/suspendido

#### Colas

Una cola es una estructura de datos donde los elementos se agregan al final y se sacan del principio. El primero que entra es el primero que sale.

Aplicado a procesos, una cola es donde se organizan los procesos que están esperando. Por ejemplo:
- Cuando un proceso pasa al estado Listo, se pone en la cola de Listos.
- Cuando un proceso está esperando por I/O, se pone en la cola de Bloqueados.

Todos los estados son de tipo cola, excepto los de ejecución. Porque, el CPU solo puede ejecutar un proceso a la vez.

#### Clasificación Estados

- **Estados Activos**

Son aquellos que compiten por el procesador o están en condiciones de hacerlo. Estos son: ejecución, listo y bloqueado (no pueden ejecutarse de momento por necesitar algún recurso ).

- **Estados Inactivos**

Son aquellos que no pueden competir por el uso del procesador. Estos son suspendido/bloqueado y suspendido/listo.

#### Razones de un Cambio de Estado de Proceso

- Interrupciones de Hardware Externas
- Excepción(trap)
- Llamada al sistema operativo
- Por finalización

### Creación de Procesos

#### Razones para crear un proceso

Todos los procesos son creados por el sistema operativo, aunque un proceso puede crear otro proceso. Hay 4 razones para crear uno:
- La llegada de un trabajo nuevo al sistema.
- Un proceso enviado por un usuario.
- La necesidad de brindar un servicio a un programa en ejecución.
- La creación explícita por parte de otro proceso existente.

#### Tipos de Creacion de Procesos

Cuando un proceso crea a otro, el proceso creador se llama **padre** y el proceso generado se llama **hijo**. Estos procesos suelen **comunicarse** y **cooperar** entre sí.

- Jerarquia: Cada proceso que se crea es hijo del proceso creador y hereda el entorno de ejecución de su padre. Puede ser de 2 maneras:
    - El padre continua ejecutando en paralelo con sus hijos
    - El padre espera que todos sus hijos hayan terminado y luego sigue él.
- No Jerarquica -> Se ejecutan de forma independiente

#### Secuencia de creación de un proceso

1. Asignar un identificador al nuevo proceso
2. Asignar espacio memoria para el proceso
3. Incializar la estructura de datos PCB
4. Establecer enlaces apropiados con otras estructuras del sistema operativo, como archivos abiertos, referencias a procesos padres, hijos o hermanos.
5. Ampliar o crear otra estructura de datos en caso que fuerza necesarios (archivos y de más)

#### Finalizar de un proceso

- Desaparece el PCB
- Liberar recursos comunes
- Recursos locales son destruidos: Los datos como variables o memoria del stack

La **Terminación en cascada** es cuando un proceso termina (muere) tambien deben terminar sus hijos.

### Hilos

#### Definición

El concepto de **hilo** ya fue mencionado anteriormente, pero realizamos un repaso:

> Dentro de un proceso pueden existir **secciones independientes** (hilos), cada una con su propio espacio de registros, pila y contador de programa. Sin embargo, **comparten el espacio de memoria** con los demás hilos del mismo proceso.

Hilos, threads o Proceso Liviano debido a que mantiene la estructura de un proceso con su PCB. Pero, dispone de estructuras,as pequeñas llamadas TCB (Thread Control Block, similar a PCB) que manejan menos información del PCB.

Cada hilo posee:
- TID (Thread Identifier)
- program counter (PC)
- registros de CPU
- Pila.

Cada hilo se ejecuta de forma **secuencial**, aunque en **multiprocesadores** pueden ejecutarse **en paralelo**.

Los hilos pueden **crear hilos hijos**, y **cooperan** entre sí compartiendo:
- Espacio de Memoria
- Archivos Abiertos
- Relojes
- Otros recursos

#### Ventajas respecto a los Procesos

- Requiere **menos tiempo** realizar un cambio de contexto entre hilos que entre procesos.
- **Comparten espacio de memoria** y recursos, permitiendo una comunicación más rápida entre ellos.

#### Implementación de Hilos

##### Hilos a Nivel de Usuario (ULT)

- **Caracteristicas**
  - Los administra el usuario mediante una aplicacion
  - Cualquier aplicación puede ser programada para ser multi-hilo mediante el uso de librerias de hilos
  - Se crean en **tiempo de compilación** y **no requieren intervención del kernel**.
  - El kernel **no sabe** de la existencia de los hilos; ve al proceso como una sola entidad.
- **Ventajas**
  - El cambio de hilo no requiere modo kernel
  - El proceso no cambia a modo kernel para manejar el hilo
  - Puede correr en cualquier sistema operativo
  - El algoritmo de planificación puede ser adapto sin molestar la planificación del Sistema operativo
- **Desventajas**
  - la mayoría de las llamadas a sistema son bloqueantes. Cuando un hilo ejecuta un llamadas a sistema no sólo se bloquea ese hilo, sino que también se bloquean todos los hilos del proceso.
  - Una aplicación multi-hilo no puede tomar ventaja del multiprocesamiento; un kernel asigna un proceso a sólo un procesador por vez.

##### Hilos a Nivel de Kernel

- **Caracteristicas**
  - El manejo de hilos es administrado por el kernel
  - Cualquier aplicación puede ser programada para ser multi-hilo
  - No hay código de manejo de hilo en el área de aplicación
- **Ventajas**
  - Las rutinas mismas del kernel pueden ser multi-hilo
  - Si un hilo se bloquea, el kernel planifica otro hilo del mismo proceso
  - Simultáneamente, el kernel, puede planificar múltiples hilos del mismo proceso en múltiples procesadores
- **Desventajas**
  - La transferencia de control de un hilo a otro dentro del mismo proceso le requiere al kernel un cambio de modo.
  - **Mayor costo** en términos de tiempo y recursos del sistema operativo.
  
#### Estado de los Hilos

Los hilos pueden seguir los mismos estados que los procesos:
1. Listo(spawn)
2. Bloqueado
3. Ejecutando
4. Terminado

![](/imgs/clase-2/Estados%20Hilos.png)

#### Estructuras de Uso de los Hilos

- **Estructura Servidor Trabajador**

Un hilo actúa como **servidor** que recibe solicitudes de trabajo y las asigna a **hilos trabajadores** inactivos, despertándolos para procesar las tareas.

![](/imgs/clase-2/Hilos%20Estructura%20servidor%20trabajador.png)

- **Estructura en Equipo**

Todos los hilos son **equivalentes** y **procesan sus propias solicitudes** de manera autónoma.

![](/imgs/clase-2/Hilos%20estructura%20en%20equipo.png)

- **Estructura de Entubamiento(pipeline)**

El procesamiento de datos se realiza en **etapas**; Cada hilo procesa una parte de la tarea y pasa los resultados al siguiente hilo en la cadena.

Este modelo se asocia con el concepto de **Pipelining**, debido a la similitud en el flujo de datos.

![](/imgs/clase-2/Hilos%20Estructura%20Entubamiento.png)


## Modulo 3: Planificación de Procesos

### Concepto de Planificación

> Orden en que ira cediendo el uso del procesador a los processo que lo vayan solicitando, y a las politicas que empleara para que el uso que den a dicho tiempo no sea excesivo respecto al uso esperado del sistema

### Objetivos

- **Ser justo:** Debe tratarse de igual manera a todos los procesos que compartan las mismas características, y nunca postergar indefinidamente uno de ellos (inanición o starvation)
- **Maximizar el rendimiento:** Dar servicio a la mayor parte de procesos por unidad de tiempo
- **Ser predecible:** Un mismo trabajo debe tomar aproximadamente la misma cantidad de tiempo en completarse independientemente de la carga del sistema
- **Minimizar la sobrecarga:** El tiempo que el algoritmo pierda en burocracia (overhead) debe mantenerse al mínimo, dado que éste es tiempo de procesamiento útil perdido
- **Equilibrar el uso de recursos:** Favorecer a los procesos que empleen recursos subutilizados, penalizar a los que peleen por un recurso sobreutilizado causando contención en el sistema
- **Evitar la postergación indefinida (starvation):** Aumentar la prioridad de los procesos más viejos, para favorecer que alcancen a obtener algún recurso por el cual estén esperando

### Tipos

- **A Largo Plazo**
  - Generacion de nuevos procesos
- **Mediano Plazo**
- **Extra largo plazo**

### Tipos de procesos

- CPU Bound -> operaciones que hacen uso del cpu 
- I/O Bounj -> hacen mas uso de entras y salidas que del cpu
- Procesos cortos .> Tipo I/O 