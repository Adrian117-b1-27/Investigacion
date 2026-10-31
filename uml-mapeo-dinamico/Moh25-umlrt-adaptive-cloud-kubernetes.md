# [Moh25] Towards the Model-Driven Development of Adaptive Cloud Applications by Leveraging UML-RT and Container Orchestration

- **Autores:** Mufasir Muthaher Mohammed, Karim Jahed, Jürgen Dingel, David J. Lamb
- **Año:** 2025
- **Publicación:** International Conference on Model-Driven Engineering and Software Development, pp. 52–63
- **DOI:** https://doi.org/10.5220/0013148000003896
- **Disponibilidad de PDF en Undermind:** no disponible en la consulta.

## Abstract original
> Containers are self-contained units of code that can be executed in various computing environments. Container orchestration tools such as Kubernetes (K8s) assist in deploying, scaling, and managing containers, permitting alterations to the execution platform (environment) at runtime. Container orchestration and model-driven engineering (MDE) both offer concepts, techniques, and tools that facilitate the realization of self-adaptation capabilities. Yet, their joint use for the design, implementation, and maintenance of adaptive cloud applications appears to be underexplored. This paper presents the results of our investigation of how container orchestration can complement an extension of existing MDE techniques (based on UML-RT, a UML 2 profile) for the effective design, implementation, and maintenance of adaptive cloud applications. We will describe an approach and toolchain for automatically generating and deploying a fully containerized distributed application from a UML-RT model and leveraging both model-and platform-level dynamic adaptation and failure recovery capabilities to allow the application to respond to runtime changes to the requirements or failures. The application of the approach with the help of a prototype implementation of our toolchain to an exemplar is described. The evaluation results show the feasibility and effectiveness of the approach.

## Resumen analítico
El trabajo investiga cómo combinar ingeniería dirigida por modelos (MDE), basada en UML-RT —un perfil de UML 2—, con herramientas de orquestación de contenedores para desarrollar aplicaciones cloud adaptativas. Propone un enfoque y una cadena de herramientas que generan y despliegan automáticamente una aplicación distribuida y contenerizada a partir de un modelo UML-RT. La solución contempla adaptación dinámica tanto a nivel del modelo como de la plataforma, además de recuperación ante fallos, para responder a cambios de requisitos o fallos durante la ejecución. Los autores describen un prototipo y lo aplican a un ejemplo para evaluar la viabilidad y efectividad del enfoque.

## Aporte para la investigación
Es el resultado más directamente alineado con la intersección UML + orquestación + adaptación en runtime. Puede servir como antecedente principal para estudiar cómo extender modelos UML-RT y conectar el modelo con el ciclo de despliegue y adaptación de una aplicación contenerizada.

## Lo que el abstract permite afirmar
- Usa UML-RT, identificado como perfil de UML 2.
- Genera y despliega una aplicación distribuida contenerizada desde un modelo.
- Combina adaptación dinámica a nivel de modelo y plataforma.
- Considera recuperación ante fallos y cambios de requisitos en runtime.
- Describe un prototipo y una evaluación con un ejemplo.

## Lo que falta verificar en el texto completo
El abstract no especifica qué elementos concretos del perfil representan nodos, contenedores, recursos, eventos de reubicación o relaciones de asignación. Tampoco permite concluir si implementa migración o remapeo dinámico de componentes, ni cómo se toman esas decisiones. Estas cuestiones deben comprobarse en el PDF antes de atribuirle ese alcance.

## Pertinencia
**Alta.** Prioridad alta para conseguir y leer el texto completo.
