# Banco Preliminar de Casos — Toma de Decisiones Asistida con IA

El estudio sigue un diseño experimental **comparativo y exploratorio**, donde se evaluará el comportamiento de distintos modelos de IA generativa frente a un conjunto estandarizado de problemas de decisión multicriterio.

---

## 1. Casos

Se desarrollarán, aproximadamente, ocho casos de decisión distribuidos en cuatro niveles de complejidad (dos casos por nivel), buscando representar distintos contextos de toma de decisiones y permitir la comparación sistemática entre modelos de IA.

| Nivel | Características |
|---|---|
| Nivel 1 | Información completa y criterios objetivos. |
| Nivel 2 | Múltiples preferencias y compensaciones (*trade-offs*). |
| Nivel 3 | Riesgo con probabilidades conocidas. |
| Nivel 4 | Alta incertidumbre e información incompleta. |

## 2. Prompts

Cada caso tendrá dos prompts base estandarizados. El primer tipo será **ambiguo**, sólo con los datos primordiales; el segundo tipo será **más específico**, con datos, preferencias y detalles. Después, si el periodo de tiempo alcanza, se generarán variaciones para estudiar el **efecto de framing** (cómo el contexto y las palabras moldean la manera en que se percibe o entiende la información). Ejemplos de variaciones: cambiar el orden de la información, el orden de las alternativas, modificar ligeramente la redacción, o presentar primero los beneficios o los riesgos.

En cuanto a la metodología de los prompts, ambos tipos se clasifican como *zero-shot prompting* (se proveen cero ejemplos a la IA; se da directamente el escenario del problema y se pide la recomendación). El tipo 1 es un **basic zero-shot**, mientras que el tipo 2 es un **contextualised zero-shot**.

- **Prompt 1 (Ambiguous).**
- **Prompt 2 (Specific).**

> Al omitir ejemplos previos de resolución (*zero-shot*), se obliga al modelo de IA a depender exclusivamente de sus capacidades nativas de cálculo, lógica y análisis de decisión bajo incertidumbre.

---

## Nivel 1 — Problemas con información completa y criterios objetivos

### Problema 1

*Caso tomado del paper **"The best vacuum robot cleaners with the help of the COMET and the TOPSIS methods"***

**Tabla 1. Criterios elegidos C₁–C₈ y sus valores característicos para las variables lingüísticas bajo/alto**

| Cᵢ | Nombre | Tipo | Unidad |
|---|---|---|---|
| C1 | Engine power | Profit | Watt [W] |
| C2 | Noise level | Cost | Decibel [dB] |
| C3 | Bag capacity | Profit | Litre [L] |
| C4 | Water tank capacity | Profit | Litre [L] |
| C5 | Charging time | Cost | Hour [h] |
| C6 | Working time | Profit | Minutes [min] |
| C7 | Battery capacity | Profit | Mega ampere hour [mAh] |
| C8 | Price | Cost | Polish złoty [PLN] |

**Tabla 2. Conjunto de alternativas y desempeño**

| Alternativa | C1 | C2 | C3 | C4 | C5 | C6 | C7 | C8 |
|---|---|---|---|---|---|---|---|---|
| Ecovacs Deebot U2 | 26 | 66.0 | 0.40 | 0.30 | 4.5 | 110 | 2600 | 899.0 |
| Ecovacs Deebot OZMO T8+ | 40 | 67.0 | 0.42 | 0.24 | 6.5 | 175 | 5200 | 3199.0 |
| Ecovacs Deebot OZMO 950 | 40 | 67.0 | 0.43 | 0.24 | 5.0 | 200 | 5200 | 1899.0 |
| Ecovacs Deebot OZMO T8 Aivi | 40 | 67.0 | 0.42 | 0.24 | 6.5 | 175 | 5200 | 2899.0 |
| Roborock S5 MAX | 58 | 67.0 | 0.46 | 0.30 | 5.0 | 180 | 5200 | 699.0 |
| Roborock E4 | 58 | 66.0 | 0.64 | 0.18 | 6.0 | 200 | 5200 | 959.0 |
| Karcher RC 3 | 24 | 71.0 | 0.35 | 0.00 | 4.0 | 120 | 2600 | 2229.0 |
| Kiano Elegance Robot | 30 | 65.0 | 0.35 | 0.35 | 5.0 | 120 | 4400 | 1199.0 |
| Black&Decker RVA425B-QW | 36 | 65.0 | 1.00 | 0.00 | 4.0 | 90 | 2500 | 1399.0 |
| Roborock E4 | 58 | 69.0 | 0.64 | 0.18 | 6.0 | 150 | 5200 | 949.0 |
| Xiaomi MI Robot Vacuum-Mop Pro | 33 | 78.0 | 0.55 | 0.20 | 3.0 | 90 | 3200 | 1288.0 |
| Ariete Evolution 2712 | 25 | 67.6 | 0.50 | 0.00 | 3.0 | 90 | 2600 | 999.0 |

