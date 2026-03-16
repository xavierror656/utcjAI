# Bloque 01 — Fundamentos de Machine Learning en Electromovilidad

## Metadatos

```
Archivo de salida : Bloque01-ML-Fundamentos.pptx
Duracion          : 2 horas (1h teoria + 1h practica)
Icono principal   : FaBrain (react-icons/fa)
Color de acento   : 00D4FF
Total de slides   : 10
```

---

## Slide 1 — Portada

```
Tipo              : PORTADA (fondo oscuro)
Fondo             : 0D1B2A
Barra izquierda   : rectangulo x=0, y=0, w=0.15, h=5.625, color 00D4FF
Icono             : FaBrain, color 00D4FF, 1.2"x1.2", centrado en x=4.4, y=0.6
Texto superior    : "BLOQUE 01" — Calibri 13pt, MUTED (64748B), centrado x=1, w=8, y=1.95
Titulo            : "Fundamentos de Machine Learning" — Calibri Bold 36pt, 00D4FF, centrado x=1, w=8, y=2.3
Subtitulo         : "Aplicado a la Electromovilidad" — Calibri 18pt, E8F4FD, centrado x=1, w=8, y=3.0
Duracion          : "2 horas  |  Teoria + Practica" — Calibri 12pt, 64748B, x=7.5, y=5.1, w=2.3
Imagen            : auto electrico en calle oscura — x=0.2, y=3.7, w=9.6, h=1.6, transparency=70
```

---

## Slide 2 — Indice del Bloque

```
Tipo              : AGENDA (fondo claro)
Fondo             : F0F4F8
Barra superior    : rectangulo x=0, y=0, w=10, h=0.75, color 1B4F72
Titulo en barra   : "Contenido del Bloque" — Calibri Bold 22pt, E8F4FD, x=0.5, y=0.18
Items (6 temas)   : layout 2 columnas, icono circulo + texto

Columna izquierda (x=0.5):
  - Circulo ACCENT + FaLayerGroup  → "Tipos de Aprendizaje"
  - Circulo ACCENT + FaTable       → "Conceptos Clave: Dataset y Variables"
  - Circulo ACCENT + FaChartLine   → "Metricas de Evaluacion"

Columna derecha (x=5.2):
  - Circulo ACCENT + FaCogs        → "Overfitting y Validacion"
  - Circulo ACCENT + FaLaptopCode  → "Herramientas: Google Colab"
  - Circulo WARNING + FaFlask      → "Practica: Teachable Machines"

Cada item: texto Calibri 15pt, TEXT_DARK, alineado izq, y separado 0.65" entre si
```

---

## Slide 3 — Tipos de Aprendizaje (Teoria)

```
Tipo              : CONTENIDO 3 COLUMNAS
Fondo             : F0F4F8
Barra superior    : 1B4F72, h=0.75
Titulo en barra   : "Tipos de Aprendizaje en Machine Learning"

Layout: 3 tarjetas lado a lado (w=2.8 cada una, y=1.0, h=3.8)

Tarjeta 1 — Supervisado
  Fondo tarjeta   : FFFFFF, sombra suave
  Icono           : FaChalkboardTeacher, color 00D4FF, 0.7"x0.7"
  Titulo          : "Supervisado" — Calibri Bold 16pt, 1A1A2E
  Subtexto        : "Aprende con datos etiquetados"
  Ejemplos        : "Clasificacion de fallas\nPrediccion de consumo"
  Badge           : "ETIQUETADO" — rectangulo 00D4FF, texto negro 10pt

Tarjeta 2 — No Supervisado
  Icono           : FaSearchPlus, color 10B981
  Titulo          : "No Supervisado"
  Subtexto        : "Encuentra patrones sin etiquetas"
  Ejemplos        : "Agrupacion de patrones\nDeteccion de anomalias"
  Badge           : "SIN ETIQUETAS" — rectangulo 10B981, texto negro

Tarjeta 3 — Refuerzo
  Icono           : FaGamepad, color F59E0B
  Titulo          : "Por Refuerzo"
  Subtexto        : "Aprende por recompensas"
  Ejemplos        : "Control de semaforos\nConduccion autonoma"
  Badge           : "RECOMPENSA" — rectangulo F59E0B, texto negro

Imagen lateral inferior: grafica de entrenamiento, x=0.3, y=4.2, w=9.4, h=1.0, transparency=60
```

---

## Slide 4 — Problemas en ML (Clasificacion, Regresion, Optimizacion)

