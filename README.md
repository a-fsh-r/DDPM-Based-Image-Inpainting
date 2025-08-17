# 🎨✨ RePaint Diffusion Inpainting

In this project, **incomplete images** from the **CelebA dataset** are transformed into fully reconstructed masterpieces using **Diffusion-Based Inpainting (DDPM)** 🖌️. Inspired by the [RePaint paper](https://arxiv.org/abs/2201.09865) 📰.

## 🚀 Features

- 🖼️ **Diffusion-Based Image Inpainting**  
  Restore missing regions while keeping known areas intact.  

- 🔄 **Smart Forward & Reverse Diffusion**  
  Utilize stochastic forward jumps and reverse steps to achieve realistic reconstruction.  

- 🛡️ **Mask Preservation**  
  Protect existing content with a flexible mask system for precise control.  

- ⚡ **Custom Scheduler Support**  
  Easily swap between standard DDPM schedules or your own custom diffusion schedules.  

- 🎛️ **Parameter Tuning**  
  Control jumps (`j`) and repetitions (`r`) for different resampling behaviors and artistic effects.

## 🏗️ Usage Example

```python
from repaint import repaint, Model, CustomScheduler
import torch

# Load model and scheduler
model = Model(pretrained_model).to(device)
scheduler = CustomScheduler.from_DDPMScheduler(pretrained_scheduler)

# Run RePaint
output = repaint(original_image, mask, model, scheduler)
```

## 💡 Tips & Recommendations

- 🚀 **GPU Recommendation:** Use NVIDIA A100 or equivalent for faster processing and to handle larger images.  
- 🎛️ **Parameter Tuning:** Adjust `j` (jumps) and `r` (repetitions) to control stochastic forward steps and achieve different artistic effects.  
- 🖌️ **Mask Combinations:** Combine multiple masks for selective inpainting of complex images.

## 📚 References

- 📰 **RePaint Paper:** [https://arxiv.org/abs/2201.09865](https://arxiv.org/abs/2201.09865)
