# Proyecto Metodología: Migración de Java Swing a Web Accesible

Repositorio del proyecto de gestión ágil trabajado con Scrum y Kanban a partir de la planificación en [Scrumdidactica.xlsx](./Scrumdidactica.xlsx).

- Tablero del proyecto en GitHub: https://github.com/users/jhonnytrivino99/projects/1
- Repositorio grupal base: https://github.com/dpperez4-hue/ProyectoMetodologia
- Documentación por unidad: [ACD-Eventos](./ACD-Eventos) | [ACD-Roles](./ACD-Roles)

---

## ACD - Eventos

### Problema y solución técnica

La aplicación actual usa una interfaz de escritorio en Java Swing que no cumple con criterios básicos de accesibilidad web ni responde bien fuera de escritorio. El objetivo del proyecto es migrar esa interfaz a una aplicación web accesible manteniendo la lógica en Java y respetando un límite total de 27 días calendario.

Para elegir la tecnología se evaluaron cuatro alternativas sobre tres criterios (accesibilidad web, usabilidad y compatibilidad con Java) dentro del plazo disponible:

| Opción evaluada | Accesibilidad Web | Usabilidad | Funcionalidad Java | Tiempo (27d) | Puntaje | Decisión |
|---|---:|---:|---:|---:|---:|---|
| Vaadin Flow (Web en Java + ARIA) | 95 | 92 | 95 | 92 | 93.5 | Elegida |
| React + TypeScript + API Java | 88 | 95 | 85 | 65 | 83.25 | Descartada (excede 27 días) |
| JavaFX (Escritorio) | 40 | 70 | 90 | 80 | 70.0 | Descartada (no es web) |
| Java Swing (Actual) | 20 | 35 | 95 | 100 | 62.5 | Se reemplaza |

Se eligió Vaadin Flow porque permite generar vistas HTML5 con etiquetas WAI-ARIA sin reescribir toda la lógica del servidor Java. Los tres pilares trabajados en la migración son:

1. Accesibilidad: contraste mínimo de 4.5:1, navegación por teclado (Tab/Enter), atributos ARIA y pruebas con NVDA.
2. Usabilidad: pantallas claras, responsivas y con mensajes comprensibles para el usuario final.
3. Funcionalidad: migración completa de formularios, botones, menús, tablas (JTable) y validaciones en Java.

### Ciclo de vida del software

El trabajo cubre las siete fases del ciclo de vida del software distribuidas entre los cuatro Sprints:

| Fase del ciclo de vida | Sprint y días | Dueño (Gema Maizapanta) | Scrum Master (Jhonny Andy) | Product Owner (Genesis Vera) | Jefe Inmediato (Derlys Perez) | Grupo de Trabajo (Alejandro Pindo) |
|---|---|---|---|---|---|---|
| 1. Planificación | Sprint 1 (D1-D2) | Aprueba idea y plazo de 27 días | Organiza Scrum y Daily | Define meta A.Web | Aprueba recursos | Revisa sistema Swing |
| 2. Análisis e investigación | Sprint 1 (D3-D4) | Aprueba el nuevo diseño | Facilita reunión de decisión | Arma Backlog y requisitos | Valida opción técnica | Investiga Vaadin vs. otros |
| 3. Diseño UI/UX accesible | Sprint 2 (D5-D9) | Revisa bocetos visuales | Controla límite de 5 días | Valida usabilidad y ARIA | Aprueba arquitectura | Diseña pantallas y estilos |
| 4. Desarrollo (migración) | Sprint 3 (D10-D17) | Revisa avances puntuales | Quita bloqueos en Daily (8d) | Aclara dudas funcionales | Revisa código Java | Programa vistas en Vaadin |
| 5. Pruebas (QA y A.Web) | Sprint 4 (D18-D22) | Prueba como usuario (UAT) | Vigila solución de bugs | Verifica criterios A.Web | Lidera pruebas QA | Corrige fallos y ARIA |
| 6. Despliegue | Sprint 4 (D23-D25) | Autoriza paso a producción | Coordina entrega a tiempo | Entrega guía de uso | Supervisa servidor | Sube sistema al servidor |
| 7. Mantenimiento y cierre | Sprint 4 (D26-D27) | Firma entrega conforme | Dirige cierre y retrospectiva | Cierra Product Backlog | Define soporte futuro | Documenta y da soporte |

