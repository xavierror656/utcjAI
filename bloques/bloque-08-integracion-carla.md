# Bloque 08 — Integracion del Sistema Integral de IA con CARLA

## Metadatos
```
Archivo de salida : Bloque08-Integracion-CARLA.pptx
Duracion          : 2 horas
Icono principal   : FaCarSide (react-icons/fa)
Total de slides   : 12
```

---

## Slide 1 — Portada
```
Icono   : FaCarSide, 00D4FF
Titulo  : "Integracion Integral de IA en Electromovilidad"
Subtitulo: "Validacion con CARLA — El Sistema Completo"
Badge   : "BLOQUE FINAL"
Imagen  : screenshot o representacion de simulacion de conduccion autonoma
```

## Slide 2 — Indice
```
FaLayerGroup    → "Integracion de los 7 modulos previos"
FaProjectDiagram→ "Interdependencia de variables"
FaCarSide       → "CARLA como entorno de validacion"
FaNetworkWired  → "Arquitectura del sistema completo"
FaChartBar      → "Analisis de impacto de variables criticas"
FaGraduationCap → "Proyecto Integrador Final"
FaFlask         → "Demo en CARLA"
```

## Slide 3 — Vision General: Los 8 Modulos Integrados
```
Tipo    : ARQUITECTURA CIRCULAR
Fondo   : 0D1B2A
Titulo  : "De Bloques Aislados a Sistema Integrado"

Diagrama circular con EV en centro:
  Centro: FaCarSide, 00D4FF, "EV INTELIGENTE"

  8 modulos alrededor (iconos de cada bloque):
  1. FaBrain        → "ML Fundamentos"    (arriba)
  2. FaCamera       → "Computer Vision"   (arriba-der)
  3. FaMicrochip    → "Chips/Deploy"      (der)
  4. FaBatteryFull  → "Gestion Energia"   (abajo-der)
  5. FaPlug         → "Carga Inteligente" (abajo)
  6. FaRoute        → "Rutas"             (abajo-izq)
  7. FaTrafficLight → "Trafico"           (izq)
  8. FaLayerGroup   → "Integracion CARLA" (arriba-izq)

Lineas de conexion entre todos los modulos
Nota: "Ninguno funciona de forma aislada — todos se alimentan entre si"
```

## Slide 4 — Interdependencia de Variables
```
Tipo    : DIAGRAMA DE DEPENDENCIAS
Titulo  : "Como se Afectan las Variables del Sistema"

Tabla de impacto cruzado (fila = causa, columna = efecto):

Variable          | SoC | Autonomia | Ruta | Velocidad | Semaforo
Temperatura alta  |  D  |    D     |  ~   |    ~      |    ~
Congestion vial   |  D  |    D     |  Re  |    D      |    A
Carga rapida frec.|  ~  |    D     |  ~   |    ~      |    ~
Ruta con rampas   |  D  |    D     |  ~   |    D      |    ~
Semaforo RL activo|  A  |    A     |  ~   |    A      |    D

Leyenda: A=mejora, D=empeora, ~=sin efecto directo, Re=reruta

Conclusion: "Una sola variable afecta todo el sistema — la IA debe integrar todas"
```

## Slide 5 — Que es CARLA
```
Tipo    : PRESENTACION DE HERRAMIENTA
Titulo  : "CARLA — Simulador de Conduccion Autonoma"

Descripcion:
  "CARLA (Car Learning to Act) es un simulador open-source"
  "Desarrollado por Intel Labs y la UPC Barcelona"
  "Entorno 3D fotorrealista para validar sistemas de conduccion autonoma"

Capacidades:
  FaCamera        → "Simula camaras RGB, profundidad, segmentacion"
  FaDotCircle     → "Simula LiDAR y Radar"
  FaCloudSun      → "Condiciones climaticas: lluvia, niebla, noche"
  FaCar           → "Trafico de vehiculos y peatones"
  FaBolt          → "Modelos de consumo electrico"
  FaCode          → "API Python para controlar todo"

Instalacion:
  "carla-simulator.org — version 0.9.x, Linux/Windows"
  "Google Colab con CARLA cloud es opcion para la practica"
```

## Slide 6 — Arquitectura del Sistema en CARLA
```
Tipo    : DIAGRAMA DE CAPAS TECNICO
Titulo  : "Como se Integran los Modulos en CARLA"

Diagrama de 5 capas:

CAPA 5 — DECISION Y CONTROL
  Planeacion de ruta (Bloque 06)
  Toma de decision energetica (Bloque 05)

CAPA 4 — PREDICCION
  SoC y autonomia estimada (Bloque 04)
  Prediccion de trafico (Bloque 07)

CAPA 3 — PERCEPCION
  CNN deteccion de objetos (Bloque 02)
  Fusion de sensores (Bloque 02)

CAPA 2 — SENSADO
  Camaras, LiDAR, Radar de CARLA (Bloque 02)
  Telemetria del vehiculo (Bloque 04)

CAPA 1 — HARDWARE SIMULADO
  Chips de inference CARLA (Bloque 03)
  BMS simulado (Bloque 04)

Flechas ascendentes y descendentes entre capas
```

