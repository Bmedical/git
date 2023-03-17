# Basic Git Commands

## Git merge

![Git-merge](https://wac-cdn.atlassian.com/dam/jcr:4639eeb8-e417-434a-a3f8-a972277fc66a/02%20Merging%20main%20into%20the%20feature%20branh.svg?cdnVersion=861 "Git Merge")

Git merge es un comando de Git que nos permite combinar cambios de dos o más ramas diferentes en una sola rama. Por ejemplo, si tenemos la rama "desarrollo" y la rama  "característica", podemos combinar los cambios de ambas ramas utilizando git merge. El comando básico para combinar una rama en otra es el siguiente:

```shell
$ git merge <rama-a-combinar>
```

Por ejemplo, si queremos combinar la rama "característica" en la rama "desarrollo", podemos hacer lo siguiente:
```shell
$ git checkout desarrollo
$ git merge caracteristica
```
Este comando fusionará los cambios de la rama "característica" en la rama "desarrollo". Si hay conflictos, Git nos pedirá que los resolvamos antes de que se complete la fusión (merge).

## Git rebase

![Git-rebase](https://wac-cdn.atlassian.com/dam/jcr:3bafddf5-fd55-4320-9310-3d28f4fca3af/03%20Rebasing%20the%20feature%20branch%20into%20main.svg?cdnVersion=861 "Git Rebase")

Git rebase es otro comando de Git que nos permite combinar cambios de dos o más ramas diferentes en una sola rama. La principal diferencia entre git merge y git rebase es la forma en que se aplican los cambios. Con git merge, los cambios se aplican a la rama actual y se crea un nuevo commit de fusión. Con git rebase, los cambios se aplican a la punta de la rama base y se reescriben los commits de la rama que se está fusionando. Esto puede resultar en una historia de git más limpia y fácil de seguir. El comando básico para hacer un rebase es el siguiente:

```shell
$ git rebase <rama-a-rebasar>
```

Por ejemplo, si queremos rebasar la rama "característica" en la rama "desarrollo", podemos hacer lo siguiente:

```shell
$ git checkout desarrollo
$ git rebase caracteristica
```
Este comando aplicará los cambios de la rama "desarrollo" a la punta de la rama "característica". Si hay conflictos, Git te pedirá que los resuelvas antes de que se complete el rebase.

## Resolver conflictos al combinar cambios de dos o más ramas
En algunos casos, cuando se combinan o se rebasan ramas en Git, pueden surgir conflictos. Esto ocurre cuando dos o más ramas tienen cambios conflictivos en la misma área del código. En este caso, Git no puede resolver automáticamente el conflicto y nos pedirá que lo resolvamos manualmente. Para resolver un conflicto, debemos editar el archivo que causa el conflicto y elegir qué cambios queremos conservar. Luego, debemos agregar el archivo editado al índice y crear un nuevo commit.

Por ejemplo, supongamos que estamos fusionando la rama "característica" en la rama "desarrollo" y hay un conflicto en el archivo "archivo.txt". Para resolver el conflicto, podemos hacer lo siguiente:

Abre el archivo "archivo.txt" en tu editor de texto.
Busca la sección que causa el conflicto. Puede haber dos o más secciones de código que tienen cambios conflictivos.
Edita el archivo para elegir qué cambios quieres conservar. Puedes eliminar una sección completa o elegir qué líneas de cada sección quieres conservar.
Guarda el archivo editado.
Agrega el archivo editado al índice utilizando el comando git add archivo.txt.
Crea un nuevo commit utilizando el comando `git commit -m "resuelto conflicto en archivo.txt".

## Git cherry-pick

![Git-cherry-pick](https://mattstauffer.com/assets/images/content/opengraph/cherry-pick.png "Git Cherry Pick")

Git cherry-pick es un comando de Git que nos permite aplicar un commit específico de una rama a otra rama diferente. Por ejemplo, si tenemos un commit en la rama "característica" que deseamos aplicar en la rama "desarrollo", podemos utilizar git cherry-pick. El comando básico para hacer un cherry-pick es el siguiente:

```shell
$ git cherry-pick <hash-del-commit>
$ git rebase caracteristica
```

Por ejemplo, si deseamos aplicar el commit con el hash "abc123" de la rama "característica" en la rama "desarrollo", puedes hacer lo siguiente:

```shell
$ git checkout desarrollo
$ git cherry-pick abc123
```

Este comando aplicará el commit con el hash "abc123" de la rama "característica" en la rama "desarrollo". Si hay conflictos, Git nos pedirá que los resolvamos antes de que se complete el cherry-pick.
