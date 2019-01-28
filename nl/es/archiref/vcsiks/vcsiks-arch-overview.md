---

copyright:

  years:  2016, 2018

lastupdated: "2018-11-16"

---

# Visión general de la arquitectura
Las ofertas de {{site.data.keyword.vmwaresolutions_full}} proporcionan la automatización para desplegar componentes de tecnología VMware en {{site.data.keyword.CloudDataCents_notm}} en todo el mundo. La arquitectura consta de una sola región de nube y permite la ampliación a más regiones de nube ubicadas en otra geografía y/o en otro pod de {{site.data.keyword.cloud_notm}} dentro del mismo centro de datos.

Puede desplegar manualmente los productos {{site.data.keyword.cloud_notm}} Private (ICP) y Cloud Automation Manager (CAM) en la plataforma de virtualización local, lo que permite gestionar la nube desde ubicaciones locales. Como alternativa, ICP y CAM se ofrecen como extensiones de servicio de un despliegue de vCenter Server on {{site.data.keyword.cloud_notm}} nuevo o existente, mediante automatización, lo que permite gestionar la nube desde {{site.data.keyword.cloud_notm}}.

ICP es una plataforma de aplicaciones para desarrollar y gestionar aplicaciones de contenedor locales. ICP es un entorno integrado para gestionar contenedores que incluye el coordinador de contenedores Kubernetes,
un repositorio de imágenes privadas, una consola de gestión e infraestructuras de supervisión.

IBM Multi-Cluster Manager proporciona visibilidad de usuario, gestión centrada en aplicaciones (política, despliegues, estado, operaciones) y conformidad basada en políticas entre nubes y clústeres. Con IBM Multi-Cluster Manager, tiene el control sobre los clústeres de Kubernetes. Se asegura de que sus clústeres sean seguros, que funcionen de forma eficiente y que proporcionen los niveles de servicio que esperan las aplicaciones.

{{site.data.keyword.cloud_notm}} Automation Manager es una plataforma de gestión de autoservicio multinube que se ejecuta en {{site.data.keyword.cloud_notm}} Private que ayuda a los desarrolladores y a los administradores a satisfacer las necesidades de la empresa. Cloud Automation Manager Service Composer le permite exponer los servicios de nube híbrida en el catálogo de IBM Cloud Private.

## Plataforma de gestión de nube desde IBM Cloud

En el diagrama siguiente se muestra ICP y CAM desplegados con la infraestructura de {{site.data.keyword.cloud_notm}}, con conexiones con el vCenter local e IBM Kubernetes Service (IKS) desplegado en {{site.data.keyword.cloud_notm}}. Los usuarios pueden desplegar máquinas virtuales (VM) locales y VM en instancias de vCenter Server y contenedores en el clúster ICP e IKS.

Figura 1. Gestión de la nube desde la nube
![Gestión de la nube en la nube](vcsiks-oncloud-cloudmgt.svg)

En el diagrama, CAM crea de forma lógica conexiones en la nube con los entornos de vCenters, proveedores de nube, ICP e IKS. Los clústeres de ICP deben desplegarse en cada entorno de centro de datos o de nube, y MCM proporciona el mecanismo para conectar los clústeres de ICP en una única vista de gestión.

ICP se puede desplegar con los componentes NSX-V o NSX-T. ICP con NSX-V permite ejecutar VM ICP en la red VXLAN y utilizar el sistema de red interno de Calico de Kubernetes.

ICP con NSX-T permite a los usuarios controlar y configurar el sistema de red, de subred y las políticas desde la interfaz de usuario central (NSX-T Manager). Para obtener información sobre las diferencias entre NSX-V y NSX-T, consulte la [arquitectura de referencia de red VCS de {{site.data.keyword.cloud_notm}}](../vcsnsxt/vcsnsxt-intro.html).

## Plataforma de gestión de nube local

En el diagrama siguiente se muestra ICP y CAM desplegados en la infraestructura local, con conexiones con vCenter e IKS desplegadas en {{site.data.keyword.cloud_notm}}. Los usuarios pueden desplegar las VM y los contenedores locales, las VM en las instancias de vCenter Server y los contenedores en el clúster IKS.

Figura 2. Gestión de nube desde el entorno local
![Gestión de nube desde el entorno local](vcsiks-onprem-cloudmgt.svg)

Se utiliza strongSwan VPN para establecer la conectividad con los contenedores IKS desplegados. strongSwan se podría sustituir por la conectividad Direct-link.

En el diagrama, CAM crea de forma lógica conexiones en la nube con los entornos de vCenters, proveedores de nube, ICP e IKS. Los clústeres de ICP deben desplegarse en cada entorno de centro de datos o de nube, y MCM proporciona el mecanismo para conectar los clústeres de ICP en una única vista de gestión.

### Enlaces relacionados

* [Visión general de vCenter Server on {{site.data.keyword.cloud_notm}} con el paquete híbrido (Hybridity)](../vcs/vcs-hybridity-intro.html)