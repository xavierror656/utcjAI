---
theme: penguin
title: "Bloque 02 — Percepción del Entorno y Computer Vision"
titleTemplate: "%s | IA Electromovilidad"
info: |
  ## Bloque 02
  IA Aplicada a la Electromovilidad
  Ciudad Juarez
transition: slide-left
class: dark-slide
mdc: true
zoom: 0.85
fonts:
  sans: 'Segoe UI'
---

# Bloque 02
## Percepción del Entorno y Computer Vision

Cómo los vehículos eléctricos ven las calles de Ciudad Juárez

<div class="abs-br m-6 text-xs text-gray-400">2 horas | Teoría + Práctica · UTCJ</div>

<img src="/img/b02-camera-car.jpg" class="absolute inset-0 w-full h-full object-cover opacity-20 -z-1" />

---
layout: default
---

# Contenido del Bloque

<img src="/img/b02-sensors.jpg" class="absolute right-0 top-0 h-full w-1/3 object-cover opacity-10 -z-1" />

<div class="grid grid-cols-3 gap-2 mt-4">
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1"><mdi-camera class="inline" /> Sensores</div>
    <div class="text-xs muted">Cámara RGB, LiDAR, Radar, Ultrasonido</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1"><mdi-shuffle-variant class="inline" /> Sensor Fusion</div>
    <div class="text-xs muted">Fusión temprana, tardía y Kalman Filter</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1"><mdi-brain class="inline" /> CNN Conceptual</div>
    <div class="text-xs muted">Convolución, pooling, feature maps</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1"><mdi-refresh class="inline" /> Transfer Learning</div>
    <div class="text-xs muted">ResNet, MobileNet, EfficientNet pre-entrenados</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1"><mdi-target class="inline" /> YOLO v8/v11</div>
    <div class="text-xs muted">Detección de objetos en tiempo real</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1"><mdi-ruler class="inline" /> Segmentación</div>
    <div class="text-xs muted">Semántica e instancia para calles de Juárez</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1"><mdi-chart-bar class="inline" /> Métricas CV</div>
    <div class="text-xs muted">IoU, mAP, Precisión, Recall, Latencia</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1"><mdi-database class="inline" /> Datasets EV</div>
    <div class="text-xs muted">KITTI, nuScenes, Waymo y el problema local</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="badge-ev mb-1">PRÁCTICA</div>
    <div class="text-xs">Roboflow + YOLO en calles de Juárez</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# ¿Qué ve un Vehículo Autónomo?

<img src="/img/b02-selfdriving.jpg" class="absolute right-0 top-0 h-full w-2/5 object-cover opacity-15 -z-1" />

<div class="grid grid-cols-2 gap-4 mt-3">
  <div>
    <div v-click class="mb-3 p-3 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2"><mdi-eye class="inline" /> Visión Humana</div>
      <div class="text-xs space-y-1">
        <div>• Campo de visión: ~180° frontal, sin trasero</div>
        <div>• Profundidad: estimada por dos ojos (estereoscopia)</div>
        <div>• Funciona: solo con luz, se fatiga con el tiempo</div>
        <div>• Tiempo de reacción: <span class="warning">200–400 ms</span></div>
      </div>
    </div>
    <div v-click class="p-3 rounded" style="background:#1B4F72;">
      <div class="font-bold mb-2" style="color:#10B981;"><mdi-robot class="inline" /> Visión Artificial</div>
      <div class="text-xs space-y-1">
        <div>• Cobertura: 360° continuo (multi-cámara + LiDAR)</div>
        <div>• Profundidad: medida exacta en metros con ±2 cm</div>
        <div>• Funciona: día y noche, sin fatiga, 24/7</div>
        <div>• Tiempo de reacción: <span class="success">&lt; 10 ms</span></div>
      </div>
    </div>
  </div>
  <div class="space-y-2">
    <div v-click class="p-3 rounded text-xs" style="background:#2a1810; border-left: 3px solid #F59E0B;">
      <div class="warning font-bold mb-1"><mdi-alert class="inline" /> Limitación clave</div>
      <div class="muted">La visión artificial falla donde el humano triunfa: contexto social, intuición, situaciones completamente inesperadas. Un humano reconoce a un niño corriendo aunque vea solo la sombra.</div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="background:#0a2a1a; border-left: 3px solid #10B981;">
      <div class="success font-bold mb-1">✓ Ventaja clave</div>
      <div class="muted">La visión artificial no se distrae, no se cansa y procesa múltiples streams de video simultáneamente a 60fps con latencia &lt; 10ms.</div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="border: 1px solid #00D4FF;">
      <div class="text-accent font-bold mb-1"><mdi-city class="inline" /> Caso Juárez</div>
      <div class="muted">En el turno de salida de maquiladoras (6am, 2pm, 10pm): miles de peatones en oscuridad. La visión artificial + LiDAR infrarrojo supera al humano en estas condiciones críticas.</div>
    </div>
  </div>
</div>

---
layout: image-right
image: /img/b02-camera-car.jpg
---

# Cámara RGB — Los Ojos Principales

<div class="space-y-2 mt-2">
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">¿Cómo funciona?</div>
    <div class="text-xs muted">Sensor CMOS captura fotones → matriz de píxeles RGB → tensor de entrada [H×W×3] para la CNN. A 60fps genera 60 capturas por segundo.</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">Especificaciones típicas en EV</div>
    <div class="grid grid-cols-2 gap-1 text-xs">
      <div class="muted">Resolución: <span class="accent">1080p – 4K</span></div>
      <div class="muted">FPS: <span class="accent">30 – 120 fps</span></div>
      <div class="muted">FOV: <span class="accent">60° – 190°</span></div>
      <div class="muted">Latencia: <span class="accent">&lt; 5 ms</span></div>
    </div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="font-bold mb-1" style="color:#10B981;">✓ Fortalezas</div>
    <div class="text-xs muted">Color, textura, semáforos, señales de tráfico, lectura de matrículas, reconocimiento de carriles y líneas del pavimento</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="font-bold mb-1" style="color:#ef4444;">✗ Retos en Juárez</div>
    <div class="text-xs muted">Sin info de profundidad. Sobreexposición con sol directo en Libramiento Aeropuerto (verano 40°C). Polvo del desierto opaca la lente en horas.</div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# LiDAR — Mapa 3D del Entorno

<img src="/img/b02-lidar.jpg" class="absolute right-0 top-0 h-full w-1/3 object-cover opacity-15 -z-1" />

<div class="grid grid-cols-2 gap-4 mt-3">
  <div class="space-y-2">
    <div v-click class="card-ev p-3">
      <div class="text-accent font-bold mb-2">¿Cómo funciona LiDAR?</div>
      <div class="text-xs muted space-y-1">
        <div>1. Emite pulsos de luz láser (905 nm / 1550 nm)</div>
        <div>2. Mide el tiempo de retorno (Time of Flight)</div>
        <div>3. Calcula distancia: <span class="accent font-mono">d = c × t / 2</span></div>
        <div>4. Genera nube de puntos 3D a 10–20 Hz</div>
      </div>
    </div>
    <div v-click class="card-ev p-3">
      <div class="font-bold mb-2" style="color:#10B981;">Especificaciones</div>
      <div class="text-xs">
        <table class="w-full">
          <tr><td class="muted">Alcance</td><td class="accent text-right">50 – 300 m</td></tr>
          <tr><td class="muted">Canales</td><td class="accent text-right">16 – 128 líneas</td></tr>
          <tr><td class="muted">Precisión</td><td class="accent text-right">±2 cm</td></tr>
          <tr><td class="muted">Puntos/seg</td><td class="accent text-right">hasta 4M pts/s</td></tr>
        </table>
      </div>
    </div>
  </div>
  <div class="space-y-2">
    <div v-click class="p-3 rounded text-xs" style="background:#0a2a1a; border-left: 3px solid #10B981;">
      <div class="success font-bold mb-1">Ventajas en EV</div>
      <div class="muted">Mapa 3D exacto, funciona de noche, detecta peatones a 150m, genera SLAM (mapeo simultáneo) para navegación autónoma sin GPS</div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="background:#2a1810; border-left: 3px solid #F59E0B;">
      <div class="warning font-bold mb-1">Limitaciones en Juárez</div>
      <div class="muted">• Costo: $4,000 – $80,000 USD por unidad</div>
      <div class="muted">• Afectado por niebla y lluvia intensa</div>
      <div style="color:#ef4444;">• Vibraciones en calles sin pavimentar desalinean la calibración</div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="border: 1px solid #00D4FF;">
      <div class="text-accent font-bold mb-1">Alternativa económica</div>
      <div class="muted">LiDAR sólido de bajo costo (~$100–500): Livox Mid-360, Ouster OS0 — viable para flotas de transporte en Juárez</div>
    </div>
  </div>
