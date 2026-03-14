# 🤝 Playbook: Flujo de Trabajo en Equipo y Buenas Prácticas

Saber escribir código es solo el 30% del trabajo. El otro 70% es cómo colaboro, comunico y comparto ese código. Este Playbook define las pautas para trabajar en proyectos con otros desarrolladores, data scientists y analistas, etc. independientemente de la herramienta (Jupyter, VS Code, Airflow, etc.).

---

## 🌿 1. Política de Ramas (Branching Flow)

### ⚡ Ciclo de vida de mi rama
1. **Nace para una misión:** Creo la rama desde `develop` para una tarea específica (ej: `feature/limpieza-ventas`).
2. **Trabajo continuo:** Al final de mi jornada, hago commit y push. Si la tarea lleva varios días, cada mañana hago un `git pull origin develop` para mantenerme al día con lo que hicieron mis colegas sin salirme de mi rama.
3. **Misión cumplida:** Una vez que termino y el equipo aprueba mi código en el Pull Request, hago el **Merge** y **borro mi rama** para no dejar rastro.

**Regla de Oro: ¡NUNCA TRABAJO EN `main`!**
- `main` (o `master`) siempre tiene el código validado que se puede mostrar (poner en producción).
- `develop` o `stage` o `staging` o `dev` es la rama donde se une el trabajo de todo el equipo.
- Yo trabajo siempre en ramas separadas que salen de `develop` (o de `main`en proyectos pequeños). 

### 1.1 La Regla de Oro: Las ramas están ligadas a "Tareas", no a "Días"

El estándar de la industria (*GitHub Flow* o *Git Flow*) dicta que el ciclo de vida de tu rama debe coincidir con el tiempo que tardes en terminar una tarea (ej: crear un gráfico, limpiar datos). 

**¿Cómo funciona el ciclo de vida de una rama?**
1. **Nace para una misión:** Creas la rama desde `develop` para tu tarea específica.
2. **El trabajo continuo:** Al final de tu jornada, haces commit y push de tus cambios. Al día siguiente, haces pull de `develop` para actualizarte, y sigues trabajando **en la misma rama**.
3. **La rama muere y desaparece:** Una vez que terminas la tarea y es aprobada por tus compañeros en un *Pull Request*, aplicas el "Merge" hacia `develop`. ¡En ese momento tu misión termina y debes **eliminar tu rama** para no acumular basura!

### 1.2 Empezando a trabajar
```bash
# Crear tu propia rama y moverte a ella (Usa features/, fix/, chore/ etc)
git checkout -b feature/mi_modelo_ventas
```

### 1.3 El camino seguro para subir tu trabajo
Antes de pedir a tus colegas que empalmen tu código, debes asegurarte de que tu rama está al día con la versión del resto del equipo. Es decir:

```bash
# 1. Trae lo último que hayan subido tus compañeros a develop (Prevención de conflictos)
git pull origin develop

# (Si hubiera conflictos, resuélvelos en tu editor)

# 2. Empaqueta tu trabajo diario
git add .
git commit -m "feat: entrenar random forest predictor mensual"

# 3. Sube tu rama a la nube
git push origin feature/mi_modelo_ventas
```

---

## 📩 2. Pull Requests (La Ceremonia de Revisión)

¡Peligro! 🚨 **NUNCA debes hacer un `git push origin develop` directamente a las ramas principales.** En ambientes profesionales estas ramas están protegidas. El único camino para que tu código entre allí es hacer un "Pull Request" (PR) o "Merge Request" (MR).

Un PR es una solicitud formal en GitHub/GitLab que dice: *"Equipo, he terminado esto, ¿podemos juntarlo a develop?"*

**Pasos de un PR Excelente (En la Nube de GitHub/GitLab):**
1. **Título Descriptivo:** Claro, que se entienda la meta final (ej. `[Feature] Dashboard de Ventas Q4`).
2. **Descripción:** 
   - ¿Qué problema resuelve este código?
   - ¿A qué ticket (Jira, Trello) corresponde?
   - Linkea capturas de pantalla si modificaste algo visual o una gráfica.
3. **Revisión en Parejas (Code Review):** Nunca apruebes tu propio PR. Pídele la revisión cruzada a un colega y sé abierto al feedback. Es el paso crucial para mejorar tu código y no romper `develop`.
4. **Merge (La Fusión):** Una vez aprobado, presionas el botón verde de "Merge pull request" en la página web. **¡En este exacto instante es cuando tu código entra por fin a `develop` en la nube!**

### 2.1 Mantenimiento en tu PC (Después del Merge)

Como tu código ya se fusionó en la web, tu ordenador se quedó desactualizado. Siempre que termines un PR en la web, vuelve a tu terminal y aplica esta limpieza:

   ```bash
# 1. Me cambio a la rama develop de mi ordenador
   git checkout develop

# 2. Me bajo la nueva versión (que ahora ya incluye mis cambios fusionados)
   git pull origin develop

# DOUBLE CHECK - compruebo que mis cambios nuevos de esa rama estan en la develop. 

# 3. Repo local - Borro mi rama de trabajo vieja porque ya no sirve (misión cumplida)
git branch -d feature/vieja-funcionalidad

# 4. Vuelvo a la develop
git switch develop 

# 5. Repo en la nube - Elimino la misma rama de GitHub
git push origin --delete feature/vieja-funcionalidad

   ```

---

## 🏆 3. Checklist de Fin de Jornada

Nunca dejes tu ordenador un viernes (ni ningún día) sin asegurarte de que tu avance está en el servidor. Si tu disco duro se rompe esa noche, no perderás ni un minuto trabajado.

1. ✅ `git status` ➡️ *"A ver, ¿qué archivos he modificado hoy? ¿Me falta alguno importante?"*
2. ✅ `git add .` ➡️ *"Vale, preparo todo lo de la sesión actual."*
3. ✅ `git commit -m "tipo: descripción en inglés"` ➡️ *"Empaqueto esto con sentido."*
4. ✅ `git push origin nombre-de-tu-rama` ➡️ *"Lo salvo en la nube para estar tranquilo/a."*

---

## 🧹 4. Buenas Prácticas Obligatorias y "Clean Code"

### Código y Notebooks
- **Evito celdas "basura":** Borrar los bloques de código rotos, las salidas irrelevantes, comentarios ofuscados o pruebas fallidas de los Notebooks antes de un commit.
- **Variables con Nombre Explícito:** Nombrar variables por lo que representan. En vez de `df1` o `tabla2`, usa `sales_Q3_df` o `cleaned_customer_base`. Mi código debe leerse como un libro.
- **DRY (Don't Repeat Yourself):** Si copio y pego 3 veces el código de hacer un bar chart, creo una función `plot_bar_chart()`.



### Trabajo en Equipo
- **Pregunto pronto:** Si me bloqueo más de 2 horas, pido ayuda. Es mejor dedicar 10 minutos de un senior que perder 8 horas frustrada.
- **Documento lo "extraño":** Si aplico una limpieza de datos compleja, lo explico en una celda de Markdown. No dejo que otro analista adivine qué hice.
- **Secretos fuera:** Nunca subo contraseñas ni llaves de APIs. Para eso uso el `.env` y el `.gitignore`.

---

## 💡 Secretos de Experiencia (Tips Pro)
- **El estado de la rama:** Cada mañana, antes de escribir una sola línea, hago `git pull origin develop`. Me ahorra tener que resolver conflictos gigantes al final de la semana.
- **La comunicación es clave:** Si voy a tocar un archivo que sé que otro colega también está usando, le aviso por Slack o Teams. Evitar el conflicto humano es más importante que evitar el conflicto de Git.
