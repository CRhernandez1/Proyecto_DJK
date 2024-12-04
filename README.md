# Proyecto_DJK
Repositorio dedicado al proyecto de digitilización
- Samuel : **@samuelcrz30**
- Cristian: **@CRhernandez1**
  
_SUPUESTOS A ANALIZAR_
Problema A 
_Startup Tecnológica_
Problema B
_Empresa de desarrollo de Software_ 
Problema C 
_Cadena de Restaurantes_
1.Identificación del Modelo de Servicio Adecuado.
2.Investigación de Plataformas.
3.Análisis Económico.
4.Conclusiones.
#Exposición




#Exposición

_Supuesto B_

Posibles plataformas como servicio para aplicar en el supuesto 
**B**

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