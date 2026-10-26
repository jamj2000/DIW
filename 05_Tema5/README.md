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
- [5. Container queries](#5-container-queries)
- [6. Reglas @ (At-rules) en CSS](#6-reglas--at-rules-en-css)
  - [6.1. Principales at-rules de CSS](#61-principales-at-rules-de-css)
    - [6.1.1. `@media`](#611-media)
    - [6.1.2. `@import`](#612-import)
    - [6.1.3. `@font-face`](#613-font-face)
    - [6.1.4. `@keyframes`](#614-keyframes)
    - [6.1.5. `@supports`](#615-supports)
    - [6.1.6. `@layer`](#616-layer)
  - [6.2. Otras reglas arroba importantes](#62-otras-reglas-arroba-importantes)
  - [6.3. Diferencia entre `@media` y `@container`](#63-diferencia-entre-media-y-container)
    - [6.3.1. `@media`: consulta el dispositivo o entorno](#631-media-consulta-el-dispositivo-o-entorno)
    - [6.3.2. `@container`: consulta el contenedor](#632-container-consulta-el-contenedor)
  - [6.4. ¿Cómo se clasifican las at-rules?](#64-cómo-se-clasifican-las-at-rules)
    - [6.4.1. Reglas con bloque](#641-reglas-con-bloque)
    - [6.4.2. Reglas con terminación en punto y coma](#642-reglas-con-terminación-en-punto-y-coma)
  - [6.5. Consejo para aprender CSS](#65-consejo-para-aprender-css)
- [7. Optimizaciones](#7-optimizaciones)
  - [7.1. Hueco de la barra de desplazamiento](#71-hueco-de-la-barra-de-desplazamiento)
  - [7.2. Desplazamiento suave](#72-desplazamiento-suave)
  - [7.3. Redimensionado de un elemento](#73-redimensionado-de-un-elemento)
  - [7.4. Recortado de un texto](#74-recortado-de-un-texto)
- [8. Desarrollo de web accesibles](#8-desarrollo-de-web-accesibles)
  - [8.1. Principios de Accesibilidad Web](#81-principios-de-accesibilidad-web)
  - [8.2. Roles y atributos WAI-ARIA](#82-roles-y-atributos-wai-aria)
  - [8.3. Atributos `data-`](#83-atributos-data-)
  - [8.4. Clase `sr-only` (screen reader only)](#84-clase-sr-only-screen-reader-only)
  - [8.5. Buenas prácticas en accesibilidad](#85-buenas-prácticas-en-accesibilidad)
  - [8.6. Ejemplo completo accesible](#86-ejemplo-completo-accesible)
- [9. Recursos](#9-recursos)
  - [9.1. Herramientas](#91-herramientas)
  - [9.2. Formación](#92-formación)





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

> [!NOTE] 
> 
> También existen las propiedades `row-gap` y `column-gap` de forma independiente.

> [!IMPORTANT] 
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

> [!NOTE] 
> 
> También existen las propiedades `row-gap` y `column-gap` de forma independiente.

> [!NOTE] 
> 
> El orden inicial de los elementos de la cuadrícula no importa. Con CSS se pueden colocar en cualquier orden, lo que hace que sea muy fácil reorganizar la cuadrícula usando `media queries`. Imagina definir el diseño de toda tu página y luego reorganizarla completamente para acomodar un ancho de pantalla diferente, todo con solo un par de líneas de CSS.

Un aspecto más avanzado es la posibilidad de definir un número automático de columnas sin la necesidad de usar media query alguna. Para ello usamos la función `repeat` junto a la función `minmax` que establece un ancho mínimo y máximo para cada columna.


```css
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
```
Los valores `auto-fill` y `auto-fit` deciden si **debe rellenarse o no una fila** que dispone de espacio sobrante para la cual no hay elementos hijo que usar.

![auto-fill vs auto-fit](assets/auto-fill_auto-fit.png)

<video width="640" controls>
  <source src="assets/auto-fill-devtools.mov" type="video/mp4">
</video>


- Referencia: https://css-tricks.com/auto-sizing-columns-css-grid-auto-fill-vs-auto-fit/



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

> [!NOTE] 
> 
> Sólo hemos comentados las propiedades, tanto del contenedor como del item, más habituales. [Existen muchas más propiedades](https://css-tricks.com/snippets/css/complete-guide-grid/#aa-css-grid-properties), que podrás consultar en el enlace anterior. 


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


# 5. Container queries

![container queries](assets/container-query.svg)

Las consultas de tamaño con `@container` son relativamente nuevas y proporcionan una forma de consultar el tamaño de un contenedor y aplicar CSS condicionalmente al contenido de ese contenedor, tanto sus hijos como otros descendientes.

```css
.contenedor {
  container-type: inline-size;    
  container-name: tarjeta;      /* nombre del container */
  resize: horizontal;           /* esto es opcional */  
}


.contenido {
  /* estilos css */
}


@container tarjeta (width > 480px) {
  .contenido {
    /* otros estilos css */
  }

}
```

Con la propiedad `container-type` indicamos el ***contexto de contención***, que nos permite indicar el tamaño a monitorizar. Tiene 2 valores:

- `inline-size`, para el tamaño horizontal
- `size`, para el tamaño horizontal y vertical

La propiedad [`resize`](https://developer.mozilla.org/en-US/docs/Web/CSS/resize) nos permite redimensionar con el ratón un elemento. 


- Referencia: [Video acerca de container query](https://youtu.be/mWtAyB5zikM?si=ULSg0l36i-FKDC38)


# 6. Reglas @ (At-rules) en CSS

A continuación mostramos un resumen de las reglas arroba más frecuentes.

Las **at-rules** o **reglas arroba** son instrucciones especiales de CSS que comienzan con el símbolo `@`. Sirven para definir condiciones, importar hojas de estilo, declarar fuentes, establecer animaciones y controlar cómo se aplican los estilos según diferentes situaciones.

## 6.1. Principales at-rules de CSS

Estas son las reglas arroba más utilizadas.

### 6.1.1. `@media`

Adapta los estilos según el tamaño de pantalla, la orientación o las características del dispositivo.

```css
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

**Ejemplo:** cambiar el diseño para móviles.

### 6.1.2. `@import`

Importa otra hoja de estilos CSS.

```css
@import url("estilos.css");
```

Normalmente se coloca al principio de la hoja de estilos, antes de las reglas ordinarias.

### 6.1.3. `@font-face`

Permite registrar fuentes personalizadas para utilizarlas en la página.

```css
@font-face {
  font-family: "MiFuente";
  src: url("fuente.woff2");
}

body {
  font-family: "MiFuente", sans-serif;
}
```

### 6.1.4. `@keyframes`

Define los pasos de una animación CSS.

```css
@keyframes aparecer {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.caja {
  animation: aparecer 2s;
}
```

### 6.1.5. `@supports`

Comprueba si el navegador admite una característica CSS antes de aplicar los estilos.

```css
@supports (display: grid) {
  .contenedor {
    display: grid;
  }
}
```

### 6.1.6. `@layer`

Organiza las reglas CSS en capas y permite controlar su prioridad en la cascada.

```css
@layer base, componentes;

@layer base {
  p {
    color: gray;
  }
}

@layer componentes {
  p {
    color: blue;
  }
}
```

## 6.2. Otras reglas arroba importantes

| At-rule           | Función                                                                                                  |
| ----------------- | -------------------------------------------------------------------------------------------------------- |
| `@container`      | Aplica estilos según el tamaño o las características de un contenedor.                                   |
| `@page`           | Define estilos para la impresión, como márgenes y tamaño de página.                                      |
| `@namespace`      | Declara espacios de nombres para selectores XML.                                                         |
| `@counter-style`  | Define estilos personalizados para contadores y listas.                                                  |
| `@property`       | Registra propiedades CSS personalizadas con tipo y comportamiento definidos.                             |
| `@starting-style` | Define los estilos iniciales para determinadas transiciones de entrada.                                  |
| `@scope`          | Limita el ámbito de aplicación de determinadas reglas CSS.                                               |
| `@charset`        | Declara la codificación de caracteres de una hoja de estilos; si se utiliza, debe aparecer al principio. |

## 6.3. Diferencia entre `@media` y `@container`

Aunque se parecen, cumplen funciones diferentes.

### 6.3.1. `@media`: consulta el dispositivo o entorno

```css
@media (max-width: 600px) {
  .tarjeta {
    width: 100%;
  }
}
```

Se activa cuando la ventana del navegador tiene 600 píxeles de ancho o menos.

### 6.3.2. `@container`: consulta el contenedor

```css
.contenedor {
  container-type: inline-size;
}

@container (max-width: 400px) {
  .tarjeta {
    font-size: 14px;
  }
}
```

Se activa cuando el contenedor de referencia cumple la condición, independientemente del ancho total de la ventana.

## 6.4. ¿Cómo se clasifican las at-rules?

Se pueden agrupar en dos grandes tipos.

### 6.4.1. Reglas con bloque

Contienen otras declaraciones o reglas entre llaves `{ }`.

Ejemplos:

- `@media`
- `@supports`
- `@keyframes`
- `@layer`

### 6.4.2. Reglas con terminación en punto y coma

Suelen introducir una declaración o instrucción.

Ejemplos:

- `@import`
- `@charset`

Esta clasificación es orientativa: algunas reglas tienen una sintaxis más específica.



## 6.5. Consejo para aprender CSS

Si estás empezando con CSS, aprende primero:

1. `@media`
2. `@import`
3. `@font-face`
4. `@keyframes`

Después estudia:

5. `@supports`
6. `@container`
7. `@layer`

Estas reglas te ayudarán a crear diseños adaptables, animaciones y hojas de estilos más avanzadas y fáciles de mantener.



# 7. Optimizaciones

A continuación se comentan brevemente algunos detalles que podemos afinar para una mejor experiencia del usuario.


## 7.1. Hueco de la barra de desplazamiento

En algunas situaciones, sobre todo si tenemos el mismo fondo fijo en distintas páginas, puede observarse que éste se desplaza ligeramente a la izquierda al aparecer la barra de scroll en páginas con mucho contenido y vuelve a la derecha al desaparecer esta barra en páginas con poco contenido. Para evitar este molesto efecto usamos la propiedad **`scrollbar-gutter`** dentro de la etiqueta html.

>
> ```css
> html {
>   scrollbar-gutter: stable; 
> }
> ```

- [Espacio para barra de desplazamiento](https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-gutter)


## 7.2. Desplazamiento suave

En algunas páginas y aplicaciones web disponemos de un menú en la parte superior con enlaces a diferentes secciones de la página. Podemos conseguir que, cuando el usuario pulse en uno de estos enlaces, se produzca un desplazamiento suave a la sección correspondiente, en lugar del desplazamiento inmediato que es el comportamiento por defecto. Para ello usaremos la propiedad **`scroll-behavior`** con el valor `smooth`.


>
> ```css
> body {
>   scroll-behavior: smooth;
> }
> ```

- [Desplazamiento suave](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior)

Cuando esta propiedad se especifica en el pseudoelemento `:root`, se aplica a la ventana gráfica. Si se especifica en el elemento `body`, no se propaga a la ventana gráfica.


## 7.3. Redimensionado de un elemento

En ciertas circunstancias, la propiedad **`resize`** resulta de gran utilidad. Esta propiedad nos permite definir si un elemento va a permitir el redimiensionado o no. Los valores pueden ser `none`,  `horizontal`, `vertical` o `both`. 



Aunque en la mayoría de los casos se emplea con elementos `textarea`,

```css
textarea {
  resize: none;
}
```

es también posible emplearlo en otro tipo de elementos, como `div`, `p`, etc


```css
p {
  overflow: auto; /* recomendable para evitar desbordamiento del texto */
  resize: both;

  border: 1px solid black;
}
```
![resize](assets/resize.png)

- [Redimensionado de un elemento](https://developer.mozilla.org/en-US/docs/Web/CSS/resize)


## 7.4. Recortado de un texto

En ciertos casos puede ser útil recortar una línea de texto, quizás porque la información que contiene es una previsualización. Para ello podemos usar la propiedad **`text-overflow`** con los valores `ellipsis` o `clip`. 

Esta propiedad requiere también el uso de `white-space: nowrap` y `overflow: hidden`.


```css
p {
  text-overflow: ellipsis;
  /* Las 2 propiedades siguientes son necesarias para text-overflow */
  white-space: nowrap;
  overflow: hidden;

  border: 1px solid black;
}
``` 
![text overflow](assets/text-overflow.png)

- [Recortado de un texto](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow)

# 8. Desarrollo de web accesibles

## 8.1. Principios de Accesibilidad Web
La accesibilidad busca que todas las personas (incluyendo con discapacidad visual, auditiva, motriz o cognitiva) puedan **percibir, comprender, navegar e interactuar** con un sitio web.  
Se apoya en las normas **WCAG 2.1** y el estándar **WAI-ARIA**.

**Principios básicos (POUR)**:

- **Perceptible:** la información debe presentarse de manera que todos puedan percibirla.  
- **Operable:** la interfaz debe poder usarse con diferentes dispositivos (ratón, teclado, lector de pantalla).  
- **Comprensible:** el contenido y la navegación deben ser claros y predecibles.  
- **Robusto:** debe funcionar con diferentes navegadores, dispositivos y tecnologías de asistencia.



## 8.2. Roles y atributos WAI-ARIA

Los atributos **ARIA** (*Accessible Rich Internet Applications*) mejoran la accesibilidad en aplicaciones web dinámicas.

**Ejemplos comunes:**
- `aria-label="..."` → etiqueta accesible para describir un elemento.  
- `aria-hidden="true"` → oculta un elemento a los lectores de pantalla.  
- `aria-expanded="true|false"` → indica si un menú/elemento está desplegado o no.  
- `aria-current="page"` → señala la página actual en una navegación.  


```html
<nav aria-label="Menú principal">
  <ul>
    <li><a href="/" aria-current="page">Inicio</a></li>
    <li><a href="/servicios">Servicios</a></li>
    <li><a href="/contacto">Contacto</a></li>
  </ul>
</nav>
```

El atributo **`role`** (definido en la especificación [WAI-ARIA](https://www.w3.org/WAI/standards-guidelines/aria/)) permite describir **la función o propósito** de un elemento en la interfaz web, sobre todo cuando el HTML semántico por sí solo no es suficiente.


**¿Por qué es importante?**

- Ayuda a los **lectores de pantalla** y otras tecnologías asistivas a interpretar correctamente los elementos.  
- Permite mejorar la **semántica** en interfaces dinámicas (menús, diálogos, pestañas, sliders, etc.).  
- Útil cuando usamos elementos genéricos como `<div>` o `<span>` y necesitamos darles un propósito.


**Ejemplos:**

- **Roles de estructura o landmark**  
  Identifican secciones importantes de la página.  
  - `role="banner"` → cabecera del sitio.  
  - `role="navigation"` → menú de navegación.  
  - `role="main"` → contenido principal.  
  - `role="contentinfo"` → pie de página.  
  - `role="complementary"` → información adicional (ej. barra lateral).  

```html
<header role="banner">
  <h1>Mi sitio web</h1>
</header>
<nav role="navigation">
  <ul>
    <li><a href="/">Inicio</a></li>
    <li><a href="/blog">Blog</a></li>
  </ul>
</nav>
<main role="main">
  <h2>Artículo destacado</h2>
  <p>Contenido principal de la página.</p>
</main>
<footer role="contentinfo">
  <p>© 2025 Mi sitio web</p>
</footer>
``` 

- **Roles de documento**
  Describen contenido estructurado.
  - `role="article"` → artículo independiente.
  - `role="note"` → nota informativa.
  - `role="presentation"` → ignora la semántica visual (ej. tablas usadas solo para maquetar).


```html
<article role="article">
  <h2>Novedades</h2>
  <p>Este es un artículo con información relevante.</p>
</article>
```


> [!TIP]
> **Buenas prácticas con `role`**
>
> **Usar primero HTML semántico**. Muchos elementos ya tienen un `role` implícito.  
>  - `<header>` → `role="banner"`  
>  - `<nav>` → `role="navigation"`  
>  - `<main>` → `role="main"`  
>  - `<footer>` → `role="contentinfo"`  
>
> No es necesario duplicar el atributo.
> ✅ **Añadir `role` solo cuando sea necesario**: Especialmente en elementos genéricos como `<div>` o `<span>` que se usan como botones, menús o pestañas.
>
>
>```html
><div role="button" tabindex="0" aria-pressed="false">
>  Hacer clic aquí
></div>
>``` 


## 8.3. Atributos `data-`

Los atributos `data-*` permiten almacenar información personalizada en los elementos HTML, útil para JavaScript o CSS sin romper la semántica.

- **Ejemplo de uso:**
```html
<button data-toggle="modal" data-target="#loginModal">
  Iniciar sesión
</button>
```

- **Acceso con JS:**

```js
const btn = document.querySelector("button");
console.log(btn.dataset.toggle); // "modal"
console.log(btn.dataset.target); // "#loginModal"
```

## 8.4. Clase `sr-only` (screen reader only)
La clase `sr-only` (usada en frameworks como **Bootstrap**) oculta visualmente un elemento, pero lo mantiene accesible para lectores de pantalla.

- **Ejemplo:**

```html
<label for="busqueda" class="sr-only">Buscar en la web</label>
<input type="text" id="busqueda" placeholder="Buscar...">
``` 

👉 El usuario visual solo ve el campo de búsqueda, pero el lector de pantalla anuncia el texto del `label`.

## 8.5. Buenas prácticas en accesibilidad
- Usar **HTML semántico**: encabezados `<h1>–<h6>`, listas, tablas con `<thead>` y `<th>`.  
- Proporcionar **texto alternativo** en imágenes (`alt`).  
- Asegurar **contraste suficiente** entre texto y fondo.  
- Hacer que todo sea **navegable con teclado** (evitar depender solo del ratón).  
- Evitar usar solo color para transmitir información.  
- Añadir **descripciones ARIA** en botones e iconos sin texto.  
- Validar accesibilidad con herramientas como **Lighthouse**, **WAVE** o el **validador de la W3C**.

## 8.6. Ejemplo completo accesible

```html
<header>
  <h1>Portal de Cursos Online</h1>
  <nav aria-label="Menú de navegación principal">
    <ul>
      <li><a href="/" aria-current="page">Inicio</a></li>
      <li><a href="/cursos">Cursos</a></li>
      <li><a href="/contacto">Contacto</a></li>
    </ul>
  </nav>
</header>

<main>
  <h2>Buscar curso</h2>
  <form>
    <label for="busqueda" class="sr-only">Buscar curso</label>
    <input type="text" id="busqueda" placeholder="Buscar..." data-type="search">
    <button type="submit" aria-label="Buscar curso">🔍</button>
  </form>
</main>
``` 


# 9. Recursos

## 9.1. Herramientas

- [Juego - Flexbox Froggy](https://flexboxfroggy.com/#es)
- [Juego - CSS Grid Garden](https://cssgridgarden.com/#es)
- [Juegos Flex Box Adventure y Grid Attack](https://codingfantasy.com)
- [Generador de Grid](https://cssgridgenerator.io/)

## 9.2. Formación

- [MDN - CSS Layout](https://developer.mozilla.org/es/docs/Learn/CSS/CSS_layout)
- [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [MDN - Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)
- [MDN - Media queries](https://developer.mozilla.org/es/docs/Web/CSS/CSS_media_queries/Using_media_queries)
- [Flexbox: flex-grow, flex-shrink y flex-basis](https://dev.to/duxtech/flexbox-flex-grow-flex-shrink-y-flex-basis-o96)
- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Media queries](https://lenguajecss.com/css/responsive-web-design/media-queries/)
- [Flexbox Cheatshet]( https://jonitrythall.com/flexbox-cheatsheet )
- [W3C Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/design-develop/es)
- [WCAG 2.1 de un vistazo](https://www.w3.org/WAI/standards-guidelines/wcag/glance/es)
- [Vídeo: Menú lateral responsive con iconos Material Symbols Outlined](https://youtu.be/iiKDMFlXZkY?si=OrICcuK3pPeMe5ee)
- [Extensión para navegador de Web Accessibility Evaluation Tool](https://wave.webaim.org/extension/)