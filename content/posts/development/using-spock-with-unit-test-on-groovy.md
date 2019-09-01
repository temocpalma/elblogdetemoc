+++
type="page"
title = "Creación de Pruebas Unitarias con Spock y Groovy"
pre ="<i class='fa fa-anchor'></i> "
weight = 1
date = "2017-09-07"
+++

*07-09-2017*

## Introducción
<!--more-->
La creación de pruebas automatizadas de software son una tarea aún poco apreciada en el desarrollo de software, ya que muchos lo consideran un trabajo "extra" no necesario de realizar, principalmente cuando el programador tiene ya dominio en la solución de problemas en el lenguaje en el que se desenvuelva; ya que muchas veces se escribe más código en las pruebas que en el componente que se está probando.

Sin embargo, esa forma de pensamiento, es equivocada. Las pruebas automatizadas son una herramienta que no sólo nos ayuda a garantizar en gran medida que el componente de software desarrollado funcione bien (que hace lo que tiene que hacer) sino que además nos ayuda a mejorar las buenas prácticas a la hora de programar (escribimos mejor código usando pruebas).

Además, ayudan a mantener la estabilidad de la aplicación completa, al poder ejecutarse de una forma muy rápida, cientos o hasta miles de pruebas de los componentes involucrados en ella, de forma que cuando algún programador cambia o modifica lógica de esos componentes tendrá que ajustar o complementar los tests relacionados, de lo contrario, las pruebas fallarán.

## Definiciones

* **Pruebas Unitarias:** Son pruebas que se aplican a un componente muy específico de la aplicación (un método). Son las más básicas de las pruebas, y en ella no se consideran afectaciones a la base de datos o archivos de configuración de la aplicación, por lo que esos elementos se "emulan" para fines de la prueba.

* **[SpockFramework](http://spockframework.org/):** Es un framework que nos ayuda a crear pruebas usando un notación muy intuitiva (*especificaciones*), para aplicaciones Java y Groovy.

* **[Groovy](http://groovy-lang.org/):** Es un lenguaje dinámico para plataforma de Java.

## Ejemplo

Para mostrar básicamente cómo crear pruebas unitarias con Spock, usaré una pequeña aplicación Groovy con [Gradle](https://gradle.org/). La aplicación consiste en clasificar a una persona en un grupo dada su edad de la siguiente manera: 

 - 0 - 11 años, Infantes
 - 12 - 18 años, Adolescentes
 - 19 - 30 años, Jóvenes
 - 30 - 60 años, Adultos
 - 61 o más, Adultos Mayores

### Agregar la dependencia a la aplicación

Lo primero es agregar la dependencia necesaria a la aplicación para poder utilizar el framework (en el archivo *build.gradle*):

```groovy
testCompile "org.spockframework:spock-core:1.1-groovy-2.4"
```

### Creando las pruebas

Dentro de la carpeta de pruebas de la aplicación (*src/test/groovy/com/exampletests/org*) creamos la clase de pruebas correspondiente, con un test de ejemplo:

```groovy

package com.exampletests.edu

import spock.lang.*

class ClasificationServiceSpec extends Specification {
  
  void "Example test"() {
    setup:
      int a=1
      int b=0
    when:
      def result = a + b
    then:
      result == 1
  }

}

```

Para ejecutar los test, en la consola de comandos, ubicados en la carpeta raíz del proyecto de la aplicación, tecleamos: ```gradle test```

La especificación (el test) en este ejemplo incluye 3 secciones: 

**setup**, para inicializar los valores necesarios para la prueba

**when**, donde se indica el proceso que se quiere probar con los valores definidos en la sección anterior

**then**, donde se definen los resultados esperados del proceso

Las secciones requeridas son **when** y **then**

### Creando las pruebas para solucionar el problema

Cambiemos la prueba anterior por la siguiente:

```groovy

  void "Should get CHILDREN category when the age is between 0 and 11 years old"() {
    given:
      int age = 5
    when:
      String category = classificationService.getCategoryForAge(age)
    then:
      category == "CHILDREN"
  }

```

Si se corren las pruebas con el comando ```gradle test``` arrojará un error, ya que el elemento **classificationService** no existe aún y la clase de pruebas no la tiene definida.

Vamos a crear la clase de servicio con el método que devolverá la categoría correspondiente según la edad que se indique. En la carpeta **src/main/groovy/com/exampletests/edu** tecleamos el siguiente código:

```groovy

package com.exampletests.edu

class ClassificationService {
  
  String getCategoryForAge(int age) {
    "CHILDREN"
  }

}
```

Ahora en la clase de pruebas, agregamos una instancia de la clase de servicio:

```groovy
 
class ClasificationServiceSpec extends Specification {
  
  ClassificationService classificationService = new ClassificationService()

  void "Should get CHILDREN category when the age is between 0 and 11 years old"() {
    ...
  }

}
```

Ejecutemos las pruebas nuevamente con el comando ```gradle test```, ahora no debería haber errores.

Bien, la prueba creada sólo cubre un sólo caso de todos los que el componente puede responder. Para incluir los otros casos, usaremos una tabla de datos.

En nuestra clase de pruebas, agreguemos la siguiente *especificación*:

```groovy
  
  @Unroll
  void "Should get the category #theCategory when the age is #theAge"() {
    given:
      int age = theAge
    when:
      String category = classificationService.getCategoryForAge(age)
    then:
      category == theCategory
    where:
      theAge              ||      theCategory
        5                 ||      "CHILDREN"
        15                ||      "TEENAGERS"
        25                ||      "YOUNGS"
        35                ||      "ADULTS"
        45                ||      "ADULTS"
        65                ||      "OLDERS"
        -1                ||      "UNDEFINED"
  }

```

Al ejecutar los tests nuevamente, no debería haber errores.

Hagamos que uno de los registros de la tabla de datos falle. Cambiemos el valor esperado de la fila con la edad 35 a "YOUNGS", y corramos las pruebas.

Ahora el resultado debería ser fallido, mostrando los resultados como se muestra en la figura siguiente:

<img src="/img/spock/failed.png" title="Prueba fallida" />

Podemos ver que en el resultado mostrado nos indica en el nombre del test los valores usados, que fueron los que fallaron. Además vemos que hay una referencia a un archivo html, generado por el framework, el cuál es un reporte bastante completo sobre las pruebas, si lo abrimos podemos ver la lista de las pruebas fallidas:

<img src="/img/spock/failed-report-list.png" title="Reporte de tests fallidos" />

Al darle clic al link del nombre del test fallido, nos da un reporte de la falla para este test en particular:

<img src="/img/spock/failed-report-detail.png" title="Detalle de test fallido" />

Como se puede observar, la creación de pruebas unitarias usando Spock, es bastante sencillo. El framework nos da un reporte bastante útil para poder ir resolviendo las fallas de los componentes correspondientes.

