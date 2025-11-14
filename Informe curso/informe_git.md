# Curso de Git, principales comandos y ejemplo practico

## Instalar Git 

### 1. Nos dirigimos a la pagina oficial de [Git](https://git-scm.com/).

![Pagina de Git](<Images/1- pagina de git.png>)

### 2. Damos click en Install y luego descargaremos el instalador dependiendo del sistema operativo con el que cuenta nuestra maquina(en mi caso Windows).
 
 ![Pagina de Git install](<Images/2-instalar git 1.png>)


### 3. Elegimos la opción de descarga.

 ![Pagina de Git instalar para windows](<Images/3-instalar git 2.png>)
 Aqui seleccionaremos la opción de descarga que se adapte a nuestras necesidades en mi caso instale la última version, para esto da click donde dice `Click here to download`.

 ### 4. Abrimos el archivo que se nos descargo que viene siendo un archivo `.exe`

![Instalador de Git](<Images/4- instalar git 3.png>)

### 5. Por último abrimos la terminal o el simbolo del sistema (cmd) en el caso de Windows. Allí verificaremos si Git se instaló usando el comando `git --version`.


![Version de Git](<Images/4- Mirar version de git.png>)


## Comandos de Git

1. `git --help`: Te mostrara ayuda para usar los comandos de Git, junto con la explicación de cada uno.
![ayuda de git](<Images/5- git --help.png>)

2. `git config --global user.name "username"`: Configurar nombre al usuario.
3. `git config --global user.email "user@example.com"`: Configurar email al usuario.

![Configurar nombre y email](<Images/6- configurar nonbre y email de usuario.png>)

A continuación se prueba si los cambios se guardaron correctamente usando el mismo comando:
![Comprobar cambios email y nombre](<Images/7- comprobar que se guardo el nombre y email.png>)  

4. `git init`: Inicializar contexto de Git.
![git init](<Images/8- git init inicializar contexto de git .png>)

5.  `git branch -m main`: Cambiar nombre de la rama.
![cambiar nombre de la rama](<Images/9-cambiar nombre de la rama.png>)

6. `git status`: Mirar estado del proyecto.

![Estado del proyecto](<Images/10- mirar estado del proyecto.png>)

7. `git add <nombre de fichero>`: Añadir fichero al stage o escenario preparado para su uso. Si quieres añadir todos los archivos simplemente colocas un punto ".", así quedaria el comando `git add .`.

![añadir fichero al stage](<Images/11- añadir fichero al stage.png>)

Observamos el estado del fichero con `git status` y se nos debe mostrar de la siguiente manera:
![Mostrar estado del proyecto](<Images/12- miramos el estado del fichero.png>)

8. `git commit -m "<mensaje>"`: Hacer una fotografia de nuestro proyecto indicando en un mensaje los cambios que se hicieron o que versión del proyecto es.
![Fotografia del proyecto](<Images/13- Primer commit o fotografia del proyecto.png>)

9. `git log`: se muestra el historial de commits junto su informacion de creación: autor, hash, mensaje, etc.

![Historial de commits](<Images/14- historial de commits.png>)

10. He creado un nuevo fichero o archivo llamado "hellogit2.py" y al hacer `git status` se nos muestra el cambio que hemos hecho y que es necesario hacer otro *commit*

![estato del repositorio](<Images/15- estado con cambios en el repositorio.png>)

11. Ahora añadimos el nuevo fichero al stage con `git add` para leugo hacer otro `git commit` que ya seria la segunda fotografia version de nuestro repositorio. Si usamos el comando `git log` veremos que ahora tendremos dos *commit*.

![nuevo commit](<Images/16- añadir fichero al stage y hacer commit.png>)

12. Ahora modifico un fichero y uso `git status` para mirar el estado del repo, donde se nos dira que no he creado un nuevo fichero pero que si realice cambios en él.
![Cambios en un fichero](<Images/17- cambios en el fichero .png>)

13. `git checkout <nombre fichero>`: Es para situarnos en un punto en concreto de una fotografia asociandole un ID.
![Volver al anterior punto de guardado](<Images/18- devolver al ultimo punto guardado.png>)

