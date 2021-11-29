# Flask
Curso de Flask
![image](https://user-images.githubusercontent.com/94714288/143951000-ca094aff-3c24-4374-b0ee-c7f06098df25.png)
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
 
 Para activar el development mode debes escribir lo siguiente en la consola:

export FLASK_ENV=development
echo $FLASK_ENV
SESSION: es un intercambio de información interactiva semipermanente, también conocido como diálogo, una conversación o un encuentro, entre dos o más dispositivos de comunicación, o entre un ordenador y usuario.

Automatiza el levantar tu entorno virtual de desarrollo (venv) con un script.

#!/bin/bash

pip install -r requierements.txt
source venv/bin/activate

export FLASK_APP=main.py
export FLASK_DEBUG=1
export FLASK_ENV=development

flask run

Crea un archivo nuevo en la raíz del proyecto y copia el script de arriba.
Guárdalo con extension .sh
Ejecútalo en consola: $ source file_name.sh
You welcome!

![image](https://user-images.githubusercontent.com/94714288/143856916-46e25265-8f83-44cf-a73a-a9e34247317a.png)

SESSION: es un intercambio de información interactiva semipermanente, también conocido como diálogo, una conversación o un encuentro, entre dos o más dispositivos de comunicación, o entre un ordenador y usuario.

<h1>Uso de método POST en Flask-WTF</h1>

Flask acepta peticiones GET por defecto y por ende no debemos declararla en nuestras rutas.

Pero cuando necesitamos hacer una petición POST al enviar un formulario debemos declararla de la siguiente manera, como en este ejemplo:

@app.route('/platzi-post', methods=['GET', 'POST'])
Debemos declararle además de la petición que queremos, GET, ya que le estamos pasando el parámetro methods para que acepte solo y únicamente las peticiones que estamos declarando.

De esta forma, al actualizar el navegador ya podremos hacer la petición POST a nuestra ruta deseada y obtener la respuesta requerida.

Nta:

GET - Es mandar la información al servidor en forma de variables a través de la url.

POST - Cuando son datos especiales que no quieres que se vean en la url, se envian a través de post, que un buen número de veces se da por medio de un formulario. Tecnicámente los datos viajan a través de los headers del protocolo http.

AJAX - Asyncronus javascript and XML. Permite actualizar el body de la página sin necesidad de redirigirme a otra url. EJ: cómo cuando agrego un comentario en facebook.

SOCKETS - Intercambio de información en tiempo real. Ej: Un juego online o un chat.

<h1>Pruebas básicas con Flask-testing</h1>

La etapa de pruebas se denomina testing y se trata de una investigación exhaustiva, no solo técnica sino también empírica, que busca reunir información objetiva sobre la calidad de un proyecto de software, por ejemplo, una aplicación móvil o un sitio web.

El objetivo del testing no solo es encontrar fallas sino también aumentar la confianza en la calidad del producto, facilitar información para la toma de decisiones y detectar oportunidades de mejora.

https://flask.palletsprojects.com/en/1.1.x/
https://flask.palletsprojects.com/en/1.1.x/tutorial/views/
https://flask-login.readthedocs.io/en/latest/
