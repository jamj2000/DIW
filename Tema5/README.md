> DISEÑO DE INTERFACES WEB

# Tema 5: Desarrollo de Webs accesibles  <!-- omit in toc -->
> LAYOUTS, FLEX, GRID, RESPONSIVE, MEDIA QUERIES

- [1. Introducción](#1-introducción)
- [2. Flex](#2-flex)
  - [2.1. Terminología](#21-terminología)
  - [2.2. Propiedades del contenedor](#22-propiedades-del-contenedor)
  - [2.3. Propiedades del item](#23-propiedades-del-item)
- [3. Grid](#3-grid)
  - [3.1. Terminología](#31-terminología)
  - [3.2. Propiedades del contenedor](#32-propiedades-del-contenedor)
  - [3.3. Propiedades del item](#33-propiedades-del-item)
- [4. Media queries](#4-media-queries)
  - [4.1. Mobile first](#41-mobile-first)
  - [4.2. Desktop first](#42-desktop-first)
- [5. Recursos](#5-recursos)
  - [5.1. Herramientas](#51-herramientas)
  - [5.2. Formación](#52-formación)


---

# 1. Introducción

Se entiende como `layout` a la disposición de elementos en una página web. En sus inicios, los diseñadores web maquetaban usando etiquetas html como `table`, `frameset` y otras parecidas. Con la llegada de los móviles estas formas de crear el `layout` se demostraron claramente inadecuadas. 

Aparecieron entonces dos nuevas formas de maquetar mucho más amigables con el diseño, tanto en pantallas de PC/portátil como en pantallas de móviles. Estas dos nuevas técnicas se conoce como **`flexbox`** (o simplemente `flex`) y **`grid`**.

Aunque ambas técnicas tienen bastantes similitudes, y hay casos en los que puede emplearse una u otra de forma indistinta, podemos resumir y aconsejar usar:

- flex para disposición de elementos en una dimensión
- grid para disposición de elementos en dos dimensiones

Debido a la gran cantidad de funcionalidades que proporcionan cada una de estas técnicas, se aconseja al lector consultar en profundidad los enlaces proporcionados en este tema. Por mi parte, para no crear confusión al intentar abordar todas las propiedades disponibles, sólo nombraré las más habituales y útiles y dejaré para su consulta las más específicas.

# 2. Flex

Disposición **flexible**
- Referencia: [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


## 2.1. Terminología

![terminología flex](assets/flex-basic-terminology.svg)

En flex trabajaremos principalmente con el **`eje principal`**, que es el eje a lo largo del cual se colocan los elementos flexibles. Ojo, no es necesariamente horizontal; Depende de la propiedad `flex-direction`, que puede tomar los siguientes valores: `row`, `columm`, `row-reverse`, `columm-reverse`.

![flex direcciones](assets/flex-direction.svg)

El `eje transversal` es el eje perpendicular al eje principal. 


## 2.2. Propiedades del contenedor

**Ejemplo:**

```css
display: flex;
gap: 10px;
flex-direction: row;
flex-wrap: wrap;
justify-content: space-between;
align-items: center;
align-content: center;
```

> **NOTA**: También existen las propiedades `row-gap` y `column-gap` de forma independiente.

> **IMPORTANTE**: 
>
> - `justify-content` distribuye elementos en el eje principal, ¡no necesariamente horizontal! 
> - `align-items` distribuye elementos en el eje transversal, ¡no necesariamente vertical!
>
> Por ejemplo, para ver con se comporta la propiedad `justify-content` en distintas orientaciones, prueba a cambiar la propiedad `flex-direction` usando cada uno de los siguientes valores: `row`, `column`, `row-reverse` y `column-reverse`
> 
>
>```html
>    <div style="display: flex; flex-direction: column; height: 100vh; justify-content: space-between;">
>        <div style="width: 20px; height: 20px; background-color: lightgray;"> 1 </div>
>        <div style="width: 20px; height: 20px; background-color: lightgray;"> 2 </div>
>        <div style="width: 20px; height: 20px; background-color: lightgray;"> 3 </div>
>    </div>
>```
 

## 2.3. Propiedades del item

**Ejemplo:**

```css
order: 1;          /* default is 0 */
flex-grow: 2;      /* default 0 */
flex-shrink: 2;    /* default 1 */
flex-basis: 100px; /* default auto */
flex: 0 1 auto;    /* shorthand para grow shrink basis */
align-self: flex-end;
```

# 3. Grid

Disposición en **cuadricula**
- Referencia: [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)


## 3.1. Terminología

A diferencia de flex, en grid los ejes no cambian de dirección. Los ejes en grid son:

- **`el eje de fila, eje horizontal o inline`**
- **`el eje de columna, eje vertical o block`**

Podemos concebir la cuadrícula o grid de dos maneras:

- **mediante líneas de cuadrícula**
- **mediante áreas**

![grid líneas](assets/grid_lines.png)

![grid areas](assets/grid-template-areas.svg)


## 3.2. Propiedades del contenedor

```css
display: grid;
gap: 10px;
place-content: center center;  /* shorthand para align-content justify-content */ 
grid-template-columns: 50px 50px 50px 50px;
grid-template-columns: repeat(4, 1fr);
grid-template-rows: auto;
grid-template-areas: 
    "header header header header"
    "main main . sidebar"
    "footer footer footer footer";
justify-items: stretch;
align-items: stretch;
```

> **NOTA**: También existen las propiedades `row-gap` y `column-gap` de forma independiente.

> **NOTA**: El orden inicial de los elementos de la cuadrícula no importa. Con CSS se pueden colocar en cualquier orden, lo que hace que sea muy fácil reorganizar la cuadrícula usando `media queries`. Imagina definir el diseño de toda tu página y luego reorganizarla completamente para acomodar un ancho de pantalla diferente, todo con solo un par de líneas de CSS.

## 3.3. Propiedades del item

 ```css
.item-a {
  grid-column-start: 2;
  grid-column-end: 5;
  grid-row-start: 1;
  grid-row-end: 3;
}

.item-d {
  grid-area: footer;
  justify-self: stretch;
  align-self: stretch;
}
```

> **NOTA**: Sólo hemos comentados las propiedades, tanto del contenedor como del item, más habituales. [Existen muchas más propiedades](https://css-tricks.com/snippets/css/complete-guide-grid/#aa-css-grid-properties), que podrás consultar en el enlace anterior. 


# 4. Media queries


**Una de las funcionalidades más usadas es el cambio de disposición o `layout` de elementos en la página según la resolución de la pantalla.**


No podemos decir que exista una resolución estándar para los dispositivos, pero sí existen algunos puntos de interrupción comúnmente utilizados en la programación diaria. Si está utilizando un framework CSS como Bootstrap, también puede utilizar sus puntos de interrupción.

Veamos algunos puntos de interrupción comunes para anchos de dispositivos:

- 320px — 480px: dispositivos móviles
- 481px — 768px: iPads, tabletas
- 769px — 1024px: pantallas pequeñas, portátiles
- 1025px — 1200px: escritorios, pantallas grandes
- 1201px y más —  Pantallas extra grandes, TV

Estos puntos de interrupción pueden diferir y no existe un estándar exactamente definido, pero estos son algunos de los que se usan comúnmente.

Existen 2 formas de especificar el punto de interrupción:

- Usando las propiedades `min-width` y `max-width`
- Usando la propiedad `width` y algún comparador como `>=`, `>`, `<=`, `<`

```css
/* Estas 2 media queries significan lo mismo */
@media (max-width: 640px) {
  /* … */
}

@media (width <= 640px) {
  /* … */
}
```


```css
/* Estas 2 media queries significan lo mismo */
@media (min-width: 640px) and (max-width: 1024px) {
  /* … */
}

@media (640px <= width <= 1024px) {
  /* … */
}
```

En cuanto a las estrategias disponibles a la hora de abordar el diseño responsive, disponemos de:

- **Mobile first**
- **Desktop first**

## 4.1. Mobile first

Diseño responsive a partir del diseño más pequeño (el de móvil)

Si seguimos esta estrategia, **diseñaremos primero para dispositivos móviles e iremos escalando hacia arriba** en los distitos puntos de interrupción. 

A continuación se muestra un ejemplo:

```css
/*
Pantallas muy pequeñas  (móviles en portrait de menos de 576px)
No hace falta media-query porque será nuestro diseño por defecto
*/

/* Pantallas pequeñas (móviles en landscape de más de 576px) */
@media (min-width: 576px) { ... }


/* Pantallas medianas (tablets de más de 768px) */
@media (min-width: 768px) { ... }


/* Pantallas grandes (desktops de más de 992px) */
@media (min-width: 992px) { ... }


/* Pantallas muy grandes (desktops de más de 1200px) */
@media (min-width: 1200px) { ... }
```


## 4.2. Desktop first

Diseño responsive a partir del diseño más grande (el de escritorio)

Si seguimos esta estrategia, **diseñaremos primero para dispositivos con pantalla grande e iremos escalando hacia abajo** en los distitos puntos de interrupción. 

A continuación se muestra un ejemplo:

```css
/*
Pantallas muy grandes  (desktops de más de 1200px de ancho)
No hace falta media-query porque será nuestro diseño por defecto
*/

/* Pantallas grandes (desktops de menos de 1200px) */
@media (max-width: 1199px) { ... }


/* Pantallas medianas (tablets de menos de 992px) */
@media (max-width: 991px) { ... }

/* Pantallas pequeñas (móviles en landscape de menos de 768px) */
@media (max-width: 767px) { ... }


/* Pantallas muy pequeñas (móviles en portrait de menos de 576px) */
@media (max-width: 575px) { ... }
```


# 5. Recursos

## 5.1. Herramientas

- [Juego - Flexbox Froggy](https://flexboxfroggy.com/#es)
- [Juego - CSS Grid Garden](https://cssgridgarden.com/#es)
- [Juegos Flex Box Adventure y Grid Attack](https://codingfantasy.com)

## 5.2. Formación

- [MDN - CSS Layout](https://developer.mozilla.org/es/docs/Learn/CSS/CSS_layout)
- [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [MDN - Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)
- [MDN - Media queries](https://developer.mozilla.org/es/docs/Web/CSS/CSS_media_queries/Using_media_queries)
- [Flexbox: flex-grow, flex-shrink y flex-basis](https://dev.to/duxtech/flexbox-flex-grow-flex-shrink-y-flex-basis-o96)
- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Media queries](https://lenguajecss.com/css/responsive-web-design/media-queries/)
- [W3C Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/design-develop/es)
- [WCAG 2.1 de un vistazo](https://www.w3.org/WAI/standards-guidelines/wcag/glance/es)
- [Vídeo: Menú lateral responsive con iconos Material Symbols Outlined](https://youtu.be/iiKDMFlXZkY?si=OrICcuK3pPeMe5ee)
