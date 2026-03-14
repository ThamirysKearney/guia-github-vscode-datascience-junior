# 💻 Playbook: Terminal y Manejo de Archivos

Para trabajar de forma profesional en Data Science, la terminal (Bash) es mi teclado principal. Aquí anoto los movimientos que me ahorran horas de ratón.

---

## 🏗️ 1. Estructura de Proyecto Express
Cuando empiezo desde cero, no creo las carpetas a mano. Uso comandos:

```bash
# 1. ¿Dónde estoy?
pwd

# 2. Voy a mi zona de trabajo
cd ~/Desktop/Proyectos

# 3. Creo el proyecto con sus subcarpetas PRO de un golpe
mkdir -p mi-proyecto-data/{data/{raw,processed},notebooks,src,models,docs}

# 4. Entro y abro VS Code
cd mi-proyecto-data
code . -r
```

## 📄 2. Creación Rápida de Archivos Escenciales
Uso el comando `touch` para crear los pilares del proyecto sin quitar las manos del teclado:

| Archivo | Propósito | Comando en Terminal |
| :--- | :--- | :--- |
| `README.md` | Documentación del proyecto | `touch README.md` |
| `requirements.txt` | Librerías necesarias | `touch requirements.txt` |
| `.gitignore` | Evita subir basura (pycache, .env) | `touch .gitignore` |
| `.env` | Variables secretas (nunca subir) | `touch .env` |
| `config.py` | Parámetros y rutas centralizadas | `touch config.py` |
| `analysis.py` | Lógica principal y cálculos | `touch analysis.py` |
| `notebook.ipynb` | Exploración de datos y experimentos| `touch notebook.ipynb` |
| `datos.csv` | Almacenamiento local de datos | `touch datos.csv` |

## 📂 3. Gestión de Archivos (Mover y Renombrar)
El comando `mv` (move) sirve para ambas cosas:
```bash
# Cambiar nombre (renombrar)
mv borrador.ipynb analisis_final.ipynb

# Mover a otra carpeta
mv datos.csv data/raw/
```

## 📋 Tabla de Referencia Rápida: Bash (Terminal)
| Comando Bash | Acción | Ejemplo |
| :--- | :--- | :--- |
| `pwd` | Ver en qué ruta estoy | `pwd` |
| `ls -lh` | Listar archivos con tamaño | `ls -lh` |
| `mkdir -p` | Crear estructura de carpetas | `mkdir -p src/data src/models` |
| `cat archivo` | Ver contenido sin abrir | `cat README.md` |

## 🚀 4. Comandos de Supervivencia Bash
| Comando | Acción | Ejemplo de uso |
| :--- | :--- | :--- |
| `ls -lh` | Ver archivos y cuánto pesan | `ls -lh data/raw` |
| `cat` | Ver qué hay dentro de un archivo rápido | `cat requirements.txt` |
| `history`| Ver qué comandos escribí antes | `history | grep git` |
| `clear` | Limpiar la pantalla cuando hay caos | `clear` |

---

## 💡 Secretos de Experiencia (Tips Pro)
- **Tabulador (Tab):** Nunca escribo los nombres de las carpetas enteros. Escribo las primeras letras y pulso `Tab`. Si hay varias, pulso `Tab` dos veces para que me dé opciones. Ahorra errores de escritura.
- **Flechas Arriba/Abajo:** Uso las flechas del teclado para recuperar comandos que ya escribí. No vuelvo a escribir rutas largas.
- **Rutas Relativas vs Absolutas:** Siempre trabajo en rutas relativas (empezando con `./`). Si uso rutas absolutas (`C:/Users/...`), mi código no funcionará en la computadora de un colega.
- **Rutas UNIX vs Windows (Git Bash):** 
    - ⚠️ En **Git Bash** (MinGW), las rutas son estilo UNIX: `/c/Users/USUARIO/...`.
    - En **PowerShell/Sistemas Windows**, se usa: `C:\Users\USUARIO\...`.
    - Entender esto es vital para que mis comandos no fallen por una barra invertida.
- **El miedo a la terminal:** Al principio asusta, pero la terminal es la única forma de procesar miles de archivos de golpe. Es mi herramienta de automatización.
