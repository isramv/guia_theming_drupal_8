# Organizacion de archivos.

Debido a la complejidad de los proyectos en Drupal 8 es recomendable usar SCSS y archivos separados en componentes, un componente puedes ser un `node-type`.

Ejemplo:

```
# carpeta de salida.
css/
	styles.css

# archivos a compilar
scss/
	blocks/
		_block_homepage.scss
		_block_footer.scss
	node/
		_node.scss
		_node-full.scss
	styles.scss
```
