# ComfyUI Experimental Workflow for Character Turnaround Based on SV3D And IPAdapter Batch

**A CozyMantis experiment with the new IPAdapter Batch nodes for driving video**

https://github.com/cozymantis/experiment-character-turnaround-animation-sv3d-ipadapter-batch-comfyui-workflow/assets/5381731/52e8b61e-5d29-4484-9e02-38ff18dafa1e

## Steps

- Generate a 1024x1024 reference image with 2 general passes and a face detailing pass;

![demo1-reference](https://github.com/cozymantis/experiment-character-turnaround-animation-sv3d-ipadapter-batch-comfyui-workflow/assets/5381731/d7b0e0d8-b78b-4f73-ae14-5910180cbd13)

- Run it through [SV3D](https://sv3d.github.io/) to get a 576x576 turnaround;

https://github.com/cozymantis/experiment-character-turnaround-animation-sv3d-ipadapter-batch-comfyui-workflow/assets/5381731/d29a4eee-3e2d-4a7d-be6d-1eadbc0655cd

- Run the frames through the [IPAdapter Tiled Batch](https://github.com/cubiq/ComfyUI_IPAdapter_plus) node;

- Upscale each frame to 1024x1024 using different values for denoise and the batch IPAdapter output models.

**Denoise 0.3**

https://github.com/cozymantis/experiment-character-turnaround-animation-sv3d-ipadapter-batch-comfyui-workflow/assets/5381731/f198a51a-8359-48f0-a9f2-96b0f9604593

**Denoise 0.5**

https://github.com/cozymantis/experiment-character-turnaround-animation-sv3d-ipadapter-batch-comfyui-workflow/assets/5381731/2b1f565e-8f83-4dab-ba3c-1ca704102b16

**Denoise 0.7**

https://github.com/cozymantis/experiment-character-turnaround-animation-sv3d-ipadapter-batch-comfyui-workflow/assets/5381731/61d14752-1f57-482c-8ccc-e3345dc15aa4

**Denoise 0.9**

https://github.com/cozymantis/experiment-character-turnaround-animation-sv3d-ipadapter-batch-comfyui-workflow/assets/5381731/46f50545-4e94-4bc1-aa2d-cf4c471ca3b1
