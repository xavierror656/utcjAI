Datasets Libres por Bloque del Curso
Bloque 01 — Fundamentos de ML
Para la practica de clasificacion/regresion no se necesita un dataset especializado. Hay dos opciones ideales en Kaggle que cualquier alumno puede abrir desde el navegador:

EV Specs Dataset 2025 — kaggle.com/datasets/urvishahir/electric-vehicle-specifications-dataset-2025 — especificaciones de EVs: autonomia, peso, tipo de carga, potencia. Perfecto para clasificacion (tipo de carga) o regresion (prediccion de autonomia).
Full Electric Vehicle Dataset — kaggle.com/datasets/sahirmaharajj/electric-vehicle-population — registro de EVs en Washington State, EE.UU. Variables limpias, ideal para Teachable Machines y primeros modelos.


Bloque 02 — Computer Vision
El KITTI Dataset del Instituto de Tecnologia de Karlsruhe es el benchmark estandar para deteccion de objetos en conduccion autonoma. Incluye 7,481 imagenes etiquetadas con camaras, LiDAR y GPS, con clases como autos, peatones, ciclistas y camiones — directamente compatible con YOLO via Ultralytics. El Udacity Self-Driving Car Dataset en Roboflow contiene 97,942 etiquetas en 15,000 imagenes para 11 clases incluyendo semaforos.

KITTI: cvlibs.net/datasets/kitti (academia, gratuito)
Udacity via Roboflow: public.roboflow.com/object-detection/self-driving-car (descarga directa en formato YOLO)


Bloque 03 — Arquitectura y Chips
Este bloque es mas de analisis/investigacion que de entrenamiento de modelos. Los alumnos buscan fichas tecnicas publicas:

NVIDIA DRIVE Orin specs: developer.nvidia.com/drive
Tesla FSD Chip: documentacion publica en Tesla AI Day (YouTube + whitepapers)
Para el calculo de FLOPS, los datos estan en hojas de especificaciones publicas de cada chip.


Bloque 04 — Gestion de Energia y Baterias
Aqui hay datasets de nivel de investigacion reales y gratuitos:
El NASA Li-ion Battery Aging Dataset del NASA Ames Prognostics Center incluye ciclos completos de carga, descarga e impedancia electroquimica con variables de voltaje, corriente y temperatura — disponible publicamente sin restricciones. El CALCE Battery Dataset de la Universidad de Maryland ofrece acceso abierto a datos experimentales de celdas LCO, LFP y NMC en diferentes perfiles de ciclado, util para estimacion de SoC y SoH.
El LG HG2 Dataset de McMaster University contiene series de tiempo de 5 variables (voltaje, corriente, temperatura, promedio de voltaje y corriente) con SoC como etiqueta, disponible en Mendeley Data en data.mendeley.com/datasets/cp3473x7xv/3.
DatasetVariablesTareaLinkNASA PCoEVoltaje, corriente, temp, capacidadSoC, SoH, RULdata.nasa.govCALCE CS2Ciclos, voltaje, tempSoH, degradacioncalce.umd.edu/battery-dataLG HG2 McMaster5 vars + SoC etiquetaPrediccion SoCdata.mendeley.comNASA en KaggleMismo NASA, mas accesibleSoC/SoH/RULkaggle.com/datasets/patrickfleith/nasa-battery-dataset

Bloque 05 — Infraestructura de Carga Inteligente
El ACN-Data de Caltech es un dataset abierto de sesiones de carga en el trabajo con datos de energia, duracion y comportamiento de usuario — disponible en ev.caltech.edu. El UrbanEV dataset publicado en Scientific Data cubre 20,000 estaciones de carga en Shenzhen durante 6 meses con datos horarios de ocupacion, duracion, volumen y precio, incluyendo condiciones climaticas.
El dataset ST-EVCDP en GitHub (github.com/IntelligentSystemsLab/ST-EVCDP) ofrece datos de 18,061 puntos de carga publica con intervalos de 5 minutos durante 30 dias, junto con datos de clima — ideal para prediccion de demanda con series de tiempo.

Bloque 06 — Logistica y Optimizacion de Rutas

EV Charging Load Dataset and Optimal Routing — kaggle.com/datasets/datasetengineer/ev-charging-load-dataset-and-optimal-routing — incluye datos de carga y escenarios de ruteo.
Para VRP puro: el benchmark clasico es Solomon VRPTW instances (neo.lcc.uma.es/vrp/vrp-instances/) — instancias en texto plano, usadas en toda la literatura academica, listas para Google OR-Tools.


Bloque 07 — Trafico Inteligente y Multiagente
El Urban Traffic Flow Dataset en Kaggle (kaggle.com/datasets/ziya07/urban-traffic-flow-dataset) contiene flujo vehicular urbano por hora, adecuado para modelos predictivos de congestion.
Ademas, SUMO (el simulador recomendado) incluye escenarios de trafico de ciudades reales que pueden generarse como dataset directamente desde la herramienta — sin necesidad de datos externos.

Bloque 08 — Integracion con CARLA
CARLA genera sus propios datos durante la simulacion. Para enriquecer el bloque:

El CARLA dataset generado con EMS3D-KITTI en Zenodo muestra como exportar datos de simulacion en formato KITTI para entrenar modelos.
Los datos de los bloques 02, 04 y 07 se pueden reutilizar aqui como entradas al sistema integrado.


Resumen de Acceso por Facilidad
FacilidadDatasetDondeMuy facil (browser)EV Specs, Udacity Roboflow, NASA KaggleKaggle.comFacil (descarga directa)KITTI, LG HG2 MendeleyLinks directosModerado (registro)CALCE, ACN-DataSitios institucionalesSin descarga necesariaSolomon VRP, SUMO scenariosGenerados localmente
Todo es gratuito para uso educativo y academico. Quieres que actualice el archivo image-guidelines.md del proyecto para agregar los links de datasets directamente en cada bloque?
