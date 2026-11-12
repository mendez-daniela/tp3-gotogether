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
| [Juan Pablo](https://github.com/JPFinal) | Pruebas de calidad (QA) | Recorrer la landing publicada desde una computadora, probar los desplegables y verificar que ambos diagramas se puedan leer y seguir. |
| [Alejandro Ramos](https://github.com/AleR25) | Documentación | Redactar el README, registrar los aportes y las herramientas de IA del equipo y documentar una iteración con el pedido de mejora y su resultado. |

## Construcción con IA

| Integrante | Aplicación | Modelo | Uso en el TP3 | Cambios solicitados |
| --- | --- | --- | --- | --- |
| Alejandro Ramos | Codex | GPT-6 Astra | Revisión del README según la consigna y organización de los estilos de la landing. | Ajustar el formato del README, corregir inconsistencias y separar los estilos de `index.html` en `styles.css`. |
| Daniela Méndez | Pendiente de confirmar | DeepSeek-V4.1-Flash-1017 | Construcción de la landing por etapas a partir de las fichas y los diagramas. | [Registrar una corrección solicitada durante el desarrollo.] |

### Una iteración de la landing

En la primera versión de la landing, le pedimos al agente que representara las condiciones necesarias para habilitar la confirmación personal del viaje. Al revisar el diagrama, observamos que todas las ramas tenían el mismo peso visual. Esto dificultaba seguir el recorrido de una persona menor de edad con autorización de su tutor y podía dar a entender que el permiso era suficiente para pasar a la confirmación.

Para mejorar la lectura, le pedimos al agente que incorporara un selector de escenarios. En la versión actual, al elegir «Menor con autorización», el diagrama resalta el camino correspondiente y atenúa las demás ramas. Así se aprecia el orden de los controles. Primero se comprueba que el trayecto, la identidad y la edad estén verificados. Luego, al tratarse de una persona menor de edad, se consulta la autorización del tutor. Si consta el permiso, se habilita el paso de confirmación personal.

### Separación de los estilos de la landing

La primera versión reunía en `index.html` el contenido de la página y las reglas de diseño. Además, varios elementos de los diagramas repetían los mismos estilos. Alejandro le pidió a Codex que trasladara esas reglas a una hoja de estilos compartida. Ahora ambos diagramas usan [styles.css](styles.css), donde se pueden ajustar los colores, las líneas y las etiquetas desde un solo lugar.

Probamos la versión local en Microsoft Edge. Comprobamos que la página cargaba la hoja de estilos, que el botón activaba el tema oscuro y que, en ambos diagramas, seleccionar «Menor con autorización» resaltaba el recorrido correspondiente.