**Tabla 3. Matriz de decisión normalizada**

| Aᵢ | C1 | C2 | C3 | C4 | C5 | C6 | C7 | C8 |
|---|---|---|---|---|---|---|---|---|
| A1 | 0.05882 | 0.92308 | 0.07692 | 0.85714 | 0.57143 | 0.18182 | 0.03704 | 0.9200 |
| A2 | 0.47059 | 0.84615 | 0.10769 | 0.68571 | 0.00000 | 0.77273 | 1.00000 | 0.0000 |
| A3 | 0.47059 | 0.84615 | 0.12308 | 0.68571 | 0.42857 | 1.00000 | 1.00000 | 0.5200 |
| A4 | 0.47059 | 0.84615 | 0.10769 | 0.68571 | 0.00000 | 0.77273 | 1.00000 | 0.1200 |
| A5 | 1.00000 | 0.84615 | 0.16923 | 0.85714 | 0.42857 | 0.81818 | 1.00000 | 1.0000 |
| A6 | 1.00000 | 0.92308 | 0.44615 | 0.51429 | 0.14286 | 1.00000 | 1.00000 | 0.8960 |
| A7 | 0.00000 | 0.53846 | 0.00000 | 0.00000 | 0.71429 | 0.27273 | 0.03704 | 0.3880 |
| A8 | 0.17647 | 1.00000 | 0.00000 | 1.00000 | 0.42857 | 0.27273 | 0.70370 | 0.8000 |
| A9 | 0.35294 | 1.00000 | 1.00000 | 0.00000 | 0.71429 | 0.00000 | 0.00000 | 0.7200 |
| A10 | 1.00000 | 0.69231 | 0.44615 | 0.51429 | 0.14286 | 0.54545 | 1.00000 | 0.9000 |
| A11 | 0.26471 | 0.00000 | 0.30769 | 0.57143 | 1.00000 | 0.00000 | 0.25926 | 0.7644 |
| A12 | 0.02941 | 0.80000 | 0.23077 | 0.00000 | 1.00000 | 0.00000 | 0.03704 | 0.8800 |

**Tabla 4. Resultado de los 12 robots aspiradores obtenido secuencialmente por el modelo**

| Alternativa | COMET_pref | TOPSIS_pref | COMET_rank | TOPSIS_rank |
|---|---|---|---|---|
| 1 | 0.4533 | 0.4705 | 9 | 9 |
| 2 | 0.4854 | 0.4907 | 7 | 7 |
| 3 | 0.6343 | 0.5996 | 4 | 4 |
| 4 | 0.5004 | 0.5002 | 6 | 6 |
| 5 | 0.7649 | 0.6883 | 1 | 1 |
| 6 | 0.7403 | 0.6659 | 2 | 2 |
| 7 | 0.2438 | 0.3092 | 12 | 12 |
| 8 | 0.5477 | 0.5315 | 5 | 5 |
| 9 | 0.4734 | 0.4842 | 8 | 8 |
| 10 | 0.6551 | 0.6155 | 3 | 3 |
| 11 | 0.3959 | 0.4286 | 10 | 10 |
| 12 | 0.3722 | 0.4252 | 11 | 11 |

**La mejor alternativa es A5 (Roborock S5 MAX).**

#### Prompts

> **Prompt 1.** Oye, quiero comprarme una aspiradora robot para mi casa. Tengo varias opciones: Ecovacs Deebot U2, Ecovacs Deebot OZMO T8, Ecovacs Deebot 950, Ecovacs Deebot OZMO T8 Aivi, Robot Rock S5 MAX, Robot Rock E4, Karcher RC 3, Kiano Elegance Robot, Black & Decker RVA425B-QW, Robot Rock E4, Xiaomi MI Robot Vacuum-Mop Pro, Ariete Evolution 2712, pero no sé por cuál decidirme. ¿Me ayudas a elegir la mejor?

