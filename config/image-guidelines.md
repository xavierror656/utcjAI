# Guia de Imagenes

## Estrategia de Imagenes

Cada slide de contenido debe tener al menos una imagen relevante. Se usan tres fuentes:

1. **Unsplash** (preferida) — imagenes de alta calidad, libres de uso
2. **Wikimedia Commons** — diagramas tecnicos y esquemas
3. **Placeholder de color** — fallback si la imagen no carga

## URLs de Imagenes por Bloque

### Bloque 01 — Machine Learning Fundamentos

```
Diagrama ML tipos:
https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/Camponotus_flavomarginatus_ant.jpg/320px-Camponotus_flavomarginatus_ant.jpg

Auto electrico / dataset:
https://images.unsplash.com/photo-1593941707882-a5bba14938c7?w=800&q=80

Overfitting grafico:
https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&q=80
```

### Bloque 02 — Computer Vision

```
Camara en auto:
https://images.unsplash.com/photo-1545048702-79362596cdc9?w=800&q=80

LiDAR visualizacion:
https://images.unsplash.com/photo-1617791160505-6f00504e3519?w=800&q=80

Deteccion de objetos:
https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800&q=80
```

### Bloque 03 — Arquitectura y Chips

```
Chip / semiconductores:
https://images.unsplash.com/photo-1518770660439-4636190af475?w=800&q=80

Tesla FSD Computer:
https://images.unsplash.com/photo-1617788138017-80ad40651399?w=800&q=80

Data center / GPU:
https://images.unsplash.com/photo-1597852074816-d933c7d2b988?w=800&q=80
```

### Bloque 04 — Gestion de Energia y Baterias

```
Bateria EV:
https://images.unsplash.com/photo-1593941707874-ef25b8b4a92b?w=800&q=80

BMS diagram (generico):
https://images.unsplash.com/photo-1581092918056-0c4c3acd3789?w=800&q=80

Serie de tiempo / grafica:
https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&q=80
```

### Bloque 05 — Infraestructura de Carga

```
Estacion de carga EV:
https://images.unsplash.com/photo-1593941707882-a5bba14938c7?w=800&q=80

Smart grid / red electrica:
https://images.unsplash.com/photo-1473341304170-971dccb5ac1e?w=800&q=80

Panel solar:
https://images.unsplash.com/photo-1509391366360-2e959784a276?w=800&q=80
```

### Bloque 06 — Logistica y Rutas

```
Mapa de rutas / GPS:
https://images.unsplash.com/photo-1524661135-423995f22d0b?w=800&q=80

Flota de vehiculos:
https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800&q=80

Optimizacion / grafo:
https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&q=80
```

### Bloque 07 — Trafico y Multiagente

```
Interseccion de trafico:
https://images.unsplash.com/photo-1449824913935-59a10b8d2000?w=800&q=80

Semaforo inteligente:
https://images.unsplash.com/photo-1543083477-4f785aeafaa9?w=800&q=80

Ciudad inteligente:
https://images.unsplash.com/photo-1573804633927-bfcbcd909acd?w=800&q=80
```

### Bloque 08 — Integracion CARLA

```
Simulacion autonoma:
https://images.unsplash.com/photo-1555949963-aa79dcee981c?w=800&q=80

Auto autonomo sensors:
https://images.unsplash.com/photo-1617791160505-6f00504e3519?w=800&q=80

Integracion sistema:
https://images.unsplash.com/photo-1518770660439-4636190af475?w=800&q=80
```

## Como Usar las Imagenes en PptxGenJS

```javascript
// Directo por URL (la forma mas sencilla)
slide.addImage({
  path: "https://images.unsplash.com/photo-XXXXX?w=800&q=80",
  x: 5.5, y: 0.9, w: 4.0, h: 2.8,
  sizing: { type: "cover", w: 4.0, h: 2.8 }
});

// Con overlay semitransparente sobre la imagen (para texto encima)
// Primero agregar imagen, luego shape semitransparente
slide.addImage({ path: URL, x: 0, y: 3, w: 10, h: 2.5 });
slide.addShape(pres.shapes.RECTANGLE, {
  x: 0, y: 3, w: 10, h: 2.5,
  fill: { color: "0D1B2A", transparency: 40 }
});
// Luego el texto encima
```

## Fallback si la Imagen Falla

Si una URL no carga, usar un rectangulo de color con icono:

```javascript
// Placeholder visual
slide.addShape(pres.shapes.RECTANGLE, {
  x: 5.5, y: 0.9, w: 4.0, h: 2.8,
  fill: { color: "1B4F72" }
});
// Icono centrado como sustituto
slide.addImage({ data: await iconPng(FaCamera, "00D4FF", 256), x: 7.0, y: 1.5, w: 1.0, h: 1.0 });
```

## Notas

- Siempre agregar `?w=800&q=80` a URLs de Unsplash para optimizar peso
- Las imagenes se cargan en tiempo de generacion del .pptx, no en tiempo de presentacion
- Mantener proporcion 16:9 en imagenes que ocupen areas grandes
- Para diagramas tecnicos, preferir fondo oscuro con imagen como accent lateral
