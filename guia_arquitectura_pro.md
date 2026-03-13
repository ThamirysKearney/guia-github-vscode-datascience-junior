# Guía de Arquitectura del Proyecto (Nivel Pro) 🚀

Esta guía explica la estructura de carpetas recomendada para proyectos de Data Science que sean escalables, limpios y fáciles de entender para otros desarrolladores o reclutadores.

## 📁 Estructura de Carpetas

```text
nombre-del-proyecto/
├── data/               # Datos crudos y procesados
│   ├── raw/            # Datos originales (NUNCA editar)
│   └── processed/      # Datos limpios listos para modelar
├── notebooks/          # Jupyter Notebooks para experimentación y EDA
├── src/                # Código fuente (.py) para producción
│   ├── data_cleaning.py
│   ├── feature_engineering.py
│   └── model_training.py
├── models/             # Modelos entrenados (archivos .pkl o .h5)
├── docs/               # Documentación adicional y guías
├── .venv/              # Entorno virtual (no se sube a Git)
├── .gitignore          # Archivos que Git debe ignorar
├── requirements.txt    # Librerías necesarias
└── README.md           # Presentación principal del proyecto
```

## 🛠️ Comandos Esenciales de Navegación

En la terminal (PowerShell o Git Bash):

- `ls`: Listar archivos.
- `ls -R`: Listar archivos de forma recursiva (ver todo el árbol).
- `cd nombre-carpeta`: Entrar en una carpeta.
- `cd ..`: Volver atrás.
- `mkdir -p carpeta/subcarpeta`: Crear una carpeta y sus carpetas padres si no existen.

## 💡 ¿Por qué separar `src` de `notebooks`?

Los **Notebooks** son excelentes para explorar y visualizar, pero el código final que "hace el trabajo" debe estar en archivos `.py` dentro de `src`. Esto facilita la automatización, el testing y el despliegue a gran escala (Big Data).
