---
theme: default
title: "Bloque 07 — Trafico Inteligente y Sistemas Multiagente"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque 07
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
fonts:
  sans: 'Segoe UI'
---

# Bloque 07
## Trafico Inteligente y Sistemas Multiagente

IA coordinando vehiculos, semaforos y ciudad

<div class="abs-br m-6 text-xs text-gray-400">2 horas | Teoria + Practica</div>

<img src="/img/b07-intersection.jpg" class="absolute inset-0 w-full h-full object-cover opacity-20 -z-1" />

---
layout: default
---

# Contenido del Bloque

<div class="grid grid-cols-2 gap-6 mt-6">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Modelos Predictivos de Flujo Vehicular</div>
    <div class="text-sm">Predecir trafico para anticiparse</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Sistemas Multiagente (MAS)</div>
    <div class="text-sm">Muchos actores, una red coordinada</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">RL en Semaforos</div>
    <div class="text-sm">Semaforos que aprenden y se adaptan</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Coordinacion V2X</div>
    <div class="text-sm">El vehiculo habla con todo su entorno</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Simuladores de Trafico</div>
    <div class="text-sm">SUMO, CARLA, Mesa, CityFlow</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="badge-ev mb-2">PRACTICA</div>
    <div class="text-sm">Simulacion de interseccion inteligente con Mesa</div>
  </div>
</div>

---
layout: image-right
image: /img/b07-traffic-jam.jpg
---

# Predecir el Trafico para Anticiparse

<div class="mt-4 space-y-4 text-sm">
  <div v-click>
    <div class="text-accent font-bold mb-2">Variables del flujo vehicular:</div>
    <ul class="space-y-1 muted">
      <li>• Densidad (vehiculos/km)</li>
      <li>• Velocidad media (km/h)</li>
      <li>• Flujo (vehiculos/hora)</li>
      <li>• Relacion fundamental: <span class="font-mono text-accent">Q = k × v</span></li>
    </ul>
  </div>
  <div v-click>
    <div class="text-accent font-bold mb-2">Modelos predictivos:</div>
    <ul class="space-y-1">
      <li><span class="font-bold">LSTM</span> — prediccion a 15-60 min</li>
      <li><span class="font-bold">Regresion espaciotemporal</span> — incorpora ubicacion</li>
      <li><span class="font-bold">GNN</span> — red vial como grafo</li>
    </ul>
  </div>
  <div v-click class="card-ev p-3">
    <strong class="text-accent">Caso Ciudad Juarez:</strong> Puente internacional, Blvd Zaragoza, centros comerciales = puntos criticos
  </div>
</div>

---
layout: default
class: dark-slide
---

# Sistema Multiagente (MAS) — Muchos Actores, Una Red

<div class="grid grid-cols-2 gap-6 mt-4">
  <div>
    <div v-click class="border rounded p-3 mb-4 text-sm" style="border-color:#00D4FF;">
      Un sistema donde multiples agentes autonomos interactuan en un entorno compartido
    </div>
    <div v-click class="space-y-2 text-sm">
      <div class="font-bold text-accent mb-2">Propiedades del MAS:</div>
      <div><span class="text-accent font-bold">Autonomia</span> — cada agente toma decisiones propias</div>
      <div><span class="text-accent font-bold">Interaccion</span> — se coordinan o compiten</div>
      <div><span class="text-accent font-bold">Emergencia</span> — el comportamiento global surge de lo local</div>
    </div>
    <div v-click class="mt-4 card-ev p-3 text-sm italic">
      "Semaforos que se coordinan entre si para crear 'olas verdes' dinamicas"
    </div>
  </div>
  <div v-click class="space-y-3 text-sm">
    <div class="font-bold text-accent mb-2">Tipos de agentes en EV y trafico:</div>
    <div class="card-ev p-2 flex items-center gap-2"><mdi-car-electric class="inline" /> <span>Agente Vehiculo EV — toma rutas, carga</span></div>
    <div class="card-ev p-2 flex items-center gap-2"><mdi-traffic-light class="inline" /> <span>Agente Semaforo — controla flujo</span></div>
    <div class="card-ev p-2 flex items-center gap-2"><mdi-power-plug class="inline" /> <span>Agente Estacion Carga — gestiona cola</span></div>
    <div class="card-ev p-2 flex items-center gap-2"><mdi-walk class="inline" /> <span>Agente Peaton — cruces y seguridad</span></div>
    <div class="card-ev p-2 flex items-center gap-2"><mdi-map class="inline" /> <span>Agente Red Vial — estado de la malla</span></div>
  </div>
