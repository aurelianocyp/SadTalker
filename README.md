
| <video  src="https://user-images.githubusercontent.com/48216707/229484996-5d7be64f-2553-4c9e-a452-c5cf0b8ebafe.mp4" type="video/mp4"> </video> | <video  src="https://user-images.githubusercontent.com/4397546/230717873-355b7bf3-d3de-49f9-a439-9220e623fce7.mp4" type="video/mp4"> </video>  | <img src='./examples/source_image/full_body_2.png' width='380'> 

- Several new modes (Still, reference, and resize modes) are now available!

- We're happy to see more community demos on [bilibili](https://search.bilibili.com/all?keyword=sadtalker), [YouTube](https://www.youtube.com/results?search_query=sadtalker) and [X (#sadtalker)](https://twitter.com/search?q=%23sadtalker&src).

## Changelog 

The previous changelog can be found [here](docs/changlelog.md).

- __[2023.06.12]__: Added more new features in WebUI extension, see the discussion [here](https://github.com/OpenTalker/SadTalker/discussions/386).

- __[2023.06.05]__: Released a new 512x512px (beta) face model. Fixed some bugs and improve the performance.

- __[2023.04.15]__: Added a WebUI Colab notebook by [@camenduru](https://github.com/camenduru/): [![sd webui-colab](https://img.shields.io/badge/Automatic1111-Colab-green)](https://colab.research.google.com/github/camenduru/stable-diffusion-webui-colab/blob/main/video/stable/stable_diffusion_1_5_video_webui_colab.ipynb)

- __[2023.04.12]__: Added a more detailed WebUI installation document and fixed a problem when reinstalling.

- __[2023.04.12]__: Fixed the WebUI safe issues becasue of 3rd-party packages, and optimized the output path in `sd-webui-extension`.

- __[2023.04.08]__: In v0.0.2, we added a logo watermark to the generated video to prevent abuse. _This watermark has since been removed in a later release._

- __[2023.04.08]__: In v0.0.2, we added features for full image animation and a link to download checkpoints from Baidu. We also optimized the enhancer logic.

## To-Do

We're tracking new updates in [issue #280](https://github.com/OpenTalker/SadTalker/issues/280).

## Troubleshooting

If you have any problems, please read our [FAQs](docs/FAQ.md) before opening an issue.



## 1. Installation.

Community tutorials: [中文Windows教程 (Chinese Windows tutorial)](https://www.bilibili.com/video/BV1Dc411W7V6/) | [日本語コース (Japanese tutorial)](https://br-d.fanbox.cc/posts/5685086).

### Linux/Unix

1. Install [Anaconda](https://www.anaconda.com/), Python and `git`.

2. Creating the env and install the requirements.
  ```bash
  git clone https://github.com/aurelianocyp/SadTalker

  cd SadTalker 

  conda create -n sadtalker python=3.8

  conda activate sadtalker

  pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 torchaudio==0.12.1 --extra-index-url https://download.pytorch.org/whl/cu113

  conda install ffmpeg

  pip install -r requirements.txt

  ### Coqui TTS is optional for gradio demo. 
  ### pip install TTS

  ```  
### Windows

A video tutorial in chinese is available [here](https://www.bilibili.com/video/BV1Dc411W7V6/). You can also follow the following instructions:

1. Install [Python 3.8](https://www.python.org/downloads/windows/) and check "Add Python to PATH".
2. Install [git](https://git-scm.com/download/win) manually or using [Scoop](https://scoop.sh/): `scoop install git`.
3. Install `ffmpeg`, following [this tutorial](https://www.wikihow.com/Install-FFmpeg-on-Windows) or using [scoop](https://scoop.sh/): `scoop install ffmpeg`.
4. Download the SadTalker repository by running `git clone https://github.com/Winfredy/SadTalker.git`.
5. Download the checkpoints and gfpgan models in the [downloads section](#2-download-models).
6. Run `start.bat` from Windows Explorer as normal, non-administrator, user, and a Gradio-powered WebUI demo will be started.

### macOS

A tutorial on installing SadTalker on macOS can be found [here](docs/install.md).

### Docker, WSL, etc

Please check out additional tutorials [here](docs/install.md).

## 2. Download Models

You can run the following script on Linux/macOS to automatically download all the models:

```bash
bash scripts/download_models.sh
```

We also provide an offline patch (`gfpgan/`), so no model will be downloaded when generating.

### Pre-Trained Models

* [Google Drive](https://drive.google.com/file/d/1gwWh45pF7aelNP_P78uDJL8Sycep-K7j/view?usp=sharing)
* [GitHub Releases](https://github.com/OpenTalker/SadTalker/releases)
* [Baidu (百度云盘)](https://pan.baidu.com/s/1kb1BCPaLOWX1JJb9Czbn6w?pwd=sadt) (Password: `sadt`)

<!-- TODO add Hugging Face links -->

### GFPGAN Offline Patch

* [Google Drive](https://drive.google.com/file/d/19AIBsmfcHW6BRJmeqSFlG5fL445Xmsyi?usp=sharing)
* [GitHub Releases](https://github.com/OpenTalker/SadTalker/releases)
* [Baidu (百度云盘)](https://pan.baidu.com/s/1P4fRgk9gaSutZnn8YW034Q?pwd=sadt) (Password: `sadt`)

<!-- TODO add Hugging Face links -->


<details><summary>Model Details</summary>


Model explains:

##### New version 
| Model | Description
| :--- | :----------
|checkpoints/mapping_00229-model.pth.tar | Pre-trained MappingNet in Sadtalker.
|checkpoints/mapping_00109-model.pth.tar | Pre-trained MappingNet in Sadtalker.
|checkpoints/SadTalker_V0.0.2_256.safetensors | packaged sadtalker checkpoints of old version, 256 face render).
|checkpoints/SadTalker_V0.0.2_512.safetensors | packaged sadtalker checkpoints of old version, 512 face render).
|gfpgan/weights | Face detection and enhanced models used in `facexlib` and `gfpgan`.
  
  
##### Old version
| Model | Description
| :--- | :----------
|checkpoints/auido2exp_00300-model.pth | Pre-trained ExpNet in Sadtalker.
|checkpoints/auido2pose_00140-model.pth | Pre-trained PoseVAE in Sadtalker.
|checkpoints/mapping_00229-model.pth.tar | Pre-trained MappingNet in Sadtalker.
|checkpoints/mapping_00109-model.pth.tar | Pre-trained MappingNet in Sadtalker.
|checkpoints/facevid2vid_00189-model.pth.tar | Pre-trained face-vid2vid model from [the reappearance of face-vid2vid](https://github.com/zhanglonghao1992/One-Shot_Free-View_Neural_Talking_Head_Synthesis).
|checkpoints/epoch_20.pth | Pre-trained 3DMM extractor in [Deep3DFaceReconstruction](https://github.com/microsoft/Deep3DFaceReconstruction).
|checkpoints/wav2lip.pth | Highly accurate lip-sync model in [Wav2lip](https://github.com/Rudrabha/Wav2Lip).
|checkpoints/shape_predictor_68_face_landmarks.dat | Face landmark model used in [dilb](http://dlib.net/). 
|checkpoints/BFM | 3DMM library file.  
|checkpoints/hub | Face detection models used in [face alignment](https://github.com/1adrianb/face-alignment).
|gfpgan/weights | Face detection and enhanced models used in `facexlib` and `gfpgan`.

The final folder will be shown as:

<img width="331" alt="image" src="https://user-images.githubusercontent.com/4397546/232511411-4ca75cbf-a434-48c5-9ae0-9009e8316484.png">


</details>

## 3. Quick Start

Please read our document on [best practices and configuration tips](docs/best_practice.md)

### WebUI Demos

**Online Demo**: [HuggingFace](https://huggingface.co/spaces/vinthony/SadTalker) | [SDWebUI-Colab](https://colab.research.google.com/github/camenduru/stable-diffusion-webui-colab/blob/main/video/stable/stable_diffusion_1_5_video_webui_colab.ipynb) | [Colab](https://colab.research.google.com/github/Winfredy/SadTalker/blob/main/quick_demo.ipynb)

**Local WebUI extension**: Please refer to [WebUI docs](docs/webui_extension.md).

**Local gradio demo (recommanded)**: A Gradio instance similar to our [Hugging Face demo](https://huggingface.co/spaces/vinthony/SadTalker) can be run locally:

```bash
## you need manually install TTS(https://github.com/coqui-ai/TTS) via `pip install tts` in advanced.
python app_sadtalker.py
```

You can also start it more easily:

- windows: just double click `webui.bat`, the requirements will be installed automatically.
- Linux/Mac OS: run `bash webui.sh` to start the webui.


### CLI usage

##### Animating a portrait image from default config:
```bash
python inference.py --driven_audio <audio.wav> --source_image <video.mp4 or picture.png> --enhancer gfpgan 
```
The results will be saved in `results/$SOME_TIMESTAMP/*.mp4`.

##### Full body/image Generation:

Using `--still` to generate a natural full body video. You can add `enhancer` to improve the quality of the generated video. 

```bash
python inference.py --driven_audio input/1min.wav --source_image input/myphoto.jpg --result_dir out --still --preprocess full --enhancer gfpgan 
```

More examples and configuration and tips can be founded in the [ >>> best practice documents <<<](docs/best_practice.md).



We also use the following 3rd-party libraries:

- **Face Utils**: https://github.com/xinntao/facexlib
- **Face Enhancement**: https://github.com/TencentARC/GFPGAN
- **Image/Video Enhancement**:https://github.com/xinntao/Real-ESRGAN

## Extensions:

- [SadTalker-Video-Lip-Sync](https://github.com/Zz-ww/SadTalker-Video-Lip-Sync) from [@Zz-ww](https://github.com/Zz-ww): SadTalker for Video Lip Editing

## Related Works
- [StyleHEAT: One-Shot High-Resolution Editable Talking Face Generation via Pre-trained StyleGAN (ECCV 2022)](https://github.com/FeiiYin/StyleHEAT)
- [CodeTalker: Speech-Driven 3D Facial Animation with Discrete Motion Prior (CVPR 2023)](https://github.com/Doubiiu/CodeTalker)
- [VideoReTalking: Audio-based Lip Synchronization for Talking Head Video Editing In the Wild (SIGGRAPH Asia 2022)](https://github.com/vinthony/video-retalking)
- [DPE: Disentanglement of Pose and Expression for General Video Portrait Editing (CVPR 2023)](https://github.com/Carlyx/DPE)
- [3D GAN Inversion with Facial Symmetry Prior (CVPR 2023)](https://github.com/FeiiYin/SPI/)
- [T2M-GPT: Generating Human Motion from Textual Descriptions with Discrete Representations (CVPR 2023)](https://github.com/Mael-zys/T2M-GPT)

## Disclaimer

This is not an official product of Tencent. 

```
1. Please carefully read and comply with the open-source license applicable to this code before using it. 
2. Please carefully read and comply with the intellectual property declaration applicable to this code before using it.
3. This open-source code runs completely offline and does not collect any personal information or other data. If you use this code to provide services to end-users and collect related data, please take necessary compliance measures according to applicable laws and regulations (such as publishing privacy policies, adopting necessary data security strategies, etc.). If the collected data involves personal information, user consent must be obtained (if applicable). Any legal liabilities arising from this are unrelated to Tencent.
4. Without Tencent's written permission, you are not authorized to use the names or logos legally owned by Tencent, such as "Tencent." Otherwise, you may be liable for legal responsibilities.
5. This open-source code does not have the ability to directly provide services to end-users. If you need to use this code for further model training or demos, as part of your product to provide services to end-users, or for similar use, please comply with applicable laws and regulations for your product or service. Any legal liabilities arising from this are unrelated to Tencent.
6. It is prohibited to use this open-source code for activities that harm the legitimate rights and interests of others (including but not limited to fraud, deception, infringement of others' portrait rights, reputation rights, etc.), or other behaviors that violate applicable laws and regulations or go against social ethics and good customs (including providing incorrect or false information, spreading pornographic, terrorist, and violent information, etc.). Otherwise, you may be liable for legal responsibilities.
```

LOGO: color and font suggestion: [ChatGPT](https://chat.openai.com), logo font: [Montserrat Alternates
](https://fonts.google.com/specimen/Montserrat+Alternates?preview.text=SadTalker&preview.text_type=custom&query=mont).

All the copyrights of the demo images and audio are from community users or the generation from stable diffusion. Feel free to contact us if you would like use to remove them.


<!-- Spelling fixed on Tuesday, September 12, 2023 by @fakerybakery (https://github.com/fakerybakery). These changes are licensed under the Apache 2.0 license. -->
