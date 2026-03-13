# 📝 Playbook: Nomenclatura Profesional de Commits

En equipos profesionales (y en gran parte de la industria), se usa **Conventional Commits**. Es mi regla de oro para que el historial de mi proyecto sea legible y parezca el de un senior.

El formato que uso es: `tipo: descripción corta y clara (en inglés recomendado)`

---

## 🚀 Tipos y ejemplos de uso diario

### 1. `feat:` (Nueva funcionalidad)
Lo uso cuando añado algo nuevo al proyecto que antes no existía.
- `feat: add student dropout prediction model`
- `feat: build interactive dashboard for sales`
- `feat: add data cleaning script for UCI dataset`
- `feat: implement random forest classifier`

### 2. `fix:` (Corrección de errores)
Lo uso para arreglar algo que estaba roto o daba resultados incorrectos.
- `fix: correct null handling in data parser`
- `fix: resolve indentation error in eda.py`
- `fix: update deprecated pandas function`
- `fix: adjust x-axis labels in bar chart overlapping`

### 3. `docs:` (Documentación)
Lo uso exclusivamente para cambios en archivos Markdown o comentarios de código.
- `docs: update setup steps in README`
- `docs: add commit nomenclature guide`
- `docs: clarify data dictionary in notebook`
- `docs: translate technical notes to spanish`

### 4. `data:` (Gestión de datos)
Lo uso para cambios exclusivos en la captura, carga o almacenamiento de datasets.
- `data: load Q3 financial records from API`
- `data: update raw csv with latest results`
- `data: split train and test sets for validation`
- `data: clean duplicates from student records`

### 5. `chore:` (Tareas rutinarias)
Lo uso para limpiezas de carpetas, actualizaciones de librerías o cambios en el `.gitignore`.
- `chore: clean repo structure following pro architecture`
- `chore: update requirements.txt with new versions`
- `chore: add .venv to gitignore`
- `chore: remove old temporary scripts`

### 6. `refactor:` (Mejora de código)
Lo uso cuando mejoro el código por dentro pero el resultado final es el mismo (lo hago más legible o eficiente).
- `refactor: simplify data loader loop`
- `refactor: extract plot functions to separate module`
- `refactor: optimize memory usage in cleaning script`
- `refactor: rename variables to follow PEP8 style`

### 7. `style:` (Formato)
Lo uso para cambios que no afectan la lógia: espacios, puntos y coma, falta de comas, etc.
- `style: fix trailing whitespaces in main.py`
- `style: adjust code indentation`
- `style: remove unused imports`

---

## 💡 Secretos de Experiencia (Tips Pro)
- **Verbo en imperativo:** Siempre intento que la descripción empiece con un verbo (add, update, fix, remove) en lugar de "added" o "fixing".
- **Todo en minúsculas:** Es una convención estética muy común en Data Science.
- **Sin punto final:** Los mensajes de commit no necesitan punto al final, así son más rápidos de leer.
- **¿Por qué esto es clave?:** Si mañana entro en un equipo grande, el "Data Architect" o el "MLOps Engineer" podrá saber qué he estado haciendo sin necesidad de llamarme por teléfono. Es comunicación asíncrona profesional.
