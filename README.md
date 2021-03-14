# CURSO PRACTICO DE WORDPRESS

##COMENZAR CON WORDPRESS

### ¿QUÉ ES WORDPRESS?

Wordpress es un Sistema Gestor de Contenido escrito en PHP. Esto significa que es un software que viene preparado para que nosotros podamos gestionar contenido como texto e imagen sin tener que tocar una línea de código. El mismo funciona con MySQL y está bajo la licencia GPL, esta licencia nos asegura que este código es abierto, que lo podemos estudiar, modificar y compartir.

#### Inicios
Wordpress tiene sus inicios en el año 2003 cuando el programador Matt Mullengweg toma el proyecto b2/cafelog el cual, estaba anunciando su retirada y toma ese proyecto para hacer Wordpress orientado a sitios de blog. Hoy día, Wordpress ha tomado diferentes caminos gracias a su comunidad y puede hacerse tanto un sitio de blog como un sitio institucional y hasta una aplicación web.
Nota: Investiga un poco más acerca de Matt Mullengweg.

[Wordpress.com](https://wordpress.com/es/ "Wordpress.com") vs [Wordpress.org](https://wordpress.org/ "Wordpress.org")

A Wordpress lo podemos encontrar en dos lugares. Uno es [Wordpress.com](https://wordpress.com/es/ "Wordpress.com"). Este es un servicio online que nos permite crear una cuenta y sin tener que descargar nada, poder administrar nuestro sitio desde su administrador.

[Wodpress.org](https://wordpress.org/ "Wodpress.org"): El otro lugar es Wordpress.org el cual, nos permite descargar el código fuente de Wordpress para instalar en cualquier servidor y así poder gestionar nuestro código para agregar funcionalidades o personalizar nuestros propios diseños.


------------

### FUNCIONAMIENTO DE WORDPRESS

Cuando alguien entra a nuestro sitio ejecuta el código fuente de wordPress, este consulta la DB, ¿Qué contenidos tiene que devolver? y los procesa con los temas que generaran vistas.

Al mismo tiempo, se van ejecutar los plugins que van a servir como apoyo a los temas para ejecutar nuevas funcionalidades.

Características

- Autoadministrable
- Gestión de usuarios
- API REST
- Flexible
- Actualizaciones
- Comunidad


------------

### ¿QUE SON LOS TEMAS EN WORDPRESS?

**Theme:**

Estructura de archivos que van a generara vistas en nuestro navegador. Para generar un tema hay que tener dos archivos específicos:

- index.php: Todas las vistas generadas van a tomar por defecto el archivo index.

- style.css: Gestiona el diseño del tema y posee la data del mismo.

**Otros Archivos que debe contener el tema:**

- front-page.php: Vista por defecto de la página principal del sitio.

- footer.php: Carga la parte de abajo de nuestro sitio además de las dependencias que le añadamos.

- functions.php: Todas las funcionalidades que posea el tema. Aquí podemos añadir nuestro código para ampliar las funcionalidades del mismo.

- header.php: Carga la parte de arriba de nuestro sitio además de las dependencias que le añadamos.

- 404.php: Corresponde a la vista de la página 404 de nuestro sitio. Está página también es conocida como la página de “no encontrado”.

- page.php: Páginas que se generen dentro del administrador.

- screenshot.png: Imagen de referencia del tema. Esta imagen se visualiza en la parte de administración.

- single.php: Corresponde a aquellos posts, entradas, post-types que no se le asignen una vista concreta.

------------

### ¿QUE SON LOS HOOKS?

Son espacios dentro del codigo donde puedes ejecutar tus propias funciones, puedes ejecutar 2 tipos de hooks, action y filter

**Action**

Ejecuta una función en un lugar que especifiques sin retornar ningun valor.

**Filter**

Ejecuta la funcion recibiendo parametros procesandolos y retornandolos ya procesados


------------

### MANEJO DE LIBRERÍAS EN WORDPRESS

Las librerías en WordPress las podemos manejar de diferentes tipos y para cada uno de ellos los vamos a utilizar de manera diferente.

Para los archivos CSS vamos a usar dos funciones, estas están basadas en dos tipos de formas para manejar la información en WordPress:

**wp_register_style():** En esta es el registro. Nos sirve para registrarnos en librería y que la tengamos a disposición con una dependencia pero no las va a ejecutar en nuestro HTML. Recibe 5 argumentos:

**$handle string:** el nombre que va a tener nuestra librería para wordpress

**$src string** or **$src boll:** Determinar de donde es la fuente de nuestro archivo. En source Podemos recibir bool porque podemos llamar todas las dependencias que nosotros necesitamos sin crear una nueva, es decir, si nosotros tenemos registrado Bootstrap, podemos llamar a bootstrap, pasar bool en vez de string en el source y recibir solamente Bootstrap. Estos es como un alias para hacer un conjunto de librerías sin llamar una nueva

**$deps=array()array**: las dependencias van a ser un array de strings que vamos a poner los nombres o handeles que fuimos registrando previamente, si tenemos alguno o directamente a registrarlo si tenemos uno nuevo

**$ver=string or $ver=bool or $ver=null:** estos son importantes si tenemos una versión de cache para poder decirle a nuestro navegador que regenere el pedido en caso de querer hacer modificaciones

**$media=’all’string:** Nos permite que nuestro ccs se pueda ejecutar en todos lados o en una resolución especifica o en un dispositivo especifico

**wp_enqueque_style():** En esta es el poner en cola. Nos va a ejecutar directamente la librería que nosotros le digamos, pero va a llamar las referencias sin necesitar alguna que tengamos registradas. Esta también va a recibir los mismos argumentos pero la ejecución va a ser directamente en vez de registrarlos, dejarla a disposición ya ejecutado en nuestro HTML.

En Javascript:

**wp_register_style():** En esta es el registro. Nos sirve para registrarnos en librería y que la tengamos a disposición con una dependencia pero no las va a ejecutar en nuestro HTML. Recibe 5 argumentos:

1. $handle string: el nombre que va a tener nuestra librería para wordpress

2. $src string or $src boll

3. $deps=array()array

4. $ver=string or $ver=bool or $ver=null: estos son importantes si tenemos una versión de cache para poder decirle a nuestro navegador que regenere el pedido en caso de querer hacer modificaciones

5. $in_footer=falsebool: Este es el único argumento diferente que podemos de cirle que se ejecute en el footer o que se ejecute en el head.

**¿Por qué manejar las librerías de forma dinámica?**

Nos van a permitir utilizar nuestros templates en diferentes sitios, diferentes urls, en las cuales nosotros tengamos nuestras propias librerías en ellas. En el momento en que nosotros cambiamos de sitio esas urls se van a generar automáticamente y van a llamar a ese archivo. Además el uso de registro de dependencias nos permite controlar con PHP el flujo en las cuales se cargan las diferentes librerías y evita problemas como generar librerías duplicadas


------------

### INSTALACION DE XAMPP

Pasos
1. [XAMPP](https://www.apachefriends.org/es/index.html "XAMPP")
2. Descargar la version para el SO
3. Next
4. Descactivar Filezilla, Mercury Mail, TomCat, Webalizer, Fake Sendmail
5. Next.
6. Importante elegir la carpeta en el orden de jerarquia: C://xampp
7. Desmarcar para saber mas sobre el uso del contenido
8. Next.
9. Permitir accesos
10. Inicializar el control panel
11. Elegir idioma
12. Abrir en el navegador localhost


------------

### INSTALACION DE WORDPRESS

Pasos
- Descargar [wordpress](https://wordpress.org/download/)
- Mover el .zip a la carpeta xampp>htdoc (con el paquete wampp es wampp>www)
- Crear nueva base de datos `platzi_gift`
- Cambiar nombre wp-config-sample.php a `wp-config.php`
- Abrid con el editor de codigo
- Establecer en el DB_NAME el nombre de la base de datos : `define('DB_NAME', 'platzi_gift');`
- Establecer en el DB_USER el user : `define('DB_USER', 'root');`
- Establecer en el DB_PASSWORD  : `define('DB_PASSWORD', '');`
- Pegar el codigo:



```
define('AUTH_KEY',         '6l]y7z$Q5*`e$XYEzAJhxlp4;1nt|Iw:c]PUS_y}+]|OG0@gB8P-e/I8/K}QQ|oe');
define('SECURE_AUTH_KEY',  ';-+%{]|<=^rQ|Fa47NU5W{e<r/g`Bxm.k]*DIIlk4(eKWiccSUnuB$wz{3nBK$S=');
define('LOGGED_IN_KEY',    'hrBx&.QW$)AKq7b`<DqbBr,cyfnt7H55M19m3=*I*3?hs:H/3kW-I( o.~|3t%4u');
define('NONCE_KEY',        '|~sZ&EywfZa!<4.E!_ <+}df/}3kFM!!8E?a]EVm]=z]P6<P{1}=;he; /&cp,<q');
define('AUTH_SALT',        'RJHk.sHIT^NRJ8g#%vkKmB+XO^?,C{jANv;0a562oLRk;vxyj X32OIC%84$-k!`');
define('SECURE_AUTH_SALT', 'sbjQkbz}|V,4YSu!$jk.+dI)_Q2 ^UN#JvjMPT_ZvFD+8X)Gn}/,;%Lf1O#iOb[:');
define('LOGGED_IN_SALT',   'pkg*-;%Y2AWA_jafxQ3|qq(LWKa<9>y#XL=.3Kl5NY^51|bfg,|ZQ/Q?1dol,D>~');
define('NONCE_SALT',       '0@k5]f+K|$~HSJ&RB4rmgAB!=:z/vkw05T%`I&#{e~#Qqj/<n j,qX+sbY3|S-I0');
```


- Abrir en el navegador localhost/nombredelacarpeta
- Elegir idioma
- Configurar titulo, nombre, correo
- Click en instalar
- Acceder con usuario y contraseña 


------------

### USUARIO Y OPCIONES DE WORDPRESS

**Administrador:** Es quien administra todo el contenido y opciones
**Editor: ** Tiene acceso al contenido propio y ajeno, pero no a la seccion de diseño o configuraciones “importantes”.
**Autor:** Puede crear contenido y administrarlo.
**Coolaborador:** Puede crear contenido pero no publicarlo.
**Suscriptor: ** Por defecto únicamente puede ver el contenido y comentar en el.


------------

### IMPORTANCIA DE LOS ROLES DE USUARIO

Los roles te permitirán gestionar los permisos de los usuarios dentro de tu sitio, es decir, qué puede y qué no puede hacer dentro del administrador. Estas acciones se denominan capabilities.

Esto es muy útil ya te permite segmentar las tareas de tus usuarios.  Esta práctica es muy importante para garantizar la seguridad y la estructura de nuestro sitio.

Se pueden presentar casos en los que los roles por defecto no alcancen o sean demasiado restrictivos, para eso WordPress brinda la posibilidad de crear, eliminar y modificar roles.

#### CREAR UN ROL DE USUARIO

Para crear un rol de usuario podés utilizar la función `add_role()` que nos provee WordPress, la tenés que utilizar dentro de una función y asignarla al hook init. Esto tiene que hacerse desde el archivo **`functions.php.`**



    function add_administrador_tema_role() { //nombre de nuestra función, puede ser el nombre que quieras
        add_role(
            'administrador_tema', //Nombre de role.
            'Administrador Tema', //Nombre que se visualará en la creación o página de opciones de usuarios.
           array(    
                'read' => true, //Permite el acceso al dashboard del adminitrador.
                'switch_themes' => true, //Permite el cambio de temas.
                'edit_themes'   => true, //Permite editar archivos desde el administrado de archivos del tema.
                'edit_theme_options' => true, //Permite modificar Widgets,Menús, Personalizar.
                'install_themes'    => true,  //Permite instalar temas nuevos.
                'update_themes' => true, //Permite actualizar temas instalados.
                'delete_themes' => true, //Permite eliminar temas.
    
                )   //Array con las capabilities
        );
    }
    
    //add_action(Hook, Nombre de la función)
    add_action('init', 'add_administrador_tema_role'); 

Una vez que este código esté inicializado, el usuario ya quedará creado con esa configuración. Si necesitás eliminarlo, no bastará con eliminar la función, tendrás que usar el método que veremos a continuación.

#### ELIMINAR UN ROL DE USUARIO

Para eliminar un rol de usuario podés a utilizar la función` remove_role()` y, de la misma forma que para crearlo, tenés que utilizarla dentro de una función asignada al hook init, en el archivo function.php.



    function remove_role_administrado_temas() { //Nombre de la función
        remove_role( 'administrador_tema' ); 
    }
     
    //add_action(Hook, Nombre de la función)
    add_action( 'init', 'remove_role_administrado_temas' );


#### MODIFICANDO CAPABILITIES EN ROLES

Para agregar capabilities en un role, lo primero que tenés que hacer es instanciar el role dentro de una variable conla función get_role(). Una vez hecho eso puedes utilizar los métodos add_cap() y remove_cap().

En el siguiente ejemplo se le dará al role de usuario subscriptor el permiso para editar posts (entradas de blog, custom post type).




    function add_cap_subscriber(){ //Nombre de la función
        $role = get_role( 'subscriber' ); //Instaciamos el role en la variable $role
        $role->add_cap( 'edit_posts'); //Agregamos la cabability usando el método add_cap().
    }
    
    //add_action(Hook, Nombre de la función)
    add_action( 'init', 'add_cap_subscriber');



    Function remove_cap_editor(){ //Nombre de la función
        $role = get_role( 'editor' ); //Instaciamos el role en la variable $role
        $role->remove_cap('edit_pages'); //Removemos la cabability usando el método remove_cap().
    }
    
    //add_action(Hook, Nombre de la función)
    add_action( 'init', 'remove_cap_editor');
    
Podés ver la lista completa de capabilities por roles en la documentación oficial de WordPress, haciendo [clic aquí.](https://wordpress.org/support/article/roles-and-capabilities/#administrator "clic aquí.")


## ARMAR ESTRUCTURA DEL THEME

### NUESTRO PRIMER THEME

Llegar a la carpeta themes. Crear nueva carpeta con el nuevo nombre del tema y abrir folder en tu editor de texto preferido.

crear archivos: 
- index.php
- style.css

Insertar en style.css: 


```
/*
Theme name: Alejandro Theme
Version: 1.0
Description: sitio para catálogo de platzi
Author: Alejandro Vera
Authon URI: https://github.com/alejandroverita
License: GNU General Public Licence v2 or later
License: http://www.gnu.org/licenses/gpl-2.0.html

*/
```


Crear archivo header.php e insertar:


```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <?php wp_head() ?>
</head>
<body>
```

Crear archivo footer.php e insertar codigo:


```
<?php wp_footer() ?>

    
</body>
</html>
```


En el index.php insertar:

```
<?php get_header(); ?>

<?php get_footer(); ?>
```


Hasta este paso deberia poderse ver la barra de navegacion de wordpress, sin embargo el title todavia tiene problemas 

Crear nuevo archivo functions.php e insertar: 


```
<? php 

function init_template(){

    add_theme_support( 'post-thumbnails');
    add_theme_support('title-tag');


}

add_action('after_setup_theme', 'init_template')//recibe 2 argumentos: 1 la direction. 2 nombre de la function

```

Añadir imagen al tema guardando el jpg/png en la misma carpeta

Recomendacion: 
[Wordpress Snnipet](https://marketplace.visualstudio.com/items?itemName=wordpresstoolbox.wordpress-toolbox)


------------

### MANEJO DE LIBRERIAS

En archivo functions.php seguir escribiendo:



    function assets(){
        wp_register_style('bootstrap', 'https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css', '', '4.4.1', 'all'); /* 5 argumentos: la referencia, el enlace, dependencias, version, dispositivos  */
        wp_register_style('montserrat', 'https://fonts.googleapis.com/css2?family=Roboto&display=swap', '', '1.0', 'all'); /* nombre, enlace, dependencia, version, dispositivos */
        
        wp_enqueue_style('styles', get_stylesheet_uri(), array('bootstrap', 'montserrat'), '1.0', 'all');
    }
    
    add_action('wp_enqueue_scripts', 'assets');
	

Codigo entero functions.php:



    <?php 
    
    function init_template(){
        add_theme_support('post-thumbnails');
        add_theme_support('title-tag');
    }
    add_action('after_setup_theme', 'init_template'); 
    
    function assets(){
        wp_register_style('bootstrap', 'https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css', '', '4.4.1', 'all');
        wp_register_style('montserrat', 'https://fonts.googleapis.com/css2?family=Roboto&display=swap', '', '1.0', 'all');
        
        wp_enqueue_style('styles', get_stylesheet_uri(), array('bootstrap', 'montserrat'), '1.0', 'all');
    }
    
    add_action('wp_enqueue_scripts', 'assets');
    
	

------------


### AGREGANDO JAVASCRIPT

Agregar a archivo functions.php:


```
wp_register_script('popper','https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js','','1.16.0', true);
    wp_enqueue_script('boostraps', 'https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js', array('jquery','popper'),'4.4.1', true);

    wp_enqueue_script('custom', get_template_directory_uri().'/assets/js/custom.js', '', '1.0', true);
```


Crear en la  carpeta assets>js el archivo custom.js


```
console.log('Hola WordPress');
```


Agregar una imagen en la carpeta img

Ir al header.php y agregar:


```
<header>
    <div class="container">
        <div class="row">
            <div class="col-4">
                 <img src="<?php echo get_template_directory_uri()?>/assets/img/logo.png" alt="logo">
            </div>
        </div>
    </div>
</header>
```



------------

### INSTALAR TEMAS EN WORDPRESS

Tres formas diferentes. 
- Desde el repositorio oficial de wordpres.org 
- Mediante un archivo .zip 
- Manualmente copiando los archivos en la carpeta correspondiente.


------------



[========]

## CONSTRUIR VISTAS

### GENERANDO EL MENU

Agregar al style.css

```
a,h1,h2,h3,h4,li,p,span,ul{font-family:Montserrat}.attachment-large{max-width:100%;height:auto!important}

h1{margin:50px 0;font-weight: 900;}

ul{margin-bottom: 0px;}

header{background-color:#1c3643}

header nav li{list-style:none;display:inline-block;padding:0 15px}

header nav li a{color:#fff;text-transform:uppercase}

header nav li a:hover{color:#fff}

footer{background-color:#1c3643;padding:10px 0}

footer{color:white}

footer p{margin:0;color:#fff}.lista-productos 

h2{font-weight:900}.lista-productos 

h4{font-weight:400}.lista-productos 

h4 a{color:#000}
```

agregar en functions.php debajo de add_theme_support('title-tag');:

```
register_nav_menus( 
        array (
            'top_menu' => 'Menu Principal'
        )
    );
```

Actualizar el administrador y entrar en el menu
Crear menu
Añadir elementos
Activar check de Menu Principal
Guardar

Agregar al header.php

```
 <div class="col-8">
    <nav>
    <?php wp_nav_menu (
            array(
                'theme_location' => 'top_menu',
                'menu_class' => 'menu-principal',
                'container_class' => 'container-menu',
        )
    ); 
    ?>
    </nav>
  </div>
```


------------

### QUE ES UN WIDGET


En WP, es un componente que nos permite mostrar nuestro contenido de diferentes formas. Este contenido lo va a mostrar en diferentes zonas o lugares (como la barra lateral o el pie de página) llamados ‘Sidebar’. Este se puede generar en cualquier parte de nuestro código.

😀 Una vez que WP reconozca nuestro Sidebar, nos los va a mostrar en el navegador y ahí podremos arrastrar el tipo de contenido que queremos mostrar.

Hoy en día ya no se usan mucho, pero es una herramienta que podemos aprovechar.

------------



### USANDO WIDGETS

```
//Ir al archivo functions.php

function sidebar() { /* sidebar son los lugares donde se encuentran los widgets */
    register_sidebar(  /* funcion predefinida de wordpress */
        array (
            'name' => 'Pie de página',
            'id' => 'footer',
            'description' => '<Zona de widgets para pie de pagina',
            'before_title' => '<p>',
            'after_title' => '</p>',
            'before_widget' => '<div id="%1$s" class="%2$s">',
            'after_widget' => '</div>',
        )
        );

}

/* loop de wordpress */

add_action('widgets_init', 'sidebar');


/* 
Refrescar
Entrar en la seccion de widgets
Arrastrar texto a la zona Pie de Pagina
Agregar un titulo y description
Ir al footer.php

*/
```



```
<footer>
    <div class="container">
        <?php dynamic_sidebar( 'footer'); ?>
    </div>
</footer>
```




------------

### QUE ES UN POST-TYPE

Wordpress tiene muchos tipos de diferentes de contenido, a cada uno de estos tipos se los llama Post Type (Tipo de contenido).

PostType por defecto:

- **Entradas** (Post)
- **Páginas **(Page)
- **Archivos multimedia **(Attachment)
- **Menús **(Navigation Menus)

Custom Post Type
Si bien tenemos varios tipos de contenido por defecto en WordPress, podemos crear tipos de contenido que se adapten a nuestro proyecto. A estos se les llaman Custom Post Type. Ejempo: Post Type Libros, Discos, Clientes…


------------



### ¿QUÉ ES UN LOOP PARA WORDPRESS?

Un Loop en WP es una herramienta que nos permite mostrar el contenido que tenemos guardado en nuestro Administrador. Este contenido es mostrado cuando alguien ingresa a nuestra página y ejecuta este loop.

#### Tipos de loop

**Básico**
Este es el que se ejecuta por defecto en nuestra página de vista page.php. Y se encarga de ejecutar en los archivos designados a sus respectivos post type.

**Personalizado**
Utilizando el objeto WP_Query de WP para personalizar consultas.


------------

### PAGES

En el administrador de Wordpress
Pagina>Añadir Nueva>Vista page.php > Agregar descripcion> Publicar.

En el editor de codigo:

Crear page.php>



```
<!-- Lista nueva que encabezara wordpress -->

<?php get_header(); ?>

<!-- traer el contenido de nuestra pagina -->

<main class="container">
    <!-- Genera el loop -->
    <?php if (have_posts()) {
        /* <!-- evalua si hay contenido o no --> */
        while(have_posts(  )){
            the_post(); ?>
            <!-- retorna el titulo de la pagina y lo imprime -->
            <h1 class="my-3"><?php the_title(); ?></h1>

            <!-- muestra el contenido -->
            <?php the_content(); ?>

        <?php }
    }?>
</main>

<?php get_footer(); ?>
```

Guardar y visitar

------------

### POST

Crear archivo single.php



```
<?php get_header(); ?>

<!-- crear un loop basico -->

<main class="container my-3">
    <?php if(have_posts()) {
        while(have_posts()) {
            the_post();
        ?>

            <h1 class='my-3'>
                <?php the_title() ?>
            </h1>
            <div class="row">
            
                <div class="col-6">
                    <?php the_post_thumbnail( 'large');?>
                </div>
                <div class="col-6">
                    <?php the_content(); ?>
                </div>
            
            </div>
        <?php
        }
    } ?>

</main>

<?php get_footer (); ?>
```

Añadir una entrada > anadir title y añadir description>añadir imagen destacada> Deshabilitar comentarios y pingbacks> actualizar

Ir a enlaces permamentes y seleccionar la opcion nombre dela entrada> guardar>Refrescar entrada con nueva url amigable

------------


Paginas > Añadir nueva > Añadir titulo > Añadir un bloque nuevo > Insertar una nueva imagen de portada > Tamaño de la imagen: completo > Publicar

Ajustes>Lectura > Elegir una pagina estatica de portada > Seleccionar una > Guardar 

Crear archivo front-page.php


```
<?php get_header(); ?>
<!-- Inicializar un loop -->
<main class='container'>
    <?php if(have_posts()){
        /* para saber si tenemos informacion que mostrar en nuestro index */
            while(have_posts()){
                the_post(); ?>
            <h1 class='my-3'><?php the_title(); ?>!!</h1>
            <?php the_content(); ?>

        <?php    }
    }?>
</main>

<?php get_footer(); ?>
```

------------


### COMO GENERAR UN CUSTOM POST TYPE

Archivo functions.php


    function productos_type(){
        $labels = array(
            'name' => 'Productos',
            'singular_name' => 'Producto',
            'manu_name' => 'Productos',
        );
    
        $args = array(
            'label'  => 'Productos', 
            'description' => 'Productos de Platzi',
            'labels'       => $labels,
            'supports'   => array('title','editor','thumbnail', 'revisions'),
            'public'    => true,
            'show_in_menu' => true,
            'menu_position' => 5,
            'menu_icon'     => 'dashicons-cart',
            'can_export' => true,
            'publicly_queryable' => true,
            'rewrite'       => true,
            'show_in_rest' => true
    
        );    
        register_post_type('producto', $args);
    }
    
    add_action('init', 'productos_type');


Ingresar producto nuevo> Actualizar los enlaces permanentes> Agregar imagen al producto

------------


### PERSONALIZAR EL LOOP DE LA PAGINA PRINCIPAL

Añadir nuevo producto>Añadir titulo > Añadir description >Añadir imagen destacada>Publicar

Front-page.php debajo de lo que hicimos antes del cierre de la etiqueta main crear una seccion para la lista de productos


```
 <div class="lista-productos my-5">
        <h2 class='text-center'>PRODUCTOS</h2>
        <div class="row">
        <?php
        $args = array(
            'post_type' => 'producto',
            'post_per_page' => -1, 
            'order'         => 'ASC',
            'orderby'       => 'title'
        );

        $productos = new WP_Query($args);

        if($productos->have_posts()){
            while($productos->have_posts()){
                $productos->the_post();
                ?>

                <div class="col-4">
                    <figure>
                        <?php the_post_thumbnail('large'); ?>
                    </figure>
                    <h4 class='my-3 text-center'>
                        <a href="<?php the_permalink(); ?>">
                            <?php the_title();?>
                        </a>
                    </h4>
                </div>

           <?php }
        }

        ?>
      </div>
    </div>
</main>
```

------------


[========]

## EXTRA

### PLUGINS

Los plugins en Wordpress son componentes que van a ayudar a la ampliación de nuestras funcionalidades o algunas modificaciones en las vistas. Son módulos que, al ser instalados y activados, amplían las funcionalidades del código fuente de Wordpress, estos solo funcionan cuando están activos. Hay plugins gratuitos y pagos.

Recomendaciones para elegir un plugin:

• Compatibilidad: Verificar que el plugin es compatible con nuestra versión de Wordpress.
• Calificación: Verificar la calificación y los comentarios del plugin para decidir si es seguro y/o ayuda a resolver la necesidad que tengamos
• Mantenimiento: Verificar si la última actualización fue hace mucho tiempo, o si el desarrollador le da mantenimiento.
• Funcionalidad: verificar que el plugin no tenga demasiadas funciones extras a las que realmente necesitamos.
¿Dónde encuentro plugins para instalar?
• [Wordpress.com](http://wordpress.com "Wordpress.com")

------------


###  INSTALACIÓN DE PLUGINS

WordPress ofrece tres formas de instalar plugins. Por medio del repositorio oficial de wordpress.org desde el administrador, mediante un archivo .zip, y subiendo manualmente los archivos a la carpeta correspondiente.

#### Recomendaciones

**CONTACT FORM 7**
Te permite crear formularios de forma sencilla y rápida, además de darte la posibilidad de agregarle funcionalidades mediante hooks

[Link de descarga](https://wordpress.org/plugins/contact-form-7/ "Link de descarga")

**CONTACT FORM 7 DATABASE ADDON**
Este plugin es un addon para contact form 7, es decir, que amplia las capacidades de ese plugin. Su función es la de mostrar dentro del administrador de WordPress todas las consultas que se enviaron desde los formularios.

[Link de descarga](https://wordpress.org/plugins/contact-form-cfdb7/ "Link de descarga")

**WORDFENCE**
Te ayuda a proteger tu sitio funcionando como antivirus y firewall, además de notificar las vulnerabilidades que encuentre.

[Link de descarga](https://wordpress.org/plugins/wordfence/ "Link de descarga")

**YOAST SEO**
Te va a permitir optimizar el contenido de tu sitio para que sea más amigable para los buscadores. Algunas de sus funcionalidades son gestionar titles, descripciones y personalizar la metadata para redes.

[Link de descarga](https://es.wordpress.org/plugins/wordpress-seo/ "Link de descarga")


------------

### CREANDO UN PLUGIN

Nueva carpeta > wp-content > plugins > crear nueva carpeta: modo-oscuro

Por estandares se recomienda iniciar el nombre con plugin
Crear archivo plugin-modo-oscuro.php

    <?php
    
    //plugin name: modo oscuro
    
    // Description: Activa el modo oscuro en tu theme
    
    //Version: 1.0
    
    //Author: Alejandro Vera
    
    //Author URI: https://github.com/alejandroverita
    
    function estilos_plugin() {
        $estilos_url = plugin_dir_url(__FILE__);
    
        wp_enqueue_style('modo_oscuro', $estilos_url.'/assets/css/estilo.css', '', '1.0', 'all');
    }
    
    /* hook */
    
    add_action('wp_enqueue_scripts', 'estilos_plugin');

Añadir carpeta assets. Dentro añadir carpeta css agregar archivo estilo.css

    body {
    
        background-color: black !important;
    
    }
    
    p,span,h1,h2,h3,h4,a{
        color: white !important;
    }

Actualizar la pagina


------------

### PAGINA 404


Pagina 404
Crear archivo 404.php



```
<?php get_header() ?>

<main class="container">
    <div class="pagina404 my-5">
        <h1>404 PAGINA NO ENCONTRADA</h1>
        <!-- echo para que se pueda enviar -->
        <h2>Haga <a href="<?php echo home_url() ?>"> click aqui </a> para volver a la pagina principal </h2>
    </div>
</main>

<?php get_footer() ?>
```


------------

### CIERRE

Formar parte de la comunidad [Wordpress](https://make.wordpress.org/ "Wordpress")


------------


[========]

