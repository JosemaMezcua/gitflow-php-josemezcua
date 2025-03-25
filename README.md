# gitflow-php-josemezcua


# Uso de Git Flow en un Proyecto PHP

Este documento describe los pasos para configurar y utilizar Git Flow en un proyecto PHP.

---

## **Paso 1: Creación del repositorio y configuración inicial**

1. Crea un repositorio en GitHub con el nombre:
   ```
   gitflow-php-[tu_nombre]
   ```

2. Clónalo en tu equipo local:
   ```bash
   git clone https://github.com/tu_usuario/gitflow-php-tu_nombre.git
   cd gitflow-php-tu_nombre
   ```

3. Inicializa Git Flow:
   ```bash
   git flow init
   ```
   Acepta las opciones por defecto.

4. Asegúrate de que la rama `develop` existe, si no, créala:
   ```bash
   git checkout -b develop
   git push origin develop
   ```

### **Entrega:**
- URL del repositorio en GitHub.
- Captura de `git branch -a`:
  ```bash
  git branch -a
  ```
- README.md con los pasos realizados.

---

## **Paso 2: Creación de un archivo PHP**

1. Crea una nueva funcionalidad en Git Flow:
   ```bash
   git flow feature start crear-mi-archivo
   ```

2. Dentro de una carpeta `alumnos/`, crea un archivo PHP:
   ```bash
   mkdir -p alumnos
   nano alumnos/tu_nombre.php
   ```

3. Contenido del archivo:
   ```php
   <?php
   // Archivo: alumnos/tu_nombre.php
   echo "Hola, soy [Tu Nombre] y estoy aprendiendo Git Flow!";
   ?>
   ```

4. Confirma y sube los cambios:
   ```bash
   git add alumnos/tu_nombre.php
   git commit -m "Añadir archivo PHP con mi nombre"
   git push origin feature/crear-mi-archivo
   ```

5. Finaliza la funcionalidad y fusiónala en `develop`:
   ```bash
   git flow feature finish crear-mi-archivo
   git push origin develop
   ```

### **Entrega:**
- Captura del log de commits:
  ```bash
  git log --oneline --graph
  ```
- README.md explicando los pasos.

---

## **Paso 3: Modificación de `index.php`**

1. Crea una nueva funcionalidad en Git Flow:
   ```bash
   git flow feature start modificar-index
   ```

2. Modifica `index.php` agregando la línea:
   ```php
   <?php
   include "alumnos/tu_nombre.php";
   ?>
   ```

3. Antes de confirmar los cambios, muestra la diferencia:
   ```bash
   git diff
   ```

4. Confirma y sube la funcionalidad:
   ```bash
   git add index.php
   git commit -m "Incluir mi archivo PHP en index.php"
   git push origin feature/modificar-index
   ```

5. Finaliza la funcionalidad:
   ```bash
   git flow feature finish modificar-index
   git push origin develop
   ```

### **Entrega:**
- Captura de `git diff` antes de confirmar.
- README.md explicando los pasos.

---

## **Paso 4: Resolución de conflictos**

1. Modifica `index.php` en la misma línea que otro compañero.
2. Realiza un merge en `develop`:
   ```bash
   git checkout develop
   git merge feature/modificar-index
   ```
3. Si hay un conflicto, usa `git status` para verlo:
   ```bash
   git status
   ```
4. Edita `index.php` manualmente y resuelve el conflicto.
5. Añade y confirma los cambios:
   ```bash
   git add index.php
   git commit -m "Resolver conflicto en index.php"
   git push origin develop
   ```

### **Entrega:**
- Captura de `git status` mostrando el conflicto.
- Captura del archivo `index.php` después de la resolución.
- README.md explicando cómo resolviste el conflicto.

---

## **Paso 5: Eliminación de un archivo**

1. Crea una nueva funcionalidad en Git Flow:
   ```bash
   git flow feature start borrar-mi-archivo
   ```

2. Elimina tu archivo PHP:
   ```bash
   rm alumnos/tu_nombre.php
   git add alumnos/tu_nombre.php
   git commit -m "Eliminar mi archivo PHP"
   ```

3. Sube los cambios y finaliza la funcionalidad:
   ```bash
   git push origin feature/borrar-mi-archivo
   git flow feature finish borrar-mi-archivo
   git push origin develop
   ```

### **Entrega:**
- Captura del log `git log --oneline` donde se vea la eliminación.
- README.md explicando cómo eliminaste el archivo.

---

## **Paso 6: Publicación de la versión final**

1. Crea una release en Git Flow:
   ```bash
   git flow release start v1.0
   ```

2. Finaliza la versión y fusiónala en `main`:
   ```bash
   git flow release finish v1.0
   ```

3. Etiqueta la versión final:
   ```bash
   git tag -a v1.0 -m "Versión 1.0 estable"
   git push origin --tags
   ```

### **Entrega:**
- Comandos utilizados (`git tag`, `git flow release finish`, etc.).
- README.md con los pasos para publicar una versión estable.

---

