[![Zero-Shot Image Editing](https://img.shields.io/badge/zero%20shot-image%20editing-Green)]([https://github.com/topics/video-editing](https://github.com/topics/text-guided-image-editing))
[![Python](https://img.shields.io/badge/python-3.8+-blue?python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org/downloads/release/python-38/)
![PyTorch](https://img.shields.io/badge/torch-2.0.0-red?PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)

# FlowEdit

[Project](https://matankleiner.github.io/flowedit/) | [Arxiv](https://arxiv.org/abs/2412.08629) | [Proceedings](https://openaccess.thecvf.com/content/ICCV2025/html/Kulikov_FlowEdit_Inversion-Free_Text-Based_Editing_Using_Pre-Trained_Flow_Models_ICCV_2025_paper.html) | [Demo](https://huggingface.co/spaces/fallenshock/FlowEdit) | [ComfyUI](#comfyui-implementation-for-different-models) | [Data](https://github.com/fallenshock/FlowEdit/tree/main/Data)

### [ICCV 2025 Best Student Paper] Official Pytorch implementation of the paper: "FlowEdit: Inversion-Free Text-Based Editing Using Pre-Trained Flow Models"

![](imgs/teaser.png)

## Installation
1. Clone the repository

2. Install the required dependencies using `pip install torch diffusers transformers accelerate sentencepiece protobuf` <br>
	* New version of diffusers may have compatibility issues, try install `diffusers==0.30.1`
 	* Tested with CUDA version 12.4 and diffusers 0.30.0

## Running examples
Run editing with Stable Diffusion 3: `python run_script.py --exp_yaml SD3_exp.yaml`

Run editing with Flux: `python run_script.py --exp_yaml FLUX_exp.yaml`

## Usage - your own examples

* Upload images to `example_images` folder. 

* Create an edits file that specifies: (a) a path to the input image, (b) a source prompt, (c) target prompts, and (d) target codes. The target codes summarize the changes between the source and target prompts and will appear in the output filename. <br>
See `edits.yaml` for example.

* Create an experiment file containing the hyperparamaters needed for running FlowEdit, such as `n_max`, `n_min`. This file also includes the path to the `edits.yaml` file<br>
See `FLUX_exp.yaml` for FLUX usage example and `SD3_exp.yaml` for Stable Diffusion 3 usage example. <br>
For a detailed discussion on the impact of different hyperparameters and the values we used, please refer to our paper.

Run `python run_script.py --exp_yaml <path to your experiment yaml>`

## ComfyUI implementation for different models 

* [FLUX](https://github.com/logtd/ComfyUI-Fluxtapoz)
* [HunyuanLoom](https://github.com/logtd/ComfyUI-HunyuanLoom)

Implemented by [logtd](https://x.com/logtdx/status/1869095838016012462?s=48&t=6Yj6BZKooDOmH_JWRWjtHg)

LTX-Video ComfyUI implementation can be found in LTX-Video [official repository](https://github.com/Lightricks/ComfyUI-LTXVideo/tree/master?tab=readme-ov-file#flow-edit).

## License
This project is licensed under the [MIT License](LICENSE).


### Citation
If you use this code for your research, please cite our paper:

```
@inproceedings{kulikov2025flowedit,
  title={Flowedit: Inversion-free text-based editing using pre-trained flow models},
  author={Kulikov, Vladimir and Kleiner, Matan and Huberman-Spiegelglas, Inbar and Michaeli, Tomer},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision},
  pages={19721--19730},
  year={2025}
}
```
