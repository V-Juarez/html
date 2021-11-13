# Sistemas de Diseño para Desarrolladores

#### Rulótico González

# Tabla de Contenido

- [Sistemas de Diseño para Desarrolladores](#sistemas-de-diseño-para-desarrolladores)
      - [Rulótico González](#rulótico-gonzález)
- [Tabla de Contenido](#tabla-de-contenido)
  - [Introducción](#introducción)
    - [Introducción y presentación](#introducción-y-presentación)
    - [Conoce Sistemas de Diseño populares](#conoce-sistemas-de-diseño-populares)
  - [Instalación y flujos de trabajo](#instalación-y-flujos-de-trabajo)
    - [Bonus: Personalizando la Terminal](#bonus-personalizando-la-terminal)
    - [Instalación y flujos de trabajo](#instalación-y-flujos-de-trabajo-1)
    - [Instalación de Node / Express desde 0](#instalación-de-node--express-desde-0)
    - [Bonus: html, css, js](#bonus-html-css-js)
  - [Automatización](#automatización)
    - [Automatización (Pre procesadores)](#automatización-pre-procesadores)
      - [¿Qué es gulp?](#qué-es-gulp)
      - [¿Qué es SCSS?](#qué-es-scss)
    - [Continuando con la automatización](#continuando-con-la-automatización)
  - [Paradigmas](#paradigmas)
    - [SMACSS: Arquitectura de CSS escalable y modular](#smacss-arquitectura-de-css-escalable-y-modular)
    - [OCSS: Orientación de objetos en CSS](#ocss-orientación-de-objetos-en-css)
    - [BEM](#bem)
    - [Bonus: Bootstrap](#bonus-bootstrap)
  - [Naming](#naming)
    - [Naming](#naming-1)
  - [Qué son los tokens](#qué-son-los-tokens)
    - [¿Qué son los tokens?](#qué-son-los-tokens-1)
  - [Espaciado](#espaciado)
    - [Espaciado](#espaciado-1)
  - [Grillas](#grillas)
    - [Grillas](#grillas-1)
    - [Bonus: Animando en CSS](#bonus-animando-en-css)
  - [Mi primer componente](#mi-primer-componente)
    - [Mi primer componente](#mi-primer-componente-1)
  - [Documentación](#documentación)
    - [Documentación](#documentación-1)
    - [Testing](#testing)
    - [Testing](#testing-1)
    - [Bonus: Debug en el navegador](#bonus-debug-en-el-navegador)
  - [Deploy y versionamiento](#deploy-y-versionamiento)
    - [Cómo empezar en Github](#cómo-empezar-en-github)
    - [Deploy y versionamiento](#deploy-y-versionamiento-1)
  - [Design review](#design-review)
    - [Design review](#design-review-1)
    - [Cierre](#cierre)

## Introducción

### Introducción y presentación

¡Bienvenido al curso de Sistemas de Diseño!

En este curso aprenderás a crear sistemas de diseño desde cero así como todas las herramientas que tienes para dialogar y trabajar junto con otros equipos a la hora de crear o iterar productos de software.

Nuestro profesor Rulótico González es un diseñador interactivo, en otras palabras, se especializa en diseñar las interfaces del futuro. Además, es diseñador y programador al mismo tiempo. Como diseñador y programador transitó en el diálogo y los conflictos entre estas profesiones, fue así como encontró los sistemas de diseño, creando mejores procesos y estructuras para dialogar.

- [Airbnb Design – A behind-the-scenes look at our design culture, process, learnings, and storytelling. Inspired by work, travel, and the creatives we serendipitously meet along the way](https://airbnb.design/designing-for-crisis/)

### Conoce Sistemas de Diseño populares

Conocer otros sistemas de diseño te permite tener referencias a la hora de pensar cómo empezar el tuyo. Muchos están documentados y puedes ver sus aprendizajes paso a paso en el proceso de construirlo.

El sistema de diseño se basa en ayudar de manera estandarizada y óptima los procesos de creación de funcionalidades, flujos y componentes del producto.

Es por eso que podemos definir diferentes puntos a tener en cuenta ahora que construyamos nuestro sistema de diseño:

  - **Flujo del equipo**
  - **Sistema de versionamiento y alta de documentos y pantallas**
  - **Documentación**
  - **Construcción y distribución**
  - **Revisión y deploy**

Como haremos la revisión de los archivos de construcción y mantendremos sano nuestro sistema, o las conexiones a nuestro sistema.

Además te permite vislumbrar todo lo que vamos a construir a lo largo de este curso, y determinar qué aspectos de tu Sistema de Diseño son necesarios o prescindibles.

> Un sistema de diseño busca sobre todo **mejorar el flujo de trabajo de equipo** permitiéndole aprender e iterar mucho más rápido y eficiente.

## Instalación y flujos de trabajo

### Bonus: Personalizando la Terminal

- [iTerm2](https://iterm2.com)
- [oh my zsh](https://ohmyz.sh)

### Instalación y flujos de trabajo

El Sistema de Diseño es como una “API del diseño”, que te servirá para comunicar tu sistema a nivel código.

Estos son los pasos que tendremos en cuenta:

Empezaremos por crear una URL que centralice los elementos principales de tu Sistema de Diseño.
Instalaremos Node y Express para poder construir tu web de manera muy visual rápidamente.

- [Express Infraestructura web rápida, minimalista y flexible para Node.js](https://expressjs.com/es/)
- [nodejs](https://nodejs.org/es/)

  - Instalar Node desde la pagina
  - Instalar Express con `npm install express-generator -g`
  - Abrir Bash en la carpeta del proyecto
  - Crear la base del proyecto con `express --view=pug Platzi_DeditoSudado`
  - Entrar a la carpeta del proyecto desde Bash
  - `npm install` para que nos permita instalar herramientas chidas
  - Escribir `npm start`
  - En el navegador escribir `localhost:3000`
  - Cerrar con ctrl+c
  - Para abrir el proyecto con VSC es code .

- [Express application generator](https://expressjs.com/en/starter/generator.html)

### Instalación de Node / Express desde 0

Para instalar NODE necesitaremos:

  - Muchas ganas
  - Pocas muecas
  - Tus manitas
  - Entrar al siguiente link → https://nodejs.org/en/download/

Ahí hay mucha información pero a ti lo único que te va importar son estos botones:

![](https://i.ibb.co/XW2Gsnk/node.jpg)

Elige dependiendo del sistema operativo que uses y con eso comenzará la descarga:

![](https://i.ibb.co/brvm2t9/node1.jpg)

Cuando abras ese archivo te informará que instalará dos cosas: Node y npm:

![](https://i.ibb.co/QvPg5N8/node2.jpg)

Ahora para probar que se haya instalado ingresa a la terminal y coloca estos comandos:

  - `node --version`
  - `npm --version`

Nos responderá con las respectivas versiones y sabremos que ya está instalado n_n

A veces la primera vez no es tan simple, y puede que la respuesta que obtengas no sea tan feliz, te cuento un par de errores posibles para que tengas en cuenta:

- Para que Node se instale bien, tienes que instalarlo estando en la carpeta correcta. Verifica que estás en la que tiene “package.json” antes de ejecutar el comando npm install. - Si aún no sabes cómo moverte entre carpetas en la terminal, es un gran momento para revisar el curso de Introducción a la Terminal y Línea de Comandos
- Si ya tienes node pero no está actualizado, puede que te salgan errores extraños. Ejecuta primero npm install y luego npm start, así se actualiza antes.
- Si estás en iOS o Mac, es probable que necesites ejecutar el comando sudo npm install , que te pedirá tu clave de administrador y luego te permitirá instalarlo sin problemas.
- Si te sale algún otro error loco que no logras solucionar, tienes algunas alternativas:
Avísanos respondiendo a este tutorial, alguien de la comunidad puede ayudarte
- **No temas:** miles de personas sufrieron miles de errores instalando Node antes que tú. Algunos de ellos aprendieron en el camino y devuelven su amor en forma de tutoriales o discusiones en Stackoverflow o las profundidades de la internet. Sumérgete en sus respuestas googleando el tipo de error que te sale, seguramente serás capaz de resolverlo muy pronto.

### Bonus: html, css, js

**`Pug`** nos permite utilizar una sintaxis un poco diferente al HTML común y corriente, pero es más amigable, en vez de encerrar las etiquetas dentro de otras etiquetas podemos simplemente tabular (dejar espacios) y automáticamente nuestro html funcionara a la perfección, también podemos utilizar las funciones extends y block para definir layouts o templates que podemos modificar cuando necesitemos:

```pug
html
	head
		link(rel="stylesheet" href="...") // los atributos van entre ()
		// al tabular obtenemos un resultado másomenos así:
		// <html>
		// 		<head>
		// 		 <link ...etc />
		// 		</head>
		// </html>
	body
		block content // cuando utilicemos este template podemos definr el contenido de aquí :o
```

- [Prepros](https://prepros.io)

- [Proyecto | GitHub | Platzi_DS](https://github.com/rulotico/Platzi_DS)

## Automatización

### Automatización (Pre procesadores)

- Instalamos `gulp-cli` mediante `npm install --global gulp-cli` de manera global.
- Instalamos gulp mediante `npm install --save-dev gulp` guardándola en el entrono de desarrollo

Dentro de nuestro proyecto vamos a instalar otras dos dependencias `npm install gulp` y `npm install scss`

#### ¿Qué es gulp?

Gulp es una herramienta para poder automatizar procesos por medio de pipelines, o sea flujos , digamos que le decimos primero haz esto y luego haz esto con tan solo un comando, justo lo que necesitamos.

#### ¿Qué es SCSS?

Como CSS requiere de muchos caracteres pues SCSS lo hace más fácil donde utilizamos el poder de la programación para definir variables y construir de manera modular CSS, esto nos mantiene óptimos y sobre todo podemos asegurar la consistencia de nuestro sistema. Comenzamos a instalar las funciones que necesitas para potenciar tu SCSS y terminaremos de hacerlo en la siguiente clase.

### Continuando con la automatización

Continuamos la instalación de las funciones que necesitamos de gulp, y una vez instalados ahora vamos crear los siguientes archivos y funciones:

  > Dentro de la carpeta de SCSS crearemos una estructura atómica

- Fundations
- Atomos
- Moléculas
- Organismos
- Páginas
- Templates

  > En gulp vamos a crear las siguientes funciones:

- Compilador de SCSS a main.css

Instalar minify-css

```bash
sudo npm install gulp-minify-css
```

  - Ejecutar minify
  
  ```bash
  gulp style_main
  ```

- Instalar gulp contac

```bash
sudo npm install gulp-concat
```

  - Ejecutar watch

  ```bash
  gulp watch
  ```

## Paradigmas

### SMACSS: Arquitectura de CSS escalable y modular

Existen diferentes paradigmas y vamos a revisar algunos de ellos en las próximas clases para definir el mejor para nuestro sistema pues depende mucho de las necesidades de cada proyecto.

En esta clase analizaremos el paradigma SMACSS o Scalable and Modular Architecture for CSS (Arquitectura en CSS Escalable y Modular).

SMACSS se trata de una manera de construcción para los estilos de tu sistema. Es un paradigma basado en las siguientes categorías, que analizaremos en profundidad en esta clase:

  - Base
  - Layout
  - Module
  - State
  - Theme

  ![](https://i.ibb.co/1r0xJxL/smacss.jpg)

Scalable and Modular Architecture for CSS. ¿En qué se basa este paradigma?

  - **`base:`** toma las etiquetas primordiales de html
  - **`layout:`** las etiquetas que segmentan la página
  - **`module:`** es más específico e interioriza en el layout
  - **`state:`** muestra el estado de un elemento
  - **`theme:`** aquí creamos archivos específicos por tema

Recuerda que tú vas a definir las reglas que mejor se adapten a tu producto y que hagan que mejore el flujo de trabajo.

- [SUIT CSS](http://suitcss.github.io)
- [Methods to Organize CSS](https://css-tricks.com/methods-organize-css/)
- [Clean-css](https://github.com/jakubpawlowicz/clean-css)

### OCSS: Orientación de objetos en CSS

OCSS o Object-Oriented CSS (Orientación de objetos en CSS).

Este se trata de un paradigma basado en la creación de objetos, que son básicamente lo que también se llama modulo o componente en otros paradigmas.

Este paradigma puede no incluir la estructura base del html Aprende a construir tu librería OCSS en esta clase.

- [OOCSS - The Future of Writing CSS](https://www.keycdn.com/blog/oocss)

### BEM

BEM es un paradigma que anticipa modificadores de un componente.
En esta metodología categorizamos o dividimos las clases de la siguiente manera:

Block (Bloque)
Los bloques consideran contenedores de los componentes que nos sirven para englobarlos tipo objetos.

Elements (Elementos)
Los elementos que van dentro de estos contenedores

Modifiers (modificadores)
Son clases de lo más geniales, nos permiten modificar el comportamiento o estilo de un componente.

- [How to organize your CSS with OOCSS, BEM & SMACSS](https://intelygenz.medium.com/how-to-organize-your-css-with-oocss-bem-smacss-a2317fa083a7)

### Bonus: Bootstrap

- [Bootstrap](https://getbootstrap.com)

![](https://i.ibb.co/PFJN9GJ/tech.png)

## Naming

### Naming

**Modificadores**
Son clases que modifican el comportamiento o clase de un elemento.

**Utilidades**
Son clases que nos ayudan a generar ciertas propiedades de uso general.

Naming genera una regla de cómo definir nuevas clases. Debes tener muy en claro cuál será la regla que utilizarás para evitar confusiones y pérdida de tiempo.

BEM va de lo general a lo particular: .house , .house_window

Recomendación: NUNCA utilices nombres en español. Puedes meter la “ñ” y esto no es reconocido por SCSS.

- [Lightning Design System](https://www.lightningdesignsystem.com)
- [Website Style Guide Resources](http://styleguides.io)

## Qué son los tokens

### ¿Qué son los tokens?
Nuestro objetivo es sistematizar nuestros procesos entonces nuestro sistema tiene que ser un ente configurable. En este sentido, los tokens son configuraciones que afectan a todo nuestro sistema tales como:

Colores
Tipografía
Reglas de espaciado
Brakepoints
Definiremos nuestros colores basándonos en algún paradigma o en los guidelines y UI kit del producto, para definir estas variables es importante que si trabajamos con un diseñador, este también este presente y pueda verificar la viabilidad de lo que estamos haciendo.

Vamos a crear las reglas necesarias para fundamentar nuestro sistema de columnas y podremos hacer otras extras que nos permitan generar un nuevo sistema de interacción mobile. Para esto crearemos un archivo llamado `brakepoints.scss`

## Espaciado
### Espaciado

Ya que tenemos elementos dentro de nuestro sistema, ahora tenemos que poner a prueba nuestros tokens de espaciado para ello crearemos un organismo para ver cuál es el efecto de nuestras reglas cuando los átomos conviven en un ecosistema de elementos.

El organismo más común de toda plataforma es el formulario que nos ayuda a recopilar información del usuario. Para esto tomaremos elementos como:

  - Label
  - Input
  - Alert
  - Btn
  - Modals

## Grillas

### Grillas

Llegó el momento que nos pongamos rudos y definamos cómo se va a comportar nuestro sistema. Para esto necesitamos crear un sistema de columnas.

Antes de hacerlo vamos a cuestionar si usaremos un layout al que tengamos que seguir, pues esto es bastante importante para la reglamentación de nuestro grid.

Utilizaremos el sistema de doce columnas como lo hace Bootstrap, basados en un layout.
Una vez definido tenemos cómo funcionan nuestras columnas, el departamento de diseño tienen que estimar cómo es que sus componentes se van a comportar y para ello este sistema les ayudara cuando estén diseñando.

Una parte importante es que el documento de diseño como programación, siga las mismas reglas.

Dentro de nuestro wrapper, donde definiremos el contenido construiremos los grid, podemos basarnos en librerías de grids que ya existen en internet, solo tenemos que modificar los estilos para que tengan sentido dentro de nuestro sistema.

Hay tres cosas importantes qué definir dentro del grid de nuestro sistema:


  1. Nomenclatura de columnas
  2. Nomenclatura de los brakepoints
  3. Obtener los tokens de nuestro sistema para esta definición.

- [Una cuadricula simple adaptable a diferentes pantallas, mejorada con Sass](https://webdesign.tutsplus.com/es/tutorials/a-simple-responsive-grid-made-even-better-with-sass--cms-21540)
- [Normalize.css](https://necolas.github.io/normalize.css/)

### Bonus: Animando en CSS



- [Animate.css](https://animate.style)

## Mi primer componente

### Mi primer componente

Estamos listos para construir elementos y para que otros puedan construir nuevos componentes respetando el sistema de diseño. Para definir un componente necesitarás tener previamente definidos:

- Tokens
- Naming
- Modificadores o Utilities


Al construir el componente en cuestión, seguimos las buenas prácticas que venimos aprendiendo. Es importante que tengas documentado el proceso en tu librería y un espacio para definir nuevos componentes.

[7 Tools for Building Your Design System in 2021](https://blog.bitsrc.io/7-tools-for-building-your-design-system-in-2020-452d9c9b3b8e)

## Documentación

### Documentación

Hay que tener en cuenta que somos parte de un proceso, un proceso que empieza desde la idea de resolver un problema, se crea una herramienta y se le da al usuario. Es súper importante documentar cada elemento del sistema para que el siguiente en la construcción de esta gran fabrica de elementos le pueda ser más fácil y eficiente la construcción. También te permite anticiparte a los momentos que puede tener el que se dedique a conectar este componente y brindarle las herramientas necesarias es nuestro trabajo. Algunos puntos importantes que tienes que definir en tu documentación dentro del sistema ## Titulo El nombre del componente que viene desde el diseño del componente ## Descripción La descripción de por qué estamos haciendo este componente y que resuelve ## Implementación Descripción sobre cómo puedes implementar este componente en tu proyecto ## Estados Estados que tiene con los modificadores o utilidades y si pudiera no funcionar en otros contextos o reglas que no se hayan definido. ## Bitacora Donde defines que cambios a tenido el componente durante la vida del sistema

## Testing

### Testing

Es muy importante definir la manera en que calificarás el éxito, cómo tendremos la capacidad de evaluar lo que diseñamos y construimos vs el usuario.

Para eso crearemos indicadores dentro del sistema que nos permitan tener esa respuesta y demuestre ante el equipo las desiciones que tomamos.

  - Evaluemos el código vs Diseño
  - Evaluemos el comportamiento
  - Evaluemos el mobile

Para hacer estas pruebas yo recomiendo que lo puedas tener dentro de una plataforma tipo KANBAN Al final del día tu puedes definir tu lista de Testing, ésta ve de forma general la evaluación de un componente pero en tu proyecto dependiendo del producto que estas desarrollando tal vez requiera más o menos.

**Lo que no se mide no se puede mejorar.**

Por eso es importante establecer qué metas o milestones tiene que cumplir el proyecto.

**Debes hacer pruebas de:**

- **Comportamiento:** esto es algo que se llega a partir de la transición del diseño a la programación.
- **Mobile** version: Mobile first siempre es el camino que debería tomar un diseñador al crear una pantalla.
- **Bitácora:** Nos dice porqué tomamos ciertas decisiones y porqué no.
- **Redifinir:** ¿Lo que estamos haciendo tiene sentido? ¿Le está sirviendo al usuario?

El tramo del trabajo de un design system puede ser largo pero hará que se tenga una efectividad del 100% y más.

### Bonus: Debug en el navegador

El inspector de elementos es una herramienta muy completa

## Deploy y versionamiento

### Cómo empezar en Github

<h3>Creamos un proyecto en GitHub</h3>

Ya creada tu cuenta dentro de Github, vamos a utilizar el ícono de “+” que está en el top navbar (barra superior) de la plataforma justo a un lado de tu foto.

![](https://i.ibb.co/dWpLPrJ/git.jpg)

Si te das cuenta bajo tu cuenta se generará un path, o sea una / para que viva ahi tu proyecto con una url, ponle como quieras.

![](https://i.ibb.co/JdJfkwq/git1.jpg)

Te cuento un poco qué pasa en esta pantalla:

<h3>Nombre y descripción</h3>

En esta sección escribiremos el nombre de nuestro proyecto y su descripción, trata que sea claro el nombre.

<h3>Público o privado</h3>

Esto es una decisión que debes de tomar, depende de que sea el proyecto , tal vez no quieres que nadie lo vea.

![](https://i.ibb.co/zR1VHQ6/gi2.jpg)

<h3>Readme y licencia</h3>

En esta sección hacemos varias cosas configurables por nuestro proyectos, el primero que es README nos permite hacer un doc dentro de nuestro proyecto con el cual vamos a dejar descripción y a veces hasta documentación.

El siguiente que es .gitignore, básicamente le decimos a GitHub que hay cosas que tendría que ignorar de nuestro proyecto para no estar subiendo todo lo que ponemos en el, esto sucede generalmente cuando usamos algún instalador de librerías como npm que justo nuestro proyecto utiliza, escogeremos Node y ya sabe que archivos ignorar.

Por último están las licencias, yo suelo usar la de MIT, pero te recomiendo leer el link que viene en el iconito de i para saber más sobre otras opciones.

![](https://i.ibb.co/R35DwZK/git3.jpg)

Ahora que ya tenemos creado nuestro proyecto vamos a seguir los siguiente pasos:

  - Vamos a presionar el botón verde llamado “clone”. Esto para que nos de una url que vamos a usar dentro de iterm, espero ya super pimpeada.

![](https://i.ibb.co/Vqmfhb1/git4.jpg)

Dentro de iterm vamos a copiar esa url, les advierto que necesitamos que ya tengan instalado GitHub y su cuenta config, de no ser así les va a pedir un mail y su contraseña, de su cuenta de Github.

Antes de correr la función que clona nuestro proyecto, asegúrate de estar en la carpeta donde guardarás tu sistema de diseño.

![](https://i.ibb.co/3zLFwx6/term.jpg)

Ahora si es hora de clonar:

![](https://i.ibb.co/wcVzbM5/term1.jpg)

Cuando clonen su proyecto ahora tendrán un proyecto conectado a GitHub, les recomienden tomen el curso de GitHub de Platzi para entender mejor este proceso. Recuerden entrar en la carpeta de su proyecto:

![](https://i.ibb.co/fNq9jj9/term2.jpg)

Ya que estamos en nuestra carpeta es aquí donde podemos instalar nuestro proyecto de express, les recomiendo den un paso atrás antes de correr el comando de express.

![](https://i.ibb.co/w74H7Zk/term3.jpg)

Justo así.

Ahora vamos crear un proyecto de express, si se dan cuenta justo lo voy a hacer sobre la carpeta que ya tenia creada con lo cual me va a preguntar si estoy seguro ya que la carpeta no está vacía.

![](https://i.ibb.co/xFpn528/term4.jpg)

Ves te dije, no tengas miedo, dile YES, presionando la “y” de tu teclado y “enter”.

Se ha creado el proyecto, regresemos dentro de la carpeta.

![](https://i.ibb.co/R0JsTbj/term5.jpg)

Y ahora veremos que esta todas las carpetas de express.

![](https://i.ibb.co/JxbcrZm/term6.jpg)

Para subir los cambios, ahora tienes que hacer tres comandos:

  - git add .
  - git commit -m “Mi actualización”
  - git push origin master

![](https://i.ibb.co/RT0vGyJ/term7.jpg)

Esto nos va a servir cuando hagamos deploy en Heroku, pero no se preocupen nos vemos en las siguientes clases y recuerden mas vale componente en mano que cientos volando.

### Deploy y versionamiento

Nuestro sistema también tienen niveles de producción y hasta ahora hemos trabajo en test, es momento de crear un pipeline de producción para que sea publico a todo mundo y se pueda utilizar de manera frecuente.

Vamos a utilizar Heroku para desarrollar este pipeline y también aprenderemos a hacer una bitácora de actualizaciones del sistema pues es importante informar al equipo del cambio.

Para ello vamos a definir en nuestro sistema una nueva ruta en la cual vamos a ir poniendo cuales son las nuevas actualizaciones, recuerda que el sistema servirá para que más equipo puedan construir es por ello que tratas de ser sumemente claro.

La función `/Whats_new` Nos ayudará a que la gente pueda ver las actualizaciones.

Consejos:

  - Trata de ser conciso.
  - informa de las clases que tuvieron algún cambio y conflictos que tu visualizas que pudiera haber.
  - Incluye hyperlinks.

- [HEROKU](https://www.heroku.com)

## Design review

### Design review

Los más importante del sistema es que todos los equipos que participan en la creación de software estén alineados.
Es por esto que también tienes que evaluar cuales son los puntos buenos o malos de tu sistema y saber si necesitas una reestructura o mejorar ciertos procesos, siempre es bueno tener en mente hacia a donde vas y que quieres lograr con el sistema, pues sin un objetivo claro todos estaremos trabajando sin un objetivo común.

Algunos puntos muy importante para cuidar el trabajo en equipo son:

  - Ten juntas semanales donde hables del sistema.
  - Pregunta a otros departamentos si les facilita la construcción del producto.
  - De no ser así media que cosas puedes hacer.
  - No generes deuda técnica, los cambios y parches rápidos al final del día te vendrán a tirar el sistema.
  - Ten un roadmap del sistema. Siempre trata de ser sistemático y trabaja para los demás. Todo el equipo te lo agradecerá.
  - Siempre asegura que lo que imaginas se diseñe y que lo que diseñas se construya.
  - Hay que tener la menos de “Deuda” posible.

Los procesos deben de estar definidos, si no están definidos caes en un caos y desastre.

- Tú puedes hacer tus propios procesos.

- Mide el nivel de éxito del design system semanalmente. Comprueba que lo que hiciste funciona.

- Lo importante es analizar qué estás haciendo y por qué lo estás haciendo.

- Deuda : Cuando alguien como el CEO, el Marketing, etc te pide que hagas cambios grandes y rápidos. Sucede entonces que no puedes hacer toda la documentación requerida y va a llevar problemas a todas las partes del equipo. Por cada cambio que hagas rápido vas a tener 10 problemas más 👎🏻. Por eso tienes que ser muy estricto y muy duro en seguir el proceso.

El objetivo es la construcción.

Así es el diseño es más que interfaces bonitas, son los procesos de creación del software. Añadiendo un poco más , a algunos desarrolladores nos gusta más el diseño de la estructura no siempre porque creamos aplicaciones web, sino porque debemos de pensar bien en los procesos de negocio y como resolvemos utilizando nuestra ingeniería. Todo lo relacionado a dev ops, como manejas contenedores, usando shell para llamar a scripts, proveer al servidor de manera constante , etc es una gran abstracción y una de las metas finales del diseño.

### Cierre

Ya tienes todos los elementos para crear, estructurar e implementar tus sistemas de diseño desde cero. Aprende a utilizarlo como herramienta de diálogo para trabajar con otros equipos y fundamentar tus perspectivas desde otro lugar en la mesa de negociación.

