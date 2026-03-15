# 🚀 Playbook: Dominando VS Code y la Terminal

Bienvenido al Playbook exclusivo sobre el uso de **Visual Studio Code (VS Code)** y la línea de comandos (Bash/Terminal). Este documento te servirá como guía rápida para moverte como un profesional, sin depender del ratón y siguiendo las mejores prácticas corporativas.

---
## 0. Continuar trabajando 
**I. ver donde estoy** pwd
**II. voy al proyecto** cd nombre-del-proyecto
**III. miro el contenido de la carpeta** ls 

## 1. actualizo la rama base (develop o main)
**IV. voy a la rama base** git switch/checkout develop
**V. traigo los ultimos cambios del remoto** git pull origin develop/main

## 2. Creo la nueva rama de trabajo
**VI. Creo una nueva rama para la tarea** git switch -c feature/nueva-tarea

## 3. Realizo cambios 
**VII. Editar o crear archivos** guardo cambios (ctrl + s)
**VIII. Ver cambios realizados** git status 

## 4. Preparo commit 
**IX. Añadir archivos al staging area** git add .
o git add archivo.py
**X. Crear commit** git commit -m "feat: what I´ve done in imperative voice"

## 5. Subir cambios al remoto
**Subir la rama al repositorio remoto** git push origin feature/nueva-tarea

## Flujo final simplificado

cd proyecto
git switch develop
git pull origin develop
git switch -c feature/nueva-tarea

# editar archivos

git status
git add .
git commit -m "feat: descripción del cambio"
git push origin feature/nueva-tarea



## 💻 1. Preparación del Terreno

### 1.1 Abrir VS Code y la Terminal
- Al abrir VS Code, asegúrate siempre de tener la terminal visible.
- **Atajo:** Presiona ``Ctrl + ` `` o `Ctrl + j`ve al menú superior: **Terminal -> New Terminal**.
- **Atajo para abrir chat IA VS code:** ``Ctrl + alt + i`` 
- **Tipo de Terminal:** Verifica que en el menú desplegable (a la derecha de la ventana de terminal) esté seleccionado **Bash** (Git Bash) o **PowerShell** si trabajas en Windows.

> ⚠️ **Buenas Prácticas:** 
> - En Git Bash (basado en UNIX), las rutas se ven así: `/c/Users/USUARIO/Desktop`.
> - En PowerShell se ven así: `C:\Users\USUARIO\Desktop`.
> - Acostúmbrate a usar rutas relativas para que tu código funcione en los ordenadores de cualquier compañero de equipo.

---

## 📁 2. Gestión de Carpetas y Proyectos

### 2.1 Crear un proyecto desde cero
Demuestra profesionalidad creando tu entorno desde la consola en lugar de navegar con el explorador de archivos manual.

```bash
# 1. Verifica dónde te encuentras
pwd

# 2. Navega a tu espacio de trabajo (ej. Escritorio)
cd ~/Desktop

# 3. Crea la carpeta de tu nuevo proyecto (Usa guiones o guiones bajos)
mkdir proyecto-data-analyst

# 4. Entra en esa carpeta
cd proyecto-data-analyst

# 5. ¡Abre VS Code automáticamente en esa nueva ruta!
code . -r
```

---

## 📄 3. Archivos Esenciales y Creación Rápida

Para crear archivos rápidamente sin tocar el ratón, utiliza el comando `touch`. Aquí tienes una lista de los archivos más comunes y su propósito:

| Archivo | Propósito | Comando en Terminal |
| :--- | :--- | :--- |
| `README.md` | Documentación del proyecto | `touch README.md` |
| `requirements.txt` | Librerías necesarias | `touch requirements.txt` |
| `.gitignore` | Evita subir basura (`__pycache__`, `.env`) | `touch .gitignore` |
| `.env` | Variables secretas (contraseñas, URIs) | `touch .env` |
| `config.py` | Parámetros y rutas centralizadas | `touch config.py` |
| `analysis.py` | Script con lógica principal | `touch analysis.py` |
| `notebook.ipynb` | Experimentación y EDA | `touch notebook.ipynb` |
| `datos.csv` | Almacenamiento local | `touch datos.csv` |

### 3.1 Cambiar nombres y mover archivos
Nunca más hagas "Clic derecho -> Renombrar". Utiliza `mv` (Move):

```bash
# Formato: mv archivo_viejo archivo_nuevo
mv borrador.ipynb analisis_final.ipynb

