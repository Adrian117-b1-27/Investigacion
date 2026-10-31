# [Ber14] UML-based Cloud Application Modeling with Libraries, Profiles, and Templates

- **Autores:** A. Bergmayr, J. Troya, Patrick Neubauer, M. Wimmer, G. Kappel
- **Año:** 2014
- **Publicación:** CloudMDE@MoDELS, pp. 56–65
- **DOI:** no localizado por Undermind. [Registro bibliográfico](https://www.semanticscholar.org/paper/2143160a6bff50358cc628320e844874a13af878)
- **PDF en Undermind:** no disponible.

## Abstract original
> Recently, several cloud modeling approaches have emerged. They address the diversity of cloud environments by introducing a considerable set of modeling concepts in terms of novel domain-specific languages. At the same time, general-purpose languages, such as UML, provide modeling concepts to represent software, platform and infrastructure artifacts from different viewpoints where the deployment view is of particular relevance for specifying the distribution of application components on the targeted cloud environments. However, the generic nature of UML’s deployment language calls for a cloud-specific extension to capture the plethora of cloud provider offerings at the modeling level. In this paper, we propose the Cloud Application Modeling Language (CAML) to facilitate expressing cloud-based deployments directly in UML, which is especially beneficial for migration scenarios where reverse-engineered UML models are tailored towards a selected cloud environment. We discuss CAML’s realization as a UML internal language that is based on a model library for expressing deployment topologies and a set of profiles for wiring them with cloud provider offerings. Finally, we report on the use of UML templates to contribute application deployments as reusable blueprints and identify conceptual mappings between CAML and the recently standardized TOSCA.

## Resumen analítico
Presenta CAML (Cloud Application Modeling Language), una extensión interna de UML para expresar despliegues de aplicaciones cloud. CAML combina una biblioteca de modelos para describir topologías de despliegue con perfiles que conectan esas topologías con ofertas de proveedores cloud. También utiliza plantillas UML para reutilizar blueprints de despliegue y establece correspondencias conceptuales con TOSCA. El artículo destaca escenarios de migración hacia entornos cloud específicos.

## Aporte para la investigación
Es un antecedente central para la representación UML del despliegue cloud: ofrece mecanismos para describir topologías y vincular elementos del modelo con servicios de proveedores. Puede servir como base estática sobre la cual investigar cómo representar cambios temporales de asignación.

## Límite
El abstract no afirma que CAML modele autoscaling, reubicación o reasignación automática en runtime. No se debe presentar como una solución de mapeo dinámico sin revisar el texto completo.

## Pertinencia
**Media-alta.** Importante para la dimensión UML y topología de despliegue.
