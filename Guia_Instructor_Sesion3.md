# 📋 Guía del Instructor — Sesión 3
## Clasificación: enseñando a decidir

**Fecha:** Viernes, Mayo 08, 2026  
**Duración:** 4 horas  
**Instructora:** Darkanita

---

## 🎯 Objetivos de aprendizaje

Al finalizar, las asistentes podrán:
1. Explicar qué es clasificación en ML con ejemplos cotidianos
2. Entender cómo funciona un árbol de decisión (preguntas Sí/No)
3. Interpretar accuracy y la matriz de confusión
4. Construir un clasificador visual en Orange Data Mining
5. Entrenar un DecisionTreeClassifier en Google Colab
6. Identificar qué variables son más importantes para una predicción

---

## ⏱️ Cronograma detallado

| Hora | Bloque | Actividad | Duración |
|------|--------|-----------|----------|
| 0:00 | Repaso | Conectar sesión 2 (datos limpios) con hoy (usarlos) | 5 min |
| 0:05 | Teoría | ¿Qué es clasificar? Ejemplos cotidianos | 10 min |
| 0:15 | Teoría | Analogía del doctor que diagnostica | 10 min |
| 0:25 | Teoría | Árboles de decisión: preguntas Sí/No | 10 min |
| 0:35 | Teoría | Buenas vs malas preguntas (pureza) | 5 min |
| 0:40 | Teoría | Accuracy + Matriz de confusión | 10 min |
| 0:50 | — | **Descanso** | 5 min |
| 0:55 | Low Code | Demo Orange: workflow de clasificación | 15 min |
| 1:10 | Low Code | Práctica guiada: ¿Este estudiante aprueba? | 40 min |
| 1:50 | Low Code | Discusión: ¿qué pregunta hace primero el árbol? | 10 min |
| 2:00 | — | **Descanso** | 10 min |
| 2:10 | Pro Code | Notebook pasos 1-3: cargar, preparar, entrenar | 20 min |
| 2:30 | Pro Code | Pasos 4-6: visualizar árbol, evaluar, importancia | 25 min |
| 2:55 | Pro Code | Pasos 7-8: predecir nuevos + experimento profundidad | 15 min |
| 3:10 | Pro Code | Discusión: overfitting (más profundo ≠ mejor) | 10 min |
| 3:20 | Reto | Explicar reto + trabajo individual | 5 min |
| 3:25 | Reto | Tiempo de trabajo | 25 min |
| 3:50 | Reto | Compartir resultados: ¿qué variable pesa más? | 10 min |
| 4:00 | — | Cierre, anticipo sesión 4 (regresión) | — |

---

## 📝 Notas para cada bloque

### Bloque 1: Teoría (45 min)

**Slide 3 — ¿Qué es clasificar?**
- Preguntar al grupo: "Cuando abren su email, ¿cómo saben si un correo es spam?"
- Mostrar que ellos YA clasifican mentalmente todo el tiempo
- Los 5 ejemplos van de lo cotidiano (email) a lo profesional (pacientes)

**Slide 4 — Analogía del doctor**
- Esta es la analogía central de la sesión. Mapea perfectamente:
  - Síntomas = Features
  - Casos anteriores = Datos de entrenamiento
  - Diagnóstico = Predicción
  - Exámenes = Evaluación
- Pregunta: "¿Qué pasa si el doctor SOLO ha visto gripe? ¿Puede diagnosticar dengue?"
  → Conectar con la importancia de datos diversos

**Slide 5 — Árboles de decisión**
- El árbol visual es el momento "ah-já" para audiencia no técnica
- Recorrer el árbol de arriba a abajo con el grupo
- Ejercicio: "Si un estudiante estudió 5 horas y asistió a clase, ¿qué predice?"
- Enfatizar: "El modelo descubrió estas preguntas SOLO. No le dijimos qué preguntar."

**Slide 6 — Buenas vs malas preguntas**
- La analogía de 20 preguntas conecta muy bien
- Mostrar visualmente: grupos mezclados (mala separación) vs grupos puros (buena separación)
- No es necesario explicar Gini o entropía. Solo el concepto: "separa bien los grupos"

**Slide 7-8 — Accuracy y Matriz de confusión**
- Accuracy es intuitivo: "de 100, ¿cuántos acertó?"
- La advertencia del 95% accuracy con spam es CLAVE: evita sobreconfianza en un solo número
- Matriz de confusión: "verde diagonal = aciertos, fuera = errores"
- No entrar en precisión/recall/F1 todavía — se ve en sesión 6

### Bloque 2: Low Code — Orange (1.5 horas)

**Preparación:**
- Tener Orange instalado con el dataset `estudiantes.csv`
- El workflow es: CSV File Import → Data Table → Select Columns → Tree → Tree Viewer → Test & Score

**Demo instructor (15 min):**
1. Cargar `estudiantes.csv`
2. En Select Columns: mover "aprueba" a Target, "id" a Meta (ignorar)
3. Conectar widget Tree → abrir configuración → max depth = 3
4. Conectar Tree Viewer → mostrar el árbol visual
5. Leer juntos: "¿Cuál es la primera pregunta? ¿Qué pasa si Sí? ¿Y si No?"
6. Conectar Test & Score → ver accuracy

