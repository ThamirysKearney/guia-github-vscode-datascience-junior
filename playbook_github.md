# 🐙 Playbook: Control de Versiones con Git y GitHub

Este Playbook es tu salvavidas para trabajar con Git. Aquí centralizamos cómo guardar tus cambios, enviarlos a la nube y cómo salir vivo cuando cometes un error.

---

## 🌱 1. Iniciar tu Repositorio

Si creas una carpeta nueva localmente y quieres que Git comience a observarla:

```bash
# Iniciar Git (Solo 1 vez por proyecto)
git init
```

### Vincular a GitHub (Solo 1 vez por proyecto)
Crea el repositorio vacío en la página web de GitHub y luego ejecuta:
```bash
# 1. Conecta tu PC con la nube
git remote add origin https://github.com/tu-usuario/tu-repo.git

# 2. Sube la rama principal (main o master)
git push -u origin main
```

---

## 🔄 2. El Ciclo de Guardado Básico

El flujo de trabajo personal es un ciclo que se repite cientos de veces durante el proyecto:

```bash
# 1. Revisa qué archivos has modificado o creado
git status

# 2. Añade los archivos validados a la zona de preparación (staging)
git add .                    # Añade TODO
git add analisis_final.py    # Añade solo ese archivo

# 3. Empaqueta todo en un "Commit" (Punto de guardado)
git commit -m "feat: añadir análisis exploratorio completo de ventas"
```

---

## 📝 3. Nomenclatura Profesional de Commits

En equipos profesionales (y en gran parte de la industria), se usa "Conventional Commits".  
El formato es: `tipo: descripción corta y clara (en inglés recomendado)`

| Tipo | Cuándo usarlo | Ejemplo |
| :--- | :--- | :--- |
| `feat:` | Añades nueva funcionalidad o gráfico | `feat: build sales bar chart` |
| `fix:` | Corriges un error o métrica mala | `fix: correct null handling in parser` |
| `docs:` | Cambios exclusivos en comentarios o Markdown | `docs: update setup steps in README` |
| `data:` | Modificas algo relativo a ingesta de datos | `data: load Q3 financial records` |
| `chore:` | Tareas rutinarias, dependencias o limpieza | `chore: clean repo structure` |
| `refactor:` | Mejoras código interno sin cambiar lo externo | `refactor: simplify data loader loop` |

---

## 🚨 4. Emergencias de Git (¡Socorro!)

Tranquilo, en Git todo error tiene solución excepto si borras la carpeta física de tu disco duro. 

| Quiero... | Comando Salvador | Qué hace |
| :--- | :--- | :--- |
| **Editar último mensaje** | `git commit --amend -m "nuevo mensaje"` | Sobrescribe el texto del último commit local. |
| **Deshacer un `git add .`** | `git reset nombre_archivo` | Lo saca de la zona "staging". ¡No borra tus archivos! |
| **Deshacer un PUSH mal hecho** | `git revert HEAD` | Crea un commit nuevo que hace exactamente lo contrario al anterior. Es la forma más madura de deshacer algo en GitHub. |
| **Deshacer cambios locales** | `git checkout -- nombre_archivo` | Borrará todo lo que no hayas commiteado de ese archivo. |
| **Borrar último commit (Soft)** | `git reset --soft HEAD~1` | Elimina el bloque del commit pero tus modificaciones siguen en tus archivos. |
| **Borrar último commit (Hard)** | `git reset --hard HEAD~1` | **¡Peligro!** Borra el historial y tus propios archivos volverán al pasado. |
| **Cancelar un Merge en curso** | `git merge --abort` | Si el comando pull/merge da conflicto, esto anula la acción. |
| **Añadir archivo olvidado** | `git add archivo && git commit --amend --no-edit` | Mete el archivo en tu commit previo sin alterar su título. |

---

## 🧩 5. Manejo de Submódulos Problemáticos
A veces, al copiar repositorios dentro de repositorios, Git detecta un "Submódulo" y la carpeta dejará de subirse a tu Github principal. Para integrarlo de nuevo a tu repositorio principal:

```bash
# 1. Quita el puntero invisible
git rm --cached -r nombre-del-submodulo

# 2. Elimina la carpeta oculta de Git de esa sub-carpeta
rm -rf nombre-del-submodulo/.git

# 3. Vuelve a añadirlo como si fuera una carpeta tuya normal
git add nombre-del-submodulo

# 4. Haz un commit de limpieza
git commit -m "chore: remove submodule and track as normal files"
```

> **Buenas Prácticas:** 
> - Haz commits pequeños y atómicos. No guardes mil cambios distintos bajo un solo `git commit -m "varios cambios"`.
> - Antes de pushear un commit, asegúrate de que el proyecto sigue ejecutándose (los tests pasan, tu notebook no se rompe).