> **Prompt 2.** Hola. Estoy comparando varios modelos de robots aspiradores porque no sé cuál me conviene más. Tengo una lista con opciones: Ecovacs Deebot U2, Ecovacs Deebot OZMO T8, Ecovacs Deebot 950, Ecovacs Deebot OZMO T8 Aivi, Robot Rock S5 MAX, Robot Rock E4, Karcher RC 3, Kiano Elegance Robot, Black&Decker RVA425B-QW, Robot Rock E4, Xiaomi MI Robot Vacuum-Mop Pro, Ariete Evolution 2712. Para decidirme quiero tomar en cuenta cosas fijas como la potencia del motor, qué tanto ruido hacen, la capacidad del tanque de agua y de la bolsa, cuánto tarda en cargar, cuánto le dura la batería en uso y, el precio. ¿Cuál opción me recomiendas?

*Nota: en ambos prompts se adjuntará la siguiente tabla de información para que sea más amigable con la IA.*

| Modelo | Potencia (W) | Ruido (dB) | Bolsa (L) | Tanque de agua (L) | Carga (h) | Autonomía (min) | Batería (mAh) | Precio (PLN) |
|---|---|---|---|---|---|---|---|---|
| Ecovacs Deebot U2 | 26 | 66.0 | 0.40 | 0.30 | 4.5 | 110 | 2600 | 899.0 |
| Ecovacs Deebot OZMO T8+ | 40 | 67.0 | 0.42 | 0.24 | 6.5 | 175 | 5200 | 3199.0 |
| Ecovacs Deebot OZMO 950 | 40 | 67.0 | 0.43 | 0.24 | 5.0 | 200 | 5200 | 1899.0 |
| Ecovacs Deebot OZMO T8 Aivi | 40 | 67.0 | 0.42 | 0.24 | 6.5 | 175 | 5200 | 2899.0 |
| Roborock S5 MAX | 58 | 67.0 | 0.46 | 0.30 | 5.0 | 180 | 5200 | 699.0 |
| Roborock E4 | 58 | 66.0 | 0.64 | 0.18 | 6.0 | 200 | 5200 | 959.0 |
| Karcher RC 3 | 24 | 71.0 | 0.35 | 0.00 | 4.0 | 120 | 2600 | 2229.0 |
| Kiano Elegance Robot | 30 | 65.0 | 0.35 | 0.35 | 5.0 | 120 | 4400 | 1199.0 |
| Black&Decker RVA425B-QW | 36 | 65.0 | 1.00 | 0.00 | 4.0 | 90 | 2500 | 1399.0 |
| Roborock E4 | 58 | 69.0 | 0.64 | 0.18 | 6.0 | 150 | 5200 | 949.0 |
| Xiaomi MI Robot Vacuum-Mop Pro | 33 | 78.0 | 0.55 | 0.20 | 3.0 | 90 | 3200 | 1288.0 |
| Ariete Evolution 2712 | 25 | 67.6 | 0.50 | 0.00 | 3.0 | 90 | 2600 | 999.0 |

---

### Problema 2 — Choosing a car

*Caso de estudio propuesto y diseñado por el equipo del proyecto.*

Supóngase que una persona quiere comprar un auto y tiene el dinero exacto, los precios son fijos, y no le importa el color, la marca ni el estatus. Se busca mejorar la seguridad y funcionalidad (airbags, cámara de reversa, tamaño de la cajuela) combinado con el mejor desempeño (eficiencia de combustible, potencia y tamaño de llantas).

> **Nota metodológica:** se definió un objetivo distinto al de reducción de costo, para poder observar en el futuro si la IA alucina o sesga de forma irracional recomendando la opción más barata.

**Alternativas:** A1 (Renault Kwid), A2 (Suzuki Swift Boostergreen), A3 (Chevrolet Aveo Sedán).

**Criterios**

| Cᵢ | Nombre | Unidad |
|---|---|---|
| C1 | Price | MXN |
| C2 | Fuel efficiency (Combined) | Kilómetros por litro (km/L) |
| C3 | Engine power | Horsepower (HP) |
| C4 | Airbags quantity | Unidades |
| C5 | Rear view camera | Indicador binario (0/1) |
| C6 | Boot capacity | Litros |
| C7 | Wheel size | Pulgadas |

**Datos**

| Alternativa | C1 | C2 | C3 | C4 | C5 | C6 | C7 |
|---|---|---|---|---|---|---|---|
| A1 (Renault Kwid) | 251,500 | 22.1 | 66 | 4 | 0 | 290 | 14" |
| A2 (Suzuki Swift Boostergreen) | 339,990 | 24.7 | 82 | 6 | 1 | 242 | 16" |
| A3 (Chevrolet Aveo Sedán) | 261,500 | 20.4 | 98 | 6 | 1 | 475 | 15" |

