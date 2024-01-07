> DISEÑO DE INTERFACES WEB

# Tema 6: Desarrollo de interfaces Web amigables  <!-- omit in toc -->
> BOOTSTRAP, TAILWIND

- [1. Introducción](#1-introducción)
- [2. Bootstrap](#2-bootstrap)
- [3. Tailwind](#3-tailwind)
  - [3.1. Instalación](#31-instalación)
  - [3.2. Desarrollo](#32-desarrollo)
  - [3.3. Características](#33-características)
    - [3.3.1. Diseño responsive](#331-diseño-responsive)
    - [3.3.2. Medidas múltiplo de 4px o 0.25rem](#332-medidas-múltiplo-de-4px-o-025rem)
    - [3.3.3. Colores](#333-colores)
- [4. Reto Landing Page](#4-reto-landing-page)
  - [4.1. Solución usando Tailwind](#41-solución-usando-tailwind)
  - [4.2. Solución usando sólo CSS](#42-solución-usando-sólo-css)
- [5. Recursos](#5-recursos)
  - [5.1. Herramientas](#51-herramientas)
  - [5.2. Formación](#52-formación)



--- 

# 1. Introducción

# 2. Bootstrap

# 3. Tailwind

Referencia:
- [Documentación de Tailwind](https://tailwindcss.com/docs)


## 3.1. Instalación

Existen distintas formas de instalar tailwind. Puedes consultarlas en la [documentación oficial](https://tailwindcss.com/docs/installation) 

**Existen numerosos frameworks web que ya lo incluyen de serie por lo que, en estos casos, no necesitaremos hacer nada.**

No obstante, si deseamos empezar a trabajar en un proyecto independiente del framework, podemos trabajar usando el Tailwind CLI, como se muestra a continuación:

```sh
npm init -y
npm i -D tailwindcss 
npx tailwindcss init
```
La última sentencia generará un archivo `tailwind.config.js`, que podremos editar para la configuración de tailwind, si así lo deseamos. A continuación se muestra un ejemplo de configuración realizada:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [ './index.html' ],
  theme: {
    screens: {
      sm: '480px',
      md: '768px',
      lg: '976px',
      xl: '1440px',
    },
    extend: {
      colors: {
        brightRed: 'hsl(12, 88%, 59%)',
        darkBlue: 'hsl(228, 39%, 23%)'
      }
    },
  },
  plugins: [],
}
```
Además de los archivos indicados en la propiedad `content`, que serán analizados para traducir las clases de tailwind que aparezca en ellos, necesitaremos 2 archivos más:

- un archivo css de entrada, al que llamaré `entrada.css`
- un archivo css de salida, al que llamaré `style.css`

En el archivo `entrada.css` colocaremos el siguiente contenido:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Otro contenido CSS */
```
 
En el archivo `index.html` colocaremos la siguiente etiqueta `link` apuntando al archivo de css de salida, ya procesado:

```html
<html>
<head>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    
</body>
</html>
```

Por último, en el archivo `package.json`, crearemos los scrips siguientes:

```json
 ...
 "scripts": {
    "build": "tailwindcss -i ./entrada.css -o ./style.css",
    "watch": "tailwindcss -i ./entrada.css -o ./style.css --watch"
  },
  ...
```

## 3.2. Desarrollo

A continuación, ya podremos lanzar el script siguiente:

```sh
npm run watch
```

y empezar a editar los archivos html, añadiendo las clases tailwind deseadas. En nuestro caso lo haremos con el archivo `index.html`.

Es aconsejable tener un servidor web con recarga automática para ver los cambios en tiempo real. Una buena alternativa para ello es usar el plugin `Live Preview` de VSCode.

![VSCode](assets/vscode.png)


## 3.3. Características

### 3.3.1. Diseño responsive

Prefijo | Ancho mínimo | CSS equivalente
--------|--------------|------------------------------
`sm`	  | 640px	       | `@media (min-width: 640px) { ... }`
`md`	  | 768px	       | `@media (min-width: 768px) { ... }`
`lg`	  | 1024px	     | `@media (min-width: 1024px) { ... }`
`xl`	  | 1280px	     | `@media (min-width: 1280px) { ... }`
`2xl`	  | 1536px	     | `@media (min-width: 1536px) { ... }`


De forma predeterminada, Tailwind utiliza un sistema *mobile-first*, similar al que podría estar acostumbrado en otros frameworks como Bootstrap.

Lo que esto significa es que las utilidades sin prefijo (como `uppercase`) tienen efecto en todos los tamaños de pantalla, mientras que las utilidades con prefijo (como `md:uppercase`) solo tienen efecto en el punto de interrupción especificado y superiores.

De forma predeterminada, los estilos aplicados por reglas como `md:flex` se aplicarán en ese punto de interrupción y permanecerán aplicados en puntos de interrupción más grandes.

### 3.3.2. Medidas múltiplo de 4px o 0.25rem

En Tailwind muchas clases de utilidad utilizan identificadores cuya cifra númerica se multiplicará por 4px al convertir a código CSS. Esta es la [escala de espaciado por defecto](https://tailwindcss.com/docs/customizing-spacing#default-spacing-scale). Por ejemplo:

Clase  | Propiedad CSS
-------|------------------------------
p-0.5	 | padding: 0.125rem; /* 2px */
p-1	   | padding: 0.25rem; /* 4px */
p-2    | padding: 0.25rem; /* 8px */

Esto sucede con las siguientes propiedades:

- [padding](https://tailwindcss.com/docs/padding)
- [margin](https://tailwindcss.com/docs/margin)
- [*space between*](https://tailwindcss.com/docs/space)
- [gap](https://tailwindcss.com/docs/gap)
- [width](https://tailwindcss.com/docs/width)
- [height](https://tailwindcss.com/docs/height)
- [*size*](https://tailwindcss.com/docs/size)
- [border-width](https://tailwindcss.com/docs/border-width)
- ...alguna otra 

Según la documentación, esta escala es heredada por padding, margin, width, minWidth, maxWidth, height, minHeight, maxHeight, gap, inset, space, translate y algunos plugins. [Esta escala puede personalizarse](https://tailwindcss.com/docs/customizing-spacing).

### 3.3.3. Colores

Tailwind incluye una [paleta de colores](https://tailwindcss.com/docs/customizing-colors) predeterminada diseñada por expertos y lista para usar que es un excelente punto de partida si no tiene su propia marca específica en mente.

![Paleta de colores](assets/paleta-colores.png)

**Ejemplos**:

```css
bg-slate-50      /* Color de fondo */
text-slate-950   /* Color de texto */
border-slate-300 /* Color de borde */
outline-black    /* Color de contorno */
shadow-slate-950 /* Color de sombra */
```




# 4. Reto [Landing Page](https://www.frontendmentor.io/challenges/manage-landing-page-SLXqC6P5)


## 4.1. [Solución usando Tailwind](https://www.youtube.com/watch?v=dFgzHOX84xQ)

> Solución proporcionada por el canal de Youtube [Traversy Media](https://www.youtube.com/@TraversyMedia)

Es un vídeo en inglés de 1 hora y media aproximada de duración.


## 4.2. [Solución usando sólo CSS](https://youtube.com/playlist?list=PL4-IK0AVhVjNDRHoXGort7sDWcna8cGPA&si=5FF176VsDJEHSfbg)

> Solución proporcionada por el canal de Youtube de [Kevin Powell](https://www.youtube.com/@KevinPowell)

Es una lista de reproducción con 11 vídeos. Cada vídeo tiene una duración entre 20 y 50 minutos aproximadamente.



# 5. Recursos

## 5.1. Herramientas

## 5.2. Formación

- [DesarrolloWeb: Manual de Tailwind](https://desarrolloweb.com/manuales/manual-de-tailwindcss)