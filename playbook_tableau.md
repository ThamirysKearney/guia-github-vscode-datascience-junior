# 📊 Playbook: Notas de Tableau

Herramienta favorita cuando necesito crear visualizaciones potentes y precisas que los perfiles gerenciales entiendan de un vistazo.

## 🎯 Pasos de Oro en Tableau
1. **Conectar y Limpiar:** Antes de arrastrar nada, reviso en la pestaña "Fuente de Datos" que los tipos (Abc, #, globo de mapa) sean correctos.
2. **Dimensiones vs Medidas:**
    - **Dimensiones (Azul):** Cosas por las que quiero filtrar o agrupar (Nombres, Categorías, Fechas).
    - **Medidas (Verde):** Números que quiero sumar o promediar (Ventas, Unidades, Descuentos).
3. **Filtros de Contexto:** Si quiero que un filtro afecte al "Top 10", debo ponerlo como "Añadir a contexto" (Color grisáceo).

## 💡 Secretos de Experiencia (Tips Pro)
- **No todo es un gráfico de tarta:** Evito los gráficos de tarta si tengo más de 3 categorías. Un gráfico de barras es mucho más fácil de leer para el ojo humano.
- **Colores con sentido:** No uso colores aleatorios. Uso el rojo para alertas/pérdidas y el azul/verde para ganancias. El exceso de colores distrae de lo importante.
- **El Dashboard no es un mural:** Menos es más. Pongo un máximo de 3-4 visualizaciones por cuadro de mando. Si necesito más, creo otra pestaña (Storytelling).
- **Tip de rendimiento:** Si la base de datos es enorme, uso **Extractos** (.hyper) en vez de conexiones en vivo. El dashboard irá volando porque Tableau procesa los datos en la PC, no en el servidor cada vez que alguien hace click.
