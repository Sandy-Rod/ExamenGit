# Práctica Git & GitHub

## Ejercicio 1

**¿Qué comando utilizaste en el paso 11? ¿Por qué?**
_git reset --hard HEAD~1_
_HEAD is now at 9dd539e creación git-nuestro.md_
Ejecuto el comando git reset porque este comando mueve el puntero de la rama actual al commit anterior, con la opción --hard
restablece tanto el staging área como el working copy al estado del commit anterior. HEAD~1 hago referencia al commit
anterior al actual, es decir, deshace el último commit.

**¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**
Git reflog, este commando mostrará una lista de todos los cambios recientes en el puntero HEAD, incluidos
los commits que se han realizado, deshecho, y cualquier otra acción.
_git reflog_
9dd539e (HEAD -> styled, origin/main, main) HEAD@{0}: reset: moving to HEAD~1
b20eef1 (origin/styled) HEAD@{1}: commit: modificación punto 9
9dd539e (HEAD -> styled, origin/main, main) HEAD@{2}: checkout: moving from main to styled
9dd539e (HEAD -> styled, origin/main, main) HEAD@{3}: commit (initial): creación git-nuestro.md
Aquí, HEAD@{1} es el commit que acabas de deshacer (b20eef1).
Ahora que tengo la referencia del commit que deso rehacer, ejecuto el siguiente comando.
_git reset --hard b20eef1_
HEAD is now at b20eef1 modificación punto 9
Esto moverá el punter HEAD de vuelta al commit que deshice en le punto 11.

**El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**
Cambio a la rama main
_git checkout main_
Antes de hacer un merge, hago un git pull para actualizar
_git pull origin main_
Ahora hago un merge
#git merge styled
Con este ultimo paso se carga los cambios styled en la rama main.
En este paso no he tenido conflicto porque no había modificaciones en la rama main.

**El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**
No, porque los mismos archivos no han sido modificados en ambas ramas, tamopoco se han modificado las mismas
líneas de codigo del fichero en ambas ramas y no se ha eliminado ni movido el archivo en una rama y en la otra si.

**¿Qué comando o comandos utilizaste en el paso 25?**
_git log --graph --decorate -–all_
Git log muestra el historial de commits de todas las ramas con el atributo –all,
con –graph añadimos un gráfico que utiliza caracteres como \*, |, / y \ para representar
las ramas y los marges. Al añadir –decorate muesta los ombres de las ramas locales y remotas.

**El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**
_git checkout main_
_git pull origin main_
_git merge --no-ff title 26_
_git push origin main_

Con fast-forward movemos el puntero de main hacia el último commit de la rama title, haciendo que le historial parezca lineal.
En cambio, con no fast-forward creamos un commit de merge que claramente indica que las ramas main y title fueron combinadas.

**¿Qué comando o comandos utilizaste en el paso 27?**
_git reset --mixed HEAD^_
Unstaged changes after reset:
M git-nuestro.md
Ejecutamos el comando git reset –mixed HEAD^.
Con git reset restablecemos el estado de repositorio al commit especificado
Con el atributo –mixed mantenemos los cambios en el working copy, pero deshace el commit del merge, moviendo los archivos modificados en el staging área.
Con el atributo HEAD^ retrocedemos al commit anterior ( el commit antes del merge)

**¿Qué comando o comandos utilizaste en el paso 28?**
_git restore --staged ._
_git restore ._
_git status_

**¿Qué comando o comandos utilizaste en el paso 29?**
_git branch -D title_ ejecuto este comando porque he eliminado la rama local, si elimanará la rama del repositorio _git push origin –-delete title_

**¿Qué comando o comandos utilizaste en el paso 30?**
_git reflog_ busco el identificador
_git reset – hard 06b9073_

**¿Qué comando o comandos usaste en el paso 32?**
Volver al commit inicial cuando se creó el poema
_git log –oneline_ con este comando busco el commit donde he creado el fichero con el poema
_git checkout 9dd539e_ entro al commit inicial.

**¿Qué comando o comandos usaste en el punto 33?**
_git switch -_ con este comando regreso al estado final.
