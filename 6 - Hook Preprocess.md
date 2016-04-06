# Hook Preprocess

los preprocess sirven para anadir informacion al twig template o modificar informacion.

los preprocess tienen que ser implementados en el archivo.

```
mitema.theme
```

el hook mas util para mi es:

```
hook_preprocess(&$variables, $hook)
```

si debugues la variable `$hook` te daras una idea de los templates que estan siendo llamados en tu thema y podras implementar otros hooks mas especificos.

ejemplo:

```
hook_preprocess_page

hook_preprocess_node
```

ejemplo de preprocess:

```
mitema_preprocess_node(&$variables) {
	$variables['saludo'] = 'Hello Friend';
}
```
entonces la variable saludo estara disponible dentro del `node.html.twig`.

```
{{ saludo }}
```