</div>

---
layout: default
---

# Semaforos que Aprenden con Reinforcement Learning

<div class="grid grid-cols-2 gap-6 mt-4">
  <div>
    <div v-click class="card-ev p-4 mb-4 text-sm">
      <div class="text-center mb-3">
        <div class="font-bold text-accent">CICLO RL EN INTERSECCION</div>
      </div>
      <div class="text-xs space-y-1">
        <div><span class="text-accent font-bold">AGENTE:</span> algoritmo RL del semaforo</div>
        <div><span class="text-accent font-bold">ACCION:</span> duracion de fase verde (5-120 seg)</div>
        <div><span class="text-accent font-bold">ENTORNO:</span> interseccion con N carriles y vehiculos</div>
        <div><span class="text-accent font-bold">ESTADO:</span> cola de vehiculos, tiempo de espera, peatones</div>
        <div class="success"><span class="font-bold">RECOMPENSA +:</span> reducir tiempo de espera</div>
        <div style="color:#ef4444;"><span class="font-bold">RECOMPENSA -:</span> congestion, accidente</div>
      </div>
    </div>
  </div>
  <div v-click class="space-y-3 text-sm">
    <div class="font-bold text-accent mb-2">Comparacion de estrategias:</div>
    <div class="card-ev p-3">
      <div class="font-bold muted">Semaforo fijo</div>
      <div class="text-xs">Ciclos predefinidos, sin adaptacion al trafico real</div>
    </div>
    <div class="card-ev p-3">
      <div class="font-bold warning">Semaforo reactivo</div>
      <div class="text-xs">Extiende verde si hay cola — regla simple</div>
    </div>
    <div class="card-ev p-3" style="border: 1px solid #00D4FF;">
      <div class="font-bold text-accent">Semaforo RL</div>
      <div class="text-xs">Aprende la politica optima segun condiciones</div>
    </div>
    <div class="border rounded p-2 text-xs text-center success" style="border-color:#10B981;">
      Estudios muestran 20-40% reduccion de espera con semaforos RL vs fijos
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# V2X: El Vehiculo Habla con Todo

<div class="grid grid-cols-2 gap-4 mt-6 text-sm">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-car-electric class="inline" />↔<mdi-car-electric class="inline" /> V2V — Vehicle to Vehicle</div>
    <div class="muted">Alertas de frenado brusco, posicion, velocidad relativa</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-car-electric class="inline" />↔<mdi-crane class="inline" /> V2I — Vehicle to Infrastructure</div>
    <div class="muted">Semaforos, senales, velocidad recomendada antes de cruce</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-car-electric class="inline" />↔<mdi-antenna class="inline" /> V2N — Vehicle to Network</div>
    <div class="muted">Actualizaciones de trafico en tiempo real, rerouting</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-car-electric class="inline" />↔<mdi-walk class="inline" /> V2P — Vehicle to Pedestrian</div>
    <div class="muted">Alertas a peatones con smartphone, cruce seguro</div>
  </div>
</div>

<div v-click class="mt-5 border rounded p-3 text-sm text-center" style="border-color:#00D4FF; color:#00D4FF;">
  El EV puede recibir senal del semaforo y ajustar velocidad para llegar en verde → ahorra energia al evitar aceleraciones y frenos innecesarios
</div>

