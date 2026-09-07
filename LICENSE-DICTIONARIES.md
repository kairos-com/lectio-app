# Licencia de los diccionarios

Los archivos de diccionario publicados en los *releases* de este repositorio
son obras derivadas de [FreeDict](https://freedict.org), y se distribuyen bajo
la misma licencia que los originales:

**Creative Commons Atribución-CompartirIgual 3.0 Unported (CC-BY-SA 3.0)**
<https://creativecommons.org/licenses/by-sa/3.0/>

## Atribución

| Qué | Quién |
|---|---|
| Diccionarios originales | [FreeDict](https://freedict.org) |
| Construcción automática | [WikDict](https://www.wikdict.com/) |
| Datos de base | [Wiktionary](https://www.wiktionary.org/) |
| Extracción estructurada | [DBnary](http://kaiko.getalp.org/about-dbnary/) |

## Qué se cambió respecto del original

Estos archivos no son copias: se convirtieron del formato `dictd` (un blob
comprimido con dictzip más un índice de desplazamientos en base 64) a un único
objeto JSON, para que un teléfono pueda consultarlos sin descomprimir el
diccionario entero en memoria en cada búsqueda.

En esa conversión, por cada palabra se conservan:

- hasta cuatro traducciones,
- una transcripción AFI,
- una sola definición.

El resto de las acepciones se descarta. Guardar todas triplicaba el tamaño del
archivo para un detalle que nadie lee en mitad de un párrafo.

## Qué implica CompartirIgual

Podés usar estos archivos para lo que quieras, incluso comercialmente, siempre
que atribuyas a las fuentes de la tabla de arriba y distribuyas cualquier
modificación bajo esta misma licencia.

CC-BY-SA aplica a **estos datos**, no a las aplicaciones que los consultan.
Una app puede descargarlos y usarlos sin que su propio código quede sujeto a
esta licencia; lo que sí debe hacer es mostrar la atribución.
