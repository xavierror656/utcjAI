---
theme: penguin
title: "Bloque 06 — Logistica y Optimizacion de Rutas"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque 06
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
zoom: 0.85
fonts:
  sans: 'Segoe UI'
---

# Bloque 06
## Logistica y Optimizacion de Rutas

Encontrar el camino optimo con restriccion de bateria

<div class="abs-br m-6 text-xs text-gray-400">2 horas | Teoria + Practica</div>

<div class="absolute bottom-0 left-0 right-0 flex justify-center items-center gap-10 py-4 px-8" style="background: rgba(13,27,42,0.92); border-top: 1px solid rgba(0,212,255,0.4);">
  <img src="/logos/1%20EDITABLE%20LOGO%20RGB-2.png" class="h-12 object-contain" />
  <img src="/logos/2%20Demoinn_Imagotipo-Color-1-1024x775.png" class="h-20 object-contain" />
  <img src="/logos/3%206647a1a689bdd0ed43fb9444_Logo-Fundacion-Coppel.png" class="h-24 object-contain" />
  <img src="/logos/4%20changeandcodelogoTRANSblack.png" class="h-12 object-contain brightness-0 invert" />
</div>
<img src="/img/b06-map.jpg" class="absolute inset-0 w-full h-full object-cover opacity-20 -z-1" />

---
layout: default
---

# Contenido del Bloque

<div class="grid grid-cols-2 gap-6 mt-6">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Vehicle Routing Problem (VRP)</div>
    <div class="text-sm">El problema central de la logistica</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Restriccion de Bateria en Rutas</div>
    <div class="text-sm">EVRP — cuando la energia cambia las reglas</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Optimizacion Heuristica</div>
    <div class="text-sm">Greedy, Genetico, Simulated Annealing</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Intro a Reinforcement Learning</div>
    <div class="text-sm">Agente que aprende a rutear</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Plataformas de Simulacion Visual</div>
    <div class="text-sm">OR-Tools, OpenRouteService, SimPy</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="badge-ev mb-2">PRACTICA</div>
    <div class="text-sm">Simulacion de rutas con restriccion de bateria</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# VRP — El Problema Central de la Logistica

<div class="grid grid-cols-2 gap-6 mt-4">
  <div>
    <div v-click class="border rounded p-4 mb-4 text-sm" style="border-color:#00D4FF;">
      Dado un deposito y N clientes, encontrar el conjunto de rutas de menor costo total tal que cada cliente sea visitado exactamente una vez
    </div>
    <div v-click class="space-y-2 text-sm">
      <div class="font-bold text-accent mb-2">Variantes en EV:</div>
      <div class="flex items-start gap-2">
        <span class="muted">VRP basico</span>
        <span class="text-accent">→</span>
        <span>Minimizar distancia</span>
      </div>
      <div class="flex items-start gap-2">
        <span class="muted">EVRP</span>
        <span class="text-accent">→</span>
        <span>+ Restriccion de bateria</span>
      </div>
      <div class="flex items-start gap-2">
        <span class="muted">EVRPTW</span>
        <span class="text-accent">→</span>
        <span>+ Ventanas de tiempo</span>
      </div>
      <div class="flex items-start gap-2">
        <span class="muted">Multi-depot EVRP</span>
        <span class="text-accent">→</span>
        <span>+ Multiples depositos y cargadores</span>
      </div>
    </div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-3">Representacion del Grafo</div>
    <div class="relative h-40">
      <div class="absolute text-xs text-center" style="top:40%; left:43%;">
        <div class="w-8 h-8 rounded bg-accent text-primary font-bold flex items-center justify-center mx-auto">D</div>
        <div class="text-accent text-xs">deposito</div>
      </div>
      <div class="grid grid-cols-3 gap-2 text-xs text-center">
        <div class="card-ev p-1 rounded-full w-6 h-6 flex items-center justify-center mx-auto">1</div>
        <div class="card-ev p-1 rounded-full w-6 h-6 flex items-center justify-center mx-auto">2</div>
        <div class="card-ev p-1 rounded-full w-6 h-6 flex items-center justify-center mx-auto">3</div>
        <div class="card-ev p-1 rounded-full w-6 h-6 flex items-center justify-center mx-auto">4</div>
        <div></div>
        <div class="card-ev p-1 rounded-full w-6 h-6 flex items-center justify-center mx-auto">5</div>
        <div class="card-ev p-1 rounded-full w-6 h-6 flex items-center justify-center mx-auto">6</div>
        <div class="card-ev p-1 rounded-full w-6 h-6 flex items-center justify-center mx-auto">7</div>
        <div class="card-ev p-1 rounded-full w-6 h-6 flex items-center justify-center mx-auto">8</div>
      </div>
    </div>
  </div>
