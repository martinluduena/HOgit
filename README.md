# HOgit
Repositorio con ejercicios para practicar comandos básicos de git

## Qué podemos hacer

### Commits
Modificar un archivo y agregarlo al repositorio como un nuevo commit

### Branches
Creamos un branch acerca de las charlas, y decimos que nos parecen buenísimas
Pasos con los que armamos el repo de github de HOgit.


## Cómo creamos este repositorio

Inicialmente estaba creado en github (desde la WEB) con 
sólo un README. EN cualquier lugar pueden (y deberían!)
correr `git status` y `git branch -a` para chequear
en qué estado está el repositorio y en qué branch están:


Clonamos un repositorio de github con sólo un README

```
git clone https://github.com/wtpc/HOgit.git
cd HOgit
```

Editamos el archivo de README y hacemos un nuevo commit

```
vi README.md
.........
git add README.md
git commit
```

Ya hay un nuevo snapshot. Ahora creamos una branch

```
git branch charlas
```
### Lo que veo luego de: git branch -a
  charlas
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/charlas
  remotes/origin/ejercicios
  remotes/origin/master



y nos movemos a ella

```
git checkout charlas
```
### Lo que veo luego de: git status
En la rama charlas
Cambios no preparados para el commit:
  (use «git add <archivo>...» para actualizar lo que se confirmará)
  (use «git checkout -- <archivo>...» para descartar cambios en el directorio de trabajo)

	modificado:    README.md

no hay cambios agregados al commit (use «git add» o «git commit -a»)

en esta branch, editamos README.md de nuevo


### Agregue esta linea 

```
vi README.md
...
git add README.md
git commit
```
### Lo que veo luego de: git branch -a
* charlas
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/charlas
  remotes/origin/ejercicios
  remotes/origin/master




ahora vamos a master (que no tiene estos cambios, porque es otra branch!)

```
git checkout master
```
### git checkout master
Switched to branch 'master'
Su rama está delante de «origin/master» para 1 commit.
  (use "git push" to publish your local commits)



y a partir de master creamos una nueva branch

```
git branch ejercicios
git checkout ejercicios
```

editamos un archivo nuevo, ejercicios.md

```
vi ejercicios.md
...
git add ejercicios.md
git commit
```

Y ahora, en master, hacemos un merge de ambas branches por separado:
(fíjense que no importa que el orden sea el mismo que en el que 
las modificamos. es sensato porque las branches no se comunican)

```
git merge --no-ff ejercicios
git merge --no-ff charlas
```

la opción --no-ff sirve para que no "mezcle" las dos branches, y queda más prolijo el network. recomienod que la usen siempre, pero no es fundamental.

si quieren ver cómo quedó la historia del repo:

```
git log --oneline --graph
```

## Lo que veo luego de: git log --oneline --graph
*   fba3382 Merge branch 'charlas'
|\  
| * 960e93a Agregue un par de lineas màs al README.md
| * 2cce7fa Modifique el archivo README.md agregando algunas lineas con comentraios mostrando lo que iba viendo al ejecutar cada uno de los comandos de git.
* | 8df429f Hice un commit del README.
* |   c5a100f Merge branch 'ejercicios' las modificaciones del archivo ejercicios.md echas en la rama ejercicios las voy a pasar a la rama master
|\ \  
| |/  
|/|   
| * e6f810e Modifique el archivo ejercicios.md dando mi opinion sobre los ejercicios
|/  
* 7868d36 Es el primer commit del archivo README. Agrege unas lineas al comienzo del archivo
* 373ee43 Cambiado protocolo por defecto a https
* ed74bb6 Agregados comandos
*   5339e09 Merge branch 'charlas'
|\  
| * 5ffe580 Más cosas de git!
* |   ab6622e Merge branch 'ejercicios'
|\ \  
| |/  
|/|   
| * c0e2aa2 Agregamos un nuevo archivo
|/  
* 0896d0e Info de qué hacer
* de70e76 Initial commit







finalmente, hacemos un push de todas las branches:

```
git push -u origin master
git push -u origin ejercicios
git push -u origin charlas
```

y listo! en nuestra cuenta de github ya tiene que estar subido. pueden ver el network de github que les va a mostrar la historia

Luego también editamos este readme para agregar los comandos con los que hicimos el repositorio

### Comentarios agregados por Martin 
hice un Fork desde el repositorio del Profe
Luego : 
```
  git clone github/martinluduena/HOgit

```


```
vi README.md
...
git add README.md
git commit
```

y el push

```
git push
```