</div>

---
layout: default
---

# Radar y Ultrasonido — Los Sensores Robustos

<div class="grid grid-cols-2 gap-4 mt-3">
  <div>
    <div class="text-accent font-bold mb-2 text-center text-sm"><mdi-antenna class="inline" /> Radar (77 GHz)</div>
    <div v-click class="space-y-2">
      <div class="card-ev p-3 text-xs">
        <div class="font-bold mb-1">Principio</div>
        <div class="muted">Ondas de radio + efecto Doppler → velocidad y distancia de objetos en movimiento con alcance de 250m</div>
      </div>
      <div class="card-ev p-3 text-xs">
        <div class="font-bold mb-1 success">✓ Fortalezas</div>
        <div class="muted">Funciona con lluvia, polvo, niebla y noche. Detecta velocidad relativa exacta. Precio moderado ($500–2000 USD)</div>
      </div>
      <div class="card-ev p-3 text-xs">
        <div class="font-bold mb-1" style="color:#ef4444;">✗ Debilidades</div>
        <div class="muted">Baja resolución lateral. <span style="color:#F59E0B;">No detecta topes (lomos de burro)</span> — crítico en colonias de Juárez</div>
      </div>
      <div class="card-ev p-3 text-xs">
        <div class="font-bold mb-1 accent">Uso en EV</div>
        <div class="muted">ACC (Cruise Control Adaptativo), detección de colisión trasera, alerta de punto ciego en cambio de carril</div>
      </div>
    </div>
  </div>
  <div>
    <div class="font-bold mb-2 text-center text-sm" style="color:#10B981;"><mdi-volume-high class="inline" /> Ultrasonido</div>
    <div v-click class="space-y-2">
      <div class="card-ev p-3 text-xs">
        <div class="font-bold mb-1">Principio</div>
        <div class="muted">Pulsos ultrasónicos (40kHz) miden distancia por tiempo de eco — igual que el murciélago en la naturaleza</div>
      </div>
      <div class="card-ev p-3 text-xs">
        <div class="font-bold mb-1 success">✓ Fortalezas</div>
        <div class="muted">Muy barato ($5–20 USD por sensor), preciso en rango corto 0.2–5m, omnidireccional, sin interferencia con otros sensores</div>
      </div>
      <div class="card-ev p-3 text-xs">
        <div class="font-bold mb-1" style="color:#ef4444;">✗ Debilidades</div>
        <div class="muted">Solo 5m de alcance, lento (10Hz), afectado por viento fuerte y superficies muy blandas (polvo suelto)</div>
      </div>
      <div class="card-ev p-3 text-xs">
        <div class="font-bold mb-1 accent">Uso en EV</div>
        <div class="muted">Parking assist, detección de obstáculos en maniobras lentas, protección de periferia en garitas fronterizas</div>
      </div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Sensor Fusion — Ninguno es Suficiente Solo

<div class="mt-2">
  <div v-click class="mb-3 p-2 rounded text-sm text-center font-bold" style="background:#1B4F72; color:#00D4FF;">
    La fusión de sensores es la arquitectura central de todo vehículo autónomo moderno
  </div>
  <div class="grid grid-cols-4 gap-2 mb-3">
    <div v-click class="text-center p-2 rounded text-xs" style="background:#1B4F72;">
      <mdi-camera class="text-2xl" />
      <div class="text-accent font-bold">Cámara</div>
      <div class="muted">Color + textura</div>
      <div class="muted">Sin profundidad</div>
    </div>
    <div v-click class="text-center p-2 rounded text-xs" style="background:#1B4F72;">
      <mdi-circle class="text-2xl" />
      <div class="font-bold" style="color:#10B981;">LiDAR</div>
      <div class="muted">Profundidad 3D</div>
      <div class="muted">Sin color</div>
    </div>
    <div v-click class="text-center p-2 rounded text-xs" style="background:#1B4F72;">
      <mdi-antenna class="text-2xl" />
      <div class="font-bold" style="color:#F59E0B;">Radar</div>
      <div class="muted">Velocidad + lluvia</div>
      <div class="muted">Sin forma</div>
    </div>
    <div v-click class="text-center p-2 rounded text-xs" style="background:#1B4F72;">
      <mdi-volume-high class="text-2xl" />
      <div class="font-bold" style="color:#A78BFA;">Ultrasonido</div>
      <div class="muted">Obstáculos cerca</div>
      <div class="muted">Solo 5m</div>
    </div>
  </div>
  <div v-click class="grid grid-cols-3 gap-2 text-xs">
    <div class="p-3 rounded" style="background:#0a2a1a; border: 1px solid #10B981;">
      <div class="success font-bold mb-1">Fusión Temprana (Early)</div>
      <div class="muted">Une datos crudos antes del modelo. Alta precisión pero muy costosa en cómputo y ancho de banda</div>
    </div>
    <div class="p-3 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-1">Fusión Media (Middle)</div>
      <div class="muted">Une representaciones intermedias (feature maps). Balance entre rendimiento y costo computacional</div>
    </div>
    <div class="p-3 rounded" style="background:#2a1810; border: 1px solid #F59E0B;">
      <div class="warning font-bold mb-1">Fusión Tardía (Late)</div>
      <div class="muted">Cada sensor decide independiente → votación por mayoría. Más simple y tolerante a fallas</div>
    </div>
  </div>
  <div v-click class="mt-2 p-2 rounded text-xs text-center" style="background:#1B4F72;">
    <span class="text-accent font-bold">Tesla:</span><span class="muted"> usa fusión tardía con 8 cámaras + radar </span>
    <span class="text-accent font-bold">| Waymo:</span><span class="muted"> fusión media con LiDAR + cámara + radar integrados</span>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Retos de Sensores en Ciudad Juárez

<div class="grid grid-cols-3 gap-3 mt-3">
  <div v-click class="card-ev p-3 text-center">
    <mdi-camera class="text-2xl mb-1" />
    <div class="text-accent font-bold mb-1">Cámara RGB</div>
    <div class="text-xs muted mb-1">Alcance: hasta 100m</div>
    <div class="text-xs mb-1 success">Color, texturas, señales, semáforos</div>
    <div class="text-xs mt-2" style="color:#ef4444;"><mdi-alert class="inline" /> Sol directo en Blvd. Zaragoza (verano 40°C) satura el sensor. Tormentas de polvo cubren la lente en minutos</div>
    <div class="badge-ev mt-2">VISIÓN</div>
  </div>
  <div v-click class="card-ev p-3 text-center" style="background:#1a3a2a;">
    <mdi-circle class="text-2xl mb-1" />
    <div class="font-bold mb-1" style="color:#10B981;">LiDAR</div>
    <div class="text-xs muted mb-1">Alcance: hasta 200m</div>
    <div class="text-xs mb-1 success">Mapa 3D preciso, funciona de noche</div>
    <div class="text-xs mt-2" style="color:#ef4444;"><mdi-alert class="inline" /> Vibraciones en calles sin pavimentar (colonias populares) desalinean la calibración. Precio prohibitivo para flotas locales</div>
    <div class="inline-block mt-2 px-2 py-0.5 rounded text-xs font-bold" style="background:#10B981;color:#0D1B2A;">3D PUNTO</div>
  </div>
  <div v-click class="card-ev p-3 text-center" style="background:#2a2010;">
    <mdi-antenna class="text-2xl mb-1" />
    <div class="font-bold mb-1" style="color:#F59E0B;">Radar</div>
    <div class="text-xs muted mb-1">Alcance: hasta 300m</div>
    <div class="text-xs mb-1 warning">Velocidad de objetos, funciona con polvo</div>
    <div class="text-xs mt-2" style="color:#ef4444;"><mdi-alert class="inline" /> No detecta topes (lomos de burro) — críticos en colonias. Requiere fusión con cámara para identificarlos</div>
    <div class="inline-block mt-2 px-2 py-0.5 rounded text-xs font-bold" style="background:#F59E0B;color:#0D1B2A;">VELOCIDAD</div>
  </div>
</div>

<div v-click class="mt-3 text-center text-sm text-accent font-bold border border-accent rounded p-2">
  Sensor Fusion — la combinación de los 3 es indispensable para el entorno de Ciudad Juárez
</div>

---
layout: default
---

# Red Neuronal Convolucional (CNN) — Conceptual