</div>

---
layout: default
---

# La Bateria Cambia las Reglas del VRP

<div class="grid grid-cols-2 gap-6 mt-4">
  <div v-click>
    <div class="text-accent font-bold mb-3">Variables adicionales del EVRP:</div>
    <ul class="space-y-2 text-sm">
      <li class="flex items-start gap-2"><span class="text-accent">•</span><span>Nivel de carga inicial del EV</span></li>
      <li class="flex items-start gap-2"><span class="text-accent">•</span><span>Consumo por km (variable segun carga y temperatura)</span></li>
      <li class="flex items-start gap-2"><span class="text-accent">•</span><span>Ubicacion y tiempo de carga en estaciones</span></li>
      <li class="flex items-start gap-2"><span class="text-accent">•</span><span>Umbral minimo de bateria al llegar al cliente</span></li>
    </ul>
    <div v-click class="mt-4 border rounded p-3 text-sm warning" style="border-color:#F59E0B;">
      Una ruta optima en distancia puede ser inviable energeticamente
    </div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-3">Comparacion de rutas</div>
    <div class="space-y-3 text-sm">
      <div class="border rounded p-2" style="border-color:#10B981; color:#10B981;">
        <mdi-circle class="inline" /> Ruta directa (sin recarga)<br>
        <span class="text-xs muted">100km | Solo si bateria alcanza</span>
      </div>
      <div class="border rounded p-2" style="border-color:#00D4FF; color:#00D4FF;">
        <mdi-circle class="inline" /> Ruta con desvio a cargador<br>
        <span class="text-xs muted">130km | Garantiza llegada</span>
      </div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Como Resolver el VRP: Heuristicas

<div class="grid grid-cols-5 gap-3 mt-6 text-center text-xs">
  <div v-click class="card-ev p-3">
    <div class="text-red-400 text-xl mb-1">✗</div>
    <div class="font-bold mb-2">Fuerza Bruta</div>
    <div class="muted">Evalua todas las permutaciones</div>
    <div class="mt-2" style="color:#ef4444;">10 clientes = 3.6M rutas</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent text-xl mb-1">⏩</div>
    <div class="font-bold mb-2">Greedy</div>
    <div class="muted">Elige siempre el cliente mas cercano</div>
    <div class="mt-2 muted">Rapido pero no optimo</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-dna class="text-green-400 text-xl mb-1" />
    <div class="font-bold mb-2">Genetico</div>
    <div class="muted">Evolucion de soluciones candidatas</div>
    <div class="mt-2 success">Buen balance calidad/velocidad</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-fire class="text-orange-400 text-xl mb-1" />
    <div class="font-bold mb-2">Sim. Annealing</div>
    <div class="muted">Acepta peores con probabilidad</div>
    <div class="mt-2 warning">Escapa de minimos locales</div>
  </div>
  <div v-click class="card-ev p-3" style="border: 1px solid #00D4FF;">
    <mdi-brain class="text-accent text-xl mb-1" />
    <div class="font-bold text-accent mb-2">RL</div>
    <div class="muted">Agente aprende politica</div>
    <div class="mt-2 text-accent">Mejora con experiencia</div>
    <div class="badge-ev mt-2">Bloque 07</div>
  </div>
</div>

---
layout: default
---

# Reinforcement Learning — Aprender Haciendo

<div class="grid grid-cols-2 gap-6 mt-4">
  <div v-click>
    <div class="card-ev p-4 mb-4">
      <div class="text-center text-sm">
        <div class="text-accent font-bold mb-2">CICLO DE APRENDIZAJE</div>
        <div class="flex items-center justify-center gap-2">
          <div class="border rounded px-2 py-1" style="border-color:#00D4FF;">AGENTE</div>
          <div class="text-accent text-xs">accion→<br>←estado+recompensa</div>
          <div class="border rounded px-2 py-1" style="border-color:#10B981;">ENTORNO</div>
        </div>
      </div>
    </div>
    <div class="text-sm muted italic">
      "Como un repartidor que aprende las mejores rutas con la experiencia diaria"
    </div>
  </div>
  <div v-click class="space-y-3 text-sm">
    <div class="font-bold text-accent mb-2">Terminologia en el VRP:</div>
    <div><span class="text-accent font-bold">Agente</span> — el algoritmo rutificador</div>
    <div><span class="text-accent font-bold">Entorno</span> — red de clientes, distancias, baterias</div>
    <div><span class="text-accent font-bold">Estado</span> — posicion actual, bateria, clientes pendientes</div>
    <div><span class="text-accent font-bold">Accion</span> — ir al siguiente cliente o estacion de carga</div>
    <div><span class="text-accent font-bold">Recompensa</span> — negativa por distancia, positiva por entrega exitosa</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Plataformas para Visualizar Rutas

