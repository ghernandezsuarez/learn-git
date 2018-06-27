
Control de versiones GIT
========================

El control de versiones es un sistema que registra los cambios realizados sobre un archivo o conjunto de archivos a lo largo del tiempo, de modo que puedas recuperar versiones específicas más adelante.


- Instantáneas no diferencias
- Es local
- Tiene integridad
- Solo añade información

Estados
-------

	- Confirmado (commited) : Los datos estan almacenados de forma segura en la base de datos local.
	- Modificado (modified) : Se ha modificado el archivo pero todavía no lo has confirmado a tu base de datos. 
	- Preparado (staged) : Se ha marcado un archivo modificado en su versión actual para que vaya en tu próxima confirmación.


Secciones
---------
	- Directorio de Git (Git direcyory) :  Es la base de datos de objetos para el proyecto. Es lo que se copia cuando se clona un repositorio.
	- Directorio de trabajo (working direcry) :  Es una copia de una versión del proyecto.
	- Area de preparación (staging area) : Es un archivo que almacena información sober lo que va a ir en la próxima confirmación.

Flujo de trabajo básico de Git
------------------------------
	1. Modificar : los archivos en tu directorio de trabajo.
	2. Preparar : los archivos, añadiendolos al área de preparación.
	3. Confirmar : los cambios, tomando los archivos tal y como están en el área de preparación, y almacena esas instantáneas de manera permanente en el directorio de Git.

Si una versión concreta de un archivo está en el directorio de Git, se considera confirmada (committed). Si ha sufrido cambios desde que se obtuvo del repositorio, pero ha sido añadida al área de preparación, está preparada (staged). Y si ha sufrido cambios desde que se obtuvo del repositorio, pero no se ha preparado, está modificada (modified). 


Iniciando git

```shell
$ git init

Initialized empty Git repository in /Users/meplaz/Documents/chubb/learn/git/.git/
```

```shell
$ git config --list

credential.helper=osxkeychain                                                                      
user.name=MiguelPlazas                                                                             
user.email=miguelplazasr@gmail.com                                                                 
core.excludesfile=/Users/meplaz/.gitignore_global                                                  
difftool.sourcetree.cmd=opendiff "$LOCAL" "$REMOTE"                                                
difftool.sourcetree.path=                                                                          
mergetool.sourcetree.cmd=/Applications/Sourcetree 2.app/Contents/Resources/opendiff-w.sh "$LOCAL" "$REMOTE" -ancestor "$BASE" -merge "$MERGED"
mergetool.sourcetree.trustexitcode=true                                                            
core.repositoryformatversion=0                                                                     
core.filemode=true                                                                                 
core.bare=false                                                                                    
core.logallrefupdates=true                                                                         
core.ignorecase=true                                                                               
core.precomposeunicode=true 
```

user.name=

user.email

### Git Status 

```shell
$ git status
```

![alt text](./img/git_status.png "Git status")

### Git Add 
```shell
$ git add .
```
![alt text](./img/staged.png "Git staged")

### Git Commit 

```shell
$ git commit -am "First commit"
```
![alt text](./img/git_commit.png "Git commit")

```shell
$ git status
```
![alt text](./img/git_commit_status.png "Git commit status")

### Git Log

```shell
$ git log
```
![alt text](./img/git_log.png "Git log")

Interfaz gráfica para visualizar el histórico

```shell
$ gitk
```

### Git Ignore

Archivos que no serán versionados


Deshacer en el área de preparación
----------------------------------

### Modificar ultimo commit

```sell
$ git commit -m "Add feature"
$ git add newfile
$ git commit --amend
```

![alt text](./img/git_amend.png "Git amend")


### Sacar un archivo del área de preparación

![alt text](./img/git_reset_add.png "Git reset add .")


```shell
$ git reset HEAD file2.txt
```

![alt text](./img/git_reset_head.png "Git reset HEAD")

### Revertir cambios de un archivo

```shell
$ git checkout -- file 
```

### Etiquetas

Listar

```shell
$ git tag
```

Crear
```shell
$ git tag -a v1.0 -m 'version 1.0'
```

Git Flow