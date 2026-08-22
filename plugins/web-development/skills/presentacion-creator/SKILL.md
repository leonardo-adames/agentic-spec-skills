---
name: presentacion-creator
description: Diseña y genera presentaciones web profesionales ("Slides-as-Code") aplicando el árbol de decisión de framework (Slidev / Reveal.js / Spectacle / Marp / impress.js / PptxGenJS), la metodología de storytelling (Problema-Tensión-Resolución, Pyramid Principle) y el sistema de diseño/motion design documentados en references/Building_Dynamic_Slideshows_with_HTML_CSS_and_JavaScript.md. Usar siempre que se pida crear, diseñar, estructurar o convertir una fuente en una presentación, deck, slideshow o slider web — incluso si no se menciona explícitamente la palabra "presentación".
---

# Presentacion Creator

Genero presentaciones web profesionales a partir de una fuente de
contenido y una paleta de marca, siguiendo la metodología "Slides-as-Code"
de `references/Building_Dynamic_Slideshows_with_HTML_CSS_and_JavaScript.md`.
No improviso el framework ni la narrativa — sigo el árbol de decisión y
el proceso documentados ahí.

## Antes de empezar: reunir estos inputs

Si no se dan, preguntarlos antes de elegir framework o escribir slides:

1. **Fuente de contenido** (artículo, documento, transcript, notas).
2. **Audiencia**: ¿técnica o no técnica?
3. **Objetivo y CTA final** de la presentación.
4. **Paleta de marca** (colores, tipografía) — si no se da, preguntar o
   usar la de un proyecto de marca existente si el usuario lo indica.
5. **Contexto de uso**: ¿conferencia en vivo, embebida en un sitio/LMS,
   documentación interna, o pitch deck?

## Árbol de decisión de framework

| Requerimiento | Framework recomendado | Razón principal |
|---|---|---|
| Conferencia de desarrolladores, grabación integrada, componentes Vue/React | **Slidev** | Integración nativa con Shiki y Monaco Editor |
| Embebida en un sitio web o LMS, sin forzar un runtime de app completo | **Reveal.js** | Biblioteca Vanilla JS, agnóstica de framework |
| Ya existen componentes React que se quieren reutilizar tal cual | **Spectacle** | Las slides son componentes reactivos |
| Documentación técnica interna, fricción mínima | **Marp** | Curva de aprendizaje casi nula, exporta directo vía CLI |
| Narrativa espacial tipo "lienzo infinito", no lineal | **impress.js** | Manipulación por coordenadas X, Y, Z |
| Se necesita un `.pptx` real y editable (no solo export a imagen) | **PptxGenJS** | Crea objetos XML nativos de PowerPoint, no capturas |

## Metodología paso a paso

1. **Definir objetivo:** audiencia (técnica/no técnica) + CTA final.
2. **Outline:** convertir la fuente en un esquema Markdown simple —
   Títulos H1 → secciones, H2 → slides individuales. No usar el texto
   original tal cual; extraer el outline semántico primero.
3. **Mapping:** una idea física por slide (Principio de la Pirámide).
   Si una slide no responde una duda concreta o no aporta un dato, se
   elimina (test "So What").
4. **Elección de framework:** usar la tabla de arriba.
5. **Sistema de diseño:** definir paleta y tipografía como CSS Custom
   Properties (`--slide-bg`, `--slide-accent`, etc.) para poder
   re-temear sin tocar el resto del código.
6. **Interactividad:** componentes vivos donde aporten — diagramas
   Mermaid para lógica compleja, resaltado de código progresivo
   (`[1-3|5|7-9]`) para guiar el ojo por cambios lógicos.
7. **Checklist de calidad:** correr la lista de abajo antes de dar por
   terminada la presentación.
8. **Despliegue:** exportar a PDF vectorial, o desplegar como sitio
   estático (Vercel, GitHub Pages) según el contexto de uso.

## Storytelling