### Roles de Scrum en el proyecto

| N° | Integrante | Usuario GitHub | Rol | Participación principal |
|---|---|---|---|---|
| 1 | Gema Maizapanta | `@Gema619` | Dueño | Define el problema, aprueba el cambio a Web, valida prototipos, ejecuta UAT y firma el cierre. |
| 2 | Jhonny Jonathan Andy Triviño | `@jhonnytrivino99` | Scrum Master | Dirige los 27 Daily Scrums de 15 minutos, controla plazos (4d, 5d, 8d, 10d) y quita bloqueos. |
| 3 | Genesis Vera | `@gcvera1-dot` | Product Owner | Crea y prioriza el Backlog verificando accesibilidad, usabilidad y funcionalidad. |
| 4 | Derlys Perez | `@dpperez4-hue` | Jefe Inmediato | Supervisa al equipo, aprueba Vaadin Flow, revisa calidad QA y autoriza producción. |
| 5 | Alejandro Pindo | `@japindo-arch` | Grupo de Trabajo | Investiga opciones, diseña la UI accesible, programa la migración y corrige errores. |

### Eventos Scrum y cronograma de actividades

Durante los 27 días se realizaron reuniones de Sprint Planning al inicio de cada iteración, 27 Daily Scrums diarios de 15 minutos dirigidos por Jhonny Andy, sesiones de Sprint Review para validar las pantallas con NVDA/teclado y la retrospectiva final al cierre.

| Sprint | Rango | Días | Fases del ciclo de vida | Actividades principales | Equipo activo | Seguimiento |
|---|---|---|---|---|---|---|
| Sprint 1 | Días 1 al 4 | 4 | Planificación y Análisis | Definir alcance, equipo y límite de 27 días (T-01); evaluar alternativas y elegir Vaadin Flow (T-02). | Gema, Jhonny, Genesis, Derlys, Alejandro | 4 Daily Scrums (SM: Jhonny) |
| Sprint 2 | Días 5 al 9 | 5 | Diseño UI/UX accesible | Diseñar prototipos web, contraste >= 4.5:1, etiquetas ARIA y arquitectura Java (T-03). | Alejandro, Derlys, Genesis, Gema | 5 Daily Scrums (SM: Jhonny) |
| Sprint 3 | Días 10 al 17 | 8 | Desarrollo (Swing a Web) | Programar vistas en Vaadin Flow, migrar formularios, botones, menús (T-04), JTable y alertas (T-05). | Alejandro, Derlys, Genesis | 8 Daily Scrums (SM: Jhonny) |
| Sprint 4 | Días 18 al 27 | 10 | Pruebas, Despliegue y Cierre | Probar A.Web con NVDA y teclado (T-06), subir al servidor (T-07), entregar manual y acta (T-08). | Derlys, Gema, Jhonny, Alejandro, Genesis | 10 Daily Scrums (SM: Jhonny) |
| Total | 27 días | 27 | 7 fases completas | Migración completa de Java Swing a diseño web accesible | 5 integrantes | 27 Daily Scrums |

---

## ACD - Roles

### Carga de trabajo por rol en el ejercicio anterior

Al revisar el reparto de fases y tareas en Excel se nota que la carga técnica no quedó equilibrada entre los cinco integrantes:

| N° | Integrante | Usuario GitHub | Rol | Fases donde participa | Carga observada |
|---|---|---|---|---|---|
| 1 | Gema Maizapanta | `@Gema619` | Dueño | Planificación, Análisis, Diseño, Pruebas UAT, Despliegue y Cierre | Carga Baja |
| 2 | Jhonny Jonathan Andy Triviño | `@jhonnytrivino99` | Scrum Master | Todas las fases (control diario en los 27 Daily Scrums) | Carga Moderada |
| 3 | Genesis Vera | `@gcvera1-dot` | Product Owner | Todas las fases (Backlog, diseño ARIA, aclaraciones, pruebas y cierre) | Carga Moderada |
| 4 | Derlys Perez | `@dpperez4-hue` | Jefe Inmediato | Todas las fases (recursos, código Java, QA, servidor y soporte) | Sobrecarga Alta |
| 5 | Alejandro Pindo | `@japindo-arch` | Grupo de Trabajo | Todas las fases (investigación, diseño UI, código, correcciones y despliegue) | Sobrecarga Crítica |

