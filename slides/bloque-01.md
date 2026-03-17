---
theme: penguin
title: "Bloque 01 — Fundamentos de Machine Learning"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque 01
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
zoom: 0.85
fonts:
  sans: 'Segoe UI'
mermaid:
  theme: dark
---

# Bloque 01
## Fundamentos de Machine Learning

Aplicado a la Electromovilidad — Ciudad Juárez, Chihuahua

<div class="abs-br m-6 text-xs text-gray-400">2 horas | Teoria + Practica · UTCJ</div>

<div class="absolute bottom-0 left-0 right-0 flex justify-center items-center gap-10 py-4 px-8" style="background: rgba(13,27,42,0.92); border-top: 1px solid rgba(0,212,255,0.4);">
  <img src="/logos/1%20EDITABLE%20LOGO%20RGB-2.png" class="h-12 object-contain" />
  <img src="/logos/2%20Demoinn_Imagotipo-Color-1-1024x775.png" class="h-20 object-contain" />
  <img src="/logos/3%206647a1a689bdd0ed43fb9444_Logo-Fundacion-Coppel.png" class="h-24 object-contain" />
  <img src="/logos/4%20changeandcodelogoTRANSblack.png" class="h-12 object-contain brightness-0 invert" />
</div>
<img src="/img/b01-ev-street.jpg" class="absolute inset-0 w-full h-full object-cover opacity-20 -z-1" />

---
layout: default
---

# Contenido del Bloque

<img src="/img/b01-analytics.jpg" class="absolute right-0 top-0 h-full w-1/3 object-cover opacity-10 -z-1" />

<div class="slide-scroll">
<div class="grid grid-cols-2 gap-4 mt-4">
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">Tipos de Aprendizaje</div>
    <div class="text-sm">Supervisado, No Supervisado, Refuerzo</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">Dataset y Variables</div>
    <div class="text-sm">Features, etiquetas, anatomia de un dataset</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">Metricas de Evaluacion</div>
    <div class="text-sm">Accuracy, Precision, Recall, RMSE</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">Overfitting y Validacion</div>
    <div class="text-sm">Train/Validation/Test split, generalizacion</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">Herramientas</div>
    <div class="text-sm">Google Colab, Teachable Machines</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="badge-ev mb-2">PRACTICA</div>
    <div class="text-sm">Entrenamiento no-code y analisis de metricas</div>
  </div>
</div>
</div>

---
layout: default
class: dark-slide
---

# ¿Qué es la Inteligencia Artificial?

<img src="/img/b01-ai-brain.jpg" class="absolute right-0 top-0 h-full w-2/5 object-cover opacity-15 -z-1" />

<div class="slide-scroll">
<div class="grid grid-cols-3 gap-5 mt-6">
  <div v-click class="card-ev p-5">
    <mdi-robot class="text-3xl mb-3" />
    <div class="text-accent font-bold text-base mb-2">Inteligencia Artificial</div>
    <div class="text-sm text-gray-300 mb-3">Sistemas que imitan capacidades humanas: razonar, aprender, percibir y tomar decisiones.</div>
    <div class="text-xs muted">Ej: asistentes de voz, autos autónomos, diagnóstico médico</div>
  </div>
  <div v-click class="card-ev p-5" style="background:#1a2e3a; border:1px solid #00D4FF30;">
    <mdi-brain class="text-3xl mb-3" />
    <div class="text-accent font-bold text-base mb-2">Machine Learning</div>
    <div class="text-sm text-gray-300 mb-3">Subconjunto de IA. El sistema <span class="text-accent font-bold">aprende de datos</span> sin ser programado explícitamente para cada tarea.</div>
    <div class="text-xs muted">Ej: predecir fallas de batería, clasificar conductores</div>
  </div>
  <div v-click class="card-ev p-5" style="background:#1a2a1a; border:1px solid #10B98130;">
    <mdi-flask class="text-3xl mb-3" />
    <div class="font-bold text-base mb-2" style="color:#10B981;">Deep Learning</div>
    <div class="text-sm text-gray-300 mb-3">Subconjunto de ML. Usa <span style="color:#10B981;" class="font-bold">redes neuronales profundas</span> con muchas capas para aprender representaciones complejas.</div>
    <div class="text-xs muted">Ej: detección de peatones, reconocimiento de señales</div>
  </div>
</div>
</div>

<div v-click class="mt-5 flex items-center justify-center gap-2 text-sm">
  <div class="card-ev px-4 py-2 text-accent font-bold">IA</div>
  <div class="text-accent text-lg">⊃</div>
  <div class="card-ev px-4 py-2 text-accent font-bold">Machine Learning</div>
  <div class="text-accent text-lg">⊃</div>
  <div class="card-ev px-4 py-2 font-bold" style="color:#10B981;">Deep Learning</div>
  <div class="ml-4 text-xs muted">El DL es un tipo de ML, que a su vez es un tipo de IA</div>
</div>

---
layout: default
class: dark-slide
---

# Mapa Conceptual — IA, ML y Deep Learning

<div class="slide-scroll mt-2">

```mermaid
%%{init: {'theme': 'dark', 'themeVariables': {'primaryColor': '#1B4F72', 'primaryTextColor': '#E8F4FD', 'primaryBorderColor': '#00D4FF', 'lineColor': '#00D4FF', 'secondaryColor': '#0D1B2A', 'tertiaryColor': '#243B55'}}}%%
flowchart TD
    IA["🤖 Inteligencia Artificial\n(1950s →)"] --> SE["Sistemas Expertos\nReglas manuales"]
    IA --> ML["🧠 Machine Learning\nAprende de datos"]
    ML --> CML["ML Clasico\nRandom Forest · SVM · KNN"]
    ML --> DL["🔬 Deep Learning\nRedes Neuronales Profundas"]
    DL --> CNN["CNN\nVision por computadora"]
    DL --> RNN["RNN / LSTM\nSeries temporales BMS"]
    DL --> TR["Transformers\nLLMs — ChatGPT · Claude"]

    style IA fill:#1B4F72,color:#E8F4FD,stroke:#00D4FF
    style ML fill:#1B4F72,color:#00D4FF,stroke:#00D4FF
    style DL fill:#1a3a2a,color:#10B981,stroke:#10B981
    style CML fill:#0D1B2A,color:#E8F4FD,stroke:#1B4F72
    style SE fill:#0D1B2A,color:#64748B,stroke:#64748B
    style CNN fill:#0D1B2A,color:#10B981,stroke:#10B981
    style RNN fill:#0D1B2A,color:#10B981,stroke:#10B981
    style TR fill:#2a1500,color:#F59E0B,stroke:#F59E0B
```

</div>

---
layout: image-right
image: /img/b01-neural-network.jpg
class: dark-slide
---

# ¿Por qué NO usamos LLMs en Electromovilidad?

<div class="flex items-center gap-3 mb-4">
  <div class="text-xs px-3 py-1 rounded-full font-bold" style="background:#ef444420; border:1px solid #ef4444; color:#ef4444;">ChatGPT ✗</div>
  <div class="text-xs px-3 py-1 rounded-full font-bold" style="background:#ef444420; border:1px solid #ef4444; color:#ef4444;">Gemini ✗</div>
  <div class="text-xs px-3 py-1 rounded-full font-bold" style="background:#ef444420; border:1px solid #ef4444; color:#ef4444;">Claude ✗</div>
  <span class="text-xs muted ml-2">para control de hardware EV</span>
</div>

<div class="slide-scroll">
<div class="space-y-2">
  <div v-click class="rounded-lg p-2 border-l-4 flex items-start gap-3" style="background:#1a1020; border-color:#ef4444;">
    <mdi-timer class="text-2xl flex-shrink-0" />
    <div>
      <div class="font-bold text-sm mb-1" style="color:#ef4444;">Latencia inaceptable</div>
      <div class="text-xs text-gray-300">BMS necesita decisiones en <span class="font-bold text-accent">milisegundos</span>. LLM tarda 1–10 seg — inaceptable en frenado regenerativo.</div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2 border-l-4 flex items-start gap-3" style="background:#1a1500; border-color:#F59E0B;">
    <mdi-chart-bar class="text-2xl flex-shrink-0" />
    <div>
      <div class="font-bold text-sm mb-1" style="color:#F59E0B;">Datos numéricos, no texto</div>
      <div class="text-xs text-gray-300">EVs generan voltaje, corriente, temp, GPS. LLMs están hechos para <span style="color:#F59E0B;" class="font-bold">lenguaje</span>, no para series temporales de sensores.</div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2 border-l-4 flex items-start gap-3" style="background:#1a0a2a; border-color:#8B5CF6;">
    <mdi-laptop class="text-2xl flex-shrink-0" />
    <div>
      <div class="font-bold text-sm mb-1" style="color:#8B5CF6;">Costo computacional enorme</div>
      <div class="text-xs text-gray-300">GPT-4: miles de GPUs A100. ECU embebida: recursos limitados. ML clásico corre en <span style="color:#8B5CF6;" class="font-bold">STM32</span> dentro del vehículo.</div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2 border-l-4 flex items-start gap-3" style="background:#0a1a10; border-color:#10B981;">
    <mdi-magnify class="text-2xl flex-shrink-0" />
    <div>
      <div class="font-bold text-sm mb-1" style="color:#10B981;">Explicabilidad obligatoria</div>
      <div class="text-xs text-gray-300">Norma <span style="color:#10B981;" class="font-bold">ISO 26262</span> exige modelos auditables. LLMs son cajas negras — no certificables para seguridad automotriz.</div>
    </div>
  </div>
