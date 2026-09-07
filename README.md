# Lectio — recursos públicos

Este repositorio contiene los archivos que la app **Lectio** necesita servir
públicamente. El código de la aplicación no vive acá.

Hay dos cosas:

- **Diccionarios bilingües** que la app descarga cuando el lector los pide,
  publicados como *releases* de este repositorio.
- **Política de privacidad**, servida por GitHub Pages, porque Google Play
  exige una URL pública que abra sin necesidad de iniciar sesión.

## Diccionarios

Lectio te deja tocar una palabra mientras leés y ver qué significa. Los
diccionarios no vienen dentro de la app: se descargan solo cuando elegís un
par de idiomas, y se pueden borrar desde Ajustes. Los doce pares juntos pesan
bastante más de lo que corresponde meter en un APK.

Cada archivo es un JSON comprimido con esta forma:

```json
{
  "meta": { "from": "eng", "to": "spa", "license": "CC-BY-SA-3.0", "words": 58855 },
  "entries": {
    "beach": {
      "t": ["playa", "embarrancar", "encallar", "varar"],
      "i": ["bit͡ʃ"],
      "d": "A horizontal strip of land, usually sandy, adjoining water."
    }
  }
}
```

`t` son las traducciones, `i` la pronunciación en AFI, y `d` una definición en
el idioma de origen. Las tres cosas juntas son deliberadas: la traducción le da
el significado a quien recién empieza, la definición es a lo que crece con el
tiempo, y el AFI le sirve a una app que corrige pronunciación.

Se generan con
[`tools/build-dictionary.mjs`](https://github.com/benjamin-dona/lectio) del
repositorio de la app, que convierte el formato `dictd` de FreeDict a este
JSON. Convertirlo una vez acá le ahorra al teléfono descomprimir 10 MB de texto
y recorrerlos linealmente en cada toque.

## Créditos y licencia de los diccionarios

Los datos vienen de **[FreeDict](https://freedict.org)**, construidos por
**[WikDict](https://www.wikdict.com/)** a partir de
**[Wiktionary](https://www.wiktionary.org/)** vía
**[DBnary](http://kaiko.getalp.org/about-dbnary/)**.

Están bajo **[Creative Commons Atribución-CompartirIgual 3.0](https://creativecommons.org/licenses/by-sa/3.0/deed.es)**
(CC-BY-SA 3.0). Los archivos convertidos que se publican acá **mantienen esa
misma licencia**: son obras derivadas, y CompartirIgual obliga a distribuirlas
igual. Cualquiera puede usarlos, incluso comercialmente, siempre que atribuya
a las fuentes de arriba y comparta las modificaciones bajo la misma licencia.

La licencia de estos datos es independiente de la licencia de la app.
