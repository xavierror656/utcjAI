# Sistema de Generacion de Material - IA Aplicada a Electromovilidad

## Descripcion

Este repositorio contiene los prompts estructurados para que un agente genere automaticamente los 8 bloques de presentaciones (.pptx) del curso **Inteligencia Artificial Aplicada a la Electromovilidad**.

---

## Estructura del Repositorio

```
curso-ia-electromovilidad/
├── README.md                    ← Este archivo (punto de entrada del agente)
├── config/
│   ├── design-system.md         ← Paleta, tipografia, reglas de diseno globales
│   ├── tech-stack.md            ← Dependencias, setup, comandos de build
│   └── image-guidelines.md      ← Como buscar y usar imagenes de Google
├── scripts/
│   └── build-all.sh             ← Script para generar todos los bloques en secuencia
└── bloques/
    ├── bloque-01-ml-fundamentos.md
    ├── bloque-02-computer-vision.md
    ├── bloque-03-arquitectura-deployment.md
    ├── bloque-04-gestion-energia.md
    ├── bloque-05-infraestructura-carga.md
    ├── bloque-06-logistica-rutas.md
    ├── bloque-07-trafico-multiagente.md
    └── bloque-08-integracion-carla.md
```

---

## Instrucciones para el Agente

### Orden de ejecucion

1. Leer `config/tech-stack.md` e instalar dependencias
2. Leer `config/design-system.md` para aplicar el estilo correcto
3. Leer `config/image-guidelines.md` para obtener imagenes
4. Para cada bloque, leer el `.md` correspondiente y generar el `.pptx`
5. Guardar todos los archivos en `/outputs/pptx/`

### Reglas globales del agente

- Cada bloque genera UN archivo `.pptx` independiente
- Nombre del archivo: `BloquoNN-NombreCorto.pptx` (ej. `Bloque01-ML-Fundamentos.pptx`)
- Minimo 8 diapositivas por bloque, maximo 12
- Siempre incluir: portada, indice, contenido, practica, cierre
- Nunca usar emojis en las diapositivas
- Usar solo iconos de react-icons (FontAwesome o Material Design)
- Cada diapositiva debe tener al menos un elemento visual (imagen, icono, forma, chart)

---

## Resumen de Bloques

| # | Nombre | Duracion | Archivo |
|---|--------|----------|---------|
| 01 | Fundamentos de Machine Learning | 2h | bloque-01-ml-fundamentos.md |
| 02 | Percepcion del Entorno y Computer Vision | 2h | bloque-02-computer-vision.md |
| 03 | Arquitectura de Sistemas y Deployment | 2h | bloque-03-arquitectura-deployment.md |
| 04 | Gestion Inteligente de Energia y Baterias | 2h | bloque-04-gestion-energia.md |
| 05 | Infraestructura de Carga Inteligente | 2h | bloque-05-infraestructura-carga.md |
| 06 | Logistica y Optimizacion de Rutas | 2h | bloque-06-logistica-rutas.md |
| 07 | Trafico Inteligente y Sistemas Multiagente | 2h | bloque-07-trafico-multiagente.md |
| 08 | Integracion Integral con CARLA | 2h | bloque-08-integracion-carla.md |