</div>
</div>

---
layout: default
class: dark-slide
---

# Problemas Técnicos de los LLMs

<img src="/img/b01-matrix.jpg" class="absolute inset-0 w-full h-full object-cover opacity-5 -z-1" />

<div class="slide-scroll">
<div class="grid grid-cols-3 gap-3 mt-3">
  <div v-click class="rounded-lg p-4" style="background:#2a0a0a; border:1px solid #ef4444;">
    <div class="flex items-center justify-between mb-2">
      <mdi-emoticon-confused class="text-2xl" />
      <div class="flex gap-1">
        <div class="w-2 h-2 rounded-full" style="background:#ef4444;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#ef4444;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#ef4444;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#ef4444;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#ef4444;"></div>
      </div>
    </div>
    <div class="font-bold mb-1 text-sm" style="color:#ef4444;">Alucinaciones</div>
    <div class="text-xs text-gray-300 mb-2">Inventa datos con confianza. Puede "reportar" SoC 87% cuando es 23%.</div>
    <div class="text-xs px-2 py-1 rounded" style="background:#3a0a0a; color:#ef4444;">Crítico en seguridad</div>
  </div>
  <div v-click class="rounded-lg p-4" style="background:#2a1a00; border:1px solid #F59E0B;">
    <div class="flex items-center justify-between mb-2">
      <mdi-antenna class="text-2xl" />
      <div class="flex gap-1">
        <div class="w-2 h-2 rounded-full" style="background:#F59E0B;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#F59E0B;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#F59E0B;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#F59E0B;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#333;"></div>
      </div>
    </div>
    <div class="font-bold mb-1 text-sm" style="color:#F59E0B;">Requiere conectividad</div>
    <div class="text-xs text-gray-300 mb-2">Sin señal en el desierto de Chihuahua → sin predicción.</div>
    <div class="text-xs px-2 py-1 rounded" style="background:#3a2a00; color:#F59E0B;">Falla offline</div>
  </div>
  <div v-click class="rounded-lg p-4" style="background:#0a1a2a; border:1px solid #00D4FF;">
    <div class="flex items-center justify-between mb-2">
      <mdi-lock class="text-2xl" />
      <div class="flex gap-1">
        <div class="w-2 h-2 rounded-full" style="background:#00D4FF;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#00D4FF;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#00D4FF;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#333;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#333;"></div>
      </div>
    </div>
    <div class="font-bold mb-1 text-sm" style="color:#00D4FF;">Privacidad de datos</div>
    <div class="text-xs text-gray-300 mb-2">Rutas y hábitos de flota enviados a API externa. Datos IMMEX son confidenciales.</div>
    <div class="text-xs px-2 py-1 rounded" style="background:#0a0a1a; color:#00D4FF;">Riesgo legal</div>
  </div>
  <div v-click class="rounded-lg p-4" style="background:#1a0a2a; border:1px solid #8B5CF6;">
    <div class="flex items-center justify-between mb-2">
      <mdi-calculator class="text-2xl" />
      <div class="flex gap-1">
        <div class="w-2 h-2 rounded-full" style="background:#8B5CF6;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#8B5CF6;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#8B5CF6;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#8B5CF6;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#333;"></div>
      </div>
    </div>
    <div class="font-bold mb-1 text-sm" style="color:#8B5CF6;">Aritmética imprecisa</div>
    <div class="text-xs text-gray-300 mb-2">RF: RMSE ~8 km en autonomía. LLM: aproximaciones impredecibles.</div>
    <div class="text-xs px-2 py-1 rounded" style="background:#2a0a3a; color:#8B5CF6;">Precisión no garantizada</div>
  </div>
  <div v-click class="rounded-lg p-4" style="background:#1a2a0a; border:1px solid #10B981;">
    <div class="flex items-center justify-between mb-2">
      <mdi-lightning-bolt class="text-2xl" />
      <div class="flex gap-1">
        <div class="w-2 h-2 rounded-full" style="background:#10B981;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#10B981;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#10B981;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#10B981;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#333;"></div>
      </div>
    </div>
    <div class="font-bold mb-1 text-sm" style="color:#10B981;">Consume demasiada energía</div>
    <div class="text-xs text-gray-300 mb-2">GPT-4: ~50 GWh de entrenamiento. Árbol de decisión: &lt;1W en ECU.</div>
    <div class="text-xs px-2 py-1 rounded" style="background:#0a1a00; color:#10B981;">Contradice el EV</div>
  </div>
  <div v-click class="rounded-lg p-4" style="background:#1a1a1a; border:1px solid #64748B;">
    <div class="flex items-center justify-between mb-2">
      <mdi-trending-down class="text-2xl" />
      <div class="flex gap-1">
        <div class="w-2 h-2 rounded-full" style="background:#64748B;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#64748B;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#333;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#333;"></div>
        <div class="w-2 h-2 rounded-full" style="background:#333;"></div>
      </div>
    </div>
    <div class="font-bold mb-1 text-sm" style="color:#94a3b8;">Sobreingeniería</div>
    <div class="text-xs text-gray-300 mb-2">5 variables de sensor → Random Forest supera al LLM en velocidad, costo y precisión.</div>
    <div class="text-xs px-2 py-1 rounded" style="background:#111; color:#64748B;">Herramienta incorrecta</div>
  </div>
</div>
</div>

<div v-after class="mt-3 text-center text-xs muted">● = nivel de severidad del problema</div>

---
layout: default
class: dark-slide
---

# LLMs vs ML Clásico — ¿Cuál usar en EV?

<div class="grid grid-cols-5 gap-0 mt-1 mb-2 rounded overflow-hidden text-xs font-bold">
  <div class="col-span-2 px-3 py-1.5" style="background:#1B4F72;">Criterio</div>
  <div class="px-2 py-1.5 text-center" style="background:#3a1010; color:#ef4444;"><mdi-robot class="inline" /> LLM</div>
  <div class="px-2 py-1.5 text-center" style="background:#103a10; color:#10B981;"><mdi-brain class="inline" /> ML Clásico</div>
  <div class="px-2 py-1.5 text-center" style="background:#1B4F72; color:#00D4FF;">Ganador</div>
</div>

<div class="slide-scroll">
<div class="space-y-1 text-xs">
  <div v-click class="grid grid-cols-5 gap-0 rounded overflow-hidden">
    <div class="col-span-2 px-3 py-1.5 font-bold" style="background:#1a1a2a;"><mdi-timer class="inline" /> Latencia</div>
    <div class="px-2 py-1.5 text-center" style="background:#2a1010; color:#ef4444;">1–10 segundos</div>
    <div class="px-2 py-1.5 text-center" style="background:#102a10; color:#10B981;">1–10 ms</div>
    <div class="px-2 py-1.5 text-center font-bold" style="background:#10B98120; color:#10B981;">ML ✓</div>
  </div>
  <div v-click class="grid grid-cols-5 gap-0 rounded overflow-hidden">
    <div class="col-span-2 px-3 py-1.5 font-bold" style="background:#151520;"><mdi-chart-bar class="inline" /> Tipo de datos</div>
    <div class="px-2 py-1.5 text-center" style="background:#251515; color:#ef4444;">Texto / NLP</div>
    <div class="px-2 py-1.5 text-center" style="background:#152515; color:#10B981;">Tabular / sensores</div>
    <div class="px-2 py-1.5 text-center font-bold" style="background:#10B98120; color:#10B981;">ML ✓</div>
  </div>
  <div v-click class="grid grid-cols-5 gap-0 rounded overflow-hidden">
    <div class="col-span-2 px-3 py-1.5 font-bold" style="background:#1a1a2a;"><mdi-antenna class="inline" /> Offline</div>
    <div class="px-2 py-1.5 text-center" style="background:#2a1010; color:#ef4444;">No — requiere nube</div>
    <div class="px-2 py-1.5 text-center" style="background:#102a10; color:#10B981;">Sí — ECU local</div>
    <div class="px-2 py-1.5 text-center font-bold" style="background:#10B98120; color:#10B981;">ML ✓</div>
  </div>
  <div v-click class="grid grid-cols-5 gap-0 rounded overflow-hidden">
    <div class="col-span-2 px-3 py-1.5 font-bold" style="background:#151520;"><mdi-magnify class="inline" /> Explicabilidad</div>
    <div class="px-2 py-1.5 text-center" style="background:#251515; color:#ef4444;">Caja negra</div>
    <div class="px-2 py-1.5 text-center" style="background:#152515; color:#10B981;">ISO 26262 ✓</div>
    <div class="px-2 py-1.5 text-center font-bold" style="background:#10B98120; color:#10B981;">ML ✓</div>
  </div>
  <div v-click class="grid grid-cols-5 gap-0 rounded overflow-hidden">
    <div class="col-span-2 px-3 py-1.5 font-bold" style="background:#1a1a2a;"><mdi-currency-usd class="inline" /> Costo</div>
    <div class="px-2 py-1.5 text-center" style="background:#2a1010; color:#ef4444;">Alto — API $$$</div>
    <div class="px-2 py-1.5 text-center" style="background:#102a10; color:#10B981;">Bajo — local</div>
    <div class="px-2 py-1.5 text-center font-bold" style="background:#10B98120; color:#10B981;">ML ✓</div>
  </div>
  <div v-click class="grid grid-cols-5 gap-0 rounded overflow-hidden">
    <div class="col-span-2 px-3 py-1.5 font-bold" style="background:#151520;"><mdi-target class="inline" /> Precisión</div>
    <div class="px-2 py-1.5 text-center" style="background:#251515; color:#ef4444;">Alucinaciones</div>
    <div class="px-2 py-1.5 text-center" style="background:#152515; color:#10B981;">RMSE controlable</div>
    <div class="px-2 py-1.5 text-center font-bold" style="background:#10B98120; color:#10B981;">ML ✓</div>
  </div>