---
layout: default
---

# Herramientas para Simular Trafico Inteligente

<div v-click class="mt-4 text-sm">

| Herramienta | Tipo | Gratis | Visual | EV Support |
|---|---|---|---|---|
| SUMO | Micro-simulacion | Si | Si | Si (plugin) |
| VISSIM | Profesional | No | Si | Parcial |
| CARLA | Autonomo/3D | Si | Si | Si |
| Mesa (Python) | Multiagente | Si | Basico | Configurable |
| CityFlow | ML-optimizado | Si | No | No |

</div>

<div v-click class="mt-4 text-center text-accent font-bold">SUMO y Mesa son los recomendados para esta practica</div>

---
layout: default
class: dark-slide
---

# Mesa — Framework de Simulacion Multiagente

<div class="grid grid-cols-2 gap-6 mt-4">
  <div v-click class="space-y-3 text-sm">
    <div class="card-ev p-3">Mesa es una libreria Python para modelar sistemas multiagente — ideal para simular intersecciones, flotas y redes de trafico</div>
    <div>
      <div class="text-accent font-bold mb-2">Componentes:</div>
      <div><span class="text-accent">Model</span> — Define el entorno (la interseccion)</div>
      <div><span class="text-accent">Agent</span> — Cada vehiculo o semaforo</div>
      <div><span class="text-accent">Schedule</span> — Controla el orden de activacion</div>
      <div><span class="text-accent">Grid</span> — Espacio donde los agentes se mueven</div>
    </div>
  </div>
  <div v-click>
    <div class="rounded p-4 text-sm" style="background:#1A1A2E; color:#00D4FF;">
      <div class="muted mb-2"># Pseudocodigo — Agente Semaforo</div>
      <div>class SemaforoAgent(Agent):</div>
      <div class="ml-4">def step(self):</div>
      <div class="ml-8 muted">cola = self.contar_vehiculos()</div>
      <div class="ml-8" style="color:#10B981;">self.fase = self.politica_rl(cola)</div>
    </div>
    <div class="mt-3 text-sm">
      <span class="text-accent font-bold">Instalacion:</span>
      <span class="font-mono ml-2">pip install mesa</span>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Practica — Bloque 07

<div class="badge-ev mb-4">PRACTICA</div>

## Simulacion Conceptual de Interseccion Inteligente

<div class="mb-3 text-sm muted">Escenario: interseccion 4 semaforos, 2 carriles por direccion, flujo variable</div>

<div class="space-y-2 mt-2">
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">1</div>
    <div class="text-sm">Instalar Mesa: <span class="font-mono">pip install mesa</span></div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">2</div>
    <div class="text-sm">Cargar cuaderno Colab con interseccion de 2×2 carriles</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">3</div>
    <div class="text-sm">Ejecutar con semaforos de ciclo fijo — medir tiempo de espera promedio</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">4</div>
    <div class="text-sm">Activar logica reactiva: extender verde si cola &gt; 5 vehiculos</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">5</div>
    <div class="text-sm">Comparar metricas: espera promedio, vehiculos atendidos por ciclo</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">6</div>
    <div class="text-sm">Discutir: como seria implementar esto con RL real</div>
  </div>
</div>

---
layout: center
class: dark-slide
---

# Puntos Clave — Bloque 07

<div class="space-y-3 mt-4 text-left max-w-xl mx-auto">
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Los modelos predictivos anticipan congestion para ajustar semaforos proactivamente</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Un MAS tiene multiples agentes autonomos que interactuan en un entorno compartido</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>RL entrena semaforos para maximizar el flujo y minimizar tiempos de espera</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>V2X permite comunicacion bidireccional entre EV e infraestructura</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Mesa permite simular intersecciones inteligentes con Python sin hardware real</span>
  </div>
</div>

<div class="mt-8 text-sm muted">
  > Siguiente: <span class="text-accent font-bold">Bloque 08 — Integracion Integral con CARLA</span>
</div>
