## CampusShop - Aplicativo Web para Compra y Venta de Productos

### Descripción del Proyecto

CampusShop es un aplicativo web diseñado para gestionar la compra y venta de productos en un entorno de E-Commerce. En este proyecto, se busca continuar el desarrollo del FrontEnd del aplicativo, basándose en un proyecto base funcional que incluye una ejemplificación frontal y un servicio trasero que proporcionará la información necesaria.

### Requerimientos Técnicos

Para llevar a cabo la división del proyecto FrontEnd, es necesario tener en cuenta los siguientes puntos:

- La interfaz de usuario (UI/UX) debe seguir el wireframe propuesto por el equipo de diseño.

----



# Estructura HTML

Hay varias secciones del HTML que se repiten como:

- Es la pagina principal del proyecto, en esta podemos ver una barra de navegación la cual lleva al usuario al catalogo, a la sección *"nosotros"* y *"contáctenos"*
- En el footer contamos con un pequeño menú de navegación el cual nos permite también ir a varias secciones de la pagina

1. **index.html:**

   Cuenta con un banner el cual da una breve introducción al proyecto.

   Tiene una sección *"Productos"* en la cual se muestran los 3 productos mas vendidos durante el ultimo mes en la plataforma. La sección *"Nosotros"* da a saber al usuario nuestra misión, visión y objetivos como plataforma virtual.

2. **categoria.html:**

   Es la pagina donde se muestran todas las categorías disponibles, cuenta con animaciones para cada ítem y este mismo tiene un enlace al catalogo dependiendo de la categoría.

3. **carrito.html:**

   Tiene un contenedor en el que se muestran todos los productos añadidos al carrito, cada elemento tiene sus respectivas animaciones.

   Cuenta con un formulario para obtener la información requerida para poder hacer el envió de los productos comprados.

   

> **Debido a que el HTML y CSS en la pagina de cada categoría es prácticamente el mismo, únicamente el nombre de las clases de los contenedores para las imágenes, me voy a referir a los mismos como *categoriaProducto.html*** , **igualmente para la pagina de los productos, (*producto.html*).**



4. **categoriaProducto.html:**

   Cada producto esta compuesto por un contenedor con dos columnas, en la primera es donde están las imágenes dinámicas y en la segunda esta una breve descripción del producto y el botón que lleva a la pagina del producto.

   En total son 4 productos por cada categoriaProducto.html

5. **producto.html:**

   La primera sección de la pagina es el producto: Las imágenes dinámicas, la descripción y el botón para comprar.

   Cuenta con una tabla de características adicionales y una descripción mas detallada.

   Por ultimo, contamos con una sección de comentarios y reseñas.

***



# Estilos

### index.html

```css
 @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400&display=swap');

:root {
    --colorPrimario: #48CADB;
    --colorSecundario: #599FA8;
    --colorTerciario: #567275;
    --colorCuaternario: #124147;
    --white: #FFF;
    --black: #000;
}

/* GLOBAL STYLES */



* {
    box-sizing: border-box;
    margin: 0;
    font-family: 'Montserrat', sans-serif;
}
h1, h2, h3 {
    margin: 0;
    color: var(--colorPrimario);
}

p{
    color: var(--white);
}

body {
    background-color: var(--colorTerciario);
}
```

Estos son los estilos generales y globales

- **`@import url()`** -> Importo la fuente para poder usarla en la pagina

- **`:root {}`** -> Defino los colores como "variables" para poderlos usar mas fácilmente en el código
- **`* {}`**  -> Defino que todos los elementos tengan un margen de 0 de manera predeterminada, también que se use en todos los párrafos la fuente elegida
- **`h1, h2, h3 {}`** -> Defino el color para los títulos en la pagina
- **`p {}`** -> Defino el color predeterminado para los párrafos
- **`body {}`** -> Defino el color de fondo para el cuerpo de la pagina

**header:**

