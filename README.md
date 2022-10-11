
___
# Curso de Git GitHub

## Configuracion Inicial

```git config --global user.name "<Name User>"``` Este comando nos permite configurar el nombre de usuario de manera local.

```git config --global user.email "<Name User>"``` Este comando nos permite configurar el E_MAIL de usuario de manera local.

```git config --global code.editor "code --wait"``` Este comando le indica git interfaz por defecto para configuraciones y resoluciones de conflito ahora sea nuestro editor de codigo por defecto.


```git config --global core.autocrlf true``` Este comando Elimina los espacio en la

```git config --global init.defaultBranch main``` Este comando hace que git al inicial un nuevo repositorio le de el nombre de main a la rama principal.


alias

```git config --global alias.<el alias> <los comando que resume el alias>``` Esta es la estructura para colocar alias a los comandos.

*Nota: Si son mas de dos comando colocarlo entre commillas doble.


### Primeros comandos de unicio.

 
```git init``` 
inicia un reposito local creando una carpeta oculta .git

```git status``` muestra el estado del reposito actual

```git add <File>```
agrega los archivos al staged 

```git reset <Files / folder>``` elina un archivo o carpeta del stage

```git commit -m "<name commit>"```hace un commit, El nombre del commit tiene que ser claro y preciso.

```git log``` muestra el registro historico de los commit. log

```git checkout -- .``` Restablece el repositorio a como estaba en el ultimo log

```git checkout -- <file / folder>``` Restablece el archivo o carpeta seleccionada.

```git branch``` Nos muestra en que rama estamos al momento de ejecutar el comando.

```git branch -m <branch name to change> <new name branch>```este comando permite cambiar el nombre la rama actual, 

```git config --global init.defaulBranch main``` este comando cambia la configuracion global haciendo que al inicial un nuevo repositorio este tenga como rama principal el nombre de main.

```git commit -am "<name commit>"``` este comando agrega las modificaciones al stage y hace el commit en 1 solo paso 

Nota: este comnando solo funciona si ya los archivos modificado estaban previamente en el stage.


#### Nota Importante:
Git  no le sa seguimiento a las carpetas vacia a menos que se cree una archivo especial .gitkeep

```git diff```muesta cuales fueron las modificaciones en los archivos


 ```git diff --staged```Muestra cuales fueron los cambios en el staged.

 ```git commit --amend -m  "<change nada commit>"``` Enmienda el nombre del ultimo commit

```git reset --soft HEAD^``` este comando permite hacer un reset al ultimo commit.  


```git reset --soft <Hash>```este coamdno nos permite hacer un reset hasta un commit determinado e indentificado con el hash y deja los archivos en el staged


```git reset --mixed <Hash>```este comando es similar al soft  pero, baja los cambios del staged.


```git reset --hard <Hash>```este comando hace un reset a un hash, pero este hard si destruye todos los cambios hasta ese momento

```git reflog```regista todo el historial de git de manera profunda, mostrando mas a detalles cada movimiento y incluyendo los que no muestra el comando log nativo.

```git mv <files to change name> <new name file>``` Este comando permite renombrar el archivo previamente


```git  reset --hard```Este comando sin especificar el hash o commit de referencia, funciona similar a un git checkout -- .

```git branch <new name branch>```Este comando nos permite crear una nueva rama.

```git checkout  <new name branch to change>```Este comando nos permite movernos a una rama.

### Nota: 
para unir una rama con el comando merge tenemos que estar en la rama a la que vamos a unir los cambios.

```git merge <name branch to united the change>```Este comando nos permite  traer los cambios de  una rama a la rama actual.


```git branch -d <name branch>```Ete comando permite borrar una rama. si existen cambios que aun no se han guardado. git solicitara confirmacion de la accion.


```git branch -d <name branch> -f```Este comando forza a git a borrar la rama. aunque poseea cambios que no se han guardado

````git checkout -b <new name the branch>```Este comando nos permite crear una nueva rama y movernos a la misma en un solo paso.


```git tag <name tag>``` Nos permite crear una etiqueta /  tag

```git tag -d <name tag>``` Nos permite borrar una etiqueta / tag


```git tag -a <Number Version> -m "<Description>```Nos permite crear un tag `


```git tag -a <Number Version> <Hash> -m "<Description>```Nos permite crear un tag `


```git show <version tag>``` Muestra el tag

___
# Seccion 5 - Git Stash & Git Rebase


```git stash```Este comando nos permite armacenar los cambios realizado antes del ultimo commit en el stash.   

```git stash list``` Nos muestra las referencias del stash

```git stash pop``` Este comando nos permite recuperar los cambios almacenado en el stash

```git stash clear``` Este comando nos permite Borrar los cambios almacenado en el stash

```git stash apply hash ``` Este comando nos permite recupara los cambios de dicho hash

```git stash drop hash-stash```  Este comando nos permite borrar un stash determinado por el hash

```git stash show <hash-stash>``` Este comando nos permite ver que archivo ha sufrido cambio en el stash

```git stash save "<Description change>"``` Este comando nos permite guardar un stash con un descripcion.

```git stash list --stat``` Este comando nos muestra mas informacion de los stash.

## Rebase
Rebase mueve los commit a una zona temporal, permitiendo: 
1. Ordenar Commit
2. Corregir mensajes de los commit
3. Unir Commit
4. Seperar Commit

```git rebase master``` Este comando permite crea una area temporal donde mueve los commit.

```git rebase -i HEAD~3```Este comando nos permite hacer un rebase 

### Rebase -> Squash
Nos permite unir determindos commit

### Rebase -> Reword

### Rebase -> Edit  
Este comando nos permite modificar o separar archivos 

___
# Seccion 6 - GitHub, Remote - Push & Pull

## GITHUB
__Es una plataforma de desarollo colaborativo de software para alojar proyectos.__

*Beneficios que nos provee GitHub:*

* Repositorio ilimiatados
* Pagina HTML, CSS y JS ilimitadas
* push, pull, clones ilimitados
* issues, wikis, estadisticas ilimitadas
* organizaciones ilimitadas
* participacion gratuita en proyectos privados

## Remote Push & Pull

### __Creacion de Nuevos Respositorios en GitHub__

Luego de tener creada la cuenta de github vamos a dirigirnos a new  Repository

![Interfaz para crear nuevo repositorio](/img/newRepository.png "new repository")


![Interfaz para crear nuevo repositorio](/img/firstRemotePushToRepository.png  "new repository")


# falta contenido.


### Push de los tags de nuestro repository

```git push --tags``` Este comando nos Permite hacer el push de los de tags al repositorio remoto.

#### Creacion Release tags

en la los servicios de git gub podemos introducirnos a los tags y poder crear un release tag..... Estos es muy util porque nos permite poder agregar o especificar que sucedio en dicho tag de una manera mas clara, inclusive esto nos permite subir imagenes, pegar url, menciones, etc.

### push & pull 

```git remote -v``` Este comando nos permite ver cual es el origen de nuestro repositorio, si perdemos el origen este comando nos devuelve el origen fetch & push


```git pull```Este comando nos permite traer/descargar los cambios que hayan sucedido en el repositorio remoto al repositorio local.

```git pull origin```Este comadno aplica los cambios traidos/descargados desde el repositorio remoto al repositorio local.

### Clonar  repositorio

```git clone <Origen repository>``` Este comando nos permite clonar un repositorio remoto de manera local, recordar que tenemos que indicarle el origen desde donde queremos clonar el repositorio.

### Subir cambios locales al repositorio remoto

`git Push` Este comando nos permite subir los cambios locales al repositorio remoto.


___
# Seccion 7 - GitHub Basico

*

