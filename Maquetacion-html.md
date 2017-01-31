## Guia Basica de buenas prácticas de maquetación en HTML

Dejo esta guia inicial para tener una buena maquetacion html y tener mejores resultados con nuestros proyectos.

inicio dejando 2 frases.

> ### Conseguir grandes resultados requiere grandes acciones- Jim Rohn

> ### La mejor publicidad es la que hacen los clientes satisfechos- Philip Kotler

### Puntos claves para iniciar..

- Lo primero es declarar un doctype. La declaración de un “Doctype” deberá localizarse al inicio del código HTML.
Es importante señalar que en la declaración del doctype NO debe haber NINGÚN espacio en blanco ni cambio de línea ANTES , la mayoría de los navegadores saben arreglárselas, pero en IE8 provocará “misteriosos comportamientos”.

- Encoding: La razón por la que se hace uso de los “&aacute” es que la página no define su encoding, debe estar en UTF-8, y especificar el meta para el encoding, de modo que no haya ninguna necesidad de utilizar HTML entities para las tildes y caracteres raros.


- Usa etiquetas de ‘Título’ con significado. Lo que introducimos en la etiqueta <title> es lo que Google utiliza para su lista de resultados.

- Usa metaetiquetas descriptivas. Las metaetiquetas descriptivas ayudan a que los robots de los buscadores obtengan mayor información acerca de las páginas.

La Metaetiqueta “Description” : Esta metaetiqueta describe el propósito principal de una página. Deberá ser diferente en cada página o sección. Google también utiliza el contenido de ésta y lo muestra en los resultados de búsqueda.
Para no saturar las descripciones es mejor que incluyas contenido conciso que atraiga a tus potenciales visitantes.

Metaetiqueta “keywords‟ (palabras clave) 
Esta metaetiqueta incluye palabras separadas por comas que son relevantes al contenido de la página y al igual que la metaetiqueta “description‟, debe ser concisa y directa.

- Utiliza divs “<div>” para maquetar y dividir tu contenido en zonas o secciones
El primer paso que debes tener en cuenta es dividir el contenido de la página en secciones principales para organizar la información de la misma. Con esto garantizarás un contenido ordenado y con una buena arquitectura de la información.

- Por regla general NO utilizar tablas, A MENOS que se trate de información tabulada,
pues si la naturaleza de la información es una relación de datos tabulados, entonces nada mejor que una tabla para representarla (ej: tablas comparativas, desgloses, una relación de elementos con sus respectivas propiedades, etc).