```css
/* NAVEGACION Y HEADER */

#header {
    background-color: var(--colorCuaternario);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
}

.navBar {
    display: flex;
    align-items: center;  
}

.linkNav {
    margin-left: 10px;
    margin-right: 10px;
    text-decoration: none;
    color: var(--white);
    font-size: 1.1rem;
    padding: 10px;
    transition: all 0.2s ease;
}
.linkNav:hover {
    background-color: var(--colorSecundario);
    color: var(--colorCuaternario);
    border-radius: 5px;
    padding: 10px;
    transform: scale(1.1);
}

.iconKart {
    margin-left: 10px;

    transition: all .5s linear;
}
.iconKart:hover {
    transform: rotateX(180deg);  
}
.navResponsive {
    visibility: hidden;
}

@media screen and (max-width: 600px) {
    #header {
        flex-direction: row;
    }

    .navResponsive {
        visibility: visible;
    }

    .contNav {
        position: fixed;
        clip-path: circle(0% at top left);
        top: 0;
        z-index: 2;
    }

    .navBar {
        display: flex;
        flex-direction: column;
        background-color: var(--colorTerciario);
        
    }

    .contNav {
        clip-path: circle(0% at top left);
        background-color: var(--colorTerciario);
        width: 100%;
        height: 100%;
        padding: 10px;
        opacity: 0.9;
    }

    .contNav:target {
        clip-path: circle(150% at top left);

    }
    .linkNav:hover {
        background-color: var(--colorSecundario);
        color: var(--white);
    }
}
```

Los estilos para el header y la barra de navegación:

- **`#header {}`** -> Establezco el color de fondo para el header, utilizo Flex Box para posicionar el icono home y el contenedor de los enlaces y alineo los elementos de manera vertical
- **`.navBar {}`** -> Utilizo Flex Box para posicionar los enlaces dentro del contenedor y se alinean verticalmente
- **`.linkNav {}`** -> Agrego separación entre los enlaces y estilizo los enlaces, agrego una transición para cuando el cursor pase sobre el enlace
- **`.linkNav:hover {}`** -> Cuando el cursor pase sobre el enlace el color de fondo va a cambiar y se va a escalar 1.1 veces el enlace
- **`.iconKart {}`** -> Agrego separación y una una transición para cuando el cursor pase sobre el icono
- **`.iconKart:hover {}`** -> Cuando el cursor pase sobre el icono va a rotar en el eje X 180°
- **`.navResponsive {}`** -> Clase que me permite esconder el icono de la barra de navegación cuando la pantalla sea lo suficientemente grande
- **`@media screen and (max-width: 600px) {}`** -> Propiedades CSS que se aplicaran cuando en ancho de pantalla sea mayor a 600px
  - **`#header {}`** -> Cambio la dirección del Flex Box a columna
  - **`.navResponsive {}`** -> Cambio la visibilidad, vuelvo visible el icono de la barra de navegación responsiva 
  - **`.contNav {}`** -> Establezco la posición del menú en el tope de la pagina, hago que no sea visible y coloco el menú desplegable, establezco al máximo el ancho y alto del menú y le aplico una opacidad del 0.9
  - **`.contNav:target {}`** -> Cuando el input del menú este activado va a mostrar el resto
  - **`.linkNav:hover {}`** -> Cuando el mouse este sobre el enlace va a cambiar el color de fondo y del texto

**banner:**

```css
/* Banner */

.contBig {
    max-width: 100%;
    height: 790px;
    background-image: url("/CampusShop/img/bannerBig.jpg");
    background-repeat: no-repeat;
    background-position: top;
    background-size:cover;

    box-shadow: inset 0px 0px 600px 200px rgba(0,0,0,0.15);
}

.separador {
    width: 100%;
    height: 40px;
    background-color: var(--colorSecundario);
}

#banner {
    
    background-color: var(--colorCuaternario);
    padding: 1%;
    width: 80%;
    display: grid;
    justify-content: center;
    align-items: center;
    grid-template-columns: 1fr 1fr;
    margin: auto;
}

.logoBanner {
    max-width: 100%;
}

.contTxt {
    padding: 5%;
    display: flex;
    flex-direction: column;
    gap: 10px;
    justify-content: center;
    height: min-content;
    width: 70%;
    margin: auto;

    background-color: var(--colorTerciario);
    border-radius: 10px;
}

@media screen and (max-width: 600px) {
    #banner {
        margin: 0;
        width: 100%;
        grid-template-columns: 100%;
        grid-template-rows: 1fr 1fr;

        align-items: center;
    }

    .contTxt {
        margin: auto;
        width: 100%;
        background-color: var(--white);
        color: var(--black);
        text-align: center;

        border-radius: 0;
    }

    .pBanner {
        color: var(--black);
    }

    .contBig {
        width: 100%;
        background-size: cover;
        background-position: right;
    }
}
```

Banner del main - hecho responsivo