</div>

</div>
<div v-after class="mt-2 rounded px-3 py-1.5 text-center text-xs font-bold" style="background:#10B98115; border:1px solid #10B981;">
  Resultado: <span style="color:#10B981;">ML Clásico 6</span> — <span style="color:#ef4444;">LLM 0</span> en aplicaciones EV críticas
</div>

---
layout: image-right
image: /img/b01-ai-brain.jpg
class: dark-slide
---

# ¿Cuándo SÍ tienen sentido los LLMs?

<div class="text-xs text-gray-400 mb-4 rounded p-2" style="background:#1B4F7240; border-left:3px solid #00D4FF;">
  Casos válidos: <span class="text-accent font-bold">soporte y gestión</span>, nunca control de hardware crítico
</div>

<div class="slide-scroll">
<div class="space-y-2">
  <div v-click class="rounded-lg p-2 flex items-start gap-3" style="background:#1a2a1a; border:1px solid #10B98130;">
    <mdi-chat class="text-2xl flex-shrink-0" />
    <div>
      <div class="font-bold text-sm mb-1" style="color:#10B981;">Asistente de flota para operadores</div>
      <div class="text-xs text-gray-300">"¿Cuál unidad tiene mayor riesgo hoy?" → LLM interpreta → consulta dashboard ML → responde en lenguaje natural.</div>
      <div class="inline-block mt-1 px-2 py-0.5 rounded text-xs font-bold" style="background:#10B98120; color:#10B981;">Interfaz NLP → ML</div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2 flex items-start gap-3" style="background:#1a2010; border:1px solid #00D4FF30;">
    <mdi-clipboard-list class="text-2xl flex-shrink-0" />
    <div>
      <div class="font-bold text-sm mb-1 text-accent">Generación de reportes técnicos</div>
      <div class="text-xs text-gray-300">Modelo ML detecta anomalía → LLM redacta el reporte en español para el técnico de Foxconn Juárez.</div>
      <div class="inline-block mt-1 px-2 py-0.5 rounded text-xs font-bold" style="background:#00D4FF15; color:#00D4FF;">Post-procesamiento</div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2 flex items-start gap-3" style="background:#20182a; border:1px solid #8B5CF630;">
    <mdi-school class="text-2xl flex-shrink-0" />
    <div>
      <div class="font-bold text-sm mb-1" style="color:#8B5CF6;">Capacitación de conductores</div>
      <div class="text-xs text-gray-300">Chatbot sobre carga nocturna CFE y manejo eficiente en calor extremo (45°C verano Juárez).</div>
      <div class="inline-block mt-1 px-2 py-0.5 rounded text-xs font-bold" style="background:#8B5CF620; color:#8B5CF6;">Educación</div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2 flex items-start gap-3" style="background:#1a1a2a; border:1px solid #F59E0B30;">
    <mdi-wrench class="text-2xl flex-shrink-0" />
    <div>
      <div class="font-bold text-sm mb-1" style="color:#F59E0B;">RAG sobre manuales técnicos</div>
      <div class="text-xs text-gray-300">Consulta instantánea de manuales BYD, Nissan Leaf, VW ID.4 sin revisar 500+ páginas manualmente.</div>
      <div class="inline-block mt-1 px-2 py-0.5 rounded text-xs font-bold" style="background:#F59E0B20; color:#F59E0B;">Recuperación info</div>
    </div>
  </div>
</div>
</div>

<div v-after class="mt-3 rounded p-2 text-xs text-center font-bold" style="background:#1B4F72; border:1px solid #00D4FF40;">
  <mdi-key class="inline" /> <span class="text-accent">El LLM habla con el humano</span> — <span style="color:#10B981;">el modelo ML habla con el hardware</span>
</div>

---
layout: default
class: dark-slide
---

# Tipos de Aprendizaje en Machine Learning

<div class="slide-scroll">
<div class="grid grid-cols-3 gap-6 mt-6">
  <div v-click class="card-ev p-5 text-center">
    <mdi-school class="text-3xl mb-2" />
    <div class="text-accent font-bold text-lg mb-2">Supervisado</div>
    <div class="text-sm text-gray-300">Aprende con datos etiquetados</div>
    <div class="badge-ev mt-3">ETIQUETADO</div>
  </div>
  <div v-click class="card-ev p-5 text-center" style="background: #1a3a2a;">
    <mdi-magnify class="text-3xl mb-2" />
    <div class="font-bold text-lg mb-2" style="color: #10B981;">No Supervisado</div>
    <div class="text-sm text-gray-300">Encuentra patrones sin etiquetas</div>
    <div class="inline-block px-3 py-1 rounded text-xs font-bold mt-3" style="background: #10B981; color: #0D1B2A;">SIN ETIQUETAS</div>
  </div>
  <div v-click class="card-ev p-5 text-center" style="background: #2a2010;">
    <mdi-gamepad-variant class="text-3xl mb-2" />
    <div class="font-bold text-lg mb-2" style="color: #F59E0B;">Por Refuerzo</div>
    <div class="text-sm text-gray-300">Aprende por recompensas</div>
    <div class="inline-block px-3 py-1 rounded text-xs font-bold mt-3" style="background: #F59E0B; color: #0D1B2A;">RECOMPENSA</div>
  </div>
</div>
</div>

<div v-click class="mt-6 text-center text-sm muted">Veamos cada uno en detalle →</div>

<img src="/img/b01-neural-network.jpg" class="absolute inset-0 w-full h-full object-cover opacity-5 -z-1" />

---
layout: default
class: dark-slide
---

# ¿Qué paradigma ML usar en tu proyecto EV?

<div class="slide-scroll mt-2">

```mermaid
%%{init: {'theme': 'dark', 'themeVariables': {'primaryColor': '#1B4F72', 'primaryTextColor': '#E8F4FD', 'primaryBorderColor': '#00D4FF', 'lineColor': '#00D4FF'}}}%%
flowchart TD
    D[("📊 Datos de Sensores EV\nBMS · GPS · CAN Bus")] --> Q{"¿Tienes etiquetas\nen tus datos?"}
    Q -->|"Sí — falla/normal\nautonomia_km"| SUP["✅ Supervisado\nClasificacion · Regresion"]
    Q -->|"No — solo\nobservaciones"| UNSUP["✅ No Supervisado\nClustering · Anomalias"]
    Q -->|"Interaccion con\nel entorno"| RL["✅ Por Refuerzo\nOptimizacion de politicas"]

    SUP --> S1["Random Forest\nRegresion Lineal · KNN"]
    UNSUP --> U1["K-Means · DBSCAN\nIsolation Forest · PCA"]
    RL --> R1["Q-Learning · DQN\nPPO · Multi-Agent RL"]

    style D fill:#1B4F72,color:#E8F4FD,stroke:#00D4FF
    style Q fill:#243B55,color:#00D4FF,stroke:#00D4FF
    style SUP fill:#1B4F72,color:#00D4FF,stroke:#00D4FF
    style UNSUP fill:#1a3a2a,color:#10B981,stroke:#10B981
    style RL fill:#2a2010,color:#F59E0B,stroke:#F59E0B
    style S1 fill:#0D1B2A,color:#E8F4FD,stroke:#1B4F72
    style U1 fill:#0D1B2A,color:#E8F4FD,stroke:#1B4F72
    style R1 fill:#0D1B2A,color:#E8F4FD,stroke:#1B4F72
```

</div>

---
layout: default
class: dark-slide
---

# <mdi-school class="inline" /> Aprendizaje Supervisado

