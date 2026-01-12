# Pre-development flow
## Task creation and alignment (Agent-driven)

This flow describes how a task is created, standardized and validated
before any development work starts.

```mermaid
flowchart TD
    A[Ticket de soporte\nNecesidad del cliente] --> B[Agente de Redacción de Tareas]

    B --> C[Tarea técnica estandarizada\nTitle · Issue · Solution · Use Cases · Refinements]

    C --> D{Revisión\nPM · Cliente · Dev}

    D -->|No aprobado| E[Feedback / Ajustes]
    E --> B

    D -->|Aprobado| F[Estimación de horas]
    F --> G[Tarea lista para desarrollo]