- **`.contBig `** -> Crea un contenedor con una imagen de fondo que cubre la altura fija
- **`.separador`** -> Es un elemento visual con un color de fondo que puede utilizarse para separar visualmente secciones en una página
- **`#banner {}`** -> Establece un estilo para un área denominada "banner", diseño en cuadrícula con  dos columnas de igual tamaño, centrando su contenido tanto horizontal  como verticalmente
- **`.logoBanner`** -> Define un estilo para las imágenes con la clase "logoBanner", estableciendo que su ancho máximo será del 100%.
- **`.contTxt {}`** ->  Establece estilos para un contenedor de texto, relleno del 5%, dirección del Flex Box en columna, espaciado entre  elementos de 10 píxeles, justificación y alineación central, altura  mínima de contenido, ancho del 70%, margen automático, color de fondo y bordes redondeados
- **`@media screen and (max-width: 600px) {}`** 
  - **`#banner`** -> Establece estilos adicionales para la sección "banner", eliminando el margen, ocupando el 100% del ancho, cambiando a una sola columna en la cuadrícula, estableciendo dos filas iguales, centrando los elementos verticalmente.
  - **`.contTxt`** -> Ajusta estilos para el contenedor de texto, centrando horizontalmente con margen automático, ocupando el 100% del ancho, con fondo blanco, texto de color negro y alineación central.
  - **`.pBanner`** -> Define estilos para los elementos de párrafo, estableciendo el color del texto en negro.
  - **`.contBig`** -> Ajusta estilos para el contenedor, estableciendo un ancho del 100%, con la imagen de fondo que cubre completamente el área y posicionada a la derecha.

**Productos:**

```css
/* Productos */ 

#productos {
    text-align: center;
    margin-top: 5%;
}

.contProductos {
    display: flex;
    justify-content: space-around;

    margin-top: 3%;
}

.producto {
    background-color: var(--colorCuaternario);
    padding: 30px;
    border-radius: 10px;
    
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 15px;
}

.contImgProducto1, .contImgProducto2, .contImgProducto3 {
    width: 300px;
    height: 250px;
    background-repeat: no-repeat;
    background-position-y: top;
    background-size: cover;
    border-radius: 10px;
    border: solid 2px var(--colorPrimario);

    transition: all 0.2s ease;
    filter: saturate(20%);
}

.contImgProducto1 {
    background-image: url("/CampusShop/img/Categorias/Portatiles/portatil1/productoGrande.webp");
}

.contImgProducto2 {
    background-image: url("/CampusShop/img/Categorias/Camisas/camisa2/productoGrande.webp");
}

.contImgProducto3 {
    background-image: url("/CampusShop/img/Categorias/Camaras/camara2/productoGrande.webp");
}
.contImgProducto1:hover, .contImgProducto2:hover, .contImgProducto3:hover {
    transform: scale(1.1);

    background-position-y: center;
    background-size: 1.2;
    filter: brightness(80%);
    filter: saturate(100%);
}

.tMains {
    color: var(--colorPrimario);
    text-align: center;
}

.btnObtener {
    background-color: var(--colorSecundario);
    border: solid 2px var(--colorTerciario);
    width: 80%;
    padding: 10px;
    color: var(--white);
    border-radius: 10px;

}

.btnObtener:hover {
    animation: colorChange 2s infinite ease-in-out;
    color: var(--black);

    border: solid 2px;
}

@keyframes colorChange {
    0% {
        background-color: var(--colorSecundario);
        border: solid 2px var(--colorTerciario);
    }
    10% {
        background-color: #9400D3;
        border: solid 2px #9400D3;
    }
    33% {
        background-color: #0000FF;
        border: solid 2px #0000FF;
    }
    66% {
        background-color: #00FF00;
        border: solid 2px #00FF00;
    }
    100% {
        background-color: #FF0000;
        border: solid 2px #FF0000;

    }
}

@media screen and (max-width: 600px) {
    .contProductos {
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 20px;
    }
    .producto {
        width: 90%;
    }
}
```



- **`#productos`** -> Establece estilos para la sección "productos", centrando el texto horizontalmente y agregando un margen en la parte superior del 5%.

- **`.contProductos`** -> Define estilos para el contenedor utilizando un diseño Flex para alinear los elementos en el centro y alrededor del contenedor, con un margen en la parte superior del 3%.

- **`.producto`** -> Establece estilos para cada elemento, color de fondo, relleno de 30px, y bordes redondeados de 10px. Utiliza un diseño flex para organizar los elementos en columna, centrando el contenido tanto horizontal como verticalmente, con un espacio entre elementos de 15px.

