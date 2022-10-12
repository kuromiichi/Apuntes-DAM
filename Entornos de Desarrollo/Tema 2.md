# Entornos de Desarrollo

## Contenidos

- [Traducción](#traducción)
- [IDE](#ide)

## Traducción

Se llama **traducción** de un programa al paso de un lenguaje de programación a lenguaje máquina que el ordenador puede procesar. Se realiza mediante un **traductor**, que puede ser un **compilador** o un **intérprete**. Sus principales fases son las siguientes:

- Análisis **léxico**: el _scanner_ analiza el código y lo separa en _tokens_.
- Análisis **sintáctico**: se comprueba la estructura y sintaxis del programa mediante el _parser_.
- Análisis **semántico**: se comprueba que el programa tenga sentido y no tenga errores.
- Generación de **código objeto**: se genera un código intermedio para optimizar el programa.
- **Optimización**: el código objeto se procesa para mejorar el rendimiento del programa.
- Generación de **código ejecutable**: finalmente se produce un fichero binario que puede ser ejecutado por el sistema operativo.

Según el tipo de traductor que utilicen, los lenguajes de programación se clasifican en tres grupos:

- Lenguajes compilados: un **compilador** traduce el código entero siguiendo todos los pasos para generar un fichero ejecutable _específico de cada sistema operativo_.
- Lenguajes interpretados: las líneas son leídas una a una por el **intérprete**, que debe estar instalado en la máquina que lo ejecuta.
- Lenguajes mixtos: el código fuente se traduce a un código intermedio que se ejecuta en una **máquina virtual** instalada en el sistema operativo correspondiente.

## IDE

Un **IDE** (_Integrated Development Environment_) es una aplicación informática compuesta por un conjunto de herramientas que facilitan la tarea del programador. 

Los entornos de desarrollo se usan independientemente del modelo de desarrollo que se utilice, y pueden ser para uno o varios lenguajes de programación.

Los entornos suelen estar compuestos por las siguientes herramientas:

- **Editor de texto**: permite escribir el código fuente del programa. Suelen ayudar al programador resaltando la sintaxis del lenguaje, marcando los errores léxicos y sintácticos y completando partes del código.
- **Compilador**: herramienta que traduce el código fuente a código máquina que el ordenador puede comprender.
- **Intérprete**: similar al compilador, traduce el código fuente línea por línea en tiempo de ejecución.
- **Depurador**: permite probar y eliminar posibles errores en el programa controlando la ejecución del programa (deteniendo, retrocediendo o avanzando línea por línea) y mostrando los datos de cada variable.
- **Constructor de interfaz gráfica**: permite diseñar las interfaces de forma intuitiva.
- **Control de versiones**: proporciona al programador control sobre los cambios que se realizan en todas las partes del programa a lo largo de su desarrollo.
- **Panel de configuración**: los IDEs permiten cambiar su aspecto o funcionalidad para amoldarse al gusto del usuario.
- **Plugins**: pequeñas extensiones que añaden funciones específicas al IDE.

### Apuntes de Joselu
[GitHub de Joselu](https://github.com/joseluisgs/EntornosDesarrollo-02-2022-2023)