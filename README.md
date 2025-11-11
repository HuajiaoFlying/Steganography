[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17578068.svg)](https://doi.org/10.5281/zenodo.17578068)
## Runtime Environment
Unity 2022.3 and above

## Algorithm Description
This algorithm is designed to embed secret information, which can be converted into binary data (such as files packaged via AssetBundle, Json files, files in the streamingAssets directory, etc.), into model textures. It enhances the security of data storage without compromising the visual appearance of the textures.

The algorithm employs IWT (Integer Wavelet Transform) frequency domain transformation for the secret information to improve stealthiness and utilizes image edges as the core embedding area to evade detection by steganalysis algorithms. Compared to other algorithms, this method ensures higher security while expanding embedding capacity to meet the demands of embedding large data files in Unity.

## Usage
1. Add the Script folder to your "Unity Project Path/Assets" directory.
2. Call the `Steganography.Embed(byte[] data, Texture2D[] textures, uint seed)` method to embed the binary parameter `data` into the texture parameters `textures`. The `seed` parameter serves as the secret key.
3. Call the `Steganography.Extract(Texture2D[] textures, uint seed)` method to extract the binary secret information from the stego-texture parameters `textures`. The `seed` parameter serves as the secret key.
