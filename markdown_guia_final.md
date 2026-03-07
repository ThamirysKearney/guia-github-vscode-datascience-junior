# 🚀 GUÍA PROFESIONAL: Git + VS Code para Data Science

Esta guía está diseñada para que puedas gestionar tus proyectos de datos de principio a fin de forma profesional, rápida y sin necesidad de ayuda externa.

---

## 📂 PARTE 1: Preparación del Terreno (VS Code + Terminal)

### 1. Crear una carpeta desde cero
Abre el VS Code. Si no ves la terminal abajo, presiona ``Ctrl + ` `` o ve a `Terminal -> New Terminal`. Asegúrate de que ponga **Bash** en el desplegable de la derecha.

```bash
# 1. Mira en qué carpeta estás ahora
pwd

# 2. Muévete al Escritorio (o la carpeta que prefieras)
cd ~/Desktop

# 3. Crea la carpeta de tu nuevo proyecto (USA_ESTE_FORMATO)
mkdir proyecto-data-analyst

# 4. Entra en la carpeta
cd proyecto-data-analyst

# 5. Abre VS Code dentro de esa carpeta
code . -r
```

### 2. Crear archivos esenciales (Comandos rápidos)
Para crear archivos rápidamente sin usar el ratón, usa el comando `touch` en la terminal:

| Archivo a crear | Comando en la Terminal | Uso común |
| :--- | :--- | :--- |
| **Notebook Python** | `touch notebook.ipynb` | Análisis de datos y experimentos |
| **Script Python** | `touch main.py` | Automatización y modelos |
| **Página Web** | `touch index.html` | Estructura de tu portfolio |
| **Estilos CSS** | `touch styles.css` | Diseño y colores |
| **Lógica JS** | `touch script.js` | Interactividad web |
| **Dataset CSV** | `touch datos.csv` | Almacenamiento de datos local |
| **Documentación** | `touch README.md` | Explicación del proyecto |

### 3. Cambiar el nombre de un archivo (Notebooks, Scripts, etc.)
Si necesitas renombrar un archivo (por ejemplo, de `borrador.ipynb` a `analisis_final.ipynb`), usa el comando `mv` (move):

```bash
# Formato: mv nombre_actual nombre_nuevo
mv borrador.ipynb analisis_final.ipynb
```
*💡 Consejo: Esto funciona para cualquier tipo de archivo (.py, .js, .csv, etc).*

---

## 🛠️ PARTE 2: Flujo Maestro de Git (Paso a Paso)

### 1. Iniciar el repositorio (Solo se hace 1 vez por proyecto)
```bash
git init
```

### 2. Guardar tus cambios (El ciclo que usarás siempre)
Imagina que has creado un archivo `analisis.ipynb`. Para guardarlo profesionalmente:

```bash
# A. Ver qué ha cambiado
git status

# B. Preparar el archivo (ponerlo en la "caja de salida")
git add .                    # Añade todo lo nuevo/modificado

# C. Crear el Commit (Guardado permanente con nombre)
git commit -m "feat: initial data cleaning of sales dataset"
```

### 3. Conectar con GitHub (Subir tus cambios a la nube)
Crea un repositorio vacío en GitHub. Copia la URL que te den y escribe en tu terminal:

```bash
# 1. Conecta tu PC con la nube
git remote add origin https://github.com/tu-usuario/tu-repo.git

# 2. Sube tus cambios por primera vez
git push -u origin main
```

---

## 🌿 PARTE 3: Ramas (El Superpoder del Data Scientist)
Nunca trabajes directamente en `main`. Crea ramas para experimentos o nuevas fases.

```bash
# 1. Crear una rama y saltar a ella
git checkout -b feature/visualizations

# 2. Hacer tus cambios y commits normales... (git add + git commit)

# 3. Subir la rama a GitHub
git push origin feature/visualizations

