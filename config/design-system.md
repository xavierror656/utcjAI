# Design System - Curso IA Electromovilidad

## Paleta de Colores

El curso usa una paleta **Midnight Tech** que combina precision tecnica con energia electrica.

```
PRIMARY   → 0D1B2A   (azul medianoche — fondo de portadas y slides de seccion)
SECONDARY → 1B4F72   (azul profundo — fondos de contenido oscuro)
ACCENT    → 00D4FF   (cyan electrico — titulos, highlights, iconos activos)
LIGHT     → F0F4F8   (gris hielo — fondo de slides de contenido claro)
CARD_BG   → FFFFFF   (blanco — tarjetas y cajas de contenido)
TEXT_DARK → 1A1A2E   (casi negro — texto sobre fondo claro)
TEXT_LIGHT→ E8F4FD   (blanco azulado — texto sobre fondo oscuro)
MUTED     → 64748B   (gris — subtextos y captions)
SUCCESS   → 10B981   (verde — metricas positivas)
WARNING   → F59E0B   (ambar — alertas y notas)
```

## Tipografia

```
Titulo de portada  → Calibri Bold, 40pt, color ACCENT (00D4FF)
Subtitulo          → Calibri, 18pt, color TEXT_LIGHT (E8F4FD)
Titulo de slide    → Calibri Bold, 30pt, color TEXT_DARK o TEXT_LIGHT segun fondo
Header de seccion  → Calibri Bold, 20pt
Cuerpo             → Calibri, 14-16pt
Caption / label    → Calibri, 11pt, color MUTED
```

## Estructura de Diapositivas por Tipo

### Slide 1 — Portada (fondo oscuro PRIMARY)
```
Fondo: PRIMARY (0D1B2A)
Barra izquierda vertical: ACCENT (00D4FF), w=0.15", full height
Logo o icono del bloque: centrado arriba, 1.2" x 1.2", color ACCENT
Numero de bloque: Calibri 13pt, MUTED, centrado bajo icono  
Titulo del bloque: Calibri Bold 36pt, ACCENT, centrado
Subtitulo: Calibri 18pt, TEXT_LIGHT, centrado
Bloque + duracion: esquina inferior derecha, 11pt, MUTED
```

### Slide 2 — Indice / Agenda (fondo LIGHT)
```
Fondo: LIGHT (F0F4F8)
Titulo: "Contenido del Bloque" — Calibri Bold 28pt, TEXT_DARK
Lista de temas: 4-6 items con icono circular ACCENT + texto 16pt
Layout: dos columnas si hay mas de 4 items
```

### Slide 3-N — Contenido (alternar fondos LIGHT y CARD)
```
Fondo: LIGHT o CARD_BG
Barra superior: SECONDARY (1B4F72), h=0.8", full width
Titulo en barra: Calibri Bold 22pt, TEXT_LIGHT, x=0.5, y=0.22
Contenido: iconos + texto, layout 2 columnas o grid 2x2
Imagenes: alineadas a la derecha o mitad inferior
```

### Slide — Practica (fondo oscuro SECONDARY)
```
Fondo: SECONDARY (1B4F72)
Badge superior: rectangulo ACCENT, texto "PRACTICA", Calibri Bold 12pt, TEXT_DARK
Titulo: Calibri Bold 28pt, ACCENT
Herramientas: iconos + nombre en cajas blancas semitransparentes
Pasos: numerados, Calibri 15pt, TEXT_LIGHT
```

### Slide — Cierre / Resumen (fondo oscuro PRIMARY)
```
Fondo: PRIMARY (0D1B2A)
Titulo: "Puntos Clave" — Calibri Bold 28pt, ACCENT
Lista de 3-5 puntos: icono check (FaCheckCircle) verde + texto
CTA: "Siguiente Bloque:" + nombre del proximo, box con borde ACCENT
```

## Iconos (react-icons)

Usar exclusivamente FontAwesome (fa) o Material Design (md):

```javascript
// Instalacion
npm install -g react-icons react react-dom sharp

// Librerias permitidas
const { FaBrain, FaRobot, FaBolt, FaRoute, FaChartLine } = require("react-icons/fa");
const { MdElectricCar, MdBatteryChargingFull, MdNetworkCheck } = require("react-icons/md");
```

### Iconos recomendados por bloque

| Bloque | Icono Principal | Iconos Secundarios |
|--------|----------------|-------------------|
| 01 ML | FaBrain | FaChartLine, FaTable, FaCheckCircle |
| 02 Vision | FaCamera | FaEye, FaCrosshairs, FaFilm |
| 03 Arquitectura | FaMicrochip | FaServer, FaNetworkWired, FaBolt |
| 04 Bateria | MdBatteryChargingFull | FaThermometerHalf, FaChartArea |
| 05 Carga | MdEvStation | FaPlug, FaSolarPanel, FaWifi |
| 06 Rutas | FaRoute | FaMapMarkerAlt, FaTruck, FaClock |
| 07 Trafico | FaTrafficLight | FaCar, FaUsers, FaBrain |
| 08 CARLA | FaCarSide | FaLayerGroup, FaCogs, FaShieldAlt |

## Funcion Helper para Iconos (copiar en cada script)

```javascript
const React = require("react");
const ReactDOMServer = require("react-dom/server");
const sharp = require("sharp");

async function iconPng(IconComponent, color = "00D4FF", size = 256) {
  const svg = ReactDOMServer.renderToStaticMarkup(
    React.createElement(IconComponent, { color: `#${color}`, size: String(size) })
  );
  const buf = await sharp(Buffer.from(svg)).png().toBuffer();
  return "image/png;base64," + buf.toString("base64");
}
```

## Reglas de Calidad

- Margen minimo en bordes: 0.4"
- Espacio entre bloques de contenido: 0.3"
- Maximo 6 lineas de texto por caja
- Nunca texto sobre imagen sin overlay semitransparente
- Siempre verificar contraste: texto claro sobre fondo oscuro, texto oscuro sobre fondo claro
- No usar lineas decorativas bajo titulos
- No mezclar mas de 3 tamaños de fuente por slide
