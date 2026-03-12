# 🖥️ Guía de Configuración: Python y Git en Windows
## (Git Bash vs PowerShell — ¿Cuál usar y por qué?)

> **Para añadir a:** `guia-github-vscode-datascience-junior` → `setup_python_git.md`

---

## 🥊 Git Bash vs PowerShell — La Comparación Definitiva

### ¿Qué son?

| | **Git Bash** | **PowerShell** |
|---|---|---|
| **¿Qué es?** | Emulador de terminal Unix/Linux que viene incluido con Git para Windows | Shell nativa de Windows, creada por Microsoft |
| **Lenguaje** | Comandos Bash (Linux/Mac) | Comandos cmdlets de PowerShell |
| **Instalación** | Se instala junto con Git for Windows | Viene preinstalado en Windows |
| **Entorno** | Simula un entorno Unix en Windows | Entorno nativo Windows |
| **Colores y UX** | Muestra la rama Git en el prompt | No muestra la rama por defecto |

### ¿Por qué Git Bash es más utilizado en Data Science?

```
🌍 El mundo de Data Science vive en Linux/Mac.
Los servidores, Docker, los entornos cloud (AWS, GCP, Azure)
y los repositorios open source usan comandos Bash.
Aprender Git Bash = aprender el "idioma universal" del desarrollo.
```

**Razones específicas:**
1. **Universalidad:** Los tutoriales, documentación y cursos de Data Science usan comandos Bash. Si aprendes en Git Bash, puedes seguir cualquier tutorial del mundo sin traducir comandos.
2. **Compatibilidad con servidores:** Cuando despliegues modelos en producción (Linux), usarás exactamente los mismos comandos.
3. **Scripts portables:** Un script `.sh` escrito en Git Bash funciona en Linux/Mac sin cambios. Un script PowerShell, no.
4. **Git nativo:** Git fue diseñado para Linux. Git Bash es su entorno natural — mejor autocompletado, colores y mensajes.
5. **La rama en el prompt:** Git Bash muestra `(main)` o `(feature/eda)` directamente en el prompt, lo cual es muy útil.

### ¿Cuándo usar PowerShell?
- Cuando trabajas con comandos **exclusivos de Windows** (gestión de usuarios, registros del sistema, Active Directory)
- En entornos corporativos donde PowerShell es obligatorio
- Para automatización de tareas de Windows específicas

### 🏆 Veredicto
> **Usa Git Bash siempre para tus proyectos de Data Science.** PowerShell está bien como fallback, pero Git Bash te prepara para el mundo real.

---

## ✅ Paso 1: Comprobar si Git y Python ya están instalados

### 🔹 En Git Bash
```bash
# Comprobar versión de Git (si muestra número = instalado ✅)
git --version

# Comprobar versión de Python
python --version
# o si tienes Python 3 específicamente:
python3 --version

# Comprobar pip (gestor de paquetes de Python)
pip --version

# Comprobar tu nombre y email configurados en Git
git config --global user.name
git config --global user.email

# Ver toda la configuración de Git de golpe
git config --list
```

### 🔸 En PowerShell
```powershell
# Comprobar versión de Git
git --version

# Comprobar versión de Python
python --version

# Comprobar pip
pip --version

# Comprobar configuración de Git
git config --global user.name
git config --global user.email

# Ver toda la configuración
git config --list
```

> 💡 **¿Qué significa cada respuesta?**
> - Si ves `git version 2.x.x` → Git instalado ✅
> - Si ves `Python 3.x.x` → Python instalado ✅
> - Si ves `'git' is not recognized` o `command not found` → No instalado ❌

---

## 🛠️ Paso 2: Instalar Git (si no está instalado)

### Instalación
1. Ve a **https://git-scm.com/download/win**
2. Descarga el instalador de 64-bit
3. Durante la instalación, opciones recomendadas:
   - ✅ "Git Bash Here" (para abrirlo desde el explorador de archivos con botón derecho)
   - ✅ "Use Git from the command line and also from third-party software"
   - ✅ "Use the OpenSSL library"
   - ✅ Editor: elige **Visual Studio Code** si te lo ofrece
   - ✅ "Use Windows' default console window" o "MinTTY" (cualquiera funciona)

### Verificación post-instalación (Git Bash)
```bash
git --version
# Esperado: git version 2.43.0 (o superior)
```

---

## 🐍 Paso 3: Instalar Python (si no está instalado)

### Instalación
1. Ve a **https://www.python.org/downloads/**
2. Descarga la última versión estable (3.11 o 3.12)
3. **MUY IMPORTANTE:** Durante la instalación, marca la casilla:
   - ✅ **"Add Python to PATH"** ← Sin esto, Python no funcionará desde la terminal

