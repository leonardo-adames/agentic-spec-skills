# 🤖 Agentic Spec Skills
<!-- BADGES DE TOPICS -->
<p align="left">
  <img src="https://img.shields.io/badge/Claude_Code-D97706?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude Code" />
  <img src="https://img.shields.io/badge/Agent_Skills-000000?style=for-the-badge&logo=githubactions&logoColor=white" alt="Agent Skills" />
  <img src="https://img.shields.io/badge/LLM_Tools-10B981?style=for-the-badge&logo=openai&logoColor=white" alt="LLM Tools" />
  <img src="https://img.shields.io/badge/Cursor_AI-000000?style=for-the-badge&logo=cursor&logoColor=white" alt="Cursor AI" />
  <img src="https://img.shields.io/badge/Codex-00A67E?style=for-the-badge&logo=openai&logoColor=white" alt="Codex" />
  <img src="https://img.shields.io/badge/Multi--Agent-6366F1?style=for-the-badge&logo=probot&logoColor=white" alt="Multi-Agent" />
  <img src="https://img.shields.io/badge/AI_Agents-8B5CF6?style=for-the-badge&logo=robot&logoColor=white" alt="AI Agents" />
  <img src="https://img.shields.io/badge/Productivity-EC4899?style=for-the-badge&logo=lightning&logoColor=white" alt="Productivity" />
  <img src="https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white" alt="PowerShell" />
  <img src="https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white" alt="Markdown" />
</p>

**Agentic Spec Skills** es una infraestructura modular, ligera y agnóstica de **habilidades puras en Markdown (`SKILL.md`)** optimizada para modelos de lenguaje locales (Local LLMs), entornos agénticos y asistentes de desarrollo de alto rendimiento.

El proyecto nace de refactorizar repositorios monolíticos complejos (como `agentic-awesome-skills`), eliminando scripts ejecutables pesados (`.py`), entornos virtuales y dependencias secundarias. El resultado es un monorepo limpio donde cada dominio técnico es un **plugin aislado y portátil**.

---
<br><br>

## 🏗️ Arquitectura del Repositorio

El proyecto implementa una arquitectura de micro-plugins. Cada plugin reside en su propia carpeta bajo `plugins/` y cuenta con manifiestos independientes para garantizar compatibilidad multi-agente sin saturar la memoria ni el contexto del modelo:

```text
agentic-skills/
├── plugins/
│   ├── plugins-compressed/        <-- Paquetes .zip listos para carga directa
│   │   ├── ai-ml.zip
│   │   ├── database.zip
│   │   └── web-development.zip
│   │
│   └── <nombre-del-plugin>/       <-- Plugin modular aislado
│       ├── skills/                <-- Habilidades puras
│       │   └── <nombre-skill>/
│       │       └── SKILL.md
│       ├── .claude-plugins/       <-- Manifiesto Claude Code
│       │   └── plugins.json
│       ├── .codex-plugins/        <-- Manifiesto Codex
│       │   └── plugins.json
│       ├── .agents-plugins/       <-- Manifiesto Agnóstico (Cursor, Windsurf, Kimi, etc.)
│       │   └── plugins.json
│       └── plugins.json           <-- Manifiesto raíz del plugin
│
├── CATALOG.md                     <-- Índice navegable de todos los plugins
└── CONSTITUTION.md                <-- Normas de gobernanza y contribución
```
<br><br>

# 🚀 Métodos de Despliegue e Integración


## Método 1: Carga Local Directa (Claude Desktop App / Web UI)

**Ideal para trabajo offline, bajo consumo de recursos e IA local.**

1. Accede a la carpeta `plugins/plugins-compressed/`.

2. Descarga el archivo .zip correspondiente a la categoría requerida (ej. database.zip).

3. Sube el .zip o arrastra el archivo SKILL.md deseado directamente a la interfaz de Claude Desktop o la versión Web.

4. Resultado: Activación inmediata de la habilidad sin instalar entornos ni ejecutar scripts.

---

<br>

## Método 2: Uso desde **Terminal / CLI** (`Claude Code, Codex, Custom Agents`)

Ideal para desarrolladores trabajando directamente en terminales y entornos de desarrollo.


### Instalación vía Registro de Plugin:

```bash

claude plugin add <tu-usuario>/agentic-skills/plugins/<nombre-del-plugin>
```

### Clonación Local:

```bash
git clone [https://github.com/](https://github.com/)<leonardo-adames>/ai-agents-plugins.git
```
<br>

---

## Método 3: Consumo Remoto Sincronizado (plugins.json)

**Ideal para pipelines CI/CD y consumo dinámico en repositorios remotos.**

Cada carpeta de plugin incluye manifiestos `plugins.json` vinculados a las URLs del repositorio. Permite que las herramientas lean los metadatos y descarguen los `SKILL.md` directamente desde GitHub mediante endpoints Raw.

## 🛡️ Compatibilidad Multi-Agente

Cada plugin incluye soporte nativo preconfigurado para los principales ecosistemas agénticos:

    Claude Code / Desktop: Mediante .claude-plugins/plugins.json

    Codex CLI: Mediante .codex-plugins/plugins.json

    Agentes Agnósticos (Cursor, Windsurf, AntiGravity, OpenCode, Kimi, DeepSeek): Mediante .agents-plugins/plugins.json

<br><br>

# 🤝 Contribuciones y Colaboración

**¡Las contribuciones son bienvenidas! Si deseas agregar un nuevo plugin o actualizar una habilidad existente:**

1. Haz un Fork del repositorio.

2. Crea una rama para tu funcionalidad (git checkout -b feature/nueva-skill).

3. Añade tu habilidad en la ruta plugins/<categoria>/skills/<nombre-skill>/SKILL.md respetando las reglas definidas en CONSTITUTION.md.

4. Ejecuta el script de compresión en PowerShell para generar el .zip correspondiente en plugins-compressed.

5. Abre un Pull Request explicando los cambios o la nueva habilidad agregada.

---

<br><br>

# ☕ Apoya el Proyecto

Si este repositorio te ha sido de utilidad para optimizar tu flujo de trabajo agéntico y deseas apoyar su desarrollo continuado, puedes realizar una contribución a través de las siguientes plataformas:

<p align="left">
  <a href="https://buymeacoffee.com/TU_USUARIO" target="_blank">
    <img src="https://img.shields.io/badge/Buy_Me_A_Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me A Coffee" />
  </a>
  <a href="https://paypal.me/TU_USUARIO" target="_blank">
    <img src="https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white" alt="PayPal" />
  </a>
  <a href="https://patreon.com/TU_USUARIO" target="_blank">
    <img src="https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white" alt="Patreon" />
  </a>
  <a href="https://github.com/sponsors/TU_USUARIO" target="_blank">
    <img src="https://img.shields.io/badge/GitHub_Sponsors-EA4AAA?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="GitHub Sponsors" />
  </a>
</p>