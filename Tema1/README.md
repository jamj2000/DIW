> DISEÑO DE INTERFACES WEB

# Tema 1: Planificación de interfaces gráficas <!-- omit in toc -->
> FORMATO DE REGLA, COLOR, MODELO DE CAJA, TEXTO, LISTAS, TABLAS

- [1. Introducción](#1-introducción)
- [2. Formato de regla CSS](#2-formato-de-regla-css)
- [3. Color](#3-color)
  - [3.1. Identificación](#31-identificación)
  - [3.2. Valores RGB](#32-valores-rgb)
  - [3.3. Valores RGBA](#33-valores-rgba)
  - [3.4. Valores HSL](#34-valores-hsl)
  - [3.5. Valores HSLA](#35-valores-hsla)
- [4. Modelo de caja (box model)](#4-modelo-de-caja-box-model)
- [5. Texto](#5-texto)
- [6. Listas](#6-listas)
- [7. Tablas](#7-tablas)
- [8. Recursos](#8-recursos)
  - [8.1. Herramientas](#81-herramientas)
  - [8.2. Formación](#82-formación)

---


## 1. Introducción

## 2. Formato de regla CSS

![Regla CSS](assets/regla-css.gif)

## 3. Color

### 3.1. Identificación

- Por **nombre**:  tomato
- Por **valor hexadecimal**: #ff6347
- Por **valores RGB**: rgb(255, 99, 71)
- Por **valores HSL**: hsl(9, 100%, 64%)


**Ejemplo**
```html
<!DOCTYPE html>
<html>
<body>

<h1 style="background-color: Tomato; text-align: center;">Tomato</h1>

<h1 style="text-align: center;">Sin Transparencia</h1>

<h1 style="background-color:#ff6347;">#ff6347</h1>
<h1 style="background-color:rgb(255, 99, 71);">rgb(255, 99, 71)</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">hsl(9, 100%, 64%)</h1>

<h1 style="text-align: center;">Con Transparencia</h1>

<h1 style="background-color:#ff634777;">#ff634777</h1>
<h1 style="background-color:rgba(255, 99, 71, 0.5);">rgba(255, 99, 71, 0.5)</h1>
<h1 style="background-color:hsla(9, 100%, 64%, 0.5);">hsla(9, 100%, 64%, 0.5)</h1>

</body>
</html>
```

![Ejemplo colores](assets/ejemplo-colores.png)


### 3.2. Valores RGB

En CSS, un color se puede especificar como un valor RGB mediante esta fórmula:

**rgb ( rojo, verde , azul )**


- Cada parámetro (rojo, verde y azul) define la **intensidad del color entre 0 y 255**.
- Por ejemplo, rgb(255, 0, 0) se muestra en rojo, porque el rojo está configurado en su valor más alto (255) y los demás están configurados en 0.
- Para mostrar negro, establezca todos los parámetros de color en 0, así: rgb(0, 0, 0).
- Para mostrar blanco, establezca todos los parámetros de color en 255, así: rgb(255, 255, 255)
- Para mostrar alguna nivel de gris, establezca todos los parámetros de color con igual valor, así: rgb(200, 200, 200)


### 3.3. Valores RGBA

Los valores de color RGBA son una extensión de los valores de color RGB con un **canal alfa**, que especifica la **opacidad de un color**.

Un valor de color RGBA se especifica con:

**rgba ( rojo, verde , azul, alfa )**

El parámetro alfa es un número **entre 0,0 (completamente transparente) y 1,0 (nada transparente)**


### 3.4. Valores HSL

En CSS, un color se puede especificar usando tono, saturación y luminosidad (HSL) en la forma:

**hsl ( tono , saturación , luminosidad )**

- El tono es un grado en la **rueda de colores de 0 a 360 grados**. 0 es rojo, 120 es verde y 240 es azul.
- **La saturación es un valor porcentual**. 0% significa un tono de gris y 100% es el color completo.
- **La luminosidad es un valor porcentual**. 0% es negro, 50% no es ni claro ni oscuro, 100% es blanco


**Tono** o Hue

![Rueda color](assets/rueda-color.webp)

**Saturación** y **Luminosidad**

![Munsell system](assets/munsell-color-system.png)

![HSL](assets/hsl_cone.jpg)


### 3.5. Valores HSLA

Los valores de color HSLA son una extensión de los valores de color HSL con un **canal alfa**, que especifica la **opacidad de un color**.

Un valor de color HSLA se especifica con:

**hsla ( tono, saturación , luminosidad, alfa )**

El parámetro alfa es un número **entre 0,0 (completamente transparente) y 1,0 (nada transparente)**


## 4. Modelo de caja (box model)

![Box Model](assets/box-model.png)

La propiedad **`box-sizing`** permite indicar si:

- Ancho y Alto se refiere al contenido. Valor **`content-box`**. Es el valor por defecto
- Ancho y Alto se refiere al margen exterior. Valor **`border-box`**

Muchos diseñadores prefieren usar un **border-box**, para así evitar descuadres:

```css
* {
  box-sizing: border-box;
}
```

## 5. Texto

Las propiedades más frecuentes para el texto son las siguientes:

- `color`
- `font-family`
- `font-size`
- `font-weight`
- `text-align`
- `word-spacing`
- `letter-spacing`
- `line-height`

Para importar un tipo de letra o fuente, podemos usar la regla `@import`

Ejemplo:

```css
@import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500&display=swap');

div {
    color: tomato;
    font-family: 'Fira Code', monospace;
    font-size: 1rem;  /* 16px */
    font-weight: 400;    
    word-spacing: 8px;
    letter-spacing: 1rem;
    line-height: 300px;
    text-align: center;
    text-decoration: none;
}
```

Los valores por defecto son:

```css
    font-size: 1rem;  /* o  font-size: 16px */
    font-weight: 400;
```

## 6. Listas

La propiedad más usada es

- `list-style-type`


Ejemplos:

```css
ul {
  list-style-type: none;
  list-style-type: circle;
  list-style-type: square;
}

ol {
  list-style-type: none;
  list-style-type: upper-roman;
  list-style-type: lower-alpha;
}
```

## 7. Tablas



## 8. Recursos

### 8.1. Herramientas

- [HTML Colors](https://htmlcolorcodes.com/)
- [Conversor de color](https://www.w3schools.com/colors/colors_converter.asp)
- [Fresh Background Gradients](https://webgradients.com/)
- [Gradient Generator](https://www.joshwcomeau.com/gradient-generator/)
- [Google Fonts](https://fonts.google.com)
- [Emojipedia](https://emojipedia.org/)
- [Algunos símbolos Unicode](https://www.w3schools.com/charsets/ref_utf_symbols.asp)

### 8.2. Formación

- [Modelo de color HSL: qué es y qué ventajas tiene](https://www.uifrommars.com/que-es-hsl/)
- [Google Fonts Knowledge](https://fonts.google.com/knowledge)