- **`.contImgProducto1, .contImgProducto2, .contImgProducto3`** -> Define estilos para contenedores de imágenes de productos, estableciendo un tamaño de 300x250 píxeles, con fondo de imagen, borde sólido de 2px y transición suave de 0.2 segundos. Además, aplica un filtro de saturación del 20%.

- **`.contImgProducto1, .contImgProducto2, .contImgProducto3`** -> Establece la imagen de fondo para cada contenedor de producto correspondientes.
- **`.contImgProducto1:hover, .contImgProducto2:hover, .contImgProducto3:hover {}`** -> Definen efectos visuales para para el contenedor de la imagen del producto al pasar el ratón sobre ellos, incluyendo un  aumento de tamaño, centrado vertical de la imagen de fondo, zoom de la  imagen, atenuación del brillo y saturación completa de los colores

- **`.tMains`** -> Define el color del texto y centra el texto en el elemento.
- **`.btnObtener`** -> Establece el fondo del botón un borde sólido de 2 píxeles, un ancho del 80%, un relleno de 10 píxeles, el color del texto como blanco, y un radio de borde de 10 píxeles para redondear las esquinas.
- **`.btnObtener:hover`** -> Define los estilos cuando el botón está en estado de "hover" (cuando el usuario pasa el ratón sobre él). Incluye una animación llamada `colorChange` con duración de 2 segundos, que alterna entre diferentes colores de fondo y borde, y cambia el color del texto a negro. La animación se repite infinitamente con un efecto de entrada y salida suave.
- **`@keyframes colorChange`** -> Define la animación `colorChange` que alterna los colores de fondo y borde del botón en diferentes porcentajes de la animación. Inicia con el color secundario y terciario, pasa por varios colores y finalmente regresa al color secundario y terciario. Esta animación crea un efecto de cambio de color cíclico en el botón cuando se realiza la interacción.
- **`@media screen and (max-width: 600px) {}`** 
  - **`.contProductos`** -> Organiza elementos en una columna centrada con espacio entre ellos.
  - **`.producto`** -> Limita el ancho de los elementos al 90% del contenedor.

**Nosotros:**

```css
#nosotros {
    margin-top: 5%;
    background-color: var(--colorSecundario);
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    justify-content: center;
    margin-bottom: 5%;
    padding: 20px;
}

.contAbout {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    text-align: center;
    flex-direction: column;
    gap: 20px;

    background-color: var(--colorCuaternario);
    width: 70%;
    border-radius: 10px;
    padding: 20px;
}

.itemAbout {
    margin-top: 2%;
    width: 80%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.contImgWe {
    margin: auto;
}

@media screen and (max-width: 600px) {
    #nosotros {
        grid-template-columns: 1fr;
        grid-template-rows: 1fr 1fr;
        justify-content: center;
        align-items: center;
    }

    .contAbout {
        width: 100%;
        margin: auto;
        border-radius: 0;
    }

    .imgWe {
        margin: auto;
        max-width: 100%;
    }
}
```



- **`#nosotros`**-> Establece un diseño de dos columnas con un margen superior del 5%, fondo de color secundario, y ajusta el espacio y alineación.

- **`.contAbout`** -> Presenta un contenedor con elementos flexibles y centrados, con fondo cuaternario, ancho del 70%, y bordes redondeados.

- **`.itemAbout`**-> Define elementos con disposición en columna, centrados y con un margen superior del 2%.

- **`.contImgWe`**-> Centra las imágenes.

- **`@media screen and (max-width: 600px) {}`** 
  - **`#nosotros`** -> Ajusta a una única columna, centrando los elementos.
  - **`.contAbout`** -> Ocupa el ancho completo y elimina los bordes redondeados.
  - **`.imgWe`** -> Ajusta el ancho máximo al 100%.

**Footer:**

```css
#footer {
    background-color: var(--colorCuaternario);
}

.contFooter {
    display: flex;
    justify-content: space-around;
}
.tFooter {
    color: var(--white);
    font-size: 1.7rem;
}

.subFooter {
    padding-top: 4rem;
}

.contTitulo {
    margin-top: 40px;
    color: var(--white);
    border-bottom: 3px solid var(--colorSecundario);
}
.contInfo {
    display: flex;
    flex-direction: column;
    padding: 20px;
}

.txtFooter {
    color: var(--white);
    font-size: 1.3rem;
}

.contContacto {
    display: flex;
    flex-direction: row;
    padding-top: 30px;
    gap: 1rem;
}

.circulo {
    background-color: var(--colorPrimario);
    border-radius: 50%;
    width: 2rem;
    height: 2rem;
}

.linkFooter {
    text-decoration: none;
    font-size: 1.3rem;
    color: var(--colorPrimario);
}

@media screen and (max-width: 600px) {
    .contFooter {
        width: 100%;
        flex-direction: column;
        align-items: center;
        text-align: left;
        gap: 10px;
    }
    .contInfo {
        padding: 20px;
    }
    .linkFooter {
        padding: 10px;
    }
}
```

