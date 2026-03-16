---
theme: penguin
title: "Bloque 05 — Infraestructura de Carga Inteligente"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque 05
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
zoom: 0.85
fonts:
  sans: 'Segoe UI'
---

# Bloque 05
## Infraestructura de Carga Inteligente

Smart Grids, prediccion de demanda y energias renovables

<div class="abs-br m-6 text-xs text-gray-400">2 horas | Teoria + Practica</div>

<img src="/img/b05-charging-station.jpg" class="absolute inset-0 w-full h-full object-cover opacity-20 -z-1" />

---
layout: default
---

# Contenido del Bloque

<div class="grid grid-cols-2 gap-6 mt-6">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Tecnologias de Carga</div>
    <div class="text-sm">Nivel 1, 2 y DC Fast Charging</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Smart Grids y V2G</div>
    <div class="text-sm">Red electrica inteligente y vehiculo como bateria</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Prediccion de Demanda</div>
    <div class="text-sm">Anticipar cuando y cuanto se cargara</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Integracion con Renovables</div>
    <div class="text-sm">Solar, eolica y carga optima</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-1">Algoritmo de Equilibrio</div>
    <div class="text-sm">Logica de balance energetico</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="badge-ev mb-2">PRACTICA</div>
    <div class="text-sm">Simulacion de balance y algoritmo de equilibrio</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Tecnologias de Carga

<div class="grid grid-cols-3 gap-5 mt-5">
  <div v-click class="card-ev p-5">
    <mdi-home class="text-2xl mb-2" />
    <div class="badge-ev mb-3">120V / 1.4kW</div>
    <div class="text-accent font-bold mb-2">Nivel 1 — AC Lento</div>
    <div class="text-sm muted mb-3">6-20 horas para carga completa</div>
    <div class="text-sm success">Uso: Residencial, pernocta</div>
  </div>
  <div v-click class="card-ev p-5">
    <mdi-office-building class="text-2xl mb-2" />
    <div class="inline-block px-3 py-1 rounded text-xs font-bold mb-3" style="background:#10B981;color:#0D1B2A;">240V / 7-22kW</div>
    <div class="font-bold mb-2" style="color:#10B981;">Nivel 2 — AC Rapido</div>
    <div class="text-sm muted mb-3">2-8 horas</div>
    <div class="text-sm success">Uso: Centros comerciales, oficinas</div>
  </div>
  <div v-click class="card-ev p-5">
    <mdi-lightning-bolt class="text-2xl mb-2" />
    <div class="inline-block px-3 py-1 rounded text-xs font-bold mb-3" style="background:#F59E0B;color:#0D1B2A;">480V / 50-350kW</div>
    <div class="font-bold mb-2 warning">DC Fast Charge</div>
    <div class="text-sm muted mb-3">15-45 minutos</div>
    <div class="text-sm success">Uso: Autopistas, corredores</div>
    <div class="text-xs mt-2" style="color:#ef4444;"><mdi-alert class="inline" /> Acelera degradacion si es frecuente</div>
  </div>
</div>

---
layout: image-right
image: /img/b05-smartgrid.jpg
---

# Smart Grid: La Red Electrica Inteligente

<div class="mt-4 space-y-3 text-sm">
  <div v-click class="flex items-center gap-2">
    <mdi-weather-sunny class="text-accent" />
    <span>Generacion Solar — energia durante el dia</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <mdi-weather-windy class="text-accent" />
    <span>Generacion Eolica — energia variable</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <mdi-factory class="text-accent" />
    <span>Planta Electrica — respaldo tradicional</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <span class="text-accent"><mdi-car-electric class="inline" />→</span>
    <span>Vehiculo Electrico — consume de la red</span>
  </div>
  <div v-click class="flex items-center gap-2">
    <span style="color:#10B981;"><mdi-car-electric class="inline" />↔</span>
    <span class="font-bold" style="color:#10B981;">V2G: Vehiculo como bateria — vende energia</span>
  </div>
</div>

<div v-click class="mt-4 card-ev p-3 text-sm">
  <strong class="text-accent">Vehicle to Grid:</strong> el EV puede vender energia de vuelta a la red — potencial economico para el propietario
</div>

---
layout: default
---

# Predecir Cuando y Cuanto se Cargara

<div class="grid grid-cols-2 gap-6 mt-4">
  <div v-click>
    <div class="card-ev p-4 mb-4">
      <div class="text-accent font-bold mb-2">Curva de Demanda Diaria</div>
      <div class="flex items-end gap-1 h-20 mt-2">
        <div class="flex-1 rounded-t text-xs text-center" style="background:#1B4F72; height:20%;">6h</div>
        <div class="flex-1 rounded-t" style="background:#1B4F72; height:35%;"></div>
        <div class="flex-1 rounded-t" style="background:#1B4F72; height:60%;"></div>
        <div class="flex-1 rounded-t" style="background:#1B4F72; height:45%;"></div>
        <div class="flex-1 rounded-t" style="background:#1B4F72; height:30%;"></div>
        <div class="flex-1 rounded-t" style="background:#F59E0B; height:90%;" title="HORA PICO"></div>
        <div class="flex-1 rounded-t" style="background:#F59E0B; height:95%;"></div>
        <div class="flex-1 rounded-t" style="background:#1B4F72; height:50%;">22h</div>
      </div>
      <div class="text-xs warning mt-2">Zona naranja: HORA PICO (18h-22h)</div>
    </div>
  </div>
  <div v-click class="space-y-4 text-sm">
    <div>
      <div class="text-accent font-bold mb-2">Variables predictoras:</div>
      <ul class="space-y-1 muted">
        <li>• Hora del dia</li>
        <li>• Dia de semana / festivo</li>
        <li>• Temperatura ambiente</li>
        <li>• Eventos locales</li>
        <li>• Historial de dias anteriores</li>
      </ul>
    </div>
    <div>
      <div class="text-accent font-bold mb-2">Modelos utiles:</div>
      <ul class="space-y-1">
        <li>LSTM para series de tiempo</li>
        <li>Random Forest — clasificacion de demanda</li>
        <li>XGBoost — regresion de kW</li>
      </ul>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Carga con Integracion de Energias Renovables