<div class="slide-scroll">
<div class="grid grid-cols-2 gap-4 mt-2">
  <div>
    <div class="text-accent font-bold mb-2">¿Como funciona?</div>
    <div class="text-sm mb-4">
      El modelo recibe <span class="text-accent font-bold">datos de entrada (X)</span> junto con la
      <span class="text-accent font-bold">respuesta correcta (Y)</span>. Aprende la relacion entre ambos
      para predecir Y en datos nuevos.
    </div>
    <div class="card-ev p-3 mb-3 text-sm">
      <div class="font-bold text-accent mb-1"><mdi-download class="inline" /> Entrada (X)</div>
      temperatura, voltaje, corriente, km recorridos
    </div>
    <div class="card-ev p-3 text-sm" style="border: 1px solid #00D4FF;">
      <div class="font-bold text-accent mb-1"><mdi-upload class="inline" /> Salida (Y)</div>
      falla / normal, autonomia_km, SoC %
    </div>
  </div>
  <div>
    <div class="font-bold mb-2" style="color: #10B981;"><mdi-calculator class="inline" /> Algoritmos Principales</div>
    <div class="space-y-2">
      <div v-click class="card-ev p-3 text-sm">
        <span class="text-accent font-bold">Regresion Lineal</span> — Predice valores continuos<br>
        <span class="muted text-xs">Ej: predecir autonomia restante en km</span>
      </div>
      <div v-click class="card-ev p-3 text-sm">
        <span class="text-accent font-bold">Regresion Logistica</span> — Clasifica en 2 categorias<br>
        <span class="muted text-xs">Ej: bateria falla SI / NO</span>
      </div>
      <div v-click class="card-ev p-3 text-sm">
        <span class="text-accent font-bold">Arboles de Decision</span> — Reglas tipo if/else<br>
        <span class="muted text-xs">Ej: si temp > 40°C y ciclos > 500 → riesgo alto</span>
      </div>
      <div v-click class="card-ev p-3 text-sm">
        <span class="text-accent font-bold">Random Forest</span> — Multiples arboles votando<br>
        <span class="muted text-xs">Ej: clasificar tipo de manejo (suave/normal/agresivo)</span>
      </div>
      <div v-click class="card-ev p-3 text-sm">
        <span class="text-accent font-bold">KNN (K-Nearest Neighbors)</span> — Clasifica por vecinos cercanos<br>
        <span class="muted text-xs">Ej: identificar tipo de vehiculo por patrones de carga</span>
      </div>
    </div>
  </div>
</div>
</div>

---
layout: default
class: dark-slide
---

# Pipeline de Entrenamiento Supervisado

<div class="slide-scroll mt-3">

```mermaid
%%{init: {'theme': 'dark', 'themeVariables': {'primaryColor': '#1B4F72', 'primaryTextColor': '#E8F4FD', 'primaryBorderColor': '#00D4FF', 'lineColor': '#00D4FF'}}}%%
flowchart LR
    A[("🔌 Datos EV\nBMS · GPS · CAN")] --> B["Preprocesamiento\nlimpieza · normalización"]
    B --> C["Split Dataset\n70% Train | 15% Val | 15% Test"]
    C --> D["Entrenamiento\nRandom Forest · KNN"]
    D --> E{"Evaluacion\nAccuracy · RMSE"}
    E -->|"No satisfactorio\najustar hiperparametros"| B
    E -->|"✓ Listo"| F["Deploy en ECU\ndel vehiculo EV"]

    style A fill:#1B4F72,color:#E8F4FD,stroke:#00D4FF
    style B fill:#243B55,color:#E8F4FD,stroke:#1B4F72
    style C fill:#1B4F72,color:#00D4FF,stroke:#00D4FF
    style D fill:#243B55,color:#E8F4FD,stroke:#1B4F72
    style E fill:#2a1500,color:#F59E0B,stroke:#F59E0B
    style F fill:#1a3a2a,color:#10B981,stroke:#10B981
```

</div>

---
layout: default
class: dark-slide
---

# <mdi-school class="inline" /> Supervisado — Ejemplos en Electromovilidad

<div class="space-y-2 mt-2">
  <div v-click class="card-ev p-2">
    <div class="flex items-start gap-2">
      <mdi-battery class="text-xl" />
      <div>
        <div class="text-accent font-bold mb-1">Prediccion de fallas en celdas — Foxconn Juárez</div>
        <div class="text-xs mb-1">Random Forest analiza voltaje, corriente y temperatura para predecir si una celda fallará en las proximas 24 horas.</div>
        <div class="flex gap-2">
          <span class="badge-ev text-xs">Clasificacion</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">Random Forest</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">Accuracy: ~95%</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="card-ev p-2">
    <div class="flex items-start gap-2">
      <mdi-car-electric class="text-xl" />
      <div>
        <div class="text-accent font-bold mb-1">Estimacion de autonomia en desierto de Chihuahua</div>
        <div class="text-xs mb-1">Regresion lineal con temperatura exterior (45°C verano), AC, velocidad y pendiente para estimar km restantes.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#10B981; color:#0D1B2A;">Regresion</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">Regresion Lineal</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">RMSE: ~8 km</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="card-ev p-2">
    <div class="flex items-start gap-2">
      <mdi-lightning-bolt class="text-xl" />
      <div>
        <div class="text-accent font-bold mb-1">Clasificacion de estilo de manejo — Blvd. Zaragoza</div>
        <div class="text-xs mb-1">Arbol de decision analiza aceleracion, frenado y velocidad promedio para clasificar conductor: suave / normal / agresivo.</div>
        <div class="flex gap-2">
          <span class="badge-ev text-xs">Clasificacion</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">Arbol de Decision</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">3 clases</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="card-ev p-2">
    <div class="flex items-start gap-2">
      <mdi-power-plug class="text-xl" />
      <div>
        <div class="text-accent font-bold mb-1">Prediccion de SoC al llegar al cruce fronterizo</div>
        <div class="text-xs mb-1">KNN estima el SoC para la espera en Puente Zaragoza (1-3 hrs con AC) más el tramo freeway en El Paso.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#10B981; color:#0D1B2A;">Regresion</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">KNN</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">SoC %</span>
        </div>
      </div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# <mdi-magnify class="inline" /> Aprendizaje No Supervisado

<img src="/img/b01-data-chart.jpg" class="absolute inset-0 w-full h-full object-cover opacity-5 -z-1" />

<div class="slide-scroll">
<div class="grid grid-cols-2 gap-4 mt-2">
  <div>
    <div style="color: #10B981;" class="font-bold mb-2">¿Como funciona?</div>
    <div class="text-sm mb-4">
      El modelo recibe <span style="color:#10B981;" class="font-bold">solo datos de entrada (X)</span>,
      <span style="color:#ef4444;" class="font-bold">sin respuestas correctas</span>.
      El algoritmo descubre patrones, grupos o anomalias por si mismo.
    </div>
    <div class="rounded-lg p-3 mb-3 text-sm" style="background:#1a3a2a; border: 1px solid #10B981;">
      <div class="font-bold mb-1" style="color:#10B981;"><mdi-download class="inline" /> Entrada (X)</div>
      velocidad, aceleracion, hora de carga, consumo kWh, ruta GPS
    </div>
    <div class="rounded-lg p-3 text-sm" style="background:#2a1a1a; border: 1px solid #ef4444;">
      <div class="font-bold mb-1" style="color:#ef4444;"><mdi-close-circle class="inline" /> NO hay salida (Y)</div>
      El modelo descubre la estructura oculta en los datos
    </div>
  </div>
  <div>
    <div class="font-bold mb-2" style="color: #10B981;"><mdi-calculator class="inline" /> Algoritmos Principales</div>
    <div class="space-y-2">
      <div v-click class="rounded-lg p-3 text-sm" style="background:#1a3a2a;">
        <span style="color:#10B981;" class="font-bold">K-Means</span> — Agrupa datos en K clusters<br>
        <span class="muted text-xs">Ej: agrupar conductores por perfil de manejo</span>
      </div>
      <div v-click class="rounded-lg p-3 text-sm" style="background:#1a3a2a;">
        <span style="color:#10B981;" class="font-bold">DBSCAN</span> — Clusters por densidad<br>
        <span class="muted text-xs">Ej: detectar zonas con alta demanda de carga en Juárez</span>
      </div>
      <div v-click class="rounded-lg p-3 text-sm" style="background:#1a3a2a;">
        <span style="color:#10B981;" class="font-bold">PCA</span> — Reduce dimensiones de datos<br>
        <span class="muted text-xs">Ej: simplificar 50 sensores CAN Bus a las 5 variables clave</span>
      </div>
      <div v-click class="rounded-lg p-3 text-sm" style="background:#1a3a2a;">
        <span style="color:#10B981;" class="font-bold">Isolation Forest</span> — Detecta anomalias<br>
        <span class="muted text-xs">Ej: detectar cargas anormales en una flota nocturna</span>
      </div>
      <div v-click class="rounded-lg p-3 text-sm" style="background:#1a3a2a;">
        <span style="color:#10B981;" class="font-bold">Autoencoders</span> — Red neuronal para anomalias<br>
        <span class="muted text-xs">Ej: detectar degradacion temprana en packs de baterias</span>
      </div>
    </div>
  </div>
