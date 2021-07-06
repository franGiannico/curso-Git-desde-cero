# Esta es la documentación del proyecto

Bienvenidos al curso de Git desde cero

Git desde cero

Es un sistema de control de versiones.
Una versión es un conjunto de nuevas características y funcionalidades de un software disponible para los usuarios finales.
Git fue creado por Linus Torvals, el creador de Linux. Es por eso que tuvo tanto éxito y hoy es considerado el estándar como sistema de control de versiones.

1er concepto de un sistema de control de versiones:
Repositorio: es una caja donde cada día del año se va imprimiendo y guardando todo nuestro programa y código que vamos creando. En el caso de git va a ser una carpeta .git donde se van a ir almacenando todos nuestros folders. 
Para dar comienzo a un repositorio debemos ejecutar el comando git init en el cmd.
Los tres estados de git:
1.	Espacio de trabajo
2.	Área de preparación
3.	Repositorio (carpeta .git)

git status 
Un commit es un punto en nuestra línea de tiempo del proyecto o cada mensaje guardado en nuestra bitácora.

Cada vez que modificamos un archivo debemos volver a ejecutar el git add para que se guarden todos los cambios 
y el archivo pase al estado de área de preparación, para luego ser commitado.

Cuando modificamos varios archivos o sumamos nuevos archivos a la carpeta y a su vez hemos avanzado en el
código de otro archivo, podemos agregarlos todos juntos al área de preparación con el comando: git add .
con el punto agregamos todos los archivos de la carpeta en la que estemos parados. 

ATAJO: con git commit -m "" podemos pasar directamente el mensaje del commit entre las comillas, sin necesidad
de abrir el editor de texto. 

Cuando modificamos varios archivos ya existentes (solo MODIFICADOS, no para archivos nuevos) podemos adherirlos
al área de preparacion y commitearlos en un solo paso, con el comando: git commit -am ""

Deshacer cambios

Cuando queremos borrar código o deshacer un código que hemos creado pero que queremos hacer de nuevo porque no funciona y queremos volver a una versión anterior o a un estado anterior del programa, lo que tenemos que hacer es ejecutar el comando: git checkout (seguido del nombre del archivo). Y si son varios archivos que hemos modificado y queremos deshacerlo en todos a la vez ejecutamos: git checkout -f.

Cuando a un archivo lo pasamos al área de preparación pero nos damos cuenta de que había algo q habíamos hecho mal en ese archivo y queremos sacarlo de ese estado, ejecutamos: git restored --staged (seguido del nombre del archivo).

Para ver qué cambios hicimos en determinado archivo (puede que hayamos hecho tantos cambios que no recordemos todo lo que hicimos) debemos ejecutar el comando: git diff y el nombre del archivo


Para volver aversiones antiguas de nuestro programa debemos usar el comando: git checkout y el código de commit, que lo encontramos cuando vemos la pantalla git log.

Bueno acá ahora falta un monton de info que está en el readme de la rama developmen ja. 
Para volver en el tiempo de nuevo para encontrar el proyecto hasta donde habíamos avanzado, usamos el comando:
git checkout master

git log --raw: nos devuelve el listado de todos los commits pero con un poco más de información. Nos agrega información de qué archivos han sido modificados (M) o si se ha añadido algún archivo (A).

git log --oneline: nos muestra todo el log pero resumido a un solo renglon por commit con su hash y mensaje. 

A cada línea de tiempo se las llama RAMAS, porque de la línea Master pueden salir varias líneas paralelas con diferentes versiones del programa y funciones que al final se integraran en una sola.

Para crear una nueva rama usamos el comando: git checkout -b + el nombre de la nueva rama.
Para conocer todas las ramas que tenemos en nuestro sistema ejecutamos: git branch

Para cambiar de rama: git checkout + el nombre de la rama a la que quiero moverme.
ó: git switch + elnombre de la rama. 

Para ver las ramas de forma gráfica usamos: git log --oneline --all --graph --decorate

Para volver a unir la rama secundaria que hemos creado con la master necesitamos dos cosas, primero lo ideal sería que no hubieramos tocado en ambas ramas los mismos archivos, para no generar un conflicto. Pero si ese no es el caso y ejecutamos el comando para unir ambas ramas, el sistema nos va a ayudar a resolver estos conflictos y despues de guardar los cambios que queramos conservar de ambas ramas ahí podremos unirlas. Utilizando el comando: (estando parado sobre la rama principal) git merge + el nombre de la rama que queramos agregarle. 

Cuando terminamos de trabajar en una rama debemos eliminarla porque ya no tiene sentido que exista la misma. 
usamos el comando: (estando parados en la rama master) git branch -D (d mayuscula)

Para ignorar un archivo, que si necesitamos tenerlo en nuestro espacio de trabajo, pero que no queremos hacerle commit porque no es parte del proyecto (por ejemplo una hoja de notas), debemos crear un archivo en la raíz de nuestro proyecto en visual estudio code con el nombre:.gitignore. Y dentro del mismo debemos poner el nombre de todos los archivos que queremos que git ignore.


GIT HUB PLATAFORMA PARA COMPARTIR EL PROYECTO EN LÍNEA Y TRABAJAR COLABORATIVAMENTE
Despues de crear un usuario y subir la carpeta del proyecto en un nuevo repositorio, debemos aprender a subir los cambios que vamos haciendo en el proyecto. Para eso usamos el comando: git push origin + el nombre de la rama. Puede que nos pida el nombre de usuario y contraseña de git hub. 

Para bajar información y cambios q están en la nube pero no en nuestra compu hacemos: git fetch origin, esto nos trae información sobre los commits que están en la nube, pero no nos baja aún los archivos al visual studio code.
Con: git pull origin + nombre de la rama nos trae los archivos que nos faltan bajar. 
