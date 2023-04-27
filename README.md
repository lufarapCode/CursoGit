## Conceptos básicos de github

# Comandos para iniciar tu repositorio con Git
***
```git init: para inicializar el repositorio git y el staged
git add nombre_del_archivo.txt: enviar el archivo al staged
git status: ver el estado, si se requiere agregar al starget o si se requiere commit
git conf: para ver las posibles configuraciones
git conf --list: para ver la lista de configuraciones hechas
git conf --list --show-origin: para mostrar las configuraciones y sus rutas
git rm --cached nombre_del_archivo.txt: para eliminar el archivo del staged(ram)
git rm nombre_del_archivo.txt: para eliminar del repositorio

```

# Comandos para analizar cambios en GIT
****
```git init: inicializar el repositorio
git add nombre_de_archivo.extensión: agregar el archivo al repositorio
git commit -m “Mensaje”: Agregamos los cambios para el repositorio
git add: Agregar los cambios de la carpeta en la que nos encontramos agregar todo
git status: visualizar cambios
git log nombre_de_archivos.extensión: histórico de cambios con detalles
git push: envía a otro repositorio remoto lo que estamos haciendo
git pull: traer repositorio remoto
ls: listado de carpetas en donde me encuentro. Es decir, como emplear dir en windows.
pwd: ubicación actual
mkdir: make directory nueva carpeta
touch archivo.extensión: crear archivo vacío
cat archivo.extensión: muestra el contenido del archivo
history: historial de comandos utilizados durante esa sesión
rm archivo.extensión: Eliminación de archivo
comando --help: ayuda sobre el comando
git checkout: traer cambios realizados
git rm --cached archivo.extensión: se utiliza para devolver el archivo que se tiene en ram. Cuando escribimos git add, lo devuelve a estado natural mientras está en staging.
git config --list: muestra la lista de configuración de git
git config --list --show-origin: rutas de acceso a la configuración de git
git log archivo.extensión: muestra la historia del archivo
```

# Analizar cambios en los archivos de un proyecto Git
*** 
```
- git log: lista de manera descendente los commits realizados.
- git log --stat: además de listar los commits, muestra la cantidad de bytes añadidos y eliminados en cada uno de los archivos modificados.
- git log --all --graph --decorate --oneline: muestra de manera comprimida toda la historia del repositorio de manera gráfica y embellecida.
- git show filename: permite ver la historia de los cambios en un archivo.
- git diff : compara diferencias entre en cambios confirmados.
```
# Volver en el tiempo con branches y checkout
```
- git reset --soft/hard: regresa al commit especificado, eliminando todos los cambios que se hicieron después de ese commit.
- git checkout : permite regresar al estado en el cual se realizó un commit o branch especificado, pero no elimina lo que está en el staging area.
- git checkout – : deshacer cambios en un archivo en estado modified (que ni fue agregado a staging)
```
# git rm y git reset

**git rm**:
```
Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

git rm no puede usarse por sí solo, así nomás. Se debe utilizar uno de los flags para indicar a Git cómo eliminar los archivos que ya no se necesitan en la última versión del proyecto:

- git rm --cached : elimina los archivos del área de Staging y del próximo commit, pero los mantiene en nuestro disco duro.
- git rm --force : elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos aplicar comandos más avanzados).
```
## **git reset**
```
Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir.

- git reset --soft: Vuelve el branch al estado del commit especificado, manteniendo los archivos en el directorio de trabajo y lo que haya en staging considerando todo como nuevos cambios. Así podemos aplicar las últimas actualizaciones a un nuevo commit.
- git reset --hard: Borra absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.
- git reset HEAD: No borra los archivos ni sus modificaciones, solo los saca del área de staging, de forma que los últimos cambios de estos archivos no se envíen al último commit. Si se cambia de opinión se los puede incluir nuevamente con git add.
```

# Ramas o Branches en git
```
Al crear una nueva rama se copia el último commit en esta nueva rama. Todos los cambios hechos en esta rama no se reflejarán en la rama master hasta que hagamos un merge.

- git branch : crea una nueva rama.
- git checkout : se mueve a la rama especificada.
- git merge : fusiona la rama actual con la rama especificada y produce un nuevo commit de esta fusión.
- git branch: lista las ramas generadas.
```

Cambio 1