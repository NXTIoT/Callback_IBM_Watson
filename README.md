Callback_IBM_Watson
===================

-	[Introducción](#introducción)

Introducción
------------

En este repositorio se muestran los pasos para la configuración del callback hacia IBM Watson. 

Primero, necesitaremos una cuenta en IBM Cloud ([Link](https://console.bluemix.net/)).
Una vez creada, entramos a nuestra cuenta y nos aparecerá el panel de control. Damos click en "Catalogo"

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm1.png?raw=true)

en el panel izquierdo, seleccionamos Plataforma -> Internet de las cosas -> Internet of things plataform

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm2.png?raw=true)

nos aparecerá una ventana con las caracteristicas del servicio. Damos click en crear

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm3.png?raw=true)

Una vez creada, nos abrirá en otra ventana la plataforma IBM Watson. En el panel izquierdo, seleccionamos "Apps"

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm4.png?raw=true)

ahora, crearemos una clave para poder conectar el backend con la plataforma de IBM. Damos click en "Generar clave de API" 

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm5.png?raw=true)

escribimos una breve descripcion y damos click en "Siguiente"

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm6.png?raw=true)

seleccionamos "Aplicacion estandar" y finalmente "Generar clave"

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm7.png?raw=true)

enseguida nos aparecera la "Clave de API" y la "Señal de Autenticacion". Estos dos datos son los que necesitamos para realizar el callback en el backend.

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm8.png?raw=true)

nos vamos a nuestra cuenta del backend y buscamos el dispositivo que deseamos conectar. Damos click en el device type

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm8a.png?raw=true)

enseguida nos aparecerá la información del device type. En el panel izquierdo, damos click en "Callbacks"

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm8b.png?raw=true)

en la esquina superior derecha seleccionamos "New" para crear un nuevo callback

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm8c.png?raw=true)

de entre los callbacks disponibles, selecionamos "IBM Watson IoT Platform" 

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm8d.png?raw=true)

copiamos y pegamos la "Clave de API" y la "Señal de Autenticacion" de acuerdo a la siguiente configuración:

-	"API Key" -> "Clave de API"

-	"Auth Token" -> "Señal de autenticación"

en el JSON ponemos las variables que queramos enviar. En este caso enviaremos dos variables que hemos creado (temperatura y humedad). 

JSON body:

	{
		"temperatura" : "customData#temp",
		"humedad" : "customData#humedad",
		"tiempo" : "{time}",
		"Nseq" : "{seqNumber}"
	}

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm12.png?raw=true)

finalmente damos click en "OK". Con esto terminamos la configuración de nuestro callback. Ahora, enviamos mensajes con nuestro dispositivo y
regresamos a la plataforma de IBM Watson. En el panel izquierdo, seleccionamos "Devices"

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm9.png?raw=true)

si ya se recibieron mensajes en el backend, nos aparecerá el ID de nuestro dispositivo en la plataforma de IBM. Damos click en el dispositivo y nos desplegará información

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm10.png?raw=true)

 seleccionamos la pestaña "Sucesos Recientes". Cada vez que se reciba un mensaje de nuestro dispositivo, nos aparecerá la información enviada en esta pestaña

![ibm1](https://github.com/NXTIoT/Callback_IBM_Watson/blob/master/imagenes/ibm11.png?raw=true)

