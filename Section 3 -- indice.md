# ESPECIFICACION DEL PROTOCOLO

Este es un protocolo define la estrucutura de los mensajes que seran enviando por 
medio de la aplicacion, este protocolo gestionara el tipo de mensajes intercambiados, 
la sintaxis con la cual seran contruidos cada uno de los mensajes que seran enviados, 
asi como tambien semantica para su correcto procesamiento y definira las reglas para 
el proceso de envio y recepcion de los mensajes.

El protocolo usa diversos tipos de peticiones las cuales son enviadas o recibidas 
segun como sean solicitadas, el servidor siempre esta atento a cualquier peticion 
del cliente y este responde  en funcion de la peticion solicitada con su respectivo 
mensaje y codigo de respuesta.

El mensaje de solicitud de autenticacion se presenta cuando un cliente necesita 
aquirir los servicios del servidor, el cliente debera presentar credenciales de 
autenticacion y demostrar que esta registrado en la base de datos del servidor, 
todo esto sera manejado mendiante el protocolo HTTP, por lo que seran implementados
todas las caracteristicas y estructuras para el uso de este protocolo en la aplicacion.

Los mensajes que se intercambian mendiante el protocolo diseñado para la apliacion
tienen un codigo que los identifican, este codigo empieza a ser un consecutico 
dentro de la transaccion, esto para poder retomarlos a la hora de generar una 
respuesta del estado de la transaccion realizada con el mensaje enviado.

	
## Definicion del formato del protocolo
	
### Lista de usuarios conectados
		
Comando:#lista_usuarios
Separador componentes:||
destino: usuario
objeto: "lista_usuarios"
token: identificador usuario
	
### Obtener lista solicitudes de usuario

Comando:#lista_solicitudes
Separador componentes:||
destino: usuario
objeto: "lista_solicitudes"
token:identificador usuario
	
### Enviar mensaje
Comando:#mensaje
Separador componentes:||
origen: Usuario
destino: usuario
id: 969999
mensaje: "hola :) "		
token:identificador usuario

### Enviar archivo
Comando:#archivo
Separador componentes:||
origen: Usuario
destino: usuario
id: 969999
nombre_archivo: "archivo.pdf"
Contenido_archivo: base64
token:identificador usuario
	
### Enviar meme
Comando:#meme
Separador componentes:||
origen: Usuario
destino: usuario
id: 969999
nombre_meme: "meme.png"
token:identificador usuario

### Enviar imagen
Comando:#img
Separador componentes:||
origen: Usuario
destino: usuario
id: 969999
nombre_archivo: "imagen.jpeg"
Contenido_archivo: base64
token: indentificador usuario
Estrucutura del mensaje

### Enviar solicitud
Comando:#solicitud
Separador componentes:||
origen: Usuario
destino: usuario
id: 969999
mensaje: "Agregar"
token:Identificador Usuario


### Respuesta
Comando:#respuesta
Comando a responder:#comando
Separador componentes:||
destino: usuario
id: 969999
Estado:Codigo respuesta
token:Identificador usuario

### Desconectar
Comando:#desconectar
Separador componentes:||
origen: usuario	
Estado:Codigo respuesta
token:Identificador usuario

## Estructura de los mensajes

### Lista de usuarios conectados
 ---------------------------------------------------
 |Comando|| token|| destino de la peticion ||objeto |
 ---------------------------------------------------
	
### Obtener lista solicitudes de usuario
 ---------------------------------------------------
| Comando|| token|| destino de la peticion ||objeto |
 ---------------------------------------------------
	
### Enviar mensaje
 ------------------------------------------------------------------------------
| Comando|| token||id mensaje||destino del mensaje||Origen del mensaje||mensaje|
 ------------------------------------------------------------------------------

### Enviar archivo
 --------------------------------------------------------------------------------------------------------
| Comando|| token||id mensaje||destino del mensaje||Origen del mensaje||Nombre archivo||Contenido archivo|
 --------------------------------------------------------------------------------------------------------
	
### Enviar meme
 ----------------------------------------------------------------------------------
| Comando|| token||id mensaje||destino del mensaje||Origen del mensaje||Nombre meme|
 ----------------------------------------------------------------------------------
	
### Enviar imagen
 -------------------------------------------------------------------------------------------------------
| Comando|| token||id mensaje||destino del mensaje||Origen del mensaje||Nombre imagen||Contenido archivo|
 -------------------------------------------------------------------------------------------------------
	
 ### Enviar Solicitud
 --------------------------------------------------------------------
| Comando|| token||destino de la solicitud||Origen Solicitud||Mensaje|
 --------------------------------------------------------------------

### Respuesta
 ---------------------------------------------------------------------------------
| Comando|| token||Id respuesta||Comando a responder||destino de respuesta||Estado|
 ---------------------------------------------------------------------------------
	
### Desconectarse
 --------------------------------
| Comando|| token||origen||Estado|
 --------------------------------