</div>
</div>

---
layout: default
class: dark-slide
---

# <mdi-magnify class="inline" /> No Supervisado — Ejemplos en Electromovilidad

<div class="space-y-2 mt-2">
  <div v-click class="rounded-lg p-2" style="background:#1a3a2a; border: 1px solid #10B98140;">
    <div class="flex items-start gap-2">
      <mdi-account-group class="text-xl" />
      <div>
        <div class="font-bold mb-1" style="color:#10B981;">Segmentacion de conductores — Corredor IMMEX</div>
        <div class="text-xs mb-1">K-Means agrupa 200 conductores en 4 perfiles (economico, normal, agresivo, variable) para adaptar alertas por grupo.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#10B981; color:#0D1B2A;">Clustering</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">K-Means</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">4 clusters</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2" style="background:#1a3a2a; border: 1px solid #10B98140;">
    <div class="flex items-start gap-2">
      <mdi-alarm-light class="text-xl" />
      <div>
        <div class="font-bold mb-1" style="color:#10B981;">Deteccion de anomalias en carga nocturna</div>
        <div class="text-xs mb-1">Isolation Forest detecta si una unidad carga 40% mas lento que lo habitual y genera alerta de degradacion.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#10B981; color:#0D1B2A;">Anomalias</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">Isolation Forest</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">Sin etiquetas</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2" style="background:#1a3a2a; border: 1px solid #10B98140;">
    <div class="flex items-start gap-2">
      <mdi-map class="text-xl" />
      <div>
        <div class="font-bold mb-1" style="color:#10B981;">Segmentacion de rutas Juárez–El Paso</div>
        <div class="text-xs mb-1">DBSCAN descubre perfiles distintos entre rutas: Puente Libre vs Puente Zaragoza tienen consumo, distancia y tiempo completamente diferentes.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#10B981; color:#0D1B2A;">Clustering</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">DBSCAN</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">Rutas GPS</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2" style="background:#1a3a2a; border: 1px solid #10B98140;">
    <div class="flex items-start gap-2">
      <mdi-trending-down class="text-xl" />
      <div>
        <div class="font-bold mb-1" style="color:#10B981;">Reduccion de datos CAN Bus — Continental Juárez</div>
        <div class="text-xs mb-1">PCA reduce 50+ señales del CAN Bus a 5-7 componentes que explican el 95% de la varianza, simplificando el monitoreo.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#10B981; color:#0D1B2A;">Reduccion</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">PCA</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">50 → 5 variables</span>
        </div>
      </div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# <mdi-gamepad-variant class="inline" /> Aprendizaje por Refuerzo

<img src="/img/b01-ai-brain.jpg" class="absolute inset-0 w-full h-full object-cover opacity-5 -z-1" />

<div class="slide-scroll">
<div class="grid grid-cols-2 gap-4 mt-2">
  <div>
    <div style="color: #F59E0B;" class="font-bold mb-2">¿Como funciona?</div>
    <div class="text-sm mb-4">
      Un <span style="color:#F59E0B;" class="font-bold">agente</span> interactua con un
      <span style="color:#F59E0B;" class="font-bold">entorno</span>, toma
      <span style="color:#F59E0B;" class="font-bold">acciones</span> y recibe
      <span style="color:#F59E0B;" class="font-bold">recompensas</span> o penalizaciones.
      Aprende la mejor estrategia por prueba y error.
    </div>
    <div class="rounded-lg p-4 text-sm" style="background:#2a2010; border: 1px solid #F59E0B40;">
      <div class="space-y-2">
        <div class="flex items-center gap-2">
          <span style="color:#F59E0B;" class="font-bold"><mdi-robot class="inline" /> Agente:</span>
          <span>El que toma decisiones</span>
        </div>
        <div class="flex items-center gap-2">
          <span style="color:#F59E0B;" class="font-bold"><mdi-earth class="inline" /> Entorno:</span>
          <span>El mundo donde opera</span>
        </div>
        <div class="flex items-center gap-2">
          <span style="color:#F59E0B;" class="font-bold"><mdi-lightning-bolt class="inline" /> Accion:</span>
          <span>Lo que hace en cada paso</span>
        </div>
        <div class="flex items-center gap-2">
          <span style="color:#F59E0B;" class="font-bold"><mdi-trophy class="inline" /> Recompensa:</span>
          <span>+1 si fue buena, -1 si no</span>
        </div>
        <div class="flex items-center gap-2">
          <span style="color:#F59E0B;" class="font-bold"><mdi-clipboard-list class="inline" /> Politica:</span>
          <span>La estrategia aprendida</span>
        </div>
      </div>
    </div>
  </div>
  <div>
    <div class="font-bold mb-2" style="color: #F59E0B;"><mdi-calculator class="inline" /> Algoritmos Principales</div>
    <div class="space-y-2">
      <div v-click class="rounded-lg p-3 text-sm" style="background:#2a2010;">
        <span style="color:#F59E0B;" class="font-bold">Q-Learning</span> — Tabla de valores por estado-accion<br>
        <span class="muted text-xs">Ej: aprender mejor ruta en un grid de calles</span>
      </div>
      <div v-click class="rounded-lg p-3 text-sm" style="background:#2a2010;">
        <span style="color:#F59E0B;" class="font-bold">Deep Q-Network (DQN)</span> — Q-Learning + red neuronal<br>
        <span class="muted text-xs">Ej: control de semáforos con miles de estados posibles</span>
      </div>
      <div v-click class="rounded-lg p-3 text-sm" style="background:#2a2010;">
        <span style="color:#F59E0B;" class="font-bold">PPO</span> — Policy Optimization estable<br>
        <span class="muted text-xs">Ej: conduccion autonoma (usado por Tesla, Waymo)</span>
      </div>
      <div v-click class="rounded-lg p-3 text-sm" style="background:#2a2010;">
        <span style="color:#F59E0B;" class="font-bold">SARSA</span> — Aprende de la accion que realmente toma<br>
        <span class="muted text-xs">Ej: gestion conservadora de energia en bateria</span>
      </div>
      <div v-click class="rounded-lg p-3 text-sm" style="background:#2a2010;">
        <span style="color:#F59E0B;" class="font-bold">Multi-Agent RL</span> — Multiples agentes cooperando<br>
        <span class="muted text-xs">Ej: coordinar carga de 50 EVs en un parque industrial</span>
      </div>
    </div>
  </div>
</div>
</div>

---
layout: default
class: dark-slide
---

# Ciclo del Agente de Aprendizaje por Refuerzo

<div class="slide-scroll mt-4">

```mermaid
%%{init: {'theme': 'dark', 'themeVariables': {'primaryColor': '#1B4F72', 'primaryTextColor': '#E8F4FD', 'primaryBorderColor': '#00D4FF', 'lineColor': '#F59E0B'}}}%%
flowchart LR
    AGT(["🤖 Agente RL\nModelo de politica"]) -->|"⚡ Accion\ncargar · descargar\noptimizar semaforo"| ENV(["🌍 Entorno\nRed CFE · Trafico\nBMS del vehiculo"])
    ENV -->|"📡 Nuevo Estado\nprecio kWh · SoC\ncongestion vial"| AGT
    ENV -->|"🏆 Recompensa\n+ahorro · -multa\n-tiempo espera"| AGT
    AGT --- POL[("📋 Politica\nEstrategia\naprendida")]

    style AGT fill:#2a2010,color:#F59E0B,stroke:#F59E0B
    style ENV fill:#1B4F72,color:#E8F4FD,stroke:#00D4FF
    style POL fill:#0D1B2A,color:#F59E0B,stroke:#F59E0B
```

<div class="mt-4 text-xs text-center muted">El agente mejora su política iterativamente — con cada episodio aprende a maximizar la recompensa acumulada</div>
</div>

---
layout: default
class: dark-slide
---

# <mdi-gamepad-variant class="inline" /> Por Refuerzo — Ejemplos en Electromovilidad

