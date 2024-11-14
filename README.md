
# Conceptos fundamentales de Gitlab

Antes de empezar debemos primero abordar Git y sus diferencias con Gitlab, para eso definamos los siguientes conceptos

## Repositorio

La definición literal de este término la podemos encontrar como, almacén o lugar donde se guardan ciertas cosas. En el contexto del desarrollo de software la podemos definir como un espacio de almacenamiento donde se guardan todos los archivos relacionados con un proyecto de software, conservando el historial (rama) completo de los cambios (Commit) realizados en cualquier archivo del proyecto.

## Estados de un archivo

Podemos entender cada modificación de un archivo como los estados de dicho archivo, por ejemplo para un archivo index.html, puede tener los siguientes estados:

1. Primero solo tiene un título h1
2. Luego tiene un párrafo además del título

## Commit

Es el registro del estado de uno o más archivos modificados, se puede entender analógicamente como los puntos de control de un videojuego, que guarda los avances del jugador en la historia del mismo.

## Atributos de un Commit

| Atributo | Descripción|
| ------ | ------ |
| Hash | Serial único de caracteres para identificar un Commit especifico |
| Autor | Responsable del Commit creado |
| Fecha | Día en el que fue creado |
| Mensaje | Texto corto que describe exactamente los cambios del Commit |
| Estados o cambios | El o los estados de los archivos a los que hace referencia el Commit |
| Rama | Rama a la que pertenece el Commit |
---
En la siguiente imagen se puede observar el ejemplo de un Commit desde terminal:
![Commit](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731362654/Gitlab/commit_ahvl12.png)

En la siguiente imagen se puede ver el mismo Commit de ejemplo desde Gitlab:
![CommitGitlab](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731362797/Gitlab/commitGitlab_ffg8jr.png)

## Rama o Branch

Es el historial de Commits realizados en un repositorio, dicho de otra manera, es una línea de tiempo de los Commits realizados y pueden existir muchas ramas en un mismo repositorio, las cuales se entenderían como una copia virtual del proyecto con la que cada desarrollador podrá trabajar una nueva funcionalidad del software, sin afectar la rama de producción o versión estable.

Una rama se identifica por su nombre.

En la siguiente imagen se puede ver el ejemplo de una rama que contiene dos Commits desde una terminal:
![Branch](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731363385/Gitlab/rama_ou2ru0.png)

En la siguiente imagen se puede ver la misma rama de ejemplo desde Gitlab:
![BranchGitlab](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731363531/Gitlab/ramaGitlab_j7mttu.png)

## Git

Es un sistema de control de versiones distribuido, ampliamente utilizado en desarrollo de software, que permite gestionar y rastrear los cambios realizados en un repositorio. Creado por Linus Torvalds en 2005.

Lo podemos entender también como una herramienta de terminal, que nos permite gestionar (crear, eliminar, modificar...) todo lo relacionado con nuestro repositorio, como Commits, Ramas o Branches, etc.

## Gitlab

Es uno de muchos servicios web para gestionar repositorios de manera remota, permitiendo el trabajo colaborativo de manera simultánea entre integrantes de un proyecto.

# Gestión de repositorios

`Realizar un laboratorio o explicación práctica de la gestión de repositorios local`

# Creación y clonación de repositorios remotos

`Realizar un laboratorio o explicación práctica de la creación y clonación de un repositorio remoto en Gitlab`

# Ramificación (Branching) y fusión (Merging)

La ramificación y fusión son dos procesos muy importantes en la gestión de repositorios, sobre todo para el trabajo colaborativo, ya que estos procesos van a permitir integrar los avances que cada desarrollador haya realizado al producto final de manera controlada, es decir, sosteniendo todo el historial de cambios de cada desarrollador.

## Ramificación o Branching

Consiste en crear copias de una rama, por lo regular de la rama principal o **main**, para trabajar sobre la copia, ya que esto nos permite realizar cambios que podrían generar errores sin afectar la rama principal o el ambiente de producción, permitiéndonos realizar pruebas o experimentos.

Existen varias prácticas sobre el cómo realizar las ramificaciones, aquí se exponen dos de las más populares:

 **1. Rama por usuario:** Consiste en crear una rama por desarrollador, es decir, cada integrante del equipo creará una rama propia con su nombre personal o nombre de usuario, es decir, una copia de la rama principal, estableciendo como nombre de la nueva rama el nombre personal o nombre de usuario. De esa manera, si el equipo tiene 3 desarrolladores, el repositorio tendrá al menos 4 ramas, 3 de cada desarrollador y la rama principal.

**2. Rama por feature o funcionalidad:** Consiste en crear una rama por la funcionalidad que se va a abordar, independientemente del número de integrantes, es decir, si se va a desarrollar un software con 2 funcionalidades, el repositorio tendrá al menos 3 ramas, 2 de cada funcionalidad y la rama principal.

