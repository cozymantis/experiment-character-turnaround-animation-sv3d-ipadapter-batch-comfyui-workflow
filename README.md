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


## Nodes You Need To Install

This workflow depends on a few other great custom nodes that you should install first. The recommended path is to use ComfyUI Manager's "Install missing nodes" feature - see https://github.com/ltdrdata/ComfyUI-Manager.

- Open the ComfyUI Manager Menu
- Click on the "Install Missing Custom Nodes" button
- Restart ComfyUI and refresh the web app

Alternatively, for manual installs, here is the list of required custom nodes and packs:

- Our Cozy Utils pack (https://github.com/cozymantis/cozy-utils-comfyui-nodes)
- Our Cozy Pose Face&Body Generator node (https://cozymantis.gumroad.com/l/cozy-pose-face-body-openpose-generator-comfyui-node-character-reference)
- Impact Pack (https://github.com/ltdrdata/ComfyUI-Impact-Pack)
- IPAdapter Plus (https://github.com/cubiq/ComfyUI_IPAdapter_plus)
  - FaceID requires insightface, you need to install it in your ComfyUI environment. Run `pip install insightface` inside your ComfyUI python env, or try the "Install pip package" options in the ComfyUI Manager menu. Check [this issue](https://github.com/cubiq/ComfyUI_IPAdapter_plus/issues/162) for help.
  - Check the IPAdapter installation instructions in the repo above.
- WAS Node Suite (https://github.com/WASasquatch/was-node-suite-comfyui)
- Image Resize for ComfyUI (https://github.com/palant/image-resize-comfyui)
- ComfyUI's ControlNet Auxiliary Preprocessors (https://github.com/Fannovel16/comfyui_controlnet_aux)
- rgthree (https://github.com/rgthree/rgthree-comfy)
- ComfyUI Essentials (https://github.com/cubiq/ComfyUI_essentials)
- ComfyUI Logic (https://github.com/theUpsider/ComfyUI-Logic)
- FizzNodes (https://github.com/FizzleDorf/ComfyUI_FizzNodes)

## Models You Need, And Where To Put Them

- An SD 1.5 checkpoint of your choice => models/checkpoints
- https://huggingface.co/stabilityai/sv3d/blob/main/sv3d_p.safetensors => models/checkpoints
- https://huggingface.co/Bingsu/adetailer/blob/main/face_yolov8m.pt => models/ultralytics/bbox
- https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth => models/sams
- https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus_sd15.safetensors => models/ipadapter
- https://huggingface.co/webui/ControlNet-modules-safetensors/blob/main/t2iadapter_openpose-fp16.safetensors => models/controlnet
- https://huggingface.co/h94/IP-Adapter/blob/main/models/image_encoder/model.safetensors => models/clip_vision/CLIP-ViT-H-14-laion2B-s32B-b79K.safetensors

## Licenses & Commercial Use

Please check licenses and terms of use for each of the nodes and models required by this workflow.

## Misuse, Malicious Use, and Out-of-Scope Use

The workflow should not be used to intentionally create or disseminate images that create hostile or alienating environments for people. This includes generating images that people would foreseeably find disturbing, distressing, or offensive; or content that propagates historical or current stereotypes.

Made with 💚 by the [CozyMantis](https://cozymantis.gumroad.com/) squad.