14. `git reset`: Hace que la rama actual *HEAD* apunte a otro commit y dependiendo del uso quiero conservar o eliminar los cambios(Descartar los cambios basicamente). En mi caso quiero revertir los cambios entonces despues de eso uso un `git checkout` para reestablecer los cambios.

![uso de git reset](<Images/20- uso git reset.png>)

15. Ahora hago un nuevo commit ya que quiero guardar cambios hechos en uno de los ficheros.
![tercer commit](<Images/21- nuevo commit guardando cambios.png>)

Usando `git log --graph` lo que estamos haciendo es mostrarnos la rama y la secuencia de creación de los commits
![mostrar commits graficamente](<Images/22- mostrar graficamente los commit hechos en la rama.png>)

Estas son otras formas de observar los *logs* para que sea vea poco más legible:
![otras formas de ver los logs](<Images/23- otras formas de observar los logs.png>)

16. `git config  --global  alias.tree "git>git log --graph --decorate  --all --oneline"`: Asignar un alias a un comando para poderlo llamar usando el alias y no escribiendo el comando entero

![alias comando](<Images/24- alias para comando.png>)

17. Si queremos ignorar algún fichero en el repositorio ya sea uno temporal o simplmente uno que no querramos añadir creamos un **.gitignore** y añadimos el nombre del fichero que querramos ignorar.

![crear .gitignore](<Images/25- creamos gitignore.png>)

![directorio](<Images/26- directorio con el .gitignore.png>)

Ahora debemos hacer un nuevo *commit* ya que el **.gitignore** es un fichero que nos interesa guardar en el repositorio.

![commit para .gitignore](<Images/27- crear commit para guardar el .gitignore.png>)

18. `git diff`: Mostrar los cambios que hemos hechos sin haber hecho la fotografia.
![mostrar cambios](<Images/28- mostrar los cambios que hemos hechos sin haber hecho la fotografia.png>)

19. `git checkout <id_commit>`: Me permite moverme entre ramas del repositorio, en este caso volvi a la primer estado, es decir, el primer commit.

![volver al primer estado](<Images/29- volver a cualquier estado anterior del proyecto.png>)

![visualizacion de los cambios al volver a ese estado](<Images/30.- volver al primer commit.png>)

20. Uso de nuevo el `checkout` para volver a la ultima fotografia o rama.

![volver a la ultima rama](<Images/31- regreso a la ultima fotografia.png>)

Vuelvem a aparecer los archivos que se habian eliminado al cambiar el commit o de version.

![vuelven los archivos](<Images/32- vuelven a aparecer los archivos que teniamos .png>)

21. `git reset --hard <id_commit>`: Descartar los commits hechos depues de cierto punto o descartando eliminando los nuevos commit y haciendo que el *HEAD* se ubique en otro puto.

![reset hard](<Images/33- Volver a un commit reseteando o omitiendo los cambios de los nuevos commit(los elimina).png>)

Estado de los ficheros despues del *reset hard*:
![Ficheros despues del reset hard](<Images/34- Ficheros al hacer el reset hard.png>)

Recuperamos los commits usando `git checkout`:

![Recuperar commits](<Images/35- Reestablecer commits.png>)


22. `git tag`: asignar una etiqueta a la version del proyecto o donde este ubicado el *HEAD*
![aignar tag](<Images/36- Agregar tag a version del proyecto.png>)

Ya que el *tag* es solo una etiqueta y no una rama como tal entonces se desconectara el repositorio y git no sabra donde guardar los cambios entonces tendremos que regresar a la rama principal que este caso es **main** usando: `git checkout main`.
![regresar a la rama main](<Images/40 - volver a la rama main.png>)

23. Creamos un nuevo fichero y miramos el estado del repositorio con `git status`.

![nuevo fichero](<Images/37- nuevo fichero creado.png>)

Si queremos añadir a la zona del stage todos los ficheros del directorio sin necesidad de añadir uno por uno usamos `git add .` (ya lo habia mencionado anteriormente). Luego ya podremos hacer nuestro *commit* o fotografia del proyecto.