# 4. Volver a la rama principal y traer los cambios (Merge)
git checkout main
git merge feature/visualizations
```

---

## ⚠️ PARTE 4: ¡Socorro! Deshacer y Editar

Aquí tienes cómo solucionar los errores más comunes. Recuerda: **en Git, casi todo tiene marcha atrás.**

### Tabla de "Emergencias"
| Acción | Comando | ¿Cuándo usarlo? |
| :--- | :--- | :--- |
| **Editar último mensaje** | `git commit --amend -m "nuevo mensaje"` | Cuando te equivocas al escribir el mensaje del último commit. |
| **Editar un commit antiguo** | `git rebase -i HEAD~3` | Para editar, juntar o borrar commits de hace unos días (avanzado). |
| **Deshacer `git add`** | `git reset nombre_archivo` | Sacas un archivo de la "caja de salida" sin borrar tus cambios. |
| **Deshacer cambios locales** | `git checkout -- nombre_archivo` | Vuelves el archivo a como estaba en el último commit (borras lo nuevo). |
| **Deshacer último commit** | `git reset --soft HEAD~1` | Borras el "recuadro" del commit pero mantienes tus archivos escritos. |
| **Deshacer un PUSH** | `git revert HEAD` | Crea un nuevo commit que "anula" el anterior en GitHub (forma segura). |
| **Deshacer un PULL** | `git reset --hard ORIG_HEAD` | Si al bajar cambios se rompe todo, vuelve a como estabas antes del pull. |
| **Deshacer un MERGE** | `git merge --abort` | Si hay conflictos al unir ramas y quieres cancelar la operación. |

### Explicación rápida de conceptos:
- **`Soft Reset`**: Solo borra el historial, tus archivos no cambian. Es como si nunca hubieras dado a "guardar".
- **`Hard Reset`**: Borra el historial Y los archivos. Úsalo solo si quieres destruir tus cambios recientes.
- **`Revert`**: En lugar de borrar el pasado, crea un futuro donde el error se corrige. Es lo mejor para trabajos en equipo.

---

## 📋 PARTE 5: Tablas de Referencia Rápida

### Comandos Bash (Navegación y Carpetas)
| Comando | Acción | Ejemplo |
| :--- | :--- | :--- |
| `pwd` | Ver en qué carpeta estás | `pwd` |
| `ls` | Ver archivos de la carpeta actual | `ls` |
| `cd nombre` | Entrar en una carpeta | `cd Desktop/proyectos` |
| `cd ..` | Ir hacia atrás (subir nivel) | `cd ..` |
| `mkdir nombre` | **Crear carpeta nueva** | `mkdir mi-nuevo-analisis` |
| `mv viejo nuevo` | **Renombrar carpeta** | `mv proyecto_v1 proyecto_final` |
| `rm -rf nombre` | **Eliminar carpeta** (permanente) | `rm -rf carpeta_basura` |
| `clear` | Limpia la consola | `clear` |

### Resumen de Comandos Git
| Comando | Función |
| :--- | :--- |
| `git init` | Crea un repo nuevo |
| `git status` | Mira qué archivos has tocado |
| `git add .` | Prepara todos los cambios para guardar |
| `git commit -m "..."` | Guarda los cambios en el historial |
| `git push` / `git pull` | Sube cambios / Baja cambios de la nube |
| `git log --oneline` | Mira tu historial de commits resumido |

---

## 📝 PARTE 6: Nomenclatura Profesional de Commits (Estándar España)

En el mundo de los datos, los mensajes deben ser claros. Formato: `tipo: descripción corta`.

- **`feat:`** Nueva funcionalidad (ej: un nuevo gráfico).
- **`fix:`** Corregir un error (ej: un cálculo mal hecho).
- **`docs:`** Cambios en documentación o README.
- **`data:`** Cambios en datasets o carga de datos.
- **`chore:`** Tareas rutinarias (limpiar carpetas).
- **`refactor:`** Limpiar código sin añadir nada nuevo.

**Regla de Oro:** Mensajes en **inglés** y tipo en **minúsculas**.

---

## 🏆 Checklist de Fin de Jornada
1. `git status` (Revisar).
2. `git add .` (Preparar).
3. `git commit -m "tipo: descripción"` (Guardar).
4. `git push origin nombre-de-tu-rama` (Subir).
