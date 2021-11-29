# Flask
Curso de Flask
Mis notas hasta el momento:
Uso de condicionales
Ejemplo de estructura:

    {% if CONDITION %}
        <p>Bloque de contenido</p>
    {% else %}
        <p>Bloque de contenido</p>
    {% endif %}
Ejemplo de uso:

    {% if user_ip %}
        <h1>Hello World Platzi, tu IP es {{ user_ip }}</h1>
    {% else %}
        <p>No tienes una IP</p>
    {% endif %}
<h1>Uso de bucles</h1>
Una vez se envie una variable al elemento(plantilla html), es posible hacer recorridos, siguiendo la sintaxis:

    {% for ITEMS in COLECTION_ELEMENTS %}
        <p>Item</p>
    {% endfor %}
Ejemplo:

    {% for description in array_descriptions %}
        <p>{{description}}</p>
    {% endfor %}
Uso de url_for
La funcion url_for se puede utilizar para consumir archivos estaticos y redirecionar a otras páginas dentro del proyecto.

<h1>Uso archivos estativos</h1>
Se llaman a traves de la funcion url_for, tiene 2 parámetros:

1.- path = 'static’
2.- filename = [Ruta del archivo]

Ejemplo:

    <link rel="stylesheet" href="{{ url_for(path = 'static', filename = 'css/main.css')}}">
    <img src="{{url_for(path = 'static', filename = 'images/platzi.png')}}" alt="Platzi logo">
<h1>Uso de redireccionamiento a paginas</h1>
Se realiza el redirecciónamiento a traves de la funcion url_for, en el primer
atributo, se explifica el path del archivo(ruta), ejemplo:

    <li><a href="{{url_for(path = 'index')}}">Inicio</a></li>
Uso Macro(funciones en plantillas)
Para crear componentes(funciones y código) se define un tipo(macro), el nombre de la funcion y los pámetros.

<h1>Ejemplo de estructura:</h1>
    {% macro NAME_FUNCTION(PARAM_1, PARAM_2) %}
        <p>Bloque de contenido<p>
    {% endmacro %}
Ejemplo de uso:
Se define un archivo render_item_list.html

    {% macro render_item(todo) %}
        <li>Descripción: {{todo}} </li>
    {% endmacro %}
Se define un archivo home.html

    {% import 'render_item_list.html' as macros %}

    {% for description in arrDescriptions %}
        {{ macros.render_item(description) }}
    {% endfor %}
Uso de plantillas(Block)
Ejemplo de archivo padre:

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>
            {% block title %} Flask Platzi | {% endblock %}
        </title>
    </head>
    <body>
        {% block content %}
        {% endblock %}
    </body>
    </html>
Ejemplo de archivo hijo(file.html)

    {% extends './base.html' %}
    {% block title %}
        {{super()}}
        Bienvenido
    {% endblock %}

    {% block content %}
        <p>Bloque de contenido del archivo hijo </p>
    {% endblock %}
 ![image](https://user-images.githubusercontent.com/94714288/143855747-bb847ab7-3ba1-43bf-8470-106949934a3c.png)

