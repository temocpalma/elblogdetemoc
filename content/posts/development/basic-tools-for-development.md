+++
type="page"
title = "Herramientas básicas para desarrollo de software"
pre ="<i class='fa fa-anchor'></i> "
weight = 2
date = "2019-08-10"
+++

*10-08-2019*

## Introducción
<!--more-->
Desde hace poco más de tres años empecé a conocer varias herramientas que considero son básicas para todos los que nos dedicamos a este "oficio".

El motivo de enlistarlas en este post, es para aquellos que (como yo en su momento) no saben que existen dichas herramientas y que (por experiencia propia) te facilitan muchísimo el trabajo como programador.

No es el fin de este post ser un tutorial de cómo instalarlas o usar estas herramientas, pero sí daré una breve descripción personal de ellas.


## Las herramientas

* **Git.** Para mi, una de las maravillas del mundo del desarrollo de software. Git es un sistema de control de versiones, nos ayuda a controlar los cambios que hagamos sobre un proyecto, a controlar el proceso de desarrollo colaborativo (combinado con una herramienta web como GitHub, GitLab o BitBucket). Es también una herramienta clave para implementar *Integración Continua/Entrega Continua*. La [documentación](https://git-scm.com/book/es/v1/Empezando) online para mi fue suficiente y clara para usarlo básicamente, por lo que la recomiendo para quienes esto es algo nuevo.

* **Editor de textos.** Hubo un tiempo en que usaba IDE's para programar (NetBeans, MS Visual Studio), y en ese entonces mi opinión era muy buena de los IDE's, sigo diciendo que son buenas herramientas, pero ahora que he estado programando sólo con Editores de texto, no los he extrañado para nada, y hasta pienso que se me complicaría regresar a usarlos :)

	¿Por qué pienso eso? Si lo tengo que decir en pocas palabras, diré que es por la gran facilidad que los editores de texto te dan a la hora de escribir código, evitas esa pequeña espera que los IDE's tienen al abrilos, evitas algunas configuraciones e instalación de plugins que son medio engorrosos. Por otro lado, pierdes la ayuda de sintaxis y tal vez autocompletado y autoimportaciones, pero esto no ha sido tan imprescindible, al menos en mi caso.

	¿Qué editores recomiendo? 

	*Vim*, es el que más tiempo he utilizado, tal vez al principio da la impresión de que es complicado su uso por los comandos que son distintos a los que estamos acostumbrados para la edición de textos y por la forma en que se manipulan estos textos (prácticamente todo se hace con el teclado, te olvidas que existe el mouse), pero nada que con la práctica no se pueda cubrir. Además hay muchos plugins que se le pueden agregar muy fácilmente para mejorar la experiencia, en particular yo uso el gestor de paquetes [Pathogen](https://github.com/tpope/vim-pathogen) para instalarlos. 

	*Sublime* es otro editor que también uso de vez en cuando, es muy ligero y bastante intuitivo, por default ya trae varios plugins que te ayudan en la escritura de código y la edición de texto es más parecida a las usadas en las procesadores de texto populares, y acá sí le puedes dar uso al mouse para realizar tareas.

	*Visual Studio Code*. Este editor es el que he estado usando desde hace algunos meses, con un proyecto en React, y aunque es más pesado que los anteriores, creo que es una buena opción también. Al igual que sublime, la edición de texto es similar a la forma de los procesadores de texto populares. Además trae una terminal de línea de comandos integrada, que te ayuda a ejecutar algunas tareas sin necesidad de abrir la terminal propia del sistema operativo.

* **Administradores de versiones.**

	Cuando te toca trabajar en varios proyectos de desarrollo en períodos de tiempo no tan largos, es muy probable que entre ellos tengas que usar distintas versiones de los lenguajes y herramientas de programación. Es en este caso donde se hacen bastante útiles los gestores de versiones para poder cambiar fácilmente entre las que necesites en un determinado momento.

	Los gestores que he usados son: **sdkman** para gestionar versiones de herramientas de programación para la JVM (java, groovy, gradle, maven, grails); **rvm** para versiones de ruby; y **nvm** para versiones de node.

* **Terminal.** 

	Por último, considero que el uso de la Terminal de línea de comandos es básico para el desarrollo de software. Con ella además de ayudarte a ejecutar operaciones de manejo de archivos del SO y a instalar herramientas en el sistema, también te ayuda bastante a realizar tareas propias del desarrollo, como ejecutar scripts de código, "levantar" un proyecto, monitorear logs de una aplicación, conectarte a servidores remotos por ssh, listar y eliminar procesos del sistema operativo, ejecutar comandos de git, consumir webservices con curl, entre otras.

	En Linux o Mac, el uso de la terminal para las tareas mencionados es bastante común, y puedes usar la terminal con la shell que por defecto viene (bash), pero recomiendo cambiarla a **ZShell** porque te permite personalizar, a través de temas, la forma en que se muestran cosas en la terminal (como el propmt, información de la barra de estado, estatus del repositorio git).

	Otra herramienta bastante útil para la terminal es **Tmux**, que te permite tener varias "pestañas" dentro de una misma ventana de la terminal,lo que te evita abrir varias ventanas de ella. Esto te da la posibilidad de que dividas la pantalla en varias secciones y así, por ejemplo, puedas monitorear un log de una aplicación en una de ellas, en otra, ejecutes algún script, en otra veas la salida en consola de otra aplicación, o muestres los procesos y uso de la memoria y los procesadores (htop). 

## Otros aspectos

Para terminar con este post, mencionaré algunas cosas más que no son propiamente herramientas de desarrollo, pero que definitivamente te ayudarán a hacer el trabajo de una forma más cómoda y a gusto.

Si trabajas con una laptop (como es mi caso), te recomiendo uses una base, con ella elevarás la pantalla y te ayudará a conservar una mejor posición mientras escribes código. Esto te implicará usar un teclado y mouse externos para trabajar.

Monitor adicional. Ya sea que trabajes con una PC o una laptop, tener un monitor adicional te facilitará mucho el trabajo de codificación, al poder tener a la vista más información relacionada con tu proyecto sin tener que estar cambiándote de una ventana a otra. Considero que un tamaño de 19 pulgados del monitor extra es muy bueno.

Silla cómoda. Generalmente cuando estamos desarrollando pasamos bastante tiempo sentados, por lo que la silla que usemos para ello debería ser lo suficientemente cómoda. Te evitará malas posturas que puedan ocasionarte cansancio en hombros o espalda. Aún teniendo una buena silla, en particular, procuro no estar sentado más de 2 horas continuas y tomarme descansos de unos minutos para caminar y estirarme un poco.
