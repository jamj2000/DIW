> DISEÑO DE INTERFACES WEB

# Tema 4: Integración de contenido interactivo  <!-- omit in toc -->
> TRANSFORMACIONES, TRANSICIONES, ANIMACIONES

- [1. Introducción](#1-introducción)
- [2. Transformaciones](#2-transformaciones)
- [3. Transiciones](#3-transiciones)
- [4. Animaciones](#4-animaciones)
- [5. Funcionalidades avanzadas](#5-funcionalidades-avanzadas)
  - [5.1. Scroll driven animations](#51-scroll-driven-animations)
  - [5.2. View Transitions](#52-view-transitions)
- [6. Recursos](#6-recursos)
  - [6.1. Herramientas](#61-herramientas)
  - [6.2. Formación](#62-formación)



--- 

# 1. Introducción

# 2. Transformaciones

# 3. Transiciones

# 4. Animaciones



# 5. Funcionalidades avanzadas

> **IMPORTANTE**: 
> 
> **Las siguientes funcionalidades son bastante modernas. Por tanto, es esperable que el soporte entre navegadores sea muy dispar. Por tanto, antes de usarlas, asegúrate de que estén suficientemente soportadas para evitar problemas de accesibilidad.**


## 5.1. Scroll driven animations

Las **animaciones asociadas al desplazamiento** proporcionan efectos visuales muy atractivos en una página a medida que nos desplazamos hacia abajo hasta el final de dicha página. 

**Ejemplo**:

```html
<body>
  <div id="progress"></div>
  …
</body>
```


```css
@keyframes grow-progress {
  from { transform: scaleX(0); }
  to { transform: scaleX(1); }
}

#progress {
  position: fixed;
  left: 0; top: 0;
  width: 100%; height: 1em;
  background: red;

  transform-origin: 0 50%;
  animation: grow-progress auto linear;
  animation-timeline: scroll();
}
```

**Referencias**:

- https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations
- https://scroll-driven-animations.style/

**Demos**:

- https://www.youtube.com/watch?v=g8LsbPzOVmY
  - https://2z9nyr.csb.app/
  - https://codepen.io/carmenansio/pen/ZEVOqOY

**SOPORTE**
(a fecha de 2 Dic 2023)

![animation scroll](assets/animation-scroll.png)


## 5.2. View Transitions

Las **transiciones de vista** son una opción de diseño popular para reducir la carga cognitiva de los usuarios, ayudarlos a mantenerse en contexto y reducir la latencia de carga percibida a medida que se mueven entre estados o vistas de una aplicación.

La API View Transitions proporciona un mecanismo para crear fácilmente transiciones animadas entre diferentes estados DOM y al mismo tiempo actualizar el contenido DOM en un solo paso.


**Referencias**:

- https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API
- https://developer.chrome.com/docs/web-platform/view-transitions/
- https://stackdiary.com/view-transitions-api/

**Demos**:

- https://astro-records.pages.dev
- https://scroll-driven-animations.style/#demos
- https://http203-playlist.netlify.app/

**SOPORTE**
(a fecha de 2 Dic 2023)

![view transitions](assets/view-transitions.png)

# 6. Recursos

## 6.1. Herramientas

- [Can I use](https://caniuse.com/)

## 6.2. Formación

- [Videotutorial de animaciones](https://www.youtube.com/watch?v=RwjgfNX41TE&t=44s)
- [MDN - Animaciones basadas en desplazamiento](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations)
- [Google - Animaciones basadas en desplazamiento](https://scroll-driven-animations.style/)
