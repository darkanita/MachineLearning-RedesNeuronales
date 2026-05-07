# 📋 Guía del Instructor — Sesión 2
## Datos: el combustible del ML

**Módulo:** Aprendizaje Automático  
**Fecha:** Miércoles, Mayo 06, 2026  
**Duración:** 4 horas  
**Instructora:** Darkanita

---

## 🎯 Objetivos de aprendizaje

Al finalizar esta sesión, las asistentes podrán:
1. Explicar de dónde vienen los datos para ML
2. Identificar 5 problemas comunes en datasets (nulos, duplicados, tipos, outliers, inconsistencias)
3. Explorar datos visualmente con Orange Data Mining
4. Ejecutar comandos básicos de pandas para explorar y limpiar datos
5. Distinguir entre features y label en un dataset

---

## ⏱️ Cronograma detallado

| Hora | Bloque | Actividad | Duración |
|------|--------|-----------|----------|
| 0:00 | Repaso | "¿Qué recuerdan de la sesión 1?" + conectar con hoy | 5 min |
| 0:05 | Teoría | ¿De dónde vienen los datos? (6 fuentes) | 10 min |
| 0:15 | Teoría | Datos limpios vs sucios + analogía del chef | 15 min |
| 0:30 | Teoría | Features y Labels con ejemplo de tienda | 10 min |
| 0:40 | Teoría | Train/Test: la analogía del examen | 10 min |
| 0:50 | — | **Descanso** | 5 min |
| 0:55 | Low Code | Demo Orange: cargar CSV y conectar widgets | 15 min |
| 1:10 | Low Code | Práctica guiada: explorar el dataset de ventas | 40 min |
| 1:50 | Low Code | Discusión: ¿qué problemas encontraron? | 10 min |
| 2:00 | — | **Descanso** | 10 min |
| 2:10 | Pro Code | Notebook paso a paso: el kit de primeros auxilios | 20 min |
| 2:30 | Pro Code | Detectives: encontrar los 5 problemas con código | 25 min |
| 2:55 | Pro Code | Limpiar datos paso a paso + comparar antes/después | 25 min |
| 3:20 | Pro Code | Experimentación libre: explorar el dataset limpio | 10 min |
| 3:30 | Reto | Explicar reto "Detective de datos" | 5 min |
| 3:35 | Reto | Tiempo de trabajo (Orange O Colab, a elección) | 25 min |
| 4:00 | — | Cierre, resumen, anticipo sesión 3 | — |

---

## 📝 Notas para cada bloque

### Bloque 1: Teoría (45 min)

**Slide 3 — Fuentes de datos**
- Pregunta al grupo: "¿En su trabajo, de dónde salen los datos que manejan?"
- Objetivo: que conecten ML con su realidad
- Tip: mencionar datos abiertos de Colombia (datos.gov.co, Kaggle)

**Slide 4 — Limpios vs sucios**
- Mostrar un ejemplo real: abrir un Excel desordenado y uno limpio
- La frase "80% del trabajo es limpiar datos" es clave: repetirla varias veces
- Esto baja expectativas irrealistas de que ML es "mágico"

**Slide 5 — Analogía del chef**
- Esta diapositiva es la más memorable. Dejar que resuene.
- "Garbage In → Garbage Out" es el mantra de la sesión

**Slide 6 — Features y Labels**
- Usar ejemplo concreto de la tabla (predecir si un cliente compra)
- Ejercicio rápido: "Si quieren predecir qué estudiante pasa el semestre, ¿cuáles serían las features? ¿Cuál el label?"
- Tip: No usar el término "variable independiente/dependiente" — es jerga estadística innecesaria

**Slide 7 — Train/Test**
- La analogía del examen es la más efectiva para audiencia no técnica
- Enfatizar: "si le muestras el examen antes, saca 100% pero NO aprendió nada"
- Concepto clave: OVERFITTING = memorizar vs aprender

### Bloque 2: Low Code — Orange Data Mining (1.5 horas)

**Preparación previa:**
- Instalar Orange en los computadores O usar la versión web
- Tener el archivo `caso_sucio.csv` accesible para todas
- Si Orange no está disponible, se puede usar como alternativa la extensión de Google Sheets "Explore" o simplemente saltar a Colab

**Demo del instructor (15 min):**
1. Abrir Orange → nuevo workflow
2. Arrastrar "CSV File Import" → cargar `caso_sucio.csv`
3. Conectar "Data Table" → ver la tabla (señalar celdas vacías, valores raros)
4. Conectar "Feature Statistics" → observar tipos, nulos, distribuciones
5. Conectar "Distributions" → elegir "edad" → ver el outlier de 999
6. Conectar "Scatter Plot" → edad vs ingreso → ver puntos aislados

**Práctica guiada (40 min):**
- Las asistentes replican el workflow del instructor
- Agregar widgets adicionales: Box Plot, Mosaic Display
- Ejercicio: "Conecten un widget 'Select Rows' para filtrar solo datos de Medellín"

