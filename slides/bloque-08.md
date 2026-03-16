---
theme: default
title: "Bloque 08 — Integracion Integral de IA con CARLA"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque 08
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
fonts:
  sans: 'Segoe UI'
---

# Bloque 08
## Integracion Integral de IA en Electromovilidad

Validacion con CARLA — El Sistema Completo

<div class="badge-ev absolute top-8 right-8">BLOQUE FINAL</div>
<div class="abs-br m-6 text-xs text-gray-400">2 horas | Teoria + Demo</div>

<img src="/img/b08-autonomous.jpg" class="absolute inset-0 w-full h-full object-cover opacity-20 -z-1" />

---
layout: default
---

# Contenido del Bloque Final

<div class="grid grid-cols-2 gap-6 mt-6">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Integracion de los 7 Modulos</div>
    <div class="text-sm">Como se conectan todos los bloques del curso</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Interdependencia de Variables</div>
    <div class="text-sm">Como una variable afecta todo el sistema</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">CARLA como Entorno de Validacion</div>
    <div class="text-sm">Simulador 3D open-source para autonomia</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Arquitectura del Sistema Completo</div>
    <div class="text-sm">5 capas de integracion tecnica</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Analisis de Variables Criticas</div>
    <div class="text-sm">Temperatura y congestion — impacto cuantificado</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="badge-ev mb-2">PROYECTO FINAL</div>
    <div class="text-sm">Propuesta de negocio con IA en electromovilidad</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# De Bloques Aislados a Sistema Integrado

<div class="grid grid-cols-4 gap-3 mt-6 text-xs text-center">
  <div v-click class="card-ev p-3">
    <mdi-brain class="text-2xl mb-1" />
    <div class="text-accent font-bold">B01</div>
    <div class="muted">ML Fundamentos</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-camera class="text-2xl mb-1" />
    <div class="text-accent font-bold">B02</div>
    <div class="muted">Computer Vision</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-laptop class="text-2xl mb-1" />
    <div class="text-accent font-bold">B03</div>
    <div class="muted">Chips/Deploy</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-battery class="text-2xl mb-1" />
    <div class="text-accent font-bold">B04</div>
    <div class="muted">Gestion Energia</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-power-plug class="text-2xl mb-1" />
    <div class="text-accent font-bold">B05</div>
    <div class="muted">Carga Inteligente</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-map class="text-2xl mb-1" />
    <div class="text-accent font-bold">B06</div>
    <div class="muted">Rutas/Logistica</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-traffic-light class="text-2xl mb-1" />
    <div class="text-accent font-bold">B07</div>
    <div class="muted">Trafico MAS</div>
  </div>
  <div v-click class="card-ev p-3" style="border: 1px solid #00D4FF;">
    <mdi-car-electric class="text-2xl mb-1" />
    <div class="text-accent font-bold">B08</div>
    <div class="muted">Integracion CARLA</div>
  </div>
</div>

<div v-click class="mt-5 text-center text-sm text-accent border rounded p-2" style="border-color:#00D4FF;">
  Ninguno funciona de forma aislada — todos se alimentan entre si
</div>

---
layout: default
---

# Como se Afectan las Variables del Sistema

<div v-click class="mt-4 text-sm">

| Variable | SoC | Autonomia | Ruta | Velocidad | Semaforo |
|---|---|---|---|---|---|
| Temperatura alta | ↓ | ↓ | ~ | ~ | ~ |
| Congestion vial | ↓ | ↓ | Reruta | ↓ | ↑ activo |
| Carga rapida frec. | ~ | ↓ largo plazo | ~ | ~ | ~ |
| Ruta con rampas | ↓ | ↓ | ~ | ↓ | ~ |
| Semaforo RL activo | ↑ | ↑ | ~ | ↑ | optimiza |

</div>

<div v-click class="mt-5 border rounded p-3 text-sm text-center" style="border-color:#00D4FF; color:#00D4FF;">
  Una sola variable afecta todo el sistema — la IA debe integrar todas en tiempo real
</div>

---
layout: image-right
image: /img/b08-sensor-fusion.jpg
---

# CARLA — Simulador de Conduccion Autonoma