### Verificación post-instalación
```bash
# En Git Bash
python --version
pip --version

# Si python no funciona pero python3 sí:
python3 --version
```

---

## ⚙️ Paso 4: Configuración inicial de Git (Obligatorio, solo se hace una vez)

Esto le dice a Git quién eres. Aparecerá en todos tus commits de GitHub.

### 🔹 En Git Bash (recomendado)
```bash
# Tu nombre (como quieres que aparezca en GitHub)
git config --global user.name "Tu Nombre Aquí"

# Tu email (DEBE ser el mismo que usas en GitHub)
git config --global user.email "tu@email.com"

# Editor de texto por defecto para mensajes de commit
git config --global core.editor "code --wait"

# Configurar el nombre de la rama por defecto como 'main' (estándar actual)
git config --global init.defaultBranch main

# Configurar el manejo de saltos de línea (crítico en Windows)
# Esto evita problemas de compatibilidad con Linux/Mac
git config --global core.autocrlf true
```

### 🔸 En PowerShell (mismos comandos, misma sintaxis)
```powershell
git config --global user.name "Tu Nombre Aquí"
git config --global user.email "tu@email.com"
git config --global core.editor "code --wait"
git config --global init.defaultBranch main
git config --global core.autocrlf true
```

> 💡 **¿Qué hace `core.autocrlf true`?**  
> Windows usa `\r\n` para saltos de línea. Linux/Mac usan `\n`.  
> Esta opción convierte automáticamente los saltos de línea para que no haya conflictos cuando compartes código con personas en Mac/Linux (muy común en equipos de Data Science).

---

## 🔐 Paso 5: Autenticación con GitHub (PAT — Personal Access Token)

Desde 2021, GitHub ya no acepta contraseñas. Usa un **Token de Acceso Personal (PAT)**.

### Cómo crear tu PAT:
1. Ve a GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
2. Haz clic en **"Generate new token (classic)"**
3. Nombre: `mi-pc-trabajo` (o lo que quieras)
4. Expiración: 90 días (o sin expiración si es tu PC personal)
5. Permisos: marca ✅ **repo** (acceso completo a repositorios)
6. Copia el token — **¡solo lo verás una vez!**

### Usar el token en Git Bash
```bash
# La primera vez que hagas push, te pedirá usuario y contraseña.
# Usuario: tu_usuario_de_github
# Contraseña: pega el PAT aquí (no tu contraseña de GitHub)

# Para no tener que introducirlo cada vez:
git config --global credential.helper store
# Tras hacer el primer push con tu PAT, se guardará automáticamente.
```

---

## ✅ Paso 6: Verificación final — Checklist completo

```bash
# En Git Bash, ejecuta todo esto. Si todo muestra resultados = listo ✅

echo "=== GIT ===" && git --version
echo "=== PYTHON ===" && python --version
echo "=== PIP ===" && pip --version
echo "=== GIT USER ===" && git config --global user.name
echo "=== GIT EMAIL ===" && git config --global user.email
echo "=== GIT BRANCH DEFAULT ===" && git config --global init.defaultBranch
```

### Resultado esperado:
```
=== GIT ===
git version 2.43.0.windows.1
=== PYTHON ===
Python 3.12.0
=== PIP ===
pip 23.3.1 from C:\...
=== GIT USER ===
Tu Nombre Aquí
=== GIT EMAIL ===
tu@email.com
=== GIT BRANCH DEFAULT ===
main
```

---

## 📦 Bonus: Librerías esenciales de Data Science (instalar una vez)

```bash
# En Git Bash o PowerShell (pip funciona igual en ambos)
pip install pandas numpy matplotlib seaborn scikit-learn jupyter plotly
```

---

## 📊 Resumen Visual: Git Bash vs PowerShell

```
┌─────────────────────────────────────────────────────────┐
│                 ¿QUÉ TERMINAL USAR?                     │
├─────────────────────────────────────────────────────────┤
│  Proyectos Data Science / ML / Git  →  GIT BASH  ✅    │
│  Automatización Windows / Empresa   →  POWERSHELL ✅   │
│  Comandos de Git en general         →  GIT BASH  ✅    │
│  Scripts que van a producción       →  GIT BASH  ✅    │
└─────────────────────────────────────────────────────────┘
```

---

> **💡 Regla de oro:** Si estás haciendo Data Science, Git, o trabajando con Python → abre **Git Bash**. Si necesitas hacer algo específico de Windows (instalar programas, gestionar usuarios, etc.) → usa **PowerShell**. En la duda, Git Bash.
