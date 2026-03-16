# Tech Stack y Setup

## Dependencias Requeridas

```bash
# Node.js (requerido v16+)
node --version

# PptxGenJS - generacion de PowerPoint
npm install -g pptxgenjs

# React Icons - iconos vectoriales
npm install -g react-icons react react-dom

# Sharp - rasterizacion de SVG a PNG para iconos
npm install -g sharp

# MarkItDown - verificacion de contenido generado
pip install "markitdown[pptx]" --break-system-packages

# Poppler - conversion a imagenes para QA visual
# Ubuntu/Debian:
apt-get install -y poppler-utils

# LibreOffice - para conversion PDF (QA visual)
# Ya instalado en entorno Claude
```

## Verificacion de Instalacion

```bash
node -e "require('pptxgenjs'); console.log('pptxgenjs OK')"
node -e "require('react-icons/fa'); console.log('react-icons OK')"
node -e "require('sharp'); console.log('sharp OK')"
python -m markitdown --help | head -1
```

## Estructura de Archivos de Trabajo

```
/home/claude/
├── curso-ia-electromovilidad/     ← Prompts y config (read-only para el agente)
└── build/
    ├── scripts/                   ← Scripts .js generados
    │   ├── bloque-01.js
    │   ├── bloque-02.js
    │   └── ...
    ├── images/                    ← Imagenes descargadas temporalmente
    └── output/                    ← PPTXs generados
        ├── Bloque01-ML-Fundamentos.pptx
        └── ...
```

## Workflow del Agente por Bloque

```
1. Leer el .md del bloque
2. Identificar imagenes necesarias (ver image-guidelines.md)
3. Descargar imagenes con curl o fetch
4. Generar script Node.js con PptxGenJS
5. Ejecutar: node build/scripts/bloque-NN.js
6. Verificar con: python -m markitdown output/BloqueNN-*.pptx
7. Convertir a imagenes para QA visual:
      soffice --headless --convert-to pdf output/BloqueNN-*.pptx
      pdftoppm -jpeg -r 150 BloqueNN-*.pdf slide
8. Revisar imagenes visualmente
9. Copiar a /mnt/user-data/outputs/
```

## Comandos de Build

```bash
# Un solo bloque
node build/scripts/bloque-01.js

# Todos los bloques en secuencia
bash curso-ia-electromovilidad/scripts/build-all.sh

# QA rapido de texto
python -m markitdown build/output/Bloque01-*.pptx | head -50

# Conversion a imagenes para inspeccion
cd build/output
python scripts/office/soffice.py --headless --convert-to pdf Bloque01-*.pptx
pdftoppm -jpeg -r 150 Bloque01-*.pdf slide
ls -1 "$PWD"/slide-*.jpg
```

## Notas Importantes

- NUNCA usar "#" en colores de PptxGenJS — causa corrupcion del archivo
- SIEMPRE crear objeto shadow fresco en cada llamada (no reutilizar referencias)
- NUNCA usar localStorage ni APIs de browser en artifacts
- Las imagenes de URL externas funcionan directamente en `slide.addImage({ path: URL })`
- Si una URL de imagen falla, usar un rectangulo de color como placeholder
- Guardar siempre en `/mnt/user-data/outputs/` al final
