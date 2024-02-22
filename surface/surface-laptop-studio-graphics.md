---
title: Surface Laptop Studio graphics overview
description: This article highlights GPUs in Surface Laptop Studio. 
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 10/04/2021
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---

# Surface Laptop Studio graphics overview

Surface Laptop Studio integrates fully modernized computing and graphics capabilities into a versatile form factor. Led by the quad-core 11th Gen Intel® Core™ i7 and NVIDIA® RTX™ A2000 or NVIDIA® GeForce RTX™ 3050 Ti, Surface Laptop Studio provides architects, engineers, data scientists, and creative professionals with the power to do their best work.

A significant differentiator across Surface Laptop Studio models is the GPU configuration. All but the Core i5 device feature a discrete NVIDIA RTX GPU, enabling hardware-accelerated ray tracing, AI, and video. The design also optimizes energy efficiency for mobile form factors. The models with NVIDIA GPUs are part of the NVIDIA Studio Products program. This program includes RTX-accelerations in the top creative apps, reliable NVIDIA Studio Drivers, and access to exclusive NVIDIA apps like Canvas or Broadcast. Ray tracing is a computationally intensive technique that simulates the physical behavior of light to achieve greater realism in computer-generated scenes. It's used in gaming and 3D rendering. NVIDIA RTX also features deep learning super sampling (DLSS), an AI technology that boosts frame rates.

These advanced graphics rendering capabilities come in two primary configurations:

- NVIDIA GeForce RTX 3050 Ti Laptop GPU for consumers or creative professionals.
- NVIDIA RTX A2000 Laptop GPU for architects, engineers, creative professionals, and other business professionals who need advanced graphics capabilities.

## Surface Laptop Studio GPUs

This section describes the integrated and discrete GPUs across Surface Laptop Studio models.

### Intel Iris™ Xe Graphics

As the integrated GPU (iGPU) on Surface Laptop Studio, Intel Iris™ Xe Graphics is the singular GPU in the Core i5 model. It supports richer gaming experiences and greater speeds for designers and creators. With advanced graphics capabilities and an AI-enhanced experience, Intel Iris Xe enables consumers, hobbyists, and online creators to run the latest productivity software like Adobe® Creative Cloud or enjoy gaming titles in 1080p. It also increases the number of supported displays from three to four. Now you can use up to three external displays alongside the internal display or four external displays at once--for both integrated GPU and discrete GPU models.[[1]](#references)

### Comparing discrete GPUs

NVIDIA GeForce RTX 30 Series and RTX professional GPUs accelerate games, 3D rendering, video editing, graphic design, AI-accelerated workflows, and other tasks. This is enabled by the NVIDIA Ampere architecture:

- Second generation RT Cores and DLSS, providing up to 2x performance boosts in top renderers, including Blender Cycles, Chaos V-Ray, and Autodesk Arnold.
- Third generation Tensor Cores that accelerate AI features. Tensor Cores also bring AI to graphics with capabilities like DLSS, AI denoising, and enhanced editing for select applications.
- The best-in-class video encoder (NVENC) and hardware acceleration for ray-traced motion blur, a common technique used in production rendering, is now boosted by up to 5x.

### NVIDIA GeForce RTX 3050 Ti Laptop GPU

The GeForce RTX 3050 Ti Laptop GPU is a great GPU for gamers and content creators. It’s powered by the NVIDIA Studio drivers for enhanced reliability and performance in creator apps.

GeForce RTX 3050 Ti enables:

- Video editing and live streaming accelerations, enabled by the dedicated hardware encoder, enhanced AI features, and app accelerations in apps like Adobe Premiere® Pro, DaVinci Resolve® or OBS.
- Graphic design and photography, with AI-accelerated features in apps like Adobe Lightroom® or Photoshop® image editing software.
- Ultra-fast 3D rendering enabled by RTX and DLSS accelerations in apps like Blender™ or Autodesk® Maya.
- Next-generation gaming with RTX graphics and high-performance enabled by DLSS and ultra-low latency with NVIDIA Reflex.

### NVIDIA RTX A2000 Laptop GPU

The NVIDIA RTX A2000 offers professional graphics rendering and AI capabilities. This enables demanding professional workflows, including manufacturing and product design, media and entertainment modeling, animating and rendering, architecture, engineering and construction design.

NVIDIA RTX A2000 builds on the GeForce RTX 3050 Ti features with the following capabilities:

- Enterprise-grade reliability, including ISV certification for professional apps and enterprise drivers tuned for software compatibility and stability.
- Enterprise-level hardware, drivers and support.
- Dedicated IT enterprise tools for remote management that help maximize uptime and minimize IT support requirements.
- Enhanced support for professional applications using Open GL graphics.

**Table 1. Discrete GPUs on Surface Laptop Studio**

| GPU                                         | NVIDIA GeForce RTX 3050 Ti Laptop GPU | NVIDIA RTX A2000 Laptop GPU |
| ------------------------------------------- | ------------------------------------- | --------------------------- |
| GPU memory                                  | 4 GB GDDR6                             | 4 GB GDDR6                   |
| GPU boost clock                             | 1035 Mhz                               | 1207.5 Mhz                   |
| Streaming multiprocessors                   | 2x FP32                               | 2x FP32                     |
| NVIDIA CUDA processing cores                | 2560                                  | 2560                        |
| NVIDIA RT cores                             | Second Gen / 20                          | Second Gen / 20                |
| Tensor cores                                | Third Gen / 80                          | Third Gen / 80                |
| Memory rate                                 | 11 Gbps                               | 11 Gbps                     |
| Memory bandwidth                            | 192 GB/s                              | 192 GB/s                    |
| Memory interface                            | 128 bit                               | 128 bits                    |
| Maximum graphics power (w)                  | 50 watts                              | 50 watts                    |
| DLSS                                        | Yes                                   | Yes                         |
| Dynamic boost 2.0                           | Yes                                   | Yes                         |
| Resizable BAR                               | Yes                                   | Yes                         |
| NVIDIA Optimus                              | Yes                                   | Yes                         |
| Nvidia Encoder                              | Seventh Gen                               | Seventh Gen                     |
| Nvidia Decoder                              | Fifth Gen                               | Fifth Gen                     |
| Tensor performance                          | 42.4 TFLOPS, Peak                     | 49.5 TFLOPS, Peak           |
| Single precision floating point performance | 5.3 TFLOPS, Peak                      | 6.2 TFLOPS, Peak            |
| PCIe generation                             | 4 (Gen3 configured)                   | 4 (Gen3 configured)         |
| Shader model                                | 7.0                                   | 7.0                         |
| Vulkan RT                                   | 1.2                                   | 1.2                         |
| OpenCL                                      | 3.0                                   | 3.0                         |
| OpenGL                                      | 4.6                                   | 4.6                         |
| DirectX                                     | 12 Ultimate                           | 12 Ultimate                 |

### References

1. Subject to the limitations of the display connection. DisplayPort 1.4a over USB-C permits 4K displays up to the following configurations: 1x 4K at 120 Hz; 2x 4K at 60 Hz; 1x 4K at 60 Hz + 2x 4K at 30 Hz; 4x 4K at 30 Hz. Display configurations of more than two displays require display support for daisy-chaining or display adapters with support for multiple displays.
