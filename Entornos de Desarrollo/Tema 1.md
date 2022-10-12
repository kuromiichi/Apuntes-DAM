# Desarrollo de Software

## Contenidos

- [Definición de desarollo](#definición-de-desarrollo)
- [Fases del desarrollo](#fases-del-desarrollo)
- [Modelos de desarrollo](#modelos-de-desarrollo)

## Definición de desarrollo

El **desarrollo de software** se concibe como el proceso desde que se concibe una idea hasta que esta se implementa y se mantiene.

Se llama **ingeniería del software** a la ciencia y el arte de especificar, diseñar y desarrollar programas, documentación y procedimientos operativos.

## Fases del desarrollo

El proceso de desarrollo sigue una serie de pasos ordenados que garantizan la creación de programas fiables y eficientes.

1. **Planificación**: se define el ámbito del proyecto, sus objetivos y se estudia la viabilidad y el coste.

2. **Análisis**: se detalla exactamente la tarea que tiene que llevar a cabo el programa. Se concretan los requisitos funcionales y se llega a un modelo.

3. **Diseño**: en esta fase se decide _cómo_ se va a hacer el proyecto, dividiendo el problema en partes pequeñas y estudiando múltiples soluciones para elegir la más apropiada.

4. **Codificación**: los algoritmos diseñados se traducen al lenguaje de programación más adecuado y se implementa el proyecto.

5. **Pruebas**: permiten corregir los posibles errores (sintácticos o semánticos) mediante verificación y validación del código.

6. **Despliegue**: el programa se publica y se instala en la máquina del usuario final.

7. **Mantenimiento**: se asegura el correcto funcionamiento y se añaden funcionalidades al programa. Hay tres tipos:

    - Mantenimiento correctivo (eliminar defectos)
    - Mantenimiento adaptivo (adaptar lo existente)
    - Mantenimiento perfectivo (añadir funcionalidades)

## Modelos de desarrollo

Existen distintos **modelos** de desarrollo de software en función de cómo se organice el paso de una fase del desarrollo a otra. Los más importantes son los siguientes:

- Modelo en **cascada sin realimentación**: las fases del desarrollo van ordenadas y sólo se avanza de etapa cuando la anterior ha terminado, sin posibilidad de volver a una fase anterior. Es un modelo clásico que no se usa mucho actualmente.

- Modelo en **cascada con realimentación**: deriva del anterior, pero implementa la posibilidad de analizar el proyecto tras cada fase y volver a la anterior en caso de querer realizar algún cambio. Se usa mucho más que el modelo original.

- Modelo **evolutivo**: se basa en la creación de una versión inicial, que es mejorada con los comentarios del usuario a lo largo de varias versiones hasta que se alcanza un producto final. Tiene dos variantes:
    - Modelo **iterativo incremental**: basado en el modelo en cascada con realimentación, las fases se repiten y propagan sus mejoras a las siguientes fases.
    - Modelo en **espiral**: combinación del modelo iterativo y el modelo en cascada. Cuando se acaba una fase, se empieza a trabajar en la siguiente versión del proyecto (como una cadena de montaje). Las versiones van mejorando e incrementando la funcionalidad del programa.

### Apuntes de Joselu
[GitHub de Joselu](https://github.com/joseluisgs/EntornosDesarrollo-01-2022-2023)