## **CountZES: Counting via Zero-Shot Exemplar Discovery and Selection** [WACV 2027 🔥]

### Abstract
Zero-shot object counting (ZOC) aims to count instances of unseen categories using only a class name. Existing exemplar-based methods discover candidate exemplars through random image patches or open-vocabulary detector proposals. However, random patch sampling often yields poorly delineated instances, while detector-based discovery may produce multi-instance regions and, in dense scenes, provide only a few or even no suitable single-instance candidates. Thus, exemplar selection is constrained by candidate quality and coverage, while counting itself remains highly sensitive to exemplar choice. To this end, we propose CountZES, an inference-only framework that jointly addresses candidate discovery and exemplar selection through density-guided candidate generation and complementary exemplar-selection mechanisms. Starting from a text-grounded anchor, CountZES progressively discovers and refines visual exemplars through three stages: Detection-Anchored Exemplar (DAE), Density-Guided Exemplar (DGE), and Feature-Consensus Exemplar (FCE). DAE establishes a reliable single-instance anchor, DGE leverages density responses to expand candidate discovery beyond the detector-constrained pool and select a statistically consistent exemplar, and FCE promotes representativeness through feature-level consensus. Together, they yield complementary exemplars balancing semantic grounding, count consistency, and feature representativeness. CountZES requires no ZOC-specific optimization and adopts a modular design that supports different pretrained components. Extensive evaluations across natural, aerial, and medical domains demonstrate strong cross-domain generalization and superior performance among inference-only ZOC methods.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a35ce198-ef8e-406c-84b4-475f6aec7a89" width="550">
</p>


## 🔥 News
* Excited to announce acceptance of PerSense at WACV 2027 🚀
* We release the code for **CountZES** 🚀
* CountZES paper is released [arXiv Link](https://arxiv.org/abs/2512.16415)
## 🌟 Highlight
We introduce **CountZES** 🚀 for **Object Counting via Zero-Shot Exemplar Selection**. 

👑 **End-to-End**  
❄️ **Training-free**  

<img width="7465" height="3543" alt="Main_figure_v2" src="https://github.com/user-attachments/assets/49aefbf0-e8c6-46de-b763-1b56e208d558" />


## 🛠️ Requirements

### Installation
Our code requires pytorch>=1.7 and torchvision>=0.8. For compatibility check [here](https://pytorch.org/get-started/locally/).
Clone the repo and create conda environment following the instructions given below:

    git clone https://github.com/Muhammad-Ibraheem-Siddiqui/CountZES.git
    cd CountZES

    conda create -n countzes python=3.8
    conda activate countzes
    
    conda install pytorch==2.2.2 torchvision==0.17.2 torchaudio==2.2.2 pytorch-cuda=12.1 -c pytorch -c nvidia
    (can be changed as per the platform following the link above)

    pip install -r requirements.txt


### Dataset
We conduct experiments over five datasets. You can download each from the given links. [FSC147](https://github.com/cvlab-stonybrook/LearningToCountEverything), [CARPK](https://lafi.github.io/LPN/), [PerSense-D](https://github.com/Muhammad-Ibraheem-Siddiqui/PerSense), [MBM](https://drive.google.com/file/d/1i54Hcw2GbCVp0Kz7jei2Lr7Cmi2DZkol/view?usp=sharing) and [VGG](https://drive.google.com/file/d/1FerZjhpA1MCtsmjD-eF1byZvOWEDnwZL/view?usp=sharing)

    data/
    ├─FSC-147/    
      │  ├─gt_density_map_adaptive_384_VarV2/
      │  ├─images_384_VarV2/
    ├─CARPK/
      │  ├─gt_density_map/
      │  ├─Images/
    ├─persenseD/
      │  ├─Images/
    ├─mbm/
      │  ├─Images/
          │  ├─blood cells/
    ├─vgg/
      │  ├─Images/
          │  ├─cells/

### 🔩 Model Weights
Please download pretrained weights of SAM from [here](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_h_4b8939.pth). Also, download weights for DSALVANet pretrained on FSC-147 from [here](https://drive.google.com/file/d/1julzH9MJSK1xTGchb1r0CXdZ2wzF5-Kp/view?usp=sharing) and weights for GroungdingDINO from [here](https://drive.google.com/file/d/13rV6dzRwWCVZYWpnmiaVwRDIDC28d82g/view?usp=sharing). Download weights for CounTR pretrained on FSC-147 and CARPK dataset from [here](https://github.com/Verg-Avesta/CounTR).

    data/
    sam_vit_h_4b8939.pth

    DSALVANet/checkpoints/
    checkpoint_200.pth

    GroundingDINO/weights/
    groundingdino_swint_ogc.pth

    CounTR/output_allnew_dir/
    FSC147.pth
    CARPK.pth
    
## 🏃‍♂️ Getting Started

To evaluate CountZES on FSC147 dataset, run:

    python countzes_fsc147.py (add argument '--visualize True' for visualization)

To evaluate CountZES on CARPK dataset, run:

    python countzes_carpk.py

To evaluate CountZES on PerSense-D dataset, run:

    python countzes_persense_D.py

To evaluate CountZES on MBM dataset, run:

    python countzes_mbm.py

To evaluate CountZES on vgg dataset, run:

    python countzes_vgg.py

## 👀 Output

![Qualitative_results_supp](https://github.com/user-attachments/assets/4291d12b-135b-43da-9bf8-21007756f6c4)

## License
[![Code License: PolyForm Noncommercial](https://img.shields.io/badge/Code%20License-PolyForm%20Noncommercial%201.0.0-orange.svg)](LICENSE)

**Usage and License Notices**: Intended and licensed for research use only.

## ❤️ Acknowledgement 
Our repo benefits from [SAM](https://github.com/facebookresearch/segment-anything), [GroundingDINO](https://github.com/IDEA-Research/GroundingDINO), [CLIP](https://github.com/openai/CLIP), [PerSense](https://github.com/muhammad-ibraheem-siddiqui/persense), [DSALVANet](https://github.com/kadvinj/DSALVANet?tab=readme-ov-file) and [CounTR](https://verg-avesta.github.io/CounTR_Webpage/). Thanks for their great work.

## ✒️ Citation

    @article{siddiqui2025countzes,
      title={CountZES: Counting via Zero-Shot Exemplar Discovery and Selection},
      author={Siddiqui, Muhammad Ibraheem and Khan, Muhammad Haris},
      journal={arXiv preprint arXiv:2512.16415},
      year={2025}
    }


            