#### Solución de referencia posible — metodología SMART (MCDA)

**1. Asignación de pesos relativos**

| Cⱼ | Importancia (0–100) | Wⱼ |
|---|---|---|
| C4 | 100 | 0.220 |
| C5 | 90 | 0.198 |
| C6 | 85 | 0.187 |
| C2 | 65 | 0.143 |
| C3 | 55 | 0.121 |
| C7 | 45 | 0.099* |
| C1 | 15 | 0.033 |
| **Total** | **455** | **1.000** |

*\* En el documento original aparece como 0.999, lo cual es inconsistente con el total de 1.000; probablemente un error de dedo por 0.099. Revisar el archivo fuente antes de publicar.*

**2. Normalización de atributos**

| | Car A | Car B | Car C |
|---|---|---|---|
| C1 | 100.0 | 0.0 | 88.7 |
| C2 | 39.5 | 100.0 | 0.0 |
| C3 | 0.0 | 50.0 | 100.0 |
| C4 | 0.0 | 100.0 | 100.0 |
| C5 | 0.0 | 100.0 | 100.0 |
| C6 | 20.6 | 0.0 | 100.0 |
| C7 | 0.0 | 100.0 | 50.0 |

**3. Valor global**

$$V(A_i) = \sum_{j=1}^{n} w_j \cdot V_j(x_{ij})$$

**Matriz de decisión final**

| Alternativa | Método SMART | Rank |
|---|---|---|
| A1 | 12.80 | 3 |
| A2 | 72.05 | 2 |
| A3 | 80.48 | 1 |

**La decisión óptima sería A3, y la alternativa secundaria sería A2.**

#### Prompts

> **Prompt 1.** Hola. Estoy por comprar un auto y mi objetivo principal es la seguridad y funcionalidad con el mejor desempeño. Estoy entre el Car A (Renault Kwid a $251,500), Car B (Suzuki Swift Boostergreen a $339,990) y Car C (Chevrolet Aveo Sedán a $261,500). Te voy a dar unos datos de cada uno, ¿cuál me recomiendas?

> **Prompt 2.** Hola, necesito decidir qué coche comprar entre tres opciones específicas: el Renault Kwid, el Suzuki Swift Boostergreen y el Chevrolet Aveo Sedán. Ya tengo el dinero exacto y los precios son fijos, así que el costo no es mi prioridad número uno. Lo que realmente me importa es que tenga la mejor seguridad, las mayores funciones para su uso (si tiene cámara de reversa y el tamaño de la cajuela) combinado con un buen rendimiento de gasolina, potencia y tamaño de las llantas. Te paso los datos de rendimiento, caballos de fuerza y espacio de cada uno para que me ayudes a decidir.

---

## Nivel 2 — Problemas con preferencias y compensaciones entre objetivos

### Problema 1 — "The summer job"

*Ejemplo tomado del libro **Making Hard Decisions: An Introduction to Decision Analysis**, p. 128.*

Sam Chu tiene dos ofertas de trabajo para el verano. La primera es como asistente en un negocio local, con salario mínimo ($5.25/h), de 25 a 35 horas por semana (principalmente entre semana, con fines de semana libres), durante tres meses. La segunda es en una cuadrilla de mantenimiento de senderos para una organización de conservación: 10 semanas de trabajo pesado, 40 horas/semana a $6.50/h, en un bosque nacional en otro estado, con campamento y convivencia constante con desconocidos.

Sam tiene dos objetivos: ganar dinero y divertirse. El dinero tiene una escala natural (dólares); la diversión no, por lo que Sam construyó una escala del 1 al 5:

**Tabla 4.5 — Escala construida para la diversión del verano**

| Nivel | Descripción |
|---|---|
| 5 (Mejor) | Grupo grande y agradable. Muchas nuevas amistades. Trabajo agradable, el tiempo pasa rápido. |
| 4 | Grupo pequeño pero agradable de amigos. Trabajo interesante, tiempo libre con algunos amigos en actividades disfrutables. |
| 3 | No se hacen nuevos amigos. Ocio dedicado a actividades típicas. Paga justa por el trabajo realizado. |
| 2 | Trabajo difícil. Compañeros se quejan de la paga y condiciones. Algunos fines de semana con amigos, otros aburridos. |
| 1 (Peor) | Trabajo extremadamente difícil, malas condiciones. Tiempo libre aburrido; pocas o ninguna amistad disponible. |

