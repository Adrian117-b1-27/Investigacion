# [Mat04] On A Software Architecture Description supporting Component Deployment and System Runtime Reconfiguration

- **Autores:** Jasminka Matevska-Meyer, W. Hasselbring, Ralf H. Reussner
- **Año:** 2004
- **Fecha registrada:** 2004-06-01
- **DOI:** no localizado por Undermind. [Registro bibliográfico](https://www.semanticscholar.org/paper/276da7712976080b42429a03c3f64532115feccd)
- **PDF en Undermind:** no disponible.

## Abstract original
> Architecture description languages (ADLs) can be used for describing architectures of component-based software systems. Typical ADLs provide explicit support for specifying components, connectors and configurations as well as for building hierarchical system configurations. All of them allow to specify structural dependencies among components, thus describing static configurations. This may be sufficient for an initial system composition, but does not provide enough information for post-deployment and runtime reconfiguration. Only a few ADLs provide some support for dynamics, usually without a clear differentiation between a possible behaviour of component descriptions and a runtime behaviour of component instances. Even XML-based ADLs such as xADL 2.0, which clearly distinguishes between the design-time and run-time, only defines structural instance schemata. In our approach, we observe the ”use” dependencies among instances of components (called ”live components”) of an already deployed and running system. The life components are constrained by specified structural dependencies (defined in ”component descriptions”). Live components are hosted in containers. The ”Service- Connector-Container” view of our model provides a way to describe the runtime behaviour of a system. Thus, it supports dynamic reconfiguration of component-based software systems. We use ”service effect automata” for runtime behaviour specification and intend to extend them using the timing and liveness concepts of ”live sequence charts”.

## Resumen analítico
El artículo parte de la limitación de las descripciones arquitectónicas estáticas: describen componentes, conectores y configuraciones iniciales, pero no necesariamente el comportamiento de instancias reales ni su reconfiguración posterior al despliegue. Propone una vista Service-Connector-Container que observa dependencias de uso entre componentes activos y permite describir el comportamiento en runtime. Incluye autómatas de efecto de servicio para especificar comportamiento y contempla su futura extensión con conceptos temporales y de vivacidad.

## Aporte para la investigación
Es un antecedente temprano sobre la diferencia entre configuración estructural en diseño y comportamiento de instancias desplegadas. La distinción entre descripción del componente y componente vivo en ejecución puede ser útil para modelar cambios temporales del mapeo.

## Límite
No se presenta como perfil UML ni como solución para Kubernetes/Docker. El abstract habla de componentes alojados en contenedores en un sentido arquitectónico, no necesariamente contenedores modernos de sistema operativo. Debe evitarse equiparar ambos usos sin revisar el texto completo.

## Pertinencia
**Antecedente conceptual.** Útil para fundamentar la necesidad de separar vista estática y runtime, pero tecnológicamente anterior a la orquestación contenerizada actual.
