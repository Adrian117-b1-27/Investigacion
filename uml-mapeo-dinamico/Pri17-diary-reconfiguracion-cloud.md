# [Pri17] Reconfiguración Dinámica e Incremental de Arquitecturas de Servicios Cloud Dirigida por Modelos

- **Autor:** Miguel Ángel Zúñiga Prieto
- **Año:** 2017
- **Tipo:** Tesis doctoral (según el registro recuperado)
- **DOI:** https://doi.org/10.4995/Thesis/10251/86288
- **PDF en Undermind:** no disponible.

## Resumen/abstract original recuperado (español)
La computación cloud permite acceder a recursos tecnológicos como servicios remotos y asignarlos de manera ágil y elástica, reservándolos o liberándolos según la demanda. El desarrollo incremental de aplicaciones cloud puede modificar sucesivamente la arquitectura de la aplicación. La tesis plantea que la ingeniería dirigida por modelos puede facilitar el diseño, implementación y despliegue incremental, manteniendo la continuidad de ejecución mientras se reconfigura dinámicamente la arquitectura orientada a servicios. Su objetivo principal es definir y validar empíricamente DIARy, un método para especificar la integración arquitectónica de incrementos y derivar artefactos que permitan desplegar/replegar servicios y modificar en tiempo de ejecución los enlaces entre ellos.

## Resumen analítico
La tesis propone DIARy, un método dirigido por modelos para reconfigurar de manera dinámica e incremental arquitecturas de servicios cloud. No se limita al despliegue inicial: especifica cómo integrar nuevos servicios en una aplicación existente y genera artefactos para ejecutar la reconfiguración, incluyendo el despliegue o repliegue de servicios y el cambio de enlaces entre servicios durante la ejecución.

## Aporte para la investigación
Es un antecedente importante en español sobre reconfiguración dinámica de arquitecturas cloud. Puede ayudar a separar dos tipos de cambio: reasignar recursos/ubicación de componentes y modificar la estructura o enlaces de servicios. Tu modelo podría necesitar representar ambos, pero no deben confundirse.

## Límite
El registro lo describe como método para arquitecturas orientadas a servicios cloud; no se presenta como perfil UML ni como propuesta específica para Docker/Kubernetes.

## Pertinencia
**Alta como antecedente conceptual de reconfiguración cloud; indirecta para UML y contenedores.**
