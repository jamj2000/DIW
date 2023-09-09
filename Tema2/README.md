> DISEÑO DE INTERFACES WEB

# Tema 2: Creación de interfaces web utilizando estilos

> SELECTORES
>

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
