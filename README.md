# Unidad 0 - Actividad 4 Uso de Git
----

## Indice

* [Configurando Git](#configurando-git)
* [Creación de proyecto y repositorio](#creacion-de-proyecto-y-repositorio)
* [Iniciando proyecto e ignorando archivos](#iniciando-proyecto-e-ignorando-archivos)
* [Trabajo con Git](#trabajo-con-git)
* [Logs de Git](#logs-de-git)
* [Ramas](#ramas)

----

### Configurando Git

Vamos a seguir configurando Git, en este ejercicio configuraremos: El **editor de comandos**, el **pager** para que nos muestre el contenido en vez de entrar al editor, el **color.status**, **color.branch**, **color.interactive** y **color.diff** :

![](Imagenes/configuracion_git_I.png)

![](Imagenes/configuracion_git_II.png)

----

### Creación de proyecto y repositorio

Lo primero es crear un nuevo repositorio público con el nombre de ***PPS-Unidad0Actividad4-Alvaro***

![](Imagenes/Creacion_repositorio_remoto.png)

Y después con linea de comandos:

![](Imagenes/comandos_basicos_iniciar_repo_local.png)

----

### Iniciando proyecto e ignorando archivos

Listamos los archivos del directorio con '*```tree -a```*'

![](Imagenes/tree-a.png)

Ahora creo el archivo ```README.md``` y agrego una descripción:

![](Imagenes/añadir_descripcion_a_readme.png)

Ahora compruebo el estado con ```git status -s``` :

![](Imagenes/git_status_modificado.png)

Veo que sale el archivo ```README.md``` modificado y en rojo porque no lo he añadido al *'staging area'*.

Ahora creo un directorio llamado Excluded para añadir en el todo lo que no sea necesario subir a Github, y creo un archivo vacio dentro, luego en el directorio principal del repositorio creo otro archivo llamado '```excluido.txt```' :

![](Imagenes/creando_archivos_para_gitignore.png)

Creo el archivo ```.gitignore``` e incluyo en el todos los archivos con extension *.txt*, y el directorio ***Excluded*** que cree anteriormente:

![](Imagenes/contenido_de_gitignore.png)

Entonces git ya no le dará seguimiento a esos archivos y directorio.

----

### Trabajo con Git

Vamos a crear un archivo llamado ***index.html*** con un 'Hola mundo' :

![](Imagenes/contenido_de_index.png)

Ahora vemos el estado de git y nos indica que esta sin seguimiendo, nos indica que hagamos ```git add```, a si que lo hacemos, luego hacemos ```git commit -m``` y volvemos a comprobar el estado, para ver que ya no nos indica que esta sin seguimiento, y por último ```git push origin main``` :

![](Imagenes/comando_status_add_index.png)

Ahora en otra pestaña del terminal ejecutamos ```php -S 0:8080``` para que cree un servidor con la página *index.html* creada anteriormente:

![](Imagenes/comando_php-S.png)

Ahora ya podemos ir al navegador y con el puerto *8080* podremos ver ejecutada nuestra pagina *index.html*:

![](Imagenes/pagina_arrancada.png)

Me creo una copia del fichero *index.html* y le llamo *index.html.save*, y modifico el *index.html*:

![](Imagenes/creando_copia_y_modificando_index.png)


Ademas compruebo con ```git diff``` las diferencias:

![](Imagenes/git_status_diff.png)

Ahora para ver la diferencia en el contenido solo hay que refrescar el navegador:

![](Imagenes/pagina_arrancada2.png)

Utilizo git restore para volver al estado anterior del index.html:

![](Imagenes/git_restore.png)

Vuelvo a refrescar el navegador para ver como ha vuelto a poner lo mismo de antes:

![](Imagenes/pagina_arrancada3.png)

Y ahora sobreescribo index.html con el contenido de la copia y confirmo los cambios, ademas hago un commit y push al repositorio remoto, y si nos vamos a Github podremos comprobar como se han reflejado los cambios en el repositorio remoto:

![](Imagenes/repositorio_remoto_con_archivos.png)

Modifico el archivo index.html desde Github y refresco el navegador:

![](Imagenes/editando_index_desde_Github.png)

![](Imagenes/pagina_arrancada4.png)

----

### Logs de Git

Ahora vamos a comprobar los logs:

![](Imagenes/mostrando_logs.png)

Le añadimos el modificador para que sean solo los últimos 3 commits:

![](Imagenes/mostrando_3_ultimos_logs.png)

Ahora con el modificador ```--pretty=oneline``` para que se muestre en una sola linea:

![](Imagenes/logs_pretty_oneline.png)

Ahora quiero que se vean las diferencias de los últimos 2 commits para ello utilizo ```git log -p -2```:

![](Imagenes/logs_diferencias.png)

Ahora los logs del último día:

![](Imagenes/logs_ultimo_dia.png)

----

### Ramas

Primero vamos a listar las ramas existentes:

![](Imagenes/listar_ramas.png)

Ahora voy a crear una nueva rama llamada Vers1 con el contenido de la rama actual y me muevo directamente a ella:

![](Imagenes/creando_rama_vers1.png)

Y ya por último modifico el contenido de index.html, y hago un push a la rama Vers1, entonces si vamos a Github podemos comprobar que el index.html de la rama main es diferente al de la rama Vers1.