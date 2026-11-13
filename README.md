# GoTogether · Dos sentencias, dos soluciones

Trabajo práctico 3 de Desarrollo de Sistemas Web (Front End), IFTS 29. Segundo cuatrimestre de 2026.

**Grupo 20 · Hallows Code**  
**Startup asignada:** GoTogether, creada por estudiantes del IFTS 16.  
**Bloque:** Autorización (S09-B).

GoTogether propone coordinar viajes en transporte público entre fans del K-pop. La landing presenta dos decisiones del recorrido de una persona que quiere sumarse a un grupo de viaje. Cada diagrama permite elegir un escenario, seguir la rama correspondiente y consultar la explicación del flujo.

## Cómo ver el proyecto

- [Repositorio del grupo en GitHub](https://github.com/mendez-daniela/tp3-gotogether)
- [Landing de GoTogether publicada en Vercel](https://tp3-gotogether.vercel.app/)

## Las dos soluciones propuestas

| Regla | Qué haría el agente | Ejemplo para recorrer en la landing |
| --- | --- | --- |
| R3 · Incorporación al grupo | Consultaría la edad y, si la persona es menor, buscaría la autorización de su tutor. Si falta el permiso, mantendría bloqueada la incorporación e indicaría que debe presentarlo. | Compará los recorridos de un menor con autorización y de otro sin ella. Solo el primero puede avanzar. |
| R4 · Confirmación personal | Comprobaría que el trayecto, la identidad y la edad estén verificados. Con esas tres verificaciones completas, habilitaría la confirmación personal a mayores de edad y a menores con autorización. | Una persona adulta con el trayecto sin verificar queda detenida. Con las tres verificaciones completas, puede pasar a confirmar el viaje. |

## Integrantes y aportes

| Integrante | Rol | Tarea asignada |
| --- | --- | --- |
| [Sol Prinzen](https://github.com/solprinz) | Análisis y lógica | Desglosar R3 y R4 en dos fichas con los datos de entrada, las condiciones, las consecuencias y una explicación de cada regla. |
| [Lucas Sosa](https://github.com/Strashoy) | Diseño de diagramas | Convertir las fichas de Sol en dos diagramas de flujo con pasos, flechas y una excepción por flujo, indicando cuándo corresponde la intervención humana. |
| [Daniela Méndez](https://github.com/mendez-daniela) | Operación agéntica | Usar los textos de Sol y los diagramas de Lucas para guiar al agente de programación por etapas, subir el código a GitHub y publicar la landing. |
| [Juan Pablo](https://github.com/JPFinal) | Pruebas de calidad (QA) | Auditoría de interfaz en versión Desktop, prueba de navegación/desplegables con teclado/clic y reporte de iteraciones y mejoras de QA. ([Ver informe de auditoría ↓](#auditoria-qa)) |
| [Alejandro Ramos](https://github.com/AleR25) | Documentación | Redactar el README, registrar los aportes y las herramientas de IA del equipo y documentar una iteración con el pedido de mejora y su resultado. |

## Construcción con IA

| Integrante | Aplicación | Modelo | Uso en el TP3 | Cambios solicitados |
| --- | --- | --- | --- | --- |
| Alejandro Ramos | Codex | GPT-6 Astra | Revisión del README según la consigna y organización de los estilos de la landing. | Ajustar el formato del README, corregir inconsistencias y separar los estilos de `index.html` en `styles.css`. |
| Daniela Méndez | Pendiente de confirmar | DeepSeek-V4.1-Flash-1017 | Construcción de la landing por etapas a partir de las fichas y los diagramas. | [Registrar una corrección solicitada durante el desarrollo.] |
| Juan Pablo | Antigravity | Gemini 3.8 Flash | Auditoría de calidad de interfaz en Desktop, diseño de matriz de pruebas, validación de accesibilidad por teclado y verificación de coherencia lógica contra la rúbrica. | Reportar e integrar casos límite de intervención humana en desplegables, restaurar texto completo de R4 y añadir estilos de foco accesible (`:focus-visible`). |

### Una iteración de la landing

En la primera versión de la landing, le pedimos al agente que representara las condiciones necesarias para habilitar la confirmación personal del viaje. Al revisar el diagrama, observamos que todas las ramas tenían el mismo peso visual. Esto dificultaba seguir el recorrido de una persona menor de edad con autorización de su tutor y podía dar a entender que el permiso era suficiente para pasar a la confirmación.

Para mejorar la lectura, le pedimos al agente que incorporara un selector de escenarios. En la versión actual, al elegir «Menor con autorización», el diagrama resalta el camino correspondiente y atenúa las demás ramas. Así se aprecia el orden de los controles. Primero se comprueba que el trayecto, la identidad y la edad estén verificados. Luego, al tratarse de una persona menor de edad, se consulta la autorización del tutor. Si consta el permiso, se habilita el paso de confirmación personal.

### Separación de los estilos de la landing

La primera versión reunía en `index.html` el contenido de la página y las reglas de diseño. Además, varios elementos de los diagramas repetían los mismos estilos. Alejandro le pidió a Codex que trasladara esas reglas a una hoja de estilos compartida. Ahora ambos diagramas usan [styles.css](styles.css), donde se pueden ajustar los colores, las líneas y las etiquetas desde un solo lugar.

Probamos la versión local en Microsoft Edge. Comprobamos que la página cargaba la hoja de estilos, que el botón activaba el tema oscuro y que, en ambos diagramas, seleccionar «Menor con autorización» resaltaba el recorrido correspondiente.

### Iteración colaborativa a partir del control de QA

Durante la revisión de calidad en computadora (Desktop) sobre la versión publicada, el área de QA (Juan Pablo) auditó la interfaz, los flujos interactivos y los desplegables contra la rúbrica oficial. Se detectaron tres aspectos a mejorar:
1. La sentencia original R4 estaba incompleta (faltaba la frase condicionante final).
2. Los desplegables técnicos omitían los casos de excepción y derivación a intervención humana.
3. Los botones de selección de caminos carecían de indicador de foco visible al navegar exclusivamente con teclado.

Juan Pablo elevó estas observaciones en un reporte formal a Daniela Méndez (Operación Agéntica). Se instruyó al agente a actualizar `index.html` y `styles.css`, subsanando los puntos observados. Posteriormente, QA realizó una re-evaluación verificando el cierre satisfactorio de todos los casos de prueba.

---

<a id="auditoria-qa"></a>
## Auditoría de Calidad (QA) y Accesibilidad Desktop

**Responsable:** Juan Pablo  
**Entorno de prueba:** Desktop (Microsoft Edge / Google Chrome en Windows)  
**Herramienta de asistencia IA:** Antigravity (Modelo: Gemini 3.8 Flash)

### 1. Matriz de Casos de Prueba

| ID | Elemento / Flujo | Criterio de Aceptación | Resultado Inicial | Resultado Final |
| :--- | :--- | :--- | :---: | :---: |
| **CP-01** | **Identidad y Logo** | El logo de GoTogether debe ser el original, verse completo, nítido y sin deformaciones. | ✅ Pasa | ✅ **Aprobado** |
| **CP-02** | **Sentencias Originales** | Las dos sentencias (R3 y R4) deben coincidir textualmente con la consigna asignada. | ⚠️ Falla *(R4 incompleta)* | ✅ **Aprobado** |
| **CP-03** | **Desplegables (Mecánica)** | Las fichas `<details>` deben abrirse y cerrarse fluidamente tanto con clic de mouse como con teclado (`Tab` + `Enter`/`Space`). | ✅ Pasa | ✅ **Aprobado** |
| **CP-04** | **Desplegables (Contenido)** | Deben detallar datos, condición, acción, resultado y **caso límite con intervención humana** (Rúbrica Nivel Propone). | ⚠️ Falla *(Faltaban casos límite)* | ✅ **Aprobado** |
| **CP-05** | **Diagramas de Flujo SVG** | Ambos diagramas deben ser legibles, seguir la lógica y resaltar el camino seleccionado mediante el panel interactivo. | ✅ Pasa | ✅ **Aprobado** |
| **CP-06** | **Accesibilidad y Foco** | Los botones de selección y cambio de tema deben mostrar contorno de foco visible (`:focus-visible`) al navegar con teclado. | ⚠️ Observación *(Sin foco claro)* | ✅ **Aprobado** |

### 2. Devolución al Equipo de Desarrollo (Reporte de Defectos)

* **Ticket QA-01 (Sentencia 2 R4 incompleta):** Se reportó que en `index.html` la sentencia R4 finalizaba prematuramente. Se solicitó restituir la oración original: *"La alternativa por edad se exige junto con todas las verificaciones anteriores."*
* **Ticket QA-02 (Casos límite en desplegables):** Se solicitó incorporar a los `<details>` la derivación a soporte al cliente por reclamos de tutores (Flujo 1) y la intervención de moderador humano ante fallas de GPS/trayecto (Flujo 2), alineando la entrega con el nivel *Propone* de la Rúbrica 04.
* **Ticket QA-03 (Foco accesible en CSS):** Se solicitó añadir en `styles.css` reglas `:focus-visible` para `.theme-btn`, `.seg-btn`, `summary` y enlaces del pie de página, garantizando estándares WCAG de accesibilidad por teclado.

### 3. Verificación Final (Re-test)

Tras la intervención del agente sobre el código:
* Se comprobó la apertura y cierre de ambos desplegables con teclado (`Tab` / `Espacio`), verificando la presencia íntegra de las fichas con sus excepciones humanas.
* Se validó que el foco visual ahora resalta claramente cada control interactivo al tabular.
* Se recorrieron los flujos de autorización comprobando que cubren tanto los casos afirmativos como los negativos.
* **Dictamen de QA:** La versión final cumple satisfactoriamente con la totalidad de los criterios de la rúbrica oficial en nivel **Propone**.
