# Diccionario de datos

## Resumen de la muestra
* **Archivo:** `datos/originales/ventas_inmobiliarias_sintetico.csv`
* **Cada fila es:** Una cotización inmobiliaria registrada por un cliente en un proyecto de vivienda (puede estar en estado *Cotizado*, *Separado*, *Vendido* o *Desistido*).
* **Filas en la muestra:** 1.095 registros de datos (1.093 cotizaciones únicas, ya que `CT0403` y `CT0795` aparecen duplicadas).
* **Periodo cubierto:** 2023-01-01 a 2026-10-29 (según `fecha_cotizacion`).
* **Cobertura geográfica:** 6 municipios (Medellín, Sabaneta, Envigado, Itagüí, Bello y Rionegro).

## Descripción de columnas

| Columna | Tipo de dato | Descripción | Valores válidos / Ejemplo | Observaciones de calidad |
| :--- | :--- | :--- | :--- | :--- |
| `cotizacion_id` | Texto (ID) | Identificador único de la cotización. | `CT0001` a `CT1093` | Hay 2 IDs duplicados exactos (`CT0403` y `CT0795`). |
| `fecha_cotizacion` | Fecha (`YYYY-MM-DD`) | Fecha en la que se registró la cotización. | `2023-01-01` a `2026-10-29` | Contiene al menos una fecha de calendario inválida (`2025-06-31` en `CT0756`). |
| `cliente_id` | Texto (ID) | Identificador del cliente que solicita la cotización. | `CL0001` a `CL0901` | Un mismo cliente puede tener varias cotizaciones en distintos proyectos o fechas. |
| `proyecto` | Texto (Categoría) | Nombre del proyecto inmobiliario cotizado. | `Ceibas`, `Yarumos`, `Guayacanes`, `Robles`, `Samanes`, `Arrayanes` | Cada proyecto corresponde a un único municipio en la muestra. |
| `municipio` | Texto (Categoría) | Municipio donde se ubica el proyecto. | `Medellín`, `Sabaneta`, `Itagüí`, `Rionegro`, `Envigado`, `Bello` | Aparece `"medellin"` sin tilde/mayúscula y `"Envigado "` con espacio final. |
| `tipo_inmueble` | Texto (Categoría) | Tipología y segmento de la vivienda. | `Apartamento VIS`, `Apartamento No VIS`, `Casa` | Sin valores nulos detectados. |
| `area_m2` | Numérico (Decimal) | Área construida del inmueble en metros cuadrados ($m^2$). | `44.1` a `164.9` | Existen registros con valor `0` (ej. `CT0762`). |
| `precio_lista` | Numérico (Entero) | Precio inicial ofrecido al cliente en pesos colombianos (COP). | `158500000` a `1613400000` | Presenta valores nulos/vacíos en algunas filas (ej. `CT0074`, `CT0122`). |
| `canal` | Texto (Categoría) | Medio por el cual llegó el cliente a cotizar. | `Sala de ventas`, `Página web`, `Feria inmobiliaria`, `Referido` | Sin valores nulos detectados. |
| `forma_pago` | Texto (Categoría) | Modalidad de financiación declarada en la cotización. | `Crédito hipotecario`, `Subsidio y crédito`, `Contado`, `Leasing habitacional` | Sin valores nulos detectados. |
| `estado` | Texto (Categoría) | Etapa comercial actual de la cotización. | `Cotizado`, `Separado`, `Vendido`, `Desistido` | Solo `Vendido` representa una venta efectiva. |
| `fecha_cierre` | Fecha (`YYYY-MM-DD`) | Fecha en la que se concretó la venta o se registró el desistimiento. | `2023-02-02` a `2026-10-31` | Vacía cuando `estado` es `Cotizado` o `Separado`. En algunos casos es anterior a `fecha_cotizacion`. |
| `precio_venta` | Numérico (Entero) | Valor final de cierre de la venta en pesos colombianos (COP). | `155000000` a `1553500000` | Solo aplica cuando `estado = 'Vendido'` (vacío en los demás estados, salvo un caso atípico en `CT0325`). |
