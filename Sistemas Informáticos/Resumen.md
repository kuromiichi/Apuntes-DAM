# Resumen sin ordenar (Sistemas Informáticos)

## Contenidos

- [Estructura de un sistema informático](#estructura-de-un-sistema-informático)
- [Representación de la información](#representación-de-la-información)
- [Arquitectura de ordenadores]()

## Estructura de un sistema informático

Un **sistema informático** está formado por el _hardware_, el _software_ y el _componente humano_.

- Hardware: representa la **parte física** del sistema informático (los componentes eléctricos y electrónicos que lo componen).
- Software: compone la **parte lógica** del sistema (el sistema operativo, el firmware y los programas).
- Componente humano: formado por **personas**; administradores de sistemas, creadores de hardware y software, y los usuarios, entre otros.

## Representación de la información

Los ordenadores trabajan con información digital, que codifica distintos niveles de tensión en 0 (tensión baja) y 1 (tensión alta). La información deben ser digitalizada para poder ser procesada. Para hacerlo, se emplean distintos tipos de codificación:

- Codificación **directa**: el dato a representar se corresponde con una combinación única de 0 y 1.
- Codificación por **campos**: la combinación se divide en distintos campos que codifican partes diferentes del dato.
- Codificación por **secuencias**: una combinación puede modificar el significado de la combinación que la sigue.

La información que se codifica con estas combinaciones se divide en **datos** e **instrucciones**:

- Los datos son información que puede ser tratada, almacenada y/o procesada por un ordenador.
- Las instrucciones son código máquina, es decir, códigos en binario que ejecutan una acción determinada por el procesador.

### Sistema binario

Para poder representar cantidades se usa un **sistema de numeración**, un conjunto de símbolos y reglas. Estos sistemas son posicionales (la posición del símbolo modifica su valor) y la base indica el número de símbolos que usa.

El sistema de numeración más usado es el **decimal** (base 10). Para transformar cantidades en otras bases a base decimal se usa el **teorema fundamental de la numeración**:

$$N = \sum_{i=-\infty}^{\infty} x_i b^i$$

donde $N$ representa la cantidad en decimal, $x$ es el dígito en la posición $i$, y $b$ es la base.

Para cambiar de base binaria a base hexadecimal se pueden agrupar los dígitos de cuatro en cuatro (o de tres en tres para octal) y traducirlos directamente.

En sistemas que necesitan representar **números del sistema decimal** (del 0 al 9) se usan códigos binarios decimales que están codificados directamente (BCD, Exceso a 3 o AIKEN, entre otros).


Los **números negativos** siguen varios sistemas:

- Módulo y signo: un bit determina el signo y el resto representan el número.
- Complemento a uno: se invierten todos los bits del número negativo.
- Complemento a dos: se complementa a uno y se suma uno. Des esta forma se evita tener +0 y -0.
- Exceso a M: se suma M a todos los números.

Para representar **números reales** se usa notación exponencial siguiendo el **Estándar IEEE 754** de precisión simple (32 bits) o precisión doble (64 bits).

- Precisión simple: 1 bit de signo, 8 bits de exponente y 23 bits de mantisa.
- Precisión doble: 1 bit de signo, 11 bits de exponente y 52 bits de mantisa.

Los **caracteres alfanuméricos** se codifican por los siguientes sistemas:

- BCD alfanumérico: 6 bits, 64 caracteres.
- EBCDIC: mainframes de IBM. 8 bits, 256 caracteres.
- ASCII: 7 bits, 128 caracteres imprimibles y no imprimibles, solo anglosajones.
- ASCII extendido: 8 bits, 256 caracteres. Añade caracteres de otros alfabetos.
- Unicode: tabla de más de 50000 símbolos con todos los alfabetos conocidos.
- UTF-8: Unicode de longitud variable. Incluye ASCII, bits de control y sincronismo.

### Sonido

El **sonido** es una onda mecánica analógica. Para representarlo, es necesario convertirla a una señal digital. Para ello, los conversores DAC (y ADC para el proceso opuesto) siguen unos pasos:

- Muestreo: se toman muestras de la señal a frecuencia constante.
- Cuantización: se aproxima un valor discreto a cada muestra.
- Codificación: los valores discretos se codifican a valores binarios.

### Imágenes

Para almacenar una **imagen** se descompone en una matriz de píxeles con valores binarios para cada píxel indicando su color. El tamaño del archivo de imagen se obtiene de la cantidad de píxeles multiplicada por el número de bits que codifican un píxel.

La codificación más usada actualmente es la de **True Color**, que usa 24 bits para cada píxel (8 bits por canal de color), o 32 si incluye el canal alfa (transparencia).

### Detección y corrección de errores

Para detectar errores en códigos binarios se añaden códigos redundantes que lo permiten. Hay distintos sistemas:

- Paridad: se añade un bit que vale 0 o 1 en función del número de unos que haya, haciéndolo par. Detecta errores en un bit pero no los corrige.

- Hamming: intercala bits de control en la palabra. Detecta errores en dos bits y puede corregir uno.

- Código de redundancia cíclica: se genera un código de detección que resulta del resto del código entre un algoritmo generador. Se usa en Internet.
