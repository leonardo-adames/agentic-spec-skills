# 📜 Constitución de Gobernanza y Desarrollo

Esta Constitución establece las reglas arquitectónicas inmutables que rigen el monorepo **Agentic Skills**. Todo colaborador, maintainer o script automatizado debe cumplir estrictamente estas directrices.

---

<br>

## Artículo I: Pureza y Aislamiento del Formato

1. **Formato Markdown Exclusivo:** Toda habilidad debe expresarse únicamente en un archivo `SKILL.md` estructurado.
2. **Cero Archivos Residuales:** Queda estrictamente prohibida la inclusión de scripts ejecutables (`.py`, `.sh`, `.bat`), entornos virtuales (`venv`), binarios o archivos de dependencias (`requirements.txt`, `package.json` de Node) dentro de las carpetas de habilidades.
3. **Frontmatter Estándar:** Cada `SKILL.md` debe iniciar con un encabezado YAML limpio definiendo nombre, descripción clara y versión.

---

<br>

## Artículo II: Estructura Multi-Agente Espejo

Todo plugin creado dentro del directorio `plugins/` debe mantener una estructura exacta de tres capas de compatibilidad:

```text
plugins/<nombre-plugin>/
├── skills/
│   └── <nombre-skill>/
│       └── SKILL.md
├── .claude-plugins/
│   └── plugins.json
├── .codex-plugins/
│   └── plugins.json
├── .agents-plugins/
│   └── plugins.json
└── plugins.json
```

## Artículo III: Distribución y Nomenclatura

    Nomenclatura Kebab-Case: Todos los nombres de carpetas y archivos deben escribirse en minúsculas separadas por guiones cortos (kebab-case).

    Empaquetado Obligatorio: Tras modificar o agregar una habilidad en un plugin, es obligatorio actualizar su paquete distribuible .zip correspondiente dentro de plugins/plugins-compressed/ ejecutando el script oficial de PowerShell.

    Cero Manifiestos Monolíticos: No se generarán manifiestos consolidados globales en la raíz que superen la capacidad de lectura ligera de los agentes.

<br>

## Artículo IV: Estándar de Contribución

Cualquier cambio que rompa la compatibilidad con LLMs locales o introduzca dependencias externas pesadas será rechazado automáticamente para mantener la agilidad y ligereza del proyecto.