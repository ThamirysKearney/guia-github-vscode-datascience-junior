# 🐙 Playbook: Guía Maestra de Git y GitHub

Git no es solo para guardar archivos, es la "máquina del tiempo" y el pilar de la colaboración profesional. Aquí unifico todas las notas sobre el flujo de trabajo para tener el control absoluto de los proyectos.

---

## 1️⃣ Conceptos Fundamentales
- **Git (Local):** Es el software en la computadora que rastrea los cambios. Es mi diario privado.
- **GitHub (Cloud):** Es el servidor en la nube donde comparto el trabajo con el equipo. Es el escaparate público.

## 2️⃣ Iniciar el repositorio (Solo 1 vez por proyecto)
Cuando empiezo un proyecto desde cero, debo inicializar el rastreo de Git:
```bash
git init
```

## 3️⃣ Mi Flujo Diario Profesional (Ciclo de Vida)
Para evitar conflictos con los compañeros y mantener el orden, siempre sigo este orden:

1. **Traer lo último:**
   ```bash
   git pull origin develop  # Antes de empezar, me aseguro de tener lo que los colegas subieron.
   ```
2. **Crear el espacio (Rama de tarea):**
   ```bash
   git checkout -b feature/nueva-tarea  # Nunca trabajo en main/develop directamente.
   ```
3. **Guardar los avances (Staging & Commit):**
   ```bash
   git status  # Reviso qué he tocado.
   git add .   # Preparo los cambios para la "foto".
   git commit -m "feat: descripción clara"  # Registro el cambio en el historial.
   ```
4. **Subir a la nube:**
   ```bash
   git push origin feature/nueva-tarea
   ```

## 4️⃣ Colaboración: Pull Requests (PR)
Una vez subida la rama, el trabajo no termina ahí:
1. Voy a GitHub y abro un **Pull Request** desde `feature/nueva-tarea` hacia `develop`.
2. Espero a que un colega revise el código.
3. Tras la aprobación, se hace el **Merge**.
4. Finalmente, elimino la rama en local: `git branch -d feature/nueva-tarea`.

---

## 5️⃣ Emergencias (Botón del Pánico 🆘)
En Git casi todo tiene solución si mantengo la calma.

| Situación | Comando | Qué hace |
| :--- | :--- | :--- |
| **Error en el mensaje del commit** | `git commit --amend -m "nuevo"` | Cambia el último mensaje. |
| **Me olvidé de añadir un archivo** | `git add . && git commit --amend` | Lo mete en el último commit. |
| **Saqué el archivo equivocado** | `git reset nombre_archivo` | Lo quita de la zona de preparación. |
| **He roto todo (Volver atrás)** | `git revert HEAD` | Crea un commit que "deshace" el anterior de forma segura. |
| **Deshacer un PULL** | `git reset --hard ORIG_HEAD` | Si todo se rompe tras un pull, vuelves a como estabas. |
| **Conflictos al hacer PULL** | `git merge --abort` | Cancela el merge y deja todo como estaba. |

### 🚨 Explicación de los "Resets"
No todos los resets son iguales. Aquí anoto cuándo usar cada uno:
- **`Soft Reset` (`git reset --soft HEAD~1`)**: Quita el último commit pero mis archivos **NO cambian**. Es perfecto si quiero "rehacer" el mensaje del commit o juntar varios commits en uno solo.
- **`Hard Reset` (`git reset --hard HEAD~1`)**: Borra el historial Y los cambios de mis archivos. **¡Peligroso!** Solo lo uso si quiero descartar todo mi trabajo reciente y volver atrás de verdad.
- **`Revert` (`git revert HEAD`)**: Es la opción más profesional. No borra el historial, sino que crea un commit nuevo que hace lo contrario al anterior. Es lo más seguro si trabajo en equipo.

---

# 6️⃣ Casos Especiales (Submódulos y "Carpetas Fantasma")
Si alguna vez una carpeta parece un "Fantasma" (tiene un icono de carpeta pero no puedo entrar en ella en GitHub), es porque tiene un archivo `.git` dentro. Así lo soluciono:

```bash
# 1. Quito el rastro del submódulo de la memoria de Git
git rm --cached -r nombre-carpeta

# 2. Borro la carpeta oculta .git de adentro (Paso vital)
rm -rf nombre-carpeta/.git

# 3. Vuelvo a añadir como archivos normales
git add nombre-carpeta

# 4. Commit y push final
git commit -m "chore: remove submodule and track as normal files"
```

---

## 📋 Tabla de Referencia Rápida: Git
| Comando Git | Función |
| :--- | :--- |
| `git status` | Mira qué archivos he tocado |
| `git add .` | Prepara todos los cambios para guardar |
| `git commit -m "..."` | Guarda los cambios en el historial |
| `git log --oneline` | Mira mi historial de commits resumido |
| `git branch` | Mira en qué rama estoy trabajando |

---

## 💡 Secretos de Experiencia (Tips Pro)
- **Commit pequeño, commit seguro:** Prefiero hacer 10 commits pequeños que uno gigante. Si el 10º rompe algo, puedo volver al 9º fácilmente.
- **Push frecuente:** No espero al final del día. Si la computadora falla, el trabajo está a salvo en la nube.
- **Ramas descriptivas:** Uso nombres como `feature/limpieza-uci` en lugar de `tarea1`. Me ayuda a mí y al equipo a saber qué estamos haciendo de un vistazo.
- **Markdown es mejor que Notebooks:** Para documentar procesos, uso archivos `.md`. Se leen directamente en GitHub, se pueden buscar con buscadores de texto y no pesan casi nada.
- **Git Bash es el aliado:** En Windows, prefiero usar Git Bash porque me da los mismos comandos que usan los ingenieros en Linux/Mac, lo que unifica el lenguaje del equipo.
