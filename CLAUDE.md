# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Proposito del Proyecto

Presentaciones interactivas para el curso **Inteligencia Artificial Aplicada a la Electromovilidad** usando **Slidev** (sli.dev). 8 bloques como archivos Markdown en `slides/`, tema `penguin` con CSS personalizado, y 48 imágenes en `public/img/`.

---

## Comandos de Desarrollo

```bash
# Ver un bloque en el navegador (modo dev con hot-reload)
npm run dev:01     # bloque-01 en puerto 3001
npm run dev:02     # bloque-02 en puerto 3002
# ... hasta dev:08

# Construir para producción (genera dist/bloque-NN/)
npm run build:01
# ... hasta build:08

# Atajo: bloque-01 en puerto por defecto
npm run dev
```

---

## Arquitectura

### Flujo de Contenido

`bloques/bloque-NN-nombre.md` (fuente de contenido, **solo lectura**) → `slides/bloque-NN.md` (presentación Slidev editable)

Los archivos en `bloques/` son el contenido pedagógico de referencia. El trabajo ocurre en `slides/`.

### Frontmatter estándar de cada archivo `slides/bloque-NN.md`

```yaml
---
theme: penguin
title: "Bloque NN — Nombre del Bloque"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque NN
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
zoom: 0.85
fonts:
  sans: 'Segoe UI'
---
```

Cada slide separado por `---` puede tener frontmatter propio (`layout:`, `class:`).

### Imágenes

Servidas desde `public/img/` — referenciadas como `/img/bNN-nombre.jpg`.

| Bloque | Imágenes |
|--------|----------|
| B01 | b01-ev-street, b01-neural-network, b01-data-chart, b01-analytics, b01-matrix, b01-ai-brain |
| B02 | b02-camera-car, b02-lidar, b02-detection, b02-robot-vision, b02-sensors, b02-selfdriving |
| B03 | b03-chip, b03-datacenter, b03-gpu, b03-circuit, b03-server, b03-processor |
| B04 | b04-battery, b04-bms, b04-energy, b04-solar, b04-ev-charge, b04-cells |
| B05 | b05-charging-station, b05-smartgrid, b05-wind, b05-solar-panel, b05-network, b05-ev-plug |
| B06 | b06-map, b06-logistics, b06-fleet, b06-routing, b06-city-roads, b06-delivery |
| B07 | b07-intersection, b07-traffic-light, b07-smart-city, b07-city-aerial, b07-traffic-jam, b07-highway |
| B08 | b08-autonomous, b08-sensor-fusion, b08-system, b08-robot, b08-ev-future, b08-integration |

---

## Diseño — Midnight Tech

### Paleta (CSS variables en `style.css`)

```css
--primary:   #0D1B2A   /* Azul medianoche — fondos oscuros */
--secondary: #1B4F72   /* Azul profundo — cards y barras */
--accent:    #00D4FF   /* Cyan eléctrico — títulos, highlights */
--light:     #F0F4F8   /* Gris hielo — fondos claros */
--success:   #10B981   /* Verde — métricas positivas */
--warning:   #F59E0B   /* Ámbar — alertas y notas */
```

### Clases CSS disponibles (`style.css`)

| Clase | Uso |
|-------|-----|
| `.dark-slide` | Fondo `--primary` con texto claro (usar en frontmatter del slide como `class: dark-slide`) |
| `.card-ev` | Tarjeta azul oscuro con padding, texto claro |
| `.badge-ev` | Badge cyan pequeño con texto oscuro |
| `.slide-scroll` | Área scrollable para slides con contenido largo (`max-height: 390px`) |
| `.accent` / `.success` / `.warning` / `.muted` | Clases de color de texto |

### Layouts Slidev usados

- `layout: cover` — portada con imagen de fondo y título centrado
- `layout: default` — contenido general
- `layout: image-right` — imagen derecha + contenido izquierdo
- `layout: center` — cierre/resumen centrado
- `v-click` — reveals progresivos en listas y grids

### Patrón típico de slide con contenido

```md
---
layout: default
---

# Título del Slide

<img src="/img/bNN-imagen.jpg" class="absolute right-0 top-0 h-full w-1/3 object-cover opacity-10 -z-1" />

<div class="slide-scroll">
<div class="grid grid-cols-2 gap-4 mt-4">
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">Subtítulo</div>
    <div class="text-sm">Contenido breve</div>
  </div>
</div>
</div>
```

---

## Resumen de los 8 Bloques

| # | Nombre | Slides |
|---|--------|--------|
| 01 | Fundamentos de Machine Learning | 30 |
| 02 | Percepción del Entorno y Computer Vision | 10 |
| 03 | Arquitectura de Sistemas y Deployment | 10 |
| 04 | Gestión Inteligente de Energía y Baterías | 10 |
| 05 | Infraestructura de Carga Inteligente | 10 |
| 06 | Logística y Optimización de Rutas | 10 |
| 07 | Tráfico Inteligente y Sistemas Multiagente | 10 |
| 08 | Integración Integral con CARLA | 12 |

**Duración total:** 16 horas (2h por bloque) — Público: UTCJ, Ciudad Juárez, nivel universitario/profesional

---

## Referencia de Diseño (solo lectura)

- `config/design-system.md` — especificación completa de colores, tipografía y estructura de slides por tipo
- `config/tech-stack.md` — stack tecnológico del curso
- `config/image-guidelines.md` — reglas para uso de imágenes