- **`#footer`** -> Configura el fondo del pie de página con el color cuaternario.

- **`.contFooter`** -> Organiza los elementos del pie de página en una fila con espaciado uniforme.

- **`.tFooter`** -> Define el estilo del texto del pie de página con color blanco y tamaño de fuente de 1.7rem.

- **`.subFooter`** -> Añade un espacio de relleno en la parte superior de 4rem.

- **`.contTitulo`** -> Configura un contenedor para el título con margen superior, color blanco y un borde inferior sólido de 3px con color secundario.

- **`.contInfo`** -> Establece un contenedor para la información con disposición en columna y relleno de 20px.

- **`.txtFooter`** -> Define el estilo del texto del pie de página con color blanco y tamaño de fuente de 1.3rem.

- **`.contContacto`** -> Coloca los elementos de contacto en una fila con un espacio de 1rem entre ellos.

- **`.circulo`** -> Configura un círculo con fondo del color primario y dimensiones de 2rem x 2rem.

- **`.linkFooter`** -> Establece el estilo de los enlaces del pie de página con sin decoración, tamaño de fuente de 1.3rem y color del color primario.

- **`@media screen and (max-width: 600px) {}`** 

  - `.contFooter`: Ajusta la disposición a una columna, centrando los elementos y alineándolos a la izquierda.

  - `.contInfo`: Incrementa el espacio de relleno.

  - `.linkFooter`: Incrementa el espacio de relleno para los enlaces.

## Catálogos

```css
#categorias {
    margin-top: 100px;

    text-align: center;
}

.contCategorias {
    display: grid;
    grid-template-rows: 1fr 1fr;
    gap: 50px;
    margin: 40px;
}

.fila {
    display: flex;
    justify-content: space-evenly;
    gap: 10px;
}

.contImgProductoCamaras, .contImgProductoCamisas, .contImgProductoCelulares, .contImgProductoPortatiles, .contImgProductoZapatos {
    width: 400px;
    height: 350px;
    background-repeat: no-repeat;
    background-position-y: center;
    background-size: cover;
    border-radius: 10px;
    border: solid 2px var(--colorPrimario);

    transition: all 0.2s ease;
    filter: saturate(20%);
}
.contImgProductoCamaras {
    background-image: url("/CampusShop/img/Categorias/Camaras/camara3/productoGrande.webp");
}
.contImgProductoCamisas {
    background-image: url("/CampusShop/img/Categorias/Camisas/camisa4/productoGrande.webp");
}
.contImgProductoCelulares {
    background-image: url("/CampusShop/img/Categorias/Celulares/celular4/productoGrande.webp");
}
.contImgProductoPortatiles{
    background-image: url("/CampusShop/img/Categorias/Portatiles/portatil1/productoGrande.webp");
}
.contImgProductoZapatos {
    background-image: url("/CampusShop/img/Categorias/Zapatos/zapato3/productoGrande.webp");
}

.contImgProductoCamaras:hover, .contImgProductoCamisas:hover, .contImgProductoCelulares:hover, .contImgProductoPortatiles:hover, .contImgProductoZapatos:hover {
    transform: scale(1.1);

    background-position-y: top;
    background-size: 1.1;
    filter: brightness(80%);
    filter: saturate(100%);
}

@media screen and (max-width: 600px) {
    #categorias {
        margin-top: 100px;
        justify-content: center;
    }

    .contCategorias {
        grid-template-columns: 100%;
        grid-template-rows: 50% 50%;
    }
    .fila {
        flex-direction: column;
        gap: 40px;
        align-items: center;
    }

    .contImgProductoCamaras, .contImgProductoCamisas, .contImgProductoCelulares, .contImgProductoPortatiles, .contImgProductoZapatos{
        width: 300px;
        height: 200px;
    }
}
```

