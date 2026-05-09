<p align="center">
  <img src="https://unl.edu.ec/sites/default/files/logogris%20copia.png" width="280" alt="Logo UNL"/>
</p>

<h1 align="center">Unidad 1 — Lógica Proposicional</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Asignatura-Matemáticas%20Discretas-003366?style=flat-square&labelColor=003366&color=5b8dd9"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Estudiante-Willy%20Ramírez-5b8dd9?style=flat-square&labelColor=003366&color=5b8dd9"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Unidad-1%20de%203-003366?style=flat-square&labelColor=5b8dd9&color=003366"/>
</p>

<p align="center">
  <a href="./README.md">← Volver al inicio</a>
</p>

---

## 📑 Índice

1. [Introducción](#1-introducción)
2. [Resumen Teórico](#2-resumen-teórico)
   - [2.1 Definición de Proposición](#21-definición-de-proposición)
   - [2.2 Tipos de Proposiciones](#22-tipos-de-proposiciones)
   - [2.3 Conectores Lógicos](#23-conectores-lógicos)
   - [2.4 Tablas de Verdad](#24-tablas-de-verdad)
   - [2.5 Principales Leyes Lógicas](#25-principales-leyes-lógicas)
   - [2.6 Reglas de Inferencia](#26-reglas-de-inferencia)
3. [Ejercicios Resueltos](#3-ejercicios-resueltos)
4. [Ejercicio Aplicado](#4-ejercicio-aplicado)
5. [Reflexión Personal](#5-reflexión-personal)
6. [Actividades APE](#6-actividades-ape)

---

## 1. Introducción

La lógica proposicional es el punto de entrada al pensamiento matemático formal. Antes de poder diseñar un algoritmo, verificar un circuito digital o demostrar la corrección de un programa, se necesita un lenguaje preciso que elimine la ambigüedad del lenguaje natural.

Esta unidad establece ese lenguaje: un sistema de símbolos, operadores y reglas de deducción que permite razonar con certeza. Cada concepto aquí aprendido tiene una contraparte directa en la programación: los conectores lógicos son los operadores booleanos, las tablas de verdad son las pruebas de cobertura, y las reglas de inferencia son la base de todo motor lógico o sistema experto.

---

## 2. Resumen Teórico

### 2.1 Definición de Proposición

Una **proposición** es un enunciado declarativo al que se le puede asignar un único valor de verdad: **Verdadero (V)** o **Falso (F)**, nunca ambos simultáneamente. Este principio se conoce como la **ley del tercio excluido**.

> **Criterio práctico:** Un enunciado es una proposición si y solo si responde a la pregunta "¿es esto verdad o mentira?" sin ambigüedad.

**Ejemplos de proposiciones válidas:**

| Enunciado | Valor |
|-----------|-------|
| "El número 7 es primo." | V |
| "Python es un lenguaje compilado." | F |
| "2 + 2 = 5" | F |

**Ejemplos que NO son proposiciones:**

| Enunciado | Razón |
|-----------|-------|
| "¿Cuántos bits tiene un byte?" | Es una pregunta |
| "Abre el archivo" | Es una orden |
| "Este enunciado es falso" | Paradoja, sin valor definido |

---

### 2.2 Tipos de Proposiciones

Las proposiciones se clasifican según su estructura interna:

**Proposiciones Simples (Atómicas)**
Son unidades indivisibles que no contienen conectores lógicos. Se representan con letras minúsculas: $p$, $q$, $r$, $s$...

- $p$: "El servidor está activo."
- $q$: "El usuario tiene sesión iniciada."

**Proposiciones Compuestas (Moleculares)**
Se forman combinando dos o más proposiciones simples mediante conectores lógicos. Su valor de verdad depende de los valores de sus componentes y del conector utilizado.

- "El servidor está activo **y** el usuario tiene sesión iniciada." → $p \land q$
- "**Si** el servidor está activo, **entonces** la página carga." → $p \to r$

---

### 2.3 Conectores Lógicos

Los conectores —también llamados operadores lógicos— son los instrumentos que permiten construir proposiciones compuestas. Su comportamiento queda completamente definido por su tabla de verdad.

| Símbolo | Nombre | Lectura en español | Condición de verdad |
|:---:|:---|:---|:---|
| $\neg$ | Negación | "No es cierto que..." | Opuesto al valor original |
| $\land$ | Conjunción | "... y ..." | Solo V cuando ambas son V |
| $\lor$ | Disyunción (inclusiva) | "... o ..." | Solo F cuando ambas son F |
| $\to$ | Condicional | "Si ... entonces ..." | Solo F cuando antecedente es V y consecuente es F |
| $\leftrightarrow$ | Bicondicional | "... si y solo si ..." | V cuando ambas tienen el mismo valor |

**Tabla de verdad fundamental de los cinco conectores:**

| $p$ | $q$ | $\neg p$ | $p \land q$ | $p \lor q$ | $p \to q$ | $p \leftrightarrow q$ |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| V | V | F | V | V | V | V |
| V | F | F | F | V | F | F |
| F | V | V | F | V | V | F |
| F | F | V | F | F | V | V |

> **Nota sobre el condicional:** La implicación $p \to q$ solo es falsa en un caso: cuando la premisa ($p$) es verdadera y la conclusión ($q$) es falsa. Equivale a decir que "no se puede romper una promesa si nunca se hizo".

---

### 2.4 Tablas de Verdad

Una tabla de verdad es un método sistemático para determinar el valor de verdad de una proposición compuesta en **todas las combinaciones posibles** de sus variables.

**Procedimiento de construcción:**

1. Identificar las variables proposicionales ($p$, $q$, $r$...).
2. Determinar el número de filas: $2^n$, donde $n$ = cantidad de variables.
3. Completar las columnas de variables con alternancia binaria.
4. Calcular columnas intermedias (subexpresiones).
5. Calcular la columna final (expresión completa).
6. Clasificar el resultado.

**Clasificación según la columna final:**

| Clasificación | Definición | Columna final |
|:---|:---|:---:|
| **Tautología** | Siempre verdadera, sin importar los valores | Solo V |
| **Contradicción** | Siempre falsa, sin importar los valores | Solo F |
| **Contingencia** | Puede ser V o F según los valores | Mezcla de V y F |

---

### 2.5 Principales Leyes Lógicas

Las leyes proposicionales son equivalencias que permiten **simplificar o transformar** expresiones lógicas sin alterar su valor de verdad. Son el álgebra de la lógica.

| Ley | Equivalencia |
|:---|:---|
| **Doble Negación** | $\neg(\neg p) \equiv p$ |
| **De Morgan (conjunción)** | $\neg(p \land q) \equiv \neg p \lor \neg q$ |
| **De Morgan (disyunción)** | $\neg(p \lor q) \equiv \neg p \land \neg q$ |
| **Conmutativa** | $p \land q \equiv q \land p \quad;\quad p \lor q \equiv q \lor p$ |
| **Asociativa** | $(p \land q) \land r \equiv p \land (q \land r)$ |
| **Distributiva** | $p \land (q \lor r) \equiv (p \land q) \lor (p \land r)$ |
| **Idempotencia** | $p \land p \equiv p \quad;\quad p \lor p \equiv p$ |
| **Absorción** | $p \land (p \lor q) \equiv p$ |
| **Implicación Material** | $p \to q \equiv \neg p \lor q$ |
| **Exportación** | $(p \land q) \to r \equiv p \to (q \to r)$ |
| **Identidad** | $p \land V \equiv p \quad;\quad p \lor F \equiv p$ |
| **Complemento** | $p \land \neg p \equiv F \quad;\quad p \lor \neg p \equiv V$ |

> **Aplicación directa en código:** La ley de De Morgan explica por qué `!(A && B)` es equivalente a `!A || !B` en cualquier lenguaje de programación.

---

### 2.6 Reglas de Inferencia

Las reglas de inferencia son esquemas de razonamiento válido que permiten derivar conclusiones a partir de premisas. A diferencia de las leyes (que son equivalencias), las reglas de inferencia son **implicaciones**: si las premisas son verdaderas, la conclusión necesariamente lo es.

**Reglas fundamentales:**

<br>

**Modus Ponendo Ponens (MPP)**
> Si tengo la implicación y su antecedente, puedo afirmar el consecuente.

$$\frac{p \to q \quad,\quad p}{\therefore\ q}$$

*Ejemplo:* "Si el código compila, el programa ejecuta. El código compila. → El programa ejecuta."

---

**Modus Tollendo Tollens (MTT)**
> Si tengo la implicación y la negación del consecuente, puedo negar el antecedente.

$$\frac{p \to q \quad,\quad \neg q}{\therefore\ \neg p}$$

*Ejemplo:* "Si hay conexión, la página carga. La página no carga. → No hay conexión."

---

**Silogismo Hipotético (SH)**
> Si la conclusión de una implicación es la premisa de otra, puedo unirlas.

$$\frac{p \to q \quad,\quad q \to r}{\therefore\ p \to r}$$

*Ejemplo:* "Si el usuario es admin, puede modificar. Si puede modificar, puede borrar. → Si es admin, puede borrar."

---

**Silogismo Disyuntivo (SD)**
> De una disyunción, si niego una alternativa, afirmo la otra.

$$\frac{p \lor q \quad,\quad \neg p}{\therefore\ q}$$

---

**Adición y Simplificación:**

$$\text{Adición: } \frac{p}{\therefore\ p \lor q} \qquad \text{Simplificación: } \frac{p \land q}{\therefore\ p}$$

---

## 3. Ejercicios Resueltos

Los siguientes ejercicios cubren los cinco tipos establecidos en la guía de la asignatura. Cada uno incluye procedimiento detallado en el documento PDF correspondiente.

> 📁 Todos los archivos se encuentran en la carpeta [`./Evidencias/`](./Evidencias/)

---

<details>
<summary><b>Ejercicio 1 — Traducción de lenguaje natural a simbólico</b></summary>

<br>

**Descripción:** Conversión de enunciados del lenguaje cotidiano a fórmulas lógicas formales, identificando proposiciones simples y conectores implícitos.


📄 [Ver resolución en PDF](./Evidencias/Ejercicio_01_Traduccion.pdf)

</details>

---

<details>
<summary><b>Ejercicio 2 — Construcción de tabla de verdad</b></summary>

<br>

**Descripción:** Análisis exhaustivo de la fórmula $p \to (q \lor \neg p)$ mediante tabla de verdad con todas sus columnas intermedias.

**Variables:** $p$, $q$ → $2^2 = 4$ filas.

| $p$ | $q$ | $\neg p$ | $q \lor \neg p$ | $p \to (q \lor \neg p)$ |
|:---:|:---:|:---:|:---:|:---:|
| V | V | F | V | **V** |
| V | F | F | F | **F** |
| F | V | V | V | **V** |
| F | F | V | V | **V** |

**Clasificación:** Contingencia (columna final tiene V y F).

📄 [Ver resolución completa en PDF](./Evidencias/Ejercicio_02_TablaVerdad.pdf)

</details>

---

<details>
<summary><b>Ejercicio 3 — Identificación de tautología, contradicción o contingencia</b></summary>

<br>

**Descripción:** Determinar la clasificación de la fórmula $(p \to q) \leftrightarrow (\neg q \to \neg p)$.

Esta fórmula expresa que un condicional y su contrarrecíproco son equivalentes.

| $p$ | $q$ | $\neg p$ | $\neg q$ | $p \to q$ | $\neg q \to \neg p$ | $(p \to q) \leftrightarrow (\neg q \to \neg p)$ |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| V | V | F | F | V | V | **V** |
| V | F | F | V | F | F | **V** |
| F | V | V | F | V | V | **V** |
| F | F | V | V | V | V | **V** |

**Clasificación: Tautología** — la columna final es siempre verdadera. Confirma que $p \to q \equiv \neg q \to \neg p$.

📄 [Ver resolución completa en PDF](./Evidencias/Ejercicio_03_Clasificacion.pdf)

</details>

---

<details>
<summary><b>Ejercicio 4 — Aplicación de leyes proposicionales</b></summary>

<br>

**Descripción:** Simplificación de la expresión $\neg(\neg p \land q) \lor (p \land \neg q)$ usando leyes lógicas, paso a paso.

**Procedimiento:**

| Paso | Expresión | Ley aplicada |
|:---:|:---|:---|
| 0 | $\neg(\neg p \land q) \lor (p \land \neg q)$ | Expresión original |
| 1 | $(\neg\neg p \lor \neg q) \lor (p \land \neg q)$ | De Morgan |
| 2 | $(p \lor \neg q) \lor (p \land \neg q)$ | Doble Negación |
| 3 | $p \lor [\neg q \lor (p \land \neg q)]$ | Asociativa |
| 4 | $p \lor [(\neg q \lor p) \land (\neg q \lor \neg q)]$ | Distributiva |
| 5 | $p \lor [(\neg q \lor p) \land \neg q]$ | Idempotencia |
| 6 | $p \lor \neg q$ | Absorción |

**Resultado:** $\neg(\neg p \land q) \lor (p \land \neg q) \equiv p \lor \neg q$

📄 [Ver resolución completa en PDF](./Evidencias/Ejercicio_04_Leyes.pdf)

</details>

---

<details>
<summary><b>Ejercicio 5 — Validación de argumento lógico</b></summary>

<br>

**Descripción:** Determinar si el siguiente argumento es válido usando reglas de inferencia.

**Argumento:**
> 1. Si el sistema detecta intrusión, activa la alarma. $(p \to q)$
> 2. Si activa la alarma, notifica al administrador. $(q \to r)$
> 3. El sistema detectó una intrusión. $(p)$
> 4. **∴ El administrador fue notificado.** $(\therefore r)$

**Demostración:**

| Paso | Expresión | Justificación |
|:---:|:---|:---|
| 1 | $p \to q$ | Premisa 1 |
| 2 | $q \to r$ | Premisa 2 |
| 3 | $p \to r$ | Silogismo Hipotético (1, 2) |
| 4 | $p$ | Premisa 3 |
| 5 | $\therefore r$ | Modus Ponens (3, 4) |

**Conclusión: El argumento es válido.** La conclusión se deduce necesariamente de las premisas.

📄 [Ver resolución completa en PDF](./Evidencias/Ejercicio_05_Validacion.pdf)

</details>

---

## 4. Ejercicio Aplicado

### Caso: Sistema de Control de Acceso a un Laboratorio de Cómputo

**Planteamiento del problema:**

El laboratorio de cómputo de la facultad tiene el siguiente reglamento de acceso:

> *"Un estudiante puede usar los equipos únicamente si presenta su carnet universitario vigente y tiene horario asignado. Si usa los equipos sin autorización, el sistema genera un reporte automático y se notifica al docente responsable."*

---

**Definición de proposiciones simples:**

| Variable | Proposición |
|:---:|:---|
| $p$ | El estudiante presenta el carnet universitario vigente. |
| $q$ | El estudiante tiene horario asignado. |
| $r$ | El estudiante puede usar los equipos. |
| $s$ | El sistema genera un reporte automático. |
| $t$ | El docente responsable es notificado. |

---

**Expresión simbólica del reglamento:**

Regla de acceso:
$$(p \land q) \to r$$

Regla de incumplimiento (si accede sin autorización, es decir $r$ ocurre pero $\neg(p \land q)$):
$$\neg(p \land q) \land r \to (s \land t)$$

---

**Análisis con tabla de verdad (Regla principal):**

| $p$ | $q$ | $p \land q$ | $r$ esperada | $(p \land q) \to r$ |
|:---:|:---:|:---:|:---:|:---:|
| V | V | V | V | V — Acceso permitido ✓ |
| V | F | F | F | V — Sin horario, no accede |
| F | V | F | F | V — Sin carnet, no accede |
| F | F | F | F | V — Sin ambos, no accede |

---

**Aplicación de leyes para análisis del caso de infracción:**

Si se detecta que el estudiante usa equipos sin autorización ($r = V$ pero $p \land q = F$):

$$\neg(p \land q) \land r$$

Aplicando De Morgan a $\neg(p \land q)$:

$$(\neg p \lor \neg q) \land r$$

Esto cubre tres escenarios: falta de carnet, falta de horario, o ambos. En cualquiera de ellos, el sistema debe ejecutar $s \land t$ (reporte + notificación).

---

**Conclusión:**

El modelo lógico demuestra que el sistema de acceso es **consistente**: no existe combinación de entradas que permita un acceso no autorizado sin activar la respuesta de seguridad. Este tipo de análisis formal es la base del diseño de sistemas de control de acceso en ciberseguridad, donde cada condición de entrada debe estar formalmente especificada y verificada.

---

## 5. Reflexión Personal

<details>
<summary><b>¿Qué fue lo más difícil de entender?</b></summary>

<br>

El concepto que más tiempo me tomó asimilar fue el **condicional lógico** ($p \to q$). Intuitivamente, parece contradictorio que una implicación sea verdadera cuando la premisa es falsa, independientemente del consecuente. ¿Cómo puede ser verdad "si llueve, me mojo" cuando simplemente no llueve?

La clave fue entenderlo no como una relación causal, sino como una **promesa**: la implicación solo se "rompe" si la premisa se cumple y la conclusión no. Si la premisa nunca ocurre, la promesa jamás fue puesta a prueba, por lo tanto sigue siendo válida. Una vez que adopté esa perspectiva, el condicional comenzó a tener pleno sentido, especialmente en el contexto de los `if` en programación.

</details>

<details>
<summary><b>¿Qué tema comprendí mejor?</b></summary>

<br>

Las **reglas de inferencia** fueron el tema que encontré más intuitivo y satisfactorio. El Modus Ponens, en particular, refleja exactamente la forma en que razonamos cotidianamente: si sabemos que cierta condición lleva a cierto resultado, y la condición se cumple, entonces el resultado sigue. Identificar ese patrón en argumentos del lenguaje natural y traducirlo a forma simbólica me resultó natural desde el principio.

También fue muy útil descubrir que el Silogismo Hipotético es la base teórica de las cadenas de llamadas en programación: si función A llama a B y B llama a C, entonces A transitivamente depende de C.

</details>

<details>
<summary><b>¿Cómo puedo aplicar la lógica en mi carrera?</b></summary>

<br>

La lógica proposicional tiene aplicaciones directas en al menos tres áreas de la ingeniería de computación que me interesan:

**Diseño de algoritmos:** Toda estructura de control (`if`, `while`, `switch`) es una proposición compuesta. Saber simplificar condiciones con las leyes de De Morgan o la implicación material permite escribir código más limpio y eficiente.

**Ciberseguridad:** Como evidencié en el ejercicio aplicado, las políticas de acceso y los sistemas de detección de intrusos son modelos lógicos. La verificación formal de que un sistema no tiene "rutas de entrada no autorizadas" es, en esencia, demostrar que ciertas fórmulas son tautologías.

**Inteligencia Artificial:** Los sistemas basados en reglas y los motores de inferencia —pilares de la IA simbólica— son implementaciones computacionales directas de las reglas de inferencia estudiadas en esta unidad. Entender Modus Ponens es entender cómo razona un sistema experto.

</details>

---

## 6. Actividades APE

Actividades Práctico-Experimentales desarrolladas durante la unidad:

| # | Actividad | Enlace |
|:---:|:---|:---:|
| APE 01 | Lógica y Simbolización | [📄 Ver documento](./Evidencias/APE_01.pdf) |
| APE 02 | Tablas de Verdad | [📄 Ver documento](./Evidencias/APE_02.pdf) |
| APE 03 | Leyes Lógicas | [📄 Ver documento](./Evidencias/APE_03.pdf) |
| APE 04 | Circuitos y Compuertas Lógicas | [📄 Ver documento](./Evidencias/APE_04.pdf) |
| APE 05 | Reglas de Inferencia | [📄 Ver documento](./Evidencias/APE_05.pdf) |
| APE 06 | Proyecto Integrador de Unidad | [📄 Ver documento](./Evidencias/APE_06.pdf) |

> **Nota:** Los archivos PDF de cada APE se encuentran dentro de la carpeta `Evidencias/` del repositorio.

---

<p align="center">
  <a href="./README.md">← Volver al inicio del portafolio</a>
  &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="./Unidad_2.md">Unidad 2 →</a>
</p>

---

<div align="center">
  <sub>Willy Ramírez &nbsp;·&nbsp; Matemáticas Discretas &nbsp;·&nbsp; Universidad Nacional de Loja &nbsp;·&nbsp; 2026</sub>
</div>
