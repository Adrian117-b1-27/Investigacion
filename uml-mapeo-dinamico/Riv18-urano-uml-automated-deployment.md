# [Riv18] UML-driven automated software deployment

- **Autores:** Luis F. Rivera, Norha M. Villegas, Gabriel Tamura, Miguel A. Jiménez, Hausi A. Müller
- **Año:** 2018
- **Publicación:** Conference of the Centre for Advanced Studies on Collaborative Research, pp. 257–268
- **DOI:** no localizado por Undermind. [Registro bibliográfico](https://www.semanticscholar.org/paper/e006c77570a857ba39f85c3376a56e8846a2263e)
- **PDF en Undermind:** no disponible.

## Abstract original
> Software companies face the challenge of ensuring customer satisfaction through the continuous delivery of functionalities and rapid response to quality issues. However, achieving frequent software delivery is not a trivial task. It requires agile---and continuous---design, development and deployment of existing and new software features. Over time, managing these systems becomes increasingly complex. This complexity stems, in part, from the deployment pipelines and the myriad possible configurations of the software components. Furthermore, software deployment is a time-consuming and error-prone process, which, even when automated, can lead to configuration errors and cost overruns. In this paper, we address deployment challenges that developers face during continuous delivery and DevOps. Our proposal consists of Urano, a mechanism for automating the deployment process, which uses UML, an interoperable and de facto modeling standard, as a means of specifying a software architecture and its associated deployment. Our approach is based on the model-driven architecture principles to generate executable deployment specifications from user-defined UML deployment diagrams. We extend this kind of diagrams by defining and applying a UML profile that captures the semantics and requirements of the installation, configuration, and update of software components. Thus, enabling more expressive deployment specifications and their automatic realization. To evaluate Urano, we conducted three case studies that demonstrate its potential to effectively automate software deployment processes in industry.

## Resumen analítico
Propone Urano, un mecanismo de automatización del despliegue basado en modelos UML. El usuario define diagramas UML de despliegue y un perfil UML amplía su expresividad para capturar requisitos y semántica de instalación, configuración y actualización de componentes. A partir de esos modelos se generan especificaciones de despliegue ejecutables. El enfoque se evalúa mediante tres estudios de caso industriales.

## Aporte para la investigación
Es relevante para convertir un diagrama UML en una especificación operativa y para modelar operaciones del ciclo de vida de componentes. Puede inspirar la representación de eventos o acciones de actualización en una metodología de despliegue.

## Límite
El abstract no describe cambios dinámicos en la asignación de componentes a nodos o recursos, ni Kubernetes/Docker como contexto central. Automatizar instalación, configuración y actualización no equivale por sí mismo a modelar autoscaling o remapeo runtime.

## Pertinencia
**Media.** Útil para el mecanismo de extensión UML y automatización, pero no resuelve el problema dinámico planteado.
