![image](https://microsoft.github.io/CameraTraps/assets/Pytorch_Banner_transparentbk.png)

<div align="center">
<font size="6"> A Collaborative Deep Learning Framework for Conservation </font>
<br>
<hr>
<a href="https://pypi.org/project/PytorchWildlife"><img src="https://img.shields.io/pypi/v/PytorchWildlife?color=limegreen" /></a>
<a href="https://pypi.org/project/PytorchWildlife"><img src="https://static.pepy.tech/badge/pytorchwildlife" /></a>
<a href="https://pypi.org/project/PytorchWildlife"><img src="https://img.shields.io/pypi/pyversions/PytorchWildlife" /></a>
<a href="https://huggingface.co/spaces/ai-for-good-lab/pytorch-wildlife"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Demo-blue" /></a>
<a href="https://colab.research.google.com/drive/1rjqHrTMzEHkMualr4vB55dQWCsCKMNXi?usp=sharing"><img src="https://img.shields.io/badge/Colab-Demo-blue?logo=GoogleColab" /></a>
<!-- <a href="https://colab.research.google.com/drive/16-OjFVQ6nopuP-gfqofYBBY00oIgbcr1?usp=sharing"><img src="https://img.shields.io/badge/Colab-Video detection-blue?logo=GoogleColab" /></a> -->
<a href="https://cameratraps.readthedocs.io/en/latest/"><img src="https://img.shields.io/badge/read-docs-yellow?logo=ReadtheDocs" /></a>
<a href="https://github.com/microsoft/CameraTraps/blob/main/LICENSE"><img src="https://img.shields.io/pypi/l/PytorchWildlife" /></a>
<a href="https://discord.gg/TeEVxzaYtm"><img src="https://img.shields.io/badge/any_text-Join_us!-blue?logo=discord&label=Discord" /></a>
<br><br>
</div>

## 🐾 Introduction

At the core of our mission is the desire to create a harmonious space where conservation scientists from all over the globe can unite. Where they're able to share, grow, use datasets and deep learning architectures for wildlife conservation.
We've been inspired by the potential and capabilities of Megadetector, and we deeply value its contributions to the community. As we forge ahead with Pytorch-Wildlife, under which Megadetector now resides, please know that we remain committed to supporting, maintaining, and developing Megadetector, ensuring its continued relevance, expansion, and utility.

Pytorch-Wildlife is pip installable:

```
pip install PytorchWildlife
```

To use the newest version of MegaDetector with all the existing functionalities, you can use our [Hugging Face interface](https://huggingface.co/spaces/ai-for-good-lab/pytorch-wildlife) or simply load the model with **Pytorch-Wildlife**. The weights will be automatically downloaded:

```python
from PytorchWildlife.models import detection as pw_detection
detection_model = pw_detection.MegaDetectorV6()
```

For those interested in accessing the previous MegaDetector repository, which utilizes the same `MegaDetectorV5` model weights and was primarily developed by Dan Morris during his time at Microsoft, please visit the [archive](https://github.com/microsoft/CameraTraps/blob/main/archive) directory, or you can visit this [forked repository](https://github.com/agentmorris/MegaDetector/tree/main) that Dan Morris is actively maintaining.

!!! tip
    If you have any questions regarding MegaDetector and Pytorch-Wildlife, please [email us](zhongqimiao@microsoft.com) or join us in our discord channel: [![](https://img.shields.io/badge/any_text-Join_us!-blue?logo=discord&label=PytorchWildife)](https://discord.gg/TeEVxzaYtm)

## 📣 Announcements

### Pytorch-Wildlife Version 1.2.1

#### SpeciesNet is available in Pytorch-Wildlife for testing

- We have added SpeciesNet into our model zoo, which is compatible with all detection models provided by Pytorch-Wildlife. Please refer to [this document](https://github.com/microsoft/CameraTraps/blob/SppNet_TF/PytorchWildlife/models/classification/speciesnet_base/sppnet_readme.md) for more details!

#### Deepfaune in Our Model Zoo

- We are excited to announce the release of the Deepfaune models—both the detector and classifier—in PyTorch-Wildlife, adding to our growing model zoo. A huge thank you to the Deepfaune team for your support! Deepfaune is one of the most comprehensive models focused on the European ecosystem for both detection and classification. It serves as a great complement to MegaDetector, which has primarily been trained on datasets from North America, South America, and Africa. The Deepfaune detector is also our first third-party camera trap detection model integrated into PyTorch-Wildlife!
- To use the model, you just need to load them as any other Pytorch-Wildife models:

```
detection_model = pw_detection.DeepfauneDetector(device=DEVICE)
classification_model = pw_classification.DeepfauneClassifier(device=DEVICE)
```

- You can also use the `detection_classification_pipeline_demo.py` script in the demo folder to test the whole detection + classification pipeline.
- Please also take a look at the original [Deepfaune website](https://www.deepfaune.cnrs.fr/en/) and give them a star!

#### Deepfaune-New-England in Our Model Zoo Too

- Besides the original Deepfaune mode, there is another fine-tuned Deepfaune model developed by USGS for the Northeastern NA area called Deepfaune-New-England (DFNE). It can also be loaded with `classification_model = pw_classification.DFNE(device=DEVICE)`
- Please take a look at the orignal [DFNE repo](https://code.usgs.gov/vtcfwru/deepfaune-new-england/-/tree/main?ref_type=heads) and give them a star!

### Previous versions

- [Pytorch-Wildlife Version 1.2.0](ANNOUNCEMENT.md)

### 🏎️💨💨 MegaDetectorV6: SMALLER, FASTER, BETTER  

We have officially released our 6th version of MegaDetector, MegaDetectorV6! In the next generation of MegaDetector, we are focusing on computational efficiency, performance, modernizing of model architectures, and licensing. We have trained multiple new models using different model architectures, including Yolo-v9, Yolo-v10, and RT-Detr for maximum user flexibility. We have a [rolling release schedule](#model-zoo) for different versions of MegaDetectorV6.

!!! note
    - Following our initial release, we've been delighted to see so many people explore our new models. We'd like to extend our heartfelt thanks to everyone who has shown interest in our latest models—your support means a great deal to us!
    - That said, we've received a number of feedback comments highlighting a discrepancy between the reported performance (particularly MDV5) and the actual performance observed. We are actively investigating this issue and have identified a potential error or corruption in the validation data we used. For the time being, we'll remove our current performance numbers from the model zoo for now to avoid confusion.
    - We sincerely apologize for any confusion or inconvenience this may have caused. Our team is working diligently to address this matter, and we will update our experiments—and potentially retrain the model if data corruption is confirmed—as soon as possible. Thank you for your patience and understanding!

MegaDetectorV6 models are based on architectures optimized for performance and low-budget devices. For example, the MegaDetectorV6-Ultralytics-YoloV10-Compact (MDV6-yolov10-c) model only have ***2% of the parameters*** of the previous MegaDetectorV5 and still exhibits comparable animal recall on our validation datasets.

<!-- In the following figure, we can see the Performance to Parameter metric of each released MegaDetector model. All of the V6 models, extra large or compact, have at least 50% less parameters compared to MegaDetectorV5 but with much higher animal detection performance. -->

<!-- ![image](assets/ParamPerf.png) -->

<!-- >[!TIP] -->
<!-- >From now on, we encourage our users to use MegaDetectorV6 as their default animal detection model and choose whichever model that fits the project needs. To reduce potential confusion, we have also standardized the model names into MDV6-Compact and MDV6-Extra for two model sizes using the same architecture. Learn how to use MegaDetectorV6 in our [image demo](demo/image_detection_demo_v6.ipynb) and [video demo](demo/video_detection_demo_v6.ipynb). -->

### ‼️ Model licensing

The **Pytorch-Wildlife** package is under MIT, however some of the models in the model zoo are not. For example, MegaDetectorV5, which is trained using the Ultralytics package, a package under AGPL-3.0, and is not for closed-source commercial uses if they are using updated 'ultralytics' packages.

There may be a confusion because YOLOv5 was initially released before the establishment of the AGPL-3.0 license. According to the official [Ultralytics-Yolov5](https://github.com/ultralytics/yolov5) package, it is under AGPL-3.0 now, and the maintainers have discussed how their licensing policy has evolved over time in their issues section.

<!-- We aim to prevent any confusion or potential issues for our users. -->

<!-- > [!IMPORTANT]
> THIS IS TRUE TO ALL EXISTING MEGADETECTORV5 MODELS IN ALL EXISTING FORKS THAT ARE TRAINED USING YOLOV5, AN ULTRALYTICS-DEVELOPED MODEL. -->

We want to make Pytorch-Wildlife a platform where different models with different licenses can be hosted and want to enable different use cases. To reduce user confusions, in our [model zoo](#model-zoo) section, we list all existing and planed future models in our model zoo, their corresponding license, and release schedules.

In addition, since the **Pytorch-Wildlife** package is under MIT, all the utility functions, including data pre-/post-processing functions and model fine-tuning functions in this packages are under MIT as well.

<a id="model-zoo"></a>
### 🔍 Model Zoo and Release Schedules

#### MegaDetectors

|Models|Version Names|Licence|Release|Parameters (M)|
|---|---|---|---|---|
|MegaDetectorV5|-|AGPL-3.0|Released|121|
|MegaDetectorV6-Ultralytics-YoloV9-Compact|MDV6-yolov9-c|AGPL-3.0|Released|25.5|
|MegaDetectorV6-Ultralytics-YoloV9-Extra|MDV6-yolov9-e|AGPL-3.0|Released|58.1|
|MegaDetectorV6-Ultralytics-YoloV10-Compact (even smaller and no NMS)|MDV6-yolov10-c|AGPL-3.0|Released|2.3|
|MegaDetectorV6-Ultralytics-YoloV10-Extra (extra large model and no NMS)|MDV6-yolov10-c|AGPL-3.0|Released|29.5|
|MegaDetectorV6-Ultralytics-RtDetr-Compact|MDV6-redetr-c|AGPL-3.0|Released|31.9|
|MegaDetectorV6-Ultralytics-YoloV11-Compact|-|AGPL-3.0|Will Not Release|2.6|
|MegaDetectorV6-Ultralytics-YoloV11-Extra|-|AGPL-3.0|Will Not Release|56.9|
|MegaDetectorV6-MIT-YoloV9-Compact|MDV6-mit-yolov9-c|MIT|Training|9.7|
|MegaDetectorV6-MIT-YoloV9-Extra|MDV6-mit-yolov9-c|MIT|Training|51|
|MegaDetectorV6-Apache-RTDetr-Compact|MDV6-apa-redetr-c|Apache|Training|20|
|MegaDetectorV6-Apache-RTDetr-Extra|MDV6-apa-redetr-c|Apache|Training|76|

<!-- |Models|Version Names|Licence|Release|Parameters (M)|mAP<sup>val<br>50-95|Animal Recall|
|---|---|---|---|---|---|---|
|MegaDetectorV5|-|AGPL-3.0|Released|121|74.7|74.9|
|MegaDetectorV6-Ultralytics-YoloV9-Compact|MDV6-yolov9-c|AGPL-3.0|Released|25.5|73.8|82.6|
|MegaDetectorV6-Ultralytics-YoloV9-Extra|MDV6-yolov9-e|AGPL-3.0|Released|58.1|80.2|87.1|
|MegaDetectorV6-Ultralytics-YoloV10-Compact (even smaller and no NMS)|MDV6-yolov10-c|AGPL-3.0|Released|2.3|71.8|78.8|
|MegaDetectorV6-Ultralytics-YoloV10-Extra (extra large model and no NMS)|MDV6-yolov10-c|AGPL-3.0|Released|29.5|79.9|85.2|
|MegaDetectorV6-Ultralytics-RtDetr-Compact|MDV6-redetr-c|AGPL-3.0|Released|31.9|73.9|83.4|
|MegaDetectorV6-Ultralytics-YoloV11-Compact|-|AGPL-3.0|Will Not Release|2.6|71.9|79.8|
|MegaDetectorV6-Ultralytics-YoloV11-Extra|-|AGPL-3.0|Will Not Release|56.9|79.3|86.0|
|MegaDetectorV6-MIT-YoloV9-Compact|MDV6-mit-yolov9-c|MIT|MDV6-mit-yolov9-c|February 2025|9.7|73.84|-|
|MegaDetectorV6-MIT-YoloV9-Extra|MDV6-mit-yolov9-c|MIT|February 2025|51|Training|Training|
|MegaDetectorV6-Apache-RTDetr-Compact|MDV6-apa-redetr-c|Apache|February 2025|20|76.3|-|
|MegaDetectorV6-Apache-RTDetr-Extra|MDV6-apa-redetr-c|Apache|February 2025|76|80.8|-| -->

!!! tip
    We are specifically reporting `Animal Recall` as our primary performance metric, even though it is not commonly used in traditional object detection studies, which typically focus on balancing overall model performance. For MegaDetector, our goal is to optimize for animal recall—in other words, minimizing false negative detections of animals or, more simply, ensuring our model misses as few animals as possible. While this may result in a higher false positive rate, we rely on downstream classification models to further filter the detected objects. We believe this approach is more practical for real-world animal monitoring scenarios.

#### Other detection models

|Models|Version Names|Licence|Release|Reference|
|---|---|---|---|---|
|Deepfaune-detection|-|CC BY-SA 4.0|Released|[Deepfaune](https://www.deepfaune.cnrs.fr/en/)|
|HerdNet-general|general|CC BY-NC-SA-4.0|Released|[Alexandre et. al. 2023](https://github.com/Alexandre-Delplanque/HerdNet)|
|HerdNet-ennedi|ennedi|CC BY-NC-SA-4.0|Released|[Alexandre et. al. 2023](https://github.com/Alexandre-Delplanque/HerdNet)|
|MegaDetector-Overhead|-|MIT|Mid 2025|-|
|MegaDetector-Bioacoustics|-|MIT|Late 2025|-|

#### Classification models

|Models|Version Names|Licence|Release|
|---|---|---|---|
|AI4G-Oppossum|-|MIT|Released|
|AI4G-Amazon-V1|v1|MIT|Released|
|AI4G-Amazon-V2|v2|MIT|Released|
|AI4G-Serengeti|-|MIT|Released|
|Deepfaune-classification|v1.3|CC BY-SA 4.0|Released|[Deepfaune](https://www.deepfaune.cnrs.fr/en/)|
|Deepfaune-New-England|v1.0|CC0 1.0 Universal|Released|[Deepfaune-New-England](https://code.usgs.gov/vtcfwru/deepfaune-new-england)|

!!! tip
    Some models, such as MegaDetectorV6, HerdNet, and AI4G-Amazon, have different versions, and they are loaded by their corresponding version names. Here is an example: `detection_model = pw_detection.MegaDetectorV6(version="MDV6-yolov10-e")`.

## 👋 Welcome to Pytorch-Wildlife

**PyTorch-Wildlife** is a platform to create, modify, and share powerful AI conservation models. These models can be used for a variety of applications, including camera trap images, overhead images, underwater images, or bioacoustics. Your engagement with our work is greatly appreciated, and we eagerly await any feedback you may have.

The **Pytorch-Wildlife** library allows users to directly load the `MegaDetector` model weights for animal detection. We've fully refactored our codebase, prioritizing ease of use in model deployment and expansion. In addition to `MegaDetector`, **Pytorch-Wildlife** also accommodates a range of classification weights, such as those derived from the Amazon Rainforest dataset and the Opossum classification dataset. Explore the codebase and functionalities of **Pytorch-Wildlife** through our interactive [HuggingFace web app](https://huggingface.co/spaces/AndresHdzC/pytorch-wildlife) or local [demos and notebooks](https://github.com/microsoft/CameraTraps/tree/main/demo), designed to showcase the practical applications of our enhancements at [PyTorchWildlife](https://github.com/microsoft/CameraTraps/blob/main/INSTALLATION.md). You can find more information in our [documentation](https://cameratraps.readthedocs.io/en/latest/).

👇 Here is a brief example on how to perform detection and classification on a single image using `PyTorch-wildlife`

```python
import numpy as np
from PytorchWildlife.models import detection as pw_detection
from PytorchWildlife.models import classification as pw_classification

img = np.random.randn(3, 1280, 1280)

# Detection
detection_model = pw_detection.MegaDetectorV6() # Model weights are automatically downloaded.
detection_result = detection_model.single_image_detection(img)

#Classification
classification_model = pw_classification.AI4GAmazonRainforest() # Model weights are automatically downloaded.
classification_results = classification_model.single_image_classification(img)
```

## ⚙️ Install Pytorch-Wildlife

```
pip install PytorchWildlife
```

Please refer to our [installation guide](https://github.com/microsoft/CameraTraps/blob/main/INSTALLATION.md) for more installation information.

## 🕵️ Explore Pytorch-Wildlife and MegaDetector with our Demo User Interface

If you want to directly try **Pytorch-Wildlife** with the AI models available, including `MegaDetector`, you can use our [**Gradio** interface](https://github.com/microsoft/CameraTraps/tree/main/demo). This interface allows users to directly load the `MegaDetector` model weights for animal detection. In addition, **Pytorch-Wildlife** also has two classification models in our initial version. One is trained from an Amazon Rainforest camera trap dataset and the other from a Galapagos opossum classification dataset (more details of these datasets will be published soon). To start, please follow the [installation instructions](https://github.com/microsoft/CameraTraps/blob/main/INSTALLATION.md) on how to run the Gradio interface! We also provide multiple [**Jupyter** notebooks](https://github.com/microsoft/CameraTraps/tree/main/demo) for demonstration.

![image](https://microsoft.github.io/CameraTraps/assets/gradio_UI.png)

## 🛠️ Core Features

   What are the core components of Pytorch-Wildlife?
![Pytorch-core-diagram](https://microsoft.github.io/CameraTraps/assets/Pytorch_Wildlife_core_figure.jpg)

### 🌐 Unified Framework

  Pytorch-Wildlife integrates **four pivotal elements:**

▪ Machine Learning Models<br>
▪ Pre-trained Weights<br>
▪ Datasets<br>
▪ Utilities<br>

### 👷 Our work

  In the provided graph, boxes outlined in red represent elements that will be added and remained fixed, while those in blue will be part of our development.

### 🚀 Inaugural Model

  We're kickstarting with YOLO as our first available model, complemented by pre-trained weights from `MegaDetector`. We have `MegaDetectorV5`, which is the same `MegaDetectorV5` model from the previous repository, and many different versions of `MegaDetectorV6` for different usecases.

### 📚 Expandable Repository

  As we move forward, our platform will welcome new models and pre-trained weights for camera traps and bioacoustic analysis. We're excited to host contributions from global researchers through a dedicated submission platform.

### 📊 Datasets from LILA

  Pytorch-Wildlife will also incorporate the vast datasets hosted on LILA, making it a treasure trove for conservation research.

### 🧰 Versatile Utilities

  Our set of utilities spans from visualization tools to task-specific utilities, many inherited from Megadetector.

### 💻 User Interface Flexibility

  While we provide a foundational user interface, our platform is designed to inspire. We encourage researchers to craft and share their unique interfaces, and we'll list both existing and new UIs from other collaborators for the community's benefit.

Let's shape the future of wildlife research, together! 🙌

## 🖼️ Examples

### Image detection using `MegaDetector`

<img src="https://microsoft.github.io/CameraTraps/assets/animal_det_1.JPG" alt="animal_det_1" width="400"/><br>
*Credits to Universidad de los Andes, Colombia.*

### Image classification with `MegaDetector` and `AI4GAmazonRainforest`

<img src="https://microsoft.github.io/CameraTraps/assets/animal_clas_1.png" alt="animal_clas_1" width="500"/><br>
*Credits to Universidad de los Andes, Colombia.*

### Opossum ID with `MegaDetector` and `AI4GOpossum`

<img src="https://microsoft.github.io/CameraTraps/assets/opossum_det.png" alt="opossum_det" width="500"/><br>
*Credits to the Agency for Regulation and Control of Biosecurity and Quarantine for Galápagos (ABG), Ecuador.*

## 🤜🤛 Collaboration with AddaxAI (formerly EcoAssist)

We are thrilled to announce our collaboration with [AddaxAI](https://addaxdatascience.com/addaxai/#spp-models)---a powerful user interface software that enables users to directly load models from the PyTorch-Wildlife model zoo for image analysis on local computers. With AddaxAI, you can now utilize MegaDetectorV5 and the classification models---AI4GAmazonRainforest and AI4GOpossum---for automatic animal detection and identification, alongside a comprehensive suite of pre- and post-processing tools. This partnership aims to enhance the overall user experience with PyTorch-Wildlife models for a general audience. We will work closely to bring more features together for more efficient and effective wildlife analysis in the future.

## 🖋️ Cite us

We have recently published a [summary paper on Pytorch-Wildlife](https://arxiv.org/abs/2405.12930). The paper has been accepted as an oral presentation at the [CV4Animals workshop](https://www.cv4animals.com/) at this CVPR 2024. Please feel free to cite us!

```
@misc{hernandez2024pytorchwildlife,
      title={Pytorch-Wildlife: A Collaborative Deep Learning Framework for Conservation}, 
      author={Andres Hernandez and Zhongqi Miao and Luisa Vargas and Sara Beery and Rahul Dodhia and Juan Lavista},
      year={2024},
      eprint={2405.12930},
      archivePrefix={arXiv},
}
```

Also, don't forget to cite our original paper for MegaDetector:

```
@misc{beery2019efficient,
      title={Efficient Pipeline for Camera Trap Image Review},
      author={Sara Beery and Dan Morris and Siyu Yang},
      year={2019}
      eprint={1907.06772},
      archivePrefix={arXiv},
}
```

## 🤝 Contributing

This project is open to your ideas and contributions. If you want to submit a pull request, we'll have some guidelines available soon.

We have adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [us](zhongqimiao@microsoft.com) with any additional questions or comments.

## License

This repository is licensed with the [MIT license](https://github.com/Microsoft/dotnet/blob/main/LICENSE).

## 👥 Existing Collaborators

The extensive collaborative efforts of Megadetector have genuinely inspired us, and we deeply value its significant contributions to the community. As we continue to advance with Pytorch-Wildlife, our commitment to delivering technical support to our existing partners on MegaDetector remains the same.

Here we list a few of the organizations that have used MegaDetector. We're only listing organizations who have given us permission to refer to them here or have posted publicly about their use of MegaDetector.

<details>
<summary><font size="3">👉 Full list of organizations</font></summary>
(Newly Added) <a href="https://www.terroiko.fr/">TerrOïko</a> (<a href="https://www.terroiko.fr/ocapi">OCAPI platform</a>)<br>

<a href="http://azdeq.gov/">Arizona Department of Environmental Quality</a><br>

<a href="https://blackbirdenv.com/">Blackbird Environmental</a><br>

<a href="https://camelotproject.org/">Camelot</a><br>

<a href="https://cpawsnab.org/">Canadian Parks and Wilderness Society (CPAWS) Northern Alberta Chapter</a><br>

<a href="https://conservationxlabs.com/">Conservation X Labs</a><br>

<a href="https://www.czu.cz/en">Czech University of Life Sciences Prague</a><br>

<a href="https://www.consult-ecologic.com/">EcoLogic Consultants Ltd.</a><br>

<a href="http://www.ebd.csic.es/inicio">Estación Biológica de Doñana</a><br>

<a href="https://idfg.idaho.gov/">Idaho Department of Fish and Game</a><br>

<a href="https://www.islandconservation.org/">Island Conservation</a><br>

<a href="https://carnivorecoexistence.info/myall-lakes-dingo-project/">Myall Lakes Dingo Project</a><br>

<a href="https://pnptc.org/">Point No Point Treaty Council</a><br>

<a href="https://www.ramat-hanadiv.org.il/en/">Ramat Hanadiv Nature Park</a><br>

<a href="https://spea.pt/en/">SPEA (Portuguese Society for the Study of Birds)</a><br>

<a href="https://www.synthetaic.com/">Synthetaic</a><br>

<a href="https://taronga.org.au/">Taronga Conservation Society</a><br>

<a href="https://www.nature.org/en-us/about-us/where-we-work/united-states/wyoming/">The Nature Conservancy in Wyoming</a><br>

<a href="https://wildeyeconservation.org/trap-tagger-about/">TrapTagger</a><br>

<a href="https://www.upperyellowstone.org/">Upper Yellowstone Watershed Group</a><br>

<a href="http://www.acmelab.ca/">Applied Conservation Macro Ecology Lab</a>, University of Victoria<br>

<a href="https://www.pc.gc.ca/en/pn-np/ab/banff/nature/conservation">Banff National Park Resource Conservation</a>, Parks Canada (<a href="https://www.pc.gc.ca/en/pn-np/ab/banff/nature/conservation">https://www.pc.gc.ca/en/pn-np/ab/banff/nature/conservation</a>)<br>

<a href="https://blumsteinlab.eeb.ucla.edu/">Blumstein Lab</a>, UCLA<br>

<a href="https://bri.sulross.edu/">Borderlands Research Institute</a>, Sul Ross State University<br>

<a href="https://www.nps.gov/care/index.htm">Capitol Reef National Park</a> / Utah Valley University<br>

<a href="https://www.amnh.org/research/center-for-biodiversity-conservation">Center for Biodiversity and Conservation</a>, American Museum of Natural History<br>

<a href="https://www.unsw.edu.au/research/">Centre for Ecosystem Science</a>, UNSW Sydney<br>

<a href="https://crossculturalecology.net/">Cross-Cultural Ecology Lab</a>, Macquarie University<br>

<a href="https://hub.dccatcount.org/">DC Cat Count</a>, led by the Humane Rescue Alliance<br>

<a href="https://www.uidaho.edu/cnr/departments/fish-and-wildlife-sciences">Department of Fish and Wildlife Sciences</a>, University of Idaho<br>

<a href="https://wec.ifas.ufl.edu/">Department of Wildlife Ecology and Conservation</a>, University of Florida<br>

<a href="https://www.researchgate.net/lab/Fernanda-Michalski-Lab-4">Ecology and Conservation of Amazonian Vertebrates Research Group</a>, Federal University of Amapá<br>

<a href="https://www.rspb.org.uk/our-work/conservation/projects/scientific-support-for-the-gola-forest-programme/">Gola Forest Programma</a>, Royal Society for the Protection of Birds (RSPB)<br>

<a href="https://wildliferesearch.co.uk/group-1">Graeme Shannon's Research Group</a>, Bangor University<br>

<a href="https://hamaarag.org.il/">Hamaarag</a>, The Steinhardt Museum of Natural History, Tel Aviv University<br>

<a href="https://isfort.uqo.ca/">Institut des Science de la Forêt Tempérée (ISFORT)</a>, Université du Québec en Outaouais<br>

<a href="https://bhlab.in/about">Lab of Dr. Bilal Habib</a>, the Wildlife Institute of India<br>

<a href="https://labs.wsu.edu/dthornton/">Mammal Spatial Ecology and Conservation Lab</a>, Washington State University<br>

<a href="http://mcloughlinlab.ca/lab/">McLoughlin Lab in Population Ecology</a>, University of Saskatchewan<br>

<a href="https://www.fws.gov/about/region/southwest">National Wildlife Refuge System, Southwest Region</a>, U.S. Fish & Wildlife Service<br>

<a href="https://nationalzoo.si.edu/news/restoring-americas-prairie">Northern Great Plains Program</a>, Smithsonian<br>

<a href="https://depts.washington.edu/sefsqel/">Quantitative Ecology Lab</a>, University of Washington<br>

<a href="https://www.nps.gov/samo/index.htm">Santa Monica Mountains Recreation Area</a>, National Park Service<br>

<a href="https://www.zoo.org/seattlecarnivores">Seattle Urban Carnivore Project</a>, Woodland Park Zoo<br>

<a href="https://www.icmbio.gov.br/parnaserradosorgaos/">Serra dos Órgãos National Park</a>, ICMBio<br>

<a href="https://emammal.si.edu/snapshot-usa">Snapshot USA</a>, Smithsonian<br>

<a href="https://wildlife.forestry.ubc.ca/">Wildlife Coexistence Lab</a>, University of British Columbia<br>

<a href="https://www.dfw.state.or.us/wildlife/research/index.asp">Wildlife Research</a>, Oregon Department of Fish and Wildlife<br>

<a href="https://www.michigan.gov/dnr/about/contact/wildlife">Wildlife Division</a>, Michigan Department of Natural Resources<br>

Department of Ecology, TU Berlin<br>

Ghost Cat Analytics<br>

Protected Areas Unit, Canadian Wildlife Service<br>

<a href="https://www.utas.edu.au/natural-sciences">School of Natural Sciences</a>, University of Tasmania <a href="https://www.utas.edu.au/about/news-and-stories/articles/2022/1204-innovative-camera-network-keeps-close-eye-on-tassie-wildlife">(story)</a><br>

<a href="https://www.fws.gov/refuge/kenai">Kenai National Wildlife Refuge</a>, U.S. Fish & Wildlife Service <a href="https://www.peninsulaclarion.com/sports/refuge-notebook-new-technology-increases-efficiency-of-refuge-cameras/">(story)</a><br>

<a href="https://www.australianwildlife.org/">Australian Wildlife Conservancy</a> <a href="https://www.australianwildlife.org/cutting-edge-technology-delivering-efficiency-gains-in-conservation/">(blog</a>, <a href="https://www.australianwildlife.org/efficiency-gains-at-the-cutting-edge-of-technology/">blog)</a><br>

<a href="https://felidaefund.org/">Felidae Conservation Fund</a> <a href="https://wildepod.org/">(WildePod platform)</a> <a href="https://abhaykashyap.com/blog/ai-powered-camera-trap-image-annotation-system/">(blog post)</a><br>

<a href="https://www.abmi.ca/home.html">Alberta Biodiversity Monitoring Institute (ABMI)</a> <a href="https://www.wildtrax.ca/">(WildTrax platform)</a> <a href="https://wildcams.ca/blog/the-abmi-visits-the-zoo/">(blog post)</a><br>

<a href="http://en.shanshui.org/">Shan Shui Conservation Center</a> <a href="https://mp.weixin.qq.com/s/iOIQF3ckj0-rEG4yJgerYw?fbclid=IwAR0alwiWbe3udIcFvqqwm7y5qgr9hZpjr871FZIa-ErGUukZ7yJ3ZhgCevs">(blog post)</a> <a href="https://mp-weixin-qq-com.translate.goog/s/iOIQF3ckj0-rEG4yJgerYw?fbclid=IwAR0alwiWbe3udIcFvqqwm7y5qgr9hZpjr871FZIa-ErGUukZ7yJ3ZhgCevs&_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=en&_x_tr_pto=wapp">(translated blog post)</a><br>

<a href="http://www.irconservancy.org/">Irvine Ranch Conservancy</a> <a href="https://www.ocregister.com/2022/03/30/ai-software-is-helping-researchers-focus-on-learning-about-ocs-wild-animals/">(story)</a><br>

<a href="https://wildlifeprotectionsolutions.org/">Wildlife Protection Solutions</a> <a href="https://customers.microsoft.com/en-us/story/1384184517929343083-wildlife-protection-solutions-nonprofit-ai-for-earth">(story</a>, <a href="https://www.enterpriseai.news/2023/02/20/ai-helps-wildlife-protection-solutions-safeguard-endangered-species/">story)</a><br>

<a href="https://roadecology.ucdavis.edu/">Road Ecology Center</a>, University of California, Davis <a href="https://wildlifeobserver.net/">(Wildlife Observer Network platform)</a><br>

<a href="https://www.nature.org/en-us/about-us/where-we-work/united-states/california/">The Nature Conservancy in California</a> <a href="https://github.com/tnc-ca-geo/animl-frontend">(Animl platform)</a><br>

<a href="https://science.sandiegozoo.org/">San Diego Zoo Wildlife Alliance</a> <a href="https://github.com/conservationtechlab/animl">(Animl R package)</a><br>

</details><br>

!!! info
    If you would like to be added to this list or have any questions regarding MegaDetector and Pytorch-Wildlife, please [email us](zhongqimiao@microsoft.com) or join us in our Discord channel: [![](https://img.shields.io/badge/any_text-Join_us!-blue?logo=discord&label=PytorchWildife)](https://discord.gg/TeEVxzaYtm)
