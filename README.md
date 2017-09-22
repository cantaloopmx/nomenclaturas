# GUÍA DE NOMENCLATURAS

### GENERAL
Todo el código, archivos, nombres de variables, bases de datos, etc deberán estar en inglés para homologación de idioma. Exceptuando por las cosas visibles por el usuario como: textos y ayudas visuales de la interfaz gráfica, urls (amigables en el idioma requerido).


### CARPETAS Y ARCHIVOS

#### Nombres de carpetas
Todos las carpetas serán nombrados con snake_case, sin uso de acentos, espacios o caracteres especiales.

**Ejemplo**: Suponiendo que necesitamos nombrar una carpeta para guardar los archivos del cliente Agencia Patito o documentos importantes.
  > agencia_patito
  
  > documentos


#### Nombres de archivos
Todos los archivos serán nombrados con snake_case, sin uso de acentos, espacios o caracteres especiales, tomando en cuenta el contexto.


#### Nombres de propuestas, cotizaciones y otros archivos
Los nombres de archivos de propuestas, cotizaciones o cualquier otro archivo que se enviará al cliente o se compartirá internamente deberán ser formados por el año, mes, día, seguido del nombre del cliente en minúsculas y por fin el nombre del proyecto. Si aplica en número de versión.

**Ejemplos**: Suponiendo que necesitamos guardar la propuesta de Agencia Patito para su proyecto de Encuesta de satisfacción, también necesitamos guardar la cotización de Cliente Importante para su proyecto Proyecto Secreto.
> /propuestas/**20170921_agencia-patito_encuesta-de-satisfaccion.doc**

> /cotizaciones/**20171130_cliente-importante_proyecto-secreto.pdf**


### BASES DE DATOS
Todas las bases de datos deberán ser *InnoDB* y estar en *utf8_general_ci*.


#### Nombres de bases de datos
Los nombres de las bases de datos deberán estar en inglés, plural siempre en minúsculas. El nombre de la base de datos se compone de: 

* Nombre del cliente en camelCase (preferible sólo manejar una palabra)
* Nombre del proyecto en inglés (siempre que sea posible)
* Siglas del ambiente cuando la base es de desarrollo (dev)

**Ejemplo**: Suponiendo un cliente llamado Agencia Patito para el cual se está desarrollando el proyecto Encuestas de Satisfacción. Nombres válidos para la base de datos:

> patito_polls

> patito_satisfactionPolls


#### Nombres de tablas de la base de datos
Los nombres de las tablas de las bases de datos deberán estar en inglés, plural siempre en minúsculas.

**Ejemplos**: Suponiendo que se requieren las siguientes estructuras de datos: Libros, Productos, Podcasts. Nombres válidos para las tablas serían:

> books
  
> products
	
> podcasts


#### Llaves primarias
Todas las tablas deberán tener una llave primaria que sea única. Esta llave deberá ser un campo número, consecutivo de auto incremento.

**Ejemplos**:
Suponiendo que necesitamos crear las tablas de Libros, Productos y Podcasts.
<table>
<tr>
<td>
<b>| books</b><br />
id<br />
name<br />
...
</td>
<td>
<b>| products</b><br />
id<br />
name<br />
...
</td>
<td>
<b>| podcasts</b><br />
id<br />
title<br />
… 
</td>
</tr>
</table>

#### Nombres de tablas relacionales
Los nombre de las tablas relacionales deberán estar en inglés, el nombre en singular de ambas tablas en snake_case.

**Ejemplos**:
Suponiendo que necesitamos vincular usuarios a los libros que posee, productos a sus categorías o podcasts con su emisora:

> user_book

> product_category

> radio_podcast


#### Nombres de llaves foráneas
Las llaves foráneas deberán tener el nombre de la tabla a la que hacen referencia, en inglés, singular y seguidas de _id. Deberán siempre estar después de la llave primaria (id) de la tabla.

**Ejemplos**:
Suponiendo que necesitamos vincular un sólo libro a un usuario, una categoría a un producto o un podcast con su emisora:
> La tabla **books** debe tener la llave foránea **user_id**

> La tabla **products** debe tener la llave foránea **category_id**

> La tabla **podcasts** debe tener la llave foránea **radio_id**


#### Campos de control
Todas las tablas principales tendrán los siguientes campos de control al final de la tabla: 

> status_id (entero y llave foránea de status)

> created_by (entero y llave foránea de usuario)

> updated_by (entero y llave foránea de usuario)

> created_at (timestamp y default NOW())

> updated_at (timestamp y default NOW())

> deleted_at (timestamp y default null)


### VARIABLES, FUNCIONES Y CLASES

#### Nombres de variables
Las variables deberán estar en inglés, minúsculas, snake_case y no deberán ser de una sóla letra. Elige nombres significativos y alusivos a su propósito.

**Ejemplos**:
Suponiendo que necesitamos crear una variable que guarde un arreglo de libros o una variable de autoincremento, los nombres válidos serían:
> books

> counter


#### Variables dentro de loops
Las variables utilizadas para iteraciones y bucles podrán ser de una sóla letra, sin repetir alguna letra que se haya utilizado previamente en el mismo bloque de código.

**Ejemplo**:
Suponiendo el siguiente loop con for:

```javascript 
for(let i=0; i<books.length; i++){...}
```


#### Tipos de variables
Se deberá respetar el tipo de variable que haya sido definido inicialmente y no deberá usarse la misma variable para tipos de datos diferentes.
* Registro de base de datos deberá utilizar variables de tipo **objeto (Object)**
* Conjunto de objetos deberá utilizar **arreglos (Array)**
* Valores numéricos deberán utilizar **enteros (Integer)**
* Valores de texto deberán utilizar **cadena (String)**


#### Nombres de Funciones
Las funciones se deberán nombrar en inglés, plural o singular tomando en cuenta el contexto y con camelCase, iniciando con minúscula.

**Ejemplo**:
Suponiendo que necesitamos crear una función que cambia el valor de un campo que se despliega en pantalla o que cambie varias opciones de otro elemento en pantalla:

```javascript
setParam(value){...}
```

```javascript
changeSettings(){...}
```


#### Nombre de Clases
Las clases se deberán nombrar en inglés, plural o singular tomando en cuenta el contexto y con CamelCase, iniciando con mayúscula siempre.

**Ejemplo**:
Suponiendo que necesitamos crear una clase que representa un registro de la tabla books: 

```javascript
default class Book extends Component {} // ReactJS
```

```php 
class Book extends Model{} // PHP
```
