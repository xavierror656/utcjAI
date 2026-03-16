# Bloque 03 — Arquitectura de Sistemas de IA y Deployment

## Metadatos

```
Archivo de salida : Bloque03-Arquitectura-Deployment.pptx
Duracion          : 2 horas (1h teoria + 1h practica)
Icono principal   : FaMicrochip (react-icons/fa)
Color de acento   : 00D4FF
Total de slides   : 10
```

---

## Slide 1 — Portada

```
Tipo    : PORTADA
Icono   : FaMicrochip, 00D4FF
Titulo  : "Arquitectura de Sistemas de IA y Deployment"
Subtitulo: "Del modelo entrenado al chip en el vehiculo"
Imagen  : chip / GPU / data center, baja opacidad fondo
```

---

## Slide 2 — Indice

```
Items:
  FaCogs          → "Pipeline de Machine Learning"
  FaMicrochip     → "Chips de Infoentretenimiento vs Conduccion Autonoma"
  FaBolt          → "FLOPS: Que son y por que importan"
  FaMapSigns      → "Casos de Uso por Chip"
  FaBatteryHalf   → "Consumo Energetico por Escenario"
  FaFlask         → "Practica: Analisis de Chips y Escenarios"
```

---

## Slide 3 — Pipeline de Machine Learning

```
Tipo    : DIAGRAMA HORIZONTAL COMPLETO
Fondo   : 0D1B2A
Titulo  : "Pipeline ML — Del Dato al Modelo en Produccion"

8 etapas en flujo horizontal con iconos y flechas:

[Recoleccion] → [Limpieza] → [EDA] → [Feature Eng.] → [Modelo] → [Evaluacion] → [Deployment] → [Monitoreo]

Colores de etapas:
  Recoleccion     : 1B4F72
  Limpieza        : 1B4F72
  EDA             : 1B4F72
  Feature Eng.    : 1B4F72
  Modelo          : 00D4FF (highlight — etapa central)
  Evaluacion      : 1B4F72
  Deployment      : 10B981 (highlight — meta)
  Monitoreo       : 1B4F72

Nota en caja debajo: "En EV el monitoreo es critico — el modelo debe funcionar con datos de temperatura, bateria y trafico en tiempo real"
```

---

## Slide 4 — Chips: Infoentretenimiento vs Conduccion Autonoma

```
Tipo    : COMPARACION 2 COLUMNAS
Fondo   : F0F4F8
Titulo  : "Dos Mundos, Dos Chips"

Columna izquierda — Chip de Infoentretenimiento
  Fondo tarjeta: FFFFFF
  Icono       : FaTabletAlt, color 1B4F72
  Nombre      : "Infotainment SoC"
  Ejemplos    : "Qualcomm Snapdragon, NVIDIA Tegra"
  Tareas:
    - Navegacion GPS y mapas
    - Reproduccion multimedia
    - Asistente de voz (natural language)
    - Conectividad (WiFi, Bluetooth, 5G)
    - Apps del tablero
  FLOPS tip   : "1-10 TOPS — carga moderada"
  Badge       : color 1B4F72 — "INTERFAZ"

Columna derecha — Chip de Conduccion Autonoma
  Icono       : FaCar, color 00D4FF
  Nombre      : "FSD Computer / Autopilot SoC"
  Ejemplos    : "Tesla FSD Chip, NVIDIA DRIVE Orin"
  Tareas:
    - Percepcion en tiempo real (CNN)
    - Fusion de sensores (camara+lidar+radar)
    - Planificacion de trayectoria
    - Toma de decisiones (RL)
    - Respuesta en < 10ms
  FLOPS tip   : "100-1000+ TOPS — carga extrema"
  Badge       : color 00D4FF — "AUTONOMIA"
```

---

## Slide 5 — Que son los FLOPS

```
Tipo    : CONTENIDO EXPLICATIVO
Fondo   : 0D1B2A
Titulo  : "FLOPS: La Unidad de Poder de Computo" — Bold 28pt, 00D4FF

Definicion (caja centrada con borde 00D4FF):
  "FLOP = Floating Point Operation (operacion de punto flotante)"
  "FLOPS = Operaciones por segundo que puede ejecutar un chip"

Tabla de escala (fondo 1B4F72):
  GFLOPS = 10^9  FLOPS → Smartphone clasico
  TFLOPS = 10^12 FLOPS → GPU gaming
  TOPS   = 10^12 Ops   → Chips de inferencia IA

Ejemplos concretos:
  Qualcomm 8155    →  8  TOPS  → Infotainment
  Tesla FSD Chip 1 → 144 TOPS  → Conduccion autonoma nivel 2-3
  NVIDIA DRIVE Orin→ 254 TOPS  → Conduccion autonoma nivel 4
  Tesla Dojo       → >1 PFLOPS → Entrenamiento en la nube

Nota clave:
  Caja ambar: "Mas FLOPS = mas calor y mas consumo electrico — hay que balancear"
```

