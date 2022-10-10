# Sistemas de control de versiones

## Contenidos

- [Sistemas de control de versiones](#sistemas-de-control-de-versiones-1)
- [Git](#git)
    - [Comandos básicos de Git](#comandos-básicos-de-git)
    - [Git avanzado](#git-avanzado)
    - [GitFlow](#gitflow)
    - [GitHub](#github)

## Sistemas de control de versiones

Los **sistemas de control de versiones** permiten guardar un registro de las modificaciones sobre un conjunto de ficheros a lo largo del tiempo, así como regresar a una versión anterior de los mismos.

Los sistemas de control de versiones hacen posibles las siguientes acciones:

- **Resolución** de conflictos: ayudan a resolver conflictos por cambios simultáneos entre desarrolladores.
- **Revertir** los cambios: permiten deshacer rápidamente a una versión estable conocida.
- **Guardar** una copia de seguridad: conservan una copia externa del código fuente.

Existen varios VCS, siendo estos los más populares:

- **Git**: uno de los mejores VCS y el más utilizado. Es compatible con muchos protocolos y maneja eficientemente todo tipo de proyectos. Permite crear copias locales del proyecto.
- **CVS**: sistema de repositorios cliente-servidor que mantiene actualizado el proyecto mientras se trabaja en paralelo.
- **Subversion** (SVN): repositorios cliente-servidor centralizados. Todos los directorios están versionados.
- **Mercurial**: VCS escrito en Python con alto rendimiento y escalabilidad. Tiene su propia interfaz web para manejar los repositorios.
- **Monotone**: escrito en C++, soporta muchos sistemas operativos y tiene su propio protocolo.

La terminología clave para comprender los VCS es la siguiente:

- **Repositorio**: lugar donde se almacenan los datos actualizados y el historial de cambios. Puede ser local o remoto.
- **Módulo**: conjunto de directorios y archivos que pertenecen a un mismo proyecto.
- **Revisión**: versión determinada del proyecto que se gestiona. Estas versiones se pueden etiquetar. La última revisión se suele llamar "_HEAD_".
- **Etiqueta** (_Tag_): nombre especial que se le puede dar a una versión para identificarla posteriormente. El módulo se "congela" (se mantiene en el historial permanentemente) durante el rotulado para imponer una versión coherente.
- **Baseline**: revisión aprobada de un fichero a partir del cual se pueden realizar nuevos cambios.
- **Rama** (_Branch_): un módulo se puede bifurcar en un momento determinado desde el cual se tienen dos copias independientes, permitiendo realizar cambios sobre una copia y después añadirlos a la rama principal.
- **Checkout**: copia local desde el repositorio.
- **Commit**: copia en el repositorio del proyecto local.
- **Conflicto**: ocurre cuando el sistema no puede manejar los cambios realizados por dos o más usuarios en el mismo archivo.
- **Resolver**: intervención del usuario para atender un conflicto.
- **Cambio** (_Change_): modificación específica a un archivo.
- **Lista de cambios** (_Changelist_): lista de los cambios incluidos en un único commit. También es una vista secuencial del código fuente.
- **Export**: similar a un checkout pero sin metadatos de control de versiones (el proyecto queda limpio). Se usa antes de publicar los contenidos.
- **Import**: copia de los datos en el repositorio por primera vez.
- **Fusión** (_Merge_): fusión de dos conjuntos de cambios sobre uno o más ficheros en uno solo. Pueden producir conflictos.
- **Merge inverso**: fundir ramas de diferentes equipos en el trunk principal del sistema de versiones.
- **Sync o update**: integra los cambios del repositorio en la copia local.
- **Workspace**: copia local del repositorio en un momento o revisión específico.
- **Congelar**: permitir los últimos commits para solucionar fallos a resolver en una entrega y suspender cualquier otro cambio.

## Git

Git es un sistema de control de versiones muy común creado por Linus Torvalds. Presenta las siguientes características:

- Sistema distribuido de control de versiones.
- Sistema muy potente.
- No depende de un repositorio central.
- Es software libre.
- Guarda un historial de revisiones completo.
- Trabaja con distintas ramas de código y permite fusionarlas ágilmente.
- Gestión distribuida, los cambios se importan como ramas adicionales que se fusionan igual que en la rama local.

Git maneja sus datos como un conjunto de instantáneas. Si un fichero no ha sido modificado no lo vuelve a almacenar, sino que guarda una referencia al archivo anterior que ya tiene almacenado.

Los archivos tienen tres estados: _committed_, _modified_ y _staged_.

- **_Committed_**: los datos están almacenados en el repositorio local.
- **_Modified_**: el archivo se ha modificado pero no se ha guardado en el repositorio local.
- **_Staged_**: el archivo está marcado para ser guardado en el siguiente _commit_.

De aquí salen las tres secciones principales de git:

- **Git directory** (repositorio local): almacena los metadatos del VCS y la base de datos de objetos del proyecto. Es la parte más importante.
- **Working directory** (directorio de trabajo): copia de una revisión. Se obtiene de la base de datos del repositorio local y se coloca en disco para poder modificarlo.
- **Staging area** (área de preparación): archivo de almacenamiento que contiene lo que va a ser confirmado en el próximo _commit_.

## Comandos básicos de Git

### **Crear un repositorio**
> `git init <nombre>`

Crea una carpeta con el nombre del repositorio. Contiene la carpeta .git donde se registran los cambios.

### **Clonar un repositorio**
> `git clone <url>`

Crea una copia local independiente del repositorio.

### **Estado del repositorio**
> `git status`

Muestra el estado de los cambios desde la última versión guardada. Compara el workspace con el último commit.

### **Añadir a stage**
> `git add <fichero/directorio>`

Añade/actualiza los cambios en el fichero/directorio al staging area.

> `git add .`

Añade todos los ficheros del working directory al staging area.

### **Eliminar ficheros**
> `git rm <fichero>`

Elimina el fichero de la zona de trabajo.

> `git rm --cached <fichero>`

Elimina el fichero del staging area.

### **Mover ficheros**
> `git mv <fichero> <nuevo_fichero>`

Mueve o renombra el fichero.

### **Descartar cambios**
> `git restore <fichero>`

Elimina los cambios a un fichero en el working directory. Puede recuperar archivos borrados.

> `git restore --staged <fichero>`

Elimina los cambios a un fichero en el staging area.

### **Añadir cambios al repositorio**
> `git commit -m "mensaje"`

Confirma todos los cambios del staging area y los añade al repositorio local. Se debe añadir un mensaje para describir los cambios introducidos.

> `git commit --amend -m "mensaje"`

Cambia el mensaje del último commit.

### **Historial de versiones**
> `git log`

Muestra el historial de commits de un repositorio por orden cronológico.

### **Información sobre un commit**
> `git show <commit>`

Muestra toda la información sobre el commit indicado (por defecto se muestra el último commit).

### **Información de un fichero**
> `git blame <fichero>`

Muestra el contenido de un fichero anotando cada línea con información del commit en el que se introdujo.

### **Mostrar diferencias en ficheros**
> `git diff`

Muestra las diferencias entre el workspace y el staging area.

> `git diff --cached`

Muestra las diferencias entre el staging area y el último commit.

> `git diff HEAD`

Muestra las diferencias entre el workspace y el último commit.

### **Volver a una versión anterior del workspace**
> `git checkout <commit> <fichero>`

Cambia un archivo por la versión guardada en el repositorio local y crea una rama desde el commit.

### **Eliminar cambios del staging area**
> `git reset <fichero>`

Elimina los cambios del staging area en un archivo, pero no toca el workspace.

### **Eliminar cambios de un commit**
> `git reset --hard <commit>`

Elimina todos los cambios posteriores al commit elegido y actualiza el workspace a esa versión.

> `git revert <fichero>`

Crea un nuevo commit que deshace los cambios del commit anterior.

### **Combinar commits**
> `git rebase -i <hash/HEAD>`

Combina los commits especificados en uno solo.

### **Ignorar ficheros**
> Fichero .gitignore

Los archivos o directorios que aparezcan en el .gitignore no serán registrados por Git. La utilidad _gitignore generator_ genera .gitignore para IDEs o lenguajes específicos de forma sencilla.

### **Etiquetar commits**
> `git tag -a <tag> -m <"mensaje">`

Crea una etiqueta para diferenciar un commit en específico.

### **Alias**
> Fichero de configuración de Git

Git permite crear comandos personalizados que realicen un comando más largo escribiendo menos. Para ello, se debe añadir al fichero de configuración de Git la siguiente línea: `git config --global alias.[comando] [comando original]`

### **Arreglar último commit (no publicado)**
> `git add <fichero>`  
> `git commit --amend -m "mensaje"`

De acuerdo a este ejemplo, se puede modificar el contenido de un commit (siempre y cuando no se haya subido el cambio a un repositorio remoto).

### **Deshacer último commit (no publicado)**
> `git reset --soft HEAD~1`

Este comando hace que la rama actual retroceda al commit especificado. `HEAD~1` hace referencia al penúltimo commit de la rama activa. `--soft` permite conservar los cambios en el staging area sin tocar el workspace.

> `git reset --hard HEAD~1`

En este caso no se conservan los cambios del commit eliminado, y el workspace y el staging area se sobrescriben con los del commit especificado.

## Git avanzado

Inicialmente cualquier repositorio tiene una rama "_main_" (o "_master_") donde se van sucediendo los commits de forma lineal.

Cada rama tiene un _head_ independiente que apunta al último commit realizado en esa rama. El "_head_ activo" indica el _head_ de la rama donde se ha hecho el último commit.

### **Mostrar ramas**
> `git branch`

Muestra todas las ramas existentes en el repositorio.

### **Mostrar historia con ramas**
> `git log --graph --oneline`

Muestra la historia de todas las ramas en forma de grafo. Este comando se puede acortar creando un alias `git tree`.

### **Cambiar de rama**
> `git checkout <rama>`

Actualiza los ficheros del workspace a la última versión del repositorio y el head activo pasa a apuntar al último commit de la rama.

### **Crear rama**
> `git branch <rama>`

Crea una rama con el nombre especificado a partir del último commit.

> `git checkout -b <rama>`

Crea una rama y después la marca como activa.

### **Eliminar rama**
> `git branch -d <rama>`

Elimina una rama si ha sido fusionada previamente, lanzando una advertencia en caso contrario.

> `git branch -D <rama>`

Elimina una rama incluso si no ha sido fusionada, perdiendo así los cambios.

### **Fusionar ramas**
> `git merge <rama>`

Fusiona la rama indicada en la rama actual, creando un commit nuevo con los cambios o trasladando el historial de la rama original a la rama destino (_fast forward_).

Para fusionar dos ramas es necesario que no haya conflictos entre ellas. En caso de haberlos, deberán ser resueltos manualmente. Git añade marcadores a los archivos a corregir.

### **Reorganización de ramas**

`git rebase <rama-1> <rama-2>`

Replica los cambios de la rama 1 en la rama 2 a partir de un commit común creando un historial único en la rama 2. Esto es lo que sucede durante un fast forward.

### **Cherry Pick**

`git cherry-pick`

Coge un commit determinado y lo coloca como head. Es una herramienta muy potente pero se debe tener cuidado.

### **Arreglar commit en rama incorrecta**

Pasar commit a la rama correcta
```
git checkout <rama_correcta>
git cherry-pick <commit_id>
```

Limpiar la otra rama
```
git checkout <rama_incorrecta>
git reset --hard HEAD~1
```

## GitFlow

GitFlow es una idea abstracta de un flujo de trabajo en Git. Establece una estructura de ramas que se deben crear y cómo se relacionan entre ellas.

Para registrar el historial del proyecto, GitFlow usa dos ramas, la **rama maestra** y la **rama de desarrollo**. La primera representa la rama de publicación oficial, mientras que la segunda es la que integra las nuevas funciones.

Cada nueva función debe estar en su propia rama, que ramifica de la rama de desarrollo y vuelve a fusionarse con ella cuando se termina de desarrollar la función.

Una vez el desarrollo está listo para ser publicado, se crea una rama de publicación en la que no se añaden nuevas funciones, sino que se corrigen errores y se genera documentación. Una vez termina este proceso, la rama se fusiona con la rama maestra y se etiqueta con un número de versión. Además se vuelve a fusionar con la rama de desarrollo para incluir todos los cambios de la publicación.

Existen ramas de mantenimiento o corrección que sirven para reparar rápidamente las publicaciones de producción. Se basan en la rama maestra en lugar de la de producción, y se vuelve a fusionar con la rama maestra (con un número de versión actualizado) y la rama de desarrollo.

## GitHub

GitHub es una plataforma para trabajar con repositorios remotos. Git tiene comandos para publicar los repositorios locales en repositorios remotos.

### **Clonación de repositorios**
> `git clone <url>`

Descarga una copia del repositorio remoto en el directorio actual.

> `git clone --depth 1 <url>`

Crea una copia con el historial truncado al último commit.

### **Añadir un repositorio remoto**
> `git remote add origin <url>`

Asocia un repositorio remoto al repositorio local. Los cambios se publican al repositorio remoto indicado (_origin_).

### **Lista de repositorios remotos**
> `git remote`

Muestra una lista con los repositorios remotos asociados al repositorio local.

> `git remote -v`

Muestra las URL independientes de cada repositorio remoto.

### **Descargar cambios de un repositorio remoto**
> `git pull <remoto> <rama>`

Descarga los cambios del repositorio remoto y la rama especificados y los integra en el repositorio local. Por defecto descarga todo el repositorio.

### **Enviar cambios a un repositorio remoto**
> `git push <remoto> <rama>`

Envía los cambios de la rama especificada al remoto. Por defecto envía todo el repositorio.

### **Eliminar un repositorio remoto**
> `git remote remove <remoto>`

Desenlaza el repositorio local con el remoto especificado.

## Colaborar con GitHub

Existen dos formas de colaborar en GitHub:

- Ser colaborador del repositorio (control total sobre el proyecto).
- Replicar el proyecto y solicitar integración de cambios (pull request).

El segundo método es el más común, ya que no permite subir contenido sin autorización y proporciona más control sobre los cambios añadidos.

Para hacer un pull request se sigue una serie de pasos:

- Crear un _fork_ del repositorio (copiar el repositorio).
- Clonar el repositorio para trabajar sobre él.
- Crear una rama para añadir los cambios.
- Añadir y confirmar los cambios en la rama creada.
- Enviar los cambios a GitHub.
- Crear un pull request en el repositorio original.