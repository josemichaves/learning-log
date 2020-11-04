# Tags

### Viewport Meta Tag

El visual viewport es lo que se ve en este momento en la pantalla, normalmente el viewport no coincide con el tamaño completo \(layout viewport\) de la web.

El `viewport meta tag` lo diseño Apple para que cuando una pagina se vea en una pantalla mas estrecha, se siga viendo bien, le de zoom y todo cuadre.

```markup
<meta name="viewport" content=" width=device-width, height=device-height, initial-scale=1" />
```

El `width` declara el ancho del viewport, puede estar especificado en pixeles o en el valor especial `device-width` que es el 100% del ancho de la pantalla en Pixeles CSS. Tambien hay `height`, con `device-height`, que es lo mismo.

El initial-scale declara el zoom con el que se inicia la pagina la primera vez que se ve. Tambien hay `maximum-scale`, `minimum-scale` y `user-scalable`.

Básicamente lo que hace, es escalar todo para que cuando un texto se vea en una pantalla mas pequeña, el layout viewport se adapte al viewport del móvil en este caso, y sea fácil de navegar por ella.

