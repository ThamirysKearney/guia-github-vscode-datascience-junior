# 🐍 Playbook: Entornos Virtuales

Caja aislada donde puedo instalar las librerías para un proyecto específico sin ensuciar el resto de la computadora. Estos son los pasos para no tener conflictos de versiones.

## 1. Crear el Entorno
Cuando empiezo un proyecto nuevo, lo primero que hago es crear una "burbuja":
```powershell
python -m venv .venv
```
*(Uso `.venv` como nombre porque es un estándar y muchos editores lo detectan solos).*

## 2. Activar la burbuja
Dependiendo de dónde esté trabajando, uso un comando distinto:

### Si estoy en PowerShell (Windows):
```powershell
.\.venv\Scripts\Activate.ps1
```
*Si la PC me bloquea por "scripts prohibidos", ejecuto esto una sola vez:* `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`

### Si estoy en Git Bash (Favorito):
```bash
source .venv/Scripts/activate
```

## 3. Instalar herramientas
Una vez veo `(.venv)` en la terminal, instalo lo que necesito:
```powershell
pip install pandas numpy scikit-learn
```

## 💡 Secretos de Experiencia (Tips Pro)
- **El Olvido del .gitignore:** Lo primero que hago tras crear el entorno es añadir `.venv/` al archivo `.gitignore`. Si lo subo a GitHub por error, el repositorio pesará muchísimo y subiré miles de archivos innecesarios.
- **Librerías innecesarias:** Intento no instalar librerías "por si acaso". Cada librería extra hace el proyecto más pesado y difícil de mantener.
- **Actualizar el requirements:** Cada vez que instalo algo nuevo, ejecuto `pip freeze > requirements.txt` para que la lista de la compra esté siempre al día.
