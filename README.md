# Local Diffusion

Flutter GUI wrapper for stable-diffusion.cpp - Run Stable Diffusion locally on Android

## Features

- Pure Flutter implementation using FFI bindings to stable-diffusion.cpp
- Android support (more platforms coming soon)
- Super lightweight with minimal dependencies
- Supports multiple model architectures:
    - SD1.x
    - SD2.x
    - SDXL
    - SD3/SD3.5
    - Flux/Flux-schnell
    - SD-Turbo and SDXL-Turbo

- Performance optimizations:
    - OpenBLAS acceleration
    - TAESD for faster decoding (reduces latent decode time from ~48s to ~2s)

- Advanced features:
    - LoRA support
    - On-the-fly model quantization (f16, q8_0, q5_0, q5_1, q4_0, q4_1, q2_k, q3_k, q4_k)
    - Negative prompts
    - Token weighting

- Sampling methods:
    - Euler A
    - Euler
    - Heun
    - DPM2
    - DPM++ 2M
    - DPM++ 2M v2
    - DPM++ 2S a
    - LCM

## Flash Attention Support

When initializing a model, you can choose to load it with or without Flash Attention:
- Without Flash Attention: Uses ~2.7GB RAM, achieves 10.2 it/s
- With Flash Attention: Uses ~2.0GB RAM, achieves 12.2 it/s

These measurements were taken using SD 1.5 fp16 model.

## Roadmap

- [ ] Vulkan backend for GPU acceleration
- [ ] ControlNet support
- [ ] img2img generation
- [ ] RealESRGAN upscaling
- [ ] iOS support

## Building

### Run in release mode
`flutter run --release`

### Release APK

`flutter build apk --release`

The APK will be available at `build/app/outputs/flutter-apk/app-release.apk`

## Credits

Based on [stable-diffusion.cpp](https://github.com/leejet/stable-diffusion.cpp)
