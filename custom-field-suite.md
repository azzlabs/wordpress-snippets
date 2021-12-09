# Utility custom field suite

## Shorthands per ottenere campi custom su pagina (ACF compatible)
```php
if (!function_exists('getField')) {
    function getField($field_name = false, $default_val = '<!-- Placeholder %s -->', $post_id = false, $options = [], $escape_html = false) {
        $result = CFS()->get($field_name, $post_id, $options);
        return $result == false ? $default_val : ($escape_html ? htmlentities($result) : $result);
    }

    function getFieldArray($field_name) {
        return getField($field_name, [], false, []);
    }
}
```

## Shorthand per ottenere impostazioni tema globali su pagina
```php
function getThemeOption($field_name, $default_val = false) {
    $result = cfs_get_option('nows_options', $field_name);
    return $result == false ? $default_val : $result;
}
```

## Pagine opzioni CFS
```php
include('inc/cfs-options-pages.php');
    function nows_cfs_options_screens( $screens ) {
        $screens[] = array(
            'name'            => 'nows_options',
            'menu_title'      => __('Opzioni tema'),
            'page_title'      => __('Opzioni del tema NowSocial'),
            'menu_position'   => 100,
            'icon'            => 'dashicons-admin-generic',
            'field_groups'    => array('Opzioni tema'), // Field Group name(s) of CFS Field Group to use on this page (can also be post IDs)
        );
    
        return $screens;
    }
    add_filter('cfs_options_screens', 'nows_cfs_options_screens');
 ```
