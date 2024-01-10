# Git

Comandos básicos git

-- Configuración

git config --global user.name "nombre"
git config --global user.email "correo"
git config core.autocrlf true

// Establece el main como nombre global para todos los repositorios

git config --global init.defaultBranch main 

-- Iniciar un repositorio

git init

-- Revisar estado

git status

-- Añadir al stage

git add "nombre"
git add . // Importa todos

-- Remover del stage

git reset "nombre"

-- Capturar los archivos

git commit -m "nombre descriptivo del cambio"

-- Volver los cambios al último commit

git checkout -- .


-- Revisar la rama 

git branch

-- Cambiar nombre rama

git branch -m master (nombre actual) main (nuevo nombre)

-- Diferentes formas de agregar al stage

git add nombre1 nombre1
git add .

// Importar todos los archivos de un mismo tipo

git add *.extension_de_archivo
git add *.html

// Pertenecientes a otro directorio

git add directorio/*.extension_de_archivo
git add js/*.js

-- Añadir un directorio vacío

Se crea un documento vacío con la extensión .gitkeep


-- Crear alias para comandos en git

git config --global alias.nombre "comando con banderas"

// Ejemplo git config --global alias.s status --short

-- Comparar cambios 

git diff archivo
git diff --stage

-- Corregir el mensaje de un commit

git commit --amend -m "Nuevo mensaje"

-- Volver a un commit anterior

// Deshace commits manteniendo los cambios en el área de preparación.

git reset --soft 

// Deshace commits y quita los cambios del área de preparación, pero los conserva en el directorio de trabajo.

git reset --mixed o git reset 

// Deshace commits y elimina cambios tanto del área de preparación como del directorio de trabajo de forma irreversible.

git reset --hard

-- Revisar todo el historial de cambios del repositorio

git reflog

-- Crear rama

git branch "nombre"

-- Cambiar ramas

git checkout "nombre rama"

-- Unir cambios

// Desde la rama en la que se desea recibir los cambios.

git merge "nombre rama con cambios a traer"

-- Crear rama y moverse automáticamente

git checkout -b "nombre rama"

-- Crear un tag

git tag -a "nombre del tag" -m "mensaje del tag"

-- Eliminar un tag

git tag -d "nombre del tag"

-- Mostrar tags

git tag

-- Ver más información del tag

git show "nombre del tag"

-- Crear un tag para otro commit

git tag -a "nombre del tag" #HASH DEL COMMIT -m "mensaje del tag"

// Ejemplo: git tag -a v0.1.0 2aaaac1 -m "Version Alpha de la app"

-- Crear una boveda de cambios temporales ref/stash

git stash 

-- Mostrar los stash

git stash list

git stash list --stat

-- Volver a los cambios del stash anterior

git stash pop

-- Borrar todos los stash

git stash clear

-- Eliminar un stash

git stash drop #hash del stash
git stash drop //Borra el último stash

-- Obtener información del stash

git stash show #hash del stash

-- Nombrar un stash

git stash save "nombre del stash"


-- Ordenar commits

// Desde la rama que se desea ordenar
git rebase "nombre rama a rebasar"

git rebase master //ejemplo

-- Unir commits con rabase interactivo

// squash para unir el commit con el anterior o los commits seleccionados
git rebase -i HEAD~4 // el 4 es numero de commits que quiero tomar.


--Actualizar referencias

git fetch

-- Importar ramas de otros compañeros en el repositorio

git pull -a

-- Revisar todas las ramas

git branch -a

-- Limpiar el historial de ramas en local para mantener las activas

// Permite limpiar el historial de las ramas que ya no están activas en el repo, pero que aparecen en el local
git remote prune origin
