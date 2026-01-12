flowchart TD
    A[Ticket de soporte / Necesidad del cliente] --> B[Agente de Redacción de Tareas]

    B --> C[Genera tarea técnica estandarizada\nTitle · Issue · Solution · Use Cases · Refinements]

    C --> D{Revisión PM / Cliente / Dev}

    D -->|No aprobado| E[Feedback / Ajustes]
    E --> B

    D -->|Aprobado| F[Estimación de horas]
    F --> G[Inicio del desarrollo]

    G --> H[Implementación]
    H --> I[Pull Request]

    I --> J[Agente de Revisión Post-Dev]

    J --> K[Revisión de Tarea en Jira]
    J --> L[Revisión del PR]
    J --> M[Análisis funcional vs Use Cases]

    K --> N{¿Cumple lo requerido?}
    L --> N
    M --> N

    N -->|No| O[Feedback automático al Dev]
    O --> G

    N -->|Sí| P[Chequeo de Documentación]

    P --> Q{¿Existe documentación?}

    Q -->|Sí, exacta| R[Linkea documentación existente]
    Q -->|Similar| S[Linkea doc similar + advertencia]
    Q -->|No existe| T[Propone nueva documentación]

    T --> U[Dev revisa y confirma propuesta de documentación]

    R --> V[PR listo para merge]
    S --> V
    U --> V
