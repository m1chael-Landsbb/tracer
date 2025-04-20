# Collectible Asset Generator 🎨

**Generador de Colecciones de Activos - Crea más de 5000 activos únicos automáticamente**

A powerful Python tool to generate thousands of unique collectible assets by combining different layers (environments, characters, equipment, effects, etc.). Each asset is guaranteed to be unique with its own attributes.

---

## 🌟 Features / Características

- ✅ Generate 5000+ unique assets automatically / Genera más de 5000 activos únicos automáticamente
- ✅ Layer-based system (environments, base, gear, features, etc.) / Sistema de capas (entornos, base, equipamiento, características, etc.)
- ✅ Rarity weights for traits / Pesos de rareza para características
- ✅ Automatic duplicate detection / Detección automática de duplicados
- ✅ JSON attributes generation for each asset / Generación de atributos JSON para cada activo
- ✅ Configurable through JSON file / Configurable mediante archivo JSON
- ✅ PNG output with transparency support / Salida PNG con soporte de transparencia

---

## 📋 Requirements / Requisitos

- Python 3.8 or higher / Python 3.8 o superior
- Pillow (PIL) library / Biblioteca Pillow (PIL)

---

## 🚀 Quick Start / Inicio Rápido

### 1. Install Dependencies / Instalar Dependencias

```bash
pip install -r requirements.txt
```

### 2. Create Example Layers / Crear Capas de Ejemplo

```bash
python create_example_layers.py
```

This will create example layer images in the `layers/` directory to help you get started.

Esto creará imágenes de capas de ejemplo en el directorio `layers/` para ayudarte a comenzar.

### 3. Generate Asset Collection / Generar Colección de Activos

```bash
# Generate 250 assets (for testing)
python generate_assets.py -n 250

# Generate 5000 assets
python generate_assets.py -n 5000

# Generate 25000 assets
python generate_assets.py -n 25000
```

Generated assets will be saved in:
- `output/images/` - PNG images
- `output/attributes/` - JSON attribute files

Los activos generados se guardarán en:
- `output/images/` - Imágenes PNG
- `output/attributes/` - Archivos de atributos JSON

---

## 📁 Project Structure / Estructura del Proyecto

```
asset_generator/
├── generate_assets.py         # Main generator script / Script principal
├── create_example_layers.py   # Create example layers / Crear capas de ejemplo
├── config.json                # Configuration file / Archivo de configuración
├── requirements.txt           # Python dependencies / Dependencias Python
├── layers/                    # Layer images directory / Directorio de capas
│   ├── environment/          # Environment layer / Capa de entorno
│   ├── base/                 # Base/character layer / Capa de base/personaje
│   ├── gear/                 # Gear layer / Capa de equipamiento
│   ├── features/             # Features layer / Capa de características
│   ├── expression/           # Expression layer / Capa de expresión
│   ├── equipment/            # Equipment layer / Capa de equipo
│   └── effects/              # Effects/rare items / Items de efectos/raros
└── output/                    # Generated assets / Activos generados
    ├── images/               # PNG images / Imágenes PNG
    ├── attributes/           # JSON attributes / Atributos JSON
    └── collection.json       # Collection info / Info de colección
```

---

## 🎨 How to Add Your Own Layers / Cómo Agregar Tus Propias Capas

### English Instructions:

1. **Prepare your artwork**: Create PNG images with transparency (1200x1200px recommended)

2. **Organize by layers**: Place images in the appropriate layer folders:
   - `layers/environment/` - Environments (should be opaque)
   - `layers/base/` - Main character/base
   - `layers/gear/` - Gear items
   - `layers/features/` - Feature variations
   - `layers/expression/` - Expression types
   - `layers/equipment/` - Equipment pieces
   - `layers/effects/` - Rare items (auras, particles, etc.)

3. **Name your files with rarity**: 
   - Format: `name_rarity.png`
   - Example: `forest_environment_100.png` (common, weight 100)
   - Example: `legendary_aura_3.png` (rare, weight 3)
   - Higher numbers = more common, lower numbers = more rare

4. **Run the generator**: `python generate_assets.py -n 5000`

---

## ⚙️ Configuration / Configuración

Edit `config.json` to customize your collection:

```json
{
  "collection_name": "My Asset Collection",
  "collection_description": "Description of your collection",
  "output_dir": "output",
  "layers_dir": "layers",
  "image_size": [1200, 1200],
  "layer_order": [
    "environment",
    "base",
    "gear",
    "features",
    "expression",
    "equipment",
    "effects"
  ]
}
```

**Important**: The `layer_order` determines how layers are stacked (first = bottom, last = top).

---

## 💡 Tips for Creating 25,000+ Unique Assets / Consejos para Crear 25,000+ Activos Únicos

### English:
- **Calculate combinations**: If you have 12 environments × 15 bases × 12 gear × 8 features × 8 expressions × 6 equipment = 82,944 possible combinations
- **Use rarity wisely**: Make rare items really rare (weight 3-8) and common items common (weight 85-100)
- **Add variety**: More layers and variants = more unique combinations
- **Test first**: Generate 250 assets first to verify everything looks good
- **Name consistently**: Use descriptive names like `crystal_environment_100.png` not just `1.png`

---

## 📊 Understanding Attributes / Entendiendo los Atributos

Each asset generates a JSON attribute file compatible with Rarible and other marketplaces:

```json
{
  "name": "My Asset Collection #1",
  "description": "Unique asset from collection",
  "image": "1.png",
  "tokenId": 1,
  "attributes": [
    {
      "trait_type": "Environment",
      "value": "Forest"
    },
    {
      "trait_type": "Base",
      "value": "Warrior Red"
    }
  ]
}
```

---

## 🔧 Advanced Usage / Uso Avanzado

### Custom Configuration File / Archivo de Configuración Personalizado

```bash
python generate_assets.py -n 10000 -c my_custom_config.json
```

### Command Line Options / Opciones de Línea de Comandos

```bash
python generate_assets.py --help

Options:
  -n, --number NUM    Number of assets to generate (default: 5000)
  -c, --config PATH   Path to configuration file (default: config.json)
```

---

## 🐛 Troubleshooting / Solución de Problemas

### "No layers found" Error
**English**: Make sure you have created layer directories and added PNG images to them.

### "Not enough unique combinations"
**English**: You need more layer variants. Add more images to your layer folders or reduce the number of assets to generate.

### Images don't look right
**English**: Check the `layer_order` in config.json. Environments should be first, overlays should be last.

---

## 📝 License / Licencia

This project is provided as-is for creating collectible asset series. Feel free to use and modify for your projects.

---

## 🤝 Contributing / Contribuir

Contributions are welcome! Feel free to submit issues or pull requests.

---

## 📧 Support / Soporte

If you have questions or need help, please open an issue on GitHub.

---

**¡Buena suerte creando tu colección de activos! / Good luck creating your asset collection! 🚀**
