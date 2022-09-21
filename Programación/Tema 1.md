# Introducción a la programación

## Contenidos

- [Algoritmos y programas](#algoritmos-y-programas)
- [Paradigmas de programación](#paradigmas-de-programación)
- [Lenguajes de programación](#lenguajes-de-programación)
- [Compiladores e intérpretes](#compiladores-e-intérpretes)

## Algoritmos y programas

Un **algoritmo** es una secuencia ordenada de pasos sin ambigüedad que resielve un problema. No depende de un lenguaje de programación, puede ser expresado con distintos lenguajes.

Un **programa** es el desarrollo de un algoritmo empleando un lenguaje de programacíón para que pueda ser procesado por un ordenador.

Todo programa se puede describir por medio de uno o varios algoritmos. Estos programas deben cumplir ciertas características fundamentales:

- Debe ser preciso y ordenado paso por paso.
- Debe estar definido, dando el mismo resultado cada vez que se ejecuta.
- Debe tener un numero finito de pasos, sin bucles infinitos.
- Debe ser legible y comprensible por una persona.

## Paradigmas de programación

Un **paradigma de programación** es el modelo o conjunto de reglas que define el diseño y la estructura de un programa. Según el conjunto de reglas se pueden hacer distintas cosas de distintas formas.

Existen numerosos paradigmas de programación:

- Programación estructurada
- Programación modular
- Programación declarativa
- Programación funcional
- Programación lógica
- Programación orientada a objetos
- Programación reactiva

## Lenguajes de programación

Los **lenguajes de programación** son conjuntos de reglas sintácticas, símbolos y palabras especiales que se usan para construir programas.

Sus principales componentes son:

- Gramática: son las reglas que aseguran la construcción de sentencias válidas.
- Léxico: representa el conjunto de símbolos y palabras especiales del lenguaje (_tokens_).
- Sintaxis: son las combinaciones de _tokens_ que dan lugar a sentencias.
- Semántica: es el significado de una sentencia, la acción que lleva a cabo.

Existen distintos **tipos de lenguajes** de acuerdo a varias clasificaciones.

Según su cercanía al programador:

- Lenguajes de **alto nivel**: son fáciles de entender por los humanos y tienen instrucciones intuitivas pero complejas. Ejemplos: C, C++, Java, Kotlin, Python...
- Lenguajes de **bajo nivel**: fáciles de entender por el hardware pero poco legibles para las personas, se componen de muchas operaciones sencillas. Ejemplos: ensamblador, código máquina...

Según su generación:

- Primera generación: lenguaje máquina (código binario).
- Segunda generación: lenguajes de tipo ensamblador.
- Tercera generación: primeros lenguajes de alto nivel: C, Pascal, COBOL...
- Cuarta generación: lenguajes capaces de generar código por sí solos (RAD, _Rapid Application Development_) que permiten desarrollar aplicaciones sin tener un amplio conocimiento del lenguaje.
- Quinta generación: lenguajes orientados a la inteligencia artificial, como LISP.

## Compiladores e intérpretes

Se llama **traducción** de un programa al paso de un lenguaje de programación a lenguaje máquina que el ordenador puede procesar. Se realiza mediante un **traductor**, que puede ser un **compilador** o un **intérprete**. Sus principales fases son las siguientes:

- Análisis léxico: el _scanner_ analiza el código y lo separa en _tokens_.
- Análisis sintáctico: se comprueba la estructura y sintaxis del programa mediante el _parser_.
- Análisis semántico: se comprueba que el programa tenga sentido y no tenga errores.
- Generación de código objeto: se genera un código intermedio para optimizar el programa.
- Optimización: el código objeto se procesa para mejorar el rendimiento del programa.
- Generación de código ejecutable: finalmente se produce un fichero binario que puede ser ejecutado por el sistema operativo.

Según el tipo de traductor que utilicen, los lenguajes de programación se clasifican en tres grupos:

- Lenguajes compilados: un **compilador** traduce el código entero siguiendo todos los pasos para generar un fichero ejecutable _específico de cada sistema operativo_.
- Lenguajes interpretados: las líneas son leídas una a una por el **intérprete**, que debe estar instalado en la máquina que lo ejecuta.
- Lenguajes mixtos: el código fuente se traduce a un código intermedio que se ejecuta en una **máquina virtual** instalada en el sistema operativo correspondiente.

### Apuntes de Joselu
[GitHub de Joselu](https://github.com/joseluisgs/Programacion-01-2022-2023#contenidos)