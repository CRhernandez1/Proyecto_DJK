# Proyecto_DJK
Repositorio dedicado al proyecto de digitilización
- Samuel : **@samuelcrz30**  
- Cristian: **@CRhernandez1** 
- Eduardo: **@edumel20**


**_SUPUESTOS A ANALIZAR:_**  

**Problema A**  
Una startup tecnológica necesita alojar una aplicación de alto rendimiento que debe escalar rápidamente durante eventos de tráfico elevado. Además, requiere un control total sobre la configuración de los servidores, la red y el almacenamiento, con el objetivo de hilar fino en el hardware para ahorrar costes.  
**Problema B**  
Una empresa de desarrollo de software debe construir y desplegar una nueva aplicación web en el menor tiempo posible, con la necesidad de disponer un sistema que permita alojar backend, frontend y conectarse con una base de datos PostgreSQL. No desea preocuparse por la gestión de servidores ni por la infraestructura subyacente.   
**Problema C**  
Una cadena de restaurantes necesita implementar una funcionalidad que permita enviar notificaciones automáticas a los clientes cuando su pedido está listo. El sistema debe ser escalable, de bajo coste, y ejecutarse únicamente cuando se realicen pedidos.  

***1.Identificación del Modelo de Servicio Adecuado.*** 

En nuestro caso hemos elegido el problema B. Y para el mismo creemos que el modelo de servicio en la nube más adecuado, sería PaaS (Plataforma como servicio).  
Con esta opción, obtenemos un servidor listo para instalar nuestras aplicaciones web, mientras que la gestión del hardware y el software necesario para que nuestra aplicación funcione (Sistema Operativo, servidor web, gestor de base de datos, etc.) es realizada por terceros.  
Lo que cumple perfectamente con la premisa del enunciado, ya que podremos centrar nuestros esfuerzos en desarrollar el código y despreocuparnos de la gestión de servidores.  

***2.Investigación de Plataformas.***  

