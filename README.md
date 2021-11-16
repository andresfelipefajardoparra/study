# Notas Clases Andrés Felipe Fajardo :man-student:

- [Notas Clases Andrés Felipe Fajardo :man-student:](#notas-clases-andrés-felipe-fajardo-man-student)
- [Frontend I](#frontend-i)
  - [CSS](#css)
    - [Selectores](#selectores)
    - [Como se usan los selectores](#como-se-usan-los-selectores)
    - [Propiedades basicas](#propiedades-basicas)

# Frontend I

## CSS

### Selectores

Los selectores se utilizan, como su nombre lo indica, para seleccionar elementos en el HTML previamente creado. Te escribo una selección rápida de selectores sacada de [esta página](https://www.w3schools.com/cssref/css_selectors.asp).

Los ejemplos van a estar orientados al siguiente codigo HTML

```
<HTML>
  <head>
    <title>Prueba</title>
  </head>
  <body>
    <h1 id="heading-principal">Titulo</h1>
    <p>Primera division</p>
    <ul class="lista-no-ordenada">
      <li class="item-lista primer-item">
        <p>Primer item, segunda división</p>
      </li>
      <li class="item-lista">Item 2</li>
      <li class="item-lista">Item 3</li>
    </ul>
    <p>Tercera división</p>
  </body 
</HTML>
```

| Selector | Ejemplo | Descripción del ejemplo |
| ----------- | ----------- | ----------- | 
| .clase | .item-lista | Selecciona todos los items que contienen la clase ```item-lista```. 3 elementos en este caso
| .clase1.clase2 | .item-lista.primer-item | Selecciona solo ```<li class="item-lista primer-item">Item 1</li>``` porque es el único que contiene las dos clases
| #id | #heading-principal | Selecciona el item que contiene el id ```heading-principal```, en este caso es ```<h1 id="heading-principal">Titulo</h1>```
| * | * | Selecciona todos los elementos
| element | li | Selecciona todos los elementos ```li```, 3 en este caso
| element > element | li > p | Selecciona todos los elementos ```p``` cuyo padre inmediato sea un elemento ```li```. En este caso sería ```<p>Primer item, segunda división</p>```, excluyendo ```<p>Primera division</p>``` porque su padre no es un elemento ```<li>```
| element + element | h1 + p | Selecciona todos los elementos ```p``` cuyo elemento inmediatamente anterior sea un ```h1```, en este caso sería solamente ```<p>Primera division</p>```
| element ~ element | h1 ~ p | Selecciona todos los elementos ```p``` cuyo elemento hermano (en el mismo nivel) sea un ```h1```, en este caso sería ```<p>Primera division</p>``` y ```<p>Tercera división</p>```
| element element | ul li | Seleccionan todos los elementos ```li``` cuyo padre, no necesariamente inmediato, sea ```ul```

### Como se usan los selectores

La sintaxis basica de una regla CSS es la siguiente

```
selector {
  color: #000,
  font-size: 14px
}
```

### Propiedades basicas

Algunas propiedades basicas

| Propiedad | Ejemplo | Descripción del ejemplo |
| ----------- | ----------- | ----------- | 
| color | color: #000 | Pone el texto en negro a los elementos seleccionados, el color se puede poner en hexadecimal o en texto para colores basicos (red, white, black, blue, etc.)
| font-size | font-size: 13px | Pone el texto en un tamaño de 13 pixeles a los elementos seleccionados
| background-color | background-color: red | Pone el color de fondo rojo para los elementos seleccionados
| border | border: 1px solid blue | Es un wrapper de varias propiedades ```border-width```, ```border-style```, ```border-color```. Pone un borde de un ancho de 1 pixel, borde solido (sin puntos ni guiones) y de color azul a los elementos seleccionados
| z-index | z-index: 200 | Sobrepone el elemento seleccionado sobre elementos con menor ```z-index```
| height | height: 200px | Hace que el alto del elemento seleccionado sea de 200 pixeles
| width | width: 100px | Hace que el ancho del elemento seleccionado sea de 100 pixeles
| position | position: relative | Determina la posición de un elemento. Se explica en detalle en el siguiente parrafo

Uno de los mas importantes es ```position```, a continuación los valores que puede tener:
- ```position: static``` es el valor por defecto, el elemento sigue el flujo regular.
- ```position: relative``` igual a estatico pero se puede ajustar la posición usando adicionalmente las propiedades ```top, right, bottom, left```.
- ```position: absolute``` el elemento se saca del flujo del documento. Se deben usar las propiedades ```top, right, bottom, left``` para ubicarlo
- ```position: fixed``` igual que absolute pero el elemento no se mueve con el scroll, queda fijo en la pantalla