incorrecto: que el marco del sitio sea una tabla que lo envuelve todo para darle estructura
correcto: que una tabla con “info tabulada” forme “parte” del cuerpo de un contenido (ej: http://en.wikipedia.org/wiki/Comparison_of_web_application_frameworks o http://drupal.org/project/usage/drupal).

- SEO: cabecera y logos como imágenes son anti-SEO, se deben utilizar trucos para representar textos (aunque estén ocultos bajo las imágenes) y en cualquier caso los “alt” y “title” de esas imágenes son bastante importante.

- Separa el contenido de la página HTML del estilo con que se muestra
El código HTML contendrá la información, el código CSS el estilo y la manera en que se presenta. Siempre hay que usar estilos separados y no dentro de la página HTML. Así el código será más limpio y permitirá modificaciones de manera más eficaz.

- Intenta unificar todos los estilos en una sola hoja de estilos

Cada archivo implica una solicitud HTTP, lo cual hace que el tiempo de carga de la página sea más lento.

Cuando son muchos CSS para IE se utiliza el “@import”, que permite entonces exceder el límite de 30, pero mucho mejor es utilizar un framework que permita “agregar” los ficheros CSS y JS en un único fichero para CSS y un único fichero para JS (lo cual resuelve el problema de las descargas paralelas).

- Intenta tener la menor cantidad de ficheros externos de JavaScript 
No es recomendable atiborrar nuestro código HTML de llamadas a ficheros externos.
Tener el código JavaScript en ficheros aparte con extensión JS, y aunque a veces hará falta poner algo del código en la página, este debe ser de mínimo impacto.

- Utiliza siempre que sea posible funcionalidades de CSS2 en lugar código JavaScript para los estilos como el hover con lo que se evita estar cargando innecesariamente la ejecución del JavaScript.

- Usar las etiquetas de encabezados “<h1>…<h6>” de manera jerárquica para otorgar importancia a nuestro contenido y que éste sea clasificado acertadamente.

- Haz un buen uso de las etiquetas HTML

Aquí te detallo algunos ejemplos:

– Usar la etiqueta <p> para los párrafos apropiadamente y no hacer uso abusivo de los saltos de linea <br> . Para añadir espacio entre párrafos hay que ayudarnos de CSS usando propiedades como ‘padding’ o ‘margin’.

– Estudiar más el potencial de los padding para ahorrarse estar repitiendo margins en los elementos que están en una misma región.

– No realizar alineaciones centradas forzadas en atributos HTML para centrar la página. Utilizaremos márgenes automáticos para centrar el div contenedor.

– Si quieres resaltar algún texto es mejor usar “em” o “strong” en lugar de usar “i” o “b”

- No abusar del uso de <div>

Evitar saturar el código de <div> anidados. Hay que usarlos cuando no haya otro elemento html que represente lo que necesitamos.

No hay que usar las DIVS como sustituto de elementos lineales para obtener elementos de bloque. En ese caso hay que utilizar elementos lineales apoyados en las propiedad ‘display: block’ de CSS.

15. No abusar de float

Esto es muy importante, para garantizar la compatibilidad entre los diferentes navegadores, los divs no deben ser flotados masivamente porque en muchos browsers (IE6 por ejemplo) el sitio se rompe de mala manera, los float se deben utilizar solamente en los casos que ya están identificados como válidos y multi-browser.

- Para maquetar los menús te recomendamos utilizar una lista desordenada <ul>

- Fíjate que has cerrado todas tus etiquetas.

- Usa minúsculas en tus etiquetas y atributos para facilitar la lectura de tu código.

- Usar los atributos “alt” y “title” para las imágenes

El atributo “alt” significa “texto alternativo”, y quiere decir, que si no se encuentra la imagen se debe mostrar ese texto, entonces un error común es introducir toda una oración, lo cuál rompería horriblemente la página si le pedimos al navegador que no muestre las imágenes, en la vida real esto solo ocurre para los navegadores textuales (de consola) o cuando una imagen está rota y no es encontrada.
los buscadores comprenden el significado de la imagen por su “title” que es realmente el título que sí puede llevar una oración explicativa, y entonces es el title quien es SEO, lo que pasa es que “en ausencia del title” los buscadores intentan encontrar significado textual en el “alt”.

- Utilizar etiquetas <fieldset> y <label> en los formularios

Es útil utilizar la etiqueta <label> para dar nombre a los elementos de un formulario y eliminar el uso de la etiqueta párrafo <p> o para evitar introducir texto sin etiqueta alguna. Igualmente es importante dividir los sets dentro de los formularios mediante la etiqueta <fieldset> y cuando sea necesario nombrar los set mediante la etiqueta <legend>.

- Evitar tener una hoja de estilo diferente en dependencia del navegador o de la versión de este.

Es posible evitar estos tweak&twist si se tiene dominio de CSS2 y CSS3, y en general de correcta maquetación multi-browser, puesto que es posible utilizar un único fichero CSS con reglas que tomen en cuentan algunas particularidades entre los diferentes browsers (ej: poner primero las reglas específicas para cada navegador y finalmente la regla CSS3 que por estar de última predominará en caso de que el navegador la soporte).

Pero si de todas formas nos encontramos haciendo semejante condicional (suele pasar cuando uno va a arreglar algo que ya está hecho y no se pretende re-hacerlo completamente nuevo) entonces hay que destacar que las reglas en ese otro fichero CSS deben ser la mínima cantidad posible.

- Ordena tu código con tabulaciones adecuadas ya que es una buena práctica para que sea fácilmente modificable y entendible por ti mismo o si es necesario por otra persona que continúe el desarrollo.

- Comenta tu código

Destacar que los comentarios deben ser sintéticos y decorosos, ya que pueden ser vistos por el usuario, la página se despacha con los comentarios HTML incluídos, y lo mismo para CSS y JS, entonces no está bien comentar como si estuviésemos hablando en familia, porque puede terminar teniendo una mayor audiencia en caso de que alguien quiera inspeccionar por dentro…..

- Valida el código
Es una herramienta muy útil que puede ayudarte a encontrar errores tales como olvidar cerrar una etiqueta, haber cerrado un estilo con dos puntos en lugar de punto y coma y un largo etc. Te animamos a usar el validador del W3C.


> **Si tienes alguna sugerencia o quieres aportar algo mas te invito a que edites esta guia y agregues datos de acuerdo a tu experiencia :)**


**Salu2.**