<div class="flex items-stretch gap-2 mt-6 text-xs text-center">
  <div v-click class="flex-1 border rounded p-3" style="border-color:#1B4F72;">
    <mdi-image class="text-2xl mb-1" />
    <div class="font-bold text-accent">IMAGEN</div>
    <div class="muted mt-1">Píxeles de entrada (cámara, video 60fps)</div>
  </div>
  <div class="flex items-center text-accent font-bold">→</div>
  <div v-click class="flex-1 border rounded p-3" style="border-color:#1B4F72;">
    <mdi-checkbox-blank class="text-2xl mb-1" />
    <div class="font-bold text-accent">CONV</div>
    <div class="muted mt-1">Detecta bordes, formas y texturas con filtros aprendidos</div>
  </div>
  <div class="flex items-center text-accent font-bold">→</div>
  <div v-click class="flex-1 border rounded p-3" style="border-color:#1B4F72;">
    <mdi-arrow-down class="text-2xl mb-1" />
    <div class="font-bold text-accent">POOLING</div>
    <div class="muted mt-1">Reduce dimensión, conserva lo más relevante</div>
  </div>
  <div class="flex items-center text-accent font-bold">→</div>
  <div v-click class="flex-1 border rounded p-3" style="border-color:#1B4F72;">
    <mdi-arrow-right class="text-2xl mb-1" />
    <div class="font-bold text-accent">FLATTEN</div>
    <div class="muted mt-1">Convierte mapa 2D en vector 1D</div>
  </div>
  <div class="flex items-center text-accent font-bold">→</div>
  <div v-click class="flex-1 border rounded p-3" style="border-color:#00D4FF;">
    <mdi-tag class="text-2xl mb-1" />
    <div class="font-bold text-accent">CLASIF.</div>
    <div class="muted mt-1">Probabilidades por clase de objeto</div>
  </div>
</div>

<div v-click class="mt-4 grid grid-cols-3 gap-3 text-xs">
  <div class="p-3 rounded" style="background:#1B4F72;">
    <div class="text-accent font-bold mb-1">Capa 1 — Bordes</div>
    <div class="muted">Los primeros filtros detectan líneas horizontales, verticales y diagonales. Como detectores de Canny, pero aprendidos automáticamente del dataset</div>
  </div>
  <div class="p-3 rounded" style="background:#1B4F72;">
    <div class="text-accent font-bold mb-1">Capa Media — Formas</div>
    <div class="muted">Combina bordes para detectar círculos, esquinas, curvas. Ya empieza a reconocer ruedas, ventanas, señales de tráfico</div>
  </div>
  <div class="p-3 rounded" style="background:#1B4F72;">
    <div class="text-accent font-bold mb-1">Capa Final — Objetos</div>
    <div class="muted">Combina formas para reconocer: "peatón", "auto", "letrero ALTO", "tope". Alta abstracción semántica</div>
  </div>
</div>

<div v-click class="mt-3 border rounded p-2 text-xs text-center" style="border-color:#00D4FF; color:#00D4FF;">
  No necesitas programar CNNs — los modelos pre-entrenados ya tienen estos pesos aprendidos con millones de imágenes
</div>

---
layout: default
class: dark-slide
---

# CNN — ¿Qué "ve" Cada Capa?

<img src="/img/b02-robot-vision.jpg" class="absolute right-0 top-0 h-full w-1/3 object-cover opacity-10 -z-1" />

<div class="mt-2">
  <div class="text-xs muted mb-3">Visualización conceptual de activaciones por capa en una CNN aplicada a cámara de EV:</div>
  <div class="grid grid-cols-5 gap-2 text-center text-xs mb-3">
    <div v-click>
      <div class="p-2 rounded mb-1" style="background:#1B4F72;">
        <div class="font-mono text-xl leading-none py-1" style="color:#00D4FF; letter-spacing:-1px;">▓░▓░<br/>░▓░▓<br/>▓░▓░<br/>░▓░▓</div>
      </div>
      <div class="text-accent font-bold">Input</div>
      <div class="muted">Imagen original 640×640 px RGB</div>
    </div>
    <div v-click>
      <div class="p-2 rounded mb-1" style="background:#1B4F72;">
        <div class="font-mono text-xl leading-none py-1" style="color:#F59E0B;">▔▔▔▔<br/>    <br/>▁▁▁▁<br/>    </div>
      </div>
      <div class="text-accent font-bold">Conv1</div>
      <div class="muted">Bordes horizontales y verticales detectados</div>
    </div>
    <div v-click>
      <div class="p-2 rounded mb-1" style="background:#1B4F72;">
        <div class="font-mono text-xl leading-none py-1" style="color:#10B981;">◢◣ <br/>◤◥ <br/>◢◣ <br/>◤◥ </div>
      </div>
      <div class="text-accent font-bold">Conv3</div>
      <div class="muted">Esquinas, curvas y ángulos</div>
    </div>
    <div v-click>
      <div class="p-2 rounded mb-1" style="background:#1B4F72;">
        <div class="font-mono text-xl leading-none py-1" style="color:#A78BFA;">○ ○ <br/>  ○ <br/>○   <br/>○ ○ </div>
      </div>
      <div class="text-accent font-bold">Conv6</div>
      <div class="muted">Formas complejas y patrones</div>
    </div>
    <div v-click>
      <div class="p-2 rounded mb-1" style="background:#0a2a1a; border: 1px solid #10B981;">
        <mdi-walk class="text-3xl py-1" />
        <div class="text-xs" style="color:#10B981;">97.3%</div>
      </div>
      <div class="text-accent font-bold">Output</div>
      <div class="muted">"Peatón detectado" con confianza</div>
    </div>
  </div>
  <div v-click class="grid grid-cols-2 gap-3 text-xs">
    <div class="p-3 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-1">¿Cuántos filtros existen?</div>
      <div class="muted">Una CNN como ResNet-50 tiene 32–512 filtros por capa. Cada filtro aprende a detectar un patrón diferente. Con 50 capas = 25 millones de parámetros entrenables</div>
    </div>
    <div class="p-3 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-1">¿Por qué funciona?</div>
      <div class="muted">Los filtros se ajustan automáticamente durante el entrenamiento (backpropagation + gradiente descendente) para minimizar el error de clasificación</div>
    </div>
  </div>
</div>

---
layout: default
---

# Transfer Learning — Reutilizar el Conocimiento

<div class="grid grid-cols-2 gap-4 mt-3">
  <div>
    <div v-click class="mb-3 p-3 rounded text-xs" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2">¿Qué es Transfer Learning?</div>
      <div class="muted">Una CNN entrenada en ImageNet (14 millones de imágenes, 1000 clases) ya "sabe" detectar bordes, texturas y formas. Reutilizamos esos pesos y solo re-entrenamos las últimas capas para nuestra tarea específica en Juárez.</div>
    </div>
    <div v-click class="mb-3 p-3 rounded text-xs" style="background:#0a2a1a; border-left: 3px solid #10B981;">
      <div class="success font-bold mb-1">Beneficio práctico</div>
      <div class="muted">En lugar de 1,000,000 de imágenes, necesitas <span class="success font-bold">200–2,000 imágenes</span> de tu caso específico. En lugar de semanas de GPU, entrenas en <span class="success font-bold">horas en Colab gratuito</span>.</div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="background:#2a1810; border-left: 3px solid #F59E0B;">
      <div class="warning font-bold mb-1">Aplicación en Juárez</div>
      <div class="muted">Tomar 500 fotos de topes y señales ALTO → freeze capas 1–40 → fine-tune últimas 3 capas de MobileNet → detector local en 2 horas en Colab T4 gratuito</div>
    </div>
  </div>
  <div>
    <div v-click class="p-3 rounded text-xs" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2">Arquitecturas populares</div>
      <table class="w-full text-xs">
        <thead>
          <tr style="color:#00D4FF;" class="border-b border-gray-600">
            <th class="text-left pb-1">Modelo</th>
            <th class="text-center">Params</th>
            <th class="text-center">Top-1</th>
            <th class="text-center">Uso ideal</th>
          </tr>
        </thead>
        <tbody class="text-gray-300">
          <tr class="border-b border-gray-700">
            <td class="py-1 font-bold">MobileNet v3</td>
            <td class="text-center">5.4M</td>
            <td class="text-center success">75.2%</td>
            <td class="text-center muted">Edge / chip</td>
          </tr>
          <tr class="border-b border-gray-700">
            <td class="py-1 font-bold">ResNet-50</td>
            <td class="text-center">25.6M</td>
            <td class="text-center success">76.1%</td>
            <td class="text-center muted">GPU servidor</td>
          </tr>
          <tr class="border-b border-gray-700">
            <td class="py-1 font-bold">EfficientNet-B4</td>
            <td class="text-center">19.3M</td>
            <td class="text-center" style="color:#10B981;">83.0%</td>
            <td class="text-center muted">Balance ideal</td>
          </tr>
          <tr>
            <td class="py-1 font-bold" style="color:#00D4FF;">YOLO v8-nano</td>
            <td class="text-center">3.2M</td>
            <td class="text-center warning">—</td>
            <td class="text-center" style="color:#00D4FF;">Tiempo real</td>
          </tr>
        </tbody>
      </table>
    </div>
    <div v-click class="mt-2 p-2 rounded text-xs" style="border: 1px solid #00D4FF;">
      <div class="text-accent font-bold mb-1">Flujo práctico</div>
      <div class="muted">ImageNet weights → Freeze capas 1–N → Fine-tune capas finales → Dataset Juárez → Exportar ONNX → Deploy en Jetson / Raspberry</div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Detección de Objetos — Conceptos Base

