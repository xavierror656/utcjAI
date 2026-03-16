# Bloque 02 — Percepcion del Entorno y Computer Vision

## Metadatos

```
Archivo de salida : Bloque02-Computer-Vision.pptx
Duracion          : 2 horas (1h teoria + 1h practica)
Icono principal   : FaCamera (react-icons/fa)
Color de acento   : 00D4FF
Total de slides   : 10
```

---

## Slide 1 — Portada

```
Tipo              : PORTADA
Fondo             : 0D1B2A
Barra izquierda   : 00D4FF, w=0.15, full height
Icono             : FaCamera, color 00D4FF, 1.2"x1.2", centrado x=4.4, y=0.6
Texto superior    : "BLOQUE 02" — 13pt, MUTED
Titulo            : "Percepcion del Entorno y Computer Vision" — Bold 34pt, 00D4FF
Subtitulo         : "Como los vehiculos electricos ven el mundo" — 18pt, E8F4FD
Imagen fondo      : auto con sensores / camara en carretera — x=0, y=3.5, w=10, h=2.1, transparency=65
```

---

## Slide 2 — Indice

```
Tipo              : AGENDA
Fondo             : F0F4F8
Barra superior    : 1B4F72, h=0.75
Titulo en barra   : "Contenido del Bloque"

Items 2 columnas:
Izquierda:
  FaCamera        → "Sensores: Camaras, LiDAR, Radar"
  FaBrain         → "Redes Neuronales Convolucionales (CNN)"
  FaCrosshairs    → "Deteccion de Objetos"

Derecha:
  FaRuler         → "Metricas: IoU, mAP, Latencia"
  FaCode          → "Roboflow y Modelos Pre-entrenados"
  FaFlask (WARNING) → "Practica: Deteccion en Tiempo Real"
```

---

## Slide 3 — Sensores en Electromovilidad

```
Tipo              : CONTENIDO 3 COLUMNAS
Fondo             : 0D1B2A
Titulo            : "Ojos del Vehiculo Autonomo" — Bold 28pt, 00D4FF, y=0.2

3 Tarjetas (fondo 1B4F72, sombra, w=2.8, y=0.9, h=4.2):

Tarjeta 1 — Camara
  Icono     : FaCamera, 00D4FF
  Titulo    : "Camara RGB"
  Alcance   : "Hasta 100m"
  Ventaja   : "Color, textura, semaforos, senales"
  Limitacion: "Sensible a lluvia y luz solar directa"
  Badge     : "VISION" — azul

Tarjeta 2 — LiDAR
  Icono     : FaDotCircle, 10B981
  Titulo    : "LiDAR"
  Alcance   : "Hasta 200m"
  Ventaja   : "Mapa 3D preciso, funciona de noche"
  Limitacion: "Costo elevado, afectado por niebla"
  Badge     : "3D PUNTO" — verde

Tarjeta 3 — Radar
  Icono     : FaBroadcastTower, F59E0B
  Titulo    : "Radar"
  Alcance   : "Hasta 300m"
  Ventaja   : "Velocidad de objetos, funciona con lluvia"
  Limitacion: "Baja resolucion, sin color"
  Badge     : "VELOCIDAD" — ambar

Nota inferior: "Los vehiculos modernos fusionan los 3 tipos de sensores — Sensor Fusion"
```

---

## Slide 4 — Fundamentos de CNN (Conceptual)

```
Tipo              : DIAGRAMA FLUJO HORIZONTAL
Fondo             : F0F4F8
Barra superior    : 1B4F72, h=0.75
Titulo en barra   : "Red Neuronal Convolucional (CNN) — Conceptual"

Diagrama horizontal simplificado (y=1.1, h=3.0):

[IMAGEN] → [CONVOLUCION] → [POOLING] → [FLATTEN] → [CLASIFICACION]
  x=0.3      x=2.2          x=4.1       x=6.0        x=7.9

Cada caja:
  Fondo     : FFFFFF, borde 1B4F72
  Icono     : pequeno en parte superior
  Nombre    : Bold 13pt, 1A1A2E
  Descripcion: 11pt, 64748B (1-2 lineas)

Descripcion de cada etapa:
  IMAGEN        → "Pixeles de entrada (camara, video)"
  CONVOLUCION   → "Detecta bordes, formas, texturas"
  POOLING       → "Reduce dimension, conserva lo importante"
  FLATTEN       → "Convierte mapa en vector"
  CLASIFICACION → "Probabilidades por clase"

Nota debajo del diagrama:
  Caja con borde 00D4FF: "No necesitas programar CNNs — los modelos pre-entrenados ya tienen estos pesos aprendidos"
```

---

## Slide 5 — Deteccion de Objetos

```
Tipo              : CONTENIDO CON IMAGEN
Fondo             : 0D1B2A
Barra superior    : ninguna
Titulo            : "Deteccion de Objetos en la Via" — Bold 28pt, 00D4FF, y=0.2

Seccion izquierda (x=0.4, y=0.9, w=5.0):
  Descripcion     : "Identifica y localiza multiples objetos simultaneamente"
  
  Tabla simple 2 columnas (clase + ejemplo en EV):
    Peatones   → Zona escolar, crucero
    Vehiculos  → Autos, motos, ciclistas
    Senales    → STOP, velocidad maxima
    Obstaculos → Conos, piedras, baches
    Semaforos  → Rojo/verde/amarillo

  Modelos populares:
    YOLO (You Only Look Once) — Bold
    MobileNet — liviano para edge
    EfficientDet — balance precision/velocidad

Imagen derecha (x=5.7, y=0.9, w=4.0, h=4.3):
  Foto de escena urbana / deteccion de objetos
  Overlay: rectangulos de colores simulando bounding boxes (formas PptxGenJS)
```

