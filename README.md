# 🎨✨ RePaint - Diffusion-Based Inpainting

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
  Control jumps (`j`) and resampling (`r`).
## 🏗️ Usage Example

```python
model_id = "path"

model = UNet2DModel.from_pretrained(model_id)
scheduler = DDPMScheduler.from_pretrained(model_id)
model = Model(model).to(device)
scheduler = CustomScheduler.from_DDPMScheduler(scheduler)

original_image = "path"
mask = "path"

# Run RePaint
output = repaint(original_image, mask, model, scheduler)
```
This workflow can be applied not only to the CelebA dataset, but also to any custom dataset where incomplete or masked images need restoration.

## 💡 Tips & Recommendations

- 🚀 **GPU Recommendation:** Use NVIDIA A100 or equivalent for faster processing and to handle larger images.  
- 🎛️ **Parameter Tuning:** Adjust `j` (jumps) and `r` (resampling).

## 📚 References

- 📰 **RePaint Paper:** [https://arxiv.org/abs/2201.09865](https://arxiv.org/abs/2201.09865)