---

## Slide 6 — Como Elegir el Chip Correcto

```
Tipo    : TABLA DE DECISION
Fondo   : F0F4F8
Barra superior: 1B4F72
Titulo  : "Seleccion de Chip por Caso de Uso"

Tabla (5 columnas):
  Caso de Uso | Chip Tipo | TOPS Requeridos | Consumo W | Ejemplo Real

Filas:
  Navegacion GPS          | Infotainment  | 1-5    | 3-8W   | Snapdragon 8155
  Reconocimiento de voz   | Infotainment  | 2-8    | 3-8W   | Snapdragon 8155
  Deteccion de peatones   | Autonomia     | 50+    | 15-30W | Tesla FSD / DRIVE Xavier
  Fusion sensor completa  | Autonomia     | 100+   | 30-65W | DRIVE Orin
  Conduccion nivel 4      | Autonomia     | 200+   | 65W+   | DRIVE Thor / FSD Chip 3

Colores de fila alternados: F0F4F8 / FFFFFF
Header fila: 1B4F72, texto blanco
```

---

## Slide 7 — Consumo por Escenario (Datos)

```
Tipo    : CHART DE BARRAS + TEXTO
Fondo   : 0D1B2A
Titulo  : "Consumo Energetico por Escenario" — Bold 28pt, 00D4FF

Chart de barras horizontales (izquierda, w=5.5, h=4.0):
  Labels : ["Infotainment", "ADAS Basico", "Autopilot", "Full FSD", "Entrenamiento (Dojo)"]
  Values : [8, 25, 45, 65, 1200]
  Color  : escala de azul a cyan

Texto derecho (x=6.0, y=1.0):
  Interpretacion:
    "El FSD consume ~8x mas que infotainment"
    "El entrenamiento en la nube es 1000x mas intensivo"
  
  Implicacion para EV:
    Caja borde 00D4FF:
    "El chip de autonomia representa hasta el 3-5% del consumo total de la bateria en conduccion activa"
```

---

## Slide 8 — Arquitectura Completa de un EV con IA

```
Tipo    : DIAGRAMA DE ARQUITECTURA
Fondo   : 1B4F72
Titulo  : "Arquitectura de IA en un EV Moderno" — Bold 26pt, E8F4FD

Diagrama capas (apiladas verticalmente):

Capa 1 (arriba) — NUBE / SERVIDOR
  [Entrenamiento de modelos] [Actualizaciones OTA] [Telemetria]

Capa 2 — CONECTIVIDAD
  [5G / WiFi] [V2X (Vehicle to Everything)]

Capa 3 — CHIP INFOENTRETENIMIENTO
  [Mapas] [Voz] [Apps] [Display]

Capa 4 — CHIP CONDUCCION AUTONOMA (highlight en 00D4FF)
  [Percepcion] [Planificacion] [Control]

Capa 5 (abajo) — HARDWARE / SENSORES
  [Camaras] [LiDAR] [Radar] [BMS] [CAN Bus]

Flechas bidireccionales entre capas
```

---

## Slide 9 — Practica del Bloque

```
Tipo    : PRACTICA
Titulo  : "Analisis de Chips y Escenarios Hipoteticos"

Actividad:
  Descripcion: "Investigar y comparar chips reales para distintos escenarios de electromovilidad"

Pasos:
  1. FaSearch    → "Buscar especificaciones de: Snapdragon 8155, Tesla FSD Chip 3, NVIDIA DRIVE Orin"
  2. FaTable     → "Crear tabla comparativa: TOPS, consumo W, temperatura maxima"
  3. FaMapMarked → "Asignar cada chip al escenario mas adecuado de la lista del Slide 6"
  4. FaCalculator→ "Calcular consumo estimado de IA en un viaje de 100km a 60 km/h"
  5. FaComments  → "Discutir: cuanto impacta la IA en la autonomia total del vehiculo"

Entregable:
  Caja: "Tabla comparativa + respuesta al calculo de impacto en autonomia"
```

---

## Slide 10 — Cierre

```
Tipo    : CIERRE
Titulo  : "Puntos Clave del Bloque 03"

5 checkpoints:
  1. "El pipeline ML va de datos crudos hasta un modelo monitoreado en produccion"
  2. "Infotainment y conduccion autonoma requieren chips con ordenes de magnitud diferentes"
  3. "FLOPS/TOPS miden la capacidad de computo — mas = mas caro y mas calor"
  4. "La eleccion del chip impacta directamente en el consumo y la autonomia del EV"
  5. "Los chips de autonomia evolucionan cada 2-3 anos — Tesla, NVIDIA y Qualcomm lideran"

Siguiente: "Bloque 04 — Gestion Inteligente de Energia y Baterias"
```

---

## Instrucciones para el Agente

Igual que Bloque 01/02. Salida: `Bloque03-Arquitectura-Deployment.pptx`
