---
theme: default
title: "Bloque 03 — Arquitectura de Sistemas de IA y Deployment"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque 03
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
fonts:
  sans: 'Segoe UI'
---

# Bloque 03
## Arquitectura de Sistemas de IA y Deployment

Del modelo entrenado al chip en el vehiculo

<div class="abs-br m-6 text-xs text-gray-400">2 horas | Teoria + Practica</div>

<img src="/img/b03-chip.jpg" class="absolute inset-0 w-full h-full object-cover opacity-20 -z-1" />

---
layout: default
---

# Contenido del Bloque

<div class="grid grid-cols-2 gap-6 mt-6">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Pipeline de Machine Learning</div>
    <div class="text-sm">Del dato crudo al modelo en produccion</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Chips: Infotainment vs Autonomia</div>
    <div class="text-sm">Dos mundos con requisitos radicalmente distintos</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">FLOPS: Que son y por que importan</div>
    <div class="text-sm">La unidad de poder de computo en IA</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Casos de Uso por Chip</div>
    <div class="text-sm">Que chip usar para cada escenario</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Consumo Energetico</div>
    <div class="text-sm">Impacto en la autonomia del EV</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="badge-ev mb-2">PRACTICA</div>
    <div class="text-sm">Analisis de chips y escenarios hipoteticos</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Pipeline ML — Del Dato al Modelo en Produccion

<div class="flex items-stretch gap-1 mt-8 text-xs text-center flex-wrap">
  <div v-click class="flex-1 rounded p-2 min-w-16" style="background:#1B4F72;">
    <mdi-download class="text-lg mb-1" />
    <div class="font-bold text-accent">Recoleccion</div>
  </div>
  <div class="flex items-center text-accent text-xs">→</div>
  <div v-click class="flex-1 rounded p-2 min-w-16" style="background:#1B4F72;">
    <mdi-broom class="text-lg mb-1" />
    <div class="font-bold text-accent">Limpieza</div>
  </div>
  <div class="flex items-center text-accent text-xs">→</div>
  <div v-click class="flex-1 rounded p-2 min-w-16" style="background:#1B4F72;">
    <mdi-chart-bar class="text-lg mb-1" />
    <div class="font-bold text-accent">EDA</div>
  </div>
  <div class="flex items-center text-accent text-xs">→</div>
  <div v-click class="flex-1 rounded p-2 min-w-16" style="background:#1B4F72;">
    <mdi-cog class="text-lg mb-1" />
    <div class="font-bold text-accent">Feature Eng.</div>
  </div>
  <div class="flex items-center text-accent text-xs">→</div>
  <div v-click class="flex-1 rounded p-2 min-w-16" style="background:#00D4FF; color:#0D1B2A;">
    <mdi-brain class="text-lg mb-1" />
    <div class="font-bold">Modelo</div>
  </div>
  <div class="flex items-center text-accent text-xs">→</div>
  <div v-click class="flex-1 rounded p-2 min-w-16" style="background:#1B4F72;">
    <mdi-ruler class="text-lg mb-1" />
    <div class="font-bold text-accent">Evaluacion</div>
  </div>
  <div class="flex items-center text-accent text-xs">→</div>
  <div v-click class="flex-1 rounded p-2 min-w-16" style="background:#10B981; color:#0D1B2A;">
    <mdi-rocket class="text-lg mb-1" />
    <div class="font-bold">Deployment</div>
  </div>
  <div class="flex items-center text-accent text-xs">→</div>
  <div v-click class="flex-1 rounded p-2 min-w-16" style="background:#1B4F72;">
    <mdi-antenna class="text-lg mb-1" />
    <div class="font-bold text-accent">Monitoreo</div>
  </div>
</div>

<div v-click class="mt-6 border rounded p-3 text-sm text-center" style="border-color:#00D4FF;">
  En EV el monitoreo es critico — el modelo debe funcionar con datos de temperatura, bateria y trafico en tiempo real
</div>

---
layout: default
---

# Dos Mundos, Dos Chips

