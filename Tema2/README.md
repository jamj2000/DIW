> DISEÑO DE INTERFACES WEB

# Tema 2: Creación de interfaces web utilizando estilos <!-- omit in toc -->
> INSERTAR CSS, CASCADA, ESPECIFICIDAD, HERENCIA, DISPLAY


- [1. Introducción](#1-introducción)
- [2. Formas de insertar CSS](#2-formas-de-insertar-css)
- [3. Selectores](#3-selectores)
  - [3.1. Selectores simples](#31-selectores-simples)
  - [3.2. Selectores combinadores](#32-selectores-combinadores)
  - [3.3. Selectores de pseudoclase](#33-selectores-de-pseudoclase)
  - [3.4. Selectores de pseudoelementos](#34-selectores-de-pseudoelementos)
  - [3.5. Selectores de atributos](#35-selectores-de-atributos)
  - [3.6. Cascada](#36-cascada)
  - [3.7. Especificidad](#37-especificidad)
  - [3.8. Herencia](#38-herencia)
- [4. Display](#4-display)
  - [4.1. Ocultar un elemento](#41-ocultar-un-elemento)
- [5. Recursos](#5-recursos)

---


# 1. Introducción

Este documento es un resumen realizado a partir de la documentación disponible en **[W3Schools](https://www.w3schools.com/css/default.asp)**. 

Por favor, para un tratamiento en mayor profundidad y demos on-line, no dudes en consultar la documentación anterior.



# 2. Formas de insertar CSS

**CSS en línea**

```html
<!DOCTYPE html>
<html>
<head>
</head>
<body>

<h1 style="color: blue; text-align: center;">Título</h1>

</body>
</html>
```

**CSS interno**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
     h1 { color: blue; text-align: center; }
  </style>
</head>
<body>

<h1>Título</h1>

</body>
</html>
```


**CSS externo**

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="estilo.css">
</head>
<body>

<h1>Título</h1>

</body>
</html>
```

```css
/* estilo.css */

h1 {
  color: blue;
  text-align: center;
}
```

# 3. Selectores

1. **Selectores simples** (selecciona elementos según la etiqueta html, identificación, clase)
2. **Selectores combinadores** (selecciona elementos en función de una relación específica entre ellos)
3. **Selectores de pseudoclase** (selecciona elementos según un determinado estado)
4. **Selectores de pseudoelementos** (selecciona y aplica estilo a una parte de un elemento)
5. **Selectores de atributos** (selecciona elementos según un atributo o valor de atributo)

## 3.1. Selectores simples


## 3.2. Selectores combinadores


## 3.3. Selectores de pseudoclase


## 3.4. Selectores de pseudoelementos


## 3.5. Selectores de atributos




## 3.6. Cascada

El listado de reglas CSS que establecemos es interpretado de forma secuencial. Es decir, si definimos una propiedad al principio de la hoja de estilos y más adelante volvemos a definir la misma propiedad con otro valor, la que se aplicará será esta última, puesto que sobreescrirá a la primera.


## 3.7. Especificidad

| Peso | Tipo                                          | Ejemplo                          |
| ---: | --------------------------------------------- | -------------------------------- |
| 1000 | en línea                                      | `<h1 style="color: pink;"></h1>` |
|  100 | id                                            | #navbar                          |
|   10 | clases, pseudoclases, selectores de atributos | .test, :hover, [href]            |
|    1 | elementos, pseudoelementos                    | h1, ::before                     |


> Material de consulta: https://www.w3schools.com/css/css_specificity.asp


## 3.8. Herencia

Muchas de los valores de las propiedades se heredan de padres a hijos, es decir que elementos contenedores a elementos contenidos.

No todas las propiedades son heredadas. Las propiedades que se heredan son:

- `border-collapse`
- `border-spacing`
- `caption-side`
- `color`
- `cursor`
- `direction`
- `empty-cells`
- `font-family`
- `font-size`
- `font-style`
- `font-variant`
- `font-weight`
- `font-size-adjust`
- `font-stretch`
- `font`
- `letter-spacing`
- `line-height`
- `list-style-image`
- `list-style-position`
- `list-style-type`
- `list-style`
- `orphans`
- `quotes`
- `tab-size`
- `text-align`
- `text-align-last`
- `text-decoration-color`
- `text-indent`
- `text-justify`
- `text-shadow`
- `text-transform`
- `visibility`
- `white-space`
- `widows`
- `word-break`
- `word-spacing`
- `word-wrap`


# 4. Display

Según la forma en la que es renderizado un elemento dentro de la página existen, en principio, 2+2 tipos de elementos:

- `block`: **Elemento de bloque**
- `inline`: **Elemento en línea**
- `flex`: **Contenedor flexible**
- `grid`: **Contenedor de cuadrícula o grilla**


**Un elemento a nivel de bloque siempre comienza en una nueva línea y ocupa todo el ancho disponible** (se extiende hacia la izquierda y hacia la derecha tanto como puede).

El elemento `<div>` es un elemento a nivel de bloque.

Ejemplos de elementos a nivel de bloque:

- `<div>`
- `<h1> - <h6>`
- `<p>`
- `<form>`
- `<header>`
- `<footer>`
- `<section>`

**Un elemento en línea no comienza en una nueva línea y solo ocupa el ancho necesario**.

El elemento <span> es un elemento en línea.

Ejemplos de elementos en línea:

- `<span>`
- `<a>`
- `<img>`

**Los contenedores de tipo `flex` y `grid` nos permiten distribuir los elementos dentro de un contenedor**


Para hacer uso en CSS de los `display` anteriores, escribimos:

```css
display: block;
display: inline;
display: flex;
display: grid;
```


## 4.1. Ocultar un elemento

Existen 2 formas de ocultar un elemento:

- **`display: none;`**
- **`visibility: hidden;`**

La primera forma, elimina de la vista el elemento y también elimina el hueco que ocupaba. Mientras que la segunda forma, no elimina el hueco que ocupaba el elemento.


# 5. Recursos
