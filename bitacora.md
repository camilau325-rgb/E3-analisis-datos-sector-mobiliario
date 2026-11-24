## Registro de uso de Inteligencia Artificial (Sesión 3)

* **Herramienta utilizada:** Gemini (Google).
* **Qué se le pidió:** Analizar la retroalimentación del docente sobre el repositorio, inspeccionar la estructura y contenido del archivo `ventas_inmobiliarias_sintetico.csv` y ayudar a estructurar la versión 2 de la ficha (`README.md`), el diccionario de datos (`diccionario.md`) y las consultas SQL iniciales.
* **Qué se aceptó y qué se modificó:**
  * Se aceptó la corrección de la unidad de análisis (pasar de "una vivienda" a "una cotización inmobiliaria"), la ampliación del alcance geográfico (los 6 municipios reales del archivo en lugar de solo Medellín) y el ajuste del periodo real de los datos (2023–2026 en lugar de 2024–2025).
  * Se incorporaron los hallazgos de calidad de datos identificados (duplicados `CT0403` y `CT0795`, variantes de texto en `municipio` y valores atípicos en área/fechas).
  * Se ajustó la redacción de los indicadores y comparaciones para alinearlos con las decisiones comerciales de las constructoras definidas por el equipo.
* **Cómo se verificó:** Se abrió directamente el archivo `ventas_inmobiliarias_sintetico.csv` para comprobar el número total de filas (1.095), los valores únicos de las columnas `municipio`, `proyecto`, `estado` y `tipo_inmueble`, las fechas mínima y máxima, y los IDs duplicados mencionados.
