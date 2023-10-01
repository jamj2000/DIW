> DISEÑO DE INTERFACES WEB

# Tema 3: Implantación de contenido multimedia  <!-- omit in toc -->



Derechos de la propiedad intelectual. Licencias. Ley de la propiedad intelectual. Derechos de autor.

Tipos de Imágenes en la Web.

Imágenes: mapa de bits, imagen vectorial. Software para crear y procesar imágenes. Formatos de imágenes.

Optimización de imágenes para la Web.

Audio: formatos. Conversiones de formatos (exportar e importar) .

Vídeo: codificación de vídeo, conversiones de formatos (exportar e importar) .


# Imágenes

## 

`object-fit` y `object-position`

Para obtener un ajuste agradable a la vista suele usarse `object-fit: cover;`.

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
 



> **Para saber más**:
>
> Es posible aplicar distintos filtros a una imagen. En el siguiente enlace tienes más información:
>
> - [MDN - Filter](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)

# Audio


# Vídeo


# Licencias



# Recursos

## Herramientas

- [Tabler Icons - Iconos SVG](https://tablericons.com/)
- [Font Awesome - Iconos SVG](https://fontawesome.com/search?o=r&m=free). Existe la posibilidad de descarga en formato SVG.
- [Unsplash - Imágenes gratuitas](https://unsplash.com/)
- [Open-source illustrations - Ilustraciones gratuitas](https://undraw.co/)
- [Get Waves](https://getwaves.io/)
