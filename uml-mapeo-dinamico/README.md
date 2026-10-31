# Revisión de literatura: UML y mapeo dinámico en infraestructura contenerizada

## Objetivo
Identificar estudios que propongan extensiones de UML, perfiles, estereotipos o metodologías de diagramas de despliegue para modelar cloud, orquestación de contenedores, elasticidad y cambios de asignación de recursos en tiempo de ejecución.

## Estrategia de búsqueda ejecutada en Undermind
**Ecuación booleana suministrada:**
`("UML" OR "Unified Modeling Language" OR "deployment diagram*") AND ("extension*" OR "UML profile*" OR "stereotype*") AND ("orchestration" OR "Kubernetes" OR "K8s" OR "Docker" OR "container*" OR "dynamic infrastructure" OR "resource mapping")`

**Prompt natural suministrado:**
> Studies proposing formal UML extensions, UML profiles, or new deployment diagram methodologies adapted for cloud orchestration, containerized environments (Docker, Kubernetes), dynamic resource mapping, and elastic infrastructure behavior.

La búsqueda profunda quedó lanzada en Undermind y puede consultarse en:
[UML dinámico en infraestructura contenerizada](https://app.undermind.ai/projects/cda3ba9f-3f75-42ac-b898-80a26ad39226?path=/UML%20din%C3%A1mico%20en%20infraestructura%20contenerizada)

Además, se ejecutó una búsqueda semántica dirigida por una descripción equivalente a la ecuación. Esta primera entrega se basa en sus resultados disponibles; la búsqueda profunda estaba todavía en ejecución al momento de crear esta versión.

## Criterios de filtrado
- **Alta pertinencia:** modela explícitamente comportamiento dinámico, adaptación, autoscaling, scheduling, reconfiguración en runtime o una extensión UML aplicada a cloud/contenedores.
- **Pertinencia media:** aporta perfiles UML, modelos de despliegue cloud, Docker/Kubernetes o transformación entre modelos, pero no demuestra mapeo dinámico en ejecución.
- **Antecedente conceptual:** aborda despliegue dinámico o reconfiguración, pero no corresponde directamente a UML + orquestación moderna de contenedores.

## Hallazgo preliminar
La literatura encontrada no respalda todavía afirmar que existe una ausencia general de estándares o metodologías. Sí muestra una fragmentación de enfoques: perfiles/extensiones UML para cloud, modelos de despliegue como TOSCA, gestión de componentes sobre contenedores y modelos de simulación de arquitecturas dinámicas. La oportunidad investigable es estudiar cómo representar explícitamente la evolución temporal del mapeo software–recursos y cómo relacionarla con modelos de despliegue existentes.

## Índice de artículos
- [Moh25](Moh25-umlrt-adaptive-cloud-kubernetes.md) — UML-RT + orquestación de contenedores y adaptación dinámica. **Alta pertinencia.**
- [Hag26](Hag26-dynamic-container-architectures-palladio.md) — autoscaling, scheduling y simulación de arquitecturas contenerizadas. **Alta pertinencia temática; no es UML.**
- [Ber14](Ber14-caml-uml-cloud-modeling.md) — CAML, bibliotecas y perfiles UML para despliegue cloud. **Pertinencia media.**
- [Riv18](Riv18-urano-uml-automated-deployment.md) — perfil UML para automatizar instalación, configuración y actualización. **Pertinencia media.**
- [Par16](Par16-model-driven-docker-management.md) — modelado y gestión de contenedores Docker. **Pertinencia media-alta; no se describe como perfil UML.**
- [Bog20](Bog20-component-aware-orchestration-tosca-docker-kubernetes.md) — TOSCA, Docker y Kubernetes con gestión de componentes independiente del contenedor. **Pertinencia alta como antecedente de modelado; no hace remapeo dinámico.**
- [Mil11](Mil11-umodd-dynamic-deployment.md) — modelo unificado de despliegue y gestión de arquitecturas distribuidas dinámicas. **Antecedente conceptual.**
- [Mat04](Mat04-runtime-reconfiguration-component-architectures.md) — arquitectura y reconfiguración en runtime. **Antecedente conceptual.**
- [Gui13](Gui13-uml-profile-multicloud.md) — perfil UML para aplicaciones multicloud. **Pertinencia media.**
- [Kam14](Kam14-ucc-uml-cloud-profile.md) — perfil UML para cloud mediante estereotipos y valores etiquetados. **Pertinencia media.**
- [Ber16](Ber16-caml2tosca-uml-tosca.md) — transformación de modelos UML/CAML a TOSCA. **Pertinencia media.**
- [Bor20](Bor20-tosca-kubernetes.md) — adaptación de TOSCA a Kubernetes. **Pertinencia media.**
- [Wur20](Wur20-tosca-light-deployment.md) — TOSCA Light y transformación a tecnologías de despliegue. **Pertinencia complementaria.**
- [Nay23](Nay23-container-orchestration-mapping-study.md) — estudio de mapeo de arquitecturas, modelos y métodos de orquestación. **Útil para ampliar antecedentes y brechas.**

## Precauciones de interpretación
1. Un perfil UML para cloud no implica que el modelo represente cambios en runtime.
2. El escalado de contenedores no equivale automáticamente a reasignar componentes de software entre recursos.
3. Docker y Kubernetes son tecnologías diferentes; no atribuir a Docker capacidades de scheduling que dependen del orquestador.
4. En los artículos sin PDF disponible, el resumen se basa en los metadatos y abstract recuperados por Undermind. No se afirma que se haya revisado el texto completo.
5. Los abstracts se conservan en inglés; los resúmenes analíticos están en español.

## Próximo paso recomendado
Completar la búsqueda profunda, leer los PDF de los estudios centrales que estén disponibles y construir una matriz comparativa de conceptos modelados: nodo, contenedor, componente, relación de hosting, evento, estado, escalado, scheduling, migración y reconfiguración.
