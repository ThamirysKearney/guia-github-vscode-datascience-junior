# 🚀 Playbook: Dominando VS Code y la Terminal

Bienvenido al Playbook exclusivo sobre el uso de **Visual Studio Code (VS Code)** y la línea de comandos (Bash/Terminal). Este documento te servirá como guía rápida para moverte como un profesional, sin depender del ratón y siguiendo las mejores prácticas corporativas.

---

## 💻 1. Preparación del Terreno

### 1.1 Abrir VS Code y la Terminal
- Al abrir VS Code, asegúrate siempre de tener la terminal visible.
- **Atajo:** Presiona ``Ctrl + ` `` o ve al menú superior: **Terminal -> New Terminal**.
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
| `clear` | Limpiar la pantalla de la terminal | `clear` |

---

## 💡 Buenas Prácticas de Trabajo en el Editor

1. **Mantén tu espacio limpio:** No dejes decenas de archivos `sin_titulo.py` abiertos.
2. **Usa Extensiones Inteligentemente:** Instala soporte para Python, Jupyter, gitlens, pre-prettier, etc. Pero no lo sobrecargues; un editor lento no ayuda.
3. **Formateo Automático:** Configura VS Code para que formatee tu código al guardar (Format on Save). Ahorrarás horas en discusiones sobre si usar espacios o tabulaciones.
4. **Estructura Modular:** A medida que los notebooks crezcan, extrae las funciones comunes a scripts `.py` (como `cleaning.py` o `utils.py`) y llámalos desde el notebook.