![Quinto commit](<Images/38- quinto commit.png>)

24. `git checkout tags/nombre_tag`: Para movernos entre ramas usando los tags
![usar tags para movernos entre ramas](<Images/39- movernos entre ramas usando el tag.png>)

Para regresar a la rama **main** usamos `git checkout main`.

25. `git branch <nombre_rama>`: Crear una nueva rama donde podremos trabajar de manera totalmente alterna a la rama **main**.
![craar nueva rama](<Images/41- crear nueva rama.png>)


26. `git switch <nombre_rama>`: Movernos a otra rama.

![cambiar de rama](<Images/42- Cambiar de rama.png>)

27. Se añade un nuevo fichero pero ahora estamos en la nueva nueva rama(En este caso **developer**), entonces todo lo que modifiquemos va quedar en esta rama y no se va a guardar en la rama **main**.

![nuevo fichero en la rama developer](<Images/43- nuevo fichero en la rama developer.png>)

Si hacemos un `git switch main` se nos mostrara que ya no estara nuestro nuevo fichero en el directorio y ademas volveremos al ultimo commit guardado en la rama.
![cambio a rama main](<Images/44- cambia a la rama principal.png>)

![Estado del directorio](<Images/45- estado del directorio.png>)


28. Ahora ya que estamos en la rama **main** podremos seguir modificando cada rama por separado, aqui voy a crear un nuevo fichero y pues generar otra version del proyecto.

![nueva version del proyecto en la rama main](<Images/46- crear nueva version del proyecto.png>)

![estado actuald del directorio](<Images/47- estado del directorio .png>)


29. Vuelvo a la rama **developer** y uno los cambios de esta con los de la rama **main** usando: `git merge main`.
Basicamente se genera un nuevo `commit` donde va queda la version unida de ambas ramas.

    
![unir dos ramas](<Images/48-  unir dos ramas.png>)

Asi se ve el **merge** en los logs:

![merge graficamente](<Images/50- graficamente como se ve el merge.png>)


**Nota:** Estoy usando el comando `git tree`, en este caso `tree` es el *tag* que le asigne a otro comando que es mas largo, usando este *tag* ahorramos su escritura.

30. Ahora en caso de que tengamos un conflicto entre ramas, un ejemplo que otra persona halla modificado la misma linea de codigo que tu, si queremos *mergear* (unir ambas ramas) no podremos hacer, a continuacion esta el paso a paso para resolverlo:

![resolucion de conflictos](Images/51-%20resolucion%20de%20conflictos.png)


32. `git stash`: Guarda temporalmente los cambios sin afectar ninguna rama, es decir, que si modificamos algo y no queremos hacer un commit ya que si queremos cambiar de rama o de version tendremos que si o si guardar estos cambios. Y si queremos recuperar los cambios que hicimos usamos `git stash pop`, pero una vez hagamos esto podremos hacer las respectivas modificaciones para luego si commitear.

![guardar cambios temporalmente](<Images/52- guardar temporalmente cambios.png>)

Y si quisieramos eliminar un stash usamos `git stash drop`, o si queremos ver la lista de stash guardado usamos `git stash list`


33. `git branch -d developer`: Nos sirve para eliminar ramas de nuestros repositorio.

![eliminar rama](<Images/53- eliminar ramas.png>)

**Nota**: Si quieres ver las ramas que hay en el repositorio usa simplemente `git branch`



34. `git reflog`: Nos sirve para ver todo el historial de cambios de nueztro repositorio.

![ver historial del repositorio](<Images/54- ver historial de los cambios del repositorio.png>)


35. Hemos eliminado la rama junto con todos los logs de esta pero todo los commits permanecen en esta por eso podremos volver a esta usando `checkout`.

![volver a los commits de la rama eliminada](<Images/55- volver a los commits de la rama eliminada.png>)

Como podemos observar en el *tree* los commits aun permanencen:
![commits permanecen](<Images/56- volver a la rama main.png>)


## Git Hub

Es la plataforma en linea basada en **git** dibde se guardaran nuestros repositorios de manera remota(en la nube). Aqui deberas crear tu cuenta con tu correo.