**Árbol de decisión**

- **Forest Job** (nivel de diversión incierto)
 - Nivel 5 (prob. 0.10) → Salario $2600.00, Diversión 5
 - Nivel 4 (prob. 0.25) → Salario $2600.00, Diversión 4
 - Nivel 3 (prob. 0.40) → Salario $2600.00, Diversión 3
 - Nivel 2 (prob. 0.20) → Salario $2600.00, Diversión 2
 - Nivel 1 (prob. 0.05) → Salario $2600.00, Diversión 1
- **In-Town Job** (horas promedio de trabajo por semana inciertas; diversión fija en nivel 3)
 - 40 horas (prob. 0.35) → Salario $2730.00, Diversión 3
 - 34 horas (prob. 0.50) → Salario $2320.50, Diversión 3
 - 30 horas (prob. 0.15) → Salario $2047.50, Diversión 3

#### Prompts

> **Prompt 1.** Tengo dos ofertas de trabajo para este verano: uno en un negocio local de mi ciudad y otro arreglando senderos en un bosque nacional. No sé cuál aceptar, ¿qué me recomiendas?

> **Prompt 2.** Hola, tengo dos ofertas de trabajo de verano y no sé qué hacer porque mis metas son ganar dinero y divertirme. El primer trabajo es en mi ciudad; me pagan el salario mínimo ($5.25 la hora), trabajo entre 25 y 35 horas por tres meses, y tengo los fines de semana libres para estar con mis amigos, aunque las horas exactas de trabajo semanal son algo inciertas; hay una probabilidad de 35% que trabaje 40 horas, 50% por 34 horas y 15% por 30 horas. El segundo trabajo es en un bosque nacional en otro estado manteniendo senderos; son 10 semanas fijas de 40 horas a $6.50 la hora (ganaría seguro $2600), pero implica acampar todo el tiempo y convivir con desconocidos las 24 horas del día, lo que me da miedo es que el ambiente sea increíble o una completa miseria. En el de la ciudad sé que la diversión será un nivel medio, pero en el bosque hay mucha incertidumbre. Evalúe los posibles niveles de diversión: 5-4 (disfrutar el trabajo y hacer nuevos amigos) con 35% de probabilidad, 3 (sólo me pagan por el trabajo hecho, no hice nuevos amigos) 40%, y 2-1 (las condiciones laborales son horribles y es aburrido) con 25%. ¿Cuál me recomiendas?

---

### Problema 2 — Choosing a university

*Caso de estudio propuesto y diseñado por el equipo del proyecto.*

**Alternativas:** A1 (Hochschule für Wirtschaft und Recht Berlin), A2 (University of Potsdam).

**Criterios**

| Cⱼ | Nombre | Descripción |
|---|---|---|
| C1 | Professional immersion & networking | Oportunidades de eventos, ferias de empleo y prácticas. (Escala 1–10, maximizar) |
| C2 | Cost of living & accommodation | Presupuesto mensual estimado en euros. (Escala en €, minimizar) |
| C3 | Student quality of life | Balance entre tranquilidad, cultura y facilidad de integración. (Escala 1–10, maximizar) |

**Datos**

| Cᵢ | A1 (HWR Berlin) | A2 (Potsdam) |
|---|---|---|
| C1 | 9/10 | 6/10 |
| C2 | 1,100 € | 850 € |
| C3 | 8/10 | 7/10 |

**Pesos**

| Cᵢ | Wⱼ |
|---|---|
| C1 | 0.50 |
| C2 | 0.30 |
| C3 | 0.20 |

> El trade-off en este ejemplo es que A1 ofrece una ventaja significativa en networking, pero a un costo extra de €250 mensuales. Entonces, ¿vale la pena pagar 29% más del presupuesto por esa ventaja profesional?

#### Solución posible usando el método TOPSIS

**Normalización euclidiana por criterio**

$$C_1: \sqrt{9^2 + 6^2} = 10.817 \qquad C_2: \sqrt{1100^2 + 850^2} = 1390.144 \qquad C_3: \sqrt{8^2 + 7^2} = 10.63$$

**Multiplicación de cada valor normalizado por su peso** ($v_{ij} = r_{ij} \cdot w_j$)

*A1 (HWR Berlin)*

$$v_{11} = \left(\frac{9}{10.817}\right) \cdot 0.50 = 0.416 \qquad v_{12} = \left(\frac{1100}{1390.144}\right) \cdot 0.30 = 0.237 \qquad v_{13} = \left(\frac{8}{10.63}\right) \cdot 0.20 = 0.151$$

