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

- Autentificación: Proceso mediante el cual el sistema verifica la identidad de un usuario que inicia sesión y le concede los permisos asociados a su rol.

- Check-in: Proceso de validación de la entrada de un asistente y registro de su acceso al recinto del festival.

- Dashboard: Panel de control que permite a los promotores consultar información del festival, como el aforo y las ventas por zona.

- Frontend: Parte visual del sistema con la que interactúan los usuarios.

- Transacción cashless: Operación que modifica el saldo digital de un asistente. Una recarga aumenta el saldo y un pago lo reduce. Los pagos se realizan mediante la credencial o pulsera del asistente.

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
Además, quiero poder consultar en todo momento el saldo disponible y los movimientos realizados para llevar un control de mis gastos durante el evento. De esta manera, podré reducir el tiempo de espera en los puntos de venta, evitar el uso de dinero en efectivo y disfrutar del festival con mayor comodidad, sin tener que preocuparme constantemente por llevar dinero encima.

#### R.G.05. Monitorización de aforo y ventas por zona

Como promotor del festival,
quiero visualizar datos del aforo del recinto en tiempo real y las ventas por zona,
para garantizar la seguridad, evitar saturaciones y tomar decisiones operativas durante el evento.

### 3.2. Usuarios del sistema

### PROMOTOR DE LOS FESTIVALES

El promotor se encarga de organizar y gestionar todos los aspectos relacionados con el festival. Entre sus funciones se encuentran la gestión del recinto, el control del aforo, la coordinación de los patrocinadores y la distribución de los diferentes escenarios.
Además, debe gestionar la participación de los artistas, organizar sus actuaciones y coordinar los horarios para garantizar que el evento se desarrolle de forma ordenada y eficiente.

### ASISTENTES DE LOS FESTIVALES

El asistente al festival necesita disponer de información clara y actualizada sobre la  ubicación de cada concierto y los horarios de las diferentes actuaciones, para poder organizar su tiempo y desplazarse entre los escenarios sin perderse ninguna actuación de su interés. También necesita conocer la localización de las entradas y los distintos accesos al recinto, para facilitar su llegada y evitar posibles confusiones. Además, es importante que pueda consultar los métodos de pago aceptados dentro del festival, como el pago con tarjeta o en efectivo, así como las opciones disponibles para comprar comida, bebida y  otros productos. De esta manera, podrá disfrutar del evento con  mayor comodidad y planificar mejor su experiencia.

### PERSONAL DE CONTROL Y ACCESO 
Gestionar las entradas de los asistentes, control de las entradas/salidas del recinto. 

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Registro de los asistentes

Como promotor de los festivales quiero que los asistentes se puedan registrar con sus datos personales para complar sus entradas y tener un contro de quien accede al festival.

**Prueba de aceptación**
- Se intenta registrar un asistente con un correo electrónico o documento de identidad ya registrado: el sistema rechaza el registro.
- Se intenta registrar dos asistentes con el mismo nombre y apellidos, pero con correos electrónicos y documentos de identidad distintos: el sistema permite ambos registros. 
- Los asistentesdeben ser mayores de edad (18 años o mas).
- Se debe aplicar la regla de negocio R.N.02.


#### R.F.02. Organizacion del festival

Como promotor de los festivales quiero organizar los distintos recintos alrededor de españa, a los artistas y patrocinadores que participaran en dicho evento y las distintas zonas de escenario que habra en el festival para tener el control de la asistencia de los artistas en cada festival ademas de los afroros en cada recinto y localizacion de los conciertos.

**Prueba de aceptación**
- Un artistas no pueden estar en mas de un escenario a la misma hora, ni durante la duracion del conciento a dicha hora. Además de que no podria estar el mismo dia en dos festivales de diferentes localizaciones. 
- Los asistentes al concierto no pueden superar el aforo del recinto.
- Se debe aplicar la regla de negocio ...
- Se debe aplicar la regla de negocio R.N.02. y el R.N.01
  

#### R.F.03. Método de pago 
Como comercio dentro del festival y como asistente al mismo quiero metodos de pago fiables y rapidos para no perder dinero y agilizar la compra venta en el festival 