<div class="grid grid-cols-2 gap-6 mt-4">
  <div v-click class="bg-white rounded-lg p-5 text-gray-800">
    <mdi-cellphone class="text-2xl mb-2" />
    <div class="font-bold text-lg mb-1" style="color:#1B4F72;">Infotainment SoC</div>
    <div class="text-xs muted mb-3">Qualcomm Snapdragon, NVIDIA Tegra</div>
    <ul class="text-sm space-y-1 mb-3">
      <li>Navegacion GPS y mapas</li>
      <li>Reproduccion multimedia</li>
      <li>Asistente de voz</li>
      <li>Conectividad (WiFi, Bluetooth, 5G)</li>
      <li>Apps del tablero</li>
    </ul>
    <div class="text-xs muted mb-2">1-10 TOPS — carga moderada</div>
    <div class="inline-block px-3 py-1 rounded text-xs font-bold" style="background:#1B4F72;color:white;">INTERFAZ</div>
  </div>
  <div v-click class="card-ev p-5">
    <mdi-car-electric class="text-2xl mb-2" />
    <div class="text-accent font-bold text-lg mb-1">FSD Computer / Autopilot SoC</div>
    <div class="text-xs muted mb-3">Tesla FSD Chip, NVIDIA DRIVE Orin</div>
    <ul class="text-sm space-y-1 mb-3">
      <li>Percepcion en tiempo real (CNN)</li>
      <li>Fusion de sensores (camara+lidar+radar)</li>
      <li>Planificacion de trayectoria</li>
      <li>Toma de decisiones (RL)</li>
      <li>Respuesta en &lt;10ms</li>
    </ul>
    <div class="text-xs muted mb-2">100-1000+ TOPS — carga extrema</div>
    <div class="badge-ev">AUTONOMIA</div>
  </div>
</div>

---
layout: image-right
image: /img/b03-gpu.jpg
---

# FLOPS: La Unidad de Poder de Computo

<div v-click class="border rounded p-3 mb-4 text-sm" style="border-color:#00D4FF; color:#00D4FF;">
  <div><strong>FLOP</strong> = Floating Point Operation</div>
  <div><strong>FLOPS</strong> = Operaciones por segundo que puede ejecutar un chip</div>
</div>

<div v-click class="card-ev p-3 mb-4 text-sm">

| Escala | Valor | Referencia |
|---|---|---|
| GFLOPS | 10⁹ | Smartphone clasico |
| TFLOPS | 10¹² | GPU gaming |
| TOPS | 10¹² Ops | Chips de inferencia IA |

</div>

<div class="space-y-2 text-sm">
  <div v-click><span class="muted">Qualcomm 8155</span> → <span class="text-accent font-bold">8 TOPS</span> — Infotainment</div>
  <div v-click><span class="muted">Tesla FSD Chip 1</span> → <span class="text-accent font-bold">144 TOPS</span> — Nivel 2-3</div>
  <div v-click><span class="muted">NVIDIA DRIVE Orin</span> → <span class="text-accent font-bold">254 TOPS</span> — Nivel 4</div>
  <div v-click><span class="muted">Tesla Dojo</span> → <span class="text-accent font-bold">&gt;1 PFLOPS</span> — Entrenamiento nube</div>
</div>

<div v-click class="mt-4 border rounded p-2 text-xs warning" style="border-color:#F59E0B;">
  Mas FLOPS = mas calor y mas consumo electrico — hay que balancear
</div>

---
layout: default
---

# Seleccion de Chip por Caso de Uso

<div v-click class="mt-4 text-sm">

| Caso de Uso | Chip Tipo | TOPS Req. | Consumo W | Ejemplo Real |
|---|---|---|---|---|
| Navegacion GPS | Infotainment | 1-5 | 3-8W | Snapdragon 8155 |
| Reconocimiento de voz | Infotainment | 2-8 | 3-8W | Snapdragon 8155 |
| Deteccion de peatones | Autonomia | 50+ | 15-30W | Tesla FSD / DRIVE Xavier |
| Fusion sensor completa | Autonomia | 100+ | 30-65W | DRIVE Orin |
| Conduccion nivel 4 | Autonomia | 200+ | 65W+ | DRIVE Thor / FSD Chip 3 |

</div>

---
layout: default
class: dark-slide
---

# Consumo Energetico por Escenario

<div class="grid grid-cols-2 gap-6 mt-4">
  <div v-click class="space-y-2">
    <div class="flex items-center gap-2 text-sm">
      <div class="text-right w-32 muted">Infotainment</div>
      <div class="h-5 rounded" style="background:#1B4F72; width: 6%;"></div>
      <div class="text-accent text-xs">8W</div>
    </div>
    <div class="flex items-center gap-2 text-sm">
      <div class="text-right w-32 muted">ADAS Basico</div>
      <div class="h-5 rounded" style="background:#1B4F72; width: 20%;"></div>
      <div class="text-accent text-xs">25W</div>
    </div>
    <div class="flex items-center gap-2 text-sm">
      <div class="text-right w-32 muted">Autopilot</div>
      <div class="h-5 rounded" style="background:#00D4FF; width: 35%;"></div>
      <div class="text-accent text-xs">45W</div>
    </div>
    <div class="flex items-center gap-2 text-sm">
      <div class="text-right w-32 muted">Full FSD</div>
      <div class="h-5 rounded" style="background:#00D4FF; width: 50%;"></div>
      <div class="text-accent text-xs">65W</div>
    </div>
    <div class="flex items-center gap-2 text-sm">
      <div class="text-right w-32 muted">Dojo (nube)</div>
      <div class="h-5 rounded" style="background:#F59E0B; width: 95%;"></div>
      <div class="text-accent text-xs">1200W</div>
    </div>
  </div>
  <div v-click class="space-y-4 text-sm">
    <div class="card-ev p-3">El FSD consume ~8x mas que infotainment</div>
    <div class="card-ev p-3">El entrenamiento en la nube es 1000x mas intensivo</div>
    <div class="border rounded p-3" style="border-color:#00D4FF; color:#E8F4FD;">
      El chip de autonomia representa hasta el 3-5% del consumo total de la bateria en conduccion activa
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Arquitectura de IA en un EV Moderno

