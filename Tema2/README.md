> DISEÑO DE INTERFACES WEB

# Tema 2: Creación de interfaces web utilizando estilos


## Formas de insertar CSS

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

## Selectores

- **Selectores simples** (selecciona elementos según la etiqueta html, identificación, clase)
- **Selectores combinadores** (selecciona elementos en función de una relación específica entre ellos)
- **Selectores de pseudoclase** (selecciona elementos según un determinado estado)
- **Selectores de pseudoelementos** (selecciona y aplica estilo a una parte de un elemento)
- **Selectores de atributos** (selecciona elementos según un atributo o valor de atributo)


### Especificidad

Peso   | Tipo                                            | Ejemplo  
------:|-------------------------------------------------|------------
1000   | en línea                                        | `<h1 style="color: pink;"></h1>`
 100   | id                                              | #navbar
  10   | clases, pseudoclases, selectores de atributos   | .test, :hover, [href]
   1   | elementos, pseudoelementos                      | h1, ::before


> Material de consulta: https://www.w3schools.com/css/css_specificity.asp
