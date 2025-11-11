
## English Version README

```markdown
# Texture Complexity-Based Steganography for Unity Engine

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17578068.svg)](https://doi.org/10.5281/zenodo.17578068)

**Note**: This code repository is directly related to the manuscript submitted to The Visual Computer journal. If you use this code, please cite the relevant manuscript.

## Environment Requirements
- Unity 2022.3 or higher

## Algorithm Description

This algorithm provides a data security storage solution for Unity applications by embedding binary data files (including AssetBundle packages, JSON configuration files, resources in StreamingAssets directory, etc.) as secret information into model textures. It significantly enhances data storage security while preserving the visual quality of textures.

### Key Technical Features:
- **Frequency Domain Encryption**: Utilizes Integer Wavelet Transform (IWT) for frequency domain processing of secret information, improving steganographic security
- **Adaptive Embedding**: Dynamically adjusts data embedding intensity and position based on image edge complexity
- **High Capacity Support**: Optimized embedding capacity to accommodate large Unity resource files
- **Anti-Detection Capability**: Prioritizes texture-complex regions for embedding, effectively evading steganalysis detection

## Usage Instructions

### Installation Steps
1. Copy the `Script` folder to your `UnityProjectPath/Assets` directory
2. Recompile the project in Unity Editor

### Core API
```csharp
// Embed binary data into multiple textures
Steganography.Embed(byte[] data, Texture2D[] textures, uint seed)
