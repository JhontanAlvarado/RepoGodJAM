# Trabajo individual

Jhonatan Alvarado Mamani

# <- Un numeral es un Titulo

##Clase 1 Apuntes <- Dos numerales es un subtitulo

### <- Tres numerales es subsubtitulo

Git es un sistema de control de versiones <- texto normal
creado por Linus Torvalds GOD.

### <- Esto es otro subsubtitulo

....

```
sudo apt instal git
```
las comillas son para crear bloques de codigo yeah.


##Apuntes clase 2  

###Directorio de trabajo
Untraked sin seguimiento
Modified modificacion 


.gitignore para igonrar archivos

##Comandos
git add <archivo> agrega un archivo al staged area
git add . agrega todos los archivos al staged area
gid restore --staged <archivo> para volver al estado anterior

##Commit punto de guardado, todos los cambios pasan al historial
git commint -m"mensaje" 
git reset --soft HEAD-1 volver al ultimo commit

Commits atomicos
Maximo 50 caracteres
Usar Verbos imperativos(Add, Change, Fix, Remove)
Usar prefijos (feat, fix, perf, build, ci, docs, refactor, style, test)


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
