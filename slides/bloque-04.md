---
theme: penguin
title: "Bloque 04 — Gestion Inteligente de Energia y Baterias"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque 04
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
zoom: 0.85
fonts:
  sans: 'Segoe UI'
---

# Bloque 04
## Gestion Inteligente de Energia y Baterias

IA aplicada al corazon electrico del vehiculo

<div class="abs-br m-6 text-xs text-gray-400">2 horas | Teoria + Practica</div>

<img src="/img/b04-battery.jpg" class="absolute inset-0 w-full h-full object-cover opacity-20 -z-1" />

---
layout: default
---

# Contenido del Bloque

<div class="grid grid-cols-2 gap-6 mt-6">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Funcionamiento del BMS</div>
    <div class="text-sm">El sistema nervioso de la bateria</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Regresion y Series de Tiempo</div>
    <div class="text-sm">Modelos predictivos para baterias</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">State of Charge (SoC)</div>
    <div class="text-sm">Estado de carga actual de la bateria</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">State of Health (SoH)</div>
    <div class="text-sm">Estado de salud y degradacion</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Variables Criticas</div>
    <div class="text-sm">Temperatura, ciclos, voltaje, corriente</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="badge-ev mb-2">PRACTICA</div>
    <div class="text-sm">Simulacion de consumo y estimacion de autonomia</div>
  </div>
</div>

---
layout: image-right
image: /img/b04-bms.jpg
---

# BMS — El Sistema Nervioso de la Bateria

<div class="mt-4 space-y-3 text-sm">
  <div v-click class="flex items-center gap-2">
    <div class="w-2 h-2 rounded-full bg-accent flex-shrink-0"></div>
    <span><strong class="text-accent">Control de Temperatura</strong> — mantiene rango operativo seguro</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <div class="w-2 h-2 rounded-full bg-accent flex-shrink-0"></div>
    <span><strong class="text-accent">Balanceo de Celdas</strong> — iguala voltaje entre celdas del pack</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <div class="w-2 h-2 rounded-full bg-accent flex-shrink-0"></div>
    <span><strong class="text-accent">Proteccion</strong> — sobredescarga, sobrecarga, cortocircuito</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <div class="w-2 h-2 rounded-full bg-accent flex-shrink-0"></div>
    <span><strong class="text-accent">Estimacion SoC / SoH</strong> — estado actual y salud del pack</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <div class="w-2 h-2 rounded-full bg-accent flex-shrink-0"></div>
    <span><strong class="text-accent">Comunicacion CAN Bus / OBD</strong> — integra con el vehiculo</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <div class="w-2 h-2 rounded-full bg-accent flex-shrink-0"></div>
    <span><strong class="text-accent">Registro historico</strong> — contador de ciclos, historial de temperatura</span>
  </div>
</div>

---
layout: default
---

# Modelos Predictivos para Baterias

<div class="grid grid-cols-2 gap-6 mt-6">
  <div v-click class="card-ev p-5">
    <div class="text-accent font-bold text-lg mb-3"><mdi-trending-up class="inline" /> Regresion</div>
    <div class="text-sm mb-3">Predice un valor numerico (SoC, autonomia)</div>
    <div class="text-sm space-y-1 muted">
      <div>• Prediccion de carga segun temperatura</div>
      <div>• Velocidad y aceleracion como inputs</div>
      <div>• Estimacion de km restantes</div>
    </div>
  </div>
  <div v-click class="card-ev p-5">
    <div class="text-accent font-bold text-lg mb-3"><mdi-clock-outline class="inline" /> Series de Tiempo</div>
    <div class="text-sm mb-3">Predice la evolucion de una variable en el tiempo</div>
    <div class="text-sm space-y-1 muted">
      <div>• Degradacion de bateria por ciclos</div>
      <div>• Prediccion de falla anticipada</div>
      <div>• Modelos: LSTM, ARIMA, Prophet</div>
    </div>
  </div>
</div>

