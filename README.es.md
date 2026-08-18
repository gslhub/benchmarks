<div align="center">

# GSLHub Benchmarks

### Evaluación reproducible para Búsqueda Generativa, GEO y visibilidad en IA

**Especificaciones de benchmark, definiciones métricas, fixtures sintéticos de validación y reglas de publicación de GSLHub**

[English](./README.md) · **Español**

[Web](https://gslhub.com) · [Metodología](https://github.com/gslhub/research) · [Software de métricas](https://github.com/gslhub/software/tree/main/packages/metrics-core) · [Plataforma](https://github.com/gslhub/website)

</div>

---

## Propósito

`gslhub/benchmarks` es la capa pública de benchmarks de **GSLHub — Generative Search Lab Hub**.

El repositorio define marcos de evaluación reproducibles para estudiar si los sistemas generativos incluyen, citan y posicionan targets evaluados, y hasta qué punto esos resultados se mantienen estables en repeticiones controladas.

Separa de forma deliberada la **especificación del benchmark** de los **resultados de investigación**. Un benchmark puede publicarse antes de que exista un dataset experimental real o cualquier hallazgo doctoral.

## Benchmark actual

### GSL-BENCH-GEO-01

La primera familia de benchmark evalúa la visibilidad controlada en Búsqueda Generativa / GEO mediante cuatro métricas gobernadas:

| Código | Métrica | Pregunta principal |
|---|---|---|
| **AIR** | Answer Inclusion Rate | ¿En qué proporción de respuestas elegibles aparece visiblemente el target? |
| **CR** | Citation Rate | ¿En qué proporción de ejecuciones elegibles se cita explícitamente el target? |
| **MCP** | Mean Citation Position | Cuando se cita, ¿en qué posición aparece la primera cita válida del target? |
| **RCR** | Response Consistency Rate | ¿Qué estabilidad tienen las respuestas repetidas respecto a una baseline congelada? |

El protocolo científico canónico y el codebook de observaciones/citas viven en [`gslhub/research`](https://github.com/gslhub/research).

## Implementación de referencia

La primera implementación independiente de estas cuatro especificaciones es [`@gslhub/metrics-core`](https://github.com/gslhub/software/tree/main/packages/metrics-core) dentro de [`gslhub/software`](https://github.com/gslhub/software).

El paquete es independiente de la capa CMS/base de datos de GSLHub y expone cálculos deterministas, exclusiones de elegibilidad, numeradores/denominadores y checksums SHA-256 de entrada/salida. Su suite de tests reproduce el fixture sintético de este repositorio.

La **especificación del benchmark sigue siendo normativa**. Las implementaciones de software se versionan por separado para poder validarse contra la especificación que declaran implementar.

## Estructura del repositorio

```text
benchmarks/
├── benchmarks/
│   └── GSL-BENCH-GEO-01/
│       ├── README.md
│       └── benchmark.yaml
├── metrics/
│   ├── AIR-v0.1.0.md
│   ├── CR-v0.1.0.md
│   ├── MCP-v0.1.0.md
│   └── RCR-v0.1.0.md
├── fixtures/
│   └── synthetic-validation.json
├── RESULTS-POLICY.md
├── CITATION.cff
└── README.md
```

## Principios de benchmark

Un benchmark GSLHub debe ser:

- **versionado** — los cambios metodológicos materiales crean una nueva versión;
- **auditable** — los resultados permanecen trazables hasta evidencia preservada y observaciones codificadas;
- **consciente de condiciones** — prompt, perfil del sistema de IA, interfaz, locale y demás condiciones relevantes se congelan o reportan;
- **explícito sobre exclusiones** — ejecuciones fallidas o no comparables se documentan, no se eliminan silenciosamente;
- **separado de la validación sintética** — los fixtures de software nunca se presentan como hallazgos científicos;
- **reproducible** — fórmulas, reglas de numerador/denominador y tratamiento de datos faltantes se documentan.

## Fixture sintético de validación

El repositorio contiene un fixture deliberadamente sintético utilizado únicamente para validar cálculos deterministas:

```text
AIR = 3 / 4 = 0.75
CR  = 2 / 4 = 0.50
MCP = 6 / 3 = 2.00
RCR = 3 / 4 = 0.75
```

Estos valores **no son hallazgos empíricos**, no describen ningún sistema de IA y nunca deben citarse como resultados de investigación.

Los mismos valores esperados se validan en la suite pública de `@gslhub/metrics-core`, creando una comprobación cruzada entre especificación e implementación.

## Resultados

Los resultados reales de benchmark se publican únicamente después de:

1. congelar el protocolo;
2. ejecutar de forma controlada;
3. preservar los artefactos;
4. codificar y revisar;
5. resolver elegibilidad/exclusiones;
6. validar determinísticamente las métricas;
7. aprobar científicamente la publicación.

Consulta [`RESULTS-POLICY.md`](RESULTS-POLICY.md).

## Licencias

Las especificaciones y documentación originales de benchmarks se publican para reutilización científica bajo **Creative Commons Attribution 4.0 International (CC BY 4.0)** salvo indicación distinta en un archivo.

Datasets y materiales de terceros se licencian por separado según procedencia y derechos.

## Citación

Los metadatos de citación están en [`CITATION.cff`](CITATION.cff). Al utilizar una release específica, cita también el identificador y versión del benchmark.

---

© 2026 GSLHub / Eduardo Yauri
