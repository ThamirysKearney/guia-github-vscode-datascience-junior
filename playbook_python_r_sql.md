# 🐍 Playbook: Python, R y SQL para Datos

Recordatorio rápido de los lenguajes que uso a diario. He seleccionado los comandos que más repito y las reglas de oro para que el equipo me entienda.

## 🔹 SQL: Llave para los datos (Bases de Datos)
SQL es lo primero que uso para extraer información.

```sql
-- Extraigo solo lo que necesito para no saturar la red (Tip: Evito SELECT *)
SELECT 
    user_id,             -- Tipo: INT (Identificador único)
    order_date,          -- Tipo: DATE (Importante para series temporales)
    SUM(amount) AS total -- Realizo una suma directamente para ahorrar tiempo en Python
FROM orders
WHERE status = 'Completed' -- Filtro pronto para traer menos datos
GROUP BY 1, 2              -- Agrupo por las columnas 1 y 2
HAVING total > 100;        -- Filtro tras agrupar
```

## 🔹 Python: Laboratorio de análisis (Pandas)
Pandas es la herramienta principal para limpiar y transformar.

```python
import pandas as pd

# Leo el archivo csv (sep=';' es común en datos europeos)
df = pd.read_csv('mi_data.csv', sep=',')

# Veo los tipos de datos (¡Vital antes de empezar!)
# Si una fecha es 'object', debo convertirla a datetime
print(df.dtypes)

# Convierto a fecha para poder extraer el mes o año
df['fecha'] = pd.to_datetime(df['fecha']) # Convierte string a objeto datetime

# Filtro filas de forma legible
ventas_altas = df[df['total'] > 100] # Creo una máscara booleana

# Calculo la media por categoría
resumen = df.groupby('categoria')['total'].mean().reset_index()
```

## 💡 Secretos de Experiencia (Tips Pro)
- **SQL: El orden importa.** SELECT > FROM > JOIN > WHERE > GROUP BY > HAVING > ORDER BY. Grabarme este orden me ahorra errores de sintaxis tontos.
- **Python: Los IDs a string.** Si tengo una columna de `ID_CLIENTE` que son números, los convierto a `str` inmediatamente. Así evito que Python intente sumarlos o calcular la media, porque un ID no es un número matemático, es una etiqueta.
- **R:** Lo uso sobre todo cuando necesito estadística muy pura o librerías muy específicas de bioinformática/econometría que en Python son más difíciles de encontrar. `ggplot2` sigue siendo imbatible en belleza rápida.
