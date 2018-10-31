---

copyright:

  years:  2016, 2018

lastupdated: "2018-10-05"

---

# Arquitectura de varios sitios

Un diferenciador de claves entre {{site.data.keyword.cloud}} y otras ofertas de nube es la capacidad de suministrar capacidad de cálculo dedicada en todo el mundo y de conectar automáticamente la infraestructura a petición con la red dentro de su cuenta privada de {{site.data.keyword.cloud_notm}}. Las funciones de red definidas por software de VMware vCenter Server y de VMware Cloud Foundation, junto con {{site.data.keyword.cloud_notm}} proporcionan una infraestructura global granular que se puede crear en cuestión de días. En las secciones siguientes se describe un ejemplo de arquitectura de varios sitios de lo que se puede lograr con la capacidad disponible de vCenter Server o Cloud Foundation.

## Entorno entre vCenter NSX

La función de NSX de vCenter permite enlazar en una relación primaria y secundaria de hasta nueve gestores de NSX: uno primario y ocho secundarios. Aunque no es necesario, tener los servidores vCenter en una relación de modalidad enlazada mejorada (ELM) para que la función entre vCenter NSX entre en funcionamiento proporciona las siguientes ventajas:

* Creación de relaciones primarias y secundarias simplificada mediante las credenciales de inicio de sesión único (SSO)
* La automatización de vCenter Server y Cloud Foundation configura la resolución de nombres DNS para todos los sitios que están enlazados
* Panel único de gestión de vidrio en todos los sitios para las funciones de NSX y vCenter normales

## Ejemplo de varios sitios

El ejemplo siguiente añade una zona de transporte universal NSX a las topologías de gestión básica y de carga de trabajo que se tratan en las secciones anteriores, además de las siguientes características:

* La zona de transporte universal abarca dos {{site.data.keyword.CloudDataCents_notm}} o POD dentro de un {{site.data.keyword.CloudDataCent_notm}}.
* Después de añadir la zona de transporte, se añaden varias VXLAN junto con un direccionador distribuido Universal que abarca las nuevas VXLAN.
* Debe configurar enlaces ascendentes en los ESG de carga de trabajo en ambos sitios. Esta configuración permite que las máquinas virtuales (VM) en el sitio local crucen a su ESG local.
* Para el tráfico de entrada, se necesita un equilibrador de carga global. Consulte las ofertas globales de equilibrio de carga de {{site.data.keyword.cloud_notm}} para cumplir con este requisito.
* Este ejemplo requiere la edición VMware NSX Enterprise Edition.

Figura 1. Topología de varios sitios

![Tipología multisitio](multisite_topology.svg "Topología multisitio")

### Enlaces relacionados

* [Servicios de red en {{site.data.keyword.cloud_notm}}](networking_services.html)