```
Tipo              : CONTENIDO CON IMAGEN LATERAL
Fondo             : FFFFFF
Barra superior    : 1B4F72, h=0.75
Titulo en barra   : "Tipos de Problemas en ML"

Layout: texto izq (x=0.5, w=5.5) + imagen der (x=6.2, w=3.5, h=4.0)

Bloque izquierdo — 3 items con icono y descripcion:

Item 1 — Clasificacion
  Icono         : FaTag, circulo 00D4FF
  Titulo        : "Clasificacion" Calibri Bold 16pt
  Texto         : "El modelo predice una categoria\nEjemplo: falla / normal en celda"

Item 2 — Regresion
  Icono         : FaChartLine, circulo 10B981
  Titulo        : "Regresion"
  Texto         : "El modelo predice un valor numerico\nEjemplo: autonomia restante en km"

Item 3 — Optimizacion
  Icono         : FaSlidersH, circulo F59E0B
  Titulo        : "Optimizacion"
  Texto         : "El modelo encuentra la mejor solucion\nEjemplo: ruta optima con menos energia"

Imagen derecha  : dashboard / grafica de datos, Unsplash foto analitica
```

---

## Slide 5 — Dataset, Variables y Etiquetas

```
Tipo              : CONTENIDO DIAGRAMA HORIZONTAL
Fondo             : 0D1B2A
Barra superior    : ninguna (fondo ya oscuro)
Titulo            : "Anatomia de un Dataset" — Calibri Bold 28pt, 00D4FF, x=0.5, y=0.3

Diagrama de flujo horizontal (3 cajas con flechas):

Caja 1 — "Variables de Entrada (Features)"
  x=0.4, y=1.1, w=2.8, h=3.2, fondo 1B4F72
  Icono FaTable color 00D4FF
  Lista: temperatura, velocidad, carga bateria, km recorridos

Flecha → color 00D4FF

Caja 2 — "Modelo ML"
  x=3.6, y=1.1, w=2.8, h=3.2, fondo 00D4FF (mas brillante)
  Icono FaBrain color 0D1B2A
  Texto: "Aprende patrones entre entrada y salida"

Flecha → color 00D4FF

Caja 3 — "Variable de Salida (Etiqueta)"
  x=6.8, y=1.1, w=2.8, h=3.2, fondo 1B4F72
  Icono FaTag color 00D4FF
  Lista: falla/normal, autonomia_km, ruta_optima

Nota inferior     : "Calibri 12pt, E8F4FD: En electromovilidad los datos provienen de sensores, BMS, GPS y CAN Bus"
```

---

## Slide 6 — Overfitting y Validacion

```
Tipo              : CONTENIDO CON DIAGRAMA
Fondo             : F0F4F8
Barra superior    : 1B4F72, h=0.75
Titulo en barra   : "Overfitting, Validacion y Particion de Datos"

Diagrama: barra horizontal dividida en 3 segmentos (x=0.5, y=1.0, w=9, h=0.8)
  Segmento 1 : w proporcional al 70%, color 1B4F72, texto "ENTRENAMIENTO 70%"
  Segmento 2 : w proporcional al 15%, color 00D4FF, texto "VALIDACION 15%"
  Segmento 3 : w proporcional al 15%, color 10B981, texto "PRUEBA 15%"

Seccion izquierda (y=2.2, w=4.5):
  Titulo          : "Underfitting" — FaArrowDown, texto rojo
  Descripcion     : "El modelo es demasiado simple\nno aprende los patrones reales"
  Titulo          : "Overfitting" — FaArrowUp, texto naranja
  Descripcion     : "El modelo memoriza el entrenamiento\nfalla con datos nuevos"

Seccion derecha (y=2.2, x=5.2, w=4.5):
  Titulo          : "Balance Optimo" — FaCheckCircle, texto verde
  Descripcion     : "Generaliza bien en datos nuevos\nEsto es lo que buscamos"
  Nota tip        : caja con borde amarillo (F59E0B):
                    "En EV: un modelo sobreajustado podria\npredecir mal autonomia en condiciones reales"
```

---

## Slide 7 — Metricas de Evaluacion

```
Tipo              : GRID 2x2 DE TARJETAS
Fondo             : 0D1B2A
Titulo            : "Metricas de Evaluacion" — Calibri Bold 28pt, 00D4FF, y=0.2

Grid 2x2 (cada tarjeta w=4.3, h=2.1):

Tarjeta TL (x=0.4, y=0.9) — Accuracy
  Fondo: 1B4F72
  Icono: FaBullseye, 00D4FF
  Nombre: "Accuracy" Bold 16pt, E8F4FD
  Formula: "(VP + VN) / Total" — Calibri 13pt, 00D4FF
  Uso: "Clasificacion balanceada"

Tarjeta TR (x=5.3, y=0.9) — Precision & Recall
  Fondo: 1B4F72
  Icono: FaBalanceScale, 00D4FF
  Nombre: "Precision / Recall"
  Descripcion: "Precision: de los que predije positivo, cuantos lo eran\nRecall: de los positivos reales, cuantos detecte"

Tarjeta BL (x=0.4, y=3.2) — RMSE
  Fondo: 1B4F72
  Icono: FaRulerCombined, 10B981
  Nombre: "RMSE"
  Formula: "Raiz del error cuadratico medio"
  Uso: "Modelos de regresion (SoC, autonomia)"

Tarjeta BR (x=5.3, y=3.2) — Cuando usar cada una
  Fondo: 243B55 (azul intermedio)
  Icono: FaLightbulb, F59E0B
  Nombre: "Guia de Seleccion"
  Texto: "Clasificacion → Accuracy + Precision\nRegresion → RMSE + MAE\nDeteccion → Precision + Recall"
```