# Mover a otra carpeta:
mv datos.csv data/processed/datos.csv
```

---

## 📋 4. Comandos Bash (Referencia Rápida)

Estos son los comandos de navegación que usarás todos los días. ¡Apréndelos de memoria!

| Comando | Acción | Ejemplo |
| :--- | :--- | :--- |
| `pwd` | Ver en qué ruta exacta estás | `pwd` |
| `ls -lh` | Listar archivos mostrando su tamaño | `ls -lh` |
| `cd ruta` | Entrar en una carpeta | `cd data/raw` |
| `cd ..` | Ir hacia atrás (subir un nivel) | `cd ..` |
| `mkdir -p` | Crear estructura de carpetas anidadas | `mkdir -p src/data/raw` |
| `rm -rf` | Eliminar carpeta y su contenido (¡Peligro!) | `rm -rf carpeta_temporal` |
| `cat` | Ver contenido de un archivo sin abrir el editor | `cat README.md` |
| `clear` | Limpia la pantalla de la terminal | `clear` |

---

## 💻 5. Operaciones de Git desde la Terminal (Git Bash)

Dado que usarás la terminal de VS Code de forma constante, aquí tienes las recetas para las acciones más comunes administrando de tu control de versiones:

### 5.1 Eliminar un archivo sobrante en una rama (y en remoto)
Si por error un archivo aparece en una rama donde no debe estar (ej: `README.md` que solo debería estar en `main`), así es como se borra para siempre usando los comandos de Bash:

```bash
# 1. Asegúrate de estar en la rama donde quieres eliminar el archivo
git checkout nombre_de_tu_rama

# 2. Elimina el archivo (Esto lo borra de tu PC y avisa a Git a la vez)
git rm nombre_del_archivo.extensión

# 3. Crea el commit como acción de limpieza
git commit -m "chore: remove unwanted file from branch"

# 4. Súbelo a la nube (GitHub/GitLab/Bitbucket)
git push origin nombre_de_tu_rama
```
*(Nota: Estos comandos son exactamente los mismos independientemente de si el código se guarda en GitHub, GitLab o Bitbucket).*

### 5.2 Cambiar el nombre a una rama de Git
Si te equivocaste al teclear el nombre de tu rama al crearla (ej: ibas a poner `feature/ventas` y pusiste `feattur/ventass`), haz esto en tu terminal:

```bash
# Opción A: Si ya estás posicionado dentro de la rama mal escrita
git branch -m feature/nuevo_nombre_correcto

# Opción B: Si estás en otra rama y quieres cambiarle el nombre desde fuera
git branch -m feattur/ventass feature/nuevo_nombre_correcto
```
**Importante:** Si la rama con el nombre "feo" ya la habías subido a la nube (`git push`), tendrás que empujar la rama nueva y borrar la antigua en remoto:
```bash
git push origin -u feature/nuevo_nombre_correcto
git push origin --delete feattur/ventass
```

---

## 💡 Buenas Prácticas de Trabajo en el Editor

1. **Mantén tu espacio limpio:** No dejes decenas de archivos `sin_titulo.py` abiertos.
2. **Usa Extensiones Inteligentemente:** Instala soporte para Python, Jupyter, gitlens, pre-prettier, etc. Pero no lo sobrecargues; un editor lento no ayuda.
3. **Formateo Automático:** Configura VS Code para que formatee tu código al guardar (Format on Save). Ahorrarás horas en discusiones sobre si usar espacios o tabulaciones.
4. **Estructura Modular:** A medida que los notebooks crezcan, extrae las funciones comunes a scripts `.py` (como `cleaning.py` o `utils.py`) y llámalos desde el notebook.