- **`#categorias`** -> Establece un margen superior de 100px y centrado de texto.
- **`.contCategorias`** -> Organiza los elementos en un grid de dos filas con un espacio entre ellas de 50px, y un margen de 40px.
- **`.fila`** -> Configura un contenedor de fila con elementos distribuidos uniformemente y un espacio entre ellos de 10px.
- **`.contImgProductoCamaras, .contImgProductoCamisas, .contImgProductoCelulares, .contImgProductoPortatiles, .contImgProductoZapatos`** -> Establece las dimensiones y estilo común para las imágenes de productos en diferentes categorías. Incluye una transición de 0.2s y un filtro de saturación del 20%.
  - **`.contImgProductoCamaras`** -> Asigna una imagen de fondo para la categoría de cámaras.
  - **`.contImgProductoCamisas`** -> Asigna una imagen de fondo para la categoría de camisas.
  - **`.contImgProductoCelulares`** -> Asigna una imagen de fondo para la categoría de celulares.
  - **`.contImgProductoPortatiles`** -> Asigna una imagen de fondo para la categoría de portátiles.
  - **`.contImgProductoZapatos`** -> Asigna una imagen de fondo para la categoría de zapatos.
- **`.contImgProductoCamaras:hover, .contImgProductoCamisas:hover, .contImgProductoCelulares:hover, .contImgProductoPortatiles:hover, .contImgProductoZapatos:hover`** -> Establece estilos adicionales para las imágenes de productos al pasar el ratón sobre ellas, incluyendo un aumento de escala, cambio de posición y tamaño de fondo, y ajustes en el brillo y saturación.
- **`@media screen and (max-width: 600px)`**
  - **`#categorias`** -> Ajusta el margen superior y centra el contenido.
  - **`.contCategorias`** -> Cambia el diseño a una sola columna y ajusta las filas a un 50% de altura cada una.
  - **`.fila`** -> Cambia la dirección de la fila a columna, ajusta el espacio entre elementos y los centra.
  - **`.contImgProductoCamaras, .contImgProductoCamisas, .contImgProductoCelulares, .contImgProductoPortatiles, .contImgProductoZapatos`** -> Modifica las dimensiones de las imágenes para adaptarse a pantallas más pequeñas.

## Catalogos

```css
/* ************** CATALOGOS ******************** */

#contCatalogos {
    display: flex;
    flex-direction: column;
    gap: 50px;
    width: 80%;
    justify-content: center;
    align-items: center;
    margin: auto;
    margin-top: 100px;
}

.contProductoCatalogo {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin-top: 50px;
    margin-bottom: 20px;
    background-color: var(--colorCuaternario);
    padding: 40px;
    border-radius: 10px;
}

.infoProducto {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 20px;
}

.precios {
    display: flex;
    width: 100px;
    justify-content: space-between;

}

.precio {
    font-size: 20px;
}
.precioTachado {
    text-decoration: line-through;
    color: red;
    font-size: 15px;
}
```

- **`#contCatalogos`** -> Contenedor principal para catálogos con disposición en columna, espacio entre elementos de 50px, ancho del 80%, centrado horizontal y verticalmente, y margen superior de 100px.
- **`.contProductoCatalogo`** -> Productos organizados en un grid de dos columnas con espacio entre ellas de 20px, estilo de fondo, relleno, y bordes redondeados.
- **`.infoProducto`** -> Contenedor para información del producto con disposición en columna, espacio entre elementos de 20px, y centrado vertical.
- **`.precios`** -> Contenedor para precios con disposición en fila, ancho de 100px y espacio uniforme entre elementos.
- **`.precio`** -> Tamaño de fuente del precio: 20px.
- **`.precioTachado`** -> Estilo de tachado al precio, color rojo, y tamaño de fuente de 15px.

## Productos

```css
/*************** PRODUCTOS (20) **********************/

.contImg{
    display: grid;
    grid-template-columns: 30% 70%;
    grid-template-rows: 1fr 1fr;
    gap: 20px;
}

/* Producto */

.imgPeque1, .img2Peque1 {
    align-items: center;
    width: 100px;
    height: 100px;
    background-repeat: no-repeat;
    background-size: cover;

    transition: all 0.1s ease-in;
}

.imgPequea1 {
    background-image: url("/CampusShop/img/productoPeque.webp");
}
.img2Peque1 {
    background-image: url("/CampusShop/img/img2Peque.webp");
}

.contImgGrande1 {
    width: 90%;
    height: 376px;
    grid-column: 2 / 2;
    grid-row: 1 / span 2;
    background-image: url("/CampusShop/img/productoGrande.webp");
    background-repeat: no-repeat;
    background-position: center;
}

.imgPeque1:hover ~ .contImgGrande1{
    background-image: url("/CampusShop/img/Categorias/Camaras/camara1/productoGrande.webp");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;

}

.img2Peque1:hover ~ .contImgGrande1{
    background-image: url("/CampusShop/img/Categorias/Camaras/camara1/img2Grande.webp");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
} 
```

