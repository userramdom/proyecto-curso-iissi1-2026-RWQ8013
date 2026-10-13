# Sistema de gestión de festivales de música

## Miembros del grupo L5-5

1. ROMERO OCAÑA, LAURA
2. MUNOZ MÉRIDA, INÉS
3. SANTAMARÍA PÉREZ, CLAUDIA
4. VICENTE JEREZ, BEATRIZ

## 1. Introducción al problema

El sector de los festivales de música ha experimentado un crecimiento exponencial en los últimos años, concentrando a miles de personas en recintos delimitados durante varios días. Al tener una gran demanda, muchos de los usuarios pueden experimentar problemas de organizacion y masificación. Por otro lado, los organizadores enfrentan grandes retos para gestionar eficientemente una gran cantidad de elementos (artistas, patrocinadores, asistentes, seguridad, etc) en tiempo real. 

En este tipo de eventos podemos identificar diferentes perfiles de usuarios. Por un lado, se encuentran los asistentes al festival, que suelen ser principalmente jóvenes de entre 18 y 35 años interesados en la música y en disfrutar de este tipo de experiencias. Por otro lado, participan los promotores, que se encargan de organizar y coordinar el evento; los patrocinadores, que contribuyen a su financiación y promoción; y los artistas, que ofrecen las actuaciones musicales. Cada uno de estos perfiles tiene necesidades diferentes, por lo que es importante tenerlos en cuenta a la hora de diseñar el sistema de gestión delfestival.

Actualmente nos enfrentamos a problemas como la falta de información en tiempo real (como los horarios y las zonas dentro del recinto), la descentralización de la información sobre el evento o largas colas en los accesos por una mala verificación de los asistentes. 

El objetivo de este proyecto es diseñar e implementar una base de datos que unifique toda la información del evento de forma organizada facilitando su acceso para aquellos que los necesiten, según el rol del usuario. De esta forma, por un lado los asistentes podran acceder a informacion a tiempo real, consultar entradas, horarios, etc; y los promotores podran usarla en forma de ayuda para organizar y administrar los eventos comprobando en tiempo real el aforo, la disponiviledad de los recintos, etc.

## 2. Glosario de términos

- Check-In: Proceso mediante el cual se escanea y valida la entrada de los asistentes en las entradas al recinto, autorizando su ingreso al festival y actualizando su estado como "presente". Si algún usuario intenta entrar en alguna zona que su tipo de entrada no autoriza dará error.
- Autentificación: Proceso mediante el cual cada usuario inicia sesión en la interfaz para que el sistema verifique su identidad y le otorgue los permisos asociados a su rol.
- Transacción cashless: Proceso de cobro mediante el escaneo de la pulsera/QR del asistente en el punto de venta. Al realizar una comprao o recarga se suma o resta del saldo asociado a su cuenta.
- Frontend: Parte del sistema correspondiente a la interfaz gráfica con la que interactúan los usuarios.
- Dashboard: Panel de control con toda la información sobre el festival en tiempo real al cual tienen acceso los organizadores del evento.

## 3. Visión general del sistema

### 3.1. Requisitos generales

#### R.G.01. Gestión centralizada de los eventos y su programación
Como promotor del festival, quiero gestionar desde una única plataforma toda la información relacionada con los escenarios, los artistas, 
los horarios de las actuaciones y las diferentes zonas del recinto, para mantener todos los datos organizados y actualizados. 
De esta forma, podré coordinar mejor la programacióndel festival, realizar cambios cuando seanecesario 
y evitar errores y confusiones durante la planificación y el desarrollo del evento.
#### R.G.02. Agilización del acceso (check-in)
Como personal de control y accesos,
quiero disponer de un sistema de lectura y validación rápida de entradas y credenciales,
para reducir las colas en la enrada del recinto y agilizar el flujo de asistenetes.

#### R.G.03. Consulta de horarios y mapa en tiempo real
Como asistente al festival,
quiero consultar los horarios actualizados y localización de los escenarios,
para organizar mi itinerario sin perderme ninguna actuación.

#### R.G.04. Gestión de saldo y pagos cashless
Como asistente al festival, quiero poder recargar saldo digital en mi perfil y realizar pagos mediante el escaneo de mi credencial o pulsera, para comprar comida, bebida y otros productos de forma rápida, sencilla y segura.
Además, quiero poder consultar en todo momento el saldo disponible y los movimientos realizados para llevar un control de mis gastos durante el evento. De esta manera, podré reducir el tiempo de espera en los puntos de venta, evitar el uso de dinero en efectivo y disfrutar del festival con mayor comodidad,sin tener que preocuparme constantemente por llevar dinero encima.

#### R.G.05. Monitorización de aforo e incidencias en timepo real
Como promotor del festival,
quiero visualizar datos del aforo del recinto en tiempo real y las ventas por zona,
para garantizar la seguridad, evitar saturaciones y tomar decisiones operativas durante el evento.

### 3.2. Usuarios del sistema

