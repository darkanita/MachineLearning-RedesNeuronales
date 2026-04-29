# 📋 Guía del Instructor — Sesión 1
## ¿Qué es Machine Learning y por qué importa?

**Módulo:** Aprendizaje Automático · IU Digital de Antioquia  
**Fecha:** Miércoles, Abril 29, 2026  
**Duración:** 4 horas  
**Instructora:** Darkanita

---

## 🎯 Objetivos de aprendizaje

Al finalizar esta sesión, las asistentes podrán:
1. Explicar qué es Machine Learning con sus propias palabras
2. Diferenciar entre programación tradicional y ML
3. Identificar los 3 tipos de ML (supervisado, no supervisado, refuerzo)
4. Crear un clasificador de imágenes sin código (Teachable Machine)
5. Ejecutar su primer notebook de ML en Google Colab

---

## ⏱️ Cronograma detallado

| Hora | Bloque | Actividad | Duración |
|------|--------|-----------|----------|
| 0:00 | Bienvenida | Presentación, expectativas, hielo roto | 10 min |
| 0:10 | Teoría | ¿Qué es ML? Prog. tradicional vs ML | 15 min |
| 0:25 | Teoría | Analogía: aprender a cocinar | 10 min |
| 0:35 | Teoría | 3 tipos de ML + ejemplos | 15 min |
| 0:50 | Teoría | Casos reales: Netflix, Spotify, bancos | 10 min |
| 1:00 | Teoría | ¿Cuándo SÍ / NO usar ML? + Pipeline | 10 min |
| 1:10 | — | **Descanso** | 5 min |
| 1:15 | Low Code | Demo Teachable Machine (instructor) | 15 min |
| 1:30 | Low Code | Práctica guiada: clasificar frutas | 40 min |
| 2:10 | Low Code | Compartir resultados + discusión | 15 min |
| 2:25 | — | **Descanso** | 10 min |
| 2:35 | Pro Code | Intro a Google Colab (qué es, cómo funciona) | 10 min |
| 2:45 | Pro Code | Ejecutar notebook paso a paso (guiado) | 35 min |
| 3:20 | Pro Code | Experimentar: cambiar valores y ver resultados | 15 min |
| 3:35 | Reto | Explicar reto + tiempo de trabajo | 25 min |
| 4:00 | — | Cierre, resumen, anticipo sesión 2 | — |

---

## 🧊 Actividad rompehielo (10 min)

**"¿Dónde viste IA hoy?"**  
Pedir a cada asistente que cuente un momento del día en que interactuó con IA sin darse cuenta (autocompletar del teclado, recomendaciones de YouTube, filtro de spam, GPS, etc.).

Esto abre la conversación mostrando que ML ya es parte de sus vidas.

---

## 📝 Notas para cada bloque

### Bloque 1: Teoría (1 hora)

**Slide 3 — ¿Qué es ML?**
- Pregunta al grupo: "Si yo les doy 1000 fotos de gatos y perros, ¿cómo le explicarían a una computadora la diferencia?"
- Dejar que respondan → mostrar que es muy difícil escribir reglas
- Entonces presentar: ML = darle los datos y dejar que la computadora descubra las reglas sola
- **Tip:** Evitar jerga técnica. Usar "modelo" como sinónimo de "programa que aprendió"

**Slide 4 — Analogía cocina**
- Esta analogía conecta muy bien con audiencia no técnica
- Enfatizar: "Un chef experimentado NO sigue una receta, SABE por experiencia cuánta sal poner. Así funciona ML."

**Slide 5 — 3 tipos**
- Supervisado: "Le muestras ejemplos con respuesta → aprende a dar la respuesta"
- No supervisado: "Le das datos SIN respuesta → encuentra grupos similares"
- Refuerzo: "Aprende jugando, como un bebé que toca algo caliente y no lo vuelve a hacer"
- **Pregunta al grupo:** "¿Netflix usa supervisado o no supervisado?" (Respuesta: ambos)

**Slide 7 — ¿Cuándo SÍ/NO?**
- Este slide es MUY importante para que no piensen que ML es magia
- Enfatizar: "Si puedes escribir las reglas en un IF/ELSE simple, NO necesitas ML"
- Ejemplo concreto: "Para saber si un número es par, no necesitas ML. Para saber si un email es spam, sí."

### Bloque 2: Low Code — Teachable Machine (1.5 horas)

**Preparación previa:**
- Verificar que teachablemachine.withgoogle.com funcione en los navegadores
- Tener objetos de ejemplo (frutas, útiles escolares, etc.)
- Si no hay webcam, se pueden subir imágenes

