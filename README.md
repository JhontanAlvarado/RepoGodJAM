# Trabajo individual

Jhonatan Alvarado Mamani

# <- Un numeral es un Titulo

##Clase 1 Apuntes <- Dos numerales es un subtitulo

## <- Dos numerales es subsubtitulo

Git es un sistema de control de versiones <- texto normal
creado por Linus Torvalds GOD.

### <- Esto es otro subsubtitulo

Instalar Git
```
sudo apt instal git
```

Las comillas son para crear bloques de codigo

----------------------------------------------------------

## Apuntes clase 2  

### Directorio de trabajo
Untraked sin seguimiento
Modified modificacion 

Para igonrar archivos
.gitignore 


### Comandos
agrega un archivo al staged area
```
git add <archivo> 
```
agrega todos los archivos al staged area
```
git add . 
```
para volver al estado anterior
```
gid restore --staged <archivo> 
```

### Commit punto de guardado, todos los cambios pasan al historial
```
git commint -m "mensaje" 
```
Volver al ultimo commit
```
git reset --soft HEAD-1 
```

### Buenas practicas para los commits
Commits atomicos
Maximo 50 caracteres
Usar Verbos imperativos(Add, Change, Fix, Remove)
Usar prefijos (feat, fix, perf, build, ci, docs, refactor, style, test)

----------------------------------------------------------

##Apuntes clase 3

### Git Hub repositorio remoto
Hay dos manera de vincular y subir el repositorio local a GitHub 

mediante SSH y HTTPS, es mejor usar SSH key

SHH se configura en GitHub, se necesita una key con el comando 

```
ssh-keygen -t ed25519 -C "correo@gmail.com"

```

Rama Main <- rama principal

Conectar repo local existente con uno a GitHub
```
git remote add origin git@github.com:User:Repo.git
```

Clonar repositorio
```
git clone "git@github.com:user:repo.git"
```

subir cambios
```
git push origin <rama>
```

bajar cambios
```
git pull origin <rama>
```

##Apuntes clase 4

Permite ver las urls donde apunta nustra repo
git remote -v 

Vincula repo local  con uno en la nube
gir remote add <apodo> "url" 

cambia la  url donde apunta nuestro repositorio
git remote set -url <apodo> "url" 


###Se puede configurar multiples ssh
Crear un archivo config para evitar conflicto
de keys
(ver diapositiva)

verificar que funciona
ssh -T git@github-miname


###Git Chekout
nos permite desplazar el HEAD hacia un punto
especifico  de la historia o a otra rama
Inspeccionar, Restaurar, Experimentar,Cambiar
Usar solo para "ver"

###Estado Detached HEAD
El HEAD esta desacoplado, apunta directamente a un commit
Espectador del pasado
No se tiene rama
Los cambios no "encarnados" se pierden

Para ir atras
git checkout <hashantiguo>

Volver al ultimo hash  de la rama
git checkout <rama>

Para guardar cambios  del "pasado,  encarnar"
git checkout <hashcommitcreado>
git checkout -b ramanueva

###Buenas practicas
No trabaja mucho tiempo en Detached HEAD
Limpiar el directorio de trabajo (add y commit)
Usarlo para aprender de proyectos grandes, como crecieron


##Apuntes clase 4 (Justificacion de falta)

### Ramas
Birfucacion  del estado del codigo que crea un nuevo camino 

###git Branch
Comando para gestionar ramas

###git branch 
Lista las ramas y muestra en que rama esta nustro HEAD

###git branch <rama> 
Crea una nueva rama a partir de la rama donde estamos

###git branch -D <rama>
Delete rama

###git checkout <rama>
Cambiar ramas

###git checkout -b <rama>
Crear y cambiar a esa rama

###git checkout  vs git switch
git checkout es multiproposito, cuidado
git switch es especializado para manejo de ramas


###gitflow basico
Flujo de trabajo, que tiene un marco de trabajo y convenciones 
que permite trabajar de manera ordenada en ramas

Ramas
main -> codigo que se encuetra en produccion 
develop -> rama ·pre-produccion· seran lanzadas pronto, probar del todo
ramas de apoyo -> codigo editable se divide en
 feature, se trabajan nuevas caracteristicas del proyecto
 realease, preparacion de un lanzamiento de una nueva version
 hotfix, cambios imprevistos, parches, bugs o problemas de produccion


###AQUI va la evidencia de motivo de falta a la clase####



##Apuntes clase 6

###git merge
Merge significa fusión, fusionar nuestras dos ramas en una sola

Con el flag –no-ff  significa no fast forward, fuerza a hacer un commit para el merge para guardarlo en el historial de commits

###git fetch
Verifica si hubo cambios en la rama y sus ramas hijas, avisa si hubo cambios

###git pull
Trae todos los cambios de la rama remota, si lo hubiera,(es como si lo actualizara), al repositorio local 

git pull origin rama

###git push
Sube los cambios del repositorio local al repositorio remoto

git push origin rama

Si el repositorio es ajeno para la primer push se pone el flag -u 
para que no tenga que pedir permiso para crear la rama.

git pull origin -u rama

##Flujo de trabajo (Sin Pull Requests)

git checkout develop
git fetch
git pull origin develop
git checkout rama
git merge develop # Solo si hubo cambios en develop

##Trabajas en tu rama
git push origin rama # Agregas -u si es la primera vez que subes cambios al repositorio remoto
git checkout develop
git fetch
git pull origin develop
git merge –no-ff rama

##Resuelves manualmente los archivos fallidos y sus conflictos
git add .
git commit
[Ctrl + O, Enter, Ctrl + X](depende si usan nano)
git branch -D rama
git push origin develop


##Clase 7

###Pull Request
Es una solicitud o aviso a los miembros del equipo
sobre mergear o  unir el codigo realizados en una rama a 
otra.

##Flujo de trabajo (Con Pull Requests)

git checkout develop
git fetch
git pull origin develop
git checkout rama # Agregas -b si estás creando la rama
git merge develop # Solo si hubo cambios en develop

### Trabajas en tu rama
git push origin rama # Agregas -u si es la primera vez que subes cambios al repositorio remoto
git checkout develop
git fetch
git checkout rama
git merge develop # Solo si hubo cambios en develop antes de hacer la PR

### Resuelves manualmente los archivos fallidos y sus conflictos
git add .
git commit
[Ctrl + O, Enter, Ctrl + X](depende si usan nano)
git push origin rama


Los PRs(Pull Request) se usan por temas de seguridad, notificando a los responsables de una solicitud de merge de una rama a otra, asi se podra revisar el codigo que se quiere unir evitando problemas, fallas o posibles ataques.

Esto da mayor manejo y garantiza mayor seguridad en trabajos colaborativos


Proteger los repositorios con limitacion de colaboracion es muy importante para moderar quienes y que aportes se mergean