### PROMOTOR DE LOS FESTIVALES
Gestionar el recinto del festival, aforo, patrocinadores, organización de los escenarios, cantidad de artistas que asistiran al festival.

### ASISTENTES DE LOS FESTIVALES
Comprobar localizacion de cada concierto, metodos de pagos dentro del recinto, horarios de los conciertos, localizacion de las entradas al recinto. 

### PERSONAL DE CONTROL Y ACCESO 
Gestionar las entradas de los asistentes, control de las entradas/salidas del recinto. 

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Registro de los asistentes

Como promotor de los festivales quiero que los asistentes se puedan registrar con sus datos personales para complar sus entradas y tener un contro de quien accede al festival.

**Prueba de aceptación**
- Dos usuarios no pueden registrase con el mismo correo electrónico, ni se pueden llamar de la misma forma (nombres y apellidos iguales) y tampoco pueden tener la misma documentación. 
- Los asistentesdeben ser mayores de edad (18 años o mas).
- Se debe aplicar la regla de negocio R.N.XX.


#### R.F.01. Organizacion del festival

Como promotor de los festivales quiero organizar los distintos recintos alrededor de españa, a los artistas y patrocinadores que participaran en dicho evento y las distintas zonas de escenario que habra en el festival para tener el control de la asistencia de los artistas en cada festival ademas de los afroros en cada recinto y localizacion de los conciertos.

**Prueba de aceptación**
- Un artistas no pueden estar en mas de un escenario a la misma hora, ni durante la duracion del conciento a dicha hora. Además de que no podria estar el mismo dia en dos festivales de diferentes localizaciones. 
- Los asistentes al concierto no pueden superar el aforo del recinto.
- Se debe aplicar la regla de negocio ...
  

#### R.F.01. Método de pago 
Como comercio dentro del festival y como asistente al mismo quiero metodos de pago fiables y rapidos para no perder dinero y agilizar la compra venta en el festival 

**Prueba de aceptación**
- Debe tener saldo suficiente para hacer la compra.

  

#### R.F.01. Control de entrada 
Como personal de control y acceso al festival quiero un metodo de identificacion rapido para garantoizar que el asistente tiene entrada y cumple los requisitos para entrar.

**Prueba de aceptación**
- Cuando pasa la entrada marca como "Entrada", una vez con eso la persona que entra no debe tener esa marca.
- Debe entrar por la zona correcta que marque su entrada
- Su informacion identificadora debe ser valida  


#### 4.1.1. Requisitos de información

##### R.I.01. Información sobre el festival 

Como asistente al festival 
quiero saber la siguente informacion sobre el festival: 

- Lugar del festival
  
- Los artistas que asistiran al evento
  
- Por donde debo entrar al evento
  
- Los horarios de cada actuación

- Donde se encuentran los aseos 

- Saber que alimentos y bebidas podré introducir al recinto 

- Las medidas de seguridad que se emplearan durante el evento

- Los precios que se ofertan dentro del recinto en referencia a la comida y o bebida.

- Los distintos escenarios que hay en el recinto 

- Los tiempos de espera de la cola de acceso

- El código de vestimenta que tiene el festival


##### R.I.02. Informacion sobre la disponibilidad para organizar el festival 

Como promotor del festival 
quiero saber la siguente información a la hora de organizar: 

- Aforo de los recintos disponibles para organizar los festivales.
  
- Los artistas disponibles.
  
- Entradas y seguridad necesaria en el recinto 
  
- Financiacion (patrocinadores) necesaria.

- Cantidad de escenarios necesarios dentro de cada recinto.

- Disponibilidad de servicios de restauración


##### R.I.03. Informacion sobre los asistentes a los festivales  

Tanto como promotor del evento que como personal de control y acceso quiero saber la siguiente informacion: 

- Informacion sobre la identidad de los asistentes (nombres y apellidos, correo, documentacion, etc)

- Control de todas las entradas/salidas de cada recinto 


##### R.I.04. Informacion sobre las entradas sus tipos y el acceso de cada una 

Como asistente al festival quiero poder consultar lo siguiente:

- Disponibilidad de entradas

- Zonas disponibles con cada entrada

- Precio de cada entrada 

Como promotor y como personal de control y acceso me gustaria saber:

- El estado de la entrada

-Identificacion de la entrada 

- Actualizacion periodica en tiempo reac de cuantas personas van entrando al evento.


##### R.I.05. Informacion sobre los pagos y comercios en el evento  

Como asistente al evento me gustaria saber:

- Saldo disponible

- Historial de recargas y operaciones realizadas 

- Verificacion de las transacciones 


  
#### 4.1.2. Reglas de negocio

##### R.N.01. Título regla negocio

Descripción de la regla de negocio.

### 4.2. Mapa de historias de usuario (opcional)
El mapa de historias de usuario organiza las necesidades del sistema por actividades principales, denominadas épicas. Cada historia identifica al usuario, la acción que necesita realizar y el objetivo que persigue. El sistema contempla la gestión de varios festivales, cada uno con su propia programación, recinto y asistentes.