**Demo del instructor (15 min):**
1. Abrir Teachable Machine → Image Project → Standard
2. Crear 2 clases: "Lápiz" vs "Borrador"
3. Tomar ~20 fotos de cada uno con la webcam
4. Entrenar (toma ~10 segundos)
5. Probar en vivo → mostrar la confianza cambiando
6. Pregunta: "¿Qué pasa si le muestro algo que NO es ni lápiz ni borrador?"

**Práctica guiada (40 min):**
- Las asistentes clasifican 3 categorías de su elección
- Circular por el salón ayudando
- Errores comunes:
  - Pocas fotos (mínimo 30 por clase)
  - Fotos muy similares (variar ángulo, distancia, fondo)
  - No cambiar el nombre de las clases

**Discusión (15 min):**
- ¿Quién logró buena precisión?
- ¿A quién le falló? ¿Por qué creen que falló?
- Introducir concepto: "más datos = mejor modelo"

### Bloque 3: Pro Code — Google Colab (1 hora)

**Antes de abrir Colab, explicar:**
- "Es como Google Docs pero para código"
- "No necesitan instalar NADA"
- "Van a EJECUTAR código, no ESCRIBIR código"
- "Si algo falla, no se rompió nada. Solo vuelvan a ejecutar."

**Compartir el notebook:**
- Subir `Sesion1_Mi_Primer_Modelo_ML.ipynb` a Google Drive
- Compartir enlace con las asistentes
- Pedir que hagan "Archivo → Guardar una copia en Drive"

**Ejecutar juntos, celda por celda:**
- Paso 0: "Solo estamos cargando herramientas, como abrir una caja de herramientas"
- Paso 1: "Miren, son datos de flores. Es una tabla como Excel"
- Paso 2: "Estas 2 líneas son TODO lo que necesitamos para entrenar un modelo"
- Paso 3: "¡El modelo descubrió las reglas solo! Miren el árbol"
- Paso 4: "93%+ de precisión con 2 líneas de código"
- Paso 5: "AHORA SÍ, cambien los números y vean qué pasa"

**Experimentación libre (15 min):**
- Pedir que cambien los valores de la flor imaginaria
- Pregunta: "¿Pueden hacer que prediga cada una de las 3 especies?"
- Pedir que observen la gráfica de importancia de variables

### Bloque 4: Reto (30 min)

**Instrucciones claras:**
1. Abrir Teachable Machine
2. Elegir 3 categorías de objetos (pueden ser del área de trabajo)
3. Entrenar con mínimo 30 fotos por categoría
4. Probar con objetos nuevos
5. Exportar → copiar enlace → compartir en el chat/grupo

**Criterios de éxito (simple):**
- ✅ Tiene 3 categorías con nombres propios
- ✅ Funciona en la demo en vivo
- ✅ Compartió el enlace

---

## 🛠️ Requisitos técnicos

| Recurso | URL | Notas |
|---------|-----|-------|
| Google Teachable Machine | teachablemachine.withgoogle.com | Chrome recomendado, necesita webcam |
| Google Colab | colab.research.google.com | Requiere cuenta Google |
| Notebook de la sesión | (subir a Drive y compartir) | Las asistentes guardan copia |
| Presentación | Sesion1_Que_es_ML.pptx | 13 slides |

---

## ❓ Preguntas frecuentes de las asistentes

**"¿Necesito saber programar?"**  
No. En la parte Pro Code solo ejecutamos código pre-escrito. Es como usar una calculadora: no necesitas saber cómo funciona por dentro.

**"¿ML y la IA son lo mismo?"**  
ML es una parte de la IA. La IA es el concepto general (máquinas que parecen inteligentes). ML es la técnica específica de aprender de datos.

**"¿Esto va a reemplazar mi trabajo?"**  
ML es una herramienta. Así como Excel no reemplazó contadores sino los hizo más productivos, ML les dará superpoderes en su área.

**"¿Por qué Python y no Excel?"**  
Excel es genial para datos pequeños. Cuando tienes miles o millones de datos, Python es más eficiente. Pero el concepto es el mismo.

---

## 📎 Archivos de la sesión

1. `Sesion1_Que_es_ML.pptx` — Presentación (13 slides)
2. `Sesion1_Mi_Primer_Modelo_ML.ipynb` — Notebook de Google Colab
3. `Guia_Instructor_Sesion1.md` — Esta guía

---

*Próxima sesión: Datos: el combustible del ML (Miércoles, Mayo 06)*