<div v-click class="mt-6 border rounded p-4 text-sm" style="border-color:#00D4FF;">
  <strong class="text-accent">Diferencia clave:</strong> la regresion usa un snapshot de variables, la serie de tiempo usa el historial para predecir el futuro
</div>

---
layout: default
class: dark-slide
---

# SoC — Estado de Carga Actual

<div class="grid grid-cols-2 gap-6 mt-4">
  <div>
    <div v-click class="card-ev p-4 mb-4 text-center">
      <div class="text-accent font-bold mb-2">Definicion</div>
      <div class="font-mono text-sm">SoC = (Carga actual / Capacidad max) × 100</div>
    </div>
    <div v-click class="space-y-2 text-sm">
      <div class="font-bold text-accent mb-2">Metodos de estimacion:</div>
      <div class="flex items-start gap-2">
        <span class="text-accent">→</span>
        <span><strong>Coulomb Counting</strong> — sumar/restar corriente en el tiempo</span>
      </div>
      <div class="flex items-start gap-2">
        <span class="text-accent">→</span>
        <span><strong>Modelo de voltaje</strong> — curva OCV vs SoC</span>
      </div>
      <div class="flex items-start gap-2">
        <span class="text-accent">→</span>
        <span><strong>Kalman Filter</strong> — fusion de ambos con IA</span>
      </div>
    </div>
  </div>
  <div v-click>
    <div class="card-ev p-4 text-center mb-4">
      <div class="text-5xl font-bold text-accent mb-2">72%</div>
      <div class="text-sm muted">SoC ejemplo actual</div>
      <div class="mt-3 flex rounded overflow-hidden h-4">
        <div style="background:#ef4444; width:20%;" class="text-xs text-center">0-20</div>
        <div style="background:#F59E0B; width:20%;" class="text-xs text-center">20-40</div>
        <div style="background:#10B981; width:60%;" class="text-xs text-center">40-100%</div>
      </div>
    </div>
    <div class="text-sm warning border rounded p-3" style="border-color:#F59E0B;">
      Temperatura, envejecimiento y corrientes de fuga afectan la precision
    </div>
  </div>
</div>

---
layout: default
---

# SoH — Estado de Salud de la Bateria

<div class="grid grid-cols-2 gap-6 mt-4">
  <div>
    <div v-click class="card-ev p-4 mb-4">
      <div class="text-accent font-bold mb-2">Definicion</div>
      <div class="font-mono text-sm mb-1">SoH = (Capacidad actual / Cap. original) × 100</div>
      <div class="text-xs muted">Bateria "degradada" cuando SoH &lt; 80%</div>
    </div>
    <div v-click class="space-y-2 text-sm">
      <div class="font-bold text-accent mb-2">Factores de degradacion:</div>
      <div>• Ciclos de carga profundos</div>
      <div>• Temperaturas extremas (&gt;45°C o &lt;0°C)</div>
      <div>• Cargas rapidas frecuentes (DC fast charging)</div>
      <div>• Tiempo en calendario</div>
    </div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-3">Curva de degradacion tipica</div>
    <div class="space-y-1 text-xs">
      <div class="flex justify-between"><span class="muted">0 ciclos</span><span class="success">SoH: 100%</span></div>
      <div class="flex justify-between"><span class="muted">200 ciclos</span><span class="success">SoH: 95%</span></div>
      <div class="flex justify-between"><span class="muted">400 ciclos</span><span>SoH: 90%</span></div>
      <div class="flex justify-between"><span class="muted">600 ciclos</span><span class="warning">SoH: 85%</span></div>
      <div class="flex justify-between"><span class="muted">800 ciclos</span><span class="warning">SoH: 80%</span></div>
      <div class="flex justify-between border-t mt-1 pt-1" style="border-color:#ef4444;"><span class="muted">1000+ ciclos</span><span style="color:#ef4444;"><mdi-alert class="inline" /> FIN DE VIDA UTIL</span></div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Variables Clave que Monitorea el BMS con IA

