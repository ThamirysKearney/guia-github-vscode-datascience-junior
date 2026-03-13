# Guía: Entornos Virtuales en Python (Windows) 🐍

Un entorno virtual es una caja aislada donde instalas las librerías para un proyecto específico sin ensuciar el resto de tu computadora.

## 1. Crear el Entorno Virtual

Asegúrate de estar en la carpeta raíz de tu proyecto y ejecuta:

```powershell
python -m venv .venv
```

## 2. Activar el Entorno

Dependiendo de qué terminal uses, el comando cambia:

### En PowerShell (Recomendado en Windows):
```powershell
.\.venv\Scripts\Activate.ps1
```
*Si recibes un error de "scripts prohibidos", ejecuta primero:* `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`

### En Git Bash:
```bash
source .venv/Scripts/activate
```

### En CMD:
```cmd
.venv\Scripts\activate
```

## 3. Instalar Librerías

Una vez activado (verás `(.venv)` al inicio de tu línea de comandos), instala lo que necesites:

```powershell
pip install pandas numpy scikit-learn ucimlrepo
```

## 4. Guardar dependencias

Para que otros puedan replicar tu trabajo:

```powershell
pip freeze > requirements.txt
```

## 5. Salir del entorno

Cuando termines:
```powershell
deactivate
```
