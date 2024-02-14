# Laboratorio Git.

## 1. Crear un repositorio en local.

Esta es la práctica, del módulo 0, del bootcamp de lemoncode Javascript 2, llamada "Laboratorio Git".

Lo primero que haremos, será abrir la terminal de nuestro editor de código favorito, Visual Studio Code.

![Inicio vsc.](/assets/vsc.png)

En nuestro caso al trabajar con macOS, usaremos el atajo de teclado **CTRL + `**, para abrir la terminal.

![Apertura de terminal.](/assets/open-terminal.png)

Con el comando **cd**, vamos navegando hasta la carpeta en la que queremos iniciar nuestro proyecto.

![Navegación por el terminal.](/assets/terminal-navigation.png)

Usando el comando **mkdir**, creamos el directorio de nuestro proyecto.

![Creación del directorio del proyecto.](/assets/project-creation.png)

Y nos posicionamos en nuestro proyecto usando de nuevo el comando **cd**.

![Navegación hasta el proyecto.](/assets/project-navigation.png)

Antes de iniciar nuestro proyecto en Git nos aseguramos de tener Git instalado en nuestra máquina, para ello vamos a utilizar el comando **git --version**, veremos así la versión que tenemos instalada.

![Verion de git instalada.](/assets/git-version.png)

Ahora si procedemos a iniciar nuestro proyecto en un repositorio Git en local, para ello utilizamos el comando **git init**.

![Inicio del proyecto Git en local](/assets/git-init.png)

Se confirma la inicialización del proyecto en Git.

![Inicializado Git.](/assets/git-initialized.png)

También podemos observar en los ficheros ocultos de nuestro proyecto como se ha creado el subdirectorio ".git" con la base de datos de Git en local, en este momento también se crea la rama principal del proyecto en local.

![Carpeta .git.](/assets/git-folder.png)

Seguidamente abrimos nuestro proyecto en el editor de código.

![Proyecto en el editor de código.](/assets/project-in-vsc.png)

Utilizando la interfaz gráfica del editor de código creamos el archivo "README.md" que aparece con el símbolo **U**, "untracked", advirtiendo que aún no ha sido agregado al repositorio local. Para añadirlo al repositorio local debemos pasar antes el archivo al estado de "staging" lo cual conseguimos con el comando **git add .**.

![Archivo en estado "untracked".](/assets/untracked.png)

A continuación observamos que el archivo "README.md" a pasado a tener el símbolo **A**, "added", confirmando que el archivo ha pasado a estado de "staging". Si usamos el comando **git status**, vemos que en la rama principal, (en nuestro caso main), hay un archivo "README.md", preparado para ser confirmado "comiteado", (committed), a la base de datos del repositorio local.

![Git status.](/assets/git-status.png)

Llegamos a este punto, realizamos el confirmado o "comiteado" con el comando **git commit -m 'mensajeExplicativo'**, dejando un mensaje descriptivo de como queda nuestro proyecto en ese punto.

![Git commit.](/assets/git-commit-m.png)

Observamos la confirmación de la realización del primer "commit" de nuestro proyecto y el archivo "README.md" vuelve a su estado inicial.

![Primer-commit.](/assets/firts-commit.png)

De igual forma procedemos para añadir algo de contenido al archivo "README.md" para que cuando lo subamos al repositorio remoto visualicemos dicho contenido; usando el comando **git status**, observamos que el archivo "README.md" ha pasado a estado "M" (modified).

![Archivo "README.md" modificado](/assets/modified-README.md.png)

Procedemos como antes a añadir el archivo "README.md" al repositorio local, al estar el archivo ya trackeado usamos el comando **git commit -am 'mensajeExplicativo'**, así añadimos el archivo a "staging" y comiteamos los cambios, además de escribir el mensaje del "commit", todo con el mismo comando.

![Git commit -am](/assets/git-commit-am.png)