<div class="grid grid-cols-3 gap-4 mt-6">
  <div v-click class="card-ev p-4 text-center">
    <mdi-lightning-bolt class="text-2xl mb-1" />
    <div class="text-accent font-bold">Voltaje por Celda</div>
    <div class="text-xs muted mt-1">V por celda individual</div>
  </div>
  <div v-click class="card-ev p-4 text-center">
    <mdi-refresh class="text-2xl mb-1" />
    <div class="text-accent font-bold">Corriente</div>
    <div class="text-xs muted mt-1">Amperios de carga/descarga</div>
  </div>
  <div v-click class="card-ev p-4 text-center">
    <mdi-thermometer class="text-2xl mb-1" />
    <div class="text-accent font-bold">Temperatura</div>
    <div class="text-xs muted mt-1">Celsius, critica &gt;45°C</div>
  </div>
  <div v-click class="card-ev p-4 text-center">
    <mdi-battery class="text-2xl mb-1" />
    <div class="text-accent font-bold">SoC</div>
    <div class="text-xs muted mt-1">% carga disponible</div>
  </div>
  <div v-click class="card-ev p-4 text-center">
    <mdi-heart class="text-2xl mb-1" />
    <div class="text-accent font-bold">SoH</div>
    <div class="text-xs muted mt-1">% salud del pack</div>
  </div>
  <div v-click class="card-ev p-4 text-center">
    <mdi-numeric class="text-2xl mb-1" />
    <div class="text-accent font-bold">Ciclos de Carga</div>
    <div class="text-xs muted mt-1">Contador de cargas completas</div>
  </div>
</div>

---
layout: default
---

# Que Algoritmo Usar para Cada Problema

<div v-click class="mt-4 text-sm">

| Problema | Algoritmo | Herramienta |
|---|---|---|
| Estimacion SoC | Kalman + LSTM | Python / TensorFlow |
| Prediccion SoH | Regresion | Scikit-learn |
| Deteccion de anomalias | Autoencoder | PyTorch |
| Prediccion de falla | Serie de tiempo | Prophet / LSTM |
| Optimizacion de carga | RL | Gym + Stable Baselines |

</div>

<img src="/img/b04-cells.jpg" class="mt-6 w-full h-28 object-cover rounded opacity-50" />

---
layout: default
class: dark-slide
---

# Practica — Bloque 04

<div class="badge-ev mb-4">PRACTICA</div>

## Simulacion de Consumo y Estimacion de Autonomia

<div class="space-y-3 mt-4">
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">1</div>
    <div class="text-sm">Cargar dataset de ciclos de bateria (CSV proporcionado: voltaje, corriente, temp, SoC)</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">2</div>
    <div class="text-sm">Ejecutar cuaderno Colab: regresion para predecir SoC</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">3</div>
    <div class="text-sm">Graficar curva de SoH por ciclos con Matplotlib</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">4</div>
    <div class="text-sm">Estimar autonomia con SoC=80% vs SoC=100%</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">5</div>
    <div class="text-sm">Analizar impacto de temperatura en la prediccion</div>
  </div>
</div>

<div v-click class="mt-4 flex gap-3 text-xs">
  <div class="card-ev px-3 py-1">Google Colab</div>
  <div class="card-ev px-3 py-1">Pandas</div>
  <div class="card-ev px-3 py-1">Scikit-learn</div>
  <div class="card-ev px-3 py-1">Matplotlib</div>
</div>

---
layout: center
class: dark-slide
---

# Puntos Clave — Bloque 04

<div class="space-y-3 mt-4 text-left max-w-xl mx-auto">
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>El BMS protege, balancea y monitorea la bateria en tiempo real</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>SoC mide la carga actual, SoH mide el envejecimiento del pack</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>La regresion predice valores puntuales; las series de tiempo predicen evolucion</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Temperatura y ciclos son los principales factores de degradacion</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>La IA mejora la precision de SoC/SoH frente a metodos tradicionales</span>
  </div>
</div>

<div class="mt-8 text-sm muted">
  > Siguiente: <span class="text-accent font-bold">Bloque 05 — Infraestructura de Carga Inteligente</span>
</div>