<div class="space-y-2 mt-2">
  <div v-click class="rounded-lg p-2" style="background:#2a2010; border: 1px solid #F59E0B40;">
    <div class="flex items-start gap-2">
      <mdi-traffic-light class="text-xl" />
      <div>
        <div class="font-bold mb-1" style="color:#F59E0B;">Optimizacion de semáforos — Tecnologico y Zaragoza</div>
        <div class="text-xs mb-1">DQN controla ciclos de semáforos. Recompensa: reducir espera. Penalizacion: congestion o alto consumo de EVs frenando/arrancando.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#F59E0B; color:#0D1B2A;">Optimizacion</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">DQN</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">-20% espera</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2" style="background:#2a2010; border: 1px solid #F59E0B40;">
    <div class="flex items-start gap-2">
      <mdi-lightning-bolt class="text-xl" />
      <div>
        <div class="font-bold mb-1" style="color:#F59E0B;">Gestion de carga V2G — Horario pico CFE</div>
        <div class="text-xs mb-1">PPO decide cuándo cargar y cuándo devolver energía. Aprovecha tarifa baja nocturna y vende en hora pico para maximizar ahorro.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#F59E0B; color:#0D1B2A;">Energia</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">PPO</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">V2G Bidireccional</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2" style="background:#2a2010; border: 1px solid #F59E0B40;">
    <div class="flex items-start gap-2">
      <mdi-taxi class="text-xl" />
      <div>
        <div class="font-bold mb-1" style="color:#F59E0B;">Ruteo de taxis electricos — Ciudad Juárez</div>
        <div class="text-xs mb-1">Q-Learning evita topes, subidas y cruces con frenado intenso. Recompensa: maximizar km por kWh consumido.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#F59E0B; color:#0D1B2A;">Ruteo</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">Q-Learning</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">Min energia</span>
        </div>
      </div>
    </div>
  </div>
  <div v-click class="rounded-lg p-2" style="background:#2a2010; border: 1px solid #F59E0B40;">
    <div class="flex items-start gap-2">
      <mdi-factory class="text-xl" />
      <div>
        <div class="font-bold mb-1" style="color:#F59E0B;">Coordinacion de carga — Parque Industrial Bermúdez</div>
        <div class="text-xs mb-1">Multi-Agent RL coordina 50 EVs para no exceder el límite de la subestacion CFE. Cada EV negocia su turno de carga.</div>
        <div class="flex gap-2">
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#F59E0B; color:#0D1B2A;">Coordinacion</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#1B4F72;">Multi-Agent RL</span>
          <span class="inline-block px-2 py-0.5 rounded text-xs" style="background:#243B55;">50 agentes</span>
        </div>
      </div>
    </div>
  </div>
</div>

---
layout: image-right
image: /img/b01-analytics.jpg
---

# Tipos de Problemas en ML

<div class="mt-4 space-y-6">
  <div v-click>
    <div class="flex items-center gap-2 mb-1">
      <div class="w-4 h-4 rounded-full bg-accent"></div>
      <span class="font-bold text-accent">Clasificacion</span>
    </div>
    <div class="text-sm ml-6">El modelo predice una categoria<br><span class="muted">Ejemplo: falla / normal en celda de bateria</span></div>
  </div>
  <div v-click>
    <div class="flex items-center gap-2 mb-1">
      <div class="w-4 h-4 rounded-full" style="background:#10B981"></div>
      <span class="font-bold" style="color:#10B981">Regresion</span>
    </div>
    <div class="text-sm ml-6">El modelo predice un valor numerico<br><span class="muted">Ejemplo: autonomia restante en km</span></div>
  </div>
  <div v-click>
    <div class="flex items-center gap-2 mb-1">
      <div class="w-4 h-4 rounded-full" style="background:#F59E0B"></div>
      <span class="font-bold" style="color:#F59E0B">Optimizacion</span>
    </div>
    <div class="text-sm ml-6">El modelo encuentra la mejor solucion<br><span class="muted">Ejemplo: ruta optima con menos energia</span></div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Variable Dependiente vs Variable Independiente

<div class="grid grid-cols-2 gap-6 mt-4">
  <div>
    <div v-click class="card-ev p-5 mb-4">
      <div class="flex items-center gap-3 mb-3">
        <div class="text-3xl font-bold text-accent">X</div>
        <div>
          <div class="font-bold text-lg">Variables Independientes</div>
          <div class="text-sm text-gray-300">Tambien llamadas: Features, Entrada, Predictores</div>
        </div>
      </div>
      <div class="text-sm mb-3">Son los <span class="text-accent font-bold">datos que le damos al modelo</span> para que aprenda. No dependen del modelo, existen por si solos.</div>
      <div class="text-xs space-y-1 muted">
        <div><mdi-antenna class="inline" /> Datos de sensores: temperatura, voltaje, corriente</div>
        <div><mdi-map-marker class="inline" /> Datos GPS: velocidad, altitud, distancia</div>
        <div><mdi-wrench class="inline" /> Datos operativos: ciclos de carga, horas de uso</div>
        <div><mdi-thermometer class="inline" /> Datos ambientales: clima, hora del dia, trafico</div>
      </div>
    </div>
  </div>
  <div>
    <div v-click class="card-ev p-5 mb-4" style="background:#00D4FF15; border: 1px solid #00D4FF;">
      <div class="flex items-center gap-3 mb-3">
        <div class="text-3xl font-bold text-accent">Y</div>
        <div>
          <div class="font-bold text-lg">Variable Dependiente</div>
          <div class="text-sm text-gray-300">Tambien llamada: Etiqueta, Target, Salida</div>
        </div>
      </div>
      <div class="text-sm mb-3">Es la <span class="text-accent font-bold">respuesta que queremos predecir</span>. Depende de las variables X — por eso se llama "dependiente".</div>
      <div class="text-xs space-y-1 muted">
        <div><mdi-tag class="inline" /> Clasificacion: falla/normal, suave/agresivo</div>
        <div><mdi-ruler class="inline" /> Regresion: autonomia_km, SoC%, kW demanda</div>
        <div><mdi-check-circle class="inline" /> Binaria: si/no, verdadero/falso</div>
        <div><mdi-target class="inline" /> Multiclase: tipo_A / tipo_B / tipo_C</div>
      </div>
    </div>
  </div>
</div>

<div v-click class="text-center mt-2">
  <div class="inline-flex items-center gap-4 card-ev px-6 py-3">
    <span class="text-accent font-bold text-lg">X</span>
    <span class="text-2xl">→</span>
    <span class="text-accent font-bold"><mdi-brain class="inline" /> Modelo ML</span>
    <span class="text-2xl">→</span>
    <span class="text-accent font-bold text-lg">Y</span>
  </div>
  <div class="text-sm mt-2 text-accent font-bold">"X entra al modelo — Y es lo que predice"</div>
</div>

---
layout: default
class: dark-slide
---

# Variable Dependiente vs Independiente — Ejemplos EV

<div class="slide-scroll">
<div class="text-sm mt-2 mb-3 text-accent font-bold">Casos reales de electromovilidad en Ciudad Juárez</div>

<div class="text-xs w-full" style="overflow-x:auto;">

| Problema — Juárez | Variables X (entrada) | Variable Y (salida) | Tipo |
|---|---|---|---|
| Autonomia en desierto de Chihuahua | temp exterior (40°C verano), AC, velocidad | km restantes | Regresion |
| Falla en celda — flota maquiladora | voltaje, corriente, temp batería, ciclos | falla / normal | Clasificacion |
| SoC en cruce fronterizo | voltaje OCV, corriente, historial del turno | SoC % al llegar | Regresion |
| Tipo de manejo en Blvd. Zaragoza | aceleración, frenado por topes, velocidad | suave / agresivo / normal | Clasificacion |
| Demanda de carga — Parque Industrial | hora, turno (1°/2°/3°), temp, día festivo | kW demandados a CFE | Regresion |

</div>
<div v-click class="mt-3 card-ev p-3">
  <div class="font-bold text-accent mb-2"><mdi-lightbulb class="inline" /> ¿Como saber cual es X y cual es Y?</div>
  <div class="grid grid-cols-2 gap-4 text-sm">
    <div>
      <span class="font-bold">Preguntate:</span> ¿Que quiero predecir?<br>
      <span class="muted">→ Eso es Y (variable dependiente)</span>
    </div>
    <div>
      <span class="font-bold">Preguntate:</span> ¿Con que datos cuento?<br>
      <span class="muted">→ Eso son las X (variables independientes)</span>
    </div>
  </div>
</div>
</div>

---
layout: default
class: dark-slide
---

# Tipos de Variables en un Dataset