- **`.contImg`** -> Contenedor para imágenes con grid de dos columnas (30%, 70%) y dos filas, con espacio entre elementos de 20px.
- **`.imgPeque1, .img2Peque1`** -> Imágenes pequeñas del producto con tamaño de 100px x 100px, fondo repetido en cover y transición suave.
  - **`.imgPeque1`** -> Imagen principal del producto.
  - **`.img2Peque1`** -> Segunda imagen pequeña del producto.
- **`.contImgGrande1`** -> Contenedor para la imagen grande del producto, ocupa el 90% de ancho y 376px de alto, ubicado en la segunda columna y abarca dos filas.
- **`.imgPeque1:hover ~ .contImgGrande1`** -> Cambia la imagen grande al hacer hover en la imagen principal pequeña del producto.
- **`.img2Peque1:hover ~ .contImgGrande1`** -> Cambia la imagen grande al hacer hover en la segunda imagen pequeña del producto.

***

# Enlaces Productos usados

## ZAPATOS

https://articulo.mercadolibre.com.co/MCO-1194588686-zapatos-tenis-bota-en-lona-zeus-tradicional-marca-venus-_JM#position=13&search_layout=grid&type=item&tracking_id=8ed95632-de00-4736-a9bd-4e14d8f9ce37

https://articulo.mercadolibre.com.co/MCO-635890018-zapato-tenis-bota-de-lona-marca-venus-_JM#reco_item_pos=0&reco_backend=pads-retrieval-model&reco_backend_type=low_level&reco_client=vip-pads-up&reco_id=3ba9873a-c8ce-4331-9dad-d217347602a8&reco_backend_model=pads_retrieval_model&is_advertising=true&ad_domain=VIPDESKTOP_UP&ad_position=1&ad_click_id=MWQ5NDQ3NzYtY2I0Ni00NGVjLTk1YjktYzk3ODFhODNhNjJk

https://articulo.mercadolibre.com.co/MCO-1098144250-zapatos-colegial-10-new-blanco-para-nino-y-nina-croydon-_JM#position=17&search_layout=grid&type=item&tracking_id=cff8188c-88b5-403e-8c5f-2fd4ecd149f2

https://articulo.mercadolibre.com.co/MCO-1944036462-tenis-bl-active-negro-ward-hombre-vans-_JM#position=24&search_layout=grid&type=item&tracking_id=0a8350a9-2d9a-4a75-a90e-26e97825060b

## PORTATILES 

https://www.mercadolibre.com.co/portatil-asus-e1504fa-nj474-ryzen-5-7520u-ram-16gb-ssd-512gb-color-negro/p/MCO23498360?pdp_filters=item_id:MCO1877326862#is_advertising=true&searchVariation=MCO23498360&position=1&search_layout=stack&type=pad&tracking_id=f3de8903-2e09-4f7f-a38a-c4e17d0b99ce&is_advertising=true&ad_domain=VQCATCORE_LST&ad_position=1&ad_click_id=MzYyZDllMjQtNDIxMC00ZjY1LWFiOTAtZmM5YmRiMWEzNDZi

https://www.mercadolibre.com.co/portatil-gamer-asus-tuf-gaming-f15-fx506hc-eclipse-gray-156-intel-core-i5-11400h-16gb-de-ram-1512gb-ssd-nvidia-geforce-rtx-3050-144-hz-1920x1080px-windows-10-home/p/MCO20885775#searchVariation=MCO20885775&position=21&search_layout=stack&type=product&tracking_id=74960812-b508-4f4b-ba93-45942794785b

https://www.mercadolibre.com.co/macbook-air-m2-2022-space-gray-136-apple-m2-8gb-de-ram-256gb-ssd-apple-m2-10-core-gpu-2560x1664px-macos/p/MCO19563444#searchVariation=MCO19563444&position=11&search_layout=stack&type=product&tracking_id=a3a0242f-c7ce-46bc-b22e-c5fb829e3a41