*A2 (Universidad de Potsdam)*

$$v_{21} = \left(\frac{6}{10.817}\right) \cdot 0.50 = 0.277 \qquad v_{22} = \left(\frac{850}{1390.144}\right) \cdot 0.30 = 0.183 \qquad v_{23} = \left(\frac{7}{10.630}\right) \cdot 0.20 = 0.132$$

Los mejores valores máximos son C1 y C3; el mejor valor mínimo es C2.

- **Solución ideal positiva (A⁺):** {0.416, 0.183, 0.151}
- **Solución ideal negativa (A⁻):** {0.277, 0.237, 0.132}

**Distancias a las soluciones ideales**

$$S_1^+ = \sqrt{(0.416-0.416)^2 + (0.237-0.183)^2 + (0.151-0.151)^2} = 0.0540$$
$$S_1^- = \sqrt{(0.416-0.277)^2 + (0.237-0.237)^2 + (0.151-0.132)^2} = 0.1403$$
$$S_2^+ = \sqrt{(0.277-0.416)^2 + (0.183-0.183)^2 + (0.132-0.151)^2} = 0.1403$$
$$S_2^- = \sqrt{(0.277-0.277)^2 + (0.183-0.237)^2 + (0.132-0.132)^2} = 0.054$$

**Coeficiente de cercanía relativa**

$$C_i = \frac{S_i^-}{S_i^+ + S_i^-}$$

| Alternativa | Cálculo | Resultado |
|---|---|---|
| A1 | 0.1403 / (0.054 + 0.1403) | **0.722** |
| A2 | 0.054 / (0.1403 + 0.054) | **0.278** |

**Usando el método TOPSIS, la alternativa óptima es A1 (HWR Berlin).**

#### Prompts

> **Prompt 1.** Me voy a ir de intercambio a Alemania y tengo que elegir entre la Hochschule für Wirtschaft und Recht Berlin y la Universidad de Potsdam. ¿Cuál me recomiendas elegir?

> **Prompt 2.** Hola, tengo que decidir a qué universidad irme de intercambio, si a la HWR en Berlín o a la Universidad de Potsdam. Tengo un dilema con mis prioridades. Hice una evaluación de las ventajas profesionales, del costo de vida en euros, y de la calidad de vida. Berlín me da nivel de networking e inmersión profesional un 9/10 frente a un 6/10 de Potsdam; de calidad de vida estudiantil le doy un 8/10 a la de Berlín y 7/10 a la de Potsdam. El problema es el dinero, vivir en Berlín me cuesta unos 1,100 euros al mes, mientras que en Potsdam gastaría unos 850 euros. O sea, Berlín es un 29% más caro. Quiero que me ayudes a decidir si crees que vale la pena pagar ese extra, ¿cuál de las dos opciones me recomiendas?

---

## Nivel 3 — Problemas con riesgo y probabilidades

### Problema 1 — "Risk"

*Ejemplo tomado del libro **Making Hard Decisions: An Introduction to Decision Analysis**, p. 463.*

Imagina que tienes la oportunidad de jugar uno de dos juegos, pero solo una vez.

- **Juego 1:** ganar $30 con probabilidad 0.5, perder $1 con probabilidad 0.5.
- **Juego 2:** ganar $2000 con probabilidad 0.5, perder $1900 con probabilidad 0.5.

El Juego 1 tiene un valor esperado de $14.50; el Juego 2, de $50.00. Si se decidiera solo con base en el valor esperado, se elegiría el Juego 2. Sin embargo, la mayoría consideraría el Juego 2 más riesgoso, y es razonable suponer que la mayoría de las personas preferiría el Juego 1: jugando 10 veces, lo peor en el Juego 1 es perder $10, mientras que en el Juego 2 es perder $19,000.

#### Prompts

> **Prompt 1.** Me ofrecieron jugar a una de dos apuestas rápidas de dinero, en uno puedo ganar $30 y perder $1, mientras que en el otro puedo ganar $2000, pero solo puedo jugar una vez. ¿Cuál debería elegir para ganar más?

> **Prompt 2.** Hola, me dieron a elegir entre jugar dos juegos de azar por única vez y tengo dudas sobre el riesgo. El Juego 1 me da un 50% de probabilidad de ganar $30 y un 50% de perder $1. El Juego 2 me da un 50% de probabilidad de ganar $2000, pero un 50% de perder $1900. ¿Cuál opción me sugieres tomar?

---