---

## Slide 8 — Google Colab y Teachable Machines

```
Tipo              : HERRAMIENTAS (fondo oscuro)
Fondo             : 1B4F72
Badge superior    : rectangulo 00D4FF, x=0.5, y=0.25, w=2, h=0.4
                    Texto "HERRAMIENTAS" — Calibri Bold 12pt, 0D1B2A
Titulo            : "Entorno de Practica" — Calibri Bold 28pt, E8F4FD, y=0.85

Layout 2 columnas:

Columna izq — Google Colab (x=0.5, y=1.6, w=4.2, h=3.4)
  Tarjeta fondo FFFFFF:
  Logo/Icono  : FaGoogle o FaCode, color naranja (F4722A)
  Nombre      : "Google Colab" Bold 18pt, 1A1A2E
  Lista:
    - Entorno Python en la nube
    - GPUs gratuitas disponibles
    - Librerias ML preinstaladas
    - Colaboracion en tiempo real
  URL badge   : "colab.research.google.com"

Columna der — Teachable Machines (x=5.3, y=1.6, w=4.2, h=3.4)
  Tarjeta fondo FFFFFF:
  Icono       : FaRobot, color 10B981
  Nombre      : "Teachable Machines" Bold 18pt, 1A1A2E
  Lista:
    - ML visual sin codigo
    - Clasificacion de imagenes
    - Modelos exportables
    - Ideal para primer acercamiento
  URL badge   : "teachablemachine.withgoogle.com"

Nota inferior: "Calibri 13pt, E8F4FD: Ambas plataformas son gratuitas y funcionan desde el navegador"
```

---

## Slide 9 — Practica del Bloque

```
Tipo              : PRACTICA
Fondo             : 0D1B2A
Badge superior    : rectangulo 00D4FF, texto "PRACTICA — BLOQUE 01"
Titulo            : "Entrenamiento No-Code y Analisis de Metricas" — Calibri Bold 26pt, 00D4FF

Pasos numerados (y desde 1.5, separacion 0.7" por paso):

Paso 1 — Badge circulo "1" + FaDownload
  "Acceder a Google Teachable Machines en el navegador"

Paso 2 — Badge circulo "2" + FaImage
  "Cargar imagenes de autos electricos vs combustion (15-20 por clase)"

Paso 3 — Badge circulo "3" + FaBrain
  "Entrenar el modelo clasificador con los datos subidos"

Paso 4 — Badge circulo "4" + FaChartBar
  "Evaluar Accuracy, Precision y Recall en el panel de metricas"

Paso 5 — Badge circulo "5" + FaFileExport
  "Exportar modelo y discutir resultados en grupo"

Herramientas (barra inferior, y=4.9):
  Caja fondo 1B4F72: "Google Teachable Machines"
  Caja fondo 1B4F72: "Google Colab (cuaderno de analisis)"
```

---

## Slide 10 — Cierre y Puntos Clave

```
Tipo              : CIERRE
Fondo             : 0D1B2A
Barra izquierda   : 00D4FF, w=0.15, full height
Titulo            : "Puntos Clave del Bloque 01" — Calibri Bold 28pt, 00D4FF, x=0.6, y=0.3

Lista 5 puntos (icono FaCheckCircle verde 10B981 + texto):
  1. "Existen 3 paradigmas de ML: supervisado, no supervisado y refuerzo"
  2. "Los problemas en electromovilidad son clasificacion, regresion y optimizacion"
  3. "Un dataset tiene features (entrada) y etiquetas (salida)"
  4. "El overfitting ocurre cuando el modelo memoriza en lugar de generalizar"
  5. "Las metricas nos dicen que tan bien generaliza nuestro modelo"

Separador horizontal: linea 1B4F72, y=4.5

Proximo bloque (y=4.7):
  Texto gris      : "Siguiente:"
  Texto acento    : "Bloque 02 — Percepcion del Entorno y Computer Vision"
  Icono           : FaArrowRight, 00D4FF

Imagen de fondo  : auto electrico, x=6, y=1.5, w=3.8, h=2.8, transparency=75
```

---

## Instrucciones de Generacion para el Agente

1. Leer `config/design-system.md` para colores y tipografia
2. Leer `config/image-guidelines.md` — usar imagenes de Bloque 01
3. Instalar dependencias: `npm install -g pptxgenjs react-icons react react-dom sharp`
4. Generar `build/scripts/bloque-01.js` implementando todas las slides descritas arriba
5. Ejecutar: `node build/scripts/bloque-01.js`
6. Verificar: `python -m markitdown build/output/Bloque01-ML-Fundamentos.pptx`
7. QA visual: convertir a imagenes e inspeccionar
8. Copiar a `/mnt/user-data/outputs/Bloque01-ML-Fundamentos.pptx`
