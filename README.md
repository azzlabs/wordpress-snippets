# Qualche snippet utile per wordpress

## Registrare e utilizzare un'area widget (sidebar)
### Registrarla nel file functions.php

```php
register_sidebar([
    'name'          => 'Nome area',
    'id'            => 'id-area',
    'before_widget' => '<div class="widgets">',
    'after_widget'  => '</div>',
    'before_title'  => '<h3>',
    'after_title'   => '</h3>',
]);
```

### Incollare questo snippet di codice dove si vuole fare apparire l'area widget
```php
<?php dynamic_sidebar('hero') ?>
```

## Registrare e utilizzare un menu
### Registrarlo nel file functions.php

```php
register_nav_menus ([
	'primary' => __('Menu principale', 'text-domain'),
	'foooter' => __('Menu footer', 'text-domain')
]);
```

### Incollare questo snippet di codice dove si vuole fare apparire l'area widget
```php
<?php wp_nav_menu(['theme_location'  => 'primary']) ?>
```
Oppure, se si vuole usare un waker personalizzato (per Bootstrap, per esempio)
```php
<?php
    wp_nav_menu([
      'theme_location'  => 'primary',
      'depth'           => 2,
      'container'       => 'div',
      'container_id'    => 'navbarNavDropdown',
      'container_class' => 'collapse navbar-collapse',
      'menu_class'      => 'nav navbar-nav ml-auto',
      'fallback_cb'     => 'WP_Bootstrap_Navwalker::fallback',
      'walker'          => new WP_Bootstrap_Navwalker()
    ]);
?>
```

## Esempio utile di loop
```php
<?php if (have_posts()): while (have_posts()): ?>
    <?php the_post(); ?>

    <h1><?php the_title(); ?></h1>
    <?php if (get_post_type() == 'post'): ?>
        <small><?php the_time('j F Y'); ?>, scritto da <?php the_author_posts_link(); ?></small>
    <?php endif; ?>

    <div class="content"><?php the_content(); ?></div>
<?php endwhile; endif; ?>
```

## Ottenere (e stampare) il titolo del sito
```php
<?= get_bloginfo('name') ?>
```

## Aggiungere un file stile css
```php
wp_enqueue_style('main', get_stylesheet_uri()); // Include il file di stile principale style.css
wp_enqueue_style('main-mobile', get_template_directory_uri() . '/assets/theme-mobile.css'); // Include un css arbitrario
```
Per gli script, esiste una funzione simile (l'array come ultimo argomento nell'esempio indica le dipendenze)
```php
wp_enqueue_script('hero', get_template_directory_uri() . '/assets/animated_hero.js', ['jquery']);
```
Asset e script vanno inseriti in una funzione enqueue, lanciata all'hook `wp_enqueue_scripts`
```php
function domain_enqueue_assets() {
    // wp_enqueue_style(...);
}
add_action('wp_enqueue_scripts', 'domain_enqueue_assets');
```

## Funzionalità tema per functions.php
Per lasciar gestire il titolo della pagina a wordpress ```add_theme_support('title-tag');```

Per poter aggiungere immagini di anteprima ai post ```add_theme_support('post-thumbnails');```

Per poter includere uno stile in TinyMCE ```add_theme_support('editor-styles');``` e relativo file CSS ```add_editor_style('style.css');```


## Metadati da inserire nel file css
```css
/*
    Theme Name: WP Sandbox
    Author: AzzLabs
    Description: Template wordpress sandbox
    Version: 1.0.0
    Text Domain: wp_sandbox
    Tags: HTML5, CSS3
*/
```

## Altre utility
### Consentire l'upload di file SVG
```php
function pre_mime_types($mimes) {
    $mimes['svg'] = 'image/svg+xml';
    return $mimes;
}
add_filter('upload_mimes', 'pre_mime_types');
```
