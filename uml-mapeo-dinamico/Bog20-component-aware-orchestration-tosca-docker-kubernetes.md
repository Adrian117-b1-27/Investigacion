# [Bog20] Component-aware orchestration of cloud-based enterprise applications, from TOSCA to Docker and Kubernetes

- **Autores:** Matteo Bogo, J. Soldani, Davide Neri, Antonio Brogi
- **Año:** 2020
- **Publicación:** Software: Practice and Experience, pp. 1793–1821
- **DOI:** https://doi.org/10.1002/spe.2848
- **PDF:** disponible en Undermind; se realizó lectura del texto completo mediante el lector de PDF de Undermind.

## Abstract original
> Enterprise IT is currently facing the challenge of coordinating the management of complex, multicomponent applications across heterogeneous cloud platforms. Containers and container orchestrators provide a valuable solution to deploy multicomponent applications over cloud platforms, by coupling the lifecycle of each application component to that of its hosting container. We hereby propose a solution for going beyond such a coupling, based on the OASIS standard TOSCA and on Docker. We indeed propose a novel approach for deploying multicomponent applications on top of existing container orchestrators, which enables managing each component independently from the container used to run it. We also present prototype tools that implement our approach, and we show how we effectively exploited them to carry out a concrete case study.

## Resumen analítico basado en el texto completo
El artículo aborda el acoplamiento entre el ciclo de vida de un componente de software y el del contenedor que lo aloja. En los orquestadores, el contenedor suele ser la unidad gestionada; por tanto, iniciar o detener el contenedor afecta a los componentes que contiene. Los autores proponen una capa de gestión consciente de componentes, construida sobre TOSCA y Docker, que permite administrar componentes de software de forma independiente del ciclo de vida del contenedor.

La arquitectura incluye tres piezas: **TOSKOSE Unit**, instalada en contenedores que alojan componentes; **TOSKOSE Manager**, que recibe solicitudes de gestión y las reenvía a la unidad correspondiente; y **TOSKOSE Packager**, que transforma una descripción TOSCA y sus artefactos en imágenes y artefactos de despliegue Docker. El modelo distingue componentes, contenedores y volúmenes, y expresa relaciones como hosting, conexión, dependencia y montaje.

La solución se demuestra con la aplicación Thinking. Los autores generan el despliegue y lo ejecutan en Docker Swarm y Kubernetes. En el caso de estudio, dos componentes pueden compartir un contenedor y seguir gestionándose por separado. La gestión de contenedores permanece en el orquestador; las operaciones sobre componentes se envían al Manager y a las Units.

## Hallazgos y limitaciones del texto completo
El artículo demuestra gestión independiente del ciclo de vida de componentes dentro de contenedores y compatibilidad de la capa propuesta con Swarm y Kubernetes en los experimentos descritos. Sin embargo, **no propone un algoritmo para cambiar en runtime la asignación de componentes a contenedores o hosts**. La topología y el hosting se describen en el modelo usado para generar el despliegue. Los autores indican que el escalado y la autorrecuperación se basan en el orquestador y que el contenedor es la unidad mínima de escalado/autorreparación en su enfoque; el escalado y la autorrecuperación a nivel de componente quedan como trabajo futuro. También dejan para trabajo futuro automatizar los flujos de operaciones para alcanzar y mantener una configuración deseada.

## Aporte para la investigación
Muy útil para separar tres niveles que tu modelo podría necesitar distinguir: componente de software, contenedor que lo aloja y recurso/nodo donde el orquestador ejecuta el contenedor. También ayuda a formular una pregunta no resuelta por este artículo: cómo representar y registrar la evolución de las relaciones de hosting y ubicación cuando la infraestructura cambia.

## Pertinencia
**Alta como antecedente de modelado y orquestación; no es una solución de mapeo dinámico.** Esta clasificación se basa en el texto completo leído, no solo en el abstract.