**Prueba de aceptación**
- Debe tener saldo suficiente para hacer la compra.
- Se debe aplicar la regla de negocio R.N.01
  

#### R.F.04. Control de entrada 
Como personal de control y acceso al festival quiero un metodo de identificacion rapido para garantoizar que el asistente tiene entrada y cumple los requisitos para entrar.

**Prueba de aceptación**
- Cuando pasa la entrada marca como "Entrada", una vez con eso la persona que entra no debe tener esa marca.
- Debe entrar por la zona correcta que marque su entrada
- Su informacion identificadora debe ser valida  
- Se debe aplicar la regla de negocio R.N.03., R.N.04, R.N.05
  

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
##### R.N.01. Datos únicos de los asistentes

No puede haber dos asistentes registrados con el mismo correo electrónico o documento de identidad. Sí pueden tener el mismo nombre y apellidos si sus correos y documentos son distintos.

**Pruebas de aceptación**

- Dos asistentes tienen el mismo nombre, pero correos y documentos distintos: el sistema permite ambos registros.
- Un asistente intenta registrarse con un correo ya registrado: el sistema rechaza el registro.
- Un asistente intenta registrarse con un documento ya registrado: el sistema rechaza el registro.

##### R.N.02. Edad mínima para registrarse

En nuestro proyecto, los asistentes deben tener al menos 18 años en el momento de registrarse.

**Pruebas de aceptación**

- Una persona de 17 años intenta registrarse: el sistema rechaza el registro.
- Una persona cumple 18 años el día del registro: el sistema permite el registro si cumple las demás condiciones.
- Una persona mayor de 18 años intenta registrarse: el sistema permite el registro si cumple las demás condiciones.

##### R.N.03. Entrada válida para el festival

La entrada debe ser válida, pertenecer al asistente y corresponder al festival y a la fecha del acceso.

**Pruebas de aceptación**

- La entrada cumple todas estas condiciones: supera esta comprobación y se revisan las demás reglas de acceso.
- Se intenta acceder con una entrada de otro festival, de otra fecha o asociada a otra persona: en cada caso, el sistema rechaza el acceso.
- Se presenta una entrada anulada o que no existe: el sistema rechaza el acceso.

##### R.N.04. Acceso a las zonas autorizadas

Los asistentes solo pueden acceder a las zonas incluidas en su tipo de entrada.

**Pruebas de aceptación**

- Un asistente solicita acceder a una zona incluida en su entrada: supera esta comprobación si también cumple las demás condiciones de acceso.
- Un asistente con una entrada general que no incluye la zona VIP intenta acceder a ella: el sistema rechaza el acceso a esa zona.

##### R.N.05. Registro de entradas y salidas

Un asistente que ya aparece dentro del recinto no puede registrar otra entrada hasta que se registre su salida. Cada entrada aceptada aumenta en uno el número de personas presentes y cada salida válida lo disminuye en uno. No se puede registrar una salida de alguien que no aparece dentro.

**Pruebas de aceptación**

- Un asistente realiza un acceso autorizado y después sale: el sistema registra ambos movimientos, aumenta en uno el número de personas presentes al entrar y lo disminuye en uno al salir.
- Un asistente que ya está dentro intenta registrar otra entrada: el sistema la rechaza y el número de personas presentes no cambia.
- Se intenta registrar la salida de alguien que no aparece dentro: el sistema la rechaza y el número de personas presentes no cambia.

##### R.N.06. Control del aforo del recinto

El número de asistentes que se encuentren dentro del recinto no puede superar el aforo máximo permitido. Cuando se alcance el límite de personas, no se permitirá la entrada de más asistentes hasta que se registre alguna salida.

**Pruebas de aceptación**
- Si el recinto tiene aforo disponible, se podrá permitir la entrada de un asistente que tenga una entrada válida.
- Si el recinto ha alcanzado su aforo máximo, no se permitirá la entrada de más personas.
- Cuando un asistente salga del recinto y se registre su salida, se actualizará el aforo disponible.

##### R.N.07. Organización de los horarios de los artistas

Un artista no puede actuar en dos escenarios diferentes a la misma hora ni tener dos actuaciones cuyos horarios se solapen. De esta forma, se evitan los conflictos en la programación del festival.

