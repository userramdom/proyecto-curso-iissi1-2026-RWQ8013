# Título Proyecto

## Miembros del grupo L5-5

1. ROMERO OCAÑA, LAURA
1. MUNOZ MÉRIDA, INÉs
1. SANTAMARÍA PÉREZ, CLAUDIA
1. VICENTE JEREZ, BEATRIZ

## 1. Introducción al problema

El sector de los festivales de música ha experimentado un crecimiento exponencial en los últimos años, concentrando a miles de personas en recintos delimitados durante varios días. Al tener una gran demanda, muchos de los usuarios pueden experimentar problemas de logística y masificación. Por otro lado, los organizadores enfrentan grandes retos para gestionar eficientemente la seguridad y el personal en tiempo real. 

En este tipo de eventos podemos encontrar asistentes al festival que suelen ser jóvenes de entre 18 y 35 años, además de los patrocinadores, promotores y artistas que participan en el festival.

Actualmente nos enfrentamos a problemas como la falta de información en tiempo real, como los horarios y las zonas dentro del recinto, la descentralización de la información sobre el evento o largas colas en los accesos por una mala verificación de los asistentes. 
El objetivo de este proyecto es diseñar e implementar una base de datos que unifique toda la información del evento de forma organizada facilitando su acceso para aquellos que los necesiten, según el rol del usuario.

## 2. Glosario de términos

- Check-In: Proceso mediante el cual se escanea y valida la entrada de los asistentes en las entradas al recinto, autorizando su ingreso al festival y actualizando su estado como "presente". Si algún usuario intenta entrar en alguna zona que su tipo de entrada no autoriza dará error.
- Autenticación: Proceso mediante el cual cada usuario inicia sesión en la interfaz para que el sistema verifique su identidad y le otorgue los permisos asociados a su rol.
- Transacción cashless: Proceso de cobro mediante el escaneo de la pulsera/QR del asistente en el punto de venta. Al realizar una comprao o recarga se suma o resta del saldo asociado a su cuenta.
- Frontend: Parte del sistema correspondiente a la interfaz gráfica con la que interactúan los usuarios.
- Dashboard: Panel de control con toda la información sobre el festival en tiempo real al cual tienen acceso los organizadores del evento.

## 3. Visión general del sistema

### 3.1. Requisitos generales

### 3.2. Usuarios del sistema

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Título requisito funcional

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- Se debe aplicar la regla de negocio R.N.XX.
- ...

#### 4.1.1. Requisitos de información

##### R.I.01. Título requisito de información

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- ...

#### 4.1.2. Reglas de negocio

##### R.N.01. Título regla negocio

Descripción de la regla de negocio.

### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Título requisito no funcional**
Como [tipo de usuario]
quiero [servicio]
para [razón]

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

- con restricciones.

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

-- fin entregable 2 --

## 7. Modelo relacional en 3FN

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.

### 7.1.  Justificación de la estrategia de transformación de jerarquías

- si se identificaron jerarquías en el MC.


### 8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)
- Incluir Reglas de negocio — Constraints/Triggers en las matrices de trazabilidad para el entregable 3

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:-------|:-------|:-------|:-------|:-------|
| TABLA-1 |        |        |        |        |
| TABLA-2 |        |        |        |        |
| TABLA-3 |        |        |        |        |
| TABLA-4 |        |        |        |        |
| TRIG-1 |        |        |        |        |
| TRIG-2 | X      | X      |        | X      |
| TRIG-3 |        | X      |        | X      |
| TRIG-4 |        |        | X      |        |
| CONST-1 |        |        |        |        |
| CONST-2 | X      | X      |        | X      |
| CONST-3 |        | X      |        | X      |
| CONST-4 |        |        | X      |        |

Se consideran todo tipo de constraints declarativas (aquellas definidas durante el CREATE TABLE).
-- fin entregable 3 --

## Referencias


