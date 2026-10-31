# [Bor20] Adaptation of the TOSCA standard model for the Kubernetes container environment

- **Autores:** A. Borisova, Valeriya Shvetcova, O. Borisenko
- **Año:** 2020
- **Publicación:** 2020 Ivannikov Memorial Workshop (IVMEM), pp. 9–14
- **DOI:** https://doi.org/10.1109/IVMEM51402.2020.00008
- **PDF en Undermind:** no disponible.

## Abstract original
> The main difference between container-based and virtualization-based cloud environments is the way of the virtualization methods for OS and auxiliary resources. Software applications can be both deployed in a cloud on virtual machines or in local data centres on physical machines. Containers are based on OS-level virtualization. To deal with the growth of various, but functionally similar cloud environments, the TOSCA [1] (Topology and Orchestration for Cloud Applications) standard was created. It allows to describe deployment resources in a TOSCA Domain-specific language that does not depend on the provider. Kubernetes [8] is an open-source system for deployment automation, scaling, and management of containerized applications. TOSCA standard was created to describe cloud applications, but the model may be suitable for describing container applications that Kubernetes orchestrate. This paper considers Kubernetes as a cloud provider and examines the applicability of the TOSCA standard for unifying deployment and orchestration not only of resources provided by virtualization-based clouds but also of containerized ones.

## Resumen analítico
Estudia la aplicabilidad de TOSCA para describir aplicaciones contenerizadas que son orquestadas por Kubernetes. Parte de la diferencia entre virtualización basada en máquinas virtuales y contenedores, y plantea tratar Kubernetes como proveedor cloud dentro de una descripción de despliegue independiente del proveedor. El objetivo es unificar la descripción y orquestación de recursos de cloud virtualizado y entornos contenerizados.

## Aporte para la investigación
Ayuda a entender cómo un modelo de topología y orquestación puede abarcar recursos contenerizados de Kubernetes. Puede complementar perfiles UML si se plantea una transformación entre modelos UML y TOSCA/Kubernetes.

## Límite
No es un perfil UML; su foco es adaptar TOSCA. El abstract no indica que describa la evolución del mapeo en runtime.

## Pertinencia
**Media.** Útil para la dimensión TOSCA–Kubernetes, no como evidencia de extensión UML.
