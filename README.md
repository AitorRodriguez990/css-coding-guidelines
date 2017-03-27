# Directrices de codificación CSS de Pisos

Este documento tiene la intención de ser un punto de referencia para aquellos desarrolladores que deban escribir código CSS. Aquí no se encuentran normas o leyes, sino sugerencias.

El objetivo es conseguir un código CSS ordenado, limpio y reutilizable.


## Tabla de contenidos

1. [Introducción](#introduccion)
2. [Nombre de clases](#nombreclases)
3. [Comentarios](#comentarios)
4. [Formato](#formato)
    - [Orden de propiedades](#ordenprioridades)
    - ~~Prefijo de propiedades~~
    - ~~Media queries~~
    - ~~Selectores~~
    - ~~Anidamiento~~
5. ~~Configuración del editor~~
6. ~~Otros enlaces de interés~~
7. ~~Agradecimientos~~
8. [Contribuciones](#contribuciones)


<a name="introduccion"></a>
## 1. Introducción

> "Para triunfar es necesario, más que nada, tener sentido común." - Napoleón Bonaparte

Son muchas las sugerencias que aquí se pueden leer, pero podemos resumirlo en:
- Todo el código CSS/LESS debe parecer escrito por la misma persona.
- Si después de consultar esta guía aún te surgen dudas sobre como hacer algo es probable que haya un vacío en ella, por lo que hay que mejorarla. ¡Ayuda a mejorarla!


<a name="nombreclases"></a>
## 2. Nombre de clases

A la hora de nombrar clases a las que aplicar estilos estas deberían seguir las siguientes reglas:
- Utiliza minúsculas y guiones para separar las palabras, no utilices guiones bajo o *camelCase*.
- Puedes recortar palabras siempre y cuando sigan siendo entendibles, de otra manera el nombre perdería su sentido.
- Añade prefijos a los nombres de las clases haciendo referencia a su *padre*, si lo tuviera. Será más fácil de saber que hace esa clase.

**Mal**
```css
.buttonBlue,
.button_red {
  padding: 10px 20px;
}

.ft {
  background: #d9d9d9;
}

.navbar {
  position: fixed;
  top: 0;
}
```

**Bien**
```css
.button-blue,
.button-red {
  padding: 10px 20px;
}

.footer {
  background: #d9d9d9;
}

.header-navbar {
  position: fixed;
  top: 0;
}
```


<a name="comentarios"></a>
## 3. Comentarios
Es muy importante tener el código bien comentado, puesto que esto ayudará a otros compañeros a saber qué es lo que hace una clase y para qué fue creada. Dedica el tiempo necesario y haz de los comentarios algo útil. A continuación algunos consejos:
- Utilízalos para explicar el funcionamiento de un objeto, no para únicamente volver a repetir el nombre de la clase.
- No hagas las líneas de los comentarios extremadamente largas, ves añadiendo saltos de línea. Se toma un ancho de 80 columnas como estándar.
- Evita los comentarios al final de los bloques o secciones.

**Ejemplo de buen uso**
```css
/* --------------------------------------------------------------------------
  Comentario de sección. Ejemplo: Botones
  --------------------------------------------------------------------------- */
  
/* Comentario de sub-sección. Ejemplo: Botones del PTA
  --------------------------------------------------------------------------- */
  
/**
 * Comentario descriptivo sobre la clase.
 * 
 * Aquí debemos describir el funcionamiento de la clase para que esta quede
 * bien documentada y sirva a otros compañeros para entenderla. Recuerda 
 * hacer saltos de línea para que la descripción se pueda leer mejor.
 * 
 * También podemos añadir un TODO, indicando que algo está pendiente de hacer
 * o bien requiere de un cambio para mejorarlo.
 */
 
 /* Comentario de una sola línea */
```

**Nota:** Algunos preprocesadores permite el uso de `//` para los comentarios de una línea. Intenta evitarlos.


<a name="formato"></a>
## 4. Formato

En construcción :+1:

<a name="ordenprioridades"></a>
### Orden de prioridades

Ordenar correctamente las propiedades hará que todas las clases se "lean" de la misma forma. Una buena práctica es ordenar estas propiedades según su afectación: Posicionamiento, modelo, formato, tipología y otros.

```css
.orden-de-propiedades {
  /* Posicionamiento */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 10;

  /* Modelo */
  display: block;
  float: left;
  width: 100%;
  max-width: 300px;
  margin: 0 auto;
  
  /* Formato */
  border-radius: 3px 3px 0 0;
  background-color: #d9d9d9;
  border: 1px solid #333;
  box-shadow: 3px 3px 5px #ccc;
  
  /* Tipografía */
  font-size: 13px;
  line-height: 1.5;
  color: #030303;
  text-align: center;

  /* Otros */
  opacity: 0.8;
}
```


<a name="contribuciones"></a>
## 8. Contribuciones

Cualquier contribución es bienvenida, así que si tienes algo que ofrecer puedes hacerlo. Para aquellos que no sepáis como colaborar porque sois nuevos en GitHub comparto algunos enlaces:

- [Cómo colaborar en un proyecto](https://gist.github.com/BCasal/026e4c7f5c71418485c1).
- [Sintaxis de los ficheros de texto](https://help.github.com/articles/basic-writing-and-formatting-syntax/).