<div class="space-y-3 mt-4 text-sm">
  <div v-click class="rounded p-3 text-center" style="background:#1a2a3a;">
    <div class="text-accent font-bold mb-1">NUBE / SERVIDOR</div>
    <div class="flex justify-center gap-4 text-xs muted">
      <span>Entrenamiento de modelos</span>
      <span>Actualizaciones OTA</span>
      <span>Telemetria</span>
    </div>
  </div>
  <div class="text-center text-accent text-xs">↕</div>
  <div v-click class="rounded p-3 text-center" style="background:#1a2a3a;">
    <div class="text-accent font-bold mb-1">CONECTIVIDAD</div>
    <div class="flex justify-center gap-4 text-xs muted"><span>5G / WiFi</span><span>V2X (Vehicle to Everything)</span></div>
  </div>
  <div class="text-center text-accent text-xs">↕</div>
  <div v-click class="rounded p-3 text-center" style="background:#1a2a3a;">
    <div class="text-accent font-bold mb-1">CHIP INFOTAINMENT</div>
    <div class="flex justify-center gap-4 text-xs muted"><span>Mapas</span><span>Voz</span><span>Apps</span><span>Display</span></div>
  </div>
  <div class="text-center text-accent text-xs">↕</div>
  <div v-click class="rounded p-3 text-center border" style="border-color:#00D4FF; background:#00D4FF15;">
    <div class="text-accent font-bold mb-1">CHIP CONDUCCION AUTONOMA ★</div>
    <div class="flex justify-center gap-4 text-xs muted"><span>Percepcion</span><span>Planificacion</span><span>Control</span></div>
  </div>
  <div class="text-center text-accent text-xs">↕</div>
  <div v-click class="rounded p-3 text-center" style="background:#1a2a3a;">
    <div class="text-accent font-bold mb-1">HARDWARE / SENSORES</div>
    <div class="flex justify-center gap-4 text-xs muted"><span>Camaras</span><span>LiDAR</span><span>Radar</span><span>BMS</span><span>CAN Bus</span></div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Practica — Bloque 03

<div class="badge-ev mb-4">PRACTICA</div>

## Analisis de Chips y Escenarios Hipoteticos

<div class="space-y-3 mt-4">
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">1</div>
    <div class="text-sm">Buscar especificaciones de: Snapdragon 8155, Tesla FSD Chip 3, NVIDIA DRIVE Orin</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">2</div>
    <div class="text-sm">Crear tabla comparativa: TOPS, consumo W, temperatura maxima</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">3</div>
    <div class="text-sm">Asignar cada chip al escenario mas adecuado de la tabla de casos de uso</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">4</div>
    <div class="text-sm">Calcular consumo estimado de IA en un viaje de 100km a 60 km/h</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">5</div>
    <div class="text-sm">Discutir: cuanto impacta la IA en la autonomia total del vehiculo</div>
  </div>
</div>

<div v-click class="mt-4 card-ev p-3 text-sm">
  <span class="font-bold text-accent">Entregable:</span> Tabla comparativa + respuesta al calculo de impacto en autonomia
</div>

---
layout: center
class: dark-slide
---

# Puntos Clave — Bloque 03

<div class="space-y-3 mt-4 text-left max-w-xl mx-auto">
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>El pipeline ML va de datos crudos hasta un modelo monitoreado en produccion</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Infotainment y conduccion autonoma requieren chips con ordenes de magnitud diferentes</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>FLOPS/TOPS miden la capacidad de computo — mas = mas caro y mas calor</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>La eleccion del chip impacta directamente en el consumo y la autonomia del EV</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Los chips de autonomia evolucionan cada 2-3 anos — Tesla, NVIDIA y Qualcomm lideran</span>
  </div>
</div>

<div class="mt-8 text-sm muted">
  > Siguiente: <span class="text-accent font-bold">Bloque 04 — Gestion Inteligente de Energia y Baterias</span>
</div>
