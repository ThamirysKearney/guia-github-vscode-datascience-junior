# 🤝 Playbook: Flujo de Trabajo en Equipo y Buenas Prácticas

Saber escribir código es solo el 30% del trabajo. El otro 70% es cómo colaboras, comunicas y compartes ese código. Este Playbook define las pautas para trabajar en proyectos con otros desarrolladores, data scientists y analistas, independientemente de la herramienta (Jupyter, VS Code, Airflow, etc.).

---

## 🌿 1. Política de Ramas (Branching Flow)

La Regla de Oro en equipos profesionales: **¡NUNCA TRABAJES EN `main`!**
- `main` (o `master`) siempre alberga código validado que se puede poner en producción.
- `develop` o `staging` es la rama donde se unen todos los features de los miembros del equipo.
- Tú trabajarás siempre en ramas separadas que salen de `develop` (o de `main` en proyectos pequeños).

### 1.1 Empezando a trabajar
```bash
# Crear tu propia rama y moverte a ella (Usa features/, fix/, chore/ etc)
git checkout -b feature/mi_modelo_ventas
```

### 1.2 El camino seguro para subir tu trabajo
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

Un Pull Request (PR) o Merge Request (MR) es una solicitud formal en GitHub/Gitlab/Bitbucket que dice: *"Equipo, he terminado esto, ¿podemos juntarlo a develop?"*

**Pasos de un PR Excelente:**
1. **Título Descriptivo:** Claro, que se entienda la meta final (ej. `[Feature] Dashboard de Ventas Q4`).
2. **Descripción:** 
   - ¿Qué problema resuelve este código?
   - ¿A qué ticket (Jira, Trello) corresponde?
   - Linkea capturas de pantalla si modificaste algo visual o una gráfica.
3. **Revisión en Parejas (Code Review):** Nunca apruebes tu propio PR. Pídele la revisión cruzada a un colega y sé abierto al feedback. Es el paso crucial para mejorar tu código y no romper `develop`.
4. **Merge:** Cuando tengas aprobación, júntalo (Merge) y elimina inmediatamente la rama `feature/mi_modelo_ventas` para no generar basura acumulada en el repositorio.

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
- **Evita celdas "basura":** Borra los bloques de código rotos, las salidas irrelevantes o comentarios ofuscados de los Notebooks antes de un commit.
- **Variables con Nombre Explícito:** Nombra variables por lo que representan. En vez de `df1` o `tabla2`, usa `sales_Q3_df` o `cleaned_customer_base`.
- **DRY (Don't Repeat Yourself):** Si copias y pegas 3 veces el código de hacer un bar chart, crea una función `plot_bar_chart()`.

### Trabajo en Equipo
- **Dudas Rápidas:** Si te quedas atascado más de 1-2 horas, **pregunta**. Es más barato para el equipo invertir 10 minutos de ayuda que 8 horas de tu frustración.
- **Evita la "Caja Negra":** Si en tu análisis aplicaste una limpieza muy exótica que elimina el 20% de los datos sin documentarlo, otro Data Analyst no entenderá nada. Explícalo en un `markdown` intermedio dentro del `.ipynb`.
- **Los Secretos fuera de los Commits:** NUNCA subas a GitHub un archivo que contenga contraseñas, URIs de bases de datos de producción real, ni información confidencial de clientes. Usa un `.env` y el `.gitignore`.
