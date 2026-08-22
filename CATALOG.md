# Archivo 2: `CATALOG.md`

#### 📚 Catálogo Oficial de Plugins y Habilidades

Este catálogo documenta los plugins modulares disponibles en **Agentic Skills**. Cada módulo se encuentra aislado en `plugins/<nombre-del-plugin>` y empaquetado en `plugins/plugins-compressed/<nombre-del-plugin>.zip`.

---

| Plugin / Categoría | Propósito del Módulo | Composición Interna | Compatibilidad |
| :--- | :--- | :--- | :--- |
| **`agent-squad`** | Orquestador multi-agente para división de roles (Rex: Requisitos, Alex: Plan, Aria: Arquitectura, Mason: Código, Luna: QA). | Flujo secuencial de desarrollo. | Claude, Codex, Universal |
| **`ai-ml`** | Diseño, evaluación y despliegue de modelos de LLM, RAG, embeddings y Machine Learning. | Habilidades `SKILL.md` especializadas. | Claude, Codex, Universal |
| **`app-builder`** | Patrones de arquitectura, estructuración de proyectos y desarrollo rápido de aplicaciones. | Estándares de diseño de software. | Claude, Codex, Universal |
| **`automation`** | Creación de bots, automatización de tareas repetitivas y workflows. | Habilidades para automatización de procesos. | Claude, Codex, Universal |
| **`backend`** | Construcción de APIs RESTful, GraphQL, microservicios y lógica de servidor. | Patrones backend y diseño de servicios. | Claude, Codex, Universal |
| **`cloud`** | Arquitecturas serverless, servicios administrados y configuración de proveedores Cloud. | Mejores prácticas de infraestructura. | Claude, Codex, Universal |
| **`content`** | Generación de documentación técnica, especificaciones y redacción especializada. | Plantillas e instrucciones de redacción. | Claude, Codex, Universal |
| **`data-science`** | Análisis exploratorio, pipelines de datos, manipulación de datasets y visualización. | Flujos de trabajo científicos. | Claude, Codex, Universal |
| **`database`** | Diseños de esquemas, optimización de consultas SQL/NoSQL, indexación y migraciones. | Patrones para Postgres, Redis, Mongo, etc. | Claude, Codex, Universal |
| **`design-it`** | Sistemas de diseño, interfaces de usuario, UX accesible y prototipado visual. | Guías de estilos e interfaz. | Claude, Codex, Universal |
| **`devops`** | Pipelines CI/CD, contenedorización (Docker, K8s) y monitoreo de infraestructura. | Despliegue e integración continua. | Claude, Codex, Universal |
| **`game-development`** | Lógica de videojuegos, física, diseño de niveles y motores de desarrollo (Unity, Godot). | Patrones de desarrollo de juegos. | Claude, Codex, Universal |
| **`libreoffice`** | Automatización de documentos, hojas de cálculo y procesamiento ofimático abierto. | Manipulación de formatos abiertos. | Claude, Codex, Universal |
| **`mobile`** | Desarrollo nativo e híbrido para iOS y Android (React Native, Flutter, Swift, Kotlin). | Estándares móviles. | Claude, Codex, Universal |
| **`monopoly`** | Reglas de negocio complejas, arquitecturas propietarias y dominios cerrados. | Lógica de negocio estructurada. | Claude, Codex, Universal |
| **`security`** | Análisis de vulnerabilidades, auditoría de código, autenticación segura y hardening. | Prácticas de ciberseguridad. | Claude, Codex, Universal |
| **`sendblue`** | Integración de servicios de mensajería API, iMessage y automatización SMS. | Conectores de comunicación. | Claude, Codex, Universal |
| **`super-code`** | Refactorización avanzada, patrones de diseño de software y optimización crítica de código. | Algoritmos y refactorización masiva. | Claude, Codex, Universal |
| **`testing`** | Estrategias de pruebas unitarias, integración, E2E (Cypress, Playwright) y QA. | Cobertura y aseguramiento de calidad. | Claude, Codex, Universal |
| **`web-development`** | Desarrollo Web moderno (React, Vue, Angular, Next.js, Tailwind, HTML5/CSS3). | Componentes y estándares frontend. | Claude, Codex, Universal |

---

## 📦 Instrucción de Consumo por Módulo

Para utilizar únicamente un dominio técnico en tu agente (por ejemplo, **`database`**):
1. Descarga `plugins/plugins-compressed/database.zip`.
2. Sube el paquete a tu entorno agéntico o extrae la skill específica que necesites.