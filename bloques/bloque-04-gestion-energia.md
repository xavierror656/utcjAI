# Bloque 04 — Gestion Inteligente de Energia y Baterias

## Metadatos

```
Archivo de salida : Bloque04-Gestion-Energia.pptx
Duracion          : 2 horas
Icono principal   : MdBatteryChargingFull (react-icons/md)
Total de slides   : 10
```

---

## Slide 1 — Portada
```
Icono   : MdBatteryChargingFull, 00D4FF
Titulo  : "Gestion Inteligente de Energia y Baterias"
Subtitulo: "IA aplicada al corazon electrico del vehiculo"
Imagen  : bateria / pack de celdas EV, baja opacidad
```

## Slide 2 — Indice
```
Items:
  FaBatteryFull   → "Funcionamiento del BMS"
  FaChartLine     → "Regresion y Series de Tiempo"
  FaPercentage    → "State of Charge (SoC)"
  FaHeartbeat     → "State of Health (SoH)"
  FaThermometerHalf → "Variables criticas: temperatura, ciclos"
  FaFlask         → "Practica: Simulacion de consumo"
```

## Slide 3 — El BMS (Battery Management System)
```
Tipo    : DIAGRAMA + TEXTO
Fondo   : 0D1B2A
Titulo  : "BMS — El Sistema Nervioso de la Bateria"

Diagrama circular (BMS en centro, 6 funciones alrededor):
  Centro: circulo 00D4FF, texto "BMS", icono FaBrain

6 modulos conectados:
  FaThermometerHalf → "Control de Temperatura"
  FaBalanceScale    → "Balanceo de Celdas"
  FaShieldAlt       → "Proteccion: sobredescarga, sobrecarga"
  FaChartLine       → "Estimacion SoC / SoH"
  FaWifi            → "Comunicacion CAN Bus / OBD"
  FaHistory         → "Registro historico de ciclos"

Imagen derecha: pack de bateria EV esquematico
```

## Slide 4 — Regresion y Series de Tiempo
```
Tipo    : CONTENIDO CON GRAFICOS
Fondo   : F0F4F8
Titulo  : "Modelos Predictivos para Baterias"

Izquierda — Regresion:
  "Predice un valor numerico (SoC, autonomia)"
  Casos: prediccion de carga segun temperatura, velocidad, aceleracion
  Icono FaChartLine

Derecha — Series de Tiempo:
  "Predice la evolucion de una variable en el tiempo"
  Casos: degradacion de bateria por ciclos, prediccion de falla
  Icono FaHistory
  Modelos: LSTM, ARIMA, Prophet

Caja informativa:
  "Diferencia clave: la regresion usa un snapshot de variables,
  la serie de tiempo usa el historial para predecir el futuro"
```

## Slide 5 — State of Charge (SoC)
```
Tipo    : DEFINICION + GAUGE VISUAL
Fondo   : 0D1B2A
Titulo  : "SoC — Estado de Carga Actual"

Gauge visual (simulado con formas PptxGenJS):
  Arco de 0% a 100%, marcadores cada 25%
  Aguja en posicion 72% (ejemplo)
  Colores: rojo 0-20%, ambar 20-40%, verde 40-100%

Definicion:
  "SoC = (Carga actual / Capacidad maxima) x 100"

Metodos de estimacion:
  Coulomb Counting  → sumar/restar corriente en el tiempo
  Modelo de voltaje → curva OCV vs SoC
  Kalman Filter     → fusion de ambos con IA

Limitantes:
  "Temperatura, envejecimiento y corrientes de fuga afectan la precision"
```

## Slide 6 — State of Health (SoH)
```
Tipo    : COMPARACION + SERIE DE TIEMPO VISUAL
Fondo   : F0F4F8
Titulo  : "SoH — Estado de Salud de la Bateria"

Grafico de linea (simulado con chart PptxGenJS):
  Eje X: Ciclos de carga (0, 200, 400, 600, 800, 1000)
  Eje Y: SoH % (100, 95, 90, 85, 80, 75)
  Linea descendente suave
  Marcador rojo en SoH=80%: "FIN DE VIDA UTIL"

Definicion:
  "SoH = (Capacidad actual / Capacidad original) x 100"
  "Bateria 'degradada' cuando SoH < 80%"

Factores de degradacion:
  - Ciclos de carga profundos
  - Temperaturas extremas (>45°C o <0°C)
  - Cargas rapidas frecuentes (DC fast charging)
  - Tiempo en calendario
```

## Slide 7 — Variables Criticas del Sistema
```
Tipo    : GRID 3x2
Fondo   : 0D1B2A
Titulo  : "Variables Clave que Monitorea el BMS con IA"

6 tarjetas compactas (fondo 1B4F72):
  Voltaje por celda    | FaBolt          | "V por celda"
  Corriente            | FaExchangeAlt   | "Amperios de carga/descarga"
  Temperatura          | FaThermometer   | "Celsius, critica >45°C"
  SoC                  | FaPercentage    | "% carga disponible"
  SoH                  | FaHeartbeat     | "% salud del pack"
  Ciclos de carga      | FaHistory       | "Contador de cargas completas"
```

## Slide 8 — Algoritmos de IA para BMS
```
Tipo    : TABLA COMPARATIVA
Fondo   : F0F4F8
Titulo  : "Que Algoritmo Usar para Cada Problema"

Tabla:
  Problema              | Algoritmo     | Herramienta
  Estimacion SoC        | Kalman + LSTM | Python / TensorFlow
  Prediccion SoH        | Regresion     | Scikit-learn
  Deteccion de anomalias| Autoencoder   | PyTorch
  Prediccion de falla   | Serie tiempo  | Prophet / LSTM
  Optimizacion de carga | RL            | Gym + Stable Baselines
```

## Slide 9 — Practica
```
Titulo  : "Simulacion de Consumo y Estimacion de Autonomia"

Pasos:
  1. FaTable      → "Cargar dataset de ciclos de bateria (CSV proporcionado)"
  2. FaCode       → "Ejecutar cuaderno Colab: regresion para predecir SoC"
  3. FaChartLine  → "Graficar curva de SoH por ciclos"
  4. FaCalculator → "Estimar autonomia con SoC=80% vs SoC=100%"
  5. FaThermometer→ "Analizar impacto de temperatura en la prediccion"

Dataset: archivo CSV con voltaje, corriente, temperatura, SoC de 500 ciclos simulados
Herramientas: Google Colab, Pandas, Scikit-learn, Matplotlib
```

## Slide 10 — Cierre
```
5 checkpoints:
  1. "El BMS es el sistema que protege, balancea y monitorea la bateria"
  2. "SoC mide la carga actual, SoH mide el envejecimiento del pack"
  3. "La regresion predice valores puntuales; las series de tiempo predicen evolucion"
  4. "Temperatura y ciclos son los principales factores de degradacion"
  5. "La IA mejora la precision de SoC/SoH frente a metodos tradicionales"

Siguiente: "Bloque 05 — Infraestructura de Carga Inteligente"
```

---

## Instrucciones para el Agente

Igual que Bloque 01/02/03. Salida: `Bloque04-Gestion-Energia.pptx`
