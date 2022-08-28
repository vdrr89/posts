# GIT CODE
---

## Cambiar el programa que se usa para editar commits, x ej el nuevo podría ser "C:\Program Files\Notepad++\notepad++.exe"
`$ git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"`

---

# Configuración del repositorio local y remoto
---
---

## Username

**Ver el username que estamos usando**
`git config user.name`

También puede ser: 

`user.name`

`user.email`

`color.status`

`color.branch`

`color.interactive`

`color.diff`


**Configurar el nombre de usuario**

* De forma local (solo para este proyecto):
`git config user.name "aqui el user name"`

* De forma global (para todos los proyectos de la pc):
`git config --global user.name "aqui el user name"`

---

## Iniciar un repositorio, ver su estado

**Iniciar un repositorio local**
`git init `
tener en cuenta debemos elegir entre:
* iniciar un nuevo repositorio (git init)
* descargar (clonar) un repositorio ya existente en github (git clone)  

**Clonar un repositorio remoto en nuestro espacio local**
`git clone https://url.Del/Repositorio/Remoto nombreRepositorio`

**ver el estado de la carpeta en git**
(la carpeta en donde nos encontramos realizando el comando)
`git status`

**Ver el historial de lo que ha sucedido en el repositorio**
`git log`

**Ver que se ha cambiado pero no se ha preparado**
`git diff`

**Limpiar los archivos innecesarios del repositorio local**
`git gc`

**Ver diferencias entre ramas**
Teniendo las ramas master y nuevaRama, 
estando parados en master, 
con esto vemos las diferencias entre ambas ramas
`git diff --stat master nuevaRama`

---

## Excluir archivos no deseados
Hacer un gitignore sirve para seleccionar los archivos que no queremos guardar en el repositorio, los seleccionamos de forma que al agregar todos nuestros archivos automáticamente, estos no se envíen. 

`gitignore`
se llama así, gitignore y no tiene ninguna extensión
se crea en la carpeta correspondiente abrir git bash o con cd y dir

**Ver archivos ignorados**
`git status --ignored`

**Comentarios en los gitignore:**
`# esto es un comentario dentro del archivo gitignore`

**Ignorar un archivo en específico**
`development.log`

**Ignorar una carpeta y su contenido**
`build`

**Ignorar todos los archivos que terminen en .log**
`*.log`

**Excepto production.log**
`!production.log`

**Ignorar los archivos terminados en .txt dentro de la carpeta doc**
(pero no sus subdirectorios)
`doc/*.txt`

**Ignorar todos los archivos terminados en .pdf** 
Dentro de la carpeta doc y sus subdirectorios
`doc/**/*.pdf`

---

## Configuración del repositorio remoto

**Ver información sobre la relación entre el repositorio local y el remoto**
`git remote`

**Ver la dirección remota (url) que está enlazada en este repositorio**
`git remote -v`

**Ver la dirección de las ramas remoto que hay**
`git show-ref`

**Enlazar un repositorio remoto con el local**
`git remote add origin onlineRepoUrl`
*origin* sería el nombre que le asignamos al repositorio remoto, solo un nombre

**Eliminar el link al repositorio online**
`git remote remove origin`
`git remote nombreDelRepositorio`

**Ver el historial de lo que ha sucedito en el repositorio**
`git log`

**Muestra últimos cambios subidos al repositorio online**
`git log --oneline`

---

# Agregar y guardar archivos en el repositorio local y enviarlos al repositorio remoto
---
---

## Agregar archivos al repositorio local

**Agregar archivos al respositorio**
Es como si guardaramos los archivos en una caja

El *punto* significa que se agregan **todos** los archivos al repositorio (local)
`git add .` 

Con *nombre del archivo al final*, solo estamos agregando ese archivo puntualmente (al repositorio local)
`git add nombreDelArchivo`


**Ponerle nombre al envío de los archivos al repositorio**
Es como si etiquetaramos, con comentarios, la caja con nuestros archivos guardados
Con este comando se hace un commit al repositorio local

`git commit -m "first commit"`
La *m* significa message, osea que si escribimos *-message* en lugar de *-m* funcionaría igual. 

**Corregir el mensaje ya enviado en el commit**
si te equivocaste en lo escrito en el mensaje del commit (del repositorio local), al escribir este comando te abre un editor de txt para que edites el mensaje, luego guardas y cierras.
`git commit --amend`

---

## Enviar desde el repositorio local al remoto
`git push origin master` 
*origin* debe ser el nombre del repositorio online que se muestra en remote -v antes del url 
*master* es el nombre de la rama a la que voy a enviar

**Editar un mensaje ya enviado en commit anterior**
`git commit --amend`
Se edita en el editor de texto, luego darle a guardar y cerrar

**Forzar el envío del commit al remoto**
Si por algún motivo no nos estpa permitiendo enviar este commit... 
(puede suceder luego de cambiar el mensaje del commit ya enviado)
`git push --force origin master`
*origin* es el nombre del repositorio remoto que aparece en git remote -v
*master* es la rama a la que se lo manda

---

# Gestionar ramas
---
---

**Éstas opciones muestran las ramas e indica donde estás tu**
`git branch` 
`git branch -v`
`git branch -vv`

**Muestra todas las ramas, remotas y locales**
`git branch -a`

**Muestra todas las ramas remotas**
`git branch -r`

**Crear nueva rama**
`git branch nuevaRama`

**cambiar de ubicación y pararse dentro de ella**
`git checkout nuevaRama`

**Crear y cambiar hacia la ubicación de una nueva rama**
`git checkout -b nuevaRama`

**Ver diferencias entre ramas**
`git diff --stat master nuevaRama`
Teniendo las ramas master y nuevaRama, estando parados en master, con esto vemos las diferencias entre ambas ramas

**Ver las ramas que SI han sido combinadas**
`git branch --merged`

**Ver las ramas que NO han sido combinadas**
`git branch --no-merged`

**Combinar ramas**
`git merge nuevaRama`
Nos vamos a la rama master y ejecutamos este código para combinar la *nuevaRama* dentro de master.

**Eliminar nuevaRama del repo local**
* Para el repositorio local:
`git branch -d nuevaRama`

* Para el repositorio remoto:
`git push origin --delete nombreDeLaRama`
(recordá que en la configuración de github debe tener marcado como "default branch" alguna rama que no sea la misma que quieres borrar (github.com... > settings > branches) )