# sistema-cliente-servidor-con-descarga-de-ficheros
# Practica Distribuidos - Extraordinario

Creada por: 

	* Rosa Maria Sacedon Ortega
	* Ángel Villaseñor Gómez

## Enunciado 


	El objetivo principal del proyecto es diseñar un sistema cliente-servidor que permita la descarga de ficheros. La implementación de este proyecto permitirá al alumno trabajar, mediante ZeroC Ice, los siguientes aspectos:
		 Comunicación asíncrona
		 Transparencia de localización
		 Manejo de canales de eventos
		 Despliegue de servidores

### Arquitectura del proyecto

	El sistema estará formado por cinco tipos de componentes: senders, encargados del envío de ficheros; transfers, para la gestión de la transferencia de cada 	archivo; receivers, empleados en la recepción de archivos; clientes, que solicitarán ficheros; y canales de eventos para la comunicación de estados entre componentes. 


### Descripcion del sistema

	El sistema consta de un cliente (FileDownloader) con una factoria de receivers, un servidor con una factoría de transfers y otro servidor con una factoría de senders. 
	El cliente, que recibirá como argumento el nombre de los ficheros, le pedirá un objeto transfer al servidor donde estos se crean y solicitará, por medio de dicho transfer, una transferencia de N ficheros poniendo en marcha una pareja receiver-sender para cada uno de ellos. Cuando todas las parejas estén listas el cliente iniciará la transferencia, el envío entre las parejas. 
	Los receivers notificarán al transfer cuando hayan terminado, y este destruirá al receiver que envía la notificación y a su sender compañero. Si todas las parejas han terminado, el tranfer informará al cliente (estará a la espera), que destruirá el transfer y terminará su ejecución.

### Manual de usuario

		  EJECUTAR el servidor
		 sudo make run-server
		 EJECUTAR el cliente
		 sudo make run-client