<div class="grid grid-cols-3 gap-3 mt-3">
  <div v-click class="card-ev p-3">
    <div class="flex items-center gap-2 mb-1">
      <div class="w-2.5 h-2.5 rounded-full bg-accent flex-shrink-0"></div>
      <span class="text-accent font-bold text-sm">Numérica Continua</span>
    </div>
    <div class="text-xs muted mb-1">Cualquier valor, incluye decimales</div>
    <div class="text-xs space-y-0.5" style="color:#94a3b8;">
      <div><mdi-thermometer class="inline" /> Temperatura: 38.5°C</div>
      <div><mdi-lightning-bolt class="inline" /> Voltaje: 3.72V</div>
      <div><mdi-car-electric class="inline" /> Velocidad: 67.3 km/h</div>
      <div><mdi-battery class="inline" /> SoC: 78.4%</div>
    </div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="flex items-center gap-2 mb-1">
      <div class="w-2.5 h-2.5 rounded-full flex-shrink-0" style="background:#10B981;"></div>
      <span class="font-bold text-sm" style="color:#10B981;">Numérica Discreta</span>
    </div>
    <div class="text-xs muted mb-1">Enteros contables, sin decimales</div>
    <div class="text-xs space-y-0.5" style="color:#94a3b8;">
      <div><mdi-refresh class="inline" /> Ciclos de carga: 150, 500</div>
      <div><mdi-car-electric class="inline" /> Pasajeros: 1, 2, 4</div>
      <div><mdi-wrench class="inline" /> Fallas: 0, 1, 3</div>
      <div><mdi-chart-bar class="inline" /> Celdas: 96</div>
    </div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="flex items-center gap-2 mb-1">
      <div class="w-2.5 h-2.5 rounded-full flex-shrink-0" style="background:#F59E0B;"></div>
      <span class="font-bold text-sm" style="color:#F59E0B;">Categórica Nominal</span>
    </div>
    <div class="text-xs muted mb-1">Categorías sin orden</div>
    <div class="text-xs space-y-0.5" style="color:#94a3b8;">
      <div><mdi-car-electric class="inline" /> Marca: Tesla, BYD, VW</div>
      <div><mdi-road class="inline" /> Ruta: Zaragoza, Córdoba</div>
      <div><mdi-factory class="inline" /> Planta: Foxconn, Bosch</div>
      <div><mdi-lightning-bolt class="inline" /> Conector: CCS, CHAdeMO</div>
    </div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="flex items-center gap-2 mb-1">
      <div class="w-2.5 h-2.5 rounded-full flex-shrink-0" style="background:#8B5CF6;"></div>
      <span class="font-bold text-sm" style="color:#8B5CF6;">Categórica Ordinal</span>
    </div>
    <div class="text-xs muted mb-1">Categorías CON jerarquía</div>
    <div class="text-xs space-y-0.5" style="color:#94a3b8;">
      <div><mdi-battery class="inline" /> Carga: bajo→medio→alto</div>
      <div><mdi-alert class="inline" /> Riesgo: bajo→moderado→crítico</div>
      <div><mdi-car-electric class="inline" /> Manejo: suave→agresivo</div>
      <div><mdi-chart-bar class="inline" /> SoH: excelente→EOL</div>
    </div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="flex items-center gap-2 mb-1">
      <div class="w-2.5 h-2.5 rounded-full flex-shrink-0" style="background:#EF4444;"></div>
      <span class="font-bold text-sm" style="color:#EF4444;">Booleana</span>
    </div>
    <div class="text-xs muted mb-1">Solo 2 valores posibles</div>
    <div class="text-xs space-y-0.5" style="color:#94a3b8;">
      <div><mdi-check-circle class="inline" /> Falla: SI / NO</div>
      <div><mdi-power-plug class="inline" /> Cargando: true / false</div>
      <div><mdi-car-electric class="inline" /> AC encendido: 1 / 0</div>
      <div><mdi-factory class="inline" /> Día festivo: SI / NO</div>
    </div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="flex items-center gap-2 mb-1">
      <div class="w-2.5 h-2.5 rounded-full flex-shrink-0" style="background:#EC4899;"></div>
      <span class="font-bold text-sm" style="color:#EC4899;">Temporal</span>
    </div>
    <div class="text-xs muted mb-1">Fechas y horas</div>
    <div class="text-xs space-y-0.5" style="color:#94a3b8;">
      <div><mdi-calendar class="inline" /> Fecha: 2026-03-13</div>
      <div><mdi-clock-outline class="inline" /> Hora pico CFE: 14-20h</div>
      <div><mdi-timer class="inline" /> Duración: 45 min</div>
      <div><mdi-chart-bar class="inline" /> Turno: 1° / 2° / 3°</div>
    </div>
  </div>
</div>

---
layout: default
---

# Anatomia de un Dataset

<div class="slide-scroll">
<div class="grid grid-cols-3 gap-4 mt-6" style="color: #E8F4FD;">
  <div v-click class="rounded-lg p-5 text-center" style="background:#1B4F72;">
    <mdi-clipboard-list class="text-xl mb-2" />
    <div class="font-bold text-accent mb-3">Variables de Entrada<br>(Features)</div>
    <div class="text-sm space-y-1">
      <div>temperatura (°C)</div>
      <div>velocidad (km/h)</div>
      <div>carga bateria (%)</div>
      <div>km recorridos</div>
    </div>
  </div>
  <div class="flex flex-col items-center justify-center">
    <div class="text-3xl text-accent">→</div>
    <div v-click class="rounded-lg p-5 text-center w-full mt-4" style="background:#00D4FF; color:#0D1B2A;">
      <mdi-brain class="text-xl mb-2" />
      <div class="font-bold mb-2">Modelo ML</div>
      <div class="text-xs">Aprende patrones entre entrada y salida</div>
    </div>
    <div class="text-3xl text-accent mt-4">→</div>
  </div>
  <div v-click class="rounded-lg p-5 text-center" style="background:#1B4F72;">
    <mdi-tag class="text-xl mb-2" />
    <div class="font-bold text-accent mb-3">Variable de Salida<br>(Etiqueta)</div>
    <div class="text-sm space-y-1">
      <div>falla / normal</div>
      <div>autonomia_km</div>
      <div>ruta_optima</div>
    </div>
  </div>
</div>
</div>

<div v-click class="mt-6 text-xs text-center muted border border-gray-600 rounded p-2">
  En electromovilidad los datos provienen de sensores, BMS, GPS y CAN Bus
</div>

---
layout: default
class: dark-slide
---

# Overfitting, Validacion y Particion de Datos

<img src="/img/b01-data-chart.jpg" class="absolute right-4 top-16 w-1/3 rounded-lg opacity-20 -z-1" />

<div class="mt-2 mb-3">
  <div class="flex rounded overflow-hidden text-sm font-bold text-center">
    <div class="py-2" style="background:#1B4F72; flex:7;">ENTRENAMIENTO 70%</div>
    <div class="py-2" style="background:#00D4FF; color:#0D1B2A; flex:1.5;">VALIDACION 15%</div>
    <div class="py-2" style="background:#10B981; color:#0D1B2A; flex:1.5;">PRUEBA 15%</div>
  </div>
</div>

<div class="grid grid-cols-2 gap-6">
  <div v-click>
    <div class="font-bold mb-2" style="color:#ef4444;"><mdi-arrow-down class="inline" /> Underfitting</div>
    <div class="text-sm">El modelo es demasiado simple — no aprende los patrones reales</div>
    <div class="font-bold mt-4 mb-2" style="color:#F59E0B;"><mdi-arrow-up class="inline" /> Overfitting</div>
    <div class="text-sm">El modelo memoriza el entrenamiento — falla con datos nuevos</div>
  </div>
  <div v-click>
    <div class="font-bold mb-2 success">✓ Balance Optimo</div>
    <div class="text-sm">Generaliza bien en datos nuevos — esto es lo que buscamos</div>
    <div class="mt-4 border rounded p-3 text-sm" style="border-color:#F59E0B; color:#F59E0B;">
      En EV: un modelo sobreajustado podria predecir mal la autonomia en condiciones reales
    </div>
  </div>
</div>

---
layout: image-right
image: /img/b01-matrix.jpg
---

# Metricas de Evaluacion

<div class="slide-scroll">
<div class="grid grid-cols-2 gap-4 mt-4">
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-target class="inline" /> Accuracy</div>
    <div class="text-sm font-mono mb-1" style="color:#00D4FF;">(VP + VN) / Total</div>
    <div class="text-xs muted">Clasificacion balanceada</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="text-accent font-bold mb-2"><mdi-scale-balance class="inline" /> Precision / Recall</div>
    <div class="text-xs mb-1"><span class="font-bold">Precision:</span> de los que predije positivo, cuantos lo eran</div>
    <div class="text-xs"><span class="font-bold">Recall:</span> de los positivos reales, cuantos detecte</div>
  </div>
  <div v-click class="card-ev p-4">
    <div class="font-bold mb-2" style="color:#10B981;"><mdi-ruler class="inline" /> RMSE</div>
    <div class="text-sm mb-1">Raiz del error cuadratico medio</div>
    <div class="text-xs muted">Modelos de regresion (SoC, autonomia)</div>
  </div>
  <div v-click class="card-ev p-4" style="background:#243B55;">
    <div class="font-bold mb-2" style="color:#F59E0B;"><mdi-lightbulb class="inline" /> Guia de Seleccion</div>
    <div class="text-xs space-y-1">
      <div>Clasificacion → Accuracy + Precision</div>
      <div>Regresion → RMSE + MAE</div>
      <div>Deteccion → Precision + Recall</div>
    </div>
  </div>
</div>
</div>

---
layout: default
class: dark-slide
---

# Casos Reales de IA en Electromovilidad

<img src="/img/b01-neural-network.jpg" class="absolute right-0 top-0 h-full w-1/3 object-cover opacity-10 -z-1" />

