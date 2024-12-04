# Proyecto_DJK
Repositorio dedicado al proyecto de digitilización
- Samuel : **@samuelcrz30**  
- Cristian: **@CRhernandez1** 

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

**Dokku**
Dokku es una plataforma como servicio para  aplicaciones en servidores virtuales privados.
_Ventajas_ :

-Dokku es gratuito y permite pagar solo por los recursos utilizados en el VPS.
-Ofrece compatibilidad con múltiples lenguajes en Node.js, Python , Ruby y otros.
-Dokku además automatiza tareas de despliegue(configurar un servidor web, base de datos, actualizaciones, etc)
-Utiliza Docker
-Permite Escalabilidad tanto horizontal (añadir más estancias) como vertical (aumentar recursos).
_Requisitos_:
VPS , Docker , GIT

[Página oficial Dokku](https://dokku.com/)

Dokku para el supuesto **B**:

Para la empresa de desarrollo de software, podría interesarle implementar esta plataforma como servicio ya que puede alojar una parte de front, back y una base de datos.

**Instalación de Dokku:**

![Instalación](/Captura%20de%20pantalla%202024-12-04%20110416%20Dokku.png)

En el caso de dokku, para el análisis económico debemos centrarnos en VPS (Virtual Private Servers) que nos permitan alojar nuestro proyecto.

| DigitalOcean | Vultr | Azure |
|-------------|-------------|-------------|
| Plan básico      | Plan básico      | Plan de ahorro 1 año      |
| $5.00 al mes     | $5.00 al mes      | $5.08 al mes      |

Para el proyecto que se nos está planteando necesitaremos un hardware con suficientes recursos para alojar cada componente y su carga:

| CPU | RAM | Almacenamiento |
|-------------|-------------|-------------|
| 2-4 núcleos o más de 4 núcleos     | 8-16 GB     | 100-200GB      |
| (Dependiendo de la magnitud del proyecto)     | Menos de 8GB para un proyecto pequeño.      | Importante tener este factor en cuenta para la base de datos.      |
3.Análisis Económico.  
4.Conclusiones.  

#Exposición






