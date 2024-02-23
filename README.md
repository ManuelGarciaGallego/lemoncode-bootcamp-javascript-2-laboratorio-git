# Laboratorio Git.

## 1. Crear un repositorio en local.

Esta es la práctica, del módulo 0, del bootcamp de lemoncode Javascript 2, llamada "Laboratorio Git".

Lo primero que haremos, será abrir la terminal de nuestro editor de código favorito, Visual Studio Code.

![inicio de Visual Studio Code.](/assets/vsc.png)

En nuestro caso al trabajar con macOS, usaremos el atajo de teclado **CTRL + `**, para abrir la terminal.

![apertura de terminal.](/assets/open_terminal.png)

Con el comando **cd**, vamos navegando hasta la carpeta en la que queremos iniciar nuestro proyecto.

![navegación por la terminal.](/assets/terminal_navigation.png)

Usando el comando **mkdir**, creamos el directorio de nuestro proyecto.

![creación del directorio del proyecto.](/assets/project_creation.png)

Y nos posicionamos en nuestro proyecto usando de nuevo el comando **cd**.

![navegación hasta el proyecto.](/assets/project_navigation.png)

Antes de iniciar nuestro proyecto en Git nos aseguramos de tener Git instalado en nuestra máquina, para ello vamos a utilizar el comando **git --version**, veremos así la versión que tenemos instalada.

![version de Git.](/assets/git_version.png)

Ahora si procedemos a iniciar nuestro proyecto en un repositorio Git en local, para ello utilizamos el comando **git init**.

![inicio del proyecto Git en local](/assets/git_init.png)

Se confirma la inicialización del proyecto en Git.

![inicializado Git.](/assets/git_initialized.png)

También podemos observar en los ficheros ocultos de la carpeta de nuestro proyecto como se ha creado el subdirectorio ".git" con la base de datos de Git en local, en este momento también se crea la rama principal del proyecto en local.

![carpeta .git.](/assets/git_folder.png)

Seguidamente abrimos nuestro proyecto en el editor de código.

![proyecto en el editor de código.](/assets/project_vsc.png)

Utilizando la interfaz gráfica del editor de código creamos el fichero "README.md" que aparece con el símbolo **U**, ("untracked"), advirtiendo que aún no ha sido agregado al repositorio local. Para añadirlo al repositorio local debemos pasar antes el fichero al estado de "staging", lo cual conseguimos con el comando **git add .**.

![archivo en estado "untracked".](/assets/untracked.png)

A continuación observamos que el archivo "README.md" a pasado a tener el símbolo **A**, ("added"), confirmando que el archivo ha pasado a estado de "staging". Si usamos el comando **git status**, vemos que en la rama principal, (en nuestro caso main), hay un fichero "README.md", preparado para ser confirmado, "comiteado", (committed), a la base de datos del repositorio local.

![git status.](/assets/git_status.png)

Llegamos a este punto, realizamos el confirmado o "comiteado" con el comando **git commit -m** + ('mensaje explicativo'), dejando un mensaje descriptivo de como queda nuestro proyecto en ese punto.

![git commit.](/assets/git_commit-m.png)

Observamos la confirmación de la realización del primer "commit" de nuestro proyecto y el fichero "README.md" vuelve a su estado inicial.

![primer-commit.](/assets/firts_commit.png)

De igual forma procedemos para añadir algo de contenido al fichero "README.md" para que cuando lo subamos al repositorio remoto visualicemos dicho contenido; usando el comando **git status**, observamos que el fichero "README.md" ha pasado a estado **M** ("modified").

![archivo "README.md" modificado](/assets/modified_README.png)

Procedemos como antes, a añadir el fichero "README.md" al repositorio local; al estar el fichero ya trackeado usamos el comando **git commit -am** + ('mensaje explicativo'), así añadimos el fichero a "staging", comiteamos los cambios y escribimos el mensaje de "commit", todo con el mismo comando.

![git commit -am](/assets/git_commit-am.png)

## 2. Subir el repositorio a GitHub.

Es momento de crear nuestro repositorio en remoto, para ello utilizaremos la plataforma Github en la cual ya estamos registrados.

![avatar Github.](/assets/github_avatar.png)

Vamos a repositorios y pinchamos en **new** para acceder a la creación de repositorios.

![nuevo repositorio](/assets/new_repository.png)

Ponemos nombre a nuestro repositorio en la nube, (en nuestro caso coincidirá con el nombre del proyecto en local); no le añadimos "README.md" ya que lo hemos añadido en nuestro repositorio en local, ni tampoco ".gitignore" ya que el proyecto es sencillo y no necesitaremos ignorar ningún archivo; lo dejaremos también como "público" para que los tutores puedan visualizarlo; creamos el repositorio pinchando en el botón **Create repository**.

![crear repositorio](/assets/create_repository.png)

Una vez creado nuestro repositorio remoto, copiamos la url del mismo con protocolo de seguridad ssh.

![url con protocolo ssh.](/assets/url_ssh.png)

De nuevo en la terminal, utilizamos ahora el comando **git remote add origin** + (url del repositorio remoto), para conectar el repositorio local y el remoto.

![conectar repositorios.](/assets/connect_repositories.png)

Con el comando **git remote -v**, comprobamos que la conexión entre repositorios es correcta, apareciendo las direcciones de carga, (push), de contenido hacia el repositorio remoto, y de descarga, (fetch), de contenido desde el repositorio remoto.

![confirmación conexión.](/assets/connection_confirmation.png)

Seguidamente, al ser los primeros cambios que vamos a subir al repositorio remoto, y encontrarse éste vacío, escribimos el comando **git push -u origin** + (nombre de la rama principal del proyecto), (en nuestro caso "main"); y subimos los cambios al repositorio remoto, enlazando la rama local con la que hay en remoto, (en caso de que no exista la crea). Además estamos indicando la rama en la que vamos a subir esos cambios, es decir la rama de trabajo.

![primer push.](/assets/first_push.png)

Así queda confirmado el primer "push" de nuestro proyecto.

![confirmado primer push.](/assets/confirmation_first_push.png)

También podemos confirmar que se han subido correctamente los cambios, actualizando el repositorio en Github y verificando que aparecen los cambios relizados.

![actualizar repositorio.](/assets/updated_repository.png)

## 3. Hacer un commit y un push.

Seguimos redactando nuestro fichero "README.md" y añadimos a nuestro proyecto la carpeta "assets" para incluir las capturas de pantalla que acompañan a la redacción.

También añadimos un fichero llamado "fichero.js", en el cual incluimos un "console.log" que más adelante modificaremos desde otra rama para crear un ejemplo de "merge".

![console.log](/assets/console_log.png)

Procederemos a continuación como hemos hecho anteriormente con el fichero "README.md"; es decir añadimos los ficheros nuevos y los que han sido modificados al estado de staging con el comando **git add .**.

También podemos hacerlo fichero a fichero con el comando **git add** + (nombre del fichero que queremos añadir a staging) y así pasar a staging un sólo fichero en concreto. En nuestro caso pasamos a staging sólo a "fichero.js", para tener un ejemplo de ello y también ser más epecífico en el mensaje de "commit".

![git add fichero.js](/assets/git_add_fichero.js.png)

Procedemos a "comitear" los cambios, (tal como describimos anteriormente con el fichero "README.md").

![commit fichero.js.](/assets/commit_fichero.js.png)

Y pasamos el fichero desde el repositorio local al repesitorio remoto usando en este caso el comando **git push** ya que antes hemos subido otros cambios en esta rama y no es el primer cambio que hacemos.

![git push.](/assets/git_push.png)

Comprobamos que aparece nuestro cambio, (fichero.js), en el repositorio en GitHub.

![fichero.js en GitHub.](/assets/fichero.js_GitHub.png)

## 4. Crear una rama.

Creamos una nueva rama llamada "development", para ello utilizamos el comando **git branch** + (nombre de la nueva rama).

![git branch.](/assets/git_brach.png)

Cambiamos a la nueva rama con el comando **git checkout** + (nombre de la rama a la que queremos cambiar).

![git checkout.](/assets/git_checkout.png)

Comprobamos, en la ejecución del comando anterior, que hemos pasado a la rama development.

![switched to branch "development".](/assets/switched.png)

Seguidamente realizamos algunos cambios en "fichero.js" de la rama "development".

![cambios en "fichero.js"](/assets/changes_fichero.js.png)

Añadimos a "staging" y hacemos "commit" de los cambios realizados en la rama "development".

![commit de "fichero.js"](/assets/commit_modified_fichero.js.png)

Subimos los cambios de la rama "development" al repositorio remoto.

![subimos la rama "development"](/assets/push_development.png)

Podemos comprobar en el repositorio remoto como ha quedado el "fichero.js" en las diferentes ramas.

![fichero.js en main](/assets/fichero.js_in_main.png)

![fichero.js en development](/assets/fichero.js_in_development.png)

## 5. Hacer un merge.

En éste último objetivo del laboratorio nos disponemos a realizar un "merge" de la rama "development" a la rama "main", para ello primero vamos a visualizar el historial de "commit" utilizando el comando **git log** al cual le añadimos algunas "flags":

- **--oneline**, para mostrar los commit en una sóla línea.
- **--decorate**, muestra los commit y ramas a los que se apunta.
- **--graph**, se muestra un ábol de commit.
- **--all**, muestra todos los commit de todas las ramas.

Así podemos ver como se organizan nuestras ramas y "commit", y observar como cambian después del "merge".

![git log](/assets/git_log.png)

Seguidamente nos posicionamos de nuevo en la rama "main" con el ya citado comando **git checkout**.

![git checkout main](/assets/git_checkout_main.png)

Una vez posicionados en nuestra rama principal, utilizamos el comando **git merge** + (nombre de la rama que queremos fusionar a la rama principal) + **-m** + ('mensaje explicativo de como queda el merge'), para realizar el "merge" de la ramar "development" a la rama "main".

![git merge development](/assets/git_merge.png)

Después de realizar el "merge", observamos que no se ha producido ningún conflicto de "merge" entre ramas. Nos disponemos ahora a visualizar de nuevo como ha quedado el historial de "commit", observando la fusión de ramas.

![git log después de merge](/assets/git_log_after_merge.png)

Realizamos "push" al repositorio remoto y actualizamos el repositorio en GitHub; como podemos observar los cambios realizado en "fichero.js" de la rama "development", ahora se ven incorporados en "fichero.js" de la rama "main", fruto del "merge" realizado.

![fichero.js en main después de merge](/assets/fichero.js_in_main_after_merge.png)

![fichero.js en development después de merge](/assets/fichero.js_in_development_after_merge.png)

Llegados a este punto podríamos borrar la rama "development" tanto del repositorio local como del remoto y así dejar nuestro proyecto más limpio, pero no lo haremos para la buena visualización del proyecto por parte de los tutores.