**Práctica (40 min):**
- Replicar el workflow
- Exploración adicional: probar con Naive Bayes, Random Forest y comparar en Test & Score
- Cambiar max_depth en Tree y ver cómo cambia el árbol
- Ejercicio: "Conectar un widget Predictions → ver las predicciones para cada estudiante"

**Discusión (10 min):**
- "¿Qué variable pregunta primero el árbol?" (Respuesta esperada: horas_estudio o nota_parcial)
- "¿Cambió algo cuando aumentaron la profundidad?"
- Conectar: "En código veremos exactamente la importancia de cada variable"

### Bloque 3: Pro Code — Google Colab (1.5 horas)

**El notebook tiene 8 pasos progresivos:**

Pasos 1-3 (20 min): cargar datos, explorar distribuciones (gráficas coloridas aprueba vs reprueba), preparar train/test. Enfatizar la comparación visual: "Miren cómo los aprobados se separan en horas de estudio."

Pasos 4-6 (25 min): entrenar árbol, visualizarlo (el momento "wow"), evaluar con accuracy y matriz de confusión. Señalar: "Es el mismo árbol que vieron en Orange, pero ahora podemos guardarlo, reutilizarlo, automatizarlo."

Pasos 7-8 (15 min): predecir 5 estudiantes nuevos (las asistentes modifican los valores) y el experimento de profundidad que demuestra overfitting visualmente.

**Discusión overfitting (10 min):**
- Mostrar la gráfica: train sube pero test puede bajar
- "Es como memorizar las respuestas del examen pasado: sacas 100 en ese, pero fallas en uno nuevo"
- Concepto: la profundidad correcta es donde TEST es más alto

### Bloque 4: Reto (30 min)

**"¿Aprueba o no?"**
1. Usar `estudiantes.csv` (ya lo tienen)
2. Entrenar un clasificador (Orange o Colab, a elección)
3. Predecir 5 estudiantes inventados por ellas
4. Responder: ¿qué variable pesa más?

**Criterios de éxito:**
- ✅ Entrenó un modelo de clasificación
- ✅ Reporta el accuracy obtenido
- ✅ Predijo correctamente 5 estudiantes nuevos
- ✅ Identificó la variable más importante

**Respuestas esperadas del dataset:**
- Las variables más importantes serán: `horas_estudio`, `nota_parcial1` o `nota_parcial2`
- Accuracy esperado: ~87-95% dependiendo de la profundidad y random split
- La variable `tiene_internet` y `horas_sueno` deberían tener baja importancia relativa

---

## 📊 Sobre el dataset estudiantes.csv

50 registros de estudiantes con 8 features y 1 label binario:

| Feature | Tipo | Rango | Descripción |
|---------|------|-------|-------------|
| horas_estudio | Float | 1.0 - 8.5 | Horas de estudio semanal |
| asistencia_pct | Int | 25 - 99 | % de asistencia a clase |
| nota_parcial1 | Float | 1.2 - 4.8 | Nota primer parcial (1-5) |
| nota_parcial2 | Float | 1.5 - 5.0 | Nota segundo parcial (1-5) |
| tareas_entregadas | Int | 2 - 10 | De 10 tareas posibles |
| horas_sueno | Int | 4 - 8 | Horas de sueño por noche |
| tiene_internet | Bin | 0/1 | Acceso a internet en casa |
| actividades_extra | Bin | 0/1 | Participa en extracurriculares |
| **aprueba** | **Bin** | **0/1** | **TARGET: 1=aprueba, 0=reprueba** |

Distribución: ~54% aprueba, ~46% reprueba (balanceado).

---

## ❓ Preguntas frecuentes

**"¿Por qué un árbol y no otro modelo?"**
Porque es el más visual e interpretable. Puedes LEER las reglas. En sesión 6 compararemos varios modelos.

**"¿Qué significa profundidad?"**
Es cuántas preguntas en cascada puede hacer. Profundidad 3 = máximo 3 preguntas antes de decidir. Más profundidad = más detalle pero riesgo de memorizar.

**"¿100% accuracy es bueno?"**
Casi nunca. Probablemente está memorizando (overfitting). Un accuracy de 85-95% en test es normalmente excelente.

**"¿Puedo usar esto en mi trabajo?"**
Sí. Este mismo código funciona para predecir: clientes que compran, empleados que renuncian, productos defectuosos, etc. Solo cambia el dataset.

---

## 📎 Archivos de la sesión

1. `Sesion3_Clasificacion.pptx` — Presentación (13 slides)
2. `Sesion3_Clasificacion.ipynb` — Notebook de Google Colab
3. `estudiantes.csv` — Dataset de 50 estudiantes
4. `Guia_Instructor_Sesion3.md` — Esta guía

---

*Próxima sesión: Regresión: prediciendo números (Miércoles, Mayo 13)*