### Problema 2 — An immediate job offer versus postgraduate study

*Caso de estudio propuesto y diseñado por el equipo del proyecto.*

Un recién graduado no está seguro de qué decisión tomar: hacer un posgrado o comenzar a trabajar de inmediato.

**Alternativas:** A1 (oferta de trabajo inmediata), A2 (programa de posgrado de tiempo completo).

**Criterios y pesos**

| Cᵢ | Criterio | Peso |
|---|---|---|
| C1 | ROI (retorno de inversión) a corto plazo | 0.15 |
| C2 | Tope salarial a largo plazo | 0.20 |
| C3 | Pasión y afinidad intelectual (personal) | 0.15 |
| C4 | Costo de oportunidad temporal (minimizar tiempo fuera del mercado) | 0.10 |
| C5 | Flexibilidad si la IA automatiza el rol | 0.15 |
| C6 | Networking | 0.15 |
| C7 | Resiliencia a la automatización | 0.10 |

**Datos** (escala 1–10)

| | A1 | A2 |
|---|---|---|
| C1 | 10 | 2 |
| C2 | 6 | 9 |
| C3 | 5 | 9 |
| C4 | 10 | 3 |
| C5 | 4 | 8 |
| C6 | 6 | 9 |
| C7 | 5 | 8 |

**Árbol de decisión (escenarios de demanda / automatización)**

| Alternativa | Escenario 1: Alta demanda | Escenario 2: Alto nivel de automatización |
|---|---|---|
| A1 | VNE $250k | VNE $140k |
| A2 | VNE $380k | VNE $180k |

#### Prompts

> **Prompt 1.** No sé si aceptar una oferta de trabajo que ya tengo en la mano o mejor meterme a estudiar un posgrado a tiempo completo. ¿Qué me conviene más para mi futuro?

> **Prompt 2.** Hola, estoy en una duda sobre qué hacer con mi futuro. Tengo una oferta de trabajo inmediata y también la opción de hacer un posgrado a tiempo completo. Para decidir, me importan varias cosas: el retorno de inversión a corto plazo, el tope salarial a futuro, mi pasión, el tiempo que estaré fuera del mercado y qué tan protegido esté el rol frente a la automatización por IA. El trabajo me da dinero e ingresos estables ya, pero si la IA automatiza el rol me quedo estancado. El posgrado me da más resiliencia y sueldo a largo plazo, pero salgo del mercado unos años. ¿Cuál opción me recomiendas?

---

## Nivel 4 — Problemas con alta incertidumbre e información incompleta

### Problema 1 — "Investing in the Stock Market, Revisited"

*Ejemplo tomado del libro **Making Hard Decisions: An Introduction to Decision Analysis**, p. 467.*

Un inversionista tiene tres opciones: una acción de alto riesgo, una de bajo riesgo, o una cuenta de ahorros que paga $500. Al invertir en acciones debe pagar una comisión de $200. Si el mercado sube, ganará $1700 (alto riesgo) o $1200 (bajo riesgo); si se mantiene igual, $300 o $400 respectivamente; si baja, pierde $800 (alto riesgo) pero gana $100 (bajo riesgo). Las probabilidades de que el mercado suba, se mantenga igual o baje son 0.5, 0.3 y 0.2, respectivamente.

**Valores esperados (EMV)**

| Alternativa | EMV |
|---|---|
| High-Risk Stock | 580 |
| Low-Risk Stock | 540 |
| Savings Account | 500 |

**Tabla 13.2 — Función de utilidad**

| Valor en dólares | Valor de utilidad |
|---|---|
| 1500 | 1.00 |
| 1000 | 0.86 |
| 500 | 0.65 |
| 200 | 0.52 |
| 100 | 0.46 |
| -100 | 0.33 |
| -1000 | 0.00 |

Un maximizador de valor esperado elegiría la acción de alto riesgo. Sin embargo, al recalcular con la utilidad esperada (EU):

| Alternativa | EU |
|---|---|
| High-Risk Stock | 0.638 |
| Low-Risk Stock | **0.652** |
| Savings Account | 0.650 |

**La acción preferida es la de bajo riesgo**, aunque no difiere mucho de la cuenta de ahorros. Según esta función de utilidad, el inversionista es lo suficientemente averso al riesgo como para considerar la acción de alto riesgo como la menos preferida de las tres.

#### Prompts

> **Prompt 1.** Tengo unos ahorros y quiero invertirlos. Estoy pensando entre comprar acciones de alto riesgo, unas de bajo riesgo o meterlo a una cuenta de ahorros normal. ¿Qué me dará más dinero?