<img src="/img/b02-detection.jpg" class="absolute right-0 top-0 h-full w-2/5 object-cover opacity-15 -z-1" />

<div class="grid grid-cols-2 gap-4 mt-3">
  <div class="space-y-2">
    <div v-click class="card-ev p-3 text-xs">
      <div class="text-accent font-bold mb-1">¿Qué hace un detector de objetos?</div>
      <div class="muted">Para cada objeto en la imagen: (1) dibuja un bounding box [x, y, w, h], (2) asigna una clase ("peatón", "tope", "ALTO"), (3) calcula confianza de 0–1</div>
    </div>
    <div v-click class="card-ev p-3 text-xs">
      <div class="text-accent font-bold mb-1">Dos familias principales</div>
      <div class="grid grid-cols-2 gap-2">
        <div>
          <div class="font-bold warning mb-1">Two-stage</div>
          <div class="muted">1. Propone regiones</div>
          <div class="muted">2. Clasifica cada región</div>
          <div class="muted">Ej: Faster R-CNN</div>
          <div class="muted">Alta precisión, lento</div>
        </div>
        <div>
          <div class="font-bold" style="color:#10B981;">One-stage</div>
          <div class="muted">Detecta todo en un solo forward pass</div>
          <div class="muted">Ej: YOLO, SSD</div>
          <div class="muted">Tiempo real, &lt;30ms</div>
        </div>
      </div>
    </div>
    <div v-click class="card-ev p-3 text-xs">
      <div class="text-accent font-bold mb-1">Clases críticas en Juárez</div>
      <div class="grid grid-cols-2 gap-1 muted">
        <div><mdi-walk class="inline" /> Peatones (turno IMMEX)</div>
        <div><mdi-car-electric class="inline" /> Vehículos y trailers</div>
        <div><mdi-stop-circle class="inline" /> Letrero "ALTO"</div>
        <div><mdi-mountain class="inline" /> Tope / lomo de burro</div>
        <div><mdi-traffic-light class="inline" /> Semáforo (apagado)</div>
        <div><mdi-passport class="inline" /> Garita fronteriza</div>
      </div>
    </div>
  </div>
  <div class="space-y-2">
    <div v-click class="p-3 rounded text-xs" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2">Bounding Box explicado</div>
      <div class="font-mono text-center p-2 rounded mb-2" style="background:#0D1B2A;">
        <div class="border-2 border-accent inline-block p-2 text-xs" style="color:#00D4FF;">[x_centro, y_centro, ancho, alto]<br/>[0.45, 0.62, 0.18, 0.35]</div>
      </div>
      <div class="muted">Coordenadas normalizadas 0–1 relativas al tamaño de imagen</div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-1">Non-Maximum Suppression (NMS)</div>
      <div class="muted">El modelo genera múltiples cajas para el mismo objeto. NMS elimina las redundantes, conservando solo la de mayor confianza donde IoU supera el umbral definido</div>
    </div>
    <div v-click class="p-2 rounded text-xs" style="background:#0a2a1a; border: 1px solid #10B981;">
      <div class="success font-bold mb-1">Escenario práctico en Juárez</div>
      <div class="muted">Un taxi eléctrico a 50km/h tiene 1.08 segundos para frenar antes de un tope a 15m. El modelo debe detectar y alertar en &lt; 200ms total de pipeline.</div>
    </div>
  </div>
</div>

---
layout: image-right
image: /img/b02-selfdriving.jpg
---

# YOLO — You Only Look Once

<div class="space-y-2 mt-2">
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">¿Por qué YOLO es especial?</div>
    <div class="text-xs muted">Divide la imagen en cuadrícula S×S. Cada celda predice N bounding boxes + confianza + clases en un solo forward pass. Resultado: 6–50ms por imagen.</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="text-accent font-bold mb-1">Evolución de versiones</div>
    <div class="grid grid-cols-2 gap-1 text-xs muted">
      <div>YOLOv1 (2015): concepto original</div>
      <div>YOLOv3 (2018): detección multi-escala</div>
      <div>YOLOv5 (2020): PyTorch nativo</div>
      <div>YOLOv8 (2023): Ultralytics API</div>
      <div class="col-span-2 text-accent font-bold">YOLOv11 (2024): última versión</div>
    </div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="font-bold mb-1" style="color:#10B981;">Velocidades en tiempo real (GPU)</div>
    <div class="text-xs muted">YOLOv8-nano: <span class="success">~6ms</span> por imagen. YOLOv8-large: <span class="warning">~52ms</span>. Ambos suficientes para 30fps en dashcam de flota maquiladora</div>
  </div>
  <div v-click class="card-ev p-3">
    <div class="font-bold mb-1 warning">Elegir modelo según dispositivo</div>
    <div class="text-xs muted">nano/small → Jetson Nano, RPi 5<br/>medium → PC con GPU básica<br/>large/x → Servidor / Tesla HW3</div>
  </div>
</div>

---
layout: default
---

# YOLO v8 — Arquitectura y Variantes

<div class="mt-2">
  <div class="flex items-stretch gap-1 text-xs text-center mb-3">
    <div v-click class="flex-1 p-2 rounded" style="background:#1B4F72;">
      <div class="font-bold text-accent mb-1">Backbone</div>
      <div class="muted">CSPDarknet</div>
      <div class="muted">Extrae features multi-escala con conexiones residuales</div>
    </div>
    <div class="flex items-center text-accent px-1">→</div>
    <div v-click class="flex-1 p-2 rounded" style="background:#1B4F72;">
      <div class="font-bold text-accent mb-1">Neck</div>
      <div class="muted">PANet</div>
      <div class="muted">Fusiona features de distintos niveles de resolución</div>
    </div>
    <div class="flex items-center text-accent px-1">→</div>
    <div v-click class="flex-1 p-2 rounded" style="border: 2px solid #00D4FF;">
      <div class="font-bold text-accent mb-1">Head</div>
      <div class="muted">Decoupled</div>
      <div class="muted">Clasificación + Localización en ramas separadas</div>
    </div>
    <div class="flex items-center text-accent px-1">→</div>
    <div v-click class="flex-1 p-2 rounded" style="background:#0a2a1a; border: 1px solid #10B981;">
      <div class="font-bold success mb-1">Output</div>
      <div class="muted">Bounding boxes + clases + confianza en una sola pasada</div>
    </div>
  </div>
  <div class="grid grid-cols-3 gap-2 text-xs">
    <div v-click class="p-3 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2">Variantes y parámetros</div>
      <table class="w-full">
        <tr><td class="muted">n (nano)</td><td class="accent text-right">3.2M</td></tr>
        <tr><td class="muted">s (small)</td><td class="accent text-right">11.2M</td></tr>
        <tr><td class="muted">m (medium)</td><td class="accent text-right">25.9M</td></tr>
        <tr><td class="muted">l (large)</td><td class="accent text-right">43.7M</td></tr>
        <tr><td class="muted">x (xlarge)</td><td class="accent text-right">68.2M</td></tr>
      </table>
    </div>
    <div v-click class="p-3 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2">mAP@0.5:0.95 en COCO</div>
      <table class="w-full">
        <tr><td class="muted">nano</td><td class="text-right warning">37.3%</td></tr>
        <tr><td class="muted">small</td><td class="text-right warning">44.9%</td></tr>
        <tr><td class="muted">medium</td><td class="text-right success">50.2%</td></tr>
        <tr><td class="muted">large</td><td class="text-right success">52.9%</td></tr>
        <tr><td class="muted">xlarge</td><td class="text-right" style="color:#10B981;">53.9%</td></tr>
      </table>
    </div>
    <div v-click class="p-3 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2">Instalación y uso</div>
      <div class="font-mono p-2 rounded" style="background:#0D1B2A; color:#10B981; font-size:0.65rem; line-height:1.4;">pip install ultralytics<br/><br/>from ultralytics import YOLO<br/>model = YOLO('yolov8n.pt')<br/>results = model('imagen.jpg')<br/>results[0].show()</div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Segmentación Semántica — Más allá del Bounding Box

<img src="/img/b02-robot-vision.jpg" class="absolute right-0 top-0 h-full w-1/3 object-cover opacity-10 -z-1" />

