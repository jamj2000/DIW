> DISEÑO DE INTERFACES WEB

# Tema 3: Implantación de contenido multimedia  <!-- omit in toc -->
> IMAGEN, AUDIO, VIDEO, LICENCIAS







---

# Imágenes

## Software para crear y procesar imágenes

**Visualizadores**

**Editores**

**Optimización de imágenes para la Web**


- Imágenes adaptables: [MDN -Responsive Images ](https://developer.mozilla.org/es/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)



## Tipos de imágenes

**Mapas de bits**

Un imagen de mapa de bits está compuesta por una cuadrícula de píxeles, organizados en una rejilla. Cada uno de los píxeles que conforma el mapa de bits tiene un color definido que presenta un valor.

Si hacemos zoom sobre la imagen podemos ver claramente cada uno de esos píxeles. Cuanto mayor sea el número de píxeles por imagen, mayor será su **resolución**. Por otro lado, los **píxeles por pulgada (ppi)** indican cuántos pixeles se muestran en una pulgada. Cuanto más alto sea este valor, mayor calidad en la visualización.


**Vectoriales**

Las imágenes vectoriales se basan en una serie de **coordenadas matemáticas que definen su posición, forma, color y otros atributos**. Estas imágenes se componen de vectores, que son unas figuras geométricas que pueden ser puntos, líneas, polígonos o segmentos. Por ejemplo, un rectángulo está definido por dos puntos, el círculo por un centro y un radio, mientras que una curva por varios puntos y una ecuación.

Eso sí, una imagen vectorial permite representar únicamente formas simples, lo que significa que no todas las imágenes se pueden describir con vectores.

A las imágenes vectoriales al estar compuestas por entidades matemáticas, se le pueden aplicar transformaciones geométricas a la misma, como ampliar, expandir o reducir, sin que pierdan nada de calidad, ya que continuaremos viendo las diferentes líneas y manchas de colores perfectamente definidas.

Además, las vectoriales permiten definir una imagen con muy poca información, lo que hace que los archivos tengan un tamaño bastante reducido.

> **Más información**: https://www.marcaprint.com/blog/diferencia-entre-bits-y-vectorial/

## Formatos

**GIF**

Características:

- Formato de mapa de bits.
- Usa comprensión SIN pérdida.
- 256 colores como máximo de paleta de 8 bits.
- Admite transparencia. No admite semitransparencia.
- Admite animaciones.
- Usado ampliamente en el pasado.
- Muy poco usado actualmente en la web.
- Muy usado en redes sociales y mensajería.


**JPEG**

Características:

- Formato de mapa de bits.
- Usa compresión CON pérdida.
- No admite transparencias.

**PNG**

Características:

- Formato de mapa de bits.
- Usa compresión SIN pérdidas.
- Admite transparencias.

**WEBP**

Características:

- Formato de mapa de bits.
- Usa compresión CON/SIN pérdidas.
- Admite transparencias.
- Admite animaciones.
- Código abierto.

> **Más información**: https://www.adslzone.net/reportajes/foto-video/webp-formato-ventajas/

**SVG**

Características:

- Formato vectorial.
- Permite reescalado sin pérdida de calidad.
- Ideal para logotipos y formas simples.
- No adecuado para fotografías.

 

## Ajuste

- Propiedades **`object-fit`** y **`object-position`**

Permite ajustar y posicionar una imagen en su área de visualización. Para obtener un ajuste agradable a la vista suele usarse **`object-fit: cover;`**.

Ejemplo:

```css
/* La imagen puede ser de inferior o superior tamaño al área de visualización. */
/* La imagen puede tener un ratio distinto al área de visualización. */
img {
  /* En este caso el área de visualización tiene un ratio 4:3 y tamaño 200x150 px */
  width: 200px;
  height: 150px;
  object-fit: cover;
}
```

Se mantiene el ratio de la imagen. Si la relación de aspecto de la imagen no coincide con la relación de aspecto del área visible, entonces la imagen se recortará para ajustarse.

Para fondos de página puede usarse la propiedad `background-size: cover;`

```css
body {
  backgroud-image: url('...');
  background-size: cover;
}
```


## Recorte

- Propiedades `clip-path` y `mask-image`.

Permite recortar la imagen según el contorno deseado. 
Por ejemplo, para recortar la imagen en forma de triángulo podemos hacer **`clip-path: polygon(50% 0%, 0% 100%, 100% 100%);`**

Existe un generador de recortes en https://bennettfeely.com/clippy/

![Clip Path](assets/clip-path.png)

Por otro lado, también podemos emplear la propiedad `mask-image` para el mismo fin. Consultar https://www.w3schools.com/css/css3_masking.asp

![Mask Image](assets/mask-image.png)

## Filtros 
 
- Propiedad **`filter`**

Permite aplicar ciertos filtros a la imagen. Por ejemplo, para aplicar un desenfoque hacemos **`filter: blur(5px);`**
En el siguiente enlace tienes más información:

- [MDN - Filter](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)

![Filter Blur](assets/filter-blur.png)

# Audio


Audio: formatos. Conversiones de formatos (exportar e importar) .


# Vídeo

Vídeo: codificación de vídeo, conversiones de formatos (exportar e importar) .

# Licencias

Derechos de la propiedad intelectual. Licencias. Ley de la propiedad intelectual. Derechos de autor.


# Recursos

## Herramientas

- [Tabler Icons - Iconos SVG](https://tablericons.com/)
- [Font Awesome - Iconos SVG](https://fontawesome.com/search?o=r&m=free). Existe la posibilidad de descarga en formato SVG.
- [Unsplash - Imágenes gratuitas](https://unsplash.com/)
- [Open-source illustrations - Ilustraciones gratuitas](https://undraw.co/)
- [Get Waves](https://getwaves.io/)
- [Clip Path Generator](https://bennettfeely.com/clippy/)

## Documentación
