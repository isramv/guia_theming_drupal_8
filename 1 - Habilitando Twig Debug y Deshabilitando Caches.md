# Habilitando Twig Debug (Forma manual).

Para habilitar la informacion de `debug` de twig sigue los siguientes pasos:

  1. Ve a `settings.php` dentro de `sites/default/settings.php`, busca y quita los comentarios de las siguientes lineas.

  	```php
  	# if (file_exists(__DIR__ . '/settings.local.php')) {
    #   include __DIR__ . '/settings.local.php';
	  # }
  	```

  2. Copia `sites/example.settings.local.php` y pega como `sites/default/settings.local.php`, modifica permisos si es necesario.

  	- Si usas la terminal cambia los permisos  `chmod 775 -Rf sites/default`


  3. Dentro del `settings.local.php` ve a la siguiente linea:

    ```
    $settings['container_yamls'][] = DRUPAL_ROOT . '/sites/development.services.yml';

    ```

    Cópiala, pega y cámbiala para añadir tu archivo local de la siguiente manera:

    ```
    $settings['container_yamls'][] = DRUPAL_ROOT . '/sites/development.services.yml';

    $settings['container_yamls'][] = DRUPAL_ROOT . '/sites/default/local.services.yml';

    ```

  4. Copia el archivo `sites/default/default.services.yml` y renómbralo `sites/default/local.services.yml`

  5. Abre `local.services.yml` cambia las siguientes configuraciones:

    ```
    [...]
    twig.config:

    [...]
        debug: true

        auto_reload: true

    [...]
        cache: false

     ```

  6. Borra caches.

# Habilitando twig debug con drupal console

Para efectos prácticos, también se puede correr un comando de [DrupalConsole](https://drupalconsole.com/ "Drupal Console").

	```
	drupal site:mode dev
	
	```

# Deshabilitando las caches por completo.

Nesecitas haber completado los pasos anteriores.

1. Abre el archivo `settings.local.php` y quita los comentarios a las siguientes lineas.

	```
	# $settings['cache']['bins']['render'] = 'cache.backend.null';

 [...]

	# $settings['cache']['bins']['dynamic_page_cache'] = 'cache.backend.null';

	```

2. Borra las caches.