<div class="grid grid-cols-2 gap-4 mt-3">
  <div class="space-y-2">
    <div v-click class="card-ev p-3 text-xs">
      <div class="text-accent font-bold mb-2">Detección vs Segmentación</div>
      <div class="grid grid-cols-2 gap-2">
        <div>
          <div class="font-bold mb-1"><mdi-package class="inline" /> Detección</div>
          <div class="muted">Bounding box rectangular. Rápido. Incluye fondo en el área detectada.</div>
        </div>
        <div>
          <div class="font-bold mb-1" style="color:#10B981;"><mdi-palette class="inline" /> Segmentación</div>
          <div class="muted">Máscara exacta por píxel. Más lento. Contorno preciso del objeto.</div>
        </div>
      </div>
    </div>
    <div v-click class="card-ev p-3 text-xs">
      <div class="text-accent font-bold mb-2">Tipos de Segmentación</div>
      <div class="space-y-1 muted">
        <div><span class="text-accent">Semántica:</span> cada píxel = una clase. Todos los peatones = mismo color</div>
        <div><span class="text-accent">Instancia:</span> cada objeto = ID único. Peatón 1, Peatón 2...</div>
        <div><span class="text-accent">Panóptica:</span> combina ambas — estado del arte (YOLO-seg, Mask R-CNN)</div>
      </div>
    </div>
  </div>
  <div class="space-y-2">
    <div v-click class="p-3 rounded text-xs" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2">¿Para qué sirve en EV en Juárez?</div>
      <div class="space-y-1 muted">
        <div><mdi-road class="inline" /> <span class="accent">Detección de carril:</span> área exacta de asfalto disponible vs tierra</div>
        <div><mdi-waves class="inline" /> <span class="accent">Charcos y baches:</span> área afectada del pavimento en lluvias</div>
        <div><mdi-construction class="inline" /> <span class="accent">Zonas de obra:</span> identificar el área exacta bloqueada</div>
        <div><mdi-walk class="inline" /> <span class="accent">Espacio peatonal:</span> cálculo de área para maniobras seguras</div>
      </div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="border: 1px solid #00D4FF;">
      <div class="text-accent font-bold mb-1">Arquitecturas populares</div>
      <div class="muted">U-Net, DeepLab v3+, SegFormer, YOLO-Seg. Todas disponibles pre-entrenadas en Hugging Face y Roboflow Universe para descarga inmediata</div>
    </div>
    <div v-click class="p-2 rounded text-xs" style="background:#0a2a1a;">
      <div class="success font-bold mb-1">YOLOv8-seg en práctica</div>
      <div class="muted">Combina detección + segmentación. Modelo "small" corre a 15fps en Jetson Nano — suficiente para alertas de carril en tiempo real</div>
    </div>
  </div>
</div>

---
layout: default
---

# Métricas — IoU (Intersection over Union)

<div class="grid grid-cols-2 gap-4 mt-4">
  <div>
    <div v-click class="mb-3">
      <div class="font-bold text-accent mb-2">¿Qué mide el IoU?</div>
      <div class="text-xs muted mb-3">Qué tan bien el bounding box predicho coincide con el anotado a mano (ground truth)</div>
      <div class="font-mono text-center p-3 rounded" style="background:#1B4F72; color:#00D4FF;">
        IoU = Área de Intersección<br/>
        ─────────────────────<br/>
        Área de Unión
      </div>
    </div>
    <div v-click class="space-y-2 text-xs">
      <div class="flex justify-between items-center p-2 rounded" style="background:#1B4F72;">
        <span class="muted">IoU = 1.0</span>
        <div class="flex-1 mx-3 h-2 rounded" style="background:#10B981;"></div>
        <span class="success font-bold">Perfecto ✓</span>
      </div>
      <div class="flex justify-between items-center p-2 rounded" style="background:#1B4F72;">
        <span class="muted">IoU &gt; 0.5</span>
        <div class="w-16 mx-3 h-2 rounded" style="background:#10B981;"></div>
        <span class="success">Aceptable</span>
      </div>
      <div class="flex justify-between items-center p-2 rounded" style="background:#1B4F72;">
        <span class="muted">IoU 0.3–0.5</span>
        <div class="w-10 mx-3 h-2 rounded" style="background:#F59E0B;"></div>
        <span class="warning">Mejorable</span>
      </div>
      <div class="flex justify-between items-center p-2 rounded" style="background:#1B4F72;">
        <span class="muted">IoU &lt; 0.3</span>
        <div class="w-5 mx-3 h-2 rounded" style="background:#ef4444;"></div>
        <span style="color:#ef4444;">Malo ✗</span>
      </div>
    </div>
  </div>
  <div>
    <div v-click class="mb-3 p-3 rounded text-xs" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2">Visualización conceptual</div>
      <div class="relative text-center font-mono" style="height:90px;">
        <div class="absolute border-2 text-xs p-1" style="border-color:#F59E0B; left:5%; top:5%; width:55%; height:75%; color:#F59E0B;">Ground Truth</div>
        <div class="absolute border-2 text-xs p-1" style="border-color:#00D4FF; left:30%; top:20%; width:55%; height:65%; color:#00D4FF;">Predicción</div>
        <div class="absolute font-bold text-lg" style="left:42%; top:40%; color:#10B981;">∩</div>
      </div>
      <div class="text-center muted mt-1">Naranja = Truth | Cyan = Predicción | ∩ = Intersección</div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-1">IoU en práctica — Juárez</div>
      <div class="muted space-y-1">
        <div>Detectar un <span class="accent">tope</span> con IoU 0.45 es suficiente para frenar a tiempo si la detección ocurre a 30m de distancia</div>
        <div>Detectar un <span class="accent">peatón</span> requiere IoU &gt; 0.6 para estimar correctamente la trayectoria y distancia de seguridad</div>
      </div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Métricas — Precisión, Recall y mAP

<div class="grid grid-cols-2 gap-4 mt-3">
  <div class="space-y-2">
    <div v-click class="card-ev p-3 text-xs">
      <div class="text-accent font-bold mb-2">Matriz de Confusión base</div>
      <table class="w-full text-center border-collapse text-xs">
        <tr>
          <td class="p-1"></td>
          <td class="p-1 muted">Detectó objeto</td>
          <td class="p-1 muted">No detectó</td>
        </tr>
        <tr>
          <td class="muted p-1">Hay objeto</td>
          <td class="p-1 font-bold" style="background:#0a2a1a; color:#10B981;">TP ✓</td>
          <td class="p-1" style="background:#2a1810; color:#ef4444;">FN ✗</td>
        </tr>
        <tr>
          <td class="muted p-1">No hay objeto</td>
          <td class="p-1" style="background:#2a1810; color:#ef4444;">FP ✗</td>
          <td class="p-1 font-bold" style="background:#0a2a1a; color:#10B981;">TN ✓</td>
        </tr>
      </table>
    </div>
    <div v-click class="card-ev p-3 text-xs">
      <div class="grid grid-cols-2 gap-2">
        <div>
          <div class="text-accent font-bold mb-1">Precisión</div>
          <div class="font-mono p-1 rounded mb-1" style="background:#0D1B2A; color:#00D4FF;">TP / (TP + FP)</div>
          <div class="muted">¿De lo que detecté, cuánto es correcto? Evita falsas alarmas innecesarias</div>
        </div>
        <div>
          <div class="font-bold mb-1" style="color:#10B981;">Recall</div>
          <div class="font-mono p-1 rounded mb-1" style="background:#0D1B2A; color:#10B981;">TP / (TP + FN)</div>
          <div class="muted">¿De lo que existe, cuánto detecto? Evita objetos perdidos peligrosos</div>
        </div>
      </div>
    </div>
  </div>
  <div class="space-y-2">
    <div v-click class="card-ev p-3 text-xs">
      <div class="font-bold mb-2" style="color:#F59E0B;">mAP — mean Average Precision</div>
      <div class="muted mb-2">Promedia la precisión en distintos umbrales de recall para todas las clases del modelo. Es la métrica estándar de la industria.</div>
      <div class="p-2 rounded font-mono" style="background:#0D1B2A;">
        <div style="color:#00D4FF;">mAP@0.50 — estándar básico</div>
        <div style="color:#10B981;">mAP@0.50:0.95 — más exigente</div>
      </div>
    </div>
    <div v-click class="card-ev p-3 text-xs">
      <div class="text-accent font-bold mb-2">Trade-off según aplicación en EV</div>
      <div class="space-y-1 muted">
        <div>Seguridad peatonal → <span style="color:#10B981;">alto Recall</span> (nunca perder un peatón, aunque haya falsas alarmas)</div>
        <div>Cobro automático de peaje → <span class="accent">alta Precisión</span> (no cobrar incorrectamente)</div>
      </div>
    </div>
    <div v-click class="p-2 rounded text-xs" style="border: 1px solid #00D4FF;">
      <div class="text-accent font-bold mb-1">Meta para proyectos UTCJ</div>
      <div class="muted">Apuntar a mAP@0.5 &gt; 80% en dataset local (topes + señales). YOLOv8-medium pre-entrenado logra ~67% en COCO — con fine-tuning local podemos superar eso.</div>
    </div>
  </div>
