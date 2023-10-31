# Barreche_Alejandro
## https://github.com/alejandrobarreche/Barreche_Alejandro.git

**1º Explica qué es un pull request**

Un _pull request_ es una solicitud de cambios a un repositorio remoto que no es tuyo. Para realizar el pull request primero habrá que hacer un fork del repositorio remoto, que significa duplicar este mismo repositorio en tu cuenta de GitHub en donde tú eres el propietario. Después de las modificaciones se hará un pull request, que manda una solicitud al propietario del repositorio de añadir los cambios que has hecho; sin embargo, si muestra conflictos se deberán resolver antes de fusionarlo (de esto se encarga el propietario); aunque también puede decidir solictirale que cambie algo antes de aceptar el pull request, así como denegar el pull request.

**2º ¿Qué es un conflicto de fusión (merge conflict) en Git?**

Un _conflicto de fusión_ es un conflicto entre dos ficheros que sucede cuando se fusionan dos ramas. Este conflicto puede hacer referencia a texto que hay en un fichero que no hay en el otro, que ocasiona problemas para fusionarlos. La manera de hacerlo sería editando el propio archivo de manera manual y eliminando las líneas donde aparecen los símbolos: "HEAD <<<<<<", "========", "<nombre_de_la_rama> >>>>>"; aunque también habrá que comprobar que el orden que establece es el que nosotros queremos y si este ha sufirdo algún cambio que pueda provocar errores en nuestro código.

**3º Procedimiento para fusionar dos ramas**

Si HEAD se encuentra en la rama _"examen_parcial"_ y ha sufrido cambios, es decir, es una secuencia de commits diferentes a la rama _main_, para fusionarlas habría que hacer los siguientes pasos:
* Primero habría que comprobar que todos los archivos estuvieran en el último commit y que no hubiera ninguno en el working directory. _git status_  /  _git commit -a -m "Mensaje significativo"_
* Segundo habría que comenzar con la fusión a traves de _git merge main_, donde estaríamos fusionando la rama main en la rama examen_parcial
* Tercero habría que solucionar los conflictos de aquellos ficheros que los tengan, para acabar haciendo _git add ._ que añadiría todo los ficheros que hemos editado.
* Por último, podríamos utilizar tanto el comando _git merge --continue_ como el comando _git commit -m "Mensaje significativo"_ para finalizar con la fusión de las ramas.
Este procedimiento nos deja la rama _examen parcial_ en el último commit, que es la fusión de ambas ramas, sin embargo, para fusionar la rama _examen_parcial_ en la rama _main habría que seguir otra serie de pasos:
* Primero habría que cambiarse a la rama main a través de _git checkout main_
* Segundo habría que fusionar las ramas con el comando _git merge examen_parcial_, que debido a que hemos fusionado las ramas anteriormente, la forma de hacerlo ahora será más sencilla ya que hará lo que se conoce como ff (fast-forward). Esto dejará la rama _main_ en el mismo commit que la rama _examen_parcial_ y podríamos decidir que hacer con la otra rama.

**4º Revertir el commit sin borrar el área de trabajo**

_$ git commit --amend_

**5º ¿Cómo se realiza un fork de un repositorio en GitHub y para qué se utiliza comúnmente esta acción?**

Para realizar el fork lo primero que habría que hacer sería acceder al repositorio remoto que no es tuyo y que queremos hacer el fork. En este repositorio debería de aparecer un botón arriba a la derecha que ponga _fork_, el cual pulsaremos, y le daremos a añadir fork; lo que genera una copia en tu directorio sobre la cual eres tú el propietario. 
Esta acción se utiliza normalmente para hacer un pull request

**6º Cómo llegar al _archivo.txt_**

_$ cd Alejandro/Universidad/Uax_  Se trata de una ruta absoluta
_$ cd Uax_ Se trata de una ruta relativa

**7º Tipo Test**

1) git clone _b_
2) git checkout _b_
3) git checkout _c_
4) git add _b_
5) git commit _b_
6) git push _b_
7) git pull _c_
8) git merge _d_
9) git reset --hard _a_
10) git log _c_

**8º Ayudar a la rama _matemáticas_ y _Diseño UX_ a integrarse en _develop_**

Consideraciones a tener en cuenta:
- Ambas ramas (tanto _matemáticas_ como _Diseño UX_) deben de tener una base en _develop_, es decir, deben de partir de alguno de los commits de dicha rama
- Una vez uno integre su rama en la rama _develop_, la otra rama no podrá publicar los cambios hasta que no integre todos los nuevos cambios subidos al repositorio remoto

Para realizar la tarea de la forma más eficiente, habría que seguir los siguientes pasos:
* Los que deberían subir los cambios realizados sobre la rama _develop_ al repositorio remoto primero sería la rama _matemáticas_, ya que la rama _Diseño UX_ depende de las nuevas implementaciones de la rama _matemáticas_ para su desarrollo
* Una vez publicados los cambios al repositorio remoto, el equipo de diseño UX deben implementar esos cambios en su rama develop a través del comando _git pull_, el cual comprueba todos los cambios que hay entre tu repositorio local y el repositorio remoto, y trata de fusionarlos. En el caso de que haya algún conflicto, se deberá resolver de la manera oportuna (que dependerá de los cambios realizados) para que tu rama _develop_ esté actualizada
* Una vez actualizada la rama _develop_, sería cuando se debería de fusionar con git merge la rama _develop_ en la rama _Diseño UX_, de manera que habrá que resolver los conflictos, y el equipo destinado a trabajar en el diseño UX podrá implementar las nuevas funcionalidades que han creado el equipo de matemáticas.
* Cuando se hayan desarrollado las implementaciones que habían creado el equipo de matemáticas, se fusionará la rama _Diseño UX_ en la rama _develop_, que ya estará actualizada, y lista para poder publicarse en el repositorio remoto a través del comando _$ git push develop_

**9º Módulo 3**

C) Añadiste el botón "x^4" al archivo "index.html" en tu repositorio local, creaste un commit con los cambios y luego subiste el repositorio local al remoto en la rama principal (master).
