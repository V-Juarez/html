<h1>Postman</h1>    

<h3>Eduardo Álvarez</h3>

<h1>Tabla de Contenido</h1>

- [1. Introducción y repaso de API](#1-introducción-y-repaso-de-api)
  - [Introducción al curso](#introducción-al-curso)
  - [Estudiando el protocolo HTTP, verbos y status](#estudiando-el-protocolo-http-verbos-y-status)
  - [Estructuras de las URLs](#estructuras-de-las-urls)
- [2. Po](#2-po)
  - [Instalación de Postman](#instalación-de-postman)
  - [Cómo ejecutar la API](#cómo-ejecutar-la-api)
  - [Llamados a un API con GET: llamado de listas y detalles de objetos](#llamados-a-un-api-con-get-llamado-de-listas-y-detalles-de-objetos)
  - [Llamados a un API con GET: parámetros en la URL](#llamados-a-un-api-con-get-parámetros-en-la-url)
  - [Llamados a un API con el método post utilizando JSON](#llamados-a-un-api-con-el-método-post-utilizando-json)
  - [Llamados a un API con el método post utilizando Form Data](#llamados-a-un-api-con-el-método-post-utilizando-form-data)
  - [Llamados a un API con el método PUT](#llamados-a-un-api-con-el-método-put)
  - [Llamados a un API con el método DELETE](#llamados-a-un-api-con-el-método-delete)
  - [Optimización de environment de postman y configuración de la colección](#optimización-de-environment-de-postman-y-configuración-de-la-colección)
  - [Agregar ejemplos de responses y descripción de endpoints](#agregar-ejemplos-de-responses-y-descripción-de-endpoints)
- [3. Automatización de procesos con JavaScript](#3-automatización-de-procesos-con-javascript)
  - [Guardar el token del login con una prueba automática](#guardar-el-token-del-login-con-una-prueba-automática)
  - [Creación de Pruebas para endpoints](#creación-de-pruebas-para-endpoints)
- [4. Puesta en producción](#4-puesta-en-producción)
  - [Publicar Documentación](#publicar-documentación)
  - [Cierre del curso](#cierre-del-curso)

# 1. Introducción y repaso de API

## Introducción al curso

Este curso sera una introducción al uso de postman y las implicaciones para el protocolo http mediante la implementación REST como es conocido el conjunto de principios de diseño que permite a HTTP abrazar su máxima potencia mediante la creación de interfaces, que pueden utilizarse desde casi cualquier dispositivo o sistema operativo, en pocas palabras REST es una forma sencilla de organizar interacciones entre sistemas independientes.

La alternativa es la construcción de convenciones relativamente complejas por encima de HTTP. A menudo, esto toma la forma de nuevos enteros lenguajes basados en XML. El ejemplo más ilustre es SOAP. Tienes que aprender un conjunto completamente nuevo de convenciones, pero nunca usas HTTP a su máxima potencia.

- [GitHub - platzi/postman-course](https://github.com/platzi/postman-course)

## Estudiando el protocolo HTTP, verbos y status

Un protocolo especifica reglas en la comunicacion entre dos entes, en este caso entre dos computudoras.

HTTP (Hyper Text Transfer Protocol) fue creado especificamente para la web.

Una de las cosas que especifica el protocolo HTTP son los verbos:

- **GET**: solicitar datos o algun recurso.
- **HEAD**: traer headers (como una peticion GET pero sin contenidos). Es util cuando vamos a utilizar APIs, para comprobar si lo que vamos a enviar esta correcto y puede ser procesado.
- **POST**: enviar datos a un recurso para la creación.
- **PUT**: reemplazar por completo un recurso.
- **PATCH**: reemplazar parcialmente un recurso.
- **DELETE**: eliminar un recurso.

Otra de las cosas que especifica el protocolo HTTP son los codigo de estado (status codes). Sirven para describir el estado de la peticion hecha al servidor.

- **1xx**: Indican que la peticion fue recibida y el servidor sigue trabajando en el proceso, es decir, no fue exitosa ni fue errónea, sino que esta siendo procesada aun.
- **2xx**: Indican que la peticion fue recibida y procesada correctamente.
- **3xx**: Indican que hay que tomar acciones adicionales para completar la solicitud. Por lo general estos codigos indican redireccion. Generalmente en los APIs no se usan redirecciones porque no contienen estados, es decir, toda la informacion esta contenida en una solicitud, no se guarda un estado en el servidor con una sesion por ejemplo.
- **4xx**: Indican errores del lado del cliente, por ejemplo: se hizo mal la solicitud, faltan datos, headers o cualquier otro error que pueda ocurrir.
- **5xx**: Indican errores del servidor. Suelen aparecer cuando existe un fallo en la ejecución en el servidor.

**Los codigos mas comunes a la hora de interactuar con un API son:**

- **200**: Todo esta OK.
- **201**: Todo OK cuando se hizo una solicitud **POST**, el recurso se creo y se guardo correctamente.
- **204**: Indica que la solicitud se completo correctamente pero no devolvio informacion. Es muy comun cuando se hacen peticiones con el verbo **DELETE**.
- **400**: Bad Request, algo esta mal en la peticion. Se nos olvido enviar un dato o algo relacionado. Por lo general la respuesta nos especifica cuales fueron los errores a la hora de hacer la peticion.
- **401**: Unauthorized, es decir, no estamos autorizados (autenticados) a realizar la peticion.
- **403**: Forbidden, yo no tengo acceso a ese recurso aunque este autenticado.
- **404**: Not Found, no existe el recurso que se esta intentando acceder.
- **500**: Interna Server Error, es un error que retorna el servidor cuando la solicitud no pudo ser procesada. Por lo general, si no tenemos acceso al backend, no tenemos control sobre los errores 500 que retorna un API.

![img](https://res.cloudinary.com/dynamic-sourcing-llc/image/upload/f_auto,q_auto,dpr_auto/v1559554843/infografia_c%C3%B3digos-estado-http_v6tgrl.png)

![img](https://1.bp.blogspot.com/-l4ENbjEoXDw/XD9PPNWIxmI/AAAAAAAAV5M/uVEboPRHjjEKvQ4KOHWpOiGwduqGVNFtACLcBGAs/s1600/statuscode.png)

**Mas errores de cliente**

1. [414 URI Too Long](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   La URI solicitada por el cliente es más larga que el servidor está dispuesto a interpretar.
2. [415 Unsupported Media Type](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   El formato multimedia de los datos solicitados no está soportada por el servidor, por lo cual el servidor rechaza la solicitud.
3. [416 Requested Range Not Satisfiable](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   El rango especificado por el campo de encabezado Range en la solicitud no cumple; es posible que el rango está fuera del tamaño de los datos objetivo del URI.
4. [417 Expectation Failed](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   Significa que la expectativa indicada por el campo de encabezado Expect solicitada no puede ser cumplida por el servidor.
5. [418 I’m a teapot](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   El servidor se reúsa a intentar hacer café con una tetera.
6. [421 Misdirected Request](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   La petición fue dirigida a un servidor que no es capaz de producir una respuesta. Esto puede ser enviado por un servidor que no esta configurado para producir respuestas por la combinación del esquema y la autoridad que estan incluidos en la URI solicitada
7. [422 Unprocessable Entity (WebDAV)](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   La petición estaba bien formada pero no se pudo seguir debido a errores de semántica.
8. [423 Locked (WebDAV)](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   El recurso que está siendo accedido está bloqueado.
9. [424 Failed Dependency (WebDAV)](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
   La petición falló debido a una falla de una petición previa.
10. [426 Upgrade Required](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
    El servidor se reúsa a aplicar la solicitud usando el protocolo actual pero puede estar dispuesto a hacerlo después que el cliente se actualize a un protocolo diferente. El servidor envía un encabezado Upgrade en una respuesta para indicar los protocolos requeridos.
11. [428 Precondition Required](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
    El servidor origen requiere que la solicitud sea condicional. Tiene la intención de prevenir problemas de ‘actualización perdida’, donde un cliente OBTIENE un estado del recurso, lo modifica, y lo PONE devuelta al servidor, cuando mientras un tercero ha modificado el estado del servidor, llevando a un conflicto.
12. [429 Too Many Requests](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
    El usuario ha enviado demasiadas solicitudes en un periodo de tiempo dado.
13. [431 Request Header Fields Too Large](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
    El servidor no está dispuesto a procesar la solicitud porque los campos de encabezado son demasiado largos. La solicitud PUEDE volver a subirse después de reducir el tamaño de los campos de encabezado solicitados.
14. [451 Unavailable For Legal Reasons](https://developer.mozilla.org/es/docs/Web/HTTP/Status)
    El usuario solicita un recurso ilegal, como alguna página web censurada por algún gobierno.

[códigos http](https://http.cat/)

## Estructuras de las URLs

En un API es importante tener bien estructuradas las rutas por las cuales se usarán cada uno de los endpoints que contiene. Antes de entrar de lleno a explicar el API con el que trabajaremos en este curso veamos unos conceptos muy importantes a la hora de trabajar con APIs.

### Recurso

Es la instancia o la representación de un objeto o la representación de algo, tiene datos y operaciones asociadas a él. Por ejemplo: `course`, `material` y `video` son recursos que tenemos disponibles en el API con la que trabajaremos y podemos realizar operaciones sobre ellos: crear, actualizar y eliminar.

### Colecciones

Es un conjunto de recursos, por ejemplo: `courses` es una colección de `course.`

### URL

(Uniform Resource Locator) es la ruta en la cual puede ser ubicado un recurso y ejecutar las operaciones sobre él.

### CRUD

Siglas que hacen referencia a las operaciones básicas que se pueden ejecutar sobre un recurso:

- C: Create (crear)
- R: Read (leer)
- U: Update (actualizar)
- D: Delete (eliminar)

### Endpoints

Es el punto final de la comunicación con un ente, en este caso, un endpoint está asociado a una URL y a las operaciones que podemos ejecutar. Este término es muy utilizado en las APIs.

Los endpoint definen operaciones que se quieren ejecutar sobre un recurso. Por ejemplo: si queremos un conjunto de operaciones CRUD sobre Cursos podríamos crear los siguientes endpoints:

- `/get-all-courses` : para obtener una colección de Cursos.
- `/add-new-course`: para crear un nuevo recurso de Cursos.
- `/delete-all-courses`: para eliminar todos los Cursos.

Y así sucesivamente. Pero, esto implicaría un problema. El API puede llenarse de endpoints que ejecutan una sola operación, esto no es escalable, significa que si por ejemplo el recurso Cursos pasa a llamarse Clases habría que actualizar absolutamente todas las URLs y asegurarse de ello puede convertirse en un dolor de cabeza.

Entonces, ¿cuál es la buena práctica en este caso?

Como lo vimos en la clase pasada, el protocolo HTTP especifica una serie de verbos que indican acciones. Lo ideal es que la operación que se ejecute sobre un recurso se obtenga a través del verbo HTTP de la petición y no que esté definido en el endpoint. Por ejemplo:

- ```
  /courses
  ```

  : Dependiendo del verbo HTTP se ejecutará una operación en particular. Quedaría así:

  - GET `/courses`: trae la colección de Cursos.
  - POST `/courses`: crea un nuevo recurso de Cursos.
  - DELETE `/courses`: elimina todos los cursos.

De esta manera queda mucho más organizado un API. Pero, qué pasa si queremos traer no una colección de cursos como en los casos anteriores, sino un recurso en específico.

Por lo general cada recurso tiene un identificador único, un ID, es con esto que llamaremos a un endpoint para que nos retorne la información del recurso. Por ejemplo:

- GET `/courses/2/`: vemos que acá se le está pasando algo que en los endpoints anteriores no veíamos, es el número 2, ese es el identificador único, de esta manera el API sabe que tiene que buscar el curso con ID 2 y retornarlo.

Así sucesivamente con cada uno de los verbos, por ejemplo: casi nunca se hace una eliminación en masa en un API, como el ejemplo que tenemos más arriba donde se eliminan todos los cursos. Lo ideal es que se elimine un recurso individualmente y no una colección, igualmente pasa con la actualización.

### Recursos anidados

Hay veces en las que un recurso depende de otro recurso, por ejemplo, comentarios depende de materiales; usualmente en los APIs las anidaciones se hacen hasta dos niveles, es decir:

- `materials/1/comments`: estos son dos niveles
- `materials/1/comments/2/answers/`: son tres niveles, ahí lo ideal sería entonces separar el endpoint de comentarios y ejecutar `comments/2/answers/`

### Nuestro API

Ya he dado algunos spoilers sobre lo que nuestro API hace, es un clon de lo que Platzi es, una plataforma es donde tenemos Cursos, Materiales, Videos y Comentarios. El API es sencillo y es una prueba que utilizamos en este curso para explorar toda las capacidades que nos ofrece Postman para trabajar con ellos.

Una convención que se usa a la hora de documentar APIs es abstraer el endpoint de la URL del sitio al cual vamos a hacer la petición, puesto que esto al final es redundante de escribir, es decir, usualmente escribimos únicamente `/api-token-auth/` en vez de `[http://mistioweb.com/api-token-auth/](http://mistioweb.com/api-token-auth/)`.

#### Los endpoints que tenemos:

- `/api-token-auth/`
- `/courses`
- `/courses/:id/`
- `/courses/:id/upload_badge/`
- `/materials/`
- `/materials/:id/`
- `/materials/:id/comments/`
- `/comments/`
- `/comments/:id/`
- `/comments/:id/like/`
- `/comments/:id/dislike/`




# 2. Postman

## Instalación de Postman

Postman es multiplataforma, lo que implica que no importa el sistema operativo que uses Postman funcionará.

Es esta dirección https://www.getpostman.com/downloads/ puedes encontrar la versión de Postman más reciente y descargarla, por defecto, el sitio sabe desde qué sistema operativo estás accediendo y te muestra como primera opción, si no, más abajo aparecen los demás sistemas operativos que soporta Postman.

![Postman1.jpg](https://static.platzi.com/media/user_upload/Postman1-60f86a49-922d-4b4f-8959-7a5804105440.jpg)

### En windows

La instalación de Postman tiende a ser mucho más sencilla que la de una aplicación tradicional; no hay una serie de configuraciones que se deben aceptar o personalizar. Postman se instala en el sistema listo para utilizarse.

- Descargar Postman
- Abrir el archivo que se descargó, una vez abrá aparecerá una ventana así:

![Postman2 (1).jpg](https://static.platzi.com/media/user_upload/Postman2%20%281%29-9d5fba40-2de8-44b0-a87d-484239e03a67.jpg)

- Una vez instalado te pedirá que inicies sesión o si es el caso que crees una nueva cuenta.

![Postman4 (1).jpg](https://static.platzi.com/media/user_upload/Postman4%20%281%29-e75d7c77-af56-44e7-b11b-f78989c1c835.jpg)

- Y ya está postman listo para usarse.

![Postman5 (1).jpg](https://static.platzi.com/media/user_upload/Postman5%20%281%29-af8258e6-ba86-42d7-86ae-4a9b7b06b7a7.jpg)

### En MacOS

El proceso no es muy diferente a lo que es en Windows. Descargamos la App y luego la movemos a las aplicaciones de nuestro sistema y ya está lista para usarse.

Para instalar sobre Linux usnado la consola es asi:

> - Debian, Ubuntu y derivados:
>
> ```sh
> sudo apt install postman
> ```
>
> - Arh, Manjaro:
>
> ```sh
> sudo pacman -S postman
> ```
>
> - Fedora:
>
> ```sh
> sudo yam install postman
> ```

## Cómo ejecutar la API

Es una versión simple de una API desarrollada con Django y Django Rest Framework usando Docker.

### Cómo correr este proyecto

- Instala [Docker](https://platzi.com/clases/1432-docker/15423-instalacion-de-docker5237/) y [Docker Compose](https://platzi.com/clases/1432-docker/15439-docker-compose-la-herramienta-todo-en-uno/)
- Descarga los archivos de la api haciendo click en este [enlace](https://static.platzi.com/media/public/uploads/postman-course-master_ffa10d45-7eaf-4beb-b2bb-3ecb7c93eff2.zip). Estos archivos también se encuentran disponibles en la sección de archivos de la siguiente clase.
- Ejecuta en la terminal `sudo docker-compose up -d` para activar los contenedores de la aplicación.
- Entra en el contenedor ejecutando `sudo docker exec -it postman-course-master_web_1 bash`
- Ejecuta `cd ./project`
- Ejecuta migraciones de Django `python manage.py migrate`
- Dentro del contenedor ejecuta `source admin_info.sh` para crear al superusuario.
- Carga los datos iniciales con: `python manage.py loaddata courses/fixtures/initial_data.json`
- Ejecuta `exit` para salir del contenedor.
- Reinicia la aplicación con `sudo docker-compose stop` y nuevamente `sudo docker-compose up -d`.
- Comprueba que tu servidor se encuentre disponible entrando a la siguiente url `http://localhost:8000/api/`

### Cómo usarlo

Con el servidor de desarrollo corriendo puedes acceder al [Django Admin](http://localhost:8000/admin/), ahí puedes ejecutar tus acciones CRUD sobre tus datos.

## Llamados a un API con GET: llamado de listas y detalles de objetos

**Reto**
Con GET obtenemos los datos en la respuesta de la solicitud, con HEAD solo nos dice si realmente la información existe y la solicitud será correcta, no retorna información, solo el estado de la petición.

[API public](https://github.com/public-apis/public-apis)

```sh
# GET
# Courses
http://localhost:8000/api/courses

# Curso especifico :id
http://localhost:8000/api/courses/2

# Materials
http://localhost:8000/api/materials/1/
```



## Llamados a un API con GET: parámetros en la URL

Para enviar parámetros a tráves de la url se utiliza el caracter ? , en postman se puede configurar
algunos parámetros de forma gráfica y postman se encarga de general la url con los parámetros indicados, un de esto es:

| Parámetros | tipo de valor | Ejemplo de valor  | Descripción                                                  |
| ---------- | ------------- | ----------------- | ------------------------------------------------------------ |
| page_size  | Numerico      | 1                 | Se acota el tamaño de los resultados, a una sola página      |
| page       | Numerico      | 2                 | Muestra la página 2 de los resultados                        |
| ordering   | clave         | -ranking, ranking | -ranking ordena los datos de mayor a menor y ranking muestra los datos ordenados de mayor a menor. cave destacar que ranking es una clave del resultado |
| begin_date | fecha         | 2019-11-30        | Muestra los resultados en una fecha especifica               |

El link quedaría así

```sh
### //localhost: 8000/api/courses/?page_size=1&page=2&ordering=-ranking&begin_date=2016-11-23
```

al momento de realizar la consulta y el servidor nos devuelve una respuesta en json, postman añade una especie de cabecera

- count, es la cantidad de resultados.
- next y previous, un link hacia la páginas siguiente o anterior de páginas de resultado,
- results, muestra el resultado de la consulta

```json
    "count": 3,
    "next": null,
    "previous": null,
    "results":
```

Ejemplo para la siguiente url se muestra un resultado

```json
   ### //localhost:8000/api/courses/?page_size=1&page=2&ordering=-ranking&begin_date=2016-11-23
{
    "count": 3,
    "next": "localhost:8000/api/courses/?begin_date=2016-11-23&ordering=-ranking&page=3&page_size=1",
    "previous": "localhost:8000/api/courses/?begin_date=2016-11-23&ordering=-ranking&page_size=1",
    "results": [
        {
            "id": 2,
            "name": "Curso de Prework",
            "description": "Curso donde aprender a configurar tu entorno de desarrollo",
            "teachers": [
                {
                    "id": 2,
                    "name": "Eduard Alvarez",
                    "description": "Backend",
                    "current_job": "Backend @ Platzi",
                    "created_at": "2020-04-13T23:38:28.631000Z",
                    "updated_at": "2020-04-13T23:38:28.631000Z"
                }
            ],
            "ranking": "5.00",
            "created_at": "2020-04-13T23:39:36.795000Z",
            "updated_at": "2020-04-13T23:39:36.795000Z"
        }
    ]
}
```

## Llamados a un API con el método post utilizando JSON

1er Paso: Ver documentación y mirar como autenticarnos [con un user y password]

2do Paso:El endpoint de la API en este caso es un espacio netamente para la generación de tokens de acceso, el cual seria …/api/api-token-auth/

3er Paso: Agrega el user y la contraseña por medio de JSON en Postman teniendo seleccionado POST(al lado izquierdo de la url) y abajo vas a body>raw>text>JSON(esta opción se despliega si le das click a text en el nivel del menú que se encuentra raw)

4to Paso: Verifica en Header el tipo de contenido que se va a enviar al servidor, en este caso es Key[Content-Key]-Value[application/json] ✔️(listo)

5to paso: Escribe dentro de una llave el user y el password, todo va entre comillas, esto retornara un token (lo usaremos en el siguiente paso)

6to paso:Si queremos agregar al servidor a un comentario tienes que poner el Headers el token del anterior paso, esto se hace añadiendo un espacio en el Headers de donde vamos a realizar el comentario** entonces, vamos a Headers y ponemos KEY=[Authorization] y el VALUE =[token *aquí va el token*]//Esta es la manera de tener acceso a esta API

7to paso: Ya hecho el anterior paso con el endpoint …api/coments/ y en el body>raw>JSON podremos poner un coment especificado su destino con la palabra material, en este caso esa es la palabra clave para identificar en qué sección irá este cometnario.

API:
https://reqres.in/api/post
esta API si funciona y permite hacer GET y POST:
Aqui muestro mis screnshots de los metodos:

1. POST (para registrarse)

   https://reqres.in/api/register

![postman1.jpg](https://static.platzi.com/media/user_upload/postman1-9abf603f-1102-48a9-902f-39994fc2c77b.jpg)

1. POST (para autenticarse)

   https://reqres.in/api/login

![postman1a.jpg](https://static.platzi.com/media/user_upload/postman1a-6fd96093-31f7-4e2b-b0f2-4fc46931a900.jpg)

1. POST (para hacer un comentario)

   https://reqres.in/api/post

   ![postman2.jpg](https://static.platzi.com/media/user_upload/postman2-7138c8c4-2af8-4be9-bcb6-9b453c4c3a6f.jpg)

#### Reto realizado:

**1. Mediante x-www-form-urlencoded**
![img](https://i.ibb.co/dg8PPcM/Postman-tarea-1.png)

**2. Mediante form-data

![img](https://i.ibb.co/yn4frmd/Postman-tarea-2.png)

## Llamados a un API con el método post utilizando Form Data

Resumen de clase:
Los llamados a un API usando el método POST pueden hacerse de varias maneras.

1. Enviando información en **formato JSON **(visto en la clase anterior)
2. Usando el método **x www form urlencoded** (en cuyo caso, la URL envía la información)
3. Utilizando el método **form-data** (que sirve especialmente para subir archivos sin necesidad de haberlos pasado a Base24)

Para ver las diferencias entre métodos, es muy útil consultar la consola que tiene el propio Postman (la versión RAW porque la “Pretty” omite detalles).

![](![2021-10-09_19h35_10.png](https://static.platzi.com/media/user_upload/2021-10-09_19h35_10-1e5c030f-1c09-405e-a18e-6fe96fb4deed.jpg)

```json
<code> 
"id": 5,
    "name": "Curso Automation",
    "description": "Con este curso aprenderas sobre automatizacion",
    "teachers": [
        {
            "id": 6,
            "name": "Isilreiberth Perez",
            "description": "Tester QA",
            "current_job": "Funder",
            "created_at": "2021-10-09T22:28:34.688717Z",
            "updated_at": "2021-10-09T22:28:34.688726Z"
        },
        {
            "id": 7,
            "name": "Williams Hidalgo",
            "description": "Tester Automation",
            "current_job": "Tech Leader",
            "created_at": "2021-10-09T22:28:34.692834Z",
            "updated_at": "2021-10-09T22:28:34.692850Z"
        }
    ],
    "ranking": "0.00",
    "created_at": "2021-10-09T22:28:34.687177Z",
    "updated_at": "2021-10-09T22:28:34.687199Z"
```

## Llamados a un API con el método PUT



## Llamados a un API con el método DELETE



## Optimización de environment de postman y configuración de la colección



## Agregar ejemplos de responses y descripción de endpoints




# 3. Automatización de procesos con JavaScript

## Guardar el token del login con una prueba automática


## Creación de Pruebas para endpoints



# 4. Puesta en producción

## Publicar Documentación



## Cierre del curso