---

## Slide 6 — Metricas de Evaluacion en Vision

```
Tipo              : GRID 2x2
Fondo             : F0F4F8
Barra superior    : 1B4F72
Titulo en barra   : "Metricas: IoU, mAP y Latencia"

Tarjeta TL — IoU (Intersection over Union)
  Fondo   : FFFFFF, sombra
  Icono   : FaVectorSquare, 00D4FF
  Nombre  : "IoU"
  Formula : "Area de interseccion / Area de union"
  Escala  : "IoU > 0.5 = buena deteccion"
  Uso     : "Mide que tan bien encaja el bounding box"

Tarjeta TR — mAP
  Icono   : FaBullseye, 10B981
  Nombre  : "mAP (mean Average Precision)"
  Texto   : "Precision promedio para todas las clases"
  Escala  : "mAP@0.5 es el estandar en benchmarks"

Tarjeta BL — Latencia
  Icono   : FaClock, F59E0B
  Nombre  : "Latencia (ms)"
  Texto   : "Tiempo de inferencia por frame"
  Escala  : "< 30ms para aplicaciones en tiempo real (33fps)"

Tarjeta BR — Trade-off
  Icono   : FaBalanceScale, 1B4F72
  Nombre  : "Precision vs Velocidad"
  Texto   : "Mayor precision = mayor computo\nModelos ligeros para chips embebidos en EV"
```

---

## Slide 7 — Roboflow: Herramienta de Practica

```
Tipo              : HERRAMIENTAS
Fondo             : 1B4F72
Badge             : rectangulo 00D4FF, "HERRAMIENTAS DE PRACTICA"
Titulo            : "Roboflow + Modelos Pre-entrenados" — Bold 26pt, E8F4FD

Layout 2 columnas:

Columna izq — Roboflow
  Tarjeta FFFFFF:
  Icono   : FaCloud, F59E0B
  Nombre  : "Roboflow"
  Lista:
    - Dataset de deteccion de objetos
    - Anotacion visual de imagenes
    - Entrenamiento con YOLO
    - API para inferencia en la nube
  URL     : "roboflow.com"

Columna der — Google Colab
  Tarjeta FFFFFF:
  Icono   : FaCode, naranja
  Nombre  : "Google Colab"
  Lista:
    - Ejecutar modelo YOLO preentrenado
    - Cargar video o imagen propia
    - Visualizar detecciones con bounding boxes
    - Medir latencia e IoU
  Badge   : "Cuaderno proporcionado por instructor"
```

---

## Slide 8 — Pipeline de Vision en EV (Conceptual)

```
Tipo              : DIAGRAMA
Fondo             : 0D1B2A
Titulo            : "Del Pixel a la Decision" — Bold 28pt, 00D4FF

Diagrama flujo vertical-horizontal combinado:

[Sensor]    →  [Pre-proceso]  →  [Modelo CNN]  →  [Post-proceso]  →  [Actuacion]
Camara RGB     Resize, norm.     Inferencia        NMS, filtrado      Freno, giro

Debajo de cada caja, nota de relevancia en EV:
  Sensor      : "30-60 fps, 1080p minimo para deteccion fiable"
  Pre-proceso : "Normalizacion 0-1, resize a 640x640 (YOLO)"
  Modelo CNN  : "Ejecuta en chip de inferencia (ej. Tesla HW)"
  Post-proceso: "Non-Max Suppression elimina duplicados"
  Actuacion   : "Señal a frenos, direccion, advertencia"

Imagen fondo baja opacidad: camara apuntando a carretera
```

---

## Slide 9 — Practica del Bloque

```
Tipo              : PRACTICA
Fondo             : 0D1B2A
Badge             : "PRACTICA — BLOQUE 02"
Titulo            : "Deteccion en Tiempo Real con Modelo Pre-entrenado"

Pasos:
  1. FaCloud     → "Crear cuenta gratuita en Roboflow"
  2. FaDownload  → "Cargar dataset publico de trafico urbano"
  3. FaPlay      → "Abrir cuaderno en Google Colab y ejecutar celda por celda"
  4. FaImage     → "Probar el modelo con una foto o video propio"
  5. FaChartBar  → "Registrar IoU, mAP y latencia obtenida"
  6. FaComment   → "Discutir: que objetos detecta bien, cuales falla"

Herramientas:
  "Roboflow"  |  "Google Colab"  |  "Modelo YOLO pre-entrenado"
```

---

## Slide 10 — Cierre

```
Tipo              : CIERRE
Fondo             : 0D1B2A
Barra izquierda   : 00D4FF
Titulo            : "Puntos Clave del Bloque 02" — Bold 28pt, 00D4FF

5 checkpoints (FaCheckCircle verde):
  1. "Camaras, LiDAR y Radar son los sensores principales en vehiculos autonomos"
  2. "Las CNN extraen caracteristicas visuales jerarquicamente"
  3. "IoU mide precision espacial, mAP mide precision por clase"
  4. "La latencia determina si un modelo es viable en tiempo real"
  5. "Roboflow y YOLO permiten deteccion sin ser experto en deep learning"

Siguiente bloque:
  Texto acento: "Bloque 03 — Arquitectura de Sistemas y Deployment"
```

---

## Instrucciones para el Agente

1. Leer `config/design-system.md` y `config/image-guidelines.md`
2. Generar `build/scripts/bloque-02.js`
3. Ejecutar y verificar igual que el Bloque 01
4. Salida: `Bloque02-Computer-Vision.pptx`
