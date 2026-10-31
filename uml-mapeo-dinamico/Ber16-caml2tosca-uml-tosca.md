# [Ber16] From Architecture Modeling to Application Provisioning for the Cloud by Combining UML and TOSCA

- **Autores:** A. Bergmayr, Uwe Breitenbücher, O. Kopp, M. Wimmer, G. Kappel, F. Leymann
- **Año:** 2016
- **Publicación:** International Conference on Cloud Computing and Services Science, pp. 97–108
- **DOI:** https://doi.org/10.5220/0005806900970108
- **PDF en Undermind:** no disponible.

## Abstract original
> Recent efforts to standardize a deployment modeling language for cloud applications resulted in TOSCA. At the same time, the software modeling standard UML supports architecture modeling from different viewpoints. Combining these standards from cloud computing and software engineering would allow engineers to refine UML architectural models into TOSCA deployment models that enable automatic provisioning of cloud applications. However, this refinement task is currently carried out manually by recreating TOSCA models from UML models because a conceptual mapping between the two languages as basis for an automated translation is missing. In this paper, we exploit cloud modeling extensions to UML called CAML as the basis for our approach CAML2TOSCA, which aims at bridging UML and TOSCA. The validation of our approach shows that UML models can directly be injected into a TOSCA-based provisioning process. As current UML modeling tools lack cloud-based refinement support for deployment models, the added value of CAML2TOSCA is emphasized because it provides the glue between architecture modeling and application provisioning.

## Resumen analítico
Propone CAML2TOSCA para conectar modelos arquitectónicos UML —enriquecidos con extensiones cloud CAML— con modelos TOSCA usados en el aprovisionamiento de aplicaciones cloud. El problema que aborda es la recreación manual de modelos TOSCA a partir de modelos UML. La contribución es una correspondencia conceptual que permite inyectar modelos UML en un proceso de aprovisionamiento basado en TOSCA; el abstract indica que se valida el enfoque.

## Aporte para la investigación
Es relevante para una arquitectura metodológica que conecte el diagrama de diseño con modelos de infraestructura y herramientas de despliegue. Puede servir para investigar cómo propagar cambios del modelo de arquitectura hacia una representación de infraestructura.

## Límite
El abstract no demuestra que CAML2TOSCA modele cambios en runtime, autoscaling o reasignación dinámica. Su foco es la transformación desde arquitectura hacia aprovisionamiento.

## Pertinencia
**Media-alta como puente UML–modelo de despliegue; limitada para dinámica runtime.**
