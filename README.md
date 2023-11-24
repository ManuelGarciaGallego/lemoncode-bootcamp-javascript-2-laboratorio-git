# Laboratorio Git.

Esta es la práctica del módulo 0 del bootcamp de lemoncode "Javascript 2", llamado laboratorio Git.

Lo primero que haremos será abrir el terminal, en nuestro caso trabajaremos con la terminal de nuestro editor de código preferido, visual studio code.

![Inicio vsc.](/assets/inicio-vsc.png)

En nuestro caso al trabajar con mac usaremos el atajo de teclado **CTRL + `** para abrir el terminal.

![Apertura de terminal.](/assets/apertura-terminal.png)

Con el comando **cd** vamos navegando hasta la carpeta en la que queremos iniciar nuestro proyecto.

![Navegación por el terminal.](/assets/navegacion-terminal.png)

Usando el comando **mkdir** creamos el directorio de nuestro proyecto.

![Creación del directorio del proyecto.](/assets/creacion-proyecto.png)

Y nos posicionamos en nuestro proyecto usando de nuevo el comando **cd**.

![Navegación hasta el proyecto.](/assets/navegacion-proyecto.png)

Antes de iniciar nuestro proyecto en Git nos aseguramos de tener Git instalado en nuestra máqu¡na, para ello vamos a utilizar el comando **git --version**, veremos así la versión que tenemos instalada.

![Verion de git instalada.](/assets/version-git.png)

Ahora si procedemos a iniciar nuestro proyecto en un repositorio Git en local, para ello utilizamos el comando **git init**.

![Inicio del proyecto Git en local](/assets/git-init.png)

Se confirma la inicialización en Git.

![Inicializado Git.](/assets/inicializado-git.png)

También podemos observar en los ficheros ocultos de nuestro proyecto como se ha creado el subdirectorio .git con la base de datos de Git en local; en este momento también se crea la rama principal del proyecto.

![Carpeta .git.](/assets/carpeta-git.png)

Seguidamente abrimos nuestro proyecto en el editor de código.

![Proyecto en el editor de código.](/assets/proyecto-en-editor.png)

Utilizando la interfaz gráfica del editor de código creamos el archivo readme.md que aparece con el símbolo **U** de untracked, advirtiendo que aún no ha sido agregado al repositorio local. Para añadirlo al repositorio local debemos pasar antes el archivo al estado de staging lo cual conseguimos con el comando **git add .** .

![Archivo en estado "untracked".](/assets/untracked.png)

A continuación observamos que el archivo readme.md a pasado a tener el símbolo **A** de added, confirmando que el archivo ha pasado a estado de staging. Si usamos el comando **git status** vemos que en la rama principal, (en nuestro caso main), hay un archivo (readme.md), preparado para ser confirmado "comiteado", (committed), a la base de datos del repositorio local.

![Git status.](/assets/git-status.png)

Llegamos a este punto, realizamos el confirmado o "comiteado" con el comando **git commit -m 'MensajeExplicativo'** dejando un mensaje descriptivo de como queda nuestro proyecto en ese punto.

![Git commit.](/assets/git-commit.png)

Observamos la confirmación de que se ha realizado el primer "commit" de nuestro proyecto y el archivo README.md vuelve a su estado inicial.

![Primer-commit.](/assets/primer-commit.png)

Es momento de crear nuestro repositorio en remoto, para ello utilizaremos la plataforma Github en la cual ya estamos registrados.

![Avatar Github.](/assets/avartar-github.png)

Vamos a nuestros repositorios y pinchamos en **new** para acceder a la creación de repositorios.

![Nuevo repositorio](/assets/new-repository.png)

Ponemos nombre a nuestro repositorio en la nube, no añadimos en nuestro caso README.md ya que lo hemos añadido en nuestro repositorio en local y dejamos como público para que los tutores puedan visualizarlo; creamos el repositorio pinchando en el botón **create repository**.

![Crear repositorio](/assets/create-repository.png)

Una vez creado nuestro repositorio remoto copiamos, la url del mismo con protocolo de seguridad ssh.

![Url con protocolo ssh.](/assets/url-ssh.png)

De nuevo en la terminal utilizamos el comando **git remote add origin UrlDelRepositorioRemoto** para conectar el repositorio local y el remoto.

![Conectar repositorios.](/assets/conectar-repositorios.png)

Con el comando **git remote -v**, comprobamos que la conexión entre repositorios es correcta, apareciendo las direcciones de carga (push) de contenido hacia el repositorio remoto, y de descarga (fetch) de contenido desde el repositorio remoto.

![Confirmación conexión.](/assets/comfirmacion-conexion.png)

Seguidamente, al ser el primer cambio que vamos a subir al repositorio remoto, y encontrarse éste vacío, escribimos el comando **git push -u origin NombreDeLaRamaDelProyecto**, (en nuestro caso "main"), subimos los cambios al repositorio remoto, enlazando la rama local con la que hay en remoto, (en caso de que no exista la crea). Y además indicamos la rama en la que vamos a subir esos cambios, es decir la rama de trabajo.

![Primer push.](/assets/primer-push.png)

Así queda confirmado el primer "push" de nuestro proyecto.

![Comfirmado primer push.](/assets/confirmado-primer-push.png)

También podemos confirmar que se han subido correctamente los cambios, actualizando el repositorio en Github y verificando que aparecen los cambios relizados.

![Actualizar-repositorio](/assets/actualizar-repositorio.png)

Seguimos redactando nuestro proyecto en formato Markdown en el fichero 'README.md' y añadimos la carpeta 'assets' para incluir capturas de pantalla para acompañar la redacción.

También añadimos un fichero llamado 'fichero.js', en el cual incluimos un 'console.log' que más adelante modificaremos desde otra rama para crear un ejemplo de conflicto de merge.

![Console.log](/assets/console-log.png)

Procederemos a continuación como hemos hecho anteriormente con el fichero README.md; es decir añadimos los ficheros nuevos y los que han sido modificados al estado de staging con el comando **git add .**.

También podemos hacerlo fichero a fichero con el comando **git add NombreDelFicheroQueQueremosAñadir** y así pasar a staging un sólo fichero en concreto. En nuestro caso pasamos a staging sólo el fichero 'fichero.js', para tener un ejemplo de ello.

![Git add fichero.js](/assets/git-add-fichero.js.png)

Procedemos a 'comitear' los cambios.

![Commit fichero.js](/assets/commit-fichero.js.png)

Y pasamos el fichero desde el repositorio local al repesitorio remoto usando en este caso el comando **git push** ya que antes hemos subido otros cambios y este no es el primero que hacemos.

![Git push](/assets/git-push.png)

Comprobamos que aparece nuestro cambio, (fichero.js), en el repositorio en GitHub.

![Fichero.js en GitHub](/assets/fichero.js-GitHub.png)