<div class="grid grid-cols-2 gap-6 mt-6">
  <div v-click>
    <div class="font-bold text-red-400 mb-3"><mdi-close-circle class="inline" /> Sin IA — Carga Tradicional</div>
    <div class="space-y-2 text-sm">
      <div class="card-ev p-2" style="background:#2a1010;">Todos cargan a las 7pm (hora pico)</div>
      <div class="card-ev p-2" style="background:#2a1010;">Red estresada, precios altos</div>
      <div class="card-ev p-2" style="background:#2a1010;">Desperdicio de energia solar nocturna</div>
    </div>
  </div>
  <div v-click>
    <div class="font-bold mb-3" style="color:#10B981;">✓ Con IA — Carga Inteligente</div>
    <div class="space-y-2 text-sm">
      <div class="card-ev p-2" style="background:#1a3a2a;">Carga desplazada a horas de alta solar</div>
      <div class="card-ev p-2" style="background:#1a3a2a;">Menor costo energetico para usuario</div>
      <div class="card-ev p-2" style="background:#1a3a2a;">Red balanceada, menos emision CO₂</div>
      <div class="card-ev p-2" style="background:#1a3a2a;">V2G durante picos de precio</div>
    </div>
  </div>
</div>

<img src="/img/b05-solar-panel.jpg" class="mt-5 w-full h-24 object-cover rounded opacity-50" />

---
layout: default
---

# Logica del Algoritmo de Equilibrio

<div v-click class="mt-4 rounded p-4 font-mono text-sm" style="background:#1A1A2E; color:#00D4FF;">
  <div class="muted mb-2"># Pseudocodigo — Algoritmo de Balance Energetico</div>
  <div>MIENTRAS sistema_activo:</div>
  <div class="ml-4">leer(SoC_vehiculo, precio_red, generacion_solar)</div>
  <div class="ml-4 mt-2">SI generacion_solar &gt; demanda_red:</div>
  <div class="ml-8" style="color:#10B981;">activar_carga(EV, potencia=maxima)</div>
  <div class="ml-4 mt-1">SI SINO precio_red &lt; umbral_bajo:</div>
  <div class="ml-8" style="color:#10B981;">activar_carga(EV, potencia=media)</div>
  <div class="ml-4 mt-1">SI SINO SoC_vehiculo &gt; 90% Y precio_red &gt; umbral_alto:</div>
  <div class="ml-8" style="color:#F59E0B;">activar_V2G(EV, potencia=exportar)</div>
  <div class="ml-4 mt-1">SINO:</div>
  <div class="ml-8 muted">esperar(intervalo=15_minutos)</div>
</div>

<div v-click class="mt-4 border rounded p-3 text-sm muted" style="border-color:#64748B;">
  Este es el esquema logico — en practica se entrena un modelo de RL para encontrar la politica optima
</div>

---
layout: default
class: dark-slide
---

# Practica — Bloque 05

<div class="badge-ev mb-4">PRACTICA</div>

## Simulacion de Balance y Algoritmo ML de Equilibrio

<div class="space-y-3 mt-4">
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">1</div>
    <div class="text-sm">Cargar dataset: precio de energia, generacion solar, SoC de flota</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">2</div>
    <div class="text-sm">Visualizar curva de demanda diaria con Matplotlib</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">3</div>
    <div class="text-sm">Implementar logica de carga inteligente (reglas if-else)</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">4</div>
    <div class="text-sm">Entrenar modelo de regresion para predecir punto de equilibrio</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">5</div>
    <div class="text-sm">Comparar consumo total: carga tradicional vs carga inteligente</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-sm flex items-center justify-center flex-shrink-0">6</div>
    <div class="text-sm">Calcular ahorro estimado en kWh y costo</div>
  </div>
</div>

---
layout: center
class: dark-slide
---

# Puntos Clave — Bloque 05

<div class="space-y-3 mt-4 text-left max-w-xl mx-auto">
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Existen 3 niveles de carga con diferentes tiempos y potencias</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Smart Grid permite comunicacion bidireccional con los EV (V2G)</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>La prediccion de demanda optimiza el uso de energia renovable</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Un algoritmo de equilibrio decide CUANDO y CUANTO cargar</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>La integracion de IA reduce costos y estres en la red electrica</span>
  </div>
</div>

<div class="mt-8 text-sm muted">
  > Siguiente: <span class="text-accent font-bold">Bloque 06 — Logistica y Optimizacion de Rutas</span>
</div>
