# 基于纹理复杂度的Unity隐写算法

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17578068.svg)](https://doi.org/10.5281/zenodo.17578068)

**注意**：本代码库关联已投稿至 The Visual Computer 期刊的论文。如使用本代码，请引用相关论文。

## 运行环境要求
- Unity 2022.3 或更高版本

## 算法概述

本算法旨在为Unity应用程序提供数据安全存储解决方案，通过将二进制数据文件（包括AssetBundle打包文件、JSON配置文件、StreamingAssets目录下的资源文件等）作为秘密信息嵌入到模型贴图中，在保持贴图视觉质量的同时显著增强数据存储的安全性。

### 核心技术特点：
- **频域加密**：采用整数小波变换(IWT)对秘密信息进行频域处理，提升隐写安全性
- **自适应嵌入**：基于图像边缘复杂度动态调整数据嵌入强度和位置
- **大容量支持**：针对Unity资源文件体积大的特点，优化嵌入容量设计
- **抗检测性**：优先选择纹理复杂区域进行嵌入，有效规避隐写分析检测

## 使用方法

### 安装步骤
1. 将 `Script` 文件夹复制到 `Unity项目路径/Assets` 目录下
2. 在Unity编辑器中重新编译项目

### 核心API
```csharp
// 将二进制数据嵌入到多个纹理中
Steganography.Embed(byte[] data, Texture2D[] textures, uint seed)
