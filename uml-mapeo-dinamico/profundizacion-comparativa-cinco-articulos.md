# Profundización y matriz comparativa de cinco estudios centrales

**Proyecto:** Modelado de mapeo dinámico de recursos en infraestructuras contenerizadas.  
**Fecha:** 31 de octubre de 2026.  
**Artículos:** Moh25, Kan14, Bet20, Hag26 y Ber14.

## Nota metodológica y calidad de evidencia

Se revisaron los textos completos disponibles para Moh25, Kan14 y Ber14. Para Bet20 se recuperaron el abstract y los metadatos, pero no el PDF. Para Hag26 se consultó el abstract de la página oficial de ICSA 2026; la página anuncia un preprint adjunto, pero no se pudo leer ese archivo en esta revisión. Por ello, las conclusiones de Bet20 y Hag26 son provisionales y no deben confundirse con una lectura completa.

## 1. Profundización por artículo

### 1.1 Moh25 — UML-RT y orquestación de contenedores

**Referencia:** Mufasir Muthaher Mohammed, Karim Jahed, Jürgen Dingel y David J. Lamb (2025), “Towards the Model-Driven Development of Adaptive Cloud Applications by Leveraging UML-RT and Container Orchestration”, MODELSWARD 2025, pp. 52–63. DOI: [10.5220/0013148000003896](https://doi.org/10.5220/0013148000003896).  
**Texto completo:** [PDF SciTePress](https://www.scitepress.org/Papers/2025/131480/131480.pdf).

**Problema y objetivo.** El trabajo investiga cómo combinar ingeniería dirigida por modelos basada en UML-RT con orquestación de contenedores para desarrollar aplicaciones cloud distribuidas y adaptativas. Sus preguntas cubren generación y despliegue de aplicaciones contenerizadas desde modelos, recuperación ante fallos y adaptación a cambios de requisitos a nivel de modelo y plataforma.

**Lenguaje y conceptos.** UML-RT es un perfil de UML 2. Su unidad estructural es la cápsula, que representa un componente ejecutable; puertos y conectores representan interacciones, y máquinas de estados describen comportamiento. El trabajo no propone simplemente un diagrama de despliegue con nuevos estereotipos: reutiliza UML-RT y lo conecta con una cadena de herramientas para despliegue contenerizado.

**Mapeo y despliegue.** Las cápsulas se particionan en modelos independientes que pueden ejecutarse por separado en nodos distintos, manteniendo comunicación mediante cápsulas proxy. KubeRT genera código C++, scripts y especificaciones para Docker y Kubernetes. El flujo incluye Dockerfiles, YAML, imágenes de contenedor, registro de imágenes y despliegue en clúster local o cloud. Esto conecta unidades de software modeladas con unidades desplegables, aunque no formaliza todo el comportamiento interno del scheduler de Kubernetes como un metamodelo independiente.

**Dinámica y decisión.** Un Adaptation Manager centraliza la observación y las decisiones. Recoge información interna —latencia extremo a extremo, mensajes intercambiados y tamaño de carga— y externa —disponibilidad y uso de nodos, memoria y CPU—. Kubernetes Metrics Server entrega métricas externas y el manager puede enviar comandos al plano de control de Kubernetes. Las acciones incluyen cambiar parámetros, sustituir cápsulas o crear conectores. La adaptación se produce a nivel del modelo y de la plataforma.

**Recuperación ante fallos.** La transformación añade controladores, checkpointing, recuperación de estado, acknowledgements y retransmisión de mensajes. Kubernetes puede reiniciar contenedores fallidos y el mecanismo del artículo busca preservar la entrega y procesamiento de mensajes.

**Evaluación.** Se usan ejemplos Word Count, Sieve of Eratosthenes, Parcel Router y una simulación UAV. Los tiempos reportados de contenerización/despliegue son 78/11 s, 96/12 s, 342/24 s y 512/54 s, respectivamente. En una prueba se inyectaron 67 fallos y el mecanismo recuperó todos los componentes afectados; el tráfico terminó llegando a su destino. En la evaluación UAV, la disponibilidad de más recursos mejoró aproximadamente 50% algunas métricas y 15% el tiempo medio de decisión, dependiendo de la estrategia.

**Limitaciones reconocidas.** Los autores señalan retos en la adaptación de aplicaciones stateful, la replicación automática de componentes con estado, la toma de decisiones consciente de costes y la generalización a sistemas industriales. También reportan una sobrecarga de 3.2% en el procesamiento de mensajes en el caso medido.

**Lectura crítica.** Es el antecedente más directo para conectar UML-RT, Kubernetes y adaptación dinámica. No obstante, su foco es el desarrollo de aplicaciones adaptativas y su toolchain; no presenta como objetivo central una vista formal que conserve el historial de asignaciones componente→instancia de contenedor→nodo. Es una base para la parte UML y la conexión con el orquestador, no una solución completa de trazabilidad temporal del mapeo.

### 1.2 Kan14 — escalado de clúster mediante diagramas de despliegue

**Referencia:** Sudhir S. Kanade y Pushkaraj B. Thorat (2014), “Automated Scaling of Cluster Using Deployment Diagrams in Platform-As-A-Service”, International Journal of Innovative Research in Computer and Communication Engineering, vol. 2, issue 12, pp. 7342–7346. Identificador del artículo: 10.15680/ijircce.2014.0212055.  
**Texto completo:** [PDF IJIRCCE](https://www.rroij.com/open-access/automated-scaling-of-cluster-usingdeployment-diagrams-in-platformasaservice.pdf).

**Problema y objetivo.** Propone un mecanismo PaaS que utiliza diagramas de despliegue para describir la topología y reglas de un clúster. Al aumentar la demanda se crean nodos; al disminuir, se liberan y retornan al pool de recursos. El enfoque es event-driven y trata principalmente escalado horizontal.

**Representación.** El archivo de topología describe arquitectura de plataforma, multiplicidad de middleware, especificaciones de máquinas virtuales, roles y reglas para decidir cuándo desplegar o destruir recursos. El artículo denomina a esto deployment diagram grammar, pero no desarrolla un perfil UML formal con metamodelo detallado, estereotipos tipados y restricciones comparables a una especificación formal. Es más prudente describirlo como un enfoque basado en diagramas de despliegue y gramática de topología.

**Arquitectura.** Consta de Deployment Engine, Monitoring/Managing Framework (MMF), interfaz web y agentes de monitorización. El Deployment Engine instala imágenes de VM, configura red, instala agentes y middleware. El MMF lee la topología y construye una definición base de plataforma con reglas. Los agentes reportan salud y carga.

**Reglas y cambios.** Cuando la carga sube, el MMF solicita scale-out del rol correspondiente; cuando baja, solicita scale-in. El algoritmo addNode obtiene una IP libre, selecciona un host preferido, prepara y ejecuta scripts, espera a que arranque la VM, configura middleware y notifica a roles dependientes. El algoritmo removeMachine notifica a dependencias, desconfigura la VM y detiene middleware.

**Evaluación.** En un entorno de laboratorio, los autores reportan que se podía incorporar aproximadamente un nodo por minuto. Para una carga de 1000 solicitudes/min y capacidad de 100 solicitudes por nodo, describen escalado hacia arriba O(n) y hacia abajo O(1). Son resultados del laboratorio de 2014, no garantías para orquestadores actuales.

**Limitaciones.** No utiliza explícitamente Pods, Docker o Kubernetes. La representación se orienta a roles, VM y middleware. No se formaliza el historial temporal de cada instancia ni una migración de servicio ya desplegado entre nodos. La gramática, umbrales, histéresis y políticas anti-oscilación no quedan completamente especificados. Los autores reconocen margen de mejora en predicción de patrones de carga.

**Lectura crítica.** Es relevante porque el diagrama no es solo documentación: funciona como entrada para una gestión de infraestructura guiada por reglas. La propuesta actual podría conservar la separación entre topología base y reglas de operación, pero precisar formalmente eventos, transiciones, dependencias y estado real observado.

### 1.3 Bet20 — reasignación dinámica en edge contenerizado

**Referencia:** Victor Pazmino Betancourt, Bo Liu y Jürgen Becker (2020), “Model-based Development of a Dynamic Container-Based Edge Computing System”, 2020 IEEE International Symposium on Systems Engineering, pp. 1–5. DOI: [10.1109/ISSE49799.2020.9272014](https://doi.org/10.1109/ISSE49799.2020.9272014).  
**Fuentes:** [registro KIT](https://www.itiv.kit.edu/english/21_53.php) y abstract recuperado por Undermind. PDF no disponible en la consulta.

**Problema y objetivo.** Aborda aplicaciones edge con dispositivos heterogéneos. Los servicios pueden fallar por indisponibilidad de un dispositivo, pérdida de conectividad o ataques. El trabajo propone un marco de desarrollo basado en modelos que combina contenedores y un orquestador de servicios para describir mecanismos y políticas de reasignación.

**Lo confirmado por el abstract.** El sistema es distribuido y orientado a servicios; utiliza servicios contenerizados y un orquestador; permite reconfigurar servicios hacia dispositivos diferentes durante la ejecución; contempla mecanismos y políticas de reasignación; y genera configuraciones para apoyar implementación y despliegue.

**Mapeo dinámico.** El aporte más relevante parece ser la reasignación de un servicio hacia otro dispositivo edge. Esto debe distinguirse de autoscaling: aumentar réplicas no es lo mismo que mover o volver a desplegar un servicio en otro nodo. Sin el texto completo no es posible afirmar qué metamodelo usa, cómo tipa servicios y dispositivos, cómo expresa las políticas, si mueve una instancia o crea otra, qué orquestador utiliza ni cómo evalúa los resultados.

**Lectura crítica.** Es el antecedente más claro de los cinco para la dimensión de reallocation entre dispositivos, pero no se ha demostrado que sea una extensión UML. No se debe atribuirle Kubernetes solo porque el abstract menciona un orquestador. La ficha queda provisional hasta obtener el PDF.

**Pendiente prioritario.** Extraer del texto completo metamodelo, relación servicio→dispositivo, algoritmo de reasignación, políticas, disparadores, infraestructura y resultados experimentales.

### 1.4 Hag26 — simulación de arquitecturas contenerizadas dinámicas

**Referencia:** Nathan Hagel, Maximilian Hummel, Jörg Henß, Sebastian Weber, Thomas Weber y Ralf Reussner (2026), “Enhancing Decision-Making on Container Orchestration Using Simulation-Driven Modeling of Dynamic Architectures”, IEEE International Conference on Software Architecture (ICSA 2026), pp. 280–287. DOI: [10.1109/ICSA66085.2026.00034](https://doi.org/10.1109/ICSA66085.2026.00034).  
**Fuente:** [página oficial ICSA 2026](https://conf.researchr.org/details/icsa-2026/icsa-2026-papers/28/Enhancing-Decision-Making-on-Container-Orchestration-Using-Simulation-Driven-Modeling). La página anuncia un preprint adjunto; el PDF no se leyó en esta revisión.

**Problema y objetivo.** La configuración de la orquestación afecta rendimiento, robustez y coste. Evaluar experimentalmente configuraciones puede ser costoso. El artículo propone modelado y simulación como alternativas ligeras para comparar arquitecturas contenerizadas dinámicas antes del despliegue.

**Base de modelado.** Se implementa como extensión de Palladio Component Model (PCM), no UML. Esta diferencia es importante para no presentarlo como evidencia de un perfil UML existente.

**Mecanismos explícitos en el abstract.** Autoscaling, container allocation scheduling y configuración de requests y limits. Son dimensiones distintas: número de instancias, ubicación de instancias y requerimientos/límites de recursos.

**Evaluación reportada.** Evaluación cualitativa con dos aplicaciones y escenarios de carga. Los autores indican que el enfoque simula de cerca arquitecturas contenerizadas dinámicas y permite comparar configuraciones con técnicas de despliegue tradicionales. El abstract no da el algoritmo de scheduling, precisión cuantitativa ni detalle de métricas.

**Lectura crítica.** Es una referencia valiosa para definir variables y mecanismos que debería contemplar un modelo de recursos dinámicos y para considerar simulación como estrategia de evaluación. No demuestra una solución UML ni, con la información disponible, una sincronización del modelo con cada evento real del orquestador. Se requiere el preprint para identificar metaclases, relaciones, semántica temporal, algoritmos y resultados.

### 1.5 Ber14 — CAML, bibliotecas, perfiles y plantillas UML

**Referencia:** Alexander Bergmayr, Javier Troya, Patrick Neubauer, Manuel Wimmer y Gerti Kappel (2014), “UML-based Cloud Application Modeling with Libraries, Profiles, and Templates”, CloudMDE@MoDELS 2014, pp. 56–65.  
**Texto completo:** [PDF institucional Universidad de Sevilla](https://idus.us.es/bitstreams/e965afa5-0d94-40db-b3a5-8c6fd080f5be/download).

**Problema y objetivo.** UML representa software, plataformas e infraestructura, pero su lenguaje genérico de despliegue no expresa suficientemente las ofertas cloud de proveedores. CAML (Cloud Application Modeling Language) amplía UML para expresar topologías cloud y refinarlas con ofertas concretas.

**Estructura de CAML.** Combina una model library para topologías, UML profiles y stereotypes para conectar modelos con ofertas de proveedores, y UML templates para blueprints reutilizables. Incluye conceptos como CloudNode, CloudStorage, CloudService, CloudConfiguration, middleware y contenedores/entornos de ejecución. Las propiedades pueden describir CPU, memoria, disco, sistema operativo, middleware, región, zona de disponibilidad, coste y estrategia de escalado.

**Mapeo.** Los artefactos/componentes se conectan mediante la relación «deploy» con CloudNodes, y los nodos se refinan con estereotipos de proveedores. El artículo separa modelos independientes del proveedor de modelos específicos (PIM/PSM). El ejemplo de AWS incluye dos nodos, balanceo de carga, grupo de autoescalado, almacenamiento replicado y zonas de disponibilidad diferentes. Los autores desarrollaron diez plantillas de despliegue reutilizables.

**Elasticidad.** CAML incluye propiedades de escalabilidad y configuración de autoescalado, como número mínimo de instancias y ajuste. Sin embargo, el objetivo principal es describir topologías y configuraciones de despliegue, no formalizar el ciclo temporal de asignación y reasignación. El propio artículo indica que conceptos para optimización de despliegue y reglas de elasticidad no quedan completamente capturados por CAML.

**Interoperabilidad.** Presenta un mapeo conceptual inicial entre CAML y un subconjunto de TOSCA, de modo que topologías y relaciones UML pueden traducirse a templates/types y descriptores de aprovisionamiento.

**Lectura crítica.** Es la base más útil para estructurar el lado UML del metamodelo: componentes, artefactos, nodos, almacenamiento, ofertas cloud, atributos de recursos y relación deploy. La contribución potencial del proyecto sería añadir una capa temporal y operacional que represente cambios observados de asignación, no simplemente repetir la topología estática.

## 2. Matriz comparativa

| Dimensión | Moh25 | Kan14 | Bet20 | Hag26 | Ber14 |
|---|---|---|---|---|---|
| Enfoque | Aplicaciones cloud adaptativas | Escalado de clúster PaaS | Reasignación de servicios edge | Simulación de arquitectura contenerizada | Topologías cloud UML |
| Lenguaje/base | UML-RT + KubeRT | Diagramas de despliegue/gramática | Model-based framework (detalle no disponible) | Palladio Component Model | CAML, extensión interna UML |
| ¿UML? | Sí, UML-RT | Diagramas de despliegue; perfil formal no demostrado | No demostrado | No; PCM | Sí |
| Unidad lógica | Cápsula/partición | Rol/componente/middleware | Servicio | Aplicación y contenedor | Componente/artefacto |
| Unidad ejecutable | Contenedor en nodo/clúster | VM/nodo | Contenedor/servicio en dispositivo | Contenedor (detalle pendiente) | CloudNode, middleware, almacenamiento |
| Relación de asignación | Partición y despliegue de cápsulas | Roles/middleware sobre VM | Servicio reasignado a otro dispositivo | Container allocation scheduling | Relación UML «deploy» |
| Recursos | CPU, memoria, nodos y métricas | Especificación de VM y topología | Dispositivos heterogéneos; detalle pendiente | Requests y limits | CPU, memoria, disco, OS, región, zona, coste |
| Escalado | Adaptación de plataforma | Scale-out/scale-in | No confirmado | Autoscaling explícito | Propiedades y grupos de autoescalado |
| Scheduling | No modela el scheduler completo | Selección de host preferido | Política de reasignación, detalles pendientes | Scheduling explícito | No es el foco |
| Migración/reasignación | Adaptación de plataforma y recuperación; remapeo individual no central | Alta/baja de nodos, no migración de servicio | Reasignación de servicios en runtime | No confirmada en abstract | No formalizada como transición runtime |
| Eventos | Métricas, latencia, requisitos y fallos | Carga y salud | Fallo, desconexión, ataque | Escenarios de carga | Configuración del proveedor |
| Decisión | Adaptation Manager | MMF y reglas | Políticas de reasignación | Modelo y simulación | Estereotipos y configuración |
| Integración runtime | Kubernetes control plane y Metrics Server | Agentes, MMF, scripts y Deployment Engine | Orquestador no identificado | Simulación | Mapeo a TOSCA/aprovisionamiento |
| Evaluación | Prototipo, cuatro ejemplos, 67 fallos inducidos | Laboratorio, carga y escalado | No verificable con abstract | Dos aplicaciones, evaluación cualitativa | Petstore, perfiles y diez plantillas |
| Principal valor | Puente UML–Kubernetes y adaptación | Topología + reglas de escalado | Reasignación entre dispositivos | Autoscaling + scheduling + simulación | Estructura UML de topología cloud |
| Principal brecha | Historial de asignaciones no es el foco | Antigüedad y formalización limitada | Texto completo pendiente | Texto completo pendiente; no UML | No representa transiciones runtime completas |

## 3. Síntesis crítica

Los cinco trabajos no resuelven el mismo problema. Ber14 aborda la topología y el mapeo estructural en UML; Moh25 conecta un modelo UML-RT con generación, despliegue y adaptación en Kubernetes; Kan14 describe escalado de nodos guiado por una topología y reglas; Bet20 declara reasignación de servicios entre dispositivos edge; Hag26 modela y simula autoscaling y scheduling mediante PCM.

Es necesario distinguir:
- **Topología:** qué componentes, recursos y relaciones están definidos.
- **Escalado:** cuántas instancias existen.
- **Scheduling/placement:** en qué nodo se coloca una instancia.
- **Reasignación/migración:** cómo cambia la ubicación de una instancia o servicio ya desplegado.
- **Recuperación:** cómo se restablece la ejecución tras un fallo.

La oportunidad no es afirmar que “no existen métodos”. Los antecedentes cubren partes del problema. Una brecha candidata más precisa es:

> Falta por comprobar si existe una representación UML integrada y sincronizable con el estado operativo que modele a nivel de instancia la evolución temporal de las relaciones entre componente/servicio, contenedor/Pod y nodo, incluyendo eventos, políticas, decisiones de autoscaling y scheduling, reasignaciones, fallos y resultado observado en el orquestador.

Esta es una hipótesis, no una conclusión definitiva del estado del arte. Requiere ampliar la búsqueda y comparar también enfoques no UML, en particular Palladio, TOSCA y modelos@runtime.

## 4. Propuesta inicial de conceptos para un metamodelo

Los siguientes conceptos son una síntesis propia derivada de la comparación; no se atribuyen literalmente a ninguno de los artículos.

| Concepto propuesto | Función | Atributos o relaciones mínimas |
|---|---|---|
| SoftwareComponent | Componente lógico/servicio | id, versión, criticidad |
| DeployableArtifact | Artefacto o imagen desplegable | imagen, tag, digest |
| ContainerInstance | Instancia ejecutable | id, estado, réplica |
| PodOrExecutionUnit | Unidad gestionada por el orquestador | namespace, labels, requests, limits |
| ComputeNode | Nodo físico, virtual o edge | CPU, memoria, zona, estado |
| DeploymentBinding | Asignación válida en un intervalo | componente, instancia, nodo, inicio, fin |
| ResourceProfile | Requerimientos y límites | CPU, memoria, almacenamiento, red |
| RuntimeObservation | Métrica observada | timestamp, fuente, valor, unidad |
| OrchestrationEvent | Evento que puede cambiar la asignación | scaling, failure, overload, recovery |
| PlacementPolicy | Restricciones y objetivos | afinidad, capacidad, latencia, coste |
| MappingTransition | Cambio entre asignaciones | origen, destino, trigger, política, resultado |
| OrchestratorAction | Acción solicitada o ejecutada | create, delete, reschedule, restart |
| ModelRuntimeSync | Sincronización entre modelo y plataforma | estado deseado, observado, drift |

**Relaciones sugeridas:** SoftwareComponent se materializa en DeployableArtifact; el artefacto tiene ContainerInstances; cada instancia se ejecuta en una unidad Pod/ExecutionUnit; esta se asigna a ComputeNode. DeploymentBinding conserva la asignación durante un intervalo. OrchestrationEvent puede provocar MappingTransition, que utiliza PlacementPolicy y produce OrchestratorAction. RuntimeObservation alimenta la decisión y verifica el resultado.

La relación temporal es importante: guardar inicio/fin o versiones de la asignación evita sobrescribir el historial. Separar estado deseado y estado observado evita asumir que el modelo siempre coincide con la plataforma real.

## 5. Preguntas de investigación derivadas

1. ¿Qué elementos de CAML y UML-RT pueden reutilizarse para representar componentes, artefactos, contenedores y nodos?
2. ¿Cómo representar formalmente la diferencia entre autoscaling, placement/scheduling y migración/reasignación?
3. ¿Qué eventos y métricas justifican una transición de asignación?
4. ¿Cómo sincronizar el modelo con el estado observado del orquestador?
5. ¿Qué propiedades deben preservarse durante un cambio: dependencias, conectividad, afinidad, recursos y disponibilidad?
6. ¿Puede generarse una vista inicial desde UML/TOSCA/PCM y actualizarse con eventos de runtime?

## 6. Recomendación para orientar la contribución

Una contribución sólida no sería simplemente “un nuevo diagrama de despliegue para Docker”. Debería especificar:
1. un metamodelo con componentes, artefactos, instancias, recursos y relaciones;
2. una semántica temporal para estados y transiciones;
3. reglas/políticas que expliquen por qué cambia una asignación;
4. una conexión con el estado observado del orquestador;
5. una evaluación con escenarios de escalado, fallo, scheduling y reasignación.

Moh25 y Ber14 ayudan a justificar la base UML; Kan14, Bet20 y Hag26 ayudan a separar y definir los mecanismos dinámicos que la extensión tendría que representar.

## 7. Referencias primarias

- Moh25: [DOI](https://doi.org/10.5220/0013148000003896) · [PDF SciTePress](https://www.scitepress.org/Papers/2025/131480/131480.pdf)
- Kan14: [PDF IJIRCCE](https://www.rroij.com/open-access/automated-scaling-of-cluster-usingdeployment-diagrams-in-platformasaservice.pdf)
- Bet20: [DOI](https://doi.org/10.1109/ISSE49799.2020.9272014) · [registro KIT](https://www.itiv.kit.edu/english/21_53.php)
- Hag26: [DOI](https://doi.org/10.1109/ICSA66085.2026.00034) · [página ICSA 2026](https://conf.researchr.org/details/icsa-2026/icsa-2026-papers/28/Enhancing-Decision-Making-on-Container-Orchestration-Using-Simulation-Driven-Modeling)
- Ber14: [PDF institucional Universidad de Sevilla](https://idus.us.es/bitstreams/e965afa5-0d94-40db-b3a5-8c6fd080f5be/download)