<div class="grid grid-cols-3 gap-2 mt-3 text-sm">
  <div v-click class="card-ev p-3">
    <div class="font-bold text-accent mb-1">Tesla Autopilot</div>
    <div class="text-xs muted">CNN + 8 cámaras 360°. Reto en Juárez: polvo del desierto y sol directo en Libramiento Aeropuerto</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="font-bold text-accent mb-1">BYD — Batería</div>
    <div class="text-xs muted">LSTM 97% precisión en SoH. Baterías degradan más rápido con 40°C+ del verano juarense</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="font-bold text-accent mb-1">Google Maps EV</div>
    <div class="text-xs muted">Optimiza ruta según autonomía. Caso: Bermúdez → Puente Córdoba (35 km, 2 estaciones)</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="font-bold mb-1" style="color:#10B981;">VW / Continental Juárez</div>
    <div class="text-xs muted">Mantenimiento predictivo en ensamble. Planta en Juárez con sensores IoT en producción</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="font-bold mb-1" style="color:#F59E0B;">Taxis UTCJ</div>
    <div class="text-xs muted">Flota 10 taxis eléctricos con ML: carga según turnos de la universidad y tarifa CFE nocturna</div>
  </div>
  <div v-click class="card-ev p-3" style="border: 1px solid #00D4FF;">
    <div class="font-bold mb-1" style="color:#00D4FF;">Reto Juárez–El Paso</div>
    <div class="text-xs muted">Predecir SoC para esperar en Puente Zaragoza (1-3h) + tramo en El Paso (freeway)</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Entorno de Practica

<div class="grid grid-cols-2 gap-6 mt-4">
  <div v-click class="bg-white rounded-lg p-5 text-gray-800">
    <mdi-circle-outline class="text-2xl mb-2" />
    <div class="font-bold text-lg mb-3">Google Colab</div>
    <ul class="text-sm space-y-1">
      <li>Entorno Python en la nube</li>
      <li>GPUs gratuitas disponibles</li>
      <li>Librerias ML preinstaladas</li>
      <li>Colaboracion en tiempo real</li>
    </ul>
    <div class="mt-3 text-xs text-blue-600 font-mono">colab.research.google.com</div>
  </div>
  <div v-click class="bg-white rounded-lg p-5 text-gray-800">
    <mdi-robot class="text-2xl mb-2" />
    <div class="font-bold text-lg mb-3">Teachable Machines</div>
    <ul class="text-sm space-y-1">
      <li>ML visual sin codigo</li>
      <li>Clasificacion de imagenes</li>
      <li>Modelos exportables</li>
      <li>Ideal para primer acercamiento</li>
    </ul>
    <div class="mt-3 text-xs text-blue-600 font-mono">teachablemachine.withgoogle.com</div>
  </div>
</div>

<div v-click class="mt-4 text-center text-sm muted">Ambas plataformas son gratuitas y funcionan desde el navegador</div>

---
layout: image-right
image: /img/b01-analytics.jpg
class: dark-slide
---

# Practica — Bloque 01

<div class="badge-ev mb-4">PRACTICA</div>

## Entrenamiento No-Code y Analisis de Metricas

<div class="slide-scroll">
<div class="space-y-2 mt-3">
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-center text-sm flex items-center justify-center flex-shrink-0">1</div>
    <div class="text-sm">Acceder a Google Teachable Machines en el navegador</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-center text-sm flex items-center justify-center flex-shrink-0">2</div>
    <div class="text-sm">Cargar imagenes de autos electricos vs combustion (15-20 por clase)</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-center text-sm flex items-center justify-center flex-shrink-0">3</div>
    <div class="text-sm">Entrenar el modelo clasificador con los datos subidos</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-center text-sm flex items-center justify-center flex-shrink-0">4</div>
    <div class="text-sm">Evaluar Accuracy, Precision y Recall en el panel de metricas</div>
  </div>
  <div v-click class="flex items-start gap-3">
    <div class="w-7 h-7 rounded-full bg-accent text-primary font-bold text-center text-sm flex items-center justify-center flex-shrink-0">5</div>
    <div class="text-sm">Exportar modelo y discutir resultados en grupo</div>
  </div>
</div>
</div>

<div class="mt-5 flex gap-3">
  <div class="card-ev px-3 py-1 text-xs">Google Teachable Machines</div>
  <div class="card-ev px-3 py-1 text-xs">Google Colab (cuaderno de analisis)</div>
</div>

---
layout: default
---

# Recursos — Bloque 01

<div class="grid grid-cols-2 gap-5 mt-4">

  <div>
    <div class="font-bold text-accent mb-3"><mdi-television class="inline" /> YouTube — Canales recomendados</div>
    <div class="space-y-2">
      <a href="https://www.youtube.com/@DotCSV" target="_blank" class="card-ev p-3 flex items-start gap-3 no-underline block">
        <div class="text-red-400 text-lg flex-shrink-0">▶</div>
        <div>
          <div class="font-bold text-sm">DotCSV — Carlos Santana</div>
          <div class="text-xs muted">ML e IA explicado en español. Buscar: "¿Qué es el Machine Learning?"</div>
        </div>
      </a>
      <a href="https://www.youtube.com/@machinelearnear" target="_blank" class="card-ev p-3 flex items-start gap-3 no-underline block">
        <div class="text-red-400 text-lg flex-shrink-0">▶</div>
        <div>
          <div class="font-bold text-sm">Machinelearnear</div>
          <div class="text-xs muted">Tutoriales paso a paso de modelos ML en español. Buscar: "Clasificacion con Python"</div>
        </div>
      </a>
      <a href="https://www.youtube.com/@EDteam" target="_blank" class="card-ev p-3 flex items-start gap-3 no-underline block">
        <div class="text-red-400 text-lg flex-shrink-0">▶</div>
        <div>
          <div class="font-bold text-sm">EDTeam</div>
          <div class="text-xs muted">Introduccion a IA y ML en español. Buscar: "Machine Learning desde cero"</div>
        </div>
      </a>
    </div>
  </div>
  <div>
    <div class="font-bold text-accent mb-3"><mdi-link class="inline" /> Links de Practica y Estudio</div>
    <div class="space-y-2">
      <a href="https://teachablemachine.withgoogle.com" target="_blank" class="card-ev p-3 flex items-center gap-3 no-underline block">
        <mdi-robot class="text-xl" />
        <div>
          <div class="font-bold text-sm">Teachable Machine</div>
          <div class="text-xs muted">ML sin codigo — clasifica imagenes en minutos</div>
        </div>
      </a>
      <a href="https://colab.research.google.com" target="_blank" class="card-ev p-3 flex items-center gap-3 no-underline block">
        <mdi-circle-outline class="text-xl" />
        <div>
          <div class="font-bold text-sm">Google Colab</div>
          <div class="text-xs muted">Python en la nube con GPU gratuita</div>
        </div>
      </a>
      <a href="https://developers.google.com/machine-learning/crash-course?hl=es" target="_blank" class="card-ev p-3 flex items-center gap-3 no-underline block">
        <mdi-book class="text-xl" />
        <div>
          <div class="font-bold text-sm">Google ML Crash Course</div>
          <div class="text-xs muted">Curso gratuito de ML de Google — disponible en español</div>
        </div>
      </a>
      <a href="https://www.kaggle.com/datasets/urvishahir/electric-vehicle-specifications-dataset-2025" target="_blank" class="card-ev p-3 flex items-center gap-3 no-underline block">
        <mdi-chart-bar class="text-xl" />
        <div>
          <div class="font-bold text-sm">Kaggle — EV Specs Dataset 2025</div>
          <div class="text-xs muted">Dataset de especificaciones de EVs para practicar</div>
        </div>
      </a>
      <a href="https://www.aprendemachinelearning.com" target="_blank" class="card-ev p-3 flex items-center gap-3 no-underline block">
        <mdi-web class="text-xl" />
        <div>
          <div class="font-bold text-sm">AprendeMachineLearning.com</div>
          <div class="text-xs muted">Blog y ejercicios de ML en español con Python</div>
        </div>
      </a>
    </div>
  </div>

</div>

---
layout: center
class: dark-slide
---

# Puntos Clave — Bloque 01

<img src="/img/b01-ev-street.jpg" class="absolute inset-0 w-full h-full object-cover opacity-10 -z-1" />

<div class="slide-scroll">
<div class="space-y-3 mt-4 text-left max-w-xl mx-auto">
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Existen 3 paradigmas de ML: supervisado, no supervisado y refuerzo</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Los problemas en electromovilidad son clasificacion, regresion y optimizacion</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Un dataset tiene features (X, entrada) y etiquetas (Y, salida)</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>El overfitting ocurre cuando el modelo memoriza en lugar de generalizar</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Las metricas nos dicen que tan bien generaliza nuestro modelo</span>
  </div>
</div>
</div>

<div class="mt-8 text-sm muted">
  > Siguiente: <span class="text-accent font-bold">Bloque 02 — Percepcion del Entorno y Computer Vision</span>
</div>
