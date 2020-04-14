# Especificación de requisitos 
## Del proyecto <Sporter>

Versión 1.0  
Generada por <Daniel Cuevas Pérez>  
<UMA>  
<14/04/2020>  

Índice
=================
* [Versiones](#versiones)
* 1 [Introducción](#1-introducción)
  * 1.1 [Objetivo del documento](#11-objetivo-del-documento)
  * 1.2 [Ámbito del proyecto](#12-ámbito-del-proyecto)
  * 1.3 [Definiciones, acrónimos y abreviaturas](#13-definiciones-acrónimos-y-abreviaturas)
  * 1.4 [Resumen del documento](#15-resumen-del-documento)
* 2 [Vista general del producto](#2-vista-general-del-producto)
  * 2.1 [Perspectiva del producto](#21-perspectiva-del-producto)
  * 2.2 [Funciones del producto](#22-funciones-del-producto)
  * 2.3 [Perfiles de usuario](#24-perfiles-de-usuario)
  * 2.4 [Suposiciones y dependencias](#25-suposiciones-y-dependencias)
* 3 [Interfaces externas](#3-interfaces-externas)
    * 3.1 [Interfaces con el Software](#31-interfaces-con-el-software)
* 4 [Requisitos](#4-requisitos)
  * 4.1 [Precedencia y prioridad](#41-precedencia-y-prioridad) 
  * 4.2 [Funcionales](#42-funcionales)

## Versiones
| Name | Date    | Reason For Changes  | Version   |
| ---- | ------- | ------------------- | --------- |
|    Sporter  |    14/04/2020     |          Inicial           |   1.0        |
|      |         |                     |           |

## 1. Introducción
El presente docuemnto, Especificación de Requisitos Sofware (SRS), ofrece una descripción detallada
de los requisitos necesarios para construir una aplicación de escritorio para la gestión de eventos deportivos.

### 1.1 Objetivo del documento
Este documento tiene como objetivo proporcionar información sobre las especificaciones funcionales, no
funcionales y de calidad del sistema para la implementación de una aplicación de escritorio que permitima a profesionales deportivos, instalaciones deportivas y el público en general,
la gestión de eventos deportivos. Este documento está destinado al cliente Sr. Joaquin Ballestero y a los miembros de desarrollo, testing y diseño
de nuestro equipo.

### 1.2 Ámbito del proyecto
Sporter es una aplicación que funcionará en un entorno de escritorio desarrollada en Java, que permitirá a las personas
gestionar, buscar y consultar eventos deportivos.

En primer objetivo más relevante sería que el sistema permitirá al usuario la opción de crear su propio evento deportivo, permitiendole personalizarlo introduciendo 
tipo de deporte, número máximo de jugadores, fecha y lugar del evento, color del equipamiento, precio por participar y duración.

Otra meta importante es la de ofrecer la posibilidad al usuario de buscar eventos dependiendo del deporte y en la ubicación que elija.
Esta opción mostrará una lista con toda la información de los distintos eventos, donde el usuario puede seleccionarlos y suscribirse.

Para poder tener una correcta gestión de los eventos, el sistema permitirá visualizar un historial de todos los eventos
deportivos, tanto si han sido creados por el usuario, como si son suscripciones a otros eventos. Además ofrece la
posibilidad de editar la información del evento creado, eliminarlo por completo o cancelar la asistencia de los eventos de otros usuarios en los que está suscrito.
Cuando se realiza una cancelación de evento o de suscripción, el sistema informa al lider y a los participates respectivamente por medio de un correo electrónico.
Estas funcionalidades facilitarán al usuario la coordinación, comunicación y búsqueda de los participantes, agilizando la puesta en marcha del evento.

Toda esta información se mantiene almacenada en una base de datos desarrollada con el software MySql, que se encuentra integrada en la propia
aplicación.

### 1.3 Definiciones, acrónimos y abreviaturas ***
Creación: Proceso por el cual una persona crea un evento deportivo.
Suscripción: Proceso por el cual una persona se une a un evento deportivo.
Participante: Persona que está inscrita para asistir al evento deportivo.
Lider: Persona que ha realizado la creación del evento deportivo y es responsable de su organización.
Historial: Proceso que muestra una lista de todos los eventos deportivos.
Java: Lenguaje de programación orientada a objetos y plataforma informática.
Base de datos: Conjunto de datos pertenecientes a un mismo contexto y almacenados sistemáticamente para su posterior uso.
MySql: Sistema de gestión de base de datos relacional.
JVM: Máquina virtual de java capaz de interpretar y ejecutar instrucciones expresadas en un código binario especial.

### 1.4 Resumen del documento
El resto del documento contiene tres secciones.
El segundo describe los factores generales que afectan al producto que se va a desarrollar y sus requisitos
de usuario o negocio. Aunque no especifica requisitos del sistema, proporciona la base para entenderlos en la sección 4.
En la tercera sección se definen las interfaces de usuario de entrada y salida del sistema software, facilitando la comprensión de los requisitos.
La cuarta sección y más importante, especifica los requisitos del producto a nivel de sistema, dividiendolos en diferentes categorías.

## 2. Vista general del producto

### 2.1 Perspectiva del producto
Sporter será un producto nuevo e independiente que no necesitará de interfaces adicionales que no sean la del sistema operatrivo y la
base de datos.

### 2.2 Funciones del producto
A continuación se detallan las funciones principales que la aplicación debe realizar o debe permitir que el usuario realice:

- Registro de cuentas en el sistema para tener diferentes entornos de trabajo y tener una mejor gestión de los eventos.
- Creación de eventos deportivos y acceso a la participación de otros usuarios a ellos.
- Posibilidad de modificar la información de los eventos creados o suscritos y su eliminación.
- Búsqueda de eventos deportivos y la posibilidad de suscribirse a ellos.
- Visualizar todos los eventos creados o suscritos.
- El sistema notificará a los participantes de un evento cuando este sea eliminado o alguien cancele su suscripción.

### 2.3 Perfiles de usuario
El sistema dispondrá de un único perfil de usuario, el cual tendrá acceso a todas las funciones de la aplicación.

### 2.4 Suposiciones y dependencias
La aplicación estará desarrollada en Java y utilizará una base de datos desarrollada en MySQL. Para su instalación y ejecución el usuario necesitará de window 8 o 10 y 
tener instalado el JVM.

### 3 Interfaces externas

#### 3.1 Interfaces con el Software
La aplicaciones se comunicará con una base de datos desarrollada con el software MySQL para realizar operaciones de consulta y escritura 
sobre los datos de las cuentas de usuario y los eventos deportivos.

## 4. Requisitos

### 4.1 Precedencia y prioridad

|  Id  |          Nombre         |                                                                                                 Descripción                                                                                                 |  Prioridad  | Precedencia |    Tipo   |
|:----:|:-----------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------:|:-----------:|:---------:|
| RF1  |     Registrar cuenta    |         El sistema deberá registrar los datos de usuario para la creación<br>de una cuenta para su posterior tratamiento. Estos incluirán su nombre<br>de usuario, contraseña y correo electrónico.         | Fundamental |             | Funcional |
| RF2  |     Inicio de sesión    |                                                                 El sistema permitirá al usuario iniciar sesión en su cuenta <br>registrada.                                                                 | Fundamental |      R1     | Funcional |
| RF3  |       Crear evento      | El sistema deberá registrar los datos de un evento deportivo para su<br>creación. Estos incluirán nombre del propietario, deporte, número de<br>participantes, ubicación, hora, fecha, equipación y precio. | Fundamental |             | Funcional |
| RF4  |      Editar evento      |                                                                       El sistema permitirá lo modificación de los datos de un evento.                                                                       | Fundamental |    R3,R7    | Funcional |
| RF5  |      Borrar evento      |                                                                              El sistema permitirá la eliminación de un evento.                                                                              | Fundamental |    R3,R7    | Funcional |
| RF6  |      Buscar evento      |                                                                     El sistema deberá mostrar los eventos deportivos de otros usuarios.                                                                     | Fundamental |             | Funcional |
| RF7  | Suscribirse a un evento |                                                                       El sistema permitirá la suscripción a eventos de otros usuarios.                                                                      | Fundamental |      R6     | Funcional |
| RF8  |   Historial de eventos  |                                                                        El sistema deberá mostrar un historial con todos los eventos.                                                                        | Fundamental |    R3,R7    | Funcional |
| RF9  |      Notificaciones     |                                                El sistema deberá notificar a los participantes de un evento de<br>modificaciones o de su propia eliminación.                                                | Fundamental |      R5     | Funcional |
| RF10 |  Comprobación de cuenta |                                                                         El sistema deberá verificar la validez del inicio de sesión.                                                                        | Fundamental |    R1,R2    | Funcional |
	
### 4.2 Funcionales

### RF1 - Registrar cuenta
El sistema permitirá la creación de una cuenta de usuario. Mostrará un formulario solicitando información sobre el nombre de la cuenta, contraseña y correo electrónico.
#### Dependencias 
Ninguna.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.

### RF2 - Iniciar sesión
El sistema permitirá el acceso al usuario a su entorno de trabajo. El sistema mostrará un pequeño formulario solicitando nombre de usuario y contraseña.
#### Dependencias 
RF1
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.

### RF3 - Crear evento deportivo
El sistema permitirá registrar, mediante un formulario, los datos referentes a la creación de un evento deportivo. El formulario tendrá como campos de texto el nombre del propietario del evento,
el cual se autocompletará al abrirse el formulario, un tipo de deporte, el numero de participantes que formarán el evento, la ubicación donde se celebrará, la hora y fecha, tipo de equipación y el
precio por participante. El evento creado se podrá visualizar en el historial.
#### Dependencias 
RF2.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.

### RF4 - Editar evento deportivo
El sistema deberá dar la posibilidad de modificar los datos sobre un evento deportivo seleccionado en el historial de eventos.
#### Dependencias 
RF2,RF8.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.

### RF5 - Borrar evento deportivo
El sistema deberá dar la posibilidad de eliminar un evento deportivo ubicado en el historial. Pueden ser eventos creados por el usuario o en los cuales está suscrito. 
#### Dependencias 
RF2,RF8.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.


### RF6 - Buscar evento deportivo
El sistema permitirá la búsqueda de eventos deportivos de otros usuarios. Esta búsqueda tendrá dos opciones de filtrado, una será por localidad y la otra por el tipo de deporte.
#### Dependencias 
RF2.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.


### RF7 - Suscrivirse a un evento
El sistema permitirá la suscripción a eventos creados por otros usuarios, mostrados en la funcionalidad de búsqueda de eventos.
#### Dependencias 
RF2,RF6.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.

### RF8 - Historial de eventos
El sistema deberá mostrar una tabla con la información de todos los eventos creados por el usuario o en los cuales está suscrito.
#### Dependencias 
RF2.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.

### RF9 - Notificaciones
El sistema deberá notificar a los suscriptores o al lider sobres modificaciones del evento o de su propia eliminación.
#### Dependencias 
RF2, RF4, RF5.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.

### RF10 - Comprobación de cuenta
El sistema deberá verificar la validez de los datos introducidos en el registro de cuenta. Comprobando que el correo electrónico es corrento y no hay una cuenta existente en la base de datos con los mismos datos.
Además tendrá que comprobar que los datos de inicio de sesión son correctos.
#### Dependencias 
RF1, RF2.
#### Priodidad
Fundamental.
#### Justificación
Derivado de un caso de uso.