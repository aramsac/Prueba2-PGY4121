"# Prueba2-PGY4121" 

INSTRUCCIONES


1.- La aplicación debe permitir la creación de un nuevo usuario en el sistema. Para ello, los campos a ingresar son correo (PK), contraseña, nombre y apellido. Para ello, se debe realizar una petición de tipo POST utilizando los siguientes parámetros:

nombreFuncion: UsuarioAlmacenar
parametros: [correo, contrasena, nombre, apellido]

Si los datos ingresados son correctos, la respuesta será:

{"result":[{"RESPUESTA":"OK"}]}

En caso de que el correo ingresado ya se encuentre en la base de datos, la respuesta será:

{"result":[{"RESPUESTA":"ERR01"}]}

La contraseña ingresada se guardará encriptada en la base de datos, pero eso para ustedes no tendrá ningún impacto en el desarrollo.


2.- La aplicación debe permitir realizar el login para el usuario anteriormente creado. Para ello, se debe realizar una petición de tipo POST utilizando los siguientes parámetros:

nombreFuncion: UsuarioLogin
parametros: [correo, contrasena]
Si los datos ingresados son correctos, la respuesta será:

{"result":"LOGIN OK"}

En caso de que las credenciales ingresadas no sean las correctas, la respuesta será:

{"result":"LOGIN NOK"}


Si las credenciales introducidas son correctas debe navegar a la siguiente página. De no ser correctas, debe enviar un mensaje al usuario indicando que los datos ingresados son incorrectos.


3.- En la pantalla principal de la aplicación (la que viene después del login), deben mostrar un mensaje de bienvenida al usuario recién logueado, mostrando el nombre y apellido de este. Para ello, se debe realizar una petición GET utilizando los siguientes parámetros:

nombreFuncion: UsuarioObtenerNombre
correo: fer.sepulvedar@gmail.com (por ejemplo).
Si el correo existe en la base de datos, se obtendrá una respuesta como el siguiente ejemplo:

{"result":[{"NOMBRE":"Fernando","APELLIDO":"Sepulveda"}]}
 
La URL utilizada en el ejemplo anterior fue:

https://fer-sepulveda.cl/API_PRUEBA2/api-service.php?nombreFuncion=UsuarioObtenerNombre&correo=fer.sepulvedar@gmail.com


4.- Solo estando en la pantalla principal (no en el login), se debe permitir modificar la contraseña del usuario correctamente logueado. Para ello, se debe realizar una petición de tipo PATCH (su uso es igual al post, pero en vez de post, se coloca patch). Los parámetros a utilizar son los siguientes:

nombreFuncion: UsuarioModificarContrasena
parametros: [correo, contrasenaActual, contrasenaNueva]

Si el cambio de contraseña es correcto, se obtendrá la siguiente respuesta:

{"result":"OK"}

Mientras que, si la contraseña actual ingresada no es la correcta, se obtendrá lo siguiente:

{"result":"ERR02"}


5.- La ruta base para todas las peticiones es:

https://fer-sepulveda.cl/API_PRUEBA2/api-service.php


6.- La aplicación debe utilizar base de datos local para guardar la información relacionada con el usuario creado y logueado. 


7.- La aplicación debe correr en un emulador o dispositivo físico. Si el usuario se loguea correctamente, la próxima vez que la aplicación se abra (en el emulador o dispositivo físico) debe pasar directamente a la página principal, y no debe pedir nuevamente las credenciales, a menos que se cierre la sesión.


8.- Para aquellos equipos que tengan problema con el emulador, pueden utilizar LOCAL STORAGE y ejecutar todo el desarrollo en el navegador, pero el código de la base de datos local de todas maneras debe estar desarrollado y no utilizado.


9.- La fecha de entrega es la semana del 17 al 21 de Octubre, en nuestro horario de clases. Esta vez, y dada la complejidad que presenta el emulador, es que no habrá presentación, pero a cambio deberá entregar además del código fuente, un video de no más de 5 minutos mostrando todas las funcionalidades.


10.- Además de todos los contenidos vistos en la unidad 2, su proyecto debe tener todo lo visto durante el semestre, tal como componentes, rutas protegidas, página 404, etc.


La próxima semana en clases, les mostraré una posible solución que tengo desarrollada, por si tienen alguna duda. También configuraremos el emulador y les mostraré como lanzar la app en vivo.

Que tengan un muy buen fin de semana largo!