## Slide 7 — Escenario de Demo: Un Viaje Completo
```
Tipo    : STORYTELLING
Titulo  : "Caso de Uso: EV Inteligente en Ciudad Simulada"

Narrativa en 6 pasos (iconos + texto):

1. FaMapMarkerAlt → "EV parte con SoC=85%, destino a 80km"
2. FaCamera       → "Vision CNN detecta trafico denso en ruta directa"
3. FaRoute        → "Sistema reruta por EVRP con parada en cargador"
4. FaTrafficLight → "Semaforos RL coordinan para dar ola verde al EV"
5. FaPlug         → "EV carga 20 min en estacion solar (precio bajo)"
6. FaCheckCircle  → "Llega al destino con SoC=42%, mision cumplida"

Imagen CARLA simulada en fondo: escena urbana con EV visible
```

## Slide 8 — Analisis de Variables Criticas
```
Tipo    : CHARTS MULTIPLES
Titulo  : "Impacto de Variables en el Sistema Completo"

Chart 1 (izq) — Autonomia vs Temperatura:
  Linea curva: a 25°C = 100%, a -10°C = 75%, a 45°C = 85%

Chart 2 (der) — SoC vs Congestion:
  Barras: ruta libre = 15kWh, congestion media = 22kWh, congestion severa = 31kWh

Interpretacion:
  "Temperatura y congestion son los dos factores mas impactantes en la autonomia real"
  "El sistema integrado debe compensar ambos en tiempo real"
```

## Slide 9 — Proyecto Integrador Final
```
Tipo    : INSTRUCCIONES PROYECTO
Fondo   : 0D1B2A
Badge   : "PROYECTO FINAL"
Titulo  : "Propuesta de Negocio con IA en Electromovilidad"

El alumno debe presentar:

1. FaQuestion    → "Problema a resolver (de cualquier bloque del curso)"
2. FaBrain       → "Tipo de modelo ML utilizado"
3. FaTable       → "Variables clave involucradas"
4. FaProjectDiagram → "Arquitectura general del sistema"
5. FaBolt        → "Impacto energetico y logistico"
6. FaChartLine   → "Viabilidad tecnica y oportunidad de mercado"

Formato:
  "Presentacion de 5-8 slides, 10 minutos de exposicion"
  "Puede basarse en 1 bloque o combinar varios"

Criterios de evaluacion:
  Comprension del problema | Justificacion del modelo | Coherencia de variables
  Arquitectura logica      | Impacto real estimado    | Creatividad/innovacion
```

## Slide 10 — Ideas de Proyectos (Inspiracion)
```
Tipo    : GRID DE IDEAS
Titulo  : "Ideas de Proyectos Integradores"

6 tarjetas (2 columnas):
  Sistema de mantenimiento predictivo de flotas EV
  Optimizacion de carga para taxis electricos en hora pico
  Plataforma de gestion de bateria para segunda vida
  Red de semaforos inteligentes con prioridad a EV
  App de autonomia adaptativa segun condiciones climaticas
  Sistema V2G para edificios corporativos en Ciudad Juarez

Nota: "Estos son ejemplos — el alumno puede proponer cualquier idea original"
```

## Slide 11 — Reflexion Final del Curso
```
Tipo    : CLOSING STATEMENT
Fondo   : 0D1B2A
Titulo  : "La Electromovilidad es un Sistema, no una Tecnologia" — 00D4FF

Texto central (Calibri 18pt, E8F4FD, centrado):
  "Cada bloque del curso representa una pieza de un ecosistema complejo.
  El valor real de la IA en electromovilidad no esta en los modelos individuales,
  sino en como se integran para tomar mejores decisiones, en tiempo real,
  con restricciones energeticas, logisticas y de seguridad simultaneas."

Linea final destacada (00D4FF, Bold 20pt):
  "El vehiculo electrico inteligente no solo conduce — percibe, predice, optimiza y aprende."

Imagen de fondo: ciudad futurista con EVs, baja opacidad
```

## Slide 12 — Cierre del Curso
```
Tipo    : CREDITOS / CIERRE
Titulo  : "Gracias — Resumen del Curso" — 00D4FF

Grid 2x4 con iconos de los 8 bloques (resumen visual):
  B01 FaBrain         B02 FaCamera
  B03 FaMicrochip     B04 FaBatteryFull
  B05 FaPlug          B06 FaRoute
  B07 FaTrafficLight  B08 FaCarSide

Texto: "IA Aplicada a la Electromovilidad — 16 horas — Ciudad Juarez"

Call to action:
  "El futuro de la movilidad se construye con datos, modelos y codigo."
```

---

## Instrucciones para el Agente

Igual que bloques anteriores.
Archivo de salida: `Bloque08-Integracion-CARLA.pptx`
Este bloque genera 12 slides en lugar de 10.
