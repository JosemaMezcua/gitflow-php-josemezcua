# gitflow-php-josemezcua

Paso 1: Creación del repositorio y configuración inicial
Crea un repositorio en GitHub con el nombre:
gitflow-php-[tu_nombre]

Clónalo en tu equipo local:

bash
Copiar
Editar
git clone https://github.com/tu_usuario/gitflow-php-tu_nombre.git
cd gitflow-php-tu_nombre
Inicializa Git Flow:

bash
Copiar
Editar
git flow init
Acepta las opciones por defecto.

Asegúrate de que la rama develop existe, si no, créala:

bash
Copiar
Editar
git checkout -b develop
git push origin develop
Entrega
URL del repositorio en GitHub.

Captura de git branch -a.

bash
Copiar
Editar
git branch -a
README.md con los pasos realizados.

Paso 2: Creación de un archivo PHP
Crea una nueva funcionalidad en Git Flow:

bash
Copiar
Editar
git flow feature start crear-mi-archivo
Dentro de una carpeta alumnos/, crea un archivo PHP:

bash
Copiar
Editar
mkdir -p alumnos
nano alumnos/tu_nombre.php
Contenido del archivo:

php
Copiar
Editar
<?php
// Archivo: alumnos/tu_nombre.php
echo "Hola, soy [Tu Nombre] y estoy aprendiendo Git Flow!";
?>
Confirma y sube los cambios:

bash
Copiar
Editar
git add alumnos/tu_nombre.php
git commit -m "Añadir archivo PHP con mi nombre"
git push origin feature/crear-mi-archivo
Finaliza la funcionalidad y fusiónala en develop:

bash
Copiar
Editar
git flow feature finish crear-mi-archivo
git push origin develop
Entrega
Captura del log de commits:

bash
Copiar
Editar
git log --oneline --graph
README.md explicando los pasos.

Paso 3: Modificación de index.php
Crea una nueva funcionalidad en Git Flow:

bash
Copiar
Editar
git flow feature start modificar-index
Modifica index.php agregando la línea:

php
Copiar
Editar
<?php
include "alumnos/tu_nombre.php";
?>
Antes de confirmar los cambios, muestra la diferencia:

bash
Copiar
Editar
git diff
Confirma y sube la funcionalidad:

bash
Copiar
Editar
git add index.php
git commit -m "Incluir mi archivo PHP en index.php"
git push origin feature/modificar-index
Finaliza la funcionalidad:

bash
Copiar
Editar
git flow feature finish modificar-index
git push origin develop
Entrega
Captura de git diff antes de confirmar.

README.md explicando los pasos.

Paso 4: Resolución de conflictos
Modifica index.php en la misma línea que otro compañero.

Realiza un merge en develop:

bash
Copiar
Editar
git checkout develop
git merge feature/modificar-index
Si hay un conflicto, usa git status para verlo:

bash
Copiar
Editar
git status
Edita index.php manualmente y resuelve el conflicto.

Añade y confirma los cambios:

bash
Copiar
Editar
git add index.php
git commit -m "Resolver conflicto en index.php"
git push origin develop
Entrega
Captura de git status mostrando el conflicto.

Captura del archivo index.php después de la resolución.

README.md explicando cómo resolviste el conflicto.

Paso 5: Eliminación de un archivo
Crea una nueva funcionalidad en Git Flow:

bash
Copiar
Editar
git flow feature start borrar-mi-archivo
Elimina tu archivo PHP:

bash
Copiar
Editar
rm alumnos/tu_nombre.php
git add alumnos/tu_nombre.php
git commit -m "Eliminar mi archivo PHP"
Sube los cambios y finaliza la funcionalidad:

bash
Copiar
Editar
git push origin feature/borrar-mi-archivo
git flow feature finish borrar-mi-archivo
git push origin develop
Entrega
Captura del log git log --oneline donde se vea la eliminación.

README.md explicando cómo eliminaste el archivo.

Paso 6: Publicación de la versión final
Crea una release en Git Flow:

bash
Copiar
Editar
git flow release start v1.0
Finaliza la versión y fusiónala en main:

bash
Copiar
Editar
git flow release finish v1.0
Etiqueta la versión final:

bash
Copiar
Editar
git tag -a v1.0 -m "Versión 1.0 estable"
git push origin --tags
Entrega
Comandos utilizados (git tag, git flow release finish, etc.).

README.md con los pasos para publicar una versión estable.