- **Arco narrativo:** Problema → Tensión → Resolución. Abrir con el
  "dolor" concreto de la audiencia, introducir la complejidad, resolver
  con la propuesta/stack.
- **Una idea por slide** — usar layouts primitivos (hero, split,
  cards, big-stat) en vez de amontonar texto.
- **Conversión de fuente:** nunca copiar el texto original directo a
  una slide. Extraer primero el outline semántico (jerarquía de
  encabezados), y de ahí mapear a slides.

## Diseño visual

- Tokens de color/tipografía como **CSS Custom Properties**, definidos
  una sola vez y reutilizados en todo el deck.
- Contraste conforme a **WCAG**. Layout de split-screen para contrastar
  teoría vs. código o antes/después.
- Accesibilidad obligatoria: atributo `alt` en imágenes, roles **ARIA**
  en carruseles/sliders, y respeto a `prefers-reduced-motion` para
  usuarios sensibles al movimiento.

## Enganche y conversión

- **Apertura (0-10s):** layout de "Big Stat" (un dato de impacto grande
  en pantalla) o una pregunta retórica — nunca un título genérico.
- **Test "So What"** en cada slide: si no responde una duda de la
  audiencia o no aporta un dato, se elimina.
- **CTA de cierre** en un layout dedicado (`closing-cta`), con enlaces
  directos a repositorio, documentación, o el siguiente paso concreto.

## Motion design con propósito

- **Cuándo animar:** resaltado de código progresivo para guiar el ojo
  por cambios lógicos en un algoritmo; transiciones de estado que
  aportan comprensión.
- **Cuándo NO animar:** transiciones aleatorias entre slides de puro
  texto — distraen del mensaje en vez de ayudarlo.
- **Duración:** máximo 500ms para micro-interacciones, 800ms para
  transiciones de slide completas.
- **GSAP:** animar `xPercent`/`yPercent` en vez de `left`/`top` para
  garantizar aceleración por hardware (fluido incluso en móviles).

## Checklist de calidad final

- [ ] **Narrativa:** ¿sigue el arco Problema-Tensión-Resolución?
- [ ] **Diseño:** ¿los tokens de color (`--slide-accent`, etc.) son
      consistentes en todo el deck?
- [ ] **Accesibilidad:** ¿se puede navegar completo con teclado (Tab)?
- [ ] **Código:** ¿el resaltado de sintaxis es progresivo/animado
      donde corresponde (no un bloque estático gigante)?
- [ ] **Técnico:** ¿los estilos están encapsulados para no filtrar CSS
      hacia el sitio que lo embeba, si aplica?

## Si se construye un slider/carrusel desde cero (no Slidev/Reveal.js)

Para casos donde no aplica un framework de presentaciones y se necesita
un slider de imágenes/tarjetas hecho a mano:

- **Animación:** `opacity` + `position: absolute` para fades elegantes;
  `transform: translateX()` (no `left`/`right`) para deslizamiento con
  aceleración por GPU.
- **Loop infinito:** variable `currentSlide` + operador módulo (`%`)
  para que la última slide vuelva a la primera sin salto.
- **Automatización:** `setInterval` para autoplay, pausado con el
  evento `hover`.
- **Contenido dinámico:** cargar título/imagen/enlace por slide desde
  un JSON externo vía `fetch`, en vez de hardcodear el HTML.
- **Rendimiento:** lazy loading de imágenes (no cargar todas de una),
  y unidades `vh`/`vw`/`%` para responsividad real.
- **Táctil:** soporte de swipe/arrastre si la audiencia es
  mayoritariamente móvil.

## Fuente

Metodología completa (contexto de mercado 2025-2026, plantilla operativa
extendida para agentes de IA) en
`references/Building_Dynamic_Slideshows_with_HTML_CSS_and_JavaScript.md`.
Consultar ese archivo para profundizar — no hace falta releerlo para
aplicar el procedimiento de arriba.
