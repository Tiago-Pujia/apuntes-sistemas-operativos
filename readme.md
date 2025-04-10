# 📘 Introducción

> Material de cursada de la materia **Sistemas Operativos**  
> 📅 Inicio: 09/04/2025  
> 🎓 Alumno: Tiago Pujia | 👨‍🏫 Prof: Alexis Villamayor  
> 🕔 Comisión 3900 [3 = Miercoles, 9 = Turno noche]
> ▶️ [Clases Grabadas](https://www.youtube.com/)

## Indice

- [📘 Introducción](#-introducción)
  - [Indice](#indice)
- [Clase 1](#clase-1)
  - [¿Que es un sistema operativo?](#que-es-un-sistema-operativo)
  - [Funciones y Objetivos](#funciones-y-objetivos)
    - [Inicialización (proceso de arranque)](#inicialización-proceso-de-arranque)
    - [Maquina Extendida](#maquina-extendida)
    - [Administración de recursos](#administración-de-recursos)
    - [Aislamiento y Seguridad](#aislamiento-y-seguridad)
  - [Tipos de Sistemas Operativos](#tipos-de-sistemas-operativos)
    - [Segun la cantidad de usuarios](#segun-la-cantidad-de-usuarios)
    - [Segun la cantidad de procesadores que soporta](#segun-la-cantidad-de-procesadores-que-soporta)
    - [Segun la cantidad de procesos que ejecutan concurrentemente](#segun-la-cantidad-de-procesos-que-ejecutan-concurrentemente)
    - [Segun sus aplicaciones](#segun-sus-aplicaciones)
    - [Segun arquitectura](#segun-arquitectura)
  - [Interrupciones](#interrupciones)
    - [Definición](#definición)
    - [Clasificación](#clasificación)
      - [Segun prioridad](#segun-prioridad)
      - [Segun su origen](#segun-su-origen)
  - [Ejecucion de la programación](#ejecucion-de-la-programación)
  - [Consideraciones sobre Computo Paralelo](#consideraciones-sobre-computo-paralelo)
  - [Definiciones Computo Distribuido](#definiciones-computo-distribuido)

# Clase 1

## ¿Que es un sistema operativo?

Definiciones dadas por el profesor sobre s.o:

> Conjunto de módulos o funciones (software), que, instalados en la computadora, se ocupan de controlar y administrar la ejecución de los programas sobre los recursos que brinda el equipo (hardware), tales como: memoria, procesador, periféricos, etc.

> Conjunto de programas que ordenadamente relacionados entre sí, contribuyen a que la computadora lleve a cabo correctamente su trabajo para nosotros en un ambiente dado.

El **kernel** es el núcleo del sistema operativo. Es la parte más importante, encargada de: administrar hardware,

## Funciones y Objetivos

Un sistema operativo se basa en cumplir 4 caracteristicas:

### Inicialización (proceso de arranque)

![inicializacion](/imgs/clase-1/inicializador.png)

Al encender una computadora, se ejecuta un **chequeo inicial**, controlado por el firmware de la placa madre, ya sea **_BIOS_** o **_UEFI_**. Este proceso se encarga de inicializar y verificar el hardware esencial (como la memoria RAM, el procesador y los discos). Además, permite al usuario acceder a una interfaz de configuración, donde puede definir opciones como el orden de arranque.

Una vez completado este chequeo, el BIOS o UEFI busca un **dispositivo de almacenamiento** que contenga un **_MBR (Master Boot Record)_** válido. Este MBR se encuentra en el **primer sector físico del disco** (sector 0). En él se almacena una pequeña parte del **código de arranque**.

El BIOS transfiere el control al código ubicado en el MBR, el cual se encarga de identificar la **_partición activa_**, es decir, aquella que está marcada como booteable. Desde allí, el MBR accede al sector de arranque de dicha partición, donde se encuentra un puntero que lo dirige al **_gestor de arranque_** o **_bootloader_**.

El **_bootloader_** es un programa almacenado dentro del sistema de archivos del disco. Su función es **cargar el núcleo del sistema operativo (kernel)** en la **memoria RAM** y dar inicio a la ejecución del sistema, dejando el entorno preparado para que el usuario comience a trabajar.

### Maquina Extendida

Procedimiento que permite la interacciÓn del usuario con el ordenador. Existen diferentes interfaces

-   GUI (Grafica para Usuarios) -> KDE, Gnome, Aero
-   CLI (Linea de Comandos) -> Bash, cmd, powershell
-   NUI (Interfaz superior a la grafica) -> tactil, voz, gestos

### Administración de recursos

-   Mas del 70% del s.o esta dedicado a esta función
-   Gestiona politicas de asiognación de recursos o de uso
-   Optimiza los recursos

### Aislamiento y Seguridad

Garantizar la integridad de los recursos y procesos como, tambien validar los usuarios del sistema. Existen 2 modos para lograrlo:

-   Modo dual de ejecución del procesador
-   Juego de instrucciones diferenciadas del procesador

El modo dual de operaciones separa en 2 tipos de instrucciones:

-   Modo usuario o no privilegiado
-   Mood kernel o privilegiado (uso exclusivo para el s.o)

Si un usuario quiere usar instrucciones de kernel entra en un trap.

## Tipos de Sistemas Operativos

### Segun la cantidad de usuarios

-   Monousuario -> Un solo usuario
-   Multiusuario -> Varios usuarios (incluyendo remeoto)

### Segun la cantidad de procesadores que soporta

-   Uniprocesador -> Solo puede manejar un procesador de la computadora. Por lo que si tiene mas de un nucleo el cpu, es inutil.
-   Multiuprocesador -> Sistemas capaces de manejar mas de un procesador

### Segun la cantidad de procesos que ejecutan concurrentemente

-   Monoprogramado o monotarea -> Solo se puede ejecutar un proceso a la vez Recien cuando finalize, arranca el siguiente.
-   Multiprogramado(multitarea) -> mas de un proceso ejecutando el sistema

### Segun sus aplicaciones

-   Proposito general -> Propositos de amplia gama con cualquier fin
-   Proposito especial -> construccion a medida para un uso especifico. Se clasifica en:
    -   Tiempo real -> Tiempo de respuesta a eventos
        -   Tiempo Real No Crítico -> El tiempo de respuesta es importante, pero no vital
        -   Tiempo Real Crítico -> Requiere una respuesta inmediata
    -   Tolerante a fallas -> Se utilizan en aplicaciones donde es fundamental mantener un servicio continuo, incluso ante fallos de hardware o software. El mismo S.O detecta y corrige errores.
    -   Sistemas virtuales -> Los Sistemas Operativos Virtuales son capaces de administrar y gestionar otros sistemas operativos que se ejecutan de forma concurrente sobre el mismo hardware.

### Segun arquitectura

Existen 2 formas principales de organización del núcleo de un sistema operativo, junto a un enfoque híbrido:

-   Monoliticos

Todo el sistema operativo corre como un único proceso privilegiado. Todas las funcionalidades (gestión de memoria, archivos, dispositivos, etc.) están integradas directamente en el núcleo.

Ventajas: Alto rendimiento, gracias a la escasa necesidad de comunicación interna

![monolitico](imgs/clase-1/monolitico.png)

-   MicroKernel

El núcleo se limita a las funciones más básicas (como planificación y comunicación). Otras funciones del sistema (drivers, sistemas de archivos, etc.) se ejecutan como procesos sin privilegios.

Ventajas: arquitectura más modular y segura, fácil de mantener y extender.

![microkernel](imgs/clase-1/microkernel.png)

-   Hibridos

Combinan características de los dos anteriores: una base monolítica, pero con algunos componentes movidos a espacio de usuario.

La mayoría de los S.O. modernos, como Windows, adoptan este modelo por su equilibrio entre rendimiento y flexibilidad.

![hibrido](imgs/clase-1/hibrido.png)

## Interrupciones

### Definición

Repaso:

Un aviso que ocurrió algo con un periférico y puede ser o no atendido. Puede ocurrir en cualquier momento de la ejecución de un programa.

### Clasificación

#### Segun prioridad

-   No enmascarable -> Debe ser atentido si o si en el momento
-   Enmascarable -> No es urgente y se atiende cuando quiere

#### Segun su origen

-   software -> llamadas del sistema (syscalls)
-   Harware -> llamadas por un componente fisico. Se subdivide en:
    -   Interno -> Dentro del procesador
    -   Externo -> Fuera del procesador

## Ejecucion de la programación

-   Procesos Secuenciales -> Caada proceso se ejecuta a continuación del otro
-   Multiprogramación -> varios programas residen en la memoria al mismo tiempo y el procesador va cambiando entre ellos rápidamente. Da la ilusión de que se ejecutan al mismo tiempo, aunque en realidad se ejecutan uno por vez, compartiendo el procesador.
-   Multiprocesasmiento -> Procesos independientes, son paralelos
-   Multiprogramación y Multiprocesamiento -> Se combinan. Las mayorias de PC funcionan asi

![](/imgs/clase-1/ejecucion-programacion.png)

## Consideraciones sobre Computo Paralelo

-   Multiprocesamiento simetrico(smp) -> 2 procesadores iguales dentro del sistema
    -   Unifrm Memory Access(UMA) -> ambos procesadores comparten la memoria, utilizan un BUS compartido
    -   Non-Uniform Memory Access(NUMA) -> cada procesador tiene bancos de memoria. Da como ventajas que es mas rapido.
-   Multiprocesamiento asimetrico -> Varioss procesadores con objetos y arquitecturas diferentes

## Definiciones Computo Distribuido

Laburar con computadoras independientes en conjunto. Los tipos mas comunes son:

-   Clusters -> Se conectan maquinas en una red local donde cada maquina tiene un s.o y arriba hay un software donde administra todo la red
-   Grids -> Computadoras distintas a nivel geografico e interconectadas a una red
-   Computo en la nube ->