<div class="mt-4 space-y-3 text-sm">
  <div v-click class="card-ev p-3">
    <strong>CARLA</strong> = Car Learning to Act<br>
    <span class="text-xs muted">Desarrollado por Intel Labs y UPC Barcelona<br>Entorno 3D fotorrealista open-source</span>
  </div>
  <div v-click class="space-y-2">
    <div class="font-bold text-accent mb-1">Capacidades:</div>
    <div class="flex items-center gap-2"><mdi-camera class="inline" /> <span>Camaras RGB, profundidad, segmentacion</span></div>
    <div class="flex items-center gap-2"><mdi-circle class="inline" /> <span>LiDAR y Radar simulados</span></div>
    <div class="flex items-center gap-2"><mdi-weather-partly-cloudy class="inline" /> <span>Condiciones climaticas: lluvia, niebla, noche</span></div>
    <div class="flex items-center gap-2"><mdi-car-electric class="inline" /> <span>Trafico de vehiculos y peatones</span></div>
    <div class="flex items-center gap-2"><mdi-lightning-bolt class="inline" /> <span>Modelos de consumo electrico</span></div>
    <div class="flex items-center gap-2"><mdi-language-python class="inline" /> <span>API Python para controlar todo</span></div>
  </div>
  <div v-click class="text-xs muted">carla-simulator.org — version 0.9.x, Linux/Windows</div>
</div>

---
layout: default
class: dark-slide
---

# Como se Integran los Modulos en CARLA

<div class="space-y-2 mt-4 text-sm">
  <div v-click class="rounded p-3" style="background:#1a2535;">
    <div class="font-bold text-accent mb-1">CAPA 5 — DECISION Y CONTROL</div>
    <div class="flex gap-6 text-xs muted">
      <span>Planeacion de ruta (Bloque 06)</span>
      <span>Toma de decision energetica (Bloque 05)</span>
    </div>
  </div>
  <div v-click class="rounded p-3" style="background:#1a2535;">
    <div class="font-bold text-accent mb-1">CAPA 4 — PREDICCION</div>
    <div class="flex gap-6 text-xs muted">
      <span>SoC y autonomia estimada (Bloque 04)</span>
      <span>Prediccion de trafico (Bloque 07)</span>
    </div>
  </div>
  <div v-click class="rounded p-3 border" style="background:#00D4FF15; border-color:#00D4FF;">
    <div class="font-bold text-accent mb-1">CAPA 3 — PERCEPCION ★</div>
    <div class="flex gap-6 text-xs muted">
      <span>CNN deteccion de objetos (Bloque 02)</span>
      <span>Fusion de sensores (Bloque 02)</span>
    </div>
  </div>
  <div v-click class="rounded p-3" style="background:#1a2535;">
    <div class="font-bold text-accent mb-1">CAPA 2 — SENSADO</div>
    <div class="flex gap-6 text-xs muted">
      <span>Camaras, LiDAR, Radar de CARLA (Bloque 02)</span>
      <span>Telemetria del vehiculo (Bloque 04)</span>
    </div>
  </div>
  <div v-click class="rounded p-3" style="background:#1a2535;">
    <div class="font-bold text-accent mb-1">CAPA 1 — HARDWARE SIMULADO</div>
    <div class="flex gap-6 text-xs muted">
      <span>Chips de inferencia CARLA (Bloque 03)</span>
      <span>BMS simulado (Bloque 04)</span>
    </div>
  </div>
</div>

---
layout: default
---

# Caso de Uso: EV Inteligente en Ciudad Simulada

<div class="space-y-3 mt-6 text-sm">
  <div v-click class="flex items-start gap-4">
    <div class="w-8 h-8 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">1</div>
    <div class="card-ev p-3 flex-1"><mdi-map-marker class="inline" /> <strong>EV parte con SoC=85%</strong>, destino a 80km en ciudad simulada CARLA</div>
  </div>
  <div v-click class="flex items-start gap-4">
    <div class="w-8 h-8 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">2</div>
    <div class="card-ev p-3 flex-1"><mdi-camera class="inline" /> <strong>Vision CNN detecta trafico denso</strong> en ruta directa — informa al planificador</div>
  </div>
  <div v-click class="flex items-start gap-4">
    <div class="w-8 h-8 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">3</div>
    <div class="card-ev p-3 flex-1"><mdi-map class="inline" /> <strong>Sistema reruta via EVRP</strong> con parada en cargador para garantizar llegada</div>
  </div>
  <div v-click class="flex items-start gap-4">
    <div class="w-8 h-8 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">4</div>
    <div class="card-ev p-3 flex-1"><mdi-traffic-light class="inline" /> <strong>Semaforos RL coordinan</strong> para dar ola verde al EV en intersecciones</div>
  </div>
  <div v-click class="flex items-start gap-4">
    <div class="w-8 h-8 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">5</div>
    <div class="card-ev p-3 flex-1"><mdi-power-plug class="inline" /> <strong>EV carga 20 min</strong> en estacion solar (precio bajo, generacion alta)</div>
  </div>
  <div v-click class="flex items-start gap-4">
    <div class="w-8 h-8 rounded-full" style="background:#10B981; color:#0D1B2A;" >
      <div class="w-full h-full flex items-center justify-center font-bold text-sm">✓</div>
    </div>
    <div class="p-3 flex-1 rounded" style="border: 1px solid #10B981; color:#10B981;">Llega al destino con SoC=42% — mision cumplida</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Impacto de Variables en el Sistema Completo

