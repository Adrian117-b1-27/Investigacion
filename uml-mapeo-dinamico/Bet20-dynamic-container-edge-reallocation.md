# [Bet20] Model-based Development of a Dynamic Container-Based Edge Computing System

- **Autores:** Victor Pazmino Betancourt, Bo Liu, J. Becker
- **Año:** 2020
- **Publicación:** 2020 IEEE International Symposium on Systems Engineering (ISSE), pp. 1–5
- **DOI:** https://doi.org/10.1109/ISSE49799.2020.9272014
- **PDF en Undermind:** no disponible.

## Abstract original
> Edge computing can reduce the amount of transported data in an IoT system by bringing data processing closer to the data sources. In this context, service-oriented distributed systems and their availability become more relevant. During operation services can fail for various reasons, e.g. if a device is not available, loses connection or is attacked. Based on the service architecture, services can be reconfigured to different devices at runtime, which makes it possible to increase availability and scalability of the system. The use of container-based technologies for dynamic provisioning of services in the edge is promising for this purpose. The heterogeneity and diversity of devices not only brings new challenges in application design, but also requires serious efforts in the configuration, deployment and re-deployment of applications and their reallocation in edge environments. This is often a time-consuming, trial and error-prune process. In this paper, we propose a model-based development framework for dynamic edge computing systems in combination with containers and service orchestrator to support the engineering process of dynamic service-based systems. Our results show that a container-based edge computing system can be described with consideration of reallocation mechanisms and policies. This supports the developer during the implementation and deployment of the system by generating configurations. In this way, errors can be avoided and the development time can be reduced. Edge computing systems from different areas, could benefit from such a model-based process. As the process supports container-based systems, availability can be increased and development time can be reduced.

## Resumen analítico
Propone un marco de desarrollo basado en modelos para sistemas dinámicos de edge computing que combinan contenedores y un orquestador de servicios. El problema central es que los servicios pueden fallar por indisponibilidad o pérdida de conectividad de dispositivos, por lo que deben poder reconfigurarse y reasignarse a otros dispositivos durante la ejecución. El marco permite describir mecanismos y políticas de reasignación y generar configuraciones para apoyar la implementación y el despliegue.

## Aporte para la investigación
Es uno de los antecedentes más cercanos al concepto de mapeo dinámico: trata explícitamente la reubicación de servicios entre dispositivos en entornos edge contenerizados y contempla políticas de reasignación.

## Límite
No se identifica como perfil UML ni como extensión de diagramas de despliegue UML. Su valor es el modelado dinámico y la reasignación, no una solución UML demostrada.

## Pertinencia
**Alta para mapeo dinámico en contenedores; indirecta para UML.**
