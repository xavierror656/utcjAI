# Bloque 05 — Infraestructura de Carga Inteligente

## Metadatos
```
Archivo de salida : Bloque05-Infraestructura-Carga.pptx
Duracion          : 2 horas
Icono principal   : MdEvStation o FaPlug
Total de slides   : 10
```

---

## Slide 1 — Portada
```
Icono   : FaPlug, 00D4FF
Titulo  : "Infraestructura de Carga Inteligente"
Subtitulo: "Smart Grids, prediccion de demanda y energias renovables"
Imagen  : estacion de carga EV con paneles solares
```

## Slide 2 — Indice
```
FaPlug          → "Tecnologias de Carga: Nivel 1, 2, DC Fast"
FaNetworkWired  → "Smart Grids y Comunicacion V2G"
FaChartLine     → "Prediccion de Demanda Energetica"
FaSolarPanel    → "Integracion con Energias Renovables"
FaCogs          → "Optimizacion Basica del Balance"
FaFlask         → "Practica: Algoritmo de Equilibrio Energetico"
```

## Slide 3 — Tecnologias de Carga
```
Tipo    : 3 TARJETAS
Fondo   : 0D1B2A

Tarjeta 1 — Nivel 1 (AC lento)
  Badge: "120V / 1.4kW"
  Icono: FaHome
  Tiempo: "6-20 horas para carga completa"
  Uso: "Residencial, pernocta"

Tarjeta 2 — Nivel 2 (AC rapido)
  Badge: "240V / 7-22kW"
  Icono: FaBuilding
  Tiempo: "2-8 horas"
  Uso: "Centros comerciales, oficinas"

Tarjeta 3 — DC Fast Charge
  Badge: "480V / 50-350kW"
  Icono: FaBolt
  Tiempo: "15-45 minutos"
  Uso: "Autopistas, corredores de carga"
  Warning: "Acelera degradacion si es frecuente"
```

## Slide 4 — Smart Grid y V2G
```
Tipo    : DIAGRAMA DE ECOSISTEMA
Titulo  : "Smart Grid: La Red Electrica Inteligente"

Centro del diagrama: "RED ELECTRICA" (circulo grande)
Conectado a:
  FaSolarPanel  → "Generacion Solar"
  FaWind        → "Generacion Eolica"
  FaIndustry    → "Planta Electrica"
  FaCar         → "Vehiculo Electrico (carga)"
  FaCar (flecha bidireccional) → "V2G: Vehiculo como bateria"
  FaHome        → "Hogar / Edificio"
  FaServer      → "Centro de datos"

V2G destacado:
  "Vehicle to Grid — el EV puede vender energia de vuelta a la red"
  "Potencial economico para el propietario del EV"
```

## Slide 5 — Prediccion de Demanda
```
Tipo    : CONTENIDO + GRAFICO
Titulo  : "Predecir Cuando y Cuanto se Cargara"

Chart de linea (izquierda):
  Eje X: Horas del dia (0h-24h)
  Eje Y: Demanda kW
  Serie 1: Demanda real (linea azul)
  Serie 2: Prediccion modelo (linea cyan punteada)
  Zona sombreada entre 18h-22h: "HORA PICO"

Texto derecho:
  Variables predictoras:
    - Hora del dia
    - Dia de la semana / festivo
    - Temperatura ambiente
    - Eventos locales
    - Historial de dias anteriores

  Modelos utiles:
    LSTM para series de tiempo
    Random Forest para clasificacion de demanda
    XGBoost para regresion de kW
```

## Slide 6 — Integracion Renovables
```
Tipo    : COMPARACION CARGA INTELIGENTE VS TRADICIONAL
Titulo  : "Carga con Integracion de Energias Renovables"

Izquierda — Sin IA:
  Todos cargan a las 7pm (hora pico)
  Red estresada, precios altos
  Desperdicio de solar nocturno

Derecha — Con IA:
  Carga desplazada a horas de alta solar
  Menor costo energetico para usuario
  Red balanceada, menos emision CO2
  V2G durante picos de precio

Diagrama: barra de tiempo 24h con zonas de carga optima marcadas
```

## Slide 7 — Algoritmo de Balance Energetico
```
Tipo    : PSEUDO-CODIGO VISUAL
Titulo  : "Logica del Algoritmo de Equilibrio"

Caja de codigo estilizada (fondo 1A1A2E, texto 00D4FF):

MIENTRAS sistema_activo:
  leer(SoC_vehiculo, precio_red, generacion_solar)

  SI generacion_solar > demanda_red:
    activar_carga(EV, potencia=maxima)

  SI SINO precio_red < umbral_bajo:
    activar_carga(EV, potencia=media)

  SI SINO SoC_vehiculo > 90% Y precio_red > umbral_alto:
    activar_V2G(EV, potencia=exportar)

  SINO:
    esperar(intervalo=15_minutos)

Nota: "Este es el esquema logico — en practica se entrena un modelo de RL para encontrar la politica optima"
```

## Slide 8 — Plataformas y Herramientas
```
Tipo    : HERRAMIENTAS
Titulo  : "Herramientas para Simular la Red de Carga"

Grid 2x2:
  OpenDSS     → Simulacion de red de distribucion
  Homer Grid  → Optimizacion de microred con renovables
  MATLAB/Simulink → Modelado de sistemas electricos
  Python + Pandas → Analisis de datos de consumo

Badge: "Practica usa Python + datos simulados en Google Colab"
```

## Slide 9 — Practica
```
Titulo  : "Simulacion de Balance y Algoritmo ML de Equilibrio"

Pasos:
  1. "Cargar dataset: precio de energia, generacion solar, SoC de flota"
  2. "Visualizar curva de demanda diaria con Matplotlib"
  3. "Implementar logica de carga inteligente (reglas if-else)"
  4. "Entrenar modelo de regresion para predecir punto de equilibrio"
  5. "Comparar consumo total: carga tradicional vs carga inteligente"
  6. "Calcular ahorro estimado en kWh y costo"
```

## Slide 10 — Cierre
```
5 checkpoints:
  1. "Existen 3 niveles de carga con diferentes tiempos y potencias"
  2. "Smart Grid permite comunicacion bidireccional con los EV (V2G)"
  3. "La prediccion de demanda optimiza el uso de energia renovable"
  4. "Un algoritmo de equilibrio decide CUANDO y CUANTO cargar"
  5. "La integracion de IA reduce costos y estres en la red electrica"

Siguiente: "Bloque 06 — Logistica y Optimizacion de Rutas"
```

---

## Instrucciones para el Agente

Igual que bloques anteriores. Salida: `Bloque05-Infraestructura-Carga.pptx`