**-[Railway](https://railway.app/):** Es una platafaroma que ofrece un enfoque simplificado para alojar aplicaciones web, servidores backend y bases de datos, permiento al usuario despreocuparase de la infraestructura.  
La cual destaca por su facilidad, puesto que ofrece una interfaz muy intuitiva para los usuarios, se encarga de configurar automaticamente recursos como bases de datos, variables de entorno y dominions personalizados.
Además tiene una gran adaptabilidad, ya que es una plataforma **Pay-as-you-go**, pagas por lo que usas.  

![Pricing](./pricing%20railway.png)  
Railway ofrece distintos planes, diseñados para diferentes necesidades. Empezando desde el plan gratuito, en el que el usuario recibe 5$, principalmente para proyectos pequeños y explorar la plataforma. Continuando por el plan Pro, en el que empezaríamos nosotros, ya que da soporte para multiples espacios de trabajo y amplía los limites por servicio. Y finalizando, con el plan Enterprise, que mejora todo lo anterior y está destinado a operaciones a gran escala.      
![Dinamically scale](./Captura%20desde%202024-12-03%2009-01-10.png)  
Dispone tanto de escalabilidad vertical como horizontal. Y se encarga de escalar automáticamente las aplicaciones según la demanda, asegurando que puedan manejar más tráfico o carga, sin necesidad de configurarlo manualmente.  
![Integration](./github%20railway.png)  
Cuenta con integración con GitHub y GitLab, permitiendo integrar repositorios y desplegar aplicaciones automáticamente.      
Por lo que desde el panel de Railway podemos vincular el proyecto con un repositorio remoto. Estableciendo así una conexión entre la plataforma y el código fuente. Para que después la misma se encarge de desplegarlo automáticamente. ¿Y cómo sucede esto? Gracias a la monitorización de ramas.  
Se puede establecer que rama se desea monitorizear. Por lo que podríamos monitorizar la rama `main` y usarla como rama de producción. Mientras usamos otras ramas para hacer pruebas o implementar nuevas funcionalidades. Con el objetivo de que Railway despliegue la aplicación cuando los cambios lleguen a la rama `main`.  

[Dokku](https://dokku.com/)
Dokku es una plataforma como servicio para  aplicaciones en servidores virtuales privados.
_Ventajas_ :

-Dokku es gratuito y permite pagar solo por los recursos utilizados en el VPS.
-Ofrece compatibilidad con múltiples lenguajes en Node.js, Python , Ruby y otros.
-Dokku además automatiza tareas de despliegue(configurar un servidor web, base de datos, actualizaciones, etc)
-Utiliza Docker
-Permite Escalabilidad tanto horizontal (añadir más estancias) como vertical (aumentar recursos).
_Requisitos_:
VPS , Docker , GIT


Dokku para el supuesto **B**:

Para la empresa de desarrollo de software, podría interesarle implementar esta plataforma como servicio ya que puede alojar una parte de front, back y una base de datos.

**Instalación de Dokku:**

![Instalación](/Captura%20de%20pantalla%202024-12-04%20110416%20Dokku.png)

#### Heroku
- [Heroku](https://www.heroku.com/) es una PaaS que permite a los desarrolladores crear, implementar y escalar aplicaciones rápidamente sin preocuparse por la gestión de servidores o infraestructura subyacente.


<div align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Heroku_logo.svg/480px-Heroku_logo.svg.png" width="200px"/>
</div>


- Sus características principales son que es multilenguaje, ya que es compatible cono múltiples lenguajes como Python, Java o PHP, permite implementar aplicaciones directamente desde GitHub (se puede vincular a un repositorio de GitHub para implementaciones automáticas cada vez que se actualiza el código en la rama *main*) o desde la terminal, se pueden utilizar complementos o herramientas externas para configurar un escalado automático (ajustando la cantidad de instancias según el tráfico o el uso de recursos) y soporta bases de datos PostgreSQL

- Heroku tiene diferentes planes de presupuesto dependiendo de las caracteísticas y del tipo de aplicación que queramos desplegar. En este caso escogeríamos una opción que permita alojar aplicaciones con funciones complejas que requieren alta disponibilidad, latencia muy baja y la gestión de un gran volumen de solicitudes simultáneas.

![Heroku_prices](./Captura%20de%20pantalla%202024-12-13%2019185.png)

- En este caso optaremos por la opción que tienen para empresas, ya que lo que buscamos es no preocuparnos por la gestión de servidores ni por la infraestructura subyacente.

## 3.Análisis Económico.  
### Heroku  

Como mencionamos previamente, Heroku trabaja con dynos. Los cuales varían según el plan que se elija. Cada uno tiene características y limitaciones específicas que afectan directamente el rendimiento de las aplicaciones.

Por lo tanto, con los planes más económicos, nos encontramos una serie de limiticiones importantes. En el plan *Eco*, la mayor de todas es el sleep mode. Es decir, si la aplicación no recibe tráfico de usuarios durante 30 minutos, el dyno entra en modo inactivo, lo que genera un tiempo de inicio más largo cuando se vuelve a acceder a la aplicación. Y en el plan *Basic*, aunque elimina el sleep mode y es una opción económica presenta limitaciones en términos de recursos y escalabilidad. Solo incluye un dyno por aplicación, lo cual puede resultar insuficiente a largo plazo cuando el proyecto crezca o se necesiten más recursos. Además, este plan no incluye soporte prioritario ni herramientas avanzadas para el manejo de aplicaciones en producción, lo que podría ser problemático si se presentan errores o si se necesitan características más sofisticadas.

Así que solo valoraremos la posibilidad del plan *Standard*, aunque a corto plazo no sea lo mejor. Según la propia Heroku es el más adecuado para aplicaciones en producción con tráfico de medio a alto, que es el que esperamos obtener en un plazo de tiempo no muy lejano. Además cuenta con dynos activos todo el tiempo (sin el inconveniente del sleep mode), con una buena escalabilidad (permite agregar más dynos si es necesario, con 2.5 GB de RAM por dyno), lo que es adecuado para un backend robusto y para aplicaciones que requieren recursos moderados.
Con el plus, de un soporte mejorado: Al tener acceso a soporte básico y herramientas de monitoreo.  

Todo por un precio que empieza desde los 25$ al mes hasta los 50$, por persona para que cada uno de los desarrolladores pueda trabajar en su propio entorno aislado, lo que facilita la colaboración y asegura que las aplicaciones estén siempre activas y sin tiempo de espera, a diferencia de los planes más básicos.

### Railway 

Comenzar con Railway para nosotros es una desventaja inicial debido a que el plan más básico de la plataforma no ofrece varios entornos de desarrollo. Por lo que tendríamos que comenzar desde el plan Pro, el cual tiene un precio de 20$ al mes por usario. Sin embargo, el principal beneficio de este plan es que proporciona acceso a recursos como 32 vCPU y 32 GB de RAM por servicio, permitiéndonos trabajar en múltiples entornos de desarrollo.  

Y no solo esto, la gran ventaja de Railway, en comparación con otras plataformas, es que su modelo de precios es muy flexible: solo se paga por los recursos que realmente se usan. Esto significa que si en algún momento la aplicación supera los límites del plan Pro, la plataforma ajustará dinámicamente los recursos, y te cobrará por los recursos adicionales que utilices. Este sistema es especialmente útil durante periodos de alta demanda, ya que puedes escalar la infraestructura según sea necesario sin comprometerte a pagar por recursos que no necesitas constantemente.  

En cambio, si la demanda disminuye y tu aplicación empieza a usar menos recursos , Railway reducirá automáticamente los costos, facturando de nuevo el precio asociado a la tarifa contratada. Este modelo de pago por uso ofrece flexibilidad y permite a las empresas adaptarse mejor a los cambios en la demanda de recursos, lo que resulta en un gran ahorro en tiempos de baja demanda.  

### Dokku

Dokku es una plataforma de implementación de aplicaciones que se utiliza para desplegar aplicaciones web en servidores privados. A diferencia de plataformas como Heroku o Railway, Dokku no tiene costos fijos de suscripción, ya que es de código abierto y puede instalarse en cualquier servidor. Sin embargo si que tiene costes, puesto que Dokku dependen principalmente de la infraestructura subyacente elegida para alojar el servidor, como un servidor dedicado o una máquina virtual.

En nuestro caso hemos decidido valorar las siguientes opciones de planes básicos de VPS (Servidor Privado Virtual) dónde implementar Dokku:

| DigitalOcean | Vultr       | Azure               |
|--------------|-------------|---------------------|
| Plan básico  | Plan básico | Plan de ahorro 1 año|
| $5.00 al mes | $5.00 al mes| $5.08 al mes        |

**Ventajas a corto plazo:**  

*1. Bajo costo inicial:* Las opciones de $5 al mes de plataformas como DigitalOcean y Vultr son económicas para el inicio del proyecto, sobre todo si el tráfico de usuarios es bajo. 

*2. Control total sobre la infraestructura:* Al usar Dokku en un VPS, tendríamos control completo sobre el servidor y la infraestructura, por lo que podríamos optimizar y personalizar los recursos.

**Desventajas a largo plazo:**  

*1. Escalabilidad:* A medida que la aplicación crezca y aumente el tráfico de usuarios, se necesitará escalar el VPS. Lo que se traduce en contratar más recursos (mayor RAM, más CPUs, o mayor almacenamiento). Por ejemplo, el plan básico de $5/mes podría no ser suficiente para manejar la aplicación, si las cosas van bien, en un período relativamente corto. Y escalar puede costar entre $10 y $40 al mes, dependiendo de cuántos recursos adicionales se necesiten.

*2. Gestión del servidor:* A diferencia de Heroku y Railway, que ofrecen soluciones gestionadas, con Dokku nosotros seremos los responsable de la gestión del servidor, lo cual incluye:  
-Mantenimiento del servidor: Actualizaciones, monitoreo y gestión de la seguridad.  
-Soporte de base de datos: Instalar y administrar bases de datos (como PostgreSQL).  

Lo que sin duda incrementa el costo indirecto, ya que el tiempo que dedicamos a gestionar el servidor, se lo tenemos que restar al que tenemos para implementar la aplicación.

*3. Costos de infraestructura adicionales:* Si en algún momento necesitamos una base de datos externa o servicios adicionales (como un CDN, almacenamiento adicional o copias de seguridad), también tendrías que pagar por estos servicios, lo que incrementaría los costos de mantenimiento.

4.Conclusiones.  

#Exposición