</div>

---
layout: default
---

# Comparativa de Modelos de Detección

<div class="slide-scroll mt-3">
  <div v-click class="mb-3">
    <table class="w-full border-collapse text-xs">
      <thead>
        <tr style="background:#1B4F72; color:#00D4FF;">
          <th class="p-2 text-left">Modelo</th>
          <th class="p-2 text-center">Velocidad GPU</th>
          <th class="p-2 text-center">mAP@0.5</th>
          <th class="p-2 text-center">Params</th>
          <th class="p-2 text-center">Hardware mín.</th>
          <th class="p-2 text-left">Uso en EV</th>
        </tr>
      </thead>
      <tbody>
        <tr class="border-b border-gray-700" style="background:#0a1520;">
          <td class="p-2 font-bold" style="color:#00D4FF;">YOLOv8-nano</td>
          <td class="p-2 text-center success">6.3 ms</td>
          <td class="p-2 text-center warning">52.9%</td>
          <td class="p-2 text-center muted">3.2M</td>
          <td class="p-2 text-center muted">Jetson Nano</td>
          <td class="p-2 muted">Dash-cam, edge IoT</td>
        </tr>
        <tr class="border-b border-gray-700">
          <td class="p-2 font-bold" style="color:#00D4FF;">YOLOv8-medium</td>
          <td class="p-2 text-center warning">18.2 ms</td>
          <td class="p-2 text-center success">67.2%</td>
          <td class="p-2 text-center muted">25.9M</td>
          <td class="p-2 text-center muted">GPU GTX/RTX</td>
          <td class="p-2 muted">Unidad central EV</td>
        </tr>
        <tr class="border-b border-gray-700" style="background:#0a1520;">
          <td class="p-2 font-bold" style="color:#A78BFA;">SSD-MobileNet v2</td>
          <td class="p-2 text-center success">8.0 ms</td>
          <td class="p-2 text-center" style="color:#ef4444;">48.0%</td>
          <td class="p-2 text-center muted">10M</td>
          <td class="p-2 text-center muted">Raspberry Pi 5</td>
          <td class="p-2 muted">IoT bajo costo</td>
        </tr>
        <tr class="border-b border-gray-700">
          <td class="p-2 font-bold" style="color:#A78BFA;">Faster R-CNN</td>
          <td class="p-2 text-center" style="color:#ef4444;">87 ms</td>
          <td class="p-2 text-center" style="color:#10B981;">73.2%</td>
          <td class="p-2 text-center muted">137M</td>
          <td class="p-2 text-center muted">GPU servidor</td>
          <td class="p-2 muted">Análisis offline</td>
        </tr>
        <tr class="border-b border-gray-700" style="background:#0a1520;">
          <td class="p-2 font-bold" style="color:#10B981;">EfficientDet-D2</td>
          <td class="p-2 text-center warning">24 ms</td>
          <td class="p-2 text-center success">68.0%</td>
          <td class="p-2 text-center muted">8.1M</td>
          <td class="p-2 text-center muted">GPU mid-range</td>
          <td class="p-2 muted">Balance ideal</td>
        </tr>
        <tr>
          <td class="p-2 font-bold" style="color:#F59E0B;">RT-DETR-L</td>
          <td class="p-2 text-center warning">21 ms</td>
          <td class="p-2 text-center" style="color:#10B981;">72.0%</td>
          <td class="p-2 text-center muted">32M</td>
          <td class="p-2 text-center muted">RTX 3060+</td>
          <td class="p-2 muted">Sistema flagship</td>
        </tr>
      </tbody>
    </table>
  </div>
  <div v-click class="p-2 rounded text-xs text-center" style="background:#1B4F72; color:#00D4FF;">
    Recomendación UTCJ: <strong>YOLOv8-nano</strong> para práctica en Colab gratuito | <strong>YOLOv8-medium</strong> para proyecto final de semestre
  </div>
</div>

---
layout: default
class: dark-slide
---

# Pipeline Completo — Del Píxel a la Decisión

<div class="mt-2">
  <div class="flex items-stretch gap-1 text-xs text-center mb-3">
    <div v-click class="card-ev flex-1 p-2">
      <mdi-camera class="text-xl mb-1" />
      <div class="font-bold text-accent">Sensor</div>
      <div class="muted mt-1">Cámara 60fps en taxi eléctrico o camioneta de flota maquiladora</div>
    </div>
    <div class="flex items-center text-accent text-lg">→</div>
    <div v-click class="card-ev flex-1 p-2">
      <mdi-cog class="text-xl mb-1" />
      <div class="font-bold text-accent">Pre-proceso</div>
      <div class="muted mt-1">Filtro de polvo + normalización 0–1. Resize 640×640 para YOLO</div>
    </div>
    <div class="flex items-center text-accent text-lg">→</div>
    <div v-click class="card-ev flex-1 p-2">
      <mdi-brain class="text-xl mb-1" />
      <div class="font-bold text-accent">Modelo CNN</div>
      <div class="muted mt-1">YOLOv8 + fine-tuning con dataset Juárez (topes, señales ALTO)</div>
    </div>
    <div class="flex items-center text-accent text-lg">→</div>
    <div v-click class="card-ev flex-1 p-2">
      <mdi-wrench class="text-xl mb-1" />
      <div class="font-bold text-accent">Post-proceso</div>
      <div class="muted mt-1">NMS filtra duplicados. Alerta si tope o peatón &lt; 15m</div>
    </div>
    <div class="flex items-center text-accent text-lg">→</div>
    <div v-click class="card-ev flex-1 p-2">
      <mdi-car-electric class="text-xl mb-1" />
      <div class="font-bold text-accent">Actuación</div>
      <div class="muted mt-1">Reduce velocidad antes del tope. Alerta de fila en garita fronteriza</div>
    </div>
  </div>
  <div v-click class="grid grid-cols-3 gap-2 text-xs">
    <div class="p-2 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-1">Latencias por etapa</div>
      <div class="font-mono space-y-0.5 muted">
        <div>Captura cámara: <span class="accent">~2ms</span></div>
        <div>Pre-proceso: <span class="accent">~3ms</span></div>
        <div>Inferencia YOLO-n: <span class="accent">~6ms</span></div>
        <div>Post-proceso NMS: <span class="accent">~1ms</span></div>
        <div class="success font-bold">Total: ~12ms ✓ (30fps+)</div>
      </div>
    </div>
    <div class="p-2 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-1">Fusión con LiDAR y Radar</div>
      <div class="muted space-y-0.5">
        <div>Cámara → clase (¿qué es?)</div>
        <div>LiDAR → posición exacta (¿dónde?)</div>
        <div>Radar → velocidad relativa</div>
        <div class="success">Fusión → decisión segura y robusta</div>
      </div>
    </div>
    <div class="p-2 rounded" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-1">Ruta Bermúdez → Zaragoza</div>
      <div class="muted space-y-0.5">
        <div>35 km, 8 zonas de topes</div>
        <div>3 intersecciones semáforo crítico</div>
        <div>2 zonas maquiladora (6am)</div>
        <div class="accent">1800 frames procesados por km</div>
      </div>
    </div>
  </div>
  <div v-click class="mt-2 text-xs text-center p-2 rounded" style="background:#1B4F72; color:#00D4FF;">
    Dato: el 40% de los accidentes en Juárez ocurren en intersecciones con semáforo apagado — la visión artificial puede compensar
  </div>
</div>

---
layout: default
---

# Datasets Internacionales para EV

