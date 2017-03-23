# Directrices de codificación CSS de Pisos

Este documento tiene la intención de ser un punto de referencia para aquellos desarrolladores que deban escribir código CSS. Aquí no se encuentran normas o leyes, sino sugerencias.

En construcción :+1:


## Tabla de contenidos

1. [Introducción](#introduccion)
2. ~~Formato~~
3. ~~Comentarios~~ 
4. [Nombre de clases](#nombreclases)
5. ~~Orden de propiedades~~
6. ~~Prefijo de propiedades~~
7. ~~Selectores~~
8. ~~Anidamiento~~
9. ~~Media queries~~
10. ~~Configuración del editor~~
11. ~~Otros enlaces de interés~~
12. ~~Agradecimientos~~
13. [Contribuyendo](#contribuyendo)


<a name="introduccion"></a>
## 1. Introducción

> "Para triunfar es necesario, más que nada, tener sentido común." - Napoleón Bonaparte

Son muchas las sugerencias que aquí se pueden leer, pero podemos resumirlo en:
- Todo el código CSS/LESS debe parecer escrito por la misma persona.
- Si después de consultar esta guía aún te surgen dudas sobre como hacer algo es probable que haya un vacío en ella, por lo que hay que mejorarla. ¡Ayuda a mejorarla!


<a name="nombreclases"></a>
## 4. Nombre de clases

A la hora de nombrar clases a las que aplicar estilos estas deberían seguir las siguientes reglas:
- Utiliza minúsculas y guiones para separar las palabras, no utilices guiones bajo o *camelCase*.
- Puedes recortar palabras siempre y cuando sigan siendo entendibles, de otra manera el nombre perdería su sentido.
- Añade prefijos a los nombres de las clases haciendo referencia a su *padre*, si lo tuviera. Será más fácil de saber que hace esta clase.

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


<a name="contribuyendo"></a>
## 13. Contribuyendo

Cualquier contribución es bienvenida, así que si tienes algo que ofrecer puedes hacerlo. Para aquellos que no sepáis como colaborar porque sois nuevos en GitHub comparto algunos enlaces:

- [Cómo colaborar en un proyecto](https://gist.github.com/BCasal/026e4c7f5c71418485c1).
- [Sintaxis de los ficheros de texto](https://help.github.com/articles/basic-writing-and-formatting-syntax/).