<div class="grid grid-cols-2 gap-4 mt-4 text-sm">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-rhombus class="inline" /> Google OR-Tools</div>
    <div class="muted mb-1">Libreria open-source de Google para VRP</div>
    <div>Python, documentacion extensa</div>
    <div class="mt-2 text-xs"><span class="badge-ev">Intermedio</span></div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-map class="inline" /> OpenRouteService</div>
    <div class="muted mb-1">API gratuita con mapa visual interactivo</div>
    <div>Ideal para demos sin codigo intensivo</div>
    <div class="mt-2 text-xs"><span class="inline-block px-2 py-0.5 rounded" style="background:#10B981;color:#0D1B2A;">Basico</span></div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-leaf class="inline" /> OSRM + Leaflet</div>
    <div class="muted mb-1">Motor de rutas open-source + mapa web</div>
    <div>Visual, interactivo, gratuito</div>
    <div class="mt-2 text-xs"><span class="inline-block px-2 py-0.5 rounded" style="background:#1B4F72;">Basico-Intermedio</span></div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-language-python class="inline" /> SimPy (Python)</div>
    <div class="muted mb-1">Simulacion de eventos discretos</div>
    <div>Flota de EV + logica de carga</div>
    <div class="mt-2 text-xs"><span class="badge-ev">Intermedio</span></div>
  </div>
</div>

<div v-click class="mt-3 text-center text-sm text-accent">Para la practica se recomienda OpenRouteService por ser el mas visual</div>

---
layout: default
---

# Como Medir si una Ruta es Buena

<div v-click class="mt-4 text-sm">

| Metrica | Descripcion | Meta |
|---|---|---|
| Distancia total (km) | Suma de todos los tramos | Minimizar |
| Tiempo total (min) | Incluyendo tiempos de servicio | Minimizar |
| Consumo energetico (kWh) | kWh totales de la flota | Minimizar |
| Tasa de entrega | Clientes atendidos / total | Maximizar |
| Violaciones de bateria | Rutas que quedan sin carga | = 0 |
| Tiempo de recarga | Horas en estaciones de carga | Minimizar |

</div>

---
layout: default
class: dark-slide
---

# Practica — Bloque 06

<div class="badge-ev mb-4">PRACTICA</div>

## Simulacion de Rutas con Restriccion de Bateria

<div class="space-y-2 mt-4 text-sm">
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">1</div>
    <div>Definir escenario: 1 deposito, 8 clientes, 2 estaciones de carga en Ciudad Juarez</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">2</div>
    <div>Calcular matriz de distancias entre todos los puntos</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">3</div>
    <div>Aplicar algoritmo greedy: ruta sin restriccion de bateria</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">4</div>
    <div>Agregar restriccion: EV con 150km de autonomia</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">5</div>
    <div>Comparar ruta greedy vs ruta con recargas obligatorias</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">6</div>
    <div>Visualizar ambas rutas en mapa y calcular diferencia en distancia, tiempo y consumo</div>
  </div>
</div>

---
layout: center
class: dark-slide
---

# Puntos Clave — Bloque 06

<div class="space-y-3 mt-4 text-left max-w-xl mx-auto">
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>El VRP busca rutas optimas para una flota desde un deposito</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>El EVRP agrega la restriccion de bateria y estaciones de recarga</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Las heuristicas (genetico, SA) dan buenas soluciones sin explorar todo el espacio</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>RL aprende una politica de ruteo a traves de experiencia simulada</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Las metricas clave son: distancia, consumo y tasa de entrega sin violaciones de bateria</span>
  </div>
</div>

<div class="mt-8 text-sm muted">
  > Siguiente: <span class="text-accent font-bold">Bloque 07 — Trafico Inteligente y Sistemas Multiagente</span>
</div>