<div class="slide-scroll mt-3">
  <div class="grid grid-cols-3 gap-2 text-xs">
    <div v-click class="card-ev p-3">
      <div class="text-accent font-bold mb-1">KITTI</div>
      <div class="badge-ev mb-1">Karlsruhe, Alemania</div>
      <div class="muted space-y-0.5">
        <div>15,000 frames etiquetados</div>
        <div>Cámara estéreo + LiDAR + GPS/IMU</div>
        <div>Clases: autos, peatones, ciclistas</div>
        <div class="success">✓ Benchmark estándar industria</div>
        <div class="warning">✗ Sin topes ni señales en español</div>
      </div>
    </div>
    <div v-click class="card-ev p-3">
      <div class="text-accent font-bold mb-1">nuScenes</div>
      <div class="badge-ev mb-1">Boston / Singapore</div>
      <div class="muted space-y-0.5">
        <div>1,000 escenas, 1.4M anotaciones</div>
        <div>6 cámaras + 5 radares + 1 LiDAR</div>
        <div>3D bounding boxes en nube LiDAR</div>
        <div class="success">✓ Multi-sensor, muy completo</div>
        <div class="warning">✗ Solo ciudades del primer mundo</div>
      </div>
    </div>
    <div v-click class="card-ev p-3">
      <div class="text-accent font-bold mb-1">Waymo Open</div>
      <div class="badge-ev mb-1">San Francisco / Phoenix</div>
      <div class="muted space-y-0.5">
        <div>1,950 escenas, 12M anotaciones 3D</div>
        <div>LiDAR 64-beam + 5 cámaras HD</div>
        <div>Cobertura nocturna y lluvia</div>
        <div class="success">✓ El más grande disponible</div>
        <div class="warning">✗ Sin infraestructura latinoamericana</div>
      </div>
    </div>
    <div v-click class="card-ev p-3">
      <div class="text-accent font-bold mb-1">BDD100K</div>
      <div class="badge-ev mb-1">Berkeley</div>
      <div class="muted space-y-0.5">
        <div>100,000 video clips de conducción</div>
        <div>Variedad: noche, lluvia, niebla, nieve</div>
        <div>Peatones, señales, carriles</div>
        <div class="success">✓ Máxima diversidad de condiciones</div>
        <div class="warning">✗ Solo señalización en inglés</div>
      </div>
    </div>
    <div v-click class="card-ev p-3">
      <div class="text-accent font-bold mb-1">Cityscapes</div>
      <div class="badge-ev mb-1">50 ciudades Europa</div>
      <div class="muted space-y-0.5">
        <div>5,000 imgs segmentación semántica</div>
        <div>25,000 imágenes semi-anotadas</div>
        <div>30 clases de objetos urbanos</div>
        <div class="success">✓ Ideal para segmentación semántica</div>
        <div class="warning">✗ Sin contexto frontera México–EE.UU.</div>
      </div>
    </div>
    <div v-click class="p-3 rounded" style="border: 2px solid #00D4FF;">
      <div class="text-accent font-bold mb-1"><mdi-city class="inline" /> Dataset Juárez (pendiente)</div>
      <div class="muted space-y-0.5">
        <div class="success">Necesidades identificadas:</div>
        <div>• Topes / lomos de burro</div>
        <div>• Señal "ALTO" (no STOP)</div>
        <div>• Garitas fronterizas en fila</div>
        <div>• Polvo de desierto + sol directo</div>
        <div>• Maquiladoras (peatones masivos 6am)</div>
        <div class="accent font-bold mt-1">→ Proyecto UTCJ: anotar 1,000 imgs locales</div>
      </div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# El Problema del Dataset Local — Juárez

<div class="grid grid-cols-2 gap-4 mt-3">
  <div>
    <div v-click class="mb-3 p-3 rounded text-xs" style="background:#2a1810; border-left: 3px solid #ef4444;">
      <div class="font-bold mb-2" style="color:#ef4444;">¿Por qué fallan los modelos internacionales?</div>
      <div class="muted space-y-1">
        <div>• Los topes (lomos de burro) <span class="warning">no existen</span> en datasets de EE.UU. ni Europa</div>
        <div>• Las señales ALTO son diferentes al STOP anglosajón en forma y tipografía</div>
        <div>• El polvo del desierto chihuahuense crea haze visual sin equivalente en datasets europeos</div>
        <div>• Las garitas del Puente Zaragoza son infraestructura única en el mundo</div>
        <div>• Colonias sin pavimento: textura de tierra sin par en datasets urbanos internacionales</div>
      </div>
    </div>
    <div v-click class="p-3 rounded text-xs" style="background:#0a2a1a; border-left: 3px solid #10B981;">
      <div class="success font-bold mb-1">Solución: Dataset propio + Transfer Learning</div>
      <div class="muted">Recopilar imágenes locales, anotar con Roboflow, combinar con COCO para transfer learning. Con solo 500–1000 imágenes anotadas se logra mAP &gt; 75% en clases locales.</div>
    </div>
  </div>
  <div>
    <div v-click class="card-ev p-3 text-xs mb-2">
      <div class="text-accent font-bold mb-2">Plan de recolección — UTCJ</div>
      <div class="space-y-1 muted">
        <div><mdi-map-marker class="inline" /> <span class="accent">Zonas clave:</span> Blvd. Zaragoza, Tecnológico, Parque Bermúdez, Puente Córdoba-Américas</div>
        <div><mdi-camera class="inline" /> <span class="accent">Cámara:</span> dashcam 1080p o smartphone en soporte</div>
        <div><mdi-clock-outline class="inline" /> <span class="accent">Horarios:</span> 6am (turno maquila), 2pm (calor máximo), 10pm (oscuridad)</div>
        <div><mdi-weather-rainy class="inline" /> <span class="accent">Condiciones:</span> día soleado, polvo, lluvia, noche</div>
        <div><mdi-tag class="inline" /> <span class="accent">Anotación:</span> 4 equipos × 250 imgs = 1,000 imágenes anotadas</div>
      </div>
    </div>
    <div v-click class="p-2 rounded text-xs" style="border: 1px solid #00D4FF;">
      <div class="text-accent font-bold mb-1">Estimación de resultados</div>
      <div class="muted">1,000 imgs + transfer learning desde YOLOv8 preentrenado → mAP esperado &gt; 75% en topes y señales locales. Tiempo de entrenamiento: 2–3h en Colab T4 gratuito.</div>
    </div>
  </div>
</div>

---
layout: default
---

# Roboflow — Anotación y Entrenamiento

<img src="/img/b02-sensors.jpg" class="absolute right-0 top-0 h-full w-1/4 object-cover opacity-10 -z-1" />

<div class="grid grid-cols-2 gap-4 mt-3">
  <div>
    <div v-click class="mb-3 p-3 rounded text-sm" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2"><mdi-cloud class="inline" /> ¿Qué es Roboflow?</div>
      <div class="text-xs muted">Plataforma end-to-end para Computer Vision: desde la carga de imágenes hasta el deploy del modelo, sin configurar servidores ni entornos complejos.</div>
    </div>
    <div v-click class="space-y-1 text-xs">
      <div class="flex items-center gap-2 p-2 rounded" style="background:#1B4F72;">
        <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold text-xs flex items-center justify-center flex-shrink-0">1</div>
        <div><span class="text-accent font-bold">Carga:</span> <span class="muted">Sube imágenes (jpg, png, video frame)</span></div>
      </div>
      <div class="flex items-center gap-2 p-2 rounded" style="background:#1B4F72;">
        <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold text-xs flex items-center justify-center flex-shrink-0">2</div>
        <div><span class="text-accent font-bold">Anota:</span> <span class="muted">Dibuja bounding boxes con drag &amp; drop, etiqueta clases</span></div>
      </div>
      <div class="flex items-center gap-2 p-2 rounded" style="background:#1B4F72;">
        <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold text-xs flex items-center justify-center flex-shrink-0">3</div>
        <div><span class="text-accent font-bold">Augmenta:</span> <span class="muted">Flip, rotación ±15°, brillo ±20% — multiplica dataset x5</span></div>
      </div>
      <div class="flex items-center gap-2 p-2 rounded" style="background:#1B4F72;">
        <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold text-xs flex items-center justify-center flex-shrink-0">4</div>
        <div><span class="text-accent font-bold">Exporta:</span> <span class="muted">Formato YOLO, COCO, Pascal VOC para Colab</span></div>
      </div>
      <div class="flex items-center gap-2 p-2 rounded" style="background:#1B4F72;">
        <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold text-xs flex items-center justify-center flex-shrink-0">5</div>
        <div><span class="text-accent font-bold">Entrena:</span> <span class="muted">Con Colab + Ultralytics o Roboflow Train directo</span></div>
      </div>
    </div>
  </div>
  <div class="space-y-2">
    <div v-click class="p-3 rounded text-xs" style="background:#1B4F72;">
      <div class="text-accent font-bold mb-2"><mdi-circle-outline class="inline" /> Código en Google Colab</div>
      <div class="font-mono p-2 rounded" style="background:#0D1B2A; color:#10B981; font-size:0.65rem; line-height:1.5;">!pip install ultralytics roboflow<br/><br/>from roboflow import Roboflow<br/>rf = Roboflow(api_key="TU_KEY")<br/>ds = rf.workspace().project("juarez-ev")<br/>ds.version(1).download("yolov8")<br/><br/>from ultralytics import YOLO<br/>model = YOLO('yolov8n.pt')<br/>model.train(data='data.yaml', epochs=50)</div>
    </div>
    <div v-click class="p-2 rounded text-xs" style="background:#0a2a1a; border: 1px solid #10B981;">
      <div class="success font-bold mb-1">Tiempo estimado en Colab Free (T4)</div>
      <div class="muted">500 imágenes + YOLOv8-nano + 50 epochs → <span class="success font-bold">~25 minutos</span> en GPU T4 gratuita de Google Colab</div>
    </div>
    <div v-click class="p-2 rounded text-xs" style="border: 1px solid #00D4FF;">
      <div class="text-accent font-bold mb-1">Data Augmentation automática</div>
      <div class="muted">Roboflow convierte 500 imgs → ~2,500 variantes con flip, rotación, brillo, recorte. Reduce overfitting sin necesitar más fotos reales.</div>
    </div>
  </div>