<div class="grid grid-cols-2 gap-6 mt-4">
  <div v-click>
    <div class="text-accent font-bold mb-3">Autonomia vs Temperatura</div>
    <div class="space-y-2 text-sm">
      <div class="flex items-center gap-2">
        <span class="w-20 muted text-xs">-10°C</span>
        <div class="h-4 rounded" style="background:#ef4444; width:75%;"></div>
        <span class="text-xs">75%</span>
      </div>
      <div class="flex items-center gap-2">
        <span class="w-20 muted text-xs">25°C (optimo)</span>
        <div class="h-4 rounded" style="background:#10B981; width:100%;"></div>
        <span class="text-xs">100%</span>
      </div>
      <div class="flex items-center gap-2">
        <span class="w-20 muted text-xs">45°C</span>
        <div class="h-4 rounded" style="background:#F59E0B; width:85%;"></div>
        <span class="text-xs">85%</span>
      </div>
    </div>
  </div>
  <div v-click>
    <div class="text-accent font-bold mb-3">Consumo kWh vs Congestion</div>
    <div class="space-y-2 text-sm">
      <div class="flex items-center gap-2">
        <span class="w-20 muted text-xs">Libre</span>
        <div class="h-4 rounded" style="background:#10B981; width:48%;"></div>
        <span class="text-xs">15 kWh</span>
      </div>
      <div class="flex items-center gap-2">
        <span class="w-20 muted text-xs">Media</span>
        <div class="h-4 rounded" style="background:#F59E0B; width:71%;"></div>
        <span class="text-xs">22 kWh</span>
      </div>
      <div class="flex items-center gap-2">
        <span class="w-20 muted text-xs">Severa</span>
        <div class="h-4 rounded" style="background:#ef4444; width:100%;"></div>
        <span class="text-xs">31 kWh</span>
      </div>
    </div>
  </div>
</div>

<div v-click class="mt-5 text-sm text-center muted border rounded p-2" style="border-color:#00D4FF;">
  Temperatura y congestion son los dos factores mas impactantes en la autonomia real — el sistema integrado debe compensar ambos
</div>

---
layout: default
class: dark-slide
---

# Proyecto Integrador Final

<div class="badge-ev mb-4">PROYECTO FINAL</div>

<div class="grid grid-cols-2 gap-6 mt-2">
  <div v-click class="space-y-2 text-sm">
    <div class="text-accent font-bold mb-2">El alumno debe presentar:</div>
    <div class="flex items-start gap-2">
      <span class="text-accent">1.</span><span>Problema a resolver (de cualquier bloque del curso)</span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-accent">2.</span><span>Tipo de modelo ML utilizado</span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-accent">3.</span><span>Variables clave involucradas (X e Y)</span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-accent">4.</span><span>Arquitectura general del sistema</span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-accent">5.</span><span>Impacto energetico y logistico</span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-accent">6.</span><span>Viabilidad tecnica y oportunidad de mercado</span>
    </div>
  </div>
  <div v-click class="space-y-3 text-sm">
    <div class="card-ev p-3">
      <div class="font-bold text-accent mb-1">Formato:</div>
      <div>Presentacion de 5-8 slides</div>
      <div>10 minutos de exposicion</div>
    </div>
    <div class="card-ev p-3">
      <div class="font-bold text-accent mb-1">Criterios:</div>
      <div class="text-xs space-y-1 muted">
        <div>• Comprension del problema</div>
        <div>• Justificacion del modelo elegido</div>
        <div>• Coherencia de variables</div>
        <div>• Arquitectura logica</div>
        <div>• Impacto real estimado</div>
        <div>• Creatividad e innovacion</div>
      </div>
    </div>
  </div>
