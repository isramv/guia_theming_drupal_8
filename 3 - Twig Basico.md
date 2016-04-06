# Twig basico.

## Haz algo `{% %}`

## Imprime algo `{{ }}`

Esto es fundamental.

la documentacion oficial de twig la encuentras [aca](http://twig.sensiolabs.org/documentation)

twig y drupal [aca](https://www.drupal.org/node/2357633)

ejemplo:

**asignacion de variables**

```
{% set saludo = 'Hello Friend' %}
```

**Imprime variable**

```
{{ saludo }}
```

```
<h2>{{ saludo }}</h2>
```

## If
**equivalente a isset() en PHP**

```
{% if saludo %}
	{{ saludo }}
{% endif %}
```
**checar si un valor es nulo**

```
{% if saludo is not null %}
	{{ saludo }}
{% endif %}
```
## Filters

Para utilizar un filtro tienes que usar `|` despues de la variable y el nombre del filtro, ejemplos:

- [slides Isra](http://slides.com/isramv/ttt#/10)
- [drupal filter](https://www.drupal.org/node/2357633)

```
{{ content.field_files['#items'].getIterator() | length }}
```
esto imprimira un numero.

Drupal translate.

```
{{ label|t }}
```

and

```
{% trans %} Written by {{ label }} {% endtrans %}
```

**date**

```
{% set node_created = node.created.value %}
<div class"date">{{ node_created|date("M D Y") }}</div>
```