**Discusión (10 min):**
- "¿Cuántos problemas encontraron en Orange?"
- Listar en la pizarra los problemas detectados por el grupo
- Conectar: "Ahora vamos a hacer lo mismo pero con código — verán que es igual de simple"

### Bloque 3: Pro Code — Google Colab (1.5 horas)

**Preparación:**
- Subir `caso_sucio.csv` a Google Drive
- Compartir notebook `Sesion2_Datos_Combustible_ML.ipynb`
- Las asistentes hacen copia y suben el CSV

**Kit de primeros auxilios (20 min):**
Las 4 líneas que siempre ejecutan primero con cualquier dataset nuevo:
- `df.head()` → "¿Cómo se ven los datos?"
- `df.info()` → "¿Qué tipos y cuántos nulos?"
- `df.describe()` → "¿Cuáles son los promedios y extremos?"
- `df.isnull().sum()` → "¿Cuánto falta?"

**Tip pedagógico:** Escribir estas 4 líneas en la pizarra. Decir: "Si solo recuerdan 4 líneas de Python de todo el curso, que sean estas."

**Detective de datos (25 min):**
Ejecutar juntas las celdas del Paso 3. Para cada problema:
1. Ejecutar celda → ver resultado
2. Discutir: "¿Esto es un problema? ¿Por qué?"
3. Anotar el hallazgo

**Limpieza (25 min):**
Ejecutar el Paso 5 celda por celda. Enfatizar:
- "Siempre hagan `df.copy()` antes de limpiar"
- "Cada decisión de limpieza tiene un tradeoff"
- La comparación visual antes/después es el momento "wow"

### Bloque 4: Reto (30 min)

El archivo `caso_sucio.csv` tiene intencionalmente estos 10+ problemas:

| # | Problema | Filas afectadas |
|---|----------|----------------|
| 1 | Valores nulos (nombre, género, ingreso, satisfacción, método pago) | 4, 5, 11, 16, 17, 19, 22, 24, 25 |
| 2 | Filas duplicadas exactas | 1=9, 5=18 |
| 3 | Inconsistencia en ciudad (Medellín/medellin/MEDELLIN/Mede/Bogota/bogotá) | 4, 6, 12, 15, 21 |
| 4 | Inconsistencia en género (Femenino/femenino/F/masculino) | 10, 15, 21 |
| 5 | Tipo incorrecto en ingreso ("tres millones") | 7 |
| 6 | Tipo incorrecto en edad ("NA" como texto) | 19 |
| 7 | Outlier edad (999, -5) | 6, 13 |
| 8 | Cantidad negativa | 20 |
| 9 | Satisfacción fuera de rango (6) | 17 |
| 10 | Fechas en formatos mixtos (YYYY-MM-DD, DD/MM/YYYY, YYYY/MM/DD, "April 20 2025") | 3, 10, 14, 23 |
| 11 | Nombre faltante | 24 |

**Las asistentes deben encontrar al menos 5.** Pueden usar Orange O Colab.

**Criterios de éxito:**
- ✅ Identificó al menos 5 problemas distintos
- ✅ Explicó por qué cada uno es un problema
- ✅ Propuso o aplicó una solución para al menos 3

---

## 🛠️ Requisitos técnicos

| Recurso | URL/Ubicación | Notas |
|---------|--------------|-------|
| Orange Data Mining | orangedatamining.com | Instalar previamente o usar versión portable |
| Google Colab | colab.research.google.com | Requiere cuenta Google |
| caso_sucio.csv | Compartir por Classroom | Dataset con problemas intencionales |
| Notebook | Sesion2_Datos_Combustible_ML.ipynb | Compartir por Classroom |
| Presentación | Sesion2_Datos_Combustible_ML.pptx | 13 slides |

---

## ❓ Preguntas frecuentes

**"¿Siempre hay que limpiar datos?"**
Sí, SIEMPRE. Incluso datasets "oficiales" tienen problemas. La diferencia es cuántos.

**"¿Y si borro datos importantes al limpiar?"**
Por eso siempre hacemos `df.copy()`. El original queda intacto. En la vida real, guardas versiones.

**"¿Cuándo es mejor eliminar una fila vs rellenar el nulo?"**
Regla general: si la columna tiene >50% nulos, considerar eliminarla. Si una fila tiene >50% nulos, eliminarla. De lo contrario, rellenar con mediana/moda.

**"¿Qué hago si no sé si un outlier es error o dato real?"**
Investigar. Un ingreso de $100M puede ser error O puede ser el CEO. El contexto del negocio decide.

---

## 📎 Archivos de la sesión

1. `Sesion2_Datos_Combustible_ML.pptx` — Presentación (13 slides)
2. `Sesion2_Datos_Combustible_ML.ipynb` — Notebook de Google Colab
3. `caso_sucio.csv` — Dataset con problemas intencionales para el reto
4. `Guia_Instructor_Sesion2.md` — Esta guía

---

*Próxima sesión: Clasificación: enseñando a decidir (Viernes, Mayo 08)*
