# [Kan14] Automated Scaling of Cluster Using Deployment Diagrams in Platform-As-A-Service

- **Autores:** S. Kanade, P. B. Thorat
- **Año:** 2014
- **Publicación:** International Journal of Innovative Research in Computer and Communication Engineering, pp. 7342–7346
- **DOI:** no localizado. [Registro bibliográfico](https://www.semanticscholar.org/paper/4ac03197c2c8936f8b2c6093a10f3e2e1786bd5d)
- **PDF en Undermind:** no disponible.

## Abstract original
> Cloud computing is delivery of computational power in the form of service. In here software, computational resources and data are shared to computers and other devices as a metered service over the network. Platform-as-a-Service is a one of the cloud based approach that provides managed middleware, isolating user from managing resources and platform. In this paper we propose a system which uses Deployment Diagrams to manage applications and its whole cluster including middleware. Here we emphasis on its capablity to add/remove resources to the cluster, i.e. when demand is increased new nodes are created and plugged into the cluster depending on the deployment diagram grammar, and when the demand is lessen the resources are claimed and returned to the free pool.

## Resumen analítico
Propone utilizar diagramas de despliegue para gestionar una aplicación y su clúster en un entorno PaaS. El abstract indica que el sistema puede añadir nodos al clúster cuando aumenta la demanda y retirar recursos cuando disminuye, utilizando una gramática asociada al diagrama de despliegue.

## Aporte para la investigación
Es un resultado muy próximo a la idea de conectar diagramas de despliegue con elasticidad: menciona explícitamente añadir y retirar nodos en función de la demanda. Conviene examinar si la gramática formaliza estados, eventos, reglas de transición y consistencia del diagrama con la infraestructura real.

## Límite
El resumen no detalla el formalismo, el mecanismo de ejecución, la evaluación ni si el enfoque está basado en UML estándar o en una notación propia de diagramas de despliegue. Tampoco menciona Docker o Kubernetes. Por ello es un antecedente prometedor, pero no prueba que exista una solución completa y validada para contenedores modernos.

## Pertinencia
**Alta para diagramas de despliegue y escalado; requiere validación del texto completo.**