> **Prompt 2.** Hola, quiero invertir un dinero y tengo tres opciones, pero el mercado está muy inestable y no sé qué pasará. Las opciones son: acciones de alto riesgo, acciones de bajo riesgo o una cuenta de ahorros segura que me da $500 fijos. Si compro acciones, tengo que pagar $200 de comisión de entrada. Si el mercado sube, gano $1700 con el riesgo alto y $1200 con el bajo; si se queda igual, gano $300 o $400 respectivamente; y si baja, pierdo $800 en el de alto riesgo pero gano $100 en el de bajo riesgo. Dicen que las probabilidades de que el mercado suba, baje o siga igual son de 0.5, 0.2 y 0.3. ¿Cuál me recomiendas?

---

### Problema 2 — Moving abroad with a start-up in Berlin

*Caso de estudio propuesto y diseñado por el equipo del proyecto.*

Una joven profesional con un trabajo estable en su país recibe una oferta para unirse a una start-up en etapa temprana en Berlín, Alemania. El puesto promete crecimiento rápido y experiencia internacional invaluable, pero la empresa solo tiene financiamiento asegurado para los próximos ocho meses. Además, no domina el idioma local, y la crisis de vivienda en Berlín hace que encontrar un departamento sea un proceso caótico y costoso.

**Incertidumbre e información incompleta:** no se sabe si la empresa asegurará una nueva ronda de inversión o quebrará en menos de un año; tampoco se sabe qué tan rápido se adaptará a la cultura y al clima invernal, ni si logrará construir una red de apoyo en el extranjero.

**Alternativas:** A1 (aceptar la oferta y mudarse a Berlín), A2 (rechazar la oferta y quedarse en el trabajo actual).

**Criterios**

| Cᵢ | Criterio |
|---|---|
| C1 | Desarrollo profesional (aprendizaje, valor en el CV, y prospectos a largo plazo) |
| C2 | Estabilidad económica y red de seguridad (seguridad de ingresos y capacidad de ahorro a corto plazo) |
| C3 | Bienestar (niveles de estrés, cercanía con seres queridos, adaptación cultural) |
| C4 | Flexibilidad y tolerancia al riesgo (margen de maniobra si algo sale mal) |

**Árbol de decisión**

| Alternativa | Escenario | Probabilidad | Resultado anual |
|---|---|---|---|
| A1 (Berlín) | Éxito de la start-up | 40% | $120,000 |
| A1 (Berlín) | Fracaso de la start-up | 60% | $20,000 |
| A2 (Quedarse) | Promoción interna | 30% | $65,000 |
| A2 (Quedarse) | Estancamiento profesional | 70% | $45,000 |

**Cálculo de EMV**

$$A1: (120{,}000 \cdot 0.40) + (20{,}000 \cdot 0.60) = \$60{,}000$$
$$A2: (65{,}000 \cdot 0.30) + (45{,}000 \cdot 0.70) = \$51{,}000$$

#### Prompts

> **Prompt 1.** Me ofrecieron trabajo e invertir en una start-up en Berlín, pero tengo miedo de dejar mi trabajo estable actual por la incertidumbre de moverme a otro país. ¿Debería irme o quedarme?

> **Prompt 2.** Hola, necesito ayuda con una decisión que me tiene muy ansiosa. Tengo un trabajo bastante estable en mi país, pero me acaban de ofrecer un puesto en una start-up y la posibilidad de convertirme en inversionista de esta. Pero está en etapa inicial y en Berlín. La oferta promete crecer rápido y darme currículum internacional, pero hay demasiada información incompleta y riesgos… Hay 40% de que la start-up resulte un éxito, dejándome $120,000 anual; y un 60% de que fracase, dejándome con $12,000 anual. No hablo alemán, hay crisis de vivienda allá y el clima de invierno me pone nerviosa. Mis opciones son: aceptar e irme, o rechazarlo y quedarme. Quedándome tengo un 30% de que me asciendan, y un 70% de quedarme estancada. Me da miedo arrepentirme si no lo intento. ¿Cuál me recomiendas?

---

## Referencias

Clemen, R. T. (1996). *Making hard decisions: An Introduction to Decision Analysis*. South Western Educational Publishing.

Yelmikheiev, M., & Norek, T. (2021). Comparison of MCDA methods based on distance to reference objects - a simple study case. *Procedia Computer Science, 192*, 4972–4979. https://www.sciencedirect.com/science/article/pii/S1877050921020147
