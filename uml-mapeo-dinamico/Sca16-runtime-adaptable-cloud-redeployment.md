# [Sca16] Towards a Goal-oriented Approach to Adaptable Re-deployment of Cloud-based Applications

- **Autores:** P. Scandurra, M. Mongiello, S. Colucci, L. Grieco
- **Año:** 2016
- **Publicación:** International Conference on Cloud Computing and Services Science, pp. 253–260
- **DOI:** https://doi.org/10.5220/0005861602530260
- **PDF en Undermind:** no disponible.

## Abstract original
> Due to the on-demand and dynamic nature of Cloud, there is an increasing interest for automated management of adaptation and (possibly) re-deployment of cloud applications to realize quality requirements and evolution needs autonomously at run-time. This paper proposes a fast and automated approach for adapting and redeploying a cloud application at run-time as dictated by evolution needs and sudden changes in the operating environment conditions. The proposed approach exploits a graph-based model and an algorithm that extracts a sub-graph identifying the adaptation processes to be executed according to evolution changes. The approach is general enough to be implemented by any cloud application management framework. A TOSCA-based description of the structure and management aspects of the cloud application may be updated according to the above mentioned sub-graph. Then, this description may be processed by a TOSCA-compliant runtime environment to effectively adapt and possibly re-deploy the cloud application in an automated manner. The paper also illustrates the instantiation of this generic approach for adapting an e-commerce cloud application.

## Resumen analítico
Propone un enfoque automatizado para adaptar y redesplegar aplicaciones cloud en runtime ante cambios de evolución o condiciones del entorno. Utiliza un modelo basado en grafos y un algoritmo que extrae un subgrafo con los procesos de adaptación que deben ejecutarse. La descripción TOSCA de la aplicación puede actualizarse y procesarse en un entorno runtime compatible para efectuar la adaptación o el redespliegue. El enfoque se ilustra con una aplicación de comercio electrónico.

## Aporte para la investigación
Es un antecedente directo para representar transiciones y acciones de adaptación en un modelo de infraestructura. El uso de grafos para identificar los cambios puede inspirar una representación de estados y transiciones del mapeo de recursos.

## Límite
No es una extensión UML y el abstract no se centra específicamente en Docker o Kubernetes. El aporte está en la adaptación y redespliegue cloud dirigidos por modelo.

## Pertinencia
**Alta para adaptación y redespliegue en runtime; complementaria al objetivo UML.**
