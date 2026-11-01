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

Además, se ejecutó una búsqueda semántica dirigida por una descripción equivalente a la ecuación. La búsqueda profunda finalizó el 31 de octubre de 2026 y recuperó 116 registros relevantes. El resumen de la búsqueda se basa en abstracts y metadatos; no implica lectura del texto completo de todos los artículos.

## Criterios de filtrado
- **Alta pertinencia:** modela explícitamente comportamiento dinámico, adaptación, autoscaling, scheduling, reconfiguración en runtime o una extensión UML aplicada a cloud/contenedores.
- **Pertinencia media:** aporta perfiles UML, modelos de despliegue cloud, Docker/Kubernetes o transformación entre modelos, pero no demuestra mapeo dinámico en ejecución.
- **Antecedente conceptual:** aborda despliegue dinámico o reconfiguración, pero no corresponde directamente a UML + orquestación moderna de contenedores.

## Hallazgos de la búsqueda profunda
La búsqueda recuperó 116 registros. El resultado principal de Undermind señala que las extensiones UML para cloud se enfocan principalmente en describir y aprovisionar topologías; el modelado explícito de la reasignación dinámica de componentes en contenedores/Kubernetes parece escaso. El antecedente más directo en la intersección UML + orquestación es [Moh25], basado en UML-RT y adaptación dinámica, aunque el abstract no aclara si formaliza colocación o reubicación de componentes. También apareció [Kan14], que plantea escalar clústeres añadiendo y retirando nodos a partir de reglas de diagramas de despliegue, pero en un contexto PaaS genérico y con información bibliográfica limitada.\n\nOtros resultados próximos son [Bet20] (reubicación dinámica de servicios contenerizados entre dispositivos edge), [Pet20] (modelado semántico y optimización para adaptación de aplicaciones contenerizadas en Fog), [Ach19] (CAMEL y models@runtime para aprovisionamiento adaptativo), [Pri17] y [Zun15] (reconfiguración dinámica e incremental de arquitecturas cloud), y [Pie22] (notación visual para Docker Compose, centrada en autoría de configuración y no en rescheduling runtime).\n\nPor tanto, no conviene afirmar una ausencia absoluta de métodos. La brecha más precisa es la posible falta de una representación UML de despliegue que modele explícitamente el estado temporal y las transiciones de la asignación software–contenedor–nodo bajo eventos de elasticidad y orquestación; esta hipótesis debe validarse con lectura completa y comparación sistemática.

## Índice de artículos
- [Ach19](Ach19-camel-models-at-runtime.md) — CAMEL y models@runtime para aprovisionamiento adaptativo multi-cloud. **Alta para modelos en runtime; no UML.**\n- [Pri17](Pri17-diary-reconfiguracion-cloud.md) — método DIARy para reconfiguración dinámica e incremental de servicios cloud. **Alta para reconfiguración; no UML.**\n- [Sca16](Sca16-runtime-adaptable-cloud-redeployment.md) — adaptación y redespliegue cloud en runtime mediante grafos y TOSCA. **Alta para dinámica; no UML.**\n- [Bet20](Bet20-dynamic-container-edge-reallocation.md) — reasignación dinámica de servicios entre dispositivos edge en sistemas contenerizados. **Alta para dinámica; no UML.**\n- [Kan14](Kan14-deployment-diagrams-cluster-autoscaling.md) — escalado de clúster mediante reglas de diagramas de despliegue. **Alta para diagramas + elasticidad; requiere verificación.**\n- [Pet20](Pet20-smada-fog-container-adaptivity.md) — modelos semánticos, optimización y adaptación de aplicaciones contenerizadas en Fog. **Alta para dinámica; no UML.**\n- [Moh25](Moh25-umlrt-adaptive-cloud-kubernetes.md) — UML-RT + orquestación de contenedores y adaptación dinámica. **Alta pertinencia.**
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
- [Nay23](Nay23-container-orchestration-mapping-study.md) — estudio de mapeo de arquitecturas, modelos y métodos de orquestación. **Útil para ampliar antecedentes y brechas.**\n- [Pie22](https://doi.org/10.1007/s10270-022-01027-8) — notación visual para Docker Compose, evaluada empíricamente. **Complementaria; no modela scheduling dinámico.**\n- [Kim19](https://doi.org/10.3390/APP9010191) — orquestación federada Kubernetes basada en topologías TOSCA y autoscaling. **Complementaria.**\n- [Zun15](https://www.semanticscholar.org/paper/6f49e64c94105abffc68befb32476276375e49b4) — enfoque dirigido por modelos para reconfiguración dinámica de arquitecturas cloud. **Antecedente conceptual.**\n- [Ber19](https://doi.org/10.1007/s11227-019-02980-w) — perfiles UML y transformaciones M2T para arquitecturas cloud; abstract no disponible. **Pendiente de texto completo.**

## Precauciones de interpretación
1. Un perfil UML para cloud no implica que el modelo represente cambios en runtime.
2. El escalado de contenedores no equivale automáticamente a reasignar componentes de software entre recursos.
3. Docker y Kubernetes son tecnologías diferentes; no atribuir a Docker capacidades de scheduling que dependen del orquestador.
4. En los artículos sin PDF disponible, el resumen se basa en los metadatos y abstract recuperados por Undermind. No se afirma que se haya revisado el texto completo.
5. Los abstracts se conservan en inglés; los resúmenes analíticos están en español.

## Próximo paso recomendado
Completar la búsqueda profunda, leer los PDF de los estudios centrales que estén disponibles y construir una matriz comparativa de conceptos modelados: nodo, contenedor, componente, relación de hosting, evento, estado, escalado, scheduling, migración y reconfiguración.

## Profundización comparativa de los cinco estudios prioritarios

Se añadió el informe **[Profundización y matriz comparativa de cinco estudios centrales](profundizacion-comparativa-cinco-articulos.md)**. Incluye análisis individual de Moh25, Kan14, Bet20, Hag26 y Ber14; matriz comparativa; síntesis crítica; propuesta inicial de conceptos de metamodelo; preguntas de investigación y referencias primarias.

**Calidad de evidencia:** se leyeron los textos completos de Moh25, Kan14 y Ber14. Para Bet20 se dispone de abstract y metadatos; para Hag26 se dispone del abstract y de la página oficial ICSA 2026 que anuncia un preprint. Estos dos análisis quedan marcados como provisionales hasta revisar sus PDF.