Alejandro Pindo concentra 5 de las 8 tareas del Backlog (incluyendo T-04 en solitario) y toda la programación directa. Derlys Perez suma funciones administrativas con revisión de código y liderazgo de QA.

### Tareas en Scrum (T-01 a T-08)

| ID | Tarea | Responsables | Sprint y fase | Estado | Carga |
|---|---|---|---|---|---|
| T-01 | Definir alcance (Java Swing a Web Accesible), equipo y límite de 27 días | Gema Maizapanta / Jhonny Andy | Sprint 1 (4d) / Planificación | Hecho | Carga Baja |
| T-02 | Investigar opciones a Java Swing y elegir Vaadin Flow | Alejandro Pindo / Derlys Perez | Sprint 1 (4d) / Análisis | Hecho | Sobrecarga Alta |
| T-03 | Crear diseño web con contraste, teclado y etiquetas ARIA | Genesis Vera / Alejandro Pindo | Sprint 2 (5d) / Diseño Web Accesible | En proceso | Carga Moderada |
| T-04 | Migrar formularios, botones y menús de Swing a Web | Alejandro Pindo (en solitario) | Sprint 2-3 / Desarrollo | Pendiente | Sobrecarga Crítica |
| T-05 | Migrar tablas (JTable) y alertas manteniendo lógica Java | Alejandro Pindo / Derlys Perez | Sprint 3 (8d) / Desarrollo | Pendiente | Sobrecarga Crítica |
| T-06 | Probar Accesibilidad (NVDA/teclado), Usabilidad y Funcionalidad | Derlys Perez / Genesis Vera / Gema Maizapanta | Sprint 4 (10d) / Pruebas QA/UAT | Pendiente | Sobrecarga Alta |
| T-07 | Subir aplicación web al servidor y capacitar al usuario | Alejandro Pindo / Derlys Perez | Sprint 4 (10d) / Despliegue | Pendiente | Sobrecarga Alta |
| T-08 | Entregar manual, acta de cierre y plan de soporte | Jhonny Andy / Gema Maizapanta | Sprint 4 (10d) / Cierre | Pendiente | Carga Moderada |

### Flujo continuo en Kanban (K-01 a K-06)

Para evitar el cuello de botella detectado en Scrum, el tablero Kanban aplica límites WIP en las columnas activas (`Backlog`, `Por Hacer (WIP: 3)`, `En Progreso (WIP: 2)`, `Revisión / QA (WIP: 2)` y `Hecho (Entregado)`):

| ID | Actividad Kanban | Responsables | Columna | Carga |
|---|---|---|---|---|
| K-01 | Redefinir métricas de flujo, Lead Time y políticas explícitas Pull | Jhonny Andy / Gema Maizapanta | Hecho (Entregado) | Carga Baja |
| K-02 | Refinar y priorizar cola de migración UI y pilares Web Accesible | Genesis Vera / Gema Maizapanta | Por Hacer (WIP: 3) | Carga Moderada |
| K-03 | Migrar formularios, menús y componentes Vaadin en pares | Alejandro Pindo / Derlys Perez | En Progreso (WIP: 2) | Carga Moderada |
| K-04 | Migrar tablas JTable y lógica de alertas Java con revisión continua | Derlys Perez / Alejandro Pindo | En Progreso (WIP: 2) | Carga Moderada |
| K-05 | Auditoría continua de Accesibilidad (ARIA/NVDA) y Usabilidad Web | Genesis Vera / Gema Maizapanta | Revisión / QA (WIP: 2) | Carga Moderada |
| K-06 | Automatizar despliegue al servidor, manual operativo y cierre continuo | Jhonny Andy / Alejandro Pindo | Backlog | Carga Baja |

### Vistas en GitHub Projects

1. `Scrum - Tablero`: tablero agrupado por estado (`Pendiente`, `En proceso`, `Hecho`) con las tareas T-01 a T-08.
2. `ACD - Roles (Tabla)`: tabla general con las 14 actividades, responsables asignados y niveles de carga.
3. `Kanban - Flujo Continuo`: tablero Kanban con límites WIP y tarjetas K-01 a K-06.