Estas prácticas no son las únicas que existen y tampoco son una camisa de fuerza que todos deban adoptar, sino al contrario el mismo equipo de desarrollo debe escoger la práctica más útil para ellos, según sea su caso.

## Fusión o Merging

Ya entendemos entonces como dividirnos el desarrollo en un repositorio, pero ahora ¿cómo unimos los avances de cada desarrollador? Para esto existe el proceso de fusión o mayormente conocido como **Merging**, el cual nos permite unir el trabajo de cada integrante del equipo.

En términos técnicos, la fusión consiste en unir dos ramas en una, alineando los nuevos commits de cada rama.

### Diagrama de flujo sobre ramificación y fusión

En el siguiente diagrama puede ver un ejemplo de un repositorio que fue ramificado desde la rama main por dos ramas más llamadas Andres y Fabian, y como al final de la rama Fabian realiza un merge con la rama main.
![Branching&Mergin](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731448474/Gitlab/branching_merging_wcu1mk.png)

## Resolución de conflictos

En cualquier trabajo en equipo es normal que surjan conflictos, en este caso son conflictos técnicos que surgen luego de que dos o más integrantes del equipo modifiquen las mismas líneas de un mismo archivo y uno logre realizar el merge a la rama principal antes de que el otro integrante lo haga, en el siguiente diagrama se puede ver un ejemplo de cuando puede ocurre un conflicto:
![GitConflict](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731548827/Gitlab/git_conflict_otruwv.png)

Los conflictos se resuelven aceptando el cambio entrante o conservando el cambio actual, lo cual podemos abordar directamente desde GitLab o desde un editor de texto como VSCode.

## Creación de scripts de CI/CD
Antes de empezar a crear y ejecutar scripts en GitLab, definamos los siguientes conceptos:

### Script:
Es un conjunto de instrucciones o comandos que se escriben en un archivo y que son ejecutados de forma automática por un intérprete o programa, es decir, no requieren de un proceso de compilación. Están diseñados para realizar tareas concretas y específicas, sin necesidad de una estructura o entorno complejo que muchos lenguajes de programaciones convencionales sí necesitan. Son idealeas para entornos donde la rapidez y simplicidad de ejecución es prioritaria, como la automatización de tareas.

Los scripts se pueden ejecutar en varios lenguajes como:

- Javascript
- Python
- Bash
- Powershell

Estos 2 últimos son intérpretes de terminal o Shell.

### Shell:
Es una interfaz que permite a los usuarios interactuar con el sistema operativo. Es una de software que **interpreta** los comandos que el usuario escribe y los traduce en acciones que el sistema puede ejecutar. En otras palabras, la Shell actúa como intermediario entre el usuario y el sistema operativo.

Existen principalmente dos tipos de shell:

- **Shell de línea de comandos (CLI):** Esta es una interfaz de texto en la que el usuario escribe comandos para interactuar con el sistema operativo. Como por ejemplo PowerShell (Windows) y Bash (Linux)
- Shell gráfica (GUI): Es una interfaz visual que permite a los usuarios interactuar con el sistema operativo a través de ventanas, íconos y menús.

Sabiendo entonces que es un script y que es una shell, podemos entender ahora que los jobs de GitLab pueden ejecutar **scripts de shell**, como por ejemplo: `echo "hola mundo"`

### Mi primer job en GitLab
Sabiendo entonces que podemos ejecutar scripts de shell, vamos a crear nuestro primer job, para eso debemos, en la raíz de nuestro repositorio de GitLab, crear un archivo con el siguiente nombre y formato **.gitlab-ci.yml**, con el siguiente contenido:

```
mi_job:
  script:
    - echo "Mi primer script se ejecutó correctamente"
```

#### ¿Se puede ejecutar Python desde la shell de un Job de GitLab? Sí
La mayoría de cosas que se puedan ejecutar desde una shell también se pueden ejecutar desde un job de GitLab, ya que este se ejecuta con una shell, para ejecutar Python, su archivo **.gitlab-ci.yml** debe contener el siguiente código de ejemplo:

```
mi_job:
  script:
    - apt-get update
    - apt-get install -y python3 python3-pip
    - python3 ./my-script.py
    - echo "Mi primer script se ejecutó correctamente"
```

Como podemos notar, primero instalamos el intérprete de Python para luego ejecutar nuestro archivo de Python, y así nos toca instalar todos los programas y dependencias en nuestra shell para ejecutar los comandos que necesitemos. Pero esto puede llegar a ser tedioso y poco práctico, por eso GitLab nos permite indicar una imagen de [DockerHub](https://hub.docker.com/)  para iniciar con una shell que ya cuente con todo lo necesario para ejecutar los comandos, como por ejemplo:

```
mi_job:
  image: python:3.9
  script:
    - python3 ./my-script.py
    - echo "Mi primer script se ejecutó correctamente"
```

De esta manera, nuestro job va a iniciar con una shell en la que Python ya se encuentra instalado y solo necesitemos indicar los comandos de Python que queramos ejecutar.

## Despliegue automatizado (CD)

