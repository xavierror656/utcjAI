# Bloque 06 — Logistica y Optimizacion de Rutas

## Metadatos
```
Archivo de salida : Bloque06-Logistica-Rutas.pptx
Duracion          : 2 horas
Icono principal   : FaRoute (react-icons/fa)
Total de slides   : 10
```

---

## Slide 1 — Portada
```
Icono   : FaRoute, 00D4FF
Titulo  : "Logistica y Optimizacion de Rutas"
Subtitulo: "Encontrar el camino optimo con restriccion de bateria"
Imagen  : mapa con rutas trazadas, vista aerea ciudad
```

## Slide 2 — Indice
```
FaRoute         → "Vehicle Routing Problem (VRP)"
FaMapMarkerAlt  → "Restriccion de bateria en rutas"
FaCogs          → "Optimizacion Heuristica"
FaBrain         → "Introduccion a Reinforcement Learning"
FaMapSigns      → "Plataformas de Simulacion Visual"
FaFlask         → "Practica: Simulacion de Rutas"
```

## Slide 3 — Vehicle Routing Problem (VRP)
```
Tipo    : DEFINICION + DIAGRAMA
Fondo   : 0D1B2A
Titulo  : "VRP — El Problema Central de la Logistica"

Definicion:
  "Dado un deposito y N clientes, encontrar el conjunto de rutas de menor
  costo total tal que cada cliente sea visitado exactamente una vez"

Diagrama de grafo (nodos y aristas):
  Nodo central (deposito): cuadrado azul
  6-8 nodos cliente: circulos blancos numerados
  Aristas con pesos (distancias/tiempo)
  Rutas coloreadas diferentes para cada vehiculo

Variantes en EV:
  VRP basico             → Minimizar distancia
  EVRP (Electric VRP)    → + Restriccion de bateria
  EVRPTW                 → + Ventanas de tiempo
  Multi-depot EVRP       → + Multiples depositos y cargadores
```

## Slide 4 — Restriccion de Bateria
```
Tipo    : CONTENIDO + MAPA SIMULADO
Titulo  : "La Bateria Cambia las Reglas del VRP"

Mapa simulado (formas PptxGenJS):
  Nodos en posiciones fijas
  Ruta verde: ruta directa (sin recarga)
  Ruta cyan: ruta con desvio a estacion de carga
  Icono FaBolt en estacion de carga

Variables adicionales del EVRP:
  Nivel de carga inicial
  Consumo por km (variable segun carga y temperatura)
  Ubicacion y tiempo de carga en estaciones
  Umbral minimo de bateria al llegar al cliente

Caja warning:
  "Una ruta optima en distancia puede ser inviable energeticamente"
```

## Slide 5 — Optimizacion Heuristica
```
Tipo    : COMPARACION DE METODOS
Titulo  : "Como Resolver el VRP: Heuristicas"

Columna 1 — Fuerza Bruta
  Icono: FaTimes (rojo)
  "Evalua todas las permutaciones"
  "Inviable: 10 clientes = 3.6 millones de rutas"

Columna 2 — Greedy (Voraz)
  Icono: FaForward
  "Elige siempre el cliente mas cercano"
  "Rapido pero no optimo"

Columna 3 — Algoritmo Genetico
  Icono: FaDna
  "Evolucion de soluciones candidatas"
  "Buen balance calidad/velocidad"

Columna 4 — Simulated Annealing
  Icono: FaFire
  "Acepta soluciones peores con cierta probabilidad"
  "Escapa de minimos locales"

Columna 5 — RL (preview)
  Icono: FaBrain (00D4FF)
  "Agente aprende politica de ruteo"
  "Mejora con experiencia"
  Badge: "Bloque 07 → mas detalle"
```

## Slide 6 — Intro a Reinforcement Learning (Conceptual)
```
Tipo    : DIAGRAMA RL
Titulo  : "Reinforcement Learning — Aprender Haciendo"

Diagrama ciclo (circular):
  AGENTE → accion → ENTORNO → estado + recompensa → AGENTE

Terminologia basica:
  Agente     → El algoritmo que toma decisiones (nuestro rutificador)
  Entorno    → La red de clientes, distancias y baterias
  Estado     → Posicion actual, bateria, clientes pendientes
  Accion     → Ir al siguiente cliente o estacion de carga
  Recompensa → Negativa por distancia, positiva por entrega exitosa

Analogia:
  "Como un repartidor que aprende las mejores rutas con la experiencia diaria"
```

## Slide 7 — Plataformas de Simulacion Visual
```
Tipo    : HERRAMIENTAS
Titulo  : "Plataformas para Visualizar Rutas (sin codigo intensivo)"

Grid 2x2:
  Google OR-Tools
    Icono: FaGoogle
    "Libreria open-source de Google para VRP"
    "Python, documentacion extensa"
    Nivel: Intermedio

  OpenRouteService
    Icono: FaMap
    "API gratuita con mapa visual interactivo"
    "Ideal para demos sin codigo"
    Nivel: Basico

  OSRM + Leaflet
    Icono: FaLeaf
    "Motor de rutas open-source + mapa web"
    "Visual, interactivo, gratuito"
    Nivel: Basico-Intermedio

  SimPy (Python)
    Icono: FaCode
    "Simulacion de eventos discretos"
    "Flota de EV + logica de carga"
    Nivel: Intermedio

Badge: "Para la practica se recomienda OpenRouteService por ser el mas visual"
```

## Slide 8 — Metricas de una Solucion de Rutas
```
Tipo    : TABLA DE METRICAS
Titulo  : "Como Medir si una Ruta es Buena"

Tabla:
  Metrica                  | Descripcion                        | Meta
  Distancia total (km)     | Suma de todos los tramos           | Minimizar
  Tiempo total (min)       | Incluyendo tiempos de servicio     | Minimizar
  Consumo energetico (kWh) | kWh totales de la flota            | Minimizar
  Tasa de entrega          | Clientes atendidos / total         | Maximizar
  Violaciones de bateria   | Rutas que quedan sin carga         | = 0
  Tiempo de recarga        | Horas en estaciones de carga       | Minimizar
```

## Slide 9 — Practica
```
Titulo  : "Simulacion de Rutas con Restriccion de Bateria"

Plataforma recomendada: OpenRouteService + Python o interfaz web

Pasos:
  1. "Definir escenario: 1 deposito, 8 clientes, 2 estaciones de carga en Ciudad Juarez"
  2. "Calcular matriz de distancias entre todos los puntos"
  3. "Aplicar algoritmo greedy: ruta sin restriccion de bateria"
  4. "Agregar restriccion: EV con 150km de autonomia"
  5. "Comparar ruta greedy vs ruta con recargas obligatorias"
  6. "Visualizar ambas rutas en mapa interactivo"
  7. "Calcular diferencia en distancia, tiempo y consumo"
```

## Slide 10 — Cierre
```
5 checkpoints:
  1. "El VRP busca rutas optimas para una flota desde un deposito"
  2. "El EVRP agrega la restriccion de bateria y estaciones de recarga"
  3. "Las heuristicas (genetico, SA) dan buenas soluciones sin explorar todo el espacio"
  4. "RL aprende una politica de ruteo a traves de experiencia simulada"
  5. "Las metricas clave son: distancia, consumo y tasa de entrega sin violaciones de bateria"

Siguiente: "Bloque 07 — Trafico Inteligente y Sistemas Multiagente"
```

---

## Instrucciones para el Agente

Igual que bloques anteriores. Salida: `Bloque06-Logistica-Rutas.pptx`