</div>

---
layout: default
---

# Ideas de Proyectos Integradores

<div class="grid grid-cols-2 gap-4 mt-6 text-sm">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1"><mdi-wrench class="inline" /> Mantenimiento Predictivo</div>
    <div class="text-xs muted">Sistema ML para flotas EV en maquiladoras de Ciudad Juarez</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1"><mdi-taxi class="inline" /> Carga de Taxis Electricos</div>
    <div class="text-xs muted">Optimizacion de carga para taxis electricos en hora pico</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1"><mdi-recycle class="inline" /> Bateria Segunda Vida</div>
    <div class="text-xs muted">Plataforma de gestion de bateria para segunda vida util</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1"><mdi-traffic-light class="inline" /> Semaforos con Prioridad EV</div>
    <div class="text-xs muted">Red de semaforos inteligentes con prioridad a EV de emergencia</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1"><mdi-thermometer class="inline" /> Autonomia Adaptativa</div>
    <div class="text-xs muted">App de prediccion de autonomia segun condiciones climaticas</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1"><mdi-office-building class="inline" /> V2G Corporativo</div>
    <div class="text-xs muted">Sistema V2G para edificios corporativos en Ciudad Juarez</div>
  </div>
</div>

<div class="mt-3 text-xs text-center muted">Estos son ejemplos — el alumno puede proponer cualquier idea original</div>

---
layout: center
class: dark-slide
---

# La Electromovilidad es un Sistema, no una Tecnologia

<img src="/img/b08-ev-future.jpg" class="absolute inset-0 w-full h-full object-cover opacity-15 -z-1" />

<div class="max-w-2xl mx-auto text-center mt-4">
  <div v-click class="text-lg leading-relaxed mb-6" style="color:#E8F4FD;">
    Cada bloque del curso representa una pieza de un ecosistema complejo.
    El valor real de la IA en electromovilidad no esta en los modelos individuales,
    sino en como se integran para tomar mejores decisiones, en tiempo real,
    con restricciones energeticas, logisticas y de seguridad simultaneas.
  </div>

  <div v-click class="text-xl font-bold text-accent">
    El vehiculo electrico inteligente no solo conduce<br>
    — percibe, predice, optimiza y aprende.
  </div>
</div>

---
layout: center
class: dark-slide
---

# Gracias — Resumen del Curso

<div class="grid grid-cols-4 gap-4 mt-6 text-center text-xs">
  <div v-click class="card-ev p-3">
    <mdi-brain class="text-2xl mb-1" />
    <div class="text-accent font-bold">Bloque 01</div>
    <div class="muted">ML Fundamentos</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-camera class="text-2xl mb-1" />
    <div class="text-accent font-bold">Bloque 02</div>
    <div class="muted">Computer Vision</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-laptop class="text-2xl mb-1" />
    <div class="text-accent font-bold">Bloque 03</div>
    <div class="muted">Arquitectura/Deploy</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-battery class="text-2xl mb-1" />
    <div class="text-accent font-bold">Bloque 04</div>
    <div class="muted">Gestion Energia</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-power-plug class="text-2xl mb-1" />
    <div class="text-accent font-bold">Bloque 05</div>
    <div class="muted">Carga Inteligente</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-map class="text-2xl mb-1" />
    <div class="text-accent font-bold">Bloque 06</div>
    <div class="muted">Logistica/Rutas</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-traffic-light class="text-2xl mb-1" />
    <div class="text-accent font-bold">Bloque 07</div>
    <div class="muted">Trafico MAS</div>
  </div>
  <div v-click class="card-ev p-3" style="border: 1px solid #00D4FF;">
    <mdi-car-electric class="text-2xl mb-1" />
    <div class="text-accent font-bold">Bloque 08</div>
    <div class="muted">CARLA Integracion</div>
  </div>
</div>

<div v-click class="mt-6 text-sm muted text-center">IA Aplicada a la Electromovilidad — 16 horas — Ciudad Juarez</div>

<div v-click class="mt-3 text-accent font-bold text-center">
  El futuro de la movilidad se construye con datos, modelos y codigo.
</div>