https://www.mercadolibre.com.co/portatil-asus-rog-strix-g16-gaming-g614-eclipse-gray-intel-core-i7-13650hx-16gb-de-ram-512gb-ssd-nvidia-geforce-rtx-4060-8gb-165-hz-1920x1200px-windows-11-home/p/MCO23358076?pdp_filters=category:MCO1652#searchVariation=MCO23358076&position=18&search_layout=stack&type=product&tracking_id=51bb9fcb-73de-44be-b2b4-b5ffd3013665

## CELULARES

https://www.mercadolibre.com.co/apple-iphone-13-128-gb-azul-medianoche/p/MCO18500844?pdp_filters=item_id:MCO1166708894#is_advertising=true&searchVariation=MCO18500844&position=1&search_layout=stack&type=pad&tracking_id=d4e32248-4717-4a28-8001-5ef2899207d8&is_advertising=true&ad_domain=VQCATCORE_LST&ad_position=1&ad_click_id=YTNhMWE0NTItOTc0Yy00YmVmLTlhZmUtZTViODhmYzZiZGZi

https://www.mercadolibre.com.co/celular-tecno-spark-10-pro-256gb-8ram-50mp/p/MCO22739138?pdp_filters=category:MCO1055#searchVariation=MCO22739138&position=4&search_layout=stack&type=product&tracking_id=920778da-c258-4c3b-8bea-fb07ce9ca559

https://www.mercadolibre.com.co/apple-iphone-15-128-gb-azul/p/MCO27172667?pdp_filters=category:MCO1055#searchVariation=MCO27172667&position=20&search_layout=stack&type=product&tracking_id=dab5d410-215c-48ba-b92d-2c844db66fe4

https://www.mercadolibre.com.co/tecno-camon-20-dual-sim-256-gb-predawn-black-8-gb-ram/p/MCO23606576?pdp_filters=category:MCO1055#searchVariation=MCO23606576&position=21&search_layout=stack&type=product&tracking_id=a58bb587-2c6c-4c7f-b04b-623b55140089

## CAMISAS

https://articulo.mercadolibre.com.co/MCO-593045146-camiseta-gojira-from-mars-to-sirius-rock-activity-_JM?searchVariation=179452969533#searchVariation=179452969533&position=11&search_layout=stack&type=item&tracking_id=dcae9cc3-28a1-430b-88cc-7305f970c7a3

https://articulo.mercadolibre.com.co/MCO-532093956-camiseta-manga-caida-camiseta-oversize-_JM?searchVariation=179852638011#searchVariation=179852638011&position=22&search_layout=stack&type=item&tracking_id=aee5ac85-9405-4e0f-85a6-071f98ba657e

https://articulo.mercadolibre.com.co/MCO-816000567-camiseta-japonesa-hombre-camiseta-gym-manga-sisa-hombre-_JM?searchVariation=179852638205#searchVariation=179852638205&position=27&search_layout=stack&type=item&tracking_id=247434c5-e4db-48f5-9f3f-36c49e2ab9e9

https://articulo.mercadolibre.com.co/MCO-648087582-camisa-oxford-dotacion-empresarial-clasica-_JM#position=4&search_layout=grid&type=item&tracking_id=cd8f90f0-a19f-4793-91e4-f99809594dff

## CAMARAS

https://www.mercadolibre.com.co/sony-alpha-kit-zv-e10-lente-16-50mm-f35-56-oss-ilczve10l-sin-espejo-color-negro/p/MCO18448013#searchVariation=MCO18448013&position=8&search_layout=stack&type=product&tracking_id=cac09190-38a0-49b6-9c88-a50d0273d854

https://www.mercadolibre.com.co/camara-profesional-sony-de-242mp-y-videos-4k-ilce-6400l-color-negro/p/MCO14689744#searchVariation=MCO14689744&position=7&search_layout=stack&type=product&tracking_id=c96fe888-b1b2-4d3d-9938-0532e1a2a005

https://www.mercadolibre.com.co/canon-eos-kit-2000d-lente-18-55mm-is-ii-dslr-color-negro/p/MCO18544086#searchVariation=MCO18544086&position=17&search_layout=stack&type=product&tracking_id=33640875-cc6a-461e-a01d-bcf3204b0ec3

https://www.mercadolibre.com.co/nikon-coolpix-p950-compacta-color-negro/p/MCO15955774#searchVariation=MCO15955774&position=24&search_layout=stack&type=product&tracking_id=9364612c-8efd-4e18-aeca-6869f3486ef4