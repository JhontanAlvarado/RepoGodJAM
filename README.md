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

