Guía de desarrollo y maquetación de E-mail Marketing | **QUADI**
===================
Estádares para escribir y mantener código para maquetacion de E-mail en **QUADI**


----------


**Introducción**
-------------


Esta guía ha sido formulada con el propósito de estandarizar el código realizado para campañas de E-mail marketing, implementando buenas practicas en la construcción de plantillas, teniendo en cuenta las convenciones estándares de **HTML** y **CSS** pero se optimizan y normalizan varias reglas implícitas las cuales están validadas y probadas por los diferentes clientes de ***E-mail***.



###**Estructura de Archivos**


----------


Para un mejor orden en el desarrollo de plantillas se propone separar los archivos base (**PSD**,**AI**) de los procesados y finales (**HTML**). 
La estructura de archivos que se muestra a continuación y dependerá del requerimiento por parte del **PM** y estrategia de la campaña:

    plantilla/
    |__ info.txt
    |__ psd/
    |   |__ arte.psd
    |__ email/  
	    |__ index.html
        |__ imagenes/
	        |__ header.jpg
	        |__ cuerpo.jpg
	        |__ boton.gif    
	        |__ twitter.jpg
    

Las carpetas y archivos. que hagan parte de la campaña no deben tener
espacios entre palabras cada separación debe ser indicada con el simbolo **underscore  [ _ ]** o guión bajo, tampoco puede contener caracteres especiales ( **,{}:"{/"?}|}+-@#!'';:''* ), acentos y mayusculas.

Ejemplo:

   


----------


// **Evita**
#####<i class="icon-folder"></i> Plantilla personas *{2017}

----------


        
// **Prefiere**
##### <i class="icon-folder"></i> plantilla_personas_2017


----------

###**Encabezado y referencia**


----------


Al iniciar con la construcción de la plantilla debemos crear un archivo **.txt**, donde indicaremos toda la información correspondiente a la plantilla, el cual deberá ser llenado por el desarrollador a cargo, de esta forma:

    //-
     * Nombre de la plantilla:
     * Fecha:
     * Descripción
     * Desarrollador:
     * Dónde se utiliza:

###**Maquetación y corte ( HTML )**


----------


Las plantillas de E-mail deben tener una estructura la cual  permita verse correctamente en todos los clientes de correo, como así también en dispositivos móviles.
Es recomendable que al maquetar la plantilla  se utilicen tipografías estándar, fondos de colores planos, como así también reducir el uso de imágenes, en favor del texto, cuanto más livianas las plantillas, más rápida será su descarga. No es conveniente que el peso del html sea mayor a 1 MB.

