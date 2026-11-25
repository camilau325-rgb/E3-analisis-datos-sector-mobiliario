# Análisis de las causas de la disminución de ventas en el sector mobiliario

Equipo E__ · Análisis de Datos Básico · Estud-IA (Capa 2)

> **Cómo llenar este archivo:** borra «Escribe aquí» y responde debajo de cada pregunta. Si todavía no sabes algo, escribe **PENDIENTE:** y qué te falta confirmar. No inventes datos.

## Ficha del proyecto · versión 1

### 1. Usuario y decisión
¿Quién usará el resultado (una persona o un área) y qué va a decidir con él?


> Gerentes comerciales y directores de ventas de empresas constructoras en Medellín. Determinar si es necesario ajustar las estrategias comerciales, los precios y los incentivos de compra para mejorar las ventas de vivienda nueva.
### 2. Pregunta principal


> ¿Cómo han evolucionado las ventas de vivienda en Medellín?

### 3. Fuente de datos

> Muestra sintetica


### 4. Qué representa una fila


> Una vivienda

### 5. Periodo


> 2024-2025

### 6. Cuatro indicadores
> Nombre de cada indicador y, si ya puedes, cómo se calcula (qué se divide entre qué).

1. Variación
2. Porcentaje
3. Total de viviendas vendidas
4. Tiempo promedio de venta

### 7. Fuera de alcance
> Lo que este proyecto NO va a responder.

Determinar las causas exactas de la disminución de las ventas de vivienda

## Si alcanzas hoy (para el jueves es obligatorio)

### Dos comparaciones útiles
> Por ejemplo: por mes, por comuna, por categoría.

1. Comparación del precio promedio de venta por municipio
Se analizaron los 281 inmuebles vendidos y se obtuvo lo siguiente:
Municipio	Ventas	Precio promedio
Envigado	43	$1.001.851.000
Rionegro	51	$710.859.000
Medellín	49	$638.925.000
Sabaneta	56	$456.791.000
Itagüí	46	$376.722.000
Bello	36

2.Comparación del precio promedio de venta según el tipo de inmueble
Tipo de inmueble	Ventas	Precio promedio
Casa	51	$997.339.000
Apartamento No VIS	149	$627.318.000
Apartamento VIS	81

### Tres riesgos de calidad
> ¿Qué podría venir mal en los datos? ¿Qué harías si la fuente falla?

1. Datos incompletos: registros con fechas o precios vacíos.
2. Datos incorrectos: fechas, valores o nombres mal escritos.
3. Fallas en la fuente: pérdida de información o errores al cargar los datos; por eso, mantendríamos copias de seguridad y validaríamos los registros.

### Mapa de preguntas
- ¿Qué pasó?
  Identificar cuántas viviendas se vendieron y cuál fue el valor total de las ventas.
  
- ¿Dónde o cuándo es distinto?
  Comparar las ventas por municipio y tipo de inmueble.
  
- ¿Qué recomendaría y con qué límites?
Enfocar la atención en los municipios con mayor valor de ventas, teniendo en cuenta que el análisis depende de la calidad y disponibilidad de los datos.

## Archivos del proyecto

| Archivo o carpeta | Qué contiene |
|---|---|
| [diccionario.md](diccionario.md) | Qué significa cada columna de la muestra |
| [bitacora.md](bitacora.md) | Decisiones y por qué; uso de IA |
| `datos/originales/` | La muestra tal como se descargó (no se modifica) |
| `consultas/` | Consultas SQL comentadas (sesión 3) |
| `notebooks/` | Cuadernos de Colab (sesiones 3 a 5) |
| `tablero/` | Capturas y enlace del tablero (sesión 6) |

## Reglas del repositorio

- Es **público**: nada de datos personales (nombres, cédulas, teléfonos, correos, direcciones), contraseñas ni llaves.
- Lo que está en `datos/originales/` no se modifica: se guarda tal como se descargó.
- Cada commit dice en su mensaje **qué** se decidió y **por qué**.

---

Proyecto desarrollado en Estud-IA · Capa 2 · Análisis de Datos.
