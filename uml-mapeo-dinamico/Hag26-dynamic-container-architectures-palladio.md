# [Hag26] Enhancing Decision-Making on Container Orchestration Using Simulation-Driven Modeling of Dynamic Architectures

- **Autores:** Nathan Hagel, Maximilian Hummel, Jörg Henß, Sebastian Weber, Thomas Weber, Ralf Reussner
- **Año:** 2026
- **Publicación:** 2026 IEEE 23rd International Conference on Software Architecture (ICSA), pp. 280–287
- **DOI:** https://doi.org/10.1109/ICSA66085.2026.00034
- **PDF en Undermind:** no disponible.

## Abstract original
> The deployment of modern containerized architectures depends on container orchestration tools, because their configuration critically influence performance, robustness, and cost. Container orchestration tools manage scaling, health checking, failure recovery, and resource distribution among containers. Configuration evaluation as well as suitability of container orchestration are nontrivial at design time, not to mention expensive. For informed decision-making in container architectures, modeling and simulation provide lightweight alternatives.In this paper, we present a novel approach to modeling and simulating dynamic container architectures. Implemented as an extension of the Palladio Component Model, our approach captures essential orchestration mechanisms such as autoscaling, container scheduling, and the configuration of requests and limits. Our qualitative evaluation uses two example applications and load scenarios. The results show that our approach closely simulates dynamic containerized architectures while enabling lightweight comparison between different configurations and traditional deployment techniques.

## Resumen analítico
Propone un enfoque de modelado y simulación de arquitecturas contenerizadas dinámicas como apoyo a decisiones de configuración de la orquestación. La extensión se implementa sobre Palladio Component Model y representa mecanismos como autoscaling, planificación de contenedores (scheduling) y configuración de requests y limits. La evaluación cualitativa utiliza dos aplicaciones de ejemplo y escenarios de carga para comparar configuraciones y técnicas de despliegue.

## Aporte para la investigación
Es especialmente importante para la dimensión dinámica del problema: identifica mecanismos concretos que un modelo debe poder representar (autoscaling, scheduling, límites y solicitudes de recursos). Puede ayudar a definir qué variables y eventos debería incluir un modelo de mapeo dinámico.

## Límite y distinción
No es una extensión UML según el abstract: extiende Palladio Component Model. Por ello no debe citarse como evidencia de una solución UML; sí como antecedente cercano de modelado de arquitecturas contenerizadas dinámicas y simulación de decisiones de orquestación.

## Pertinencia
**Alta para dinámica y orquestación; media para el objetivo UML estricto.** Es un trabajo reciente que conviene revisar en texto completo.