</div>

---
layout: default
class: dark-slide
---

# Edge Deployment — IA en el Vehículo

<img src="/img/b02-selfdriving.jpg" class="absolute right-0 top-0 h-full w-1/3 object-cover opacity-10 -z-1" />

<div class="grid grid-cols-3 gap-2 mt-3 text-xs">
  <div v-click class="card-ev p-3">
    <mdi-circle class="text-2xl mb-1 text-center" />
    <div class="text-accent font-bold mb-1 text-center">Raspberry Pi 4/5</div>
    <div class="muted space-y-0.5 mb-2">
      <div>CPU: ARM Cortex-A72 4-core</div>
      <div>RAM: 4–8 GB LPDDR4</div>
      <div>Costo: <span class="success">~$80 USD</span></div>
    </div>
    <div class="p-1 rounded mb-2" style="background:#0D1B2A;">
      <div class="muted">YOLOv8-nano: <span style="color:#ef4444;">~500ms</span> (sin GPU accel.)</div>
      <div class="muted">Con TPU Coral: <span class="success">~80ms</span></div>
    </div>
    <div class="muted">Ideal: alertas básicas, parking assist, cámara de respaldo en flota de bajo costo</div>
  </div>
  <div v-click class="card-ev p-3" style="border: 1px solid #10B981;">
    <mdi-lightning-bolt class="text-2xl mb-1 text-center" />
    <div class="font-bold mb-1 text-center" style="color:#10B981;">NVIDIA Jetson Nano</div>
    <div class="muted space-y-0.5 mb-2">
      <div>GPU: 128-core Maxwell CUDA</div>
      <div>RAM: 4 GB LPDDR4</div>
      <div>Costo: <span class="warning">~$99 USD</span></div>
    </div>
    <div class="p-1 rounded mb-2" style="background:#0D1B2A;">
      <div class="muted">YOLOv8-nano: <span class="warning">~50ms</span> (~20fps)</div>
      <div class="muted">Con TensorRT: <span class="success">~20ms</span> (50fps)</div>
    </div>
    <div class="muted">Ideal: detección en tiempo real — dashcam inteligente para flota de taxis UTCJ</div>
  </div>
  <div v-click class="card-ev p-3">
    <mdi-rocket class="text-2xl mb-1 text-center" />
    <div class="text-accent font-bold mb-1 text-center">NVIDIA Jetson Orin Nano</div>
    <div class="muted space-y-0.5 mb-2">
      <div>GPU: 1024-core Ampere + 32 Tensor Cores</div>
      <div>RAM: 8 GB LPDDR5</div>
      <div>Costo: <span style="color:#F59E0B;">$249–329 USD</span></div>
    </div>
    <div class="p-1 rounded mb-2" style="background:#0D1B2A;">
      <div class="muted">YOLOv8-nano INT8: <span class="success">~16ms</span> (60fps)</div>
      <div class="muted">80× más rápido que Jetson Nano</div>
    </div>
    <div class="muted">Ideal: vehículo autónomo completo nivel L3/L4, sistema multi-sensor en tiempo real</div>
  </div>
</div>

<div v-click class="mt-3 p-2 rounded text-xs text-center" style="background:#1B4F72;">
  <span class="text-accent font-bold">Ruta UTCJ:</span>
  <span class="muted"> Desarrollar en Colab (gratis) → validar en Jetson Nano ($99) → producción con Orin Nano ($249) si el proyecto lo justifica</span>
</div>

---
layout: default
class: dark-slide
---

# Práctica — Bloque 02

<div class="badge-ev mb-2">PRÁCTICA — DETECCIÓN EN CALLES DE JUÁREZ</div>

<div class="grid grid-cols-2 gap-3 mt-2">
  <div class="space-y-1">
    <div v-click class="flex items-start gap-2 text-xs p-2 rounded" style="background:#1B4F72;">
      <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold flex items-center justify-center flex-shrink-0">1</div>
      <div>Crear cuenta gratuita en <strong>Roboflow</strong> y explorar datasets públicos de tráfico urbano en Roboflow Universe</div>
    </div>
    <div v-click class="flex items-start gap-2 text-xs p-2 rounded" style="background:#1B4F72;">
      <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold flex items-center justify-center flex-shrink-0">2</div>
      <div>Cargar dataset <strong>Udacity Self-Driving</strong> (Roboflow Universe) — peatones, autos, señales de tráfico</div>
    </div>
    <div v-click class="flex items-start gap-2 text-xs p-2 rounded" style="background:#1B4F72;">
      <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold flex items-center justify-center flex-shrink-0">3</div>
      <div>Abrir cuaderno Colab con <strong>YOLOv8-nano</strong> pre-entrenado y ejecutar inferencia célula por célula</div>
    </div>
    <div v-click class="flex items-start gap-2 text-xs p-2 rounded" style="background:#1B4F72;">
      <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold flex items-center justify-center flex-shrink-0">4</div>
      <div><strong>Foto propia de calle juarense</strong> — o Google Street View (Blvd. Zaragoza, Tecnológico, Parque Bermúdez)</div>
    </div>
    <div v-click class="flex items-start gap-2 text-xs p-2 rounded" style="background:#1B4F72;">
      <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold flex items-center justify-center flex-shrink-0">5</div>
      <div>Registrar <strong>IoU, mAP y latencia</strong>. Identificar qué objetos locales el modelo internacional NO detecta</div>
    </div>
    <div v-click class="flex items-start gap-2 text-xs p-2 rounded" style="background:#1B4F72;">
      <div class="w-5 h-5 rounded-full bg-accent text-primary font-bold flex items-center justify-center flex-shrink-0">6</div>
      <div>Anotar 10 imágenes locales en Roboflow y observar la mejora con Transfer Learning de 1 epoch</div>
    </div>
  </div>
  <div class="space-y-2">
    <div v-click class="card-ev p-3 text-xs">
      <div class="font-bold text-accent mb-2">Objetos a buscar en foto local</div>
      <div class="grid grid-cols-2 gap-0.5 muted">
        <div>✓ Letrero "ALTO"</div>
        <div>✓ Tope / lomo de burro</div>
        <div>✓ Camión de ruta urbana</div>
        <div>✓ Bache o pavimento dañado</div>
        <div>✓ Puesto informal en banqueta</div>
        <div>✓ Garita fronteriza</div>
      </div>
      <div class="mt-2 muted">Si el modelo no detecta → necesitamos anotar y reentrenar con datos locales</div>
    </div>
    <div v-click class="p-2 rounded text-xs" style="border: 1px solid #00D4FF;">
      <div class="text-accent font-bold mb-1">Entregable</div>
      <div class="muted">Captura de detecciones + tabla IoU/mAP/latencia + lista de objetos no detectados + propuesta de 3 clases para dataset local de Juárez</div>
    </div>
  </div>
</div>

---
layout: center
class: dark-slide
---

# Puntos Clave — Bloque 02

<div class="space-y-2 mt-3 text-left max-w-2xl mx-auto text-sm">
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Cámaras, LiDAR y Radar se fusionan — en Juárez el polvo del desierto y el sol intenso hacen que ningún sensor funcione solo</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Las CNN extraen características visuales jerárquicamente: bordes → formas → objetos completos, sin programar reglas manualmente</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Transfer Learning permite re-entrenar en horas con 200–2,000 imágenes locales, reutilizando pesos pre-entrenados en millones de imágenes</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>IoU mide calidad del bounding box, mAP mide precisión promedio por clase — métricas estándar en toda la industria de visión artificial</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Los datasets internacionales (KITTI, Waymo, nuScenes) no tienen topes, señales ALTO ni garitas — Juárez necesita su propio dataset local</span>
  </div>
  <div v-click class="flex items-start gap-2">
    <span style="color:#10B981;">✓</span>
    <span>Roboflow + YOLOv8 + Colab gratuito permiten crear un detector funcional en una sesión de laboratorio, sin GPU propia ni presupuesto extra</span>
  </div>
</div>

<div class="mt-4 text-sm muted">
  > Siguiente: <span class="text-accent font-bold">Bloque 03 — Arquitectura de Sistemas y Deployment</span>
</div>
