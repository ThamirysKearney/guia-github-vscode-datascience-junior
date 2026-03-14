# ⚙️ Playbook: Setup de Entorno

Aquí anoto los pasos y comandos que necesito la primera vez que configuro mi entorno de trabajo en una máquina nueva o cuando quiero resetear mi espacio para empezar de cero. Es la base para que todo lo demás funcione.

---

## 🚀 1. Configurar mi identidad en Git
Para que GitHub sepa quién soy cuando hago commits:
```bash
git config --global user.name "Mi Nombre"
git config --global user.email "mi-email@ejemplo.com"
```
*💡 Consejo: Verifico mi configuración con `git config --list`.*

## 💻 2. Configurar mi terminal visual (VS Code)
Prefiero usar **Git Bash** dentro de VS Code porque me da los mismos comandos que usan los ingenieros en Linux/Mac.
1. Abro la terminal con `Ctrl + `  o `Ctrl + j` .
2. En el desplegable de arriba a la derecha, elijo "Select Default Profile".
3. Selecciono **Git Bash**.

## 📦 3. Instalar mi stack básico de Python
En mi entorno global (o en mi `.venv`), estas son las librerías que casi siempre necesito para empezar a ver datos:
```bash
# Actualizo pip primero para evitar errores de instalación
python -m pip install --upgrade pip

# Mi kit esencial de análisis
pip install pandas       # Para cargar y limpiar tablas
pip install matplotlib   # Para mis gráficos base
pip install seaborn      # Para mis gráficos estadísticos avanzados
pip install notebook     # Para poder usar Jupyter Notebooks en local
```

## 🛠️ 4. Conectar con GitHub (SSH) - Pasos para generar acceso automático
Estos comandos NO son mis datos personales guardados, sino los **pasos manuales** que debo seguir en una PC nueva para que GitHub me deje subir cambios sin pedirme contraseña cada vez:

1. **Genero una llave nueva:** Ejecuto `ssh-keygen -t ed25519 -C "mi-email@ejemplo.com"`. (Le doy a Enter a todo lo que me pregunte).
2. **Veo el código generado:** Ejecuto `cat ~/.ssh/id_ed25519.pub`. (Aparecerá un texto largo que empieza por `ssh-ed25519...`).
3. **Lo guardo en la web:** Copio ese texto largo y lo pego en mi cuenta de GitHub: `Settings > SSH and GPG keys > New SSH Key`.

---

## 💡 Secretos de Experiencia (Tips Pro)
- **Versión de Python:** Siempre verifico la versión de la computadora con `python --version`. Si tengo varias (Python 3.10, 3.12), me aseguro de que el VS Code esté usando la que yo quiero en el "Interpreter Selector" abajo a la derecha.
- **Evito instalar todo global:** Mi regla de oro es instalar en global solo lo mínimo (como `pip` y `virtualenv`) e instalar las librerías de datos (Pandas, etc.) solamente dentro de mis entornos virtuales (`.venv`).

### 🆘 Manual de Rescate: Recuperar el control de la terminal
A veces la terminal se queda "congelada" o entro en un sitio donde no sé salir. Aquí están mis llaves maestras:

| Si pasa esto... | Mi reacción rápida | Qué hace |
| :--- | :--- | :--- |
| **Terminal llena de texto sucio** | `clear` o `Ctrl + L` | Limpia la pantalla para empezar de cero. |
| **Un comando no termina nunca** | `Ctrl + C` | **EL BOTÓN DEL PÁNICO.** Aborta cualquier proceso que esté corriendo. |
| **He entrado en el editor VIM** | `ESC` y luego `:q!` | Salgo de VIM sin guardar nada (si me equivoqué). |
| **Quiero guardar y salir de VIM**| `ESC` y luego `:wq` | Guarda los cambios (Write) y sale (Quit). |
| **Git me muestra un log largo** | `q` | Salgo de la vista de lectura (Quit) y vuelvo a escribir. |
| **La terminal no responde** | `Ctrl + D` | Cierra la sesión actual de forma limpia. |
