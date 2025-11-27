# ULTRAVIOLET-ENGINE

> Un motor de traducción visual: de píxeles a caracteres, de imagen a sintaxis

**Live demo:** [medusahra.github.io/ultraviolet-engine](https://medusahra.github.io/ultraviolet-engine/)

---

## CONCEPTO

Este engine descompone fotografías en su estructura más primitiva: patrones de luz convertidos en caracteres. Cada píxel se analiza mediante su valor de luminancia (0-255) y se mapea a un glyph específico dentro de un charset seleccionado. El resultado es una arqueología del píxel: la imagen reconstruida como texto, como código, como algo que se puede leer y ejecutar.

---

## PROCESO DE CONVERSIÓN

### 01. CAPTURA
La imagen se carga en Canvas API. Cada píxel se extrae como data RGB (red, green, blue).

### 02. ANÁLISIS
Se calcula brightness mediante fórmula de luminancia:
```
brightness = 0.299 × R + 0.587 × G + 0.114 × B
```

### 03. MAPEO
Cada valor de brightness (0-255) se mapea a un carácter del charset seleccionado:
- Valores altos → caracteres densos (`█`, `@`, `#`)
- Valores bajos → caracteres ligeros (`.`, `·`, ` `)

### 04. RENDER
Output en dos modos:
- **Monocromo:** Texto puro con colores uniformes
- **Color:** Preserva RGB original de cada píxel

---

## FEATURES

- 🎨 **Dual mode:** Color y monocromo
- 📝 **20+ character sets:** Hiragana, blocks, braille, ASCII, símbolos
- 🔍 **Dynamic sizing:** Small (60), Medium (150), Large (300 chars)
- 🖼️ **Export:** PNG (imagen rasterizada) o TXT (texto plano)
- 🔎 **Zoom:** Hasta 8× para exploración detallada
- 🎯 **Aspect ratio preservation:** Cálculo dinámico según charset

---

## STACK TÉCNICO

| Componente | Tecnología |
|------------|-----------|
| Frontend | React 18 + Vite 6 |
| Processing | Canvas API (getImageData) |
| Algoritmo | Brightness-to-character mapping |
| Charsets | Unicode, ASCII, Hiragana, Braille |
| Performance | Real-time (<1s para 150 chars) |
| Deploy | GitHub Pages (CI/CD automático) |

---

## USO

### Ejecución local

```bash
npm install
npm run dev
```

### Build para producción

```bash
npm run build
```

### Deploy a GitHub Pages

```bash
npm run deploy
```

---

## GUÍA DE OPERACIÓN

### INPUT
Drag & drop cualquier imagen (JPG/PNG/GIF). Acepta hasta 5MB.

### CHARSET
- **Hiragana:** Espaciado uniforme óptimo (aspect ratio 0.9)
- **Blocks:** Alta densidad visual (aspect ratio 0.5)
- **Braille:** Textura sutil, minimalista
- **ASCII:** Clásico, compatible universal

### RESOLUTION
Ajusta densidad entre 60-300 caracteres de ancho:
- **Small (60):** Rápido, estilo pixel art
- **Medium (150):** Balance detalle/performance
- **Large (300):** Máximo detalle

### COLOR MODE
- **Color:** Preserva RGB original de cada píxel
- **Monochrome:** Solo luminancia, estética ultraviolet

### EXPORT
- **PNG:** Imagen rasterizada del ASCII art
- **TXT:** Texto plano editable, portable

---

## APLICACIONES

→ **Glitch art:** Genera texturas ASCII para composiciones visuales experimentales

→ **Data visualization:** Representa imágenes como data legible, editable como texto

→ **Compresión estética:** Reduce imágenes a su estructura esencial de luminancia

→ **Creative coding:** Output exportable como input para otros procesos generativos

---

## NOTA TÉCNICA

El aspect ratio se ajusta dinámicamente según el charset seleccionado. Caracteres monospace estándar usan ratio 0.55, mientras que glyphs japoneses (hiragana) requieren 0.9 para mantener proporciones correctas. El engine calcula font-size y line-height en tiempo real para evitar cropping y garantizar que el output visual coincida con las dimensiones originales de la imagen.

---

## CRÉDITOS

**Programado por:** [medusahra](https://github.com/medusahra)

**Links:**
- X: [@medusahra](https://x.com/medusahra)
- GitHub: [github.com/medusahra](https://github.com/medusahra)
- Portfolio: [medusahra.github.io](https://medusahra.github.io)

---

## LICENCIA

MIT License - Libre para uso, modificación y distribución.

---

*// ULTRAVIOLET-ENGINE v1.0 · MOTOR DE TRADUCCIÓN VISUAL · PÍXEL → CARÁCTER //*
