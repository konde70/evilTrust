# evilTrust

<p align="center">
<img src="images/evil.png"
	alt="Evil logo"
	width="200"
	style="float: left; margin-right: 10px;" />
</p>

Herramienta ideal para el despliegue automatizado de un **Rogue AP** con capacidad de selección de plantilla.

Esta herramienta dispone de varias plantillas a utilizar, incluyendo una opción de plantilla personalizada, donde el atacante es capaz de desplegar su propia plantilla.

¿Cómo funciona?
======
La herramienta comienza haciendo una comprobación de las utilidades necesarias para desplegar el ataque:

<p align="center">
<img src="images/inicio.png"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

Una vez pasada la verificación, se listan las interfaces de red disponibles, siendo necesario en este punto seleccionar la interfaz configurada en modo monitor (se configura de manera automática):

<p align="center">
<img src="images/interfaces.png"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

Tras seleccionar la interfaz en modo monitor, será necesario especificar el nombre del punto de acceso que se desee crear así como el canal en el que se desea que opere. Una vez especificado, se configurará la interfaz en modo monitor para que opere como router, asignado como puerta de enlace predeterminada la dirección IP **192.168.1.1**, actuando en modo **DHCP**.

<p align="center">
<img src="images/config.png"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

En este punto será necesario especificar la plantilla con la que se desea trabajar. Es importante seleccionar una de las plantillas listadas como ejemplo, especificando su nombre tal y como se muestra a continuación:

<p align="center">
<img src="images/plantilla_000.png"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>


Ya en este punto, se montará el punto de acceso y se dispondrá una ventana a la espera de obtener credenciales:

<p align="center">
<img src="images/wait.png"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

Desde el lado de la víctima, se podrá visualizar el punto de acceso creado. La víctima se conectará al AP (pues todos somos yonkis del WiFi) y recibirá el siguiente aviso:

<p align="center">
<img src="images/aps.jpg"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

De manera automática, se abrirá el navegador mostrando la plantilla web configurada en la fase de selección:

<p align="center">
<img src="images/plantilla.jpg"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

La víctima introducirá sus credenciales, pues ve que para continuar navegando es necesario autenticarse bajo la plataforma configurada:

<p align="center">
<img src="images/iniciosesion.jpg"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

Una vez introducidas las credenciales, el atacante dispone de sus credenciales:

<p align="center">
<img src="images/first_step_000.png"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>


Para no quedarnos cortos, en caso de que la víctima disponga de segundo factor de autenticación configurado, tras introducir sus credenciales, la víctima es redirigida al siguiente portal web:

<p align="center">
<img src="images/sms.jpg"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

¿Por qué?, por lo siguiente. Dado que nosotros como atacantes disponemos de las credenciales de la víctima, de manera inmediata ya estaremos validando sus credenciales desde nuestro navegador. Si la víctima utiliza segundo factor de autenticación, tras iniciar sesión, nos saltará el aviso de que es necesario enviar un SMS al dispositivo móvil o correo electrónico para iniciar sesión.

Como esta comprobación se realiza manualmente casi de manera inmediata, la víctima quedará a la espera de ese SMS. Por tanto, tras iniciar sesión de nuestro lado y enviar el SMS a la víctima, la víctima introduce el SMS recibido en su dispositivo:

<p align="center">
<img src="images/sms_code.jpg"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

Y el atacante ahora, dispone del SMS necesario para acceder en ese intento de inicio de sesión:

<p align="center">
<img src="images/second_step.png"
        alt="Evil logo"
        style="float: left; margin-right: 10px;" />
</p>

