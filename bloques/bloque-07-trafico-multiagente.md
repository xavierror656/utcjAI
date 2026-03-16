# Bloque 07 — Trafico Inteligente y Sistemas Multiagente

## Metadatos
```
Archivo de salida : Bloque07-Trafico-Multiagente.pptx
Duracion          : 2 horas
Icono principal   : FaTrafficLight (react-icons/fa)
Total de slides   : 10
```

---

## Slide 1 — Portada
```
Icono   : FaTrafficLight, 00D4FF
Titulo  : "Trafico Inteligente y Sistemas Multiagente"
Subtitulo: "IA coordinando vehiculos, semaforos y ciudad"
Imagen  : interseccion aerea nocturna con luces de trafico
```

## Slide 2 — Indice
```
FaChartArea     → "Modelos Predictivos de Flujo Vehicular"
FaUsers         → "Sistemas Multiagente"
FaTrafficLight  → "Aprendizaje por Refuerzo en Semaforos"
FaCar           → "Coordinacion V2X"
FaDesktop       → "Simuladores de Trafico"
FaFlask         → "Practica: Simulacion Interseccion Inteligente"
```

## Slide 3 — Modelos de Flujo Vehicular
```
Tipo    : CONTENIDO + GRAFICO
Titulo  : "Predecir el Trafico para Anticiparse"

Variables del flujo:
  Densidad (vehiculos/km)
  Velocidad media (km/h)
  Flujo (vehiculos/hora)
  Relacion fundamental: Q = k * v

Modelos predictivos:
  Series de tiempo (LSTM)     → prediccion a 15-60 min
  Regresion espaciotemporal   → incorpora ubicacion
  GNN (Graph Neural Networks) → red vial como grafo

Grafico de linea:
  Prediccion de congestion en horario pico
  Eje X: 6am-10pm, Eje Y: vehiculos/hora
  Zona roja: congestion, zona verde: fluido

Caso Ciudad Juarez:
  "Puente internacional, Blvd Zaragoza, centros comerciales = puntos criticos"
```

## Slide 4 — Sistemas Multiagente
```
Tipo    : DIAGRAMA DE AGENTES
Fondo   : 0D1B2A
Titulo  : "Sistema Multiagente (MAS) — Muchos Actores, Una Red"

Definicion:
  "Un sistema donde multiples agentes autonomos interactuan en un entorno compartido"

Tipos de agentes en EV y trafico:
  Agente Vehiculo EV    → FaCar
  Agente Semaforo       → FaTrafficLight
  Agente Estacion Carga → FaPlug
  Agente Peaton         → FaWalking
  Agente Red Vial       → FaMapMarkedAlt

Propiedades:
  Autonomia    → cada agente toma decisiones propias
  Interaccion  → se coordinan o compiten
  Emergencia   → el comportamiento global surge de lo local

Ejemplo: "Semaforos que se coordinan entre si para crear 'olas verdes' dinamicas"
```

## Slide 5 — RL en Semaforos
```
Tipo    : DIAGRAMA RL APLICADO
Titulo  : "Semaforos que Aprenden con Reinforcement Learning"

Diagrama RL especifico:
  AGENTE (RL)    → accion: duracion de fase verde (5-120 seg)
  ENTORNO        → interseccion con N carriles y vehiculos
  ESTADO         → cola de vehiculos, tiempo de espera, demanda peatonal
  RECOMPENSA     → positiva: reducir tiempo de espera
                   negativa: congestion, accidente, semaforo ignorado

Comparacion:
  Semaforo fijo    → ciclos predefinidos, sin adaptacion
  Semaforo reactivo→ extiende verde si hay cola (regla simple)
  Semaforo RL      → aprende la politica optima segun condiciones

Benchmark:
  "Estudios muestran 20-40% reduccion de espera con semaforos RL vs fijos"
```

## Slide 6 — Coordinacion V2X
```
Tipo    : MAPA CONCEPTUAL
Titulo  : "V2X: El Vehiculo Habla con Todo"

V2X abarca:
  V2V (Vehicle to Vehicle)        → alertas de frenado, posicion
  V2I (Vehicle to Infrastructure) → semaforos, senales, velocidad recomendada
  V2N (Vehicle to Network)        → actualizaciones trafico en tiempo real
  V2P (Vehicle to Pedestrian)     → alertas a peatones con smartphone

Diagrama: auto en centro con flechas a 4 destinos (V2V, V2I, V2N, V2P)

Beneficio en EV:
  "El EV puede recibir senal de semaforo y ajustar velocidad para llegar en verde
  → ahorra energia al evitar aceleraciones y frenos innecesarios"
```

## Slide 7 — Simuladores de Trafico
```
Tipo    : TABLA COMPARATIVA
Titulo  : "Herramientas para Simular Trafico Inteligente"

Tabla:
  Herramienta  | Tipo              | Gratis | Visual | EV Support
  SUMO         | Micro-simulacion  | Si     | Si     | Si (plugin)
  VISSIM       | Profesional       | No     | Si     | Parcial
  CARLA        | Autonomo/3D       | Si     | Si     | Si
  Mesa (Python)| Multiagente       | Si     | Basico | Configurable
  CityFlow     | ML-optimizado     | Si     | No     | No

Badge: "SUMO y Mesa son los recomendados para esta practica"
```

## Slide 8 — Mesa: Simulacion Multiagente en Python
```
Tipo    : HERRAMIENTA DETALLE
Titulo  : "Mesa — Framework de Simulacion Multiagente"

Descripcion:
  "Mesa es una libreria Python para modelar sistemas multiagente"
  "Ideal para simular intersecciones, flotas y redes de trafico"

Componentes:
  Model   → Define el entorno (la interseccion)
  Agent   → Cada vehiculo o semaforo
  Schedule→ Controla el orden de activacion
  Grid    → Espacio donde los agentes se mueven

Codigo conceptual (caja estilizada):
  class SemaforoAgent(Agent):
    def step(self):
      cola = self.contar_vehiculos()
      self.fase = self.politica_rl(cola)

Instalacion:
  pip install mesa
```

## Slide 9 — Practica
```
Titulo  : "Simulacion Conceptual de Interseccion Inteligente"

Escenario:
  "Interseccion con 4 semaforos, 2 carriles por direccion"
  "Flujo de vehiculos variable (hora pico vs no pico)"

Pasos:
  1. "Instalar Mesa: pip install mesa"
  2. "Cargar cuaderno Colab con interseccion de 2x2 carriles"
  3. "Ejecutar con semaforos de ciclo fijo — medir tiempo de espera"
  4. "Activar logica reactiva: extender verde si cola > 5 vehiculos"
  5. "Comparar metricas: espera promedio, vehiculos atendidos por ciclo"
  6. "Discutir: como seria implementar esto con RL real"

Herramientas: Mesa + Matplotlib + Google Colab
```

## Slide 10 — Cierre
```
5 checkpoints:
  1. "Los modelos predictivos anticipan congestion para ajustar semaforos proactivamente"
  2. "Un MAS tiene multiples agentes autonomos que interactuan en un entorno compartido"
  3. "RL entrena semaforos para maximizar el flujo y minimizar tiempos de espera"
  4. "V2X permite comunicacion bidireccional entre EV e infraestructura"
  5. "Mesa permite simular intersecciones inteligentes con Python sin hardware real"

Siguiente: "Bloque 08 — Integracion Integral con CARLA"
```

---

## Instrucciones para el Agente

Igual que bloques anteriores. Salida: `Bloque07-Trafico-Multiagente.pptx`
