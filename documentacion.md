# Tarea Git - Github - Markdown - Visual Studio Code
> Crea un repositorio PRIVADO en Github con la documentación de esta práctica. Añade la profesor
como colaborador de ese repositorio. Redacta la práctica usando Markdown, aporta trozos de código
con los comandos **git** y capturas de pantalla.
# GIT
## Instalación y configuración inicial. (config)
> Para trabajar en Windows con git utilizaremos la terminal: **git bash**.

Instala o comprueba que ya esté instalado el servicio: **git**.
>Utiliza --version para mostrar la versión.

>Utiliza el comando **which git** para saber la ubicación del ejecutable.

Muestra el archivo de configuración global de git.

>El archivo de configuración global de git, si está creado, se encuentra en: **~/.gitconfig**.



Configura de forma global los datos de usuario: nombre y correo electrónico.

Muestra el listado de las distintas opciones de configuración.

Vuelve a mostrar el archivo de configuración global.

```bash
Kevin@DESKTOP-TIUU4RP MINGW64 ~
$ git --version
git version 2.39.1.windows.1

Kevin@DESKTOP-TIUU4RP MINGW64 ~
$ which git
/mingw64/bin/git

Kevin@DESKTOP-TIUU4RP MINGW64 ~
$ cat ~/.gitconfig
[user]
        name = Kevin
        email = kevnmm96@gmail.com

Kevin@DESKTOP-TIUU4RP MINGW64 ~
$ git config --global user.name "Kevin"

Kevin@DESKTOP-TIUU4RP MINGW64 ~
$ git config --global user.email "kevnmm96@gmail.com"

Kevin@DESKTOP-TIUU4RP MINGW64 ~
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.name=Kevin
user.email=kevnmm96@gmail.com

Kevin@DESKTOP-TIUU4RP MINGW64 ~
$ cat ~/.gitconfig
[user]
        name = Kevin
        email = kevnmm96@gmail.com
```

## Crear repositorios locales (init, status, add, commit, log)
Vamos a crear un repositorio llamado despliegue-demo. Crea una carpeta con el mismo nombre que el
repositorio y accede a ella.

Inicia un repositorio.

>Recuerda usar **git status** y **git log --oneline** para ir comprobando el estado de git y los registros de commit.

Muestra el estado de git antes de nada.

Muestra también los registros de commit antes de realizar cambios. Como aún no has hecho ningún
commit, debe darte un error.

Crea desde la línea de comandos un archivo **README.md** que contenga el nombre del repositorio.

>Puedes crear un archivo desde terminal con el comando **echo 'Contenido del archivo' >
archivo.md**. Si lo que quieres es un archivo vacío puedes usar el comando **touch archivo.md** y
después con **nano** darle contenido.

Vuelve a mostrar el estado de git después de crear un archivo.

Añade el archivo recién creado al área de intercambio o **staged**.

Vuelve a mostrar el estado de git después de añadir un archivo al **staged**.

Añade los archivos del área de intercambio al repositorio local con **commit**.

>Recuerda poner un mensaje al realizar el commit, con **-m "mensaje"**.

Vuelve a mostrar el estado de git después de añadir un archivo al **commit**.

Muestra los registros de commit después de realizar este primer commit.

Existe un comando git para a modificar el último commit. Este comando elimina el último commit y
crea otro nuevo con los cambios actuales del **staged**. El comando es **git commit --amend -m
"mensaje"**.

## Deshacer cambios en repositorios locales
### Cambios en un archivo que ya se ha incluido en algún commit. (diff, restore)
>Recuerda usar **git diff**, **git diff HEAD** o **git diff --cached**/ **git diff --staged** para ir viendo las diferencias de los archivos.

>Puedes usar **HEAD**, **HEAD~1**, **HEAD~2**, ... para referenciar el último commit, al anterior, ...

Vamos a modificar el archivo **README.md**. Lo editamos con un editor gráfico o desde el terminal con **nano**. Insertamos un par de espacios en blanco y ponermos el nombre del módulo: Despliegue de aplicaciones
web.

Muestra el contenido del archivo **README.md**.

Muestra el estado de git después de las modificaciones.

Muestra las diferencia de los cambios entre el directorio de trabajo y el último commit.

Añadimos el archivo al **staged**.

Vuelve a mostrar el estado de git después de añadir un archivo al **staged**.

Vuelve a mostrar las diferencia de los cambios pero esta vez entre el **staged** y el último commit.

Ahora deshaz este cambio y que el cambio se quede en el directorio de trabajo o **workspace**.

>Recuerda utilizar **git restore** con los parámetros adecuados en lugar de **git reset** o **git checkout**. Es la recomentación de las versiones más actuales de git.

Vuelve a mostrar el estado de git después de deshacer los cambios.

Muestra el contenido del archivo **README.md**. La línea con el nombre del módulo debe seguir estando ya que hemos deshecho el **staged** pero aún no hemos restaurado la copia del commit anterior.

Ahora sí queremos restaurar la copia del commit anterior. Es decir, deshacer los cambios del directorio de trabajo.

Vuelve a mostrar el contenido del archivo **README.md**. Ya debe verse como se salvo en el anterior commit.

Muestra el estado de git para comprobar el estado de los cambios en el directorio de trabajo.

### Cambios en un archivo que aún **NO** se ha incluido en algún commit.
Crear otro archivo **autor.md** con tu nombre y apellidos.

Muestra el estado de git para comprobar que hay cambios en el directorio de trabajo.

Borra el archivo recien creado.

Vuelve a mostrar el estado de git. El status de git debe aparecer limpio.

Crea un archivo **modulo.md** con el nombre del módulo: Despliegue.

Añade este archivo al **staged**.

Vuelve a mostrar el estado de git. Debe haber archivos para hacer commit.

Modifica el archivo **modulo.md** y añade el ciclo: DAW.

Muestra el contenido del archivo **modulo.md**.

Vuelve a mostrar el estado de git. Ahora debe estar el mismo archivo para añadir a staged y para hacer commit.

Muestra las diferencia de los cambios entre el directorio de trabajo y el **staged**.

Añade los nuevos cambios al **staged**.

Muestra el estado de git para comprobar que hay cambios listos para hacer un **commit**.

Deshaz los cambios cambios anteriores. Es decir, quita el archivo **modulo.md** del staged, pero se
mantenga en el directorio de trabajo.

Vuelve a mostrar el estado de git para ver que los cambios están en el directorio de trabajo.

Muestra el archivo **modulo.md** para comprobar que los cambios siguen estando en el directorio de trabajo.
Elimina el archivo **modulo.md**.