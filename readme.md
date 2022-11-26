1)¿Qué comando utilizaste en el paso 11? ¿Por qué?.

Deshacer el último commit (perdiendo los cambios realizados en el    working copy). 

He utilizado el comando git reset --hard HEAD~1 ya que si utilizaba el comando git reset HEAD~1 deshace el último commit pero mantiene lo que había en mi working copy.



2)¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

 Rehacer el último commit (el que acabamos de deshacer).

Utilice el comando git reflog para obtener el hash del último commit y utilice el comando git reset + hash para restaurarlo.



3)El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

 Hacer un merge con ‘master’ (styled absorbe a master)

No ha habido ningún conflicto ya que para que éstos ocurran, dos (o más) archivos han de haberse editado en la misma línea en dos ramas diferentes. En este caso, tan solo se ha modificado el archivo [git-nuestro.md](http://git-nuestro.md) en la rama styled, por lo que ésta absorberá sin problemas la rama master. 



4)El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

 Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify).

Al haber hecho cambios sobre el mismo archivo git-nuestro.md, en dos ramas diferentes y en la misma linea, al intentar hacer el merge, surge un conflicto ya que git no sabe con que cambios quedarse.



5) El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

Desde “master”, hacer un merge con “styled”

No, no ha causado conflicto porque en master se encontraba la versión del archivo git-nuestro.md original y al absorber la rama styled, absorbe también los cambios en este archivo y pasa a ser la versión modificada en styled. En resumen, al haber habido solo cambios del archivo en una rama, el merge puede hacerse sin conflictos.



6) ¿Qué comando o comandos utilizaste en el paso 25?

Dibujar el diagrama

git log --graph



7)El merge del paso 26, ¿Podría ser fast-forward? ¿Por qué? 

Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)

Si, podría haber sido un merge ff porque en la obtención del resultado final no hay diferencias entre los dos modos de hacer un merge, tan solo cambia la visualización del histórico de commits en las ramas. 



8) ¿Qué comando o comandos utilizaste en el paso 27?

 Deshacer el merge (sin perder los cambios del working copy)

Utilice el comando git reset HEAD~1 y así retrocedemos un commit. Al hacer git status nos aparece que nuestro fichero esta en estado modified.



9) ¿Qué comando o comandos utilizaste en el paso 28?

Descartar los cambios.

Utilizo el comando git checkout [git-nuestro.md](http://git-nuestro.md/), y utilizo el comando cat git-nuestro.md para verificar que el titulo obtenido con el merge anterior se ha eliminado correctamente y el archivo deja de estar en estado modified.



10) ¿Qué comando o comandos utilizaste en el paso 29?

Eliminar la rama “title”.

Para eliminar ramas se utiliza el comando git branch -D + (nombre de la rama) en este caso title. Para comprobar que se ha eliminado correctamente uso el comando git branch y en la lista de ramas ya no aparece.



11) ¿Qué comando o comandos utilizaste en el paso 30?

 Rehacer el merge que hemos deshecho

Git reflog para obtener histórico de cambios (commits) 

Obtenemos el hash del commit del merge.

git checkout -b title + hash.

Para recuperar la rama title en el estado del merge 

he vuelto a la rama master e intentado hacer un merge, obteniendo el mensaje de ‘already up to date’. Pero los estados de el archivo [git-nuestro.md](http://git-nuestro.md) son diferentes en ambas ramas (para mi sorpresa)

Ante esta situación y tras unas búsquedas en stack overflow, he ejecutado desde master git reset —-hard title y git reset —-hard master, obteniendo así el archivo [git-nuestro.md](http://git-nuestro.md) en el estado de la rama title y volviendo al estado del merge.



12) ¿Qué comando o comandos usaste en el paso 32?

Volver al commit inicial cuando se creó el poema

Use el comando git reflog para obtener el hash del commit del poema original, pero no sé porque no aparece, así que use el comando git log --reverse para obtener el hash completo, en este caso 2183e1e5264bb8e93dc6a62aded93b6fa9edfae5. 

Y por último utilice el comando git reset --hard 2183e1e5264bb8e93dc6a62aded93b6fa9edfae5.

Para asegurarme que era el git-nuestro original use el comando cat git-nuestro.md



13) ¿Qué comando o comandos usaste en el punto 33?

Volver al estado final, cuando pusimos título al poema

Igual que en el punto 12. git reflog para obtener el hash, el comando git reset - -hard + hash para restaurarlo, y el comando cat [git-nuestro.md](http://git-nuestro.md) para verificar que vuelve a tener el titulo.
