# [Par16] Model-Driven Management of Docker Containers

- **Autores:** Fawaz Paraiso, Stéphanie Challita, Yahya Al-Dhuraibi, Philippe Merle
- **Año:** 2016
- **Publicación:** 2016 IEEE 9th International Conference on Cloud Computing (CLOUD), pp. 718–725
- **DOI:** https://doi.org/10.1109/CLOUD.2016.0100
- **PDF en Undermind:** no disponible en la consulta.

## Abstract original
> With the emergence of Docker, it becomes easier to encapsulate applications and their dependencies into lightweight Linux containers and make them available to the world by deploying them in the cloud. Compared to hypervisor-based virtualization approaches, the use of containers provides faster start-ups times and reduces the consumption of computer resources. However, Docker lacks of deployability verification tool for containers at design time. Currently, the only way to be sure that the designed containers will execute well is to test them in a running system. If errors occur, a correction is made but this operation can be repeated several times before the deployment becomes operational. Docker does not provide a solution to increase or decrease the size of container resources in demand. Besides the deployment of containers, Docker lacks of synchronization between the designed containers and those deployed. Moreover, container management with Docker is done at low level, and therefore requires users to focus on low level system issues. In this paper we focus on these issues related to the management of Docker containers. In particular, we propose an approach for modeling Docker containers. We provide tooling to ensure the deployability and the management of Docker containers. We illustrate our proposal using an event processing application and show how our solution provides a significantly better compromise between performance and development costs than the basic Docker container solution.

## Resumen analítico
El artículo aborda problemas de diseño y gestión de contenedores Docker: ausencia de verificación de desplegabilidad en diseño, falta de sincronización entre contenedores diseñados y desplegados, y gestión de bajo nivel. Propone un enfoque para modelar contenedores Docker y herramientas para comprobar su desplegabilidad y administrarlos. La propuesta se ilustra con una aplicación de procesamiento de eventos y se compara con el uso básico de Docker en términos de compromiso entre rendimiento y coste de desarrollo.

## Aporte para la investigación
Aporta un antecedente de modelado dirigido por modelos aplicado directamente a Docker. Puede ayudar a identificar qué información del contenedor debe describirse antes de desplegarlo y qué problemas aparecen al mantener sincronizados el modelo y la infraestructura desplegada.

## Límite
El abstract no identifica una extensión UML, un perfil o un mecanismo explícito de reasignación de recursos en runtime. Además, la afirmación sobre aumentar o disminuir recursos se formula como una limitación de Docker en el contexto del artículo de 2016; no debe extrapolarse a las capacidades actuales de plataformas de orquestación.

## Pertinencia
**Media-alta.** Relevante para modelado de contenedores y gestión, pero requiere comprobar el texto completo para conocer el formalismo utilizado.
