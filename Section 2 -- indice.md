# INTRODUCCION

Este protocolo se define con la intención de hacer un datagrama que permita establecer 
la comunicación por intercambio de paquetes entre ordenadores interconectados mediante 
la aplicación MSGR UQ.

Este protocolo aporta un procedimiento para que un usuario pueda enviar mensajes a otros
a otros usuarios mediante la aplicación MSGR UQ, con un mínimo de   mecanismo de 
protocolo.

Este protocolo utiliza a su vez protocolos de redes locales, para llevar el datagrama a un
próximo escenario en internet (“Gateway”) o host destino, por ejemplo, hará uso del protocolo TCP
para la trasmisión de los datos en la capa de transporte, así como también manejará el
protocolo HTTP para establecer la conexión con el servidor al momento de iniciar sesión.

La aplicación contara con códigos de error por defecto, como son los códigos de error 
del protocolo http, a la hora de conectarse al servidor, es decir: 
1xx-Informativas
2xx-Peticiones
3xx-Redirecciones
4xx-Errores del cliente
5xx Errores del servidor.

Adicional a esto, se manejará una serie de código propios para el manejo 
de los estados del funciomaniento de la aplocacion en cuanto al envio de mensajes 
y administracion de usuarios, estos son:

6xx: Informacion
7xx: Exito 
8xx: Advertencias
9xx: Errores del Servidor
	
Codios de respuesta para Login de usuarios:	
601 : Se han enviando campos vacios.
701 : Autenticacion Exitosa.	
801 : No existe el usuario con los datos proporcionados de autenticacion	
802 : Usuario se encuentra bloqueado, no puede iniciar sesion		
901 : Error General, usuario y clave no fueron enviados. No se puede comprobar identidad.
	
Codigos de respuesta para actualizacion de usuarios:
702: Actualizacion de Informacion Correcta.	
803: No se logro actualizar la informacion del usuario.
902: Error General, la informacion enviada no fue suficiente para actualizar usuario.  
	
Codios de respuesta para el funcionamiento de la aplicacion:
	
602: Solicitud de Amistad Aceptada.
603: Solicitud de Amistad Rechazada.	
704: Solicitud de Informacion enviada correctamente.	
804: No se encuentra usuario, no se enviara solicitud.
903: Error General, la informacion suministrada no fue suficiente para enviar solicitud.