### Organización del mapa

Las actividades se ordenan siguiendo el recorrido de cada tipo de usuario:

| Usuario | Preparación | Participación y operación | Seguimiento |
| --- | --- | --- | --- |
| Promotor de los festivales | Consultar recintos, organizar escenarios y programar actuaciones. | Consultar la programación y supervisar el aforo. | Consultar las ventas por zona. |
| Asistente a los festivales | Registrarse, consultar festivales y adquirir entradas. | Consultar horarios y escenarios, acceder al recinto y utilizar el saldo cashless. | Consultar el saldo y el historial de operaciones. |
| Personal de control y acceso | Consultar los datos y permisos de las entradas. | Validar entradas y registrar accesos y salidas. | Consultar los registros de entradas y salidas. |

### Épica 1. Organización de festivales y programación

Relacionada con R.G.01: Gestión centralizada de los eventos y su programación.

#### H.U.01. Consulta de recintos

Como promotor de los festivales, quiero consultar la ubicación, el aforo y la disponibilidad de los recintos, para seleccionar un espacio adecuado para cada festival.

#### H.U.02. Organización de escenarios

Como promotor de los festivales, quiero organizar los escenarios y las zonas del recinto de cada festival, para distribuir las actuaciones y mantener identificados los espacios del evento.

#### H.U.03. Programación de actuaciones

Como promotor de los festivales, quiero asignar los artistas a las actuaciones de cada festival e indicar su escenario y horario, para mantener una programación coordinada.

### Épica 2. Consulta de festivales y programación

Relacionada con R.G.03: Consulta de horarios y mapa en tiempo real.

#### H.U.04. Consulta de festivales

Como asistente a los festivales, quiero consultar los distintos festivales y sus datos de ubicación y programación, para elegir a cuáles asistir.

#### H.U.05. Consulta de horarios

Como asistente a los festivales, quiero consultar los horarios actualizados de las actuaciones de un festival, para organizar los conciertos que quiero ver.

#### H.U.06. Localización de escenarios y accesos

Como asistente a los festivales, quiero consultar la ubicación de los escenarios y de los accesos al recinto, para orientarme dentro del festival.

### Épica 3. Gestión de entradas y control de acceso

Relacionada con R.G.02: Agilización del acceso (check-in).

#### H.U.07. Registro de asistentes

Como asistente a los festivales, quiero registrarme con mis datos personales, para poder adquirir entradas y quedar identificado en el sistema.

#### H.U.08. Consulta de entradas

Como asistente a los festivales, quiero consultar la disponibilidad, el precio y las zonas autorizadas de cada tipo de entrada, para elegir la que mejor se adapte a mis necesidades.

#### H.U.09. Adquisición de entradas

Como asistente a los festivales, quiero adquirir una entrada para el festival seleccionado, para poder asistir y acceder a las zonas que incluye.

#### H.U.10. Validación de entradas

Como personal de control y acceso, quiero comprobar la identidad del asistente, la validez de su entrada y las zonas que autoriza, para permitir únicamente los accesos que correspondan.

#### H.U.11. Registro de entradas y salidas

Como personal de control y acceso, quiero registrar las entradas y salidas de los asistentes de cada recinto, para mantener actualizado el control de acceso al festival.

#### H.U.12. Consulta de registros de acceso

Como personal de control y acceso, quiero consultar los registros de entradas y salidas de cada festival, para comprobar los accesos realizados.

### Épica 4. Gestión de saldo y pagos cashless

Relacionada con R.G.04: Gestión de saldo y pagos cashless.

#### H.U.13. Consulta de saldo

Como asistente a los festivales, quiero consultar mi saldo cashless disponible, para saber cuánto puedo gastar dentro del recinto.

#### H.U.14. Recarga de saldo

Como asistente a los festivales, quiero recargar mi saldo cashless, para disponer de dinero suficiente para realizar compras dentro del recinto.

#### H.U.15. Pago mediante credencial o pulsera

Como asistente a los festivales, quiero realizar pagos utilizando mi credencial o pulsera y el saldo disponible, para comprar dentro del recinto sin utilizar dinero en efectivo.

#### H.U.16. Consulta del historial de operaciones

Como asistente a los festivales, quiero consultar mis recargas y pagos realizados, para comprobar los movimientos de mi saldo y verificar las transacciones.

### Épica 5. Seguimiento del festival

Relacionada con R.G.05: Monitorización de aforo e incidencias en tiempo real.

#### H.U.17. Consulta del aforo

Como promotor de los festivales, quiero consultar el número de asistentes presentes en el recinto de cada festival, para supervisar la ocupación y detectar posibles saturaciones.

#### H.U.18. Consulta de ventas por zona

Como promotor de los festivales, quiero consultar las ventas realizadas en las distintas zonas del recinto, para supervisar la actividad comercial durante el festival.

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


