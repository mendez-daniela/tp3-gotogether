# GoTogether · Dos sentencias, dos soluciones

Trabajo práctico 3 de Desarrollo de Sistemas Web (Front End), IFTS 29. Segundo cuatrimestre de 2026.

**Grupo 20 · Hallows Code**  
**Startup asignada:** GoTogether, creada por estudiantes del IFTS 16.  
**Bloque:** Autorización (S09-B).

GoTogether propone coordinar viajes en transporte público entre fans del K-pop. La landing presenta dos decisiones del recorrido de una persona que quiere sumarse a un grupo de viaje. Cada diagrama permite elegir un escenario, seguir la rama correspondiente y consultar la explicación del flujo.

## Cómo ver el proyecto

- [Repositorio del grupo en GitHub](https://github.com/mendez-daniela/tp3-gotogether)
- [Landing de GoTogether publicada en Vercel](https://tp3-gotogether.vercel.app/)

## Cómo ejecutar y comprobar

La landing es HTML, CSS y JavaScript, sin dependencias ni paso de compilación.

1. Descargar o clonar el repositorio.
2. Abrir `index.html` en el navegador de una computadora.
3. Probar los botones de cada diagrama y los desplegables, con clic y con teclado (`Tab`, `Enter` y `Espacio`).

Antes de entregar se comprueba, desde una ventana sin sesión, que el repositorio y la landing abren y que el sitio muestra la versión final.

## Las dos soluciones propuestas

| Regla | Qué haría el agente | Ejemplo para recorrer en la landing |
| --- | --- | --- |
| R3 · Incorporación al grupo | Consultaría la edad y, si la persona es menor, buscaría la autorización de su tutor. Si falta el permiso, mantendría bloqueada la incorporación e indicaría que debe presentarlo. | Compará los recorridos de un menor con autorización y de otro sin ella. Solo el primero puede avanzar. |
| R4 · Confirmación personal | Comprobaría que el trayecto, la identidad y la edad estén verificados. Con esas tres verificaciones completas, habilitaría la confirmación personal a mayores de edad y a menores con autorización. | Una persona adulta con el trayecto sin verificar queda detenida. Con las tres verificaciones completas, puede pasar a confirmar el viaje. |

### Qué define cada sentencia y qué agrega el grupo

En los diagramas, los bordes y las flechas punteados marcan lo que agrega el grupo.

| Regla | Lo que define la sentencia | Lo que agrega el grupo |
| --- | --- | --- |
| R3 · Incorporación al grupo | Si el usuario es menor de edad y no consta autorización de su tutor, se mantiene bloqueada su incorporación. | Permitir avanzar en los demás casos. Mensaje que indica cómo subir el permiso. Revisión humana con soporte cuando el tutor reclama haber autorizado. |
| R4 · Confirmación personal | Con trayecto, identidad y edad verificados, y con mayoría de edad o autorización del tutor, se habilita la confirmación personal. | Detener el proceso y solicitar revisión de datos si falta una verificación. Detener el paso de confirmación para una persona menor sin autorización. Revisión humana de un moderador ante fallas de GPS o datos que no coinciden. |

## Integrantes y aportes

Todas las personas del equipo trabajaron como operadoras agénticas: cada una dirigió a un agente de IA sobre una parte del trabajo, y el rol indica cuál.

| Integrante | Rol | Tarea asignada |
| --- | --- | --- |
| [Sol Prinzen](https://github.com/solprinz) | Operadora agéntica de lógica y análisis técnico | Desglosar R3 y R4 en dos fichas con los datos de entrada, las condiciones, las consecuencias y una explicación de cada regla. |
| [Lucas Eliel Sosa](https://github.com/Strashoy) | Operador agéntico de diagramas e interacción | Convertir las fichas de Sol en dos diagramas de flujo interactivos, con pasos, flechas, un selector de escenarios y una excepción por flujo que indica cuándo corresponde la intervención humana. |
| [Daniela Méndez](https://github.com/mendez-daniela) | Operadora agéntica de código y desarrollo front end | Usar los textos de Sol y los diagramas de Lucas para guiar al agente de programación por etapas, subir el código a GitHub y publicar la landing. |
| [Juan Pablo](https://github.com/JPFinal) | Operador agéntico de testing | Auditoría de interfaz en versión Desktop, prueba de navegación/desplegables con teclado/clic y reporte de iteraciones y mejoras de QA. ([Ver informe de auditoría ↓](#auditoria-qa)) |
| [Alejandro Ramos](https://github.com/AleR25) | Operador agéntico de documentación | Redactar el README, registrar los aportes y las herramientas de IA del equipo y documentar una iteración con el pedido de mejora y su resultado. |

## Construcción con IA

| Integrante | Aplicación | Modelo | Uso en el TP3 | Cambios solicitados |
| --- | --- | --- | --- | --- |
| Lucas Eliel Sosa | Claude Code (aplicación de escritorio de Claude) | Claude Sonnet 5.5 | Uso de las fichas de Sol y del trabajo previo como contexto. Escritura directa de los dos diagramas de flujo como SVG, sin herramientas de modelado ni conectores externos. Paleta de colores derivada del logo de la startup. Componente interactivo con selector de escenarios, en lugar de un dibujo fijo para replicar. Exportación a SVG y PNG para documentos. Ajustes de la landing según la rúbrica: logo legible, bloque asignado, decisiones del grupo, revisión humana en los diagramas y navegación. | Plan de colores a partir del logo; exploración de seis formatos para exponer la lógica y elección del diagrama de flujo; selector de escenarios con resaltado del recorrido; SVG y PNG en modo claro; páginas que abren en modo claro; logo grande al inicio de la página; bloque asignado visible; nodo de revisión humana y marcas de decisión del grupo en los dos diagramas; índice de secciones. |
| Alejandro Ramos | Codex | GPT-6 Astra | Revisión del README según la consigna y organización de los estilos de la landing. | Ajustar el formato del README, corregir inconsistencias y separar los estilos de `index.html` en `styles.css`. |
| Daniela Méndez | Pendiente de confirmar | DeepSeek-V4.1-Flash-1017 | Construcción de la landing por etapas a partir de las fichas y los diagramas. Actualización del código a partir del informe de QA. Publicación en GitHub y Vercel. | Primera versión de la landing con diagramas interactivos y desplegables. Restitución de la frase final de R4 («La alternativa por edad se exige junto con todas las verificaciones anteriores.») y casos límite con intervención humana en los desplegables, a partir del informe de QA. |
| Juan Pablo | Antigravity | Gemini 3.8 Flash | Auditoría de calidad de interfaz en Desktop, diseño de matriz de pruebas, validación de accesibilidad por teclado y verificación de coherencia lógica contra la rúbrica. | Reportar e integrar casos límite de intervención humana en desplegables, restaurar texto completo de R4 y añadir estilos de foco accesible (`:focus-visible`). |
| Sol Prinzen | Gemini (Google AI Plus) | Gemini 2.5 Pro | Organización y división de roles del equipo, desglose lógico de las sentencias R3 y R4, redacción de fichas técnicas y modelado de flujos en texto. | Organizar la división de tareas del equipo en 5 roles claros y desglosar los flujos de decisión pregunta por pregunta (en cascada) para facilitar el diseño de los diagramas. |

### Una iteración de la landing

En la primera versión de la landing, le pedimos al agente que representara las condiciones necesarias para habilitar la confirmación personal del viaje. Al revisar el diagrama, observamos que todas las ramas tenían el mismo peso visual. Esto dificultaba seguir el recorrido de una persona menor de edad con autorización de su tutor y podía dar a entender que el permiso era suficiente para pasar a la confirmación.

Para mejorar la lectura, se incorporó a la landing el selector de escenarios diseñado en la etapa de diagramas (ver «Del diagrama estático al componente interactivo»). En la versión actual, al elegir «Menor con autorización», el diagrama resalta el camino correspondiente y atenúa las demás ramas. Así se aprecia el orden de los controles. Primero se comprueba que el trayecto, la identidad y la edad estén verificados. Luego, al tratarse de una persona menor de edad, se consulta la autorización del tutor. Si consta el permiso, se habilita el paso de confirmación personal.

### Separación de los estilos de la landing

La primera versión reunía en `index.html` el contenido de la página y las reglas de diseño. Además, varios elementos de los diagramas repetían los mismos estilos. Alejandro le pidió a Codex que trasladara esas reglas a una hoja de estilos compartida. Ahora ambos diagramas usan [styles.css](styles.css), donde se pueden ajustar los colores, las líneas y las etiquetas desde un solo lugar.

Probamos la versión local en Microsoft Edge. Comprobamos que la página cargaba la hoja de estilos, que el botón activaba el tema oscuro y que, en ambos diagramas, seleccionar «Menor con autorización» resaltaba el recorrido correspondiente.

### Iteración colaborativa a partir del control de QA

Durante la revisión de calidad en computadora (Desktop) sobre la versión publicada, el operador agéntico de testing (Juan Pablo) auditó la interfaz, los flujos interactivos y los desplegables contra la rúbrica oficial. Se detectaron tres aspectos a mejorar:
1. La sentencia original R4 estaba incompleta (faltaba la frase condicionante final).
2. Los desplegables técnicos omitían los casos de excepción y derivación a intervención humana.
3. Los botones de selección de caminos carecían de indicador de foco visible al navegar exclusivamente con teclado.

Juan Pablo elevó estas observaciones en un reporte formal a Daniela Méndez (operadora agéntica de código y desarrollo front end). Se instruyó al agente a actualizar `index.html` y `styles.css`, subsanando los puntos observados. Posteriormente, Juan Pablo realizó una re-evaluación verificando el cierre satisfactorio de todos los casos de prueba.

### Del diagrama estático al componente interactivo

**Instrucción inicial.** A partir de las fichas de Sol y del trabajo previo del grupo, se pidió un diagrama de flujo por cada regla, con los colores de la startup.

**Problema detectado.** Un diagrama fijo debe ser redibujado por quien arma la landing, y todas las ramas se leen con el mismo peso visual.

**Pedido de mejora.** Un componente que se dibuje una sola vez y permita elegir un escenario para resaltar su recorrido.

**Qué cambió y por qué.** Los diagramas se escribieron directamente como SVG, sin herramientas de modelado ni conectores externos. Cada elemento (decisiones, flechas, etiquetas y resultados) lleva un atributo que indica a qué escenarios pertenece. Al elegir un escenario, una regla de estilos atenúa lo que no corresponde y un texto enumera los pasos. No se generan gráficos nuevos: se activan y se atenúan piezas del mismo dibujo. De este modo, el mismo SVG se incorpora a la landing sin redibujarlo y el recorrido se lee de un vistazo.

**Comprobación.** Se definieron los recorridos de prueba de cada flujo: tres casos para el flujo 1 y cuatro para el flujo 2, cada uno con su resultado esperado. Los diagramas se entregaron en SVG y en PNG, con una versión de la página que abre en modo claro. Luego se ajustó la landing a la rúbrica: se agrandó el logo, se mostró el bloque asignado, se dibujó la revisión humana en cada flujo y se marcó con líneas punteadas lo que agrega el grupo. Se probó en un navegador de escritorio que los botones de escenario resaltan el recorrido y actualizan los pasos, sin errores de JavaScript.

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
