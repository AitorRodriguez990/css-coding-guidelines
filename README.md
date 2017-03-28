# Directrices de codificación CSS de Pisos

Este documento tiene la intención de ser un punto de referencia para aquellos desarrolladores que deban escribir código CSS. Aquí no se encuentran normas o leyes, sino sugerencias.

El objetivo es conseguir un código CSS ordenado, limpio y reutilizable.


## Tabla de contenidos

1. [Introducción](#introduccion)
2. [Nombre de clases](#nombreclases)
3. [Comentarios](#comentarios)
4. [Formato](#formato)
    - [Orden de propiedades](#ordenprioridades)
    - [Declaraciones individuales](#declaracionesindividuales)
    - [Prefijo de propiedades](#prefijopropiedades)
    - [Media queries](#mediaqueries)
    - [Selectores y anidamiento](#selectoresyanidamiento)
5. ~~Configuración del editor~~
6. [Enlaces de interés](#enlacesinteres)
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

  - Cuando se apliquen las mismas propiedades a varias clases añade cada una de estas en una nueva línea.
  - Abre la declaración de propiedades con `{` en la misma línea que declares la clase y después de un espacio. Pon el cierre `}` en una nueva línea.
  - Deja una línea en blanco entre clases.
  - Añade un espacio después de `:`. Solo uno.
  - Acaba siempre con `;` cada una de las propiedades, aunque sea la última o única propiedad.
  - En valores hexadecimales utiliza mayúsculas y códigos abreviados: `color: #ccc`.
  - Haz siempre uso de comillas dobles: `content: ""`.
  - No indiques unidades en valores 0 siempre que sea posible: `margin: 0 auto`.
  - Indica siempre 0 a valores con coma menores a uno. Mejor `opacity: 0.8` que `opacity: .8` porque resultará más fácil de leer. 
  - Deja un espacio después de cada valor dentro de una función: `background-color: rgba(0, 0, 0, 0.7)`.
  - Añade comillas en los valores de los atributos de los selectores: `input[type="text"]`. En algunos casos no son necesarios, pero de esta manera evitamos errores.
  - Evita el uso de `!important`. En muchos casos es necesario por no haber sabido hacer las cosas bien.
  
**Ejemplo de buenas prácticas**
```css
.clase1,
.clase2,
.clase3 {
  color: #ccc;
  font-weight: bold;
  content: "|";
}

.clase4 {
  color: #c2c2c2;
}

.clase5 { margin: 0 10px 5px 0; }
```


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


<a name="declaracionesindividuales"></a>
### Declaraciones individuales

Solo en clases con una única propiedad es conveniente mantenerlo todo escrito en una sola línea añadiendo espacios dentro de las llaves. Las clases con múltiples propiedades nunca se deben escribir en una sola línea, ya que en caso de error de compilación no sabremos que propiedad es la que nos está fallando.

```css
.una-propiedad { color: #333; }

.multiples-propiedades {
  color: #444;
  font-size: 18px;
  font-weight: bold;
}

```


<a name="prefijopropiedades"></a>
### Prefijo de prioridades

Es conveniente alinear correctamente aquellas propiedades que necesitan de prefijos específicos para navegadores, de esta manera se facilita la lectura y comprensión.

```css
.prefijo-de-propiedades {
  -webkit-border-radius: 3px;
     -moz-border-radius: 3px;
          border-radius: 3px;
}

```


<a name="mediaqueries"></a>
### Media queries

Añade los *media queries* inmediatamente después de su clase y no en otro fichero o al final del fichero, ya que cuando queramos modificar algo será más fácil de localizar.

```css
.formulario-contacto {
  width: 300px;
  font-size: 16px;
}

@media screen and (min-width: 768px) and (max-width: 991px) {
  .formulario-contacto {
    width: 225px;
    font-size: 14px;
  }
}
```

**Nota**: Esto únicamente aplica a vistas *responsive*. No aplicará en caso de tener diferentes vistas para escritorio y móvil puesto será más óptimo cargar un fichero independiente con menos código CSS.


<a name="selectoresyanidamiento"></a>
### Selectores y anidamiento

- Para conseguir que el código CSS sea lo más ordenado, limpio y reutilizable posible es necesario pensar en componentes. De esta manera no habrá necesidad de crear selectores muy específicos que en otras muchas situaciones será necesario sobrescribir.
- Aplicar propiedades sobre clases y no sobre etiquetas mejora el rendimiento y evita equivocaciones aplicando estilos donde no queremos. Mejor `.titulo-1 { color: #333; }` que `h1 { color: #333; }`.

A continuación muestro un ejemplo de un código CSS *común* y uno añadiendo prefijos a las clases, el cual se basa en los componentes y mejor la comprensión del código:

**Mal**

```html
<div class="inmobiliaria">
  <div class="nombre">
    Nombre inmobiliaria
  </div>
  <div class="descripcion">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer et facilisis leo.
  </div>
  <div class="contactar">
    Contactar
  </div>
</div>
```

```css
.inmobiliaria { }
.inmobiliaria .nombre { }
.inmobiliaria .descripcion { }
.inmobiliaria .contactar { }
```

**Bien**

```html
<div class="inmobiliaria">
  <div class="inmobiliaria-nombre">
    Nombre inmobiliaria
  </div>
  <div class="inmobiliaria-descripcion">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer et facilisis leo.
  </div>
  <div class="inmobiliaria-contactar">
    Contactar
  </div>
</div>
```

```css
.inmobiliaria { }
.inmobiliaria-nombre { }
.inmobiliaria-descripcion { }
.inmobiliaria-contactar { }
```


<a name="enlacesinteres"></a>
## 6. Enlaces de interés

- [Comillas en los valores de los atributos](https://mathiasbynens.be/notes/unquoted-attribute-values#css).
- [Stop a la cascada de estilos](http://markdotto.com/2012/03/02/stop-the-cascade/).


<a name="contribuciones"></a>
## 8. Contribuciones

Cualquier contribución es bienvenida, así que si tienes algo que ofrecer puedes hacerlo. Para aquellos que no sepáis como colaborar porque sois nuevos en GitHub comparto algunos enlaces:

- [Cómo colaborar en un proyecto](https://gist.github.com/BCasal/026e4c7f5c71418485c1).
- [Sintaxis de los ficheros de texto](https://help.github.com/articles/basic-writing-and-formatting-syntax/).
