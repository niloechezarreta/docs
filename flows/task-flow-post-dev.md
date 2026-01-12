# Post-development flow
## Task validation and documentation (Agent-driven)

This flow describes how completed work is validated against requirements
and how documentation is ensured or proposed.

```mermaid
flowchart TD
    A[Inicio del desarrollo] --> B[Implementación]
    B --> C[Pull Request]

    C --> D[Agente de Revisión Post-Dev]

    D --> E[Revisión de tarea en Jira]
    D --> F[Revisión del PR]
    D --> G[Análisis funcional\nvs Use Cases]

    E --> H{¿Cumple lo requerido?}
    F --> H
    G --> H

    H -->|No| I[Feedback automático al Dev]
    I --> B

    H -->|Sí| J[Chequeo de documentación]

    J --> K{¿Existe documentación?}

    K -->|Sí, exacta| L[Linkea documentación existente]
    K -->|Similar| M[Linkea doc similar\n+ advertencia]
    K -->|No existe| N[Propone nueva documentación]

    N --> O[Dev revisa y confirma]

    L --> P[PR listo para merge]
    M --> P
    O --> P