![E-mail Responsive](https://www.nobledesktop.com/image/sem-graphic/responsive-html-email-500.png)
####**Uso de HTML para las plantillas y Accessibility**


----------


Para estructurar la plantilla de E-mail se utilizará como base  elementos básicos de [HTML4](http://html.conclase.net/w3c/html401-es/index/elements.html) junto con los atributos probados y validados en diferentes clientes de E-mail:

    <table>  en lugar de <div>,
    H2 titulo del Email
    H3 descripcion del email
    H1 Titulo contenido principal
    H4 Subtitulo segundario
    alt describe el contenido de nuestras imagenes
    title titulo de los hipervinculos e imagenes
    #FFFFFF  en lugar de #FFF,
    padding  en lugar de margin,
    CSS2  en lugar de CSS3,
    HTML4 en lugar de HTML5,
    background-color en lugar de background,
	CSS inline en lugar de hojas de stylo o bloques <style>.
	

> **Nota**
> Al realizar la maquetacion de nuestra plantilla es importante declarar los atributos [ *border="0" cellpadding="0" cellspacing="0"* ] en las tablas.

El buen uso de las etiquetas básicas de [HTML](http://html.conclase.net/w3c/html401-es/index/elements.html), nos ayudan a organizar y estructurar nuestras plantillas, a su vez ayuda a los buscadores a identificar los elementos importantes de nuestro contenido. Cuando los motores de búsqueda acceden a nuestro Email o desde la vista web, entienden que las palabras que están dentro de un encabezado tienen mucha más importancia que el resto, le dará más peso a los encabezados de primer nivel (H1), luego a los de segundo (H2) y así sucesivamente.

####**[CSS](http://www.mclibre.org/consultar/htmlcss/css/css_propiedades.html) in line**


----------


Algunos clientes de email (WEB,desktop) eliminan cualquier [CSS](http://www.mclibre.org/consultar/htmlcss/css/css_propiedades.html),es importante codificar correctamente el estilo para evitar problemas en clientes de email.

----------


// **Evita**

    <style type="text/css">
        .bqcentro{
    	    color:#000000 ;
    	    font-size:25px;
    	 }  
     </style>

----------


        
// **Prefiere**

    <p style="color:#000; font-size:25px;">Texto demo</p>

 


----------
####**Uso de imágenes**


----------


Al  usar imágenes cortadas o al lado de otra, en la construccion de nuestras plantillas, es necesario que cada imagen tenga el estilo **“display:block”.**

Algunos clientes de correo, generan automáticamente espacios blanco,  entre las imágenes, desarmando el diseño de la plantilla.
// **Evita**

    <style type="text/css">
        .bqcentro{
    	    color:#000000 ;
    	    font-size:25px;
    	 }  
     </style>

----------


        
// **Prefiere**

    <p style="color:#000; font-size:25px;">Texto demo</p>

 
----------

// **Evita**

    <img src="chanfle.jpg"/>


----------


        
// **Prefiere**

    <img src="https://www.web.com/wp-content/uploads/2016/11/uno.jpg" alt="descripcion" width="100" height="1000" border="0" style="border:0; outline:none; text-decoration:none; display:block;">

 


----------

***Formatos***
Los formatos de imágenes soportados para E-mail en la actualidad son: JPG, PNG y GIF.

Nombres y formatos siempre deben ir en minúsculas.

***Optimización:*** 
Toda imagen debe ser comprimida según sea el mejor método, según el formato.

Herramientas para comprension de imagenes:

Compressor.io
Kraken.io
tinypng.com
tinyjpg.com
imageoptimizer.net

###**Buttons**
----------

// **Evita**

    <a href="#" class="btn btn-primary">Click Here</a>


----------


        
// **Prefiere**

   

     <table border="0" cellpadding="0" cellspacing="0" class="btn btn-primary">
      <tr>
        <td align="center">
          <table border="0" cellpadding="0" cellspacing="0">
            <tr>
              <td> <a href="" target="_blank">Take action now</a> </td>
            </tr>
          </table>
        </td>
      </tr>
    </table>

 


----------

####**Responsive**


----------


> Al realizar la version responsive de la plantilla debemos tener en cuenta los media queries, en este caso se hace el uso del bloque `<style></style>`
> Donde declararemos  por medio en un condicional el comportamiento de nuestra plantilla en diferentes resoluciones.

    <style type="text/css">
    @media only screen and (max-width:480px){
    .bqcentro{
	    color:#d9d9d9 !important;
	    font-size:25px; !important;
	    }
    }
    </style>

Cada regla debe ir definida de acuerdo a la resolución de pantalla a la que se  deba adaptar, lista de las mas usadas.

 - **Smartphones: Portrait**
@media only screen and (max-width : 320px)

 - **Smartphones: Landscape**
@media only screen and (min-width : 321px)

 - **Smartphones: Portrait and Landscape**
@media only screen and (min-device-width : 320px) and (max-device-width : 480px)

 - **iPads: Portrait**
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : portrait)

 - **iPads: Landscape**
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px) and (orientation : landscape)

 - **iPads: Portrait and Landscape**
@media only screen and (min-device-width : 768px) and (max-device-width : 1024px)

 - **iPhone4**
@media only screen and (-webkit-min-device-pixel-ratio : 1.5), screen and (min-device-pixel-ratio : 1.5)

 - **iPhone 5: Portrait**
@media only screen and (min-device-width : 320px) and (max-device-width : 568px) and (orientation : portrait)

 - **iPhone 5: Landscape**
@media only screen and (min-device-width : 320px) and (max-device-width : 568px) and (orientation : landscape)

 - **iPhone 5: Portrait and Landscape**
@media only screen and (min-device-width : 320px) and (max-device-width : 568px)

 - **Desktops and Laptops**
@media only screen and (min-width : 1224px)

 - **Large Screens**
@media only screen and (min-width : 1824px)


###**URL's**
Prefiere URL's absoluta al  linkear imagenes,call to action.

####**Clientes de correo electrónico**


----------


Los clientes de correo electrónico utilizan diferentes motores para renderizar correos HTML:

 - Apple Mail, Outlook para Mac, Android Mail y correo de iOS utilizan
   WebKit .
 - Outlook 2000, 2002 y 2003 utilizan Internet Explorer .
 - Outlook 2007, 2010 y 2013 utilizan Microsoft Word.
 - Los clientes Web utilizan el motor respectivo de su navegador (Safari utiliza WebKit y Chrome utiliza Blink).

También añaden sus propios estilos en la parte superior del encabezado. Por ejemplo, Gmail establece todas las fuentes <td> en font-family: Arial,sans-serif;


####**Test de plantillas** ([Litmus](https://litmus.com/))


----------


Es necesario testar las plantillas en distintos clientes de correo

 - Imágenes: La mayoría de los clientes de correo electrónico bloquean las imágenes por defecto. Entonces, al realizar un test es posible
   saber cómo se visualizará el mensaje en la instancia  de “vista
   previa”.
 
 - Verificación de texto sin formato:Dado que hay usuarios que al
   momento de suscribirse seleccionan la opción de recibir emails sin
   formato, no está de más previsualizar cómo llegarán estos envíos.
 - Optimización de la línea de asunto: a través de Litmus se puede ver de antemano cómo se leerá el “asunto” en las distintas plataformas y dispositivos.



De esta manera, nos  aseguramos que los destinatarios las visualicen correctamente en todos los casos.

###**Sintaxis**


----------


 - Utiliza 2 espacios (soft tab) / 1 tab (hard tab) para indentar.
 - Usa doble comilla " (double quote) para abrir y cerrar atributos,
   propiedades, valores, etc.

###**Software**


----------


 - Mac OS X
    - Sublime Text
    - Dreamweaver
    - Illustrator
    - Photoshop
 -  Windows
    - Sublime Text
    - Dreamweaver
    - Illustrator
    - Photoshop
   
###**Ambiente Local**


----------


El ambiente de desarrollo local debe correr en http://localhost/ y contempla:

 - Apache


----------


***Contributor***
Fredy teheran tovar