![pagina principal de git hub](<Images/57- pagina principal de git hub.png>)


1. Para crear un nuevo repositorio damos click en "**New**", aqui podremos asisnarle un nombre a nuestro repositorio, añadir un -gitignore, o añadir un archivo *README*. Tambien podremos verificar las licencias para subir nuestro proyecto. Finalmente damos click en "**Create repository**" 

![crear repositorio](<Images/58- crear nuevo repositorio.png>)

![repositorio creado](<Images/59- repositorio creado.png>)


2. Autenticacion con SSH:

- Documentacion de autenticacion:

![documentacion de autenticacion](<Images/60 documentacion de autenticacion.png>)

- Daz click en la parte superior izquierda en en el menú desplegae, y alli encontraremos toda la documentacion que lleguemos a requerir para autenticarnos en este caso nos centraremos en la seccion de "**Conexion con SSH**", mas especificamente en la subseccion "*Reenvio del agente SSH*"

![menu de autenticacion](<Images/61- menu de autenticacion.png>)

![agente SSH](<Images/62- agente de SSH.png>)

Alli se te dara el paso a paso para que puedas añadir esta autenticacion.


3. Repositorio remoto

-   Ahora creamos un nuevo repositorio con el nombre de nuestro proyecto en este caso va a ser "Hello git". 

![crear nuevo repo](<Images/63- crear nuevo repo Hello git.png>)


- Ahora entramos a consola y confirmamos que todo este actualizado con `git status` para luego ejecutar el siguiente comando: `git remote add origin <Link del repositorio de git hub>`.
Esto añadira nuestro repositorio remoto que se encuentra en *Git Hub*.

![añadir repositorio remoto](<Images/64- añadir repositorio remoto.png>)

- Ahora con el comando: `git push -u origin main`
Esto subira al repositorio remoto de *Git Hub*.

![subir al repositorio](<Images/65- subir al repositorio remoto en git hub.png>)

- Asi quedan nuestro ficheros subidos en *git Hub*.

![ficheros en repo de git hub](<Images/66- ficheros en el repositorio de git hub.png>)

-Añadir un *README.md* en *Git Hub*

![Añadir README.md](<Images/67- Añadir README.png>)

Aqui se crea un nuevo commit desde *Git hub* para añadir el README.
![nuevo commit para README](<Images/68- commit para README.png>)

4. Ahora modifico un fichero desde mi local y lo commiteo:
![Commitear ficheros modificados](<Images/69- Commitear fichero modificado.png>)

- Al hacer `git push` nos va generar error ya que no estamos sictronizados con el repo remoto por el README que hemos añadido alli, pero este solo se encuentra en remoto no en local.

![Error al hacer push](<Images/70- Error al hacer push.png>)

- Ahora usamos `git fetch`, lo que hara sera actualizar el repositorio local con la informacion mas reciente del remoto, pero este no modifica tus archivos ni tus ramas.
  
![git fetch](<Images/71- traer informacion mas reciente del repo remoto.png>)

- Hacemos un **merge** entre la rama local y la rama remota y ahora con `git pull` traemos estos cambios hechos en git hub a la rama local de git.

![traer los cambios de la rama remota a la local](<Images/72- traer los cambios de la rama remota a la rama local.png>) 


-Ahora ya podemos hacer `git push` a nuestra rama remota.

![Subir los cambios a rama remota](<Images/73- subir cambios a nuestra rama remota.png>)


5.  Si tenemos que trabajar con alguien nuevo y queremos que este tenga los mismos cambios de nosotros subidos al git hub, entonces podemos clonar nuestro repo remoto a uno local de otro usuario. Usamos `git clone <URL del repo remoto>`.
Podemos clonarlo usando HTTPS, SSH y CLI pero en mi caso lo voy a hacer por HTTPS.

![clonar repositorio](<Images/74- clonar repositorio.png>)

Ahora ya tendremos en nuestra otra maquina el mismo proyecto para trabajar en conjunto:
![ficheros clonados](<Images/75- ficheros clonados.png>)






  

  





