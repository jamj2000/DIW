> DISEÑO DE INTERFACES WEB

# Tema 5: Desarrollo de Webs accesibles  <!-- omit in toc -->
> LAYOUTS, FLEX, GRID, RESPONSIVE, MEDIA QUERIES


---
# Flex

Disposición **flexible**
- Referencia: [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


## Propiedades del contenedor

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


## Propiedades del item

**Ejemplo:**

```css
order: 1;          /* default is 0 */
flex-grow: 2;      /* default 0 */
flex-shrink: 2;    /* default 1 */
flex-basis: 100px; /* default auto */
flex: 0 1 auto;    /* shorthand para grow shrink basis */
align-self: flex-end;
```

# Grid

Disposición en **cuadricula**
- Referencia: [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

## Propiedades del contenedor

```css
display: grid;
gap: 10px;
flex-direction: row;
flex-wrap: wrap;
justify-content: space-between;
align-items: center;
align-content: center;
```



> **NOTA**: También existen las propiedades `row-gap` y `column-gap` de forma independiente.


## Propiedades del item




> **NOTA**: Sólo hemos comentados las propiedades, tanto del contenedor como del item, más habituales. [Existen muchas más propiedades](https://css-tricks.com/snippets/css/complete-guide-grid/#aa-css-grid-properties), que podrás consultar en el enlace anterior. 


# Media queries


 
# Reto

- Landing Page: https://www.frontendmentor.io/challenges/manage-landing-page-SLXqC6P5
- Lista de reproducción: https://youtube.com/playlist?list=PL4-IK0AVhVjNDRHoXGort7sDWcna8cGPA&si=5FF176VsDJEHSfbg
- Parte 1: https://youtu.be/h3bTwCqX4ns?si=etDa01_wycsRgUty
- Parte 2: https://youtu.be/3K6zr1CdZy8?si=s3a23on9rFLRKdyv
- Parte 3: https://youtu.be/Ch_LoWKLv3A?si=acT6zLGtNp7E36_l
- Parte 4: https://youtu.be/zPHMqqyD2kY?si=A1UwRxRxN2Vjb9G8
- Parte 5: https://youtu.be/mQYRWvIj0Yw?si=GXDtHb9MowBpmQY9
- Parte 6: https://youtu.be/NorLM-dalTE?si=M55NUbaJ2YPDeya2
- Parte 7: https://youtu.be/eX9JhQtMxCg?si=x8BA1coC3UFKn3zC
- Parte 8: https://youtu.be/r6hx35TbtN4?si=NpSxri_mw2K2Mifu
- Parte 9: https://youtu.be/a8OiB2NnHMo?si=rqYEz-BxDyGiPVAQ
- Parte 10: https://youtu.be/vGFiOhl-hjY?si=iODUxlKk-VDDO-b0
- Parte 11: https://youtu.be/e7o69Zi-Iao?si=XtRgYhfEimoZCJEw


# Recursos

## Herramientas

- [Juego - Flexbox Froggy](https://flexboxfroggy.com/#es)
- [Juego - CSS Grid Garden](https://cssgridgarden.com/#es)

## Formación

- [MDN - CSS Layout](https://developer.mozilla.org/es/docs/Learn/CSS/CSS_layout)
- [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [MDN - Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)
- [Flexbox: flex-grow, flex-shrink y flex-basis](https://dev.to/duxtech/flexbox-flex-grow-flex-shrink-y-flex-basis-o96)
- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [W3C Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/design-develop/es)
- [WCAG 2.1 de un vistazo](https://www.w3.org/WAI/standards-guidelines/wcag/glance/es)
