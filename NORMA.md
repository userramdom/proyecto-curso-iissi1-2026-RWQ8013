# Norma del Proyecto de IISSI-1

## Índice

1. Objetivos
2. Entregables
3. Norma del proyecto
4. Criterios de evaluación

---

## Objetivos

- Asentar los conocimientos teóricos explicados en clase mediante su aplicación en el desarrollo parcial de un sistema de información.
- Practicar el trabajo en grupo mediante el desarrollo del proyecto en grupos de entre 3 y 5 alumnos.
- Practicar la recopilación de información sobre un dominio de problema dado.

---

## Entregables

### Primer entregable

Incluye:

1. Introducción al problema:
   - Descripción del problema para poner en contexto el proyecto, incluyendo información sobre los clientes y usuarios, la situación actual, problemas, expectativas, etc. Se valorará la presencia de información multimedia (fotos, gráficos, documentos escaneados, etc.).
2. Glosario de términos:
   - Términos específicos del dominio del problema, ordenados alfabéticamente. Se valorará la presencia de información multimedia.
3. Visión general del sistema:
   - Requisitos generales
   - Usuarios del sistema
4. Catálogo de requisitos:
   - Mapa de historias de usuario (opcional)
   - Requisitos de información
   - Reglas de negocio
   - Requisitos funcionales (solo listados y consultas)
   - Requisitos no funcionales (opcional)
   - Pruebas de aceptación de reglas de negocio

**Fecha de entrega:** 16/10/2025 23:59

---

### Segundo entregable

Incluye el contenido del primer entregable mejorado, añadiendo:

5. Modelo conceptual:
   - Diagramas de clases UML con restricciones.
   - Escenarios de prueba con descripción textual y diagrama de objetos UML.
6. Matrices de trazabilidad:
   - Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos de información y reglas de negocio.

**Fecha de entrega:** 6/11/2025 23:59

---

### Tercer entregable

Incluye el contenido del primer y segundo entregables mejorado, añadiendo:

7. Modelo relacional en 3FN:

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.
- Justificación de la estrategia de transformación de jerarquías (si se identificaron jerarquías en el MC).

8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)

9. Scripts:

- Scripts de creación de tablas y restricciones. (1.scripts_tablas_restricciones.sql)
- Scripts de creación de funciones y procedimientos. (2.scripts_funciones_procedimientos.sql)
- Scripts de cursores y listados de consultas. (3.scripts_cursores_consultas.sql)
- Script de creación de triggers. (4.scripts_triggers.sql)
- Script de inserción de datos de prueba. (5.script_poblado_tablas.sql)

**Fecha de entrega:** 15/12/2025 23:59

## Norma del Proyecto

- La documentación del proyecto debe redactarse con formato Markdown en el archivo README.md de su repositorio seguiendo la plantilla proporcionada en el propio archivo:
  - Portada con:
    - Título del trabajo
    - Apellidos y nombres de los miembros del grupo
  - Las secciones especificadas en este documento
  - Sección de referencias y bibliografía consultada en su caso
- El código del proyecto debe funcionar en un servidor de bases de datos MariaDB.
- La gestión del proyecto se realizará a través de GitHub.
- Se evaluará el último commit realizado al repositorio remoto antes de cada fecha/hora de entrega.

## Revisiones y defensa del proyecto

- Los entregables 1 y 2 serán revisados por el tutor del proyecto.
- El grupo completo debe asistir a la revisión de entregables (salvo causa debidamente justificada).
- El entregable 3 deberá ser defendido por el grupo frente a las preguntas del tutor, quien podrá realizar cuestiones de manera individual para determinar la autoría y calificación.

---

## Criterios de evaluación

- Para la calificación de cada entregable se tendrá en cuenta tanto la calidad alcanzada como la complejidad del sistema de información desarrollado.
- Es obligatorio que el código SQL se ejecute correctamente.
- Durante la defensa, se valorará la autoría y participación de cada miembro del grupo, pudiendo establecerse calificaciones diferentes si se observaran diferencias significativas.
- Durante la defensa se podrán solicitar cambios en el código fuente para comprobar las capacidades de cada miembro del grupo.
