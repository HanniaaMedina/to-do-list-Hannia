# Aplicación de to do list en Python/Flask con login de usuario 

Una aplicación full-stack que utiliza el framework Flask de Python. Una vez autenticados podemos entrar a una vista desde la que podemos gestionar una lista de tareas (listar, actualizar y eliminar). Las peticiones al backend son controladas por [</>htmx](https://htmx.org/) ([hypermedia](https://hypermedia.systems/) solamente).

### como funciona

La aplicación nos permite realizar un CRUD completo sobre la base de datos, en este caso SQLite3, pero el ORM de Flask (Flask-SQLAlchemy) nos permite utilizar cualquier base de datos SQL.

La BD almacena tanto una tabla con los usuarios como otra tabla para las tareas de cada usuario. Ambas tablas están relacionadas mediante una clave foránea.

El uso de </>html permite un comportamiento similar al de una SPA, sin recargas de página al cambiar de una ruta a otra o al realizar peticiones al backend.

Por otro lado, el estilizado de las vistas se consigue a través de Tailwind CSS y DaisyUI que se obtienen de sus respectivos CDN.

## uso:

Como requisito previo, debemos tener Python instalado en nuestra máquina, además de las librerías que en nuestro sistema operativo nos permitan crear un entorno virtual para la instalación de las dependencias requeridas.

Para activar el entorno virtual (En Unix/MacOS o Windows):


tu@usuario:~/ruta/a/la/aplicación/flask-htmx-todolist$ source .venv/bin/activate # En Windows, ejecuta: .venv\Scripts\activate


Para instalar las dependencias:
(.venv) tu@usuario:~/ruta/a/la/aplicación/flask-htmx-todolist$ pip install -r requirements.txt

Para iniciar la aplicación en modo desarrollo:
$ python3 run.py # En Windows, ejecuta: python run.py

Para ejecutar la aplicación en producción, primero tendrías que cambiar la configuración en el archivo __init__.py (pasar el atributo DEGUB = False). Luego, instala gunicorn (servidor HTTP WSGI de Python para UNIX [pip install gunicorn]) y ejecuta la aplicación con el comando:
$ gunicorn run:app
