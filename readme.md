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
      - [Caracteristicas](#caracteristicas)
      - [Ventajas respecto a los Procesos](#ventajas-respecto-a-los-procesos)
      - [Implementación de Hilos](#implementación-de-hilos)
        - [Hilos a Nivel de Usuario (ULT)](#hilos-a-nivel-de-usuario-ult)
        - [Hilos a Nivel de Kernel (KLT)](#hilos-a-nivel-de-kernel-klt)
      - [Estado de los Hilos](#estado-de-los-hilos)
      - [Patrones de Trabajo con Hilos](#patrones-de-trabajo-con-hilos)
    - [Fibra](#fibra)
      - [Definición](#definición-2)
      - [Caracteristicas](#caracteristicas-1)
      - [Ventajas](#ventajas)
  - [Modulo 3: Planificación de Procesos](#modulo-3-planificación-de-procesos)
    - [Definición](#definición-3)
    - [Objetivos](#objetivos)
    - [Tipos de Planificación](#tipos-de-planificación)
    - [Relación entre Tipos Planificadores y Estados de los Procesos](#relación-entre-tipos-planificadores-y-estados-de-los-procesos)
    - [Tipos de procesos](#tipos-de-procesos)
    - [Mediendo las respuestas](#mediendo-las-respuestas)
      - [Unidades de Medición](#unidades-de-medición)
      - [Métricas Utilizadas](#métricas-utilizadas)
    - [Clasificación Algoritmos de Planificación](#clasificación-algoritmos-de-planificación)
      - [Primero en Llegar, Primero Servido (FCFS) (Procesos Secuenciales)](#primero-en-llegar-primero-servido-fcfs-procesos-secuenciales)
      - [Round Robin (multiprogramación)](#round-robin-multiprogramación)
      - [El Proceso más Corto a Continuación (SPN, Shortest Process Next)](#el-proceso-más-corto-a-continuación-spn-shortest-process-next)
      - [El más Penalizado a Continuación (HPRN, Highest Penality Ratio Next)](#el-más-penalizado-a-continuación-hprn-highest-penality-ratio-next)
      - [Ronda Egoista (SRR)](#ronda-egoista-srr)
      - [Algoritmos con Múltiples Colas de Listos](#algoritmos-con-múltiples-colas-de-listos)

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

Las llamadas al sistema son expuestas al programador mediante las _interfaces de apliacación al programador_(API).

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

-   **¿Que es un Programa?**

> Conjunto de instrucciones que resuelven un problema

-   **¿Que es una Instrucción?**

> Unidad de ejecución que dura un tiempo finito y se ejecuta sobre un procesador. No se descompone ni interrumpe

-   **¿Que es un Proceso?**

> Porcion de un programa cargando en memoria central al cual se le asocia su contexto de ejecucion (run time environment) mediante una estructura de datos llamada vector de estado o **Bloque de Control del Proceso (PCB)**

Esa es la definición dada por los docentes, la que esta en el libro se define como:

> Un _proceso_ es la imagen en memoria de un programa, junto con la información relacionada con el estado de su ejecución

### Entidad Pasiva y Activa

-   **Entidad Pasiva**

No cambia por si mismo, no tiene actividad propia, solo es un conjunto de instrucciones a ser esperado. Ejemplo: Un **programa** almacenado en disco o memoria.

-   **Entidad Activa**

Cambia de estado mientras se ejecuta, tiene actividad propia (consume CPU, E/S y memoria). Ejemplo: Un **proceso** en ejecucion

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

-   **Procesos**
    Un proceso se define como la imagen de un programa en ejecucion; en memoria usando la CPU. A esta altura, un proceso tiene un espacio de direcciones de memoria, una pila, regitros y program counter (PC)

-   **Hilo(thread) o Proceso Liviano**
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

-   **Cambio de Contexto**

Mecanismo mediante el cual el Sistema Operativo guarda el estado actual de la CPU (registros, contador de programa, etc.) asociado al proceso en ejecución, para luego cargar el estado de otro proceso que debe ejecutarse

El cambio de contexto permite interrumpir un proceso y continuarlo más adelante desde el mismo punto donde quedó.

-   **Cambio de Proceso**

Ocurre cuando el Sistema Operativo decide suspender el proceso actual y darle la CPU a otro proceso diferenteo. El cambio se puede dar por distintos motivos, por ejemplo: Finalización de una tarea, Interrupciones del sistema.

Implica necesariamente hacer un cambio de contexto: primero se guarda el estado del proceso que se suspende y luego se carga el estado del nuevo proceso.

-   **Diferencia**

| Concepto               | ¿Qué hace?                                         | ¿Cuándo ocurre?                                                                            |
| ---------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **Cambio de Contexto** | Guarda el estado de un proceso y carga el de otro. | Cada vez que se cambia el proceso en ejecución.                                            |
| **Cambio de Proceso**  | Elige otro proceso para ejecutar.                  | Cuando el sistema operativo lo decide (fin de proceso, interrupción, planificación, etc.). |

#### Objetivos del PCB

-   Localización de la información sobre el proceso por parte del S.O
-   Mantener registrados los datos del proceso en caso de suspender la ejecución

#### Contenido del PCB

-   **Estado Actual del Proceso**
-   **Contador de Programa**: Cuál es la siguiente instrucción a ser ejecutada por el proceso
-   **Registros del CPU**: Debe ser respaldada y restaurada cuando se registra un cambio de estado
-   **Información de Planificación(scheduling)**: Prioridad del proceso, cola que tiene agendada
-   **Información de Administración de Memoria**: Información de mapeo de memoria
-   **Información de Contabilidad**: Información de la utilización de recursos que ha tenido este proceso
-   **Estado de E/S**: Listado de dispositivos y archivos asignados que el proceso tiene abiertos en un momento dado

Muchos de estos temas seran vistos a futuro.

### Transición de Estados de un Proceso

#### Tipos de Estados

Un proceso puede transitar por varios estados a lo largo de su vida dentro del sistema operativo:

-   **Nuevo (New):** Se solicitó al sistema operativo la creación de un proceso, y sus recursos y estructuras están siendo creadas (PCB). Ejemplo: Se abre un programa

-   **Listo (Ready):** El proceso ya está preparado para ejecutarse, pero todavía no se le ha asignado un procesador. Permanece en espera en la cola de procesos listos. Ejemplo: El programa ya esta cargado en memoria

-   **En Ejecución (Running):** El proceso está siendo ejecutado en este momento. El programa se empieza a ejecutar y se puede utilizar. Ejemplo: El programa empieza a ejecutarse y el usuario puede utilizarlo.

-   **Bloqueado (Blocked):** El proceso no puede avanzar porque está esperando a que ocurra algún evento (como la finalización de una operación de entrada/salida). Aunque haya un procesador disponible. El programa espera que el disco duro termine de abrir un archivo. Ejemplo: el programa espera que el disco duro termine de abrir un archivo.

-   **Zombie:** El proceso ha finalizado su ejecución, pero el sistema operativo debe realizar ciertas operaciones de limpieza para poder eliminarlo de la lista. Ejemplo: El programa terminó su ejecución, pero su información aún debe ser recolectada por el sistema operativo.

-   **Terminado (Exit):** El proceso terminó de ejecutarse; sus estructuras están a la espera de ser limpiadas por el sistema operativo. Ejemplo: Finalmente, el sistema elimina toda la memoria, PCB, y otros recursos asociados al programa.

#### Diagrama de Proceso

Un proceso puede pasar varias etapas diferentes en el sistema operativo, y el modelo depende del mismo. Hay varios modelos, pero el mas generico es el siguiente:

![](/imgs/clase-2/Modelo%20Generico%20Estados.png)

##### Modelo 7 Estados

![](/imgs/clase-2/Modelo%207%20estados.png)

Se crea un nuevo proceso que debe ser admitido, este se puede poner en listo o en listo/suspendido (esperando memoria). Cuando esta listo, esta esperando que el S.O le otorgue el CPU para ponerlo en ejecución. Cuando se encuentra en ejecución pueden pasar 2 cosas, finaliza o se bloquea por una interrupción

##### Modelo 5 Estados

![](/imgs/clase-2/Modelo%205%20Estados.png)

Modelo mas sencillo, no existe los estados de listo/suspendido o bloqueado/suspendido

#### Colas

Una cola es una estructura de datos donde los elementos se agregan al final y se sacan del principio. El primero que entra es el primero que sale.

Aplicado a procesos, una cola es donde se organizan los procesos que están esperando. Por ejemplo:

-   Cuando un proceso pasa al estado Listo, se pone en la cola de Listos.
-   Cuando un proceso está esperando por I/O, se pone en la cola de Bloqueados.

Todos los estados son de tipo cola, excepto los de ejecución. Porque, el CPU solo puede ejecutar un proceso a la vez.

#### Clasificación Estados

-   **Estados Activos**

Son aquellos que compiten por el procesador o están en condiciones de hacerlo. Estos son: ejecución, listo y bloqueado (no pueden ejecutarse de momento por necesitar algún recurso ).

-   **Estados Inactivos**

Son aquellos que no pueden competir por el uso del procesador. Estos son suspendido/bloqueado y suspendido/listo.

#### Razones de un Cambio de Estado de Proceso

-   Interrupciones de Hardware Externas
-   Excepción(trap)
-   Llamada al sistema operativo
-   Por finalización

### Creación de Procesos

#### Razones para crear un proceso

Todos los procesos son creados por el sistema operativo, aunque un proceso puede crear otro proceso. Hay 4 razones para crear uno:

-   La llegada de un trabajo nuevo al sistema.
-   Un proceso enviado por un usuario.
-   La necesidad de brindar un servicio a un programa en ejecución.
-   La creación explícita por parte de otro proceso existente.

#### Tipos de Creacion de Procesos

Cuando un proceso crea a otro, el proceso creador se llama **padre** y el proceso generado se llama **hijo**. Estos procesos suelen **comunicarse** y **cooperar** entre sí.

-   Jerarquia: Cada proceso que se crea es hijo del proceso creador y hereda el entorno de ejecución de su padre. Puede ser de 2 maneras:
    -   El padre continua ejecutando en paralelo con sus hijos
    -   El padre espera que todos sus hijos hayan terminado y luego sigue él.
-   No Jerarquica -> Se ejecutan de forma independiente

#### Secuencia de creación de un proceso

1. Asignar un identificador al nuevo proceso
2. Asignar espacio memoria para el proceso
3. Incializar la estructura de datos PCB
4. Establecer enlaces apropiados con otras estructuras del sistema operativo, como archivos abiertos, referencias a procesos padres, hijos o hermanos.
5. Ampliar o crear otra estructura de datos en caso que fuerza necesarios (archivos y de más)

#### Finalizar de un proceso

-   Desaparece el PCB
-   Liberar recursos comunes
-   Recursos locales son destruidos: Los datos como variables o memoria del stack

La **Terminación en cascada** es cuando un proceso termina (muere) tambien deben terminar sus hijos.

### Hilos

#### Definición

La simple transferencia de de memoria a el procesador con toda su planificación, podría llevara un desperdicio burocratico (tiempo que se pierde en asuntos administrativos) de recursos, una respuesta este problema son los hilos.El concepto de **hilo** (también llamados _threads_ o _procesos livianos_) ya fue mencionado anteriormente, pero realizamos un repaso:

> Dentro de un proceso pueden existir **secciones independientes** (hilos), cada una con su propio espacio de registros, pila y contador de programa. Sin embargo, **comparten el espacio de memoria** con los demás hilos del mismo proceso.

#### Caracteristicas

Cada hilo posee una estructura propia llamada **TCB** (_Thread Control Block_), que es similar al PCB de un proceso, pero contiene **menos información**, ya que muchos recursos son compartidos con los demás hilos del mismo proceso.

Cada hilo incluye:

-   Un **TID** (Thread Identifier)
-   Un **program counter (PC)**
-   Un conjunto de **registros de CPU**
-   Una **pila** propia

Cada hilo se ejecuta de forma **secuencial**, aunque en sistemas **multiprocesadores** pueden ejecutarse **en paralelo**.

Todos los hilos de un mismo proceso comparten:

-   Un único **espacio de direccionamiento en memoria**
-   Los **archivos y dispositivos abiertos**
-   El uso de **relojes y otros recursos del sistema operativo**

Además, los hilos pueden **crear hilos hijos**, y están diseñados para **cooperar entre sí** compartiendo los recursos mencionados.

#### Ventajas respecto a los Procesos

-   Requiere **menos tiempo** realizar un cambio de contexto entre hilos que entre procesos.
-   **Comparten espacio de memoria** y recursos, permitiendo una comunicación más rápida entre ellos.

#### Implementación de Hilos

##### Hilos a Nivel de Usuario (ULT)

**Características:**

-   Administrados completamente por el **usuario** mediante una librería en la aplicación.
-   Se crean en **tiempo de compilación**.
-   El sistema operativo **no tiene conocimiento** de su existencia.
-   Todo el proceso se ve como una sola unidad para el sistema operativo.

**Ventajas:**

-   El cambio entre hilos es **rápido** y no requiere cambiar a modo kernel.
-   Compatible con **cualquier sistema operativo**
-   El algoritmo de planificación puede ser **definido libremente** por el programador sin interferir con el planificador del sistema.
-   Se comparten memoria sin establecer mecanismos de comunicación, por lo que es más rapido

**Desventajas:**

-   No aprovecha **multiprocesamiento real**: el kernel solo ejecuta un hilo del proceso a la vez.
-   Las **llamadas bloqueantes** afectan a **todos los hilos del proceso**.
-   Se puede usar una técnica llamada **Jacketing** para transformar llamadas bloqueantes en no bloqueantes, pero esto **agrega sobrecarga** al sistema.

##### Hilos a Nivel de Kernel (KLT)

**Características:**

-   Administrados directamente por el **kernel del sistema operativo**.
-   Son completamente visibles y controlables por el sistema operativo.

**Ventajas:**

-   Las rutinas del **kernel también pueden ser multi-hilo**.
-   Si un hilo se bloquea, el kernel puede planificar otro hilo del mismo proceso.
-   Se puede ejecutar **múltiples hilos del mismo proceso en distintos procesadores**, logrando **paralelismo real**.
-   Aprovecha la comunicación con el sistema operativo tanto para solicitar recursos como para gestion de recursos en ejecucion multiprocesador

**Desventajas:**

-   El cambio de hilo requiere pasar a **modo kernel**, lo cual es más costoso.
-   Tiene **mayor overhead** (sobrecarga) en tiempo y recursos del sistema operativo.
-   Se requiere utilizar librerias para implementarlo

#### Estado de los Hilos

Los hilos pueden seguir los mismos estados que los procesos:

1. Listo(spawn)
2. Bloqueado
3. Ejecutando
4. Terminado

![](/imgs/clase-2/Estados%20Hilos.png)

#### Patrones de Trabajo con Hilos

Se puede emplear más de uno de estos patrones en diferentes áreas de cada aplicación

-   **Estructura Jefe/Trabajador**

Un hilo tiene una tarea distinta de todos los demás: el hilo _jefe_ genera o recopila tareas para realizar, las separa y se las entrega a los hilos _trabajadores_

Recomendado para servidores (como apache) y aplicaciones graficas (GUI).

![](/imgs/clase-2/Hilos%20Estructura%20servidor%20trabajador.png)

-   **Estructura en Equipo de Trabajo**

Se crean muchos hilos idénticos, que realizarán las mismas tareas sobre diferentes datos. Todos los hilos son **equivalentes** y **procesan sus propias solicitudes** de manera autónoma.

Recomendado para calculos matematicos.

![](/imgs/clase-2/Hilos%20estructura%20en%20equipo.png)

-   **Estructura de Entubamiento o linea de Ensablado(pipeline)**

El procesamiento de datos se realiza en **etapas**. Cada hilo puede enfocarse a hacer solo un paso y pasarlo los datos a otro hilo conforme vaya terminando. Todos los hilos cumplen tareas diferentes .Una de las ventajas es que ayuida a mantener rutinas simples de comprender, y permite que el procesamiento de datos continue, incluse si parte del programa está bloqueado.

Este modelo se asocia con el concepto de **Pipelining**, debido a la similitud en el flujo de datos.

![](/imgs/clase-2/Hilos%20Estructura%20Entubamiento.png)

### Fibra

#### Definición

Una **fibra** es una unidad de ejecución que debe ser **agendada manualmente** (`scheduler`) por la propia **aplicación**.

-   Las fibras se ejecutan dentro del contexto de un hilo
-   Un mismo hilo puede agendar y administrar **varias fibras** simultáneamente.

#### Caracteristicas

-   Las fibras no son planificadas por el sistema operativo, sino que su **cambio de contexto es controlado por la aplicación**.
-   Una fibra **no posee su propio hilo**: se ejecuta usando el hilo que la agenda.

#### Ventajas

-   En general, **una fibra no presenta ventajas** sobre una aplicación multi-hilo bien diseñada.
-   El uso de fibras puede **hacer más flexible** a aplicaciones que fueron pensadas para **agendar sus propios hilos** de ejecución.

## Modulo 3: Planificación de Procesos

### Definición

La _planificación de procesos_ se refiere a cómo determina el sistema operativo el orden en que irá cediendo el uso del procesador a los procesos que lo vayan solicitando, y a las politicas que empleara para que el uso que den a dicho tiempo no sea excesivo respecto al usop esperado al sistema.

### Objetivos

-   **Ser justo:** Debe tratarse de igual manera a todos los procesos que compartan las mismas características, y nunca postergar indefinidamente uno de ellos (inanición o starvation)
-   **Maximizar el rendimiento:** Dar servicio a la mayor parte de procesos por unidad de tiempo.
-   **Ser predecible:** Un mismo trabajo debe tomar aproximadamente la misma cantidad de tiempo en completarse independientemente de la carga del sistema
-   **Minimizar la sobrecarga:** El tiempo que el algoritmo pierda en burocracia (`overhead`) debe mantenerse al mínimo, dado que éste es tiempo de procesamiento útil perdido
-   **Equilibrar el uso de recursos:** Favorecer a los procesos que empleen recursos subutilizados, penalizar a los que peleen por un recurso sobreutilizado causando contención en el sistema
-   **Evitar la postergación indefinida (`starvation`):** Aumentar la prioridad de los procesos más viejos, para favorecer que alcancen a obtener algún recurso por el cual estén esperando
-   **Favorecer el uso esperado del sistema:** En un sistema con usuarios interactivos, darle prioridad a los procesos que sirvan a solicitudes iniciadas por los usuarios(aun a cambio de penalizar a los procesos de sistema).
-   **Dar Preferencia a los procesos que podrain causar bloqueo:** El proceso que esta ejecutando que puede causar un bloqueo, no los sacamos de encima rapido.
-   **Favorecer a los procesos con un comportamiento deseable:** Si un proceso causa mucha demora, se lo puede penalizar porque degrada el rendimiento del sistema
-   **Degradarse suavemente:** Tratar que no impacte la carga del proceso cuando este cerca del 100%; tratar de bajar la performance del sistema para que no afecte

### Tipos de Planificación

-   **Largo Plazo:** Generacion de nuevos procesos largos
    -   Se ejecuta periódicamente una vez cada varios segundos, minutos u horas
    -   Decide que procesos seran iniciados
    -   Modelo en deshuso
-   **Mediano Plazo (scheduler):** Toma decisiones conforme los procesos entran y salen del estado bloqueado
    -   Decide que procesos bloquear y activar. Esto ocurre debido a que los procesos típicamente se bloquean por escasez de algún recurso.
-   **Corto Plazo (dispatcher):** Decide entre los procesos listos para ejecutar, cual activar
    -   Decide cómo compartir momento a momento la CPU entre los procesos que la requieren
    -   Se ejecuta decenas de veces por segundo
    -   Se encarga de hacer el cambio de contexto
    -   Detiene aquellos que exceden su tiempo de procesador
    -   Ske busca una planificación a dar un tratamiento preferente a los procesos cortos. Porque no los sacamos rapido de encima.
-   **Extra largo plazo**
    -   El administrador decide que tarea realizar
    -   Modelo en deshuso

### Relación entre Tipos Planificadores y Estados de los Procesos

Los tipos de planificación incluyen los estados de procesos que van a trabajar:

-   **Largo Plazo:** Se encarga de las transiciones de nuevo a listo
-   **Mediano Plazo:** Se encarga de las transiciones de ejecución y bloqueado, y bloqueado y listo
-   **Corto Plazo:** Se encarga de las transiciones de listo y ejecución. Ejemplo:
    -   Ejecutando -> bloqueado => Llamada al sistema operativo
    -   Ejecutando -> listos => Interrupción por quantum (tema proximo)
    -   Bloqueado -> listos => Interrupción de finalización de E/S
    -   Ejecutado -> Terminado => Exit()

### Tipos de procesos

-   **CPU Bound:** Orientado al uso del CPU; procesos que alternan entre ráfagas y que realizan computo interno
-   **I/O Bound:** Orientado al uso de dispositivos externos; Procesos que realizan mas usos de entradas y salidas que del CPU
-   **Procesos Cortos:** Aquellos que son de tipo I/O Bound pero, cada tanto hace uso del CPU, y estan bloqueados esperando que se libera I/O

### Mediendo las respuestas

#### Unidades de Medición

Se laburan con 2 unidades para saber cuanto van a tardar:

-   **Tick:**
    -   Unidad de tiempo mínima en que el sistema operativo mide el paso del tiempo internamente.
    -   Cada Tick corresponde a una interrupción de reloj programada por el timer del sistema.
    -   Su duración lo determina el timer del sistema. En linux el tick es de 1 milisegundo y en windows entre 10 y 15ms
-   **Quantum:**
    -   Tiempo máximo que un proceso puede usar la CPU antes de ser interrumpido.
    -   En linux el quantum varia entre 10 y 200 ticks (10 y 200 ms) y en windows entre 2 y 12 ticks (10 y 180ms)

El Tick es como el "tic-tac" de un reloj muy rápido ⏱️. El Quantum es cuántos "tic-tac" seguidos puede quedarse un proceso usando el CPU antes de ser interrumpido. Ejemplo:

| Proceso | Ticks | Llegada |
| ------- | ----- | ------- |
| A       | 7     | 0       |
| B       | 3     | 2       |
| C       | 12    | 6       |
| D       | 4     | 20      |

El cambio de contexto se realiza cada 2 ticks, y un Quantum es de 5 ticks con un ordenamiento de ronda. Se operan con 4 procesos:

![](/imgs/clase-2/ticks%20grafico.png)

#### Métricas Utilizadas

Para un proceso _p_ que requiere de un tiempo _t_ de ejecución:

-   **Tiempo de respuesta(T):** Tiempo total desde que empieza hasta que termina su ejecución. Pero no esta en la cola de procesos, osea apartir desde que se le da el CPU.
-   **Tiempo Espera(E = T - t):** Tiempo total menos tiempo perdido; cuánto tiempo _p_ está listo y esperando ejecutar.
-   **Proporción de Penalización(P = T/t):** Tiempo total sobre tiempop de espera. Proporción tiempo de respuesta en relación al tiempo de uso del procesador.
-   **Proporción de Respuesta(R = t/T):** Inverso de P; fracción del tiempo de respuesta durante la cual _p_ pudo ejecutarse.
-   **Tiempo Núcleo o Kernel:** Tiempo que pasa el sistema en espacio de nucleo
-   **Tiempo de Sistema:** Espacio que pasa en una llamada al sistema
-   **Tiempo de Usuario:** Proceso en modo suario; ejecutando instrucciones que forman parte explícita y directamente del programa
-   **Tiempo de uso del Procesador:** Tiempo durante el cual el procesador ejecuto instrucciones por cuenta de un proceso(modo usuario o kernel).
-   **Tiempo desocupado (idle):** Tiempo en que la cola de procesos listos está vacía y no puede realizarse ningún trabajo
-   **Utilización CPU:** Porcentaje del tiempo en que el CPU realiza trabajo útil
-   **Valor Saturación** Formula en función de frecuencias de llegada al proceso(α) y el tiempo de servicio requerido para resolverlo(β). Se define por la división _p_ = α/β si:
    -   _p_ = 0 => Nunca lelgan procesos nuevos (sistema desocupado)
    -   0 < _p_ < 1 =>
    -   _p_ = 1 => Los procesos se despachan al ritmo que van llegando
    -   _p_ > 1 => El sistema esta saturado

### Clasificación Algoritmos de Planificación

El planificador a corto plazo, se invoca por alguna de las 4 circustancias:

-   Ejecutado a Espera
-   Ejecutado a Listo
-   Espera a Listo
-   Ejecutando a Terminado

Luego, los algoritmos se pueden clasificar por 2 tipos:

-   **Sistemas Expropiativo, Cooperativo o Non-Non-Preemptive,(desusho):** El sistema operativo no interrumpue el proceso en ejecución. Algunos de ellos son:
    -   FCFS
    -   SPN
    -   HPRN
-   **Sistema Apropiativos, No Cooperativo o Preemptive:** Son aquellos donde el reloj del sistema interrumpe periodicamente al proceso en ejecución para devolver el control al sistema operativo para decididir quien es el siguiente. Algunos ejemplos:
    -   Round Robin
    -   PSPN
    -   SRR

#### Primero en Llegar, Primero Servido (FCFS) (Procesos Secuenciales)

Funciona como una cola de procesos; el primero en llegar, es el primero que atiendo. Es el algoritmo mas simple. Presenta caracteristicas:

-   Reduce al minimo la sobrecarga administrativa (overhead)
-   Si hay procesos largos, se vera afectado el rendimiento
-   Favorece los procesos largos
-   Este algoritmo da salida a todos los procesos siempre que ρ ≤ 1. Si ρ > 1 la demora en iniciar a los nuevos procesos aumentará cada vez produciéndose inanición
-   No requiere hardware de apoyo

Ejemplo:

![](/imgs/clase-2/Algoritmo%20FCFS.png)

#### Round Robin (multiprogramación)

Es como una combinación al concepto de multiprogramación y FCFS; Tiene tambien un mismo sistema de colas, la diferencia radica en que cada tantos _t_ tiks de un proceso, alterna por otro proceso. Caracteristicas:

-    Favorece a los procesos cortos
-    Reduce al minimo la sobrecarga administrativa (overhead)
-   Busca dar una relación de respuesta buena para los procesos largos y cortos
-   Si un proceso no ha concluido dentro de su quantum se lo expulsará y será puesto al final en la cola de listos donde deberá esperar su turno nuevamente
-   Los procesos que son despertados de estado de suspensión son también puestos al final de la cola de listos
-   La ronda puede ser ajustada modificando la duracion de quantum. Conforme se incrementa quantum, mas se asemeja a FCFS.

![](</imgs/clase-2/Algoritmo%20Round%20Robin(1).png>)

![](</imgs/clase-2/Algoritmo%20Round%20Robin(2).png>)

#### El Proceso más Corto a Continuación (SPN, Shortest Process Next)

Se ordenada la cola de listos de acuerdo al mas corto. Llega a ser mas justo que FCFS. El problema que tiene es saber la duración del proceso, entonces lo que se haces es analizar ejecuciones anteriores. Presenta las caracteristicas:

-   Favorece a los procesos cortos
-   Mas justo que FCFS
-   Un proceso largo puede esperar mucho para su ejecución

![](/imgs/clase-2/SPN.png)

Tambien se cuenta con **PSPN** (Apropiativo SPN) que incluso favorece a los procesos largos, combina las ideas de SPN con un esquema multitarea apropiativo

#### El más Penalizado a Continuación (HPRN, Highest Penality Ratio Next)

Intenta situarse a un punto intermedio entre el FCFS (que favorece a los procesos largos) y SPN (que favorece a los cortos). Calcula un índice de penalización P para cada proceso que está en la cola:

```
P = (w+t)/t
```

Donde:

-   `w` = tiempo de espera del proceso
-   `t` = tiempo de CPU requerido

Elige el proceso con el mayor valor de P (el más "penalizado" por el tiempo que lleva esperando).

Presenta las caracteristicas:

-   Cuando hay muchos procesos en cola, calcular P para todos puede generar overhead.
-   Ayuda a evitar inanicisión _p_ < 1
-   Más justo que SPN y FCFS.

Inanicisión: Ocurre cuando un proceso o hilo nunca consigue acceso a un recurso porque otros procesos siempre son priorizados sobre él.  

#### Ronda Egoista (SRR)

Es una variante del Round Robin que introduce una distinción entre 2 colas de procesos:
- `Cola de procesos nuevos`
- `Cola de procesos aceptados` 

Mientras haya procesos aceptados listos, solo ellos compiten por la CPU. Los procesos nuevos esperan en procesos nuevos. Los procesos nuevos aumentan su prioridad mientras esperan. Cuando la prioridad de un proceso nuevo crece lo suficiente, se promueve a la cola de aceptados y empieza a competir.

Cuenta con los siguientes parametros:

- `a`: Ritmo al que sube la prioridad de procesos nuevos.
- `b`: Ritmo al que sube la prioridad de procesos aceptados.

Apartir del resultado dado por division b/a, se puede llegar a las siguientes conclusiones:

-   b/a = 0 => Se comporta como un Round Robin (todos los procesos compiten por igual)
-   b/a < 1 => Los procesos nuevos eventualmente seran aceptados
-   b/a >= 1 => Su comportamiento tiende a FCFS (los procesos nuevos pueden quedarse esperando mucho más)

Presenta las siguientes caracteristicas:

-   Favorece a procesos que ya llevan tiempo ejecutándose antes de aceptar procesos nuevos.
-   Mejora el rendimiento bajo alta carga

![](/imgs/clase-2/SRR.png)

#### Algoritmos con Múltiples Colas de Listos

Para poder entender el próximo algoritmo (multilevel feedback), primero se analiza cómo funciona típicamente un sistema con múltiples colas de listos.

![](/imgs/clase-2/multiples%20colas.png)

Se definen múltiples colas, cada una con una prioridad. Se atienden sólo los procesos de la cola de más prioridad hasta que ésta se vacía. Luego se pasa a ejecutar los procesos de la cola siguiente.
