# Evolución y comportamiento de las ventas inmobiliarias en el Valle de Aburrá y Rionegro (2023–2026)

Equipo E3 · Análisis de Datos Básico · Estud-IA (Capa 2)

## Ficha del proyecto · versión 2

### 1. Usuario y decisión
> Gerentes comerciales y directores de ventas de empresas constructoras con proyectos en el Área Metropolitana del Valle de Aburrá y Rionegro. Decidir en qué municipios, proyectos, tipos de inmueble y canales comerciales concentrar esfuerzos, ajustar precios de lista o diseñar incentivos para mejorar la conversión de cotizaciones a ventas cerradas.

### 2. Pregunta principal
> ¿Cómo han evolucionado las ventas de vivienda (en unidades cerradas y en pesos) entre 2023 y 2026 en los proyectos de Medellín, Sabaneta, Envigado, Itagüí, Bello y Rionegro?

### 3. Fuente de datos
> Base sintética `ventas_inmobiliarias_sintetico.csv` ubicada en `datos/originales/`, correspondiente al registro comercial de cotizaciones y cierres de 6 proyectos inmobiliarios.

### 4. Qué representa una fila
> **Una cotización inmobiliaria** (`cotizacion_id`), realizada por un cliente (`cliente_id`) para un inmueble dentro de un proyecto específico, la cual puede terminar en estado *Cotizado*, *Separado*, *Vendido* o *Desistido*.

### 5. Periodo
> **1 de enero de 2023 al 29 de octubre de 2026** (según `fecha_cotizacion`).

### 6. Cuatro indicadores
1. **Total de viviendas vendidas (unidades):** Conteo de cotizaciones cuyo `estado` es igual a `'Vendido'` (eliminando duplicados de `cotizacion_id`).
2. **Monto total de ventas (COP):** Suma de la columna `precio_venta` (en pesos colombianos) para los registros con `estado = 'Vendido'`.
3. **Variación porcentual anual / trimestral de ventas:** Cambio relativo en el número de unidades vendidas (o monto en COP) frente al periodo anterior: `(Ventas_actual - Ventas_anterior) / Ventas_anterior * 100`.
4. **Tiempo promedio de cierre (días) y tasa de conversión (%):** Promedio de días transcurridos entre `fecha_cotizacion` y `fecha_cierre` para inmuebles vendidos, junto con el porcentaje de cotizaciones que se convierten en venta (`Total Vendido / Total Cotizaciones únicas * 100`).

### 7. Fuera de alcance
> Determinar las causas macroeconómicas o externas (tasas de interés del mercado, políticas nacionales de subsidios o factores personales de los compradores) que explican por qué un cliente desiste o compra.

---

## Comparaciones y riesgos

### Dos comparaciones útiles
1. **Por municipio y tipo de inmueble:** Comparar el volumen de unidades vendidas, ticket promedio (`precio_venta`) y porcentaje de desistimiento entre los 6 municipios (Medellín, Sabaneta, Envigado, Itagüí, Bello y Rionegro) y segmentos (*Apartamento VIS*, *Apartamento No VIS* y *Casa*).
2. **Por canal comercial y periodo (año/trimestre):** Comparar la evolución temporal (2023 a 2026) y la tasa de conversión a venta según el `canal` de origen (*Sala de ventas*, *Página web*, *Feria inmobiliaria* y *Referido*).

### Tres riesgos de calidad
1. **Filas duplicadas:** Existen registros exactamente repetidos con el mismo `cotizacion_id` (por ejemplo, `CT0403` y `CT0795`). *Mitigación:* Aplicar `SELECT DISTINCT` o filtrar duplicados por `cotizacion_id` antes de calcular totales.
2. **Inconsistencias de formato en texto:** La columna `municipio` mezcla `"Medellín"`, `"medellin"` (sin tilde y en minúscula) y `"Envigado "` (con espacio final). *Mitigación:* Normalizar texto con `TRIM()` y estandarizar mayúsculas/tildes antes de agrupar por municipio.
3. **Nulos, valores en cero y fechas anómalas:** Se detectan registros con `area_m2 = 0` (`CT0762`), `precio_lista` vacío (`CT0074`, `CT0122`), fechas inexistentes como `2025-06-31` (`CT0756`) y cierres anteriores a la cotización (`CT0390`). *Mitigación:* Documentar y excluir o corregir estos casos puntuales según el indicador que se calcule (por ejemplo, al calcular días de cierre).

### Mapa de preguntas
* **¿Qué pasó?** ¿Cuántas cotizaciones se generaron, cuántas cerraron como venta (`Vendido`), cuánto dinero ingresó (`precio_venta`) y cómo variaron las ventas año a año entre 2023 y 2026?
* **¿Dónde o cuándo es distinto?** ¿Qué municipios, proyectos (*Yarumos, Ceibas, Samanes, Guayacanes, Arrayanes, Robles*), tipos de vivienda (*VIS, No VIS, Casa*) y canales comerciales presentan mayor volumen de ventas o mayor tasa de desistimiento?
* **¿Qué recomendaría y con qué límites?** Priorizar los canales y segmentos con mayor conversión y menor descuento respecto al `precio_lista`, teniendo en cuenta que es una base sintética con registros duplicados y datos atípicos que no incluye variables externas del mercado.
