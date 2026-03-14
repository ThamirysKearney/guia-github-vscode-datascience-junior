# 📁 Playbook: Arquitectura de Proyectos

Estructura de carpetas recomendada para proyectos de Data Science que sean escalables, limpios y fáciles de entender para otros desarrolladores.

## 🗂️ Organización de carpetas
Así es como voy a estructurar los repositorios para no perder el control cuando el proyecto crezca:

```text
nombre-del-proyecto/
├── data/               # Aquí guardo los datos
│   ├── raw/            # Datos originales (¡PROHIBIDO TOCAR!)
│   └── processed/      # Datos limpios tras el script de Python
├── notebooks/          # Jupyter Notebooks para jugar y explorar
├── src/                # Código "formal" (.py) que va a producción
│   ├── data_cleaning.py
│   ├── feature_engineering.py
│   └── model_training.py
├── models/             # Aquí guardaré los modelos entrenados (archivos .pkl)
├── docs/               # Apuntes, diagramas y documentación extra
├── .venv/              # Entorno virtual (nunca lo subo a GitHub)
├── .gitignore          # Lista de archivos que Git debe ignorar
├── requirements.txt    # Lista de librerías para que otros las instalen
└── README.md           # Carta de presentación del proyecto
```

## 🛠️ Comandos Clave de Navegación
Para moverme rápido en la terminal utilizo:
- `ls`: Para ver qué hay en la carpeta actual.
- `ls -R`: Para ver todo el árbol de carpetas de golpe.
- `cd nombre-carpeta`: Para entrar.
- `cd ..`: Para volver un nivel atrás.
- `mkdir -p data/raw`: Para crear carpetas y subcarpetas en un solo paso.

## 💡 Secretos de Experiencia (Tips Pro)
- **Rutas Relativas:** Nunca uso rutas como `C:/Usuarios/Yo/Documents...`. Siempre uso rutas relativas como `./data/raw/data.csv`. Si muevo el proyecto de carpeta o de PC, las rutas absolutas romperán todo el código.
- **Data Raw es Sagrada:** Nunca guardo cambios encima del archivo original. Si cometo un error limpiando, siempre puedo volver al original si lo dejé intacto en `data/raw`.
- **src vs notebooks:** Uso los Notebooks para probar ideas rápidas, pero cuando el código funciona, lo muevo a archivos `.py` en `src`. Así es más fácil de reutilizar y automatizar.
