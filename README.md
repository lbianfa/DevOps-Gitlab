# Conceptos fundamentales de Gitlab

Antes de empezar debemos primero abordar Git y sus diferencias con Gitlab, para eso definamos los siguientes conceptos

## Repositorio

La definición literal de este término la podemos encontrar como, almacén o lugar donde se guardan ciertas cosas.

En el contexto del desarrollo de software la podemos definir como un espacio de almacenamiento donde se guardan todos los archivos relacionados con un proyecto de software, conservando el historial (rama) completo de los cambios (commit) realizados en cualquier archivo del proyecto.

## Estados de un archivo

Podemos entender cada modificación del contenido de un archivo como los estados de dicho archivo, por ejemplo para un archivo index.html, puede tener los siguientes estados:

1. Primero solo tiene un título h1
2. Luego tiene un párrafo además del título

## COMMIT

Es el registro del estado de uno o más archivos modificados, se puede entender analógicamente como los puntos de control de un videojuego, que guarda los avances del jugador en la historia del mismo.

## Atributos de un COMMIT

| Atributo          | Descripción                                                          |
| ----------------- | -------------------------------------------------------------------- |
| Hash              | Serial único de caracteres para identificar un COMMIT especifico     |
| Autor             | Responsable del COMMIT creado                                        |
| Fecha             | Día en el que fue creado                                             |
| Mensaje           | Texto corto que describe exactamente los cambios del COMMIT          |
| Estados o cambios | El o los estados de los archivos a los que hace referencia el COMMIT |
| Rama              | Rama a la que pertenece el COMMIT                                    |

---

En la siguiente imagen se puede observar el ejemplo de un COMMIT desde terminal:
![Ejemplo1](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731362654/Gitlab/commit_ahvl12.png)

En la siguiente imagen se puede ver el mismo COMMIT de ejemplo desde Gitlab:
![Ejemplo2](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731362797/Gitlab/commitGitlab_ffg8jr.png)

## Rama o Branch

Es el historial de COMMITs realizados en un repositorio, dicho de otra manera, es una línea de tiempo de los COMMITs realizados y pueden existir muchas ramas en un mismo repositorio, las cuales se entenderían como una copia del proyecto con la que cada desarrollador podrá desarrollar una nueva funcionalidad del software en la que estén trabajando, sin afectar la rama de producción o versión estable.

Una rama se diferencia por su nombre.

En la siguiente imagen se puede ver el ejemplo de una rama que contiene dos COMMITs desde una terminal:
![Ejemplo3](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731363385/Gitlab/rama_ou2ru0.png)

En la siguiente imagen se puede ver la misma rama de ejemplo desde Gitlab:
![Ejemplo4](https://res.cloudinary.com/dmvqwbpht/image/upload/v1731363531/Gitlab/ramaGitlab_j7mttu.png)

## Git

Es un sistema de control de versiones distribuido, ampliamente utilizado en desarrollo de software, que permite gestionar y rastrear los cambios realizados en un repositorio. Creado por Linus Torvalds en 2005.

Lo podemos entender también como una herramienta de terminal, que nos permite gestionar (crear, eliminar, modificar...) todo lo relacionado con nuestro repositorio, como COMMITs, Ramas o Branches, etc.

## Gitlab

Es uno de muchos servicios web para gestionar repositorios de manera remota, permitiendo el trabajo colaborativo de manera simultánea entre integrantes de un proyecto.
