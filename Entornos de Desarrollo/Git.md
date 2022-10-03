# Tema de Git

## Sistemas de control de versiones

Los sistemas de control de versiones permiten guardar un registro de las modificaciones sobre un conjunto de ficheros a lo largo del tiempo, así como regresar a una versión anterior de los mismos.

Los sistemas de control de versiones hacen posibles las siguientes acciones:

- Resolución de conflictos: ayudan a resolver conflictos por cambios simultáneos entre desarrolladores.
- Revertir los cambios: permiten deshacer rápidamente a una versión estable conocida.
- Guardar una copia de seguridad: conservan una copia externa del código fuente.

Existen varios VCS, siendo estos los más populares:

- Git: uno de los mejores VCS y el más utilizado. Es compatible con muchos protocolos y maneja eficientemente todo tipo de proyectos. Permite crear copias locales del proyecto.
- CVS: sistema de repositorios cliente-servidor que mantiene actualizado el proyecto mientras se trabaja en paralelo.
- Subversion (SVN): repositorios cliente-servidor centralizados. Todos los directorios están versionados.
- Mercurial: VCS escrito en Python con alto rendimiento y escalabilidad. Tiene su propia interfaz web para manejar los repositorios.
- Monotone: escrito en C++, soporta muchos sistemas operativos y tiene su propio protocolo.

La terminología clave para comprender los VCS es la siguiente:

- Repositorio: lugar donde se almacenan los datos actualizados y el historial de cambios. Puede ser local o remoto.
- Módulo: conjunto de directorios y archivos que pertenecen a un mismo proyecto.
- Revisión: versión determinada del proyecto que se gestiona. Estas versiones se pueden etiquetar. La última revisión se suele llamar "_HEAD_".
- Etiqueta (_Tag_): nombre especial que se le puede dar a una versión para identificarla posteriormente. El módulo se "congela" (se mantiene en el historial permanentemente) durante el rotulado para imponer una versión coherente.
- Baseline: revisión aprobada de un fichero a partir del cual se pueden realizar nuevos cambios.
- Rama (_Branch_): un módulo se puede bifurcar en un momento determinado desde el cual se tienen dos copias independientes, permitiendo realizar cambios sobre una copia y después añadirlos a la rama principal.
- Checkout: copia local desde el repositorio.
- Commit: copia en el repositorio del proyecto local.
- Conflicto: ocurre cuando el sistema no puede manejar los cambios realizados por dos o más usuarios en el mismo archivo.
- Resolver: intervención del usuario para atender un conflicto.
- Cambio (_Change_): modificación específica a un archivo.
- Lista de cambios (_Changelist_): lista de los cambios incluidos en un único commit. También es una vista secuencial del código fuente.
- Export: similar a un checkout pero sin metadatos de control de versiones (el proyecto queda limpio). Se usa antes de publicar los contenidos.
- Import: copia de los datos en el repositorio por primera vez.
- Fusión (_Merge_): fusión de dos conjuntos de cambios sobre uno o más ficheros en uno solo. Pueden producir conflictos.
- Merge inverso: fundir ramas de diferentes equipos en el trunk principal del sistema de versiones.
- Sync o update: integra los cambios del repositorio en la copia local.
- Workspace: copia local del repositorio en un momento o revisión específico.
- Congelar: permitir los últimos commits para solucionar fallos a resolver en una entrega y suspender cualquier otro cambio.

## Git