**Pruebas de aceptación**
- Se podrá asignar un artista a una actuación si no tiene otra programada en ese mismo horario.
- No se permitirá guardar una programación en la que un artista tenga dos actuaciones que coincidan total o parcialmente en el tiempo.
- Se podrá programar al mismo artista en diferentes horarios, siempre que las actuaciones no se solapen.

##### R.N.08. Participación de los artistas en diferentes festivales

Un artista no puede participar el mismo día en dos festivales que se celebren en lugares diferentes, ya que no podría asistir a ambas actuaciones.

**Pruebas de aceptación**
- Se podrá asignar un artista a un festival si no tiene otra actuación ese mismo día en un festival situado en otra localización.
- No se permitirá programar al mismo artista en dos festivales diferentes el mismo día si se celebran en lugares distintos.
- Se podrá programar al artista en festivales diferentes si las fechas no coinciden.

##### R.N.09. Saldo suficiente para realizar pagos

Para realizar una compra dentro del festival mediante el sistema de pago cashless, el asistente debe tener saldo suficiente en su cuenta. Si el saldo es inferior al importe de la compra, el pago no se realizará.

**Pruebas de aceptación**
- Si el asistente tiene saldo suficiente para pagar una compra, se permitirá realizar el pago.
- Si el saldo del asistente es inferior al importe de la compra, se rechazará el pago.
- Cuando se realice una compra correctamente, se descontará del saldo el importe correspondiente.

##### R.N.10. Actualización del saldo y registro de las operaciones

Cada vez que un asistente realice una recarga o un pago mediante el sistema cashless, se deberá actualizar su saldo y guardar la operación realizada para que pueda consultarla posteriormente.

**Pruebas de aceptación**
- Cuando se realice una recarga correctamente, se sumará el importe al saldo disponible del asistente.
- Cuando se realice un pago correctamente, se restará el importe correspondiente del saldo.
- Las recargas y los pagos realizados quedarán registrados en el historial de operaciones del asistente.

##### R.N.01. Título regla negocio

Descripción de la regla de negocio.

### 4.2. Mapa de historias de usuario (opcional)

Este mapa organiza lo que necesita hacer cada usuario en el sistema. Las historias se agrupan por temas, llamados épicas. Cada historia explica quién realiza una acción, qué quiere hacer y para qué.

El sistema permite gestionar varios festivales, cada uno con sus artistas, actuaciones, escenarios, entradas y asistentes.

#### Organización del mapa

La siguiente tabla resume las actividades de cada usuario:

| Usuario | Antes del festival | Durante el festival | Consultas de seguimiento |
| --- | --- | --- | --- |
| Promotor | Consultar recintos, organizar escenarios y preparar los horarios de las actuaciones. | Supervisar la programación y el aforo. | Consultar las ventas por zona. |
| Asistente | Registrarse, consultar festivales y comprar una entrada. | Consultar horarios y escenarios, acceder al recinto y pagar con su saldo. | Consultar su saldo y sus operaciones. |
| Personal de control y acceso | Comprobar la información y los permisos de las entradas. | Validar entradas y registrar entradas y salidas. | Consultar los registros de acceso. |

#### Épica 1. Organización de festivales y programación

Relacionada con R.G.01: Gestión centralizada de los eventos y su programación.

##### H.U.01. Consulta de recintos

Como promotor, quiero consultar la ubicación, el aforo y la disponibilidad de los recintos, para elegir dónde celebrar cada festival.

##### H.U.02. Organización de escenarios

Como promotor, quiero organizar los escenarios y las zonas de cada festival, para distribuir las actuaciones dentro del recinto.

##### H.U.03. Programación de actuaciones

Como promotor, quiero asignar a cada actuación sus artistas, escenario y horario, para organizar la programación del festival.

#### Épica 2. Consulta de festivales y programación

Relacionada con R.G.03: Consulta de horarios y mapa en tiempo real.

##### H.U.04. Consulta de festivales

Como asistente, quiero consultar dónde se celebran los festivales y qué actuaciones tienen, para elegir a cuáles ir.

##### H.U.05. Consulta de horarios

Como asistente, quiero consultar los horarios actualizados de las actuaciones, para organizar los conciertos que quiero ver.

##### H.U.06. Localización de escenarios y accesos

Como asistente, quiero consultar dónde están los escenarios y los accesos al recinto, para orientarme en el festival.

#### Épica 3. Gestión de entradas y control de acceso

Relacionada con R.G.02: Agilización del acceso (check-in).

##### H.U.07. Registro de asistentes

Como asistente, quiero registrarme con mis datos personales, para poder comprar entradas y quedar identificado en el sistema.

##### H.U.08. Consulta de entradas

Como asistente, quiero consultar los tipos de entrada, sus precios, su disponibilidad y las zonas que incluyen, para elegir cuál comprar.

##### H.U.09. Compra de entradas

Como asistente, quiero comprar una entrada para el festival elegido, para poder asistir y acceder a las zonas que incluye.

##### H.U.10. Validación de entradas

Como personal de control y acceso, quiero comprobar que la entrada es válida, pertenece al asistente y permite acceder a la zona solicitada, para autorizar el acceso correctamente.

##### H.U.11. Registro de entradas y salidas

Como personal de control y acceso, quiero registrar cuándo entran y salen los asistentes, para mantener actualizado quién está dentro del recinto.

##### H.U.12. Consulta de registros de acceso

Como personal de control y acceso, quiero consultar las entradas y salidas registradas, para comprobar los accesos de los asistentes al festival.

#### Épica 4. Gestión de saldo y pagos cashless

Relacionada con R.G.04: Gestión de saldo y pagos cashless.

##### H.U.13. Consulta de saldo

Como asistente, quiero consultar mi saldo disponible, para saber cuánto puedo gastar dentro del recinto.

##### H.U.14. Recarga de saldo

Como asistente, quiero añadir saldo a mi cuenta cashless, para poder realizar compras dentro del recinto.

##### H.U.15. Pago con credencial o pulsera

Como asistente, quiero pagar con mi credencial o pulsera utilizando mi saldo disponible, para comprar sin usar dinero en efectivo.

##### H.U.16. Consulta del historial de operaciones

Como asistente, quiero consultar las recargas y los pagos que he realizado, para comprobar en qué he gastado mi saldo.

#### Épica 5. Seguimiento del festival

Relacionada con R.G.05: Monitorización de aforo y ventas por zona.

##### H.U.17. Consulta del aforo

Como promotor, quiero consultar cuántas personas están dentro del recinto, para controlar la ocupación del festival.

##### H.U.18. Consulta de ventas por zona

Como promotor, quiero consultar las ventas de las distintas zonas del recinto, para hacer un seguimiento de la actividad comercial del festival.

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Seguridad y protección de los datoss personales**

Como promotor del festival, quiero que los datos personales de los asistentes estén protegidos y que únicamente puedan acceder a ellos los usuarios autorizados, para garantizar así su privacidad y evitar accesos no permitidos. Además, quiero que la información almaceada en el sistema se gestione de forma segura, especialmente los datos relacionados con el registro de usuario y la compra de entradas, además del pago con la pulsera.

**R.N.F. 02. Rendimiento del sistema**

Como promotor del festival, quiero que las consultas relacionadas con las entradas, el aforo y la información de los asistentes se realicen en un tiempo razonable, para gestionar el evento de forma eficiente. Asimismo, el sistema debe funcionar correctamente cuando varios usuarios lo utilicen al mismo tiempo, evitando así retrasos excesivos y facilitando el acceso a la información tanto a los organizadores como a los asistentes.


**R.N.F. 03. Facilidad de uso**

Como asistente al festival, quiero que la plataforma sea sencilla e intuitiva, para poder consultar fácilmente la información sobre las entradas, los horarios de los conciertos y la ubicación exacta de los escenarios. Además, quiero que los diferentes apartados estén organizados de forma clara, para encontrar rápidamente la información que necesito sin tener conocimientos técnicos previos.

**R.N.F. 04. Compatibilidad con diferentes dispositivos**

Como asistente al festival, quiero poder acceeder a la plataforma desde diferentes dispositivos, como móviles, tabletas y ordenadores, tanto desde IOS como con Android u otros. Para poder consultar toda la información desde cualquier punto y utilizar el dispositivo que me resulte más cómodo.


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


