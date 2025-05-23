![Static Badge](https://img.shields.io/badge/Build-Updating-blue)
[![Static Badge](https://img.shields.io/badge/PR-Welcome-orange)](https://github.com/seanzhuh/awesome-open-vocabulary-detection-and-segmentation/pulls)
[![Static Badge](https://img.shields.io/badge/%E7%9F%A5%E4%B9%8E-%E4%B8%AD%E6%96%87%E7%89%88-blue)](https://zhuanlan.zhihu.com/p/692846245)
<a href='https://arxiv.org/abs/2307.09220'>
    <img src='https://img.shields.io/badge/arXiv-PDF-green?style=flat&logo=arXiv&logoColor=green' alt='arXiv PDF'>
</a>
<p align="center">
  <h1 align="center"><a href='https://arxiv.org/abs/2307.09220'>A Survey on Open-Vocabulary Detection and Segmentation: Past, Present, and Future</a></h1>
  <p align="center">
    <a href="https://scholar.google.com/citations?user=jkxdiToAAAAJ&hl=en" style="text-decoration: none;">Chaoyang Zhu</a>,
    <a href="https://scholar.google.com/citations?hl=en&user=-gtmMpIAAAAJ" style="text-decoration: none;">Long Chen<sup>*</sup></a>
  </p>
<br>

## News

Please remain tuned, this repo will be maintained on a week-to-week basis.

* 27/06/2024: NeRF and 3DGS based 3D scene understanding is added.
* 05/06/2024: Our 2nd version manuscript is accepted by TPAMI.

<a id="ack"></a>
## Bibtex

If you find our survey helpful, please consider citing our paper:

```bibtex
@article{survey-ovd-ovs,
  title={A survey on open-vocabulary detection and segmentation: Past, present, and future},
  author={Zhu, Chaoyang and Chen, Long},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence},
  year={2024}
}
```

## :sparkles: PR is welcome!

Though we aim to cover every paper, still chances may happen that some works are missing. We believe the repository should be maintained by the community. Peer review is welcome and will be highly appreciated, if you are the authors and find our recordings incorrect, don't hesitate to contact me and fire a PR.

## General Overview

In this survey, we cover two settings (zero-shot and open-vocabulary) and six tasks (object detection, semantic/instance/panoptic segmentation, 3D scene understanding, and video understanding). We pivot on the permission to weak supervision signals and the usage of weak supervision signals to build a taxonomy that is universal across these diverse settings and tasks. The weak supervision signals can be image-text pairs or large vision-language models. Below is a general overview of each methodology.

<image src="figs/comp.png" width="50%" aligh="middle">

In current literature, zero-shot and open-vocabulary are used interchangeably, however, we highlight their subtle differences through the evolvement from traditional zero-shot to the newly formulated open-vocabulary setting.

<image src="figs/table.png" width="50%">

## Table of Contents

- [Zero-Shot Object Detection](#zsd)
  - [Visual-Semantic Space Mapping](#zsd-vssm)
  - [Novel Visual Feature Synthesis](#zsd-nvfs)
- [Zero-Shot Segmentation](#zss)
    - [Zero-Shot Semantic Segmentation](#zsss)
        - [Visual-Semantic Space Mapping](#zsss-vssm)
        - [Novel Visual Feature Synthesis](#zsss-nvfs)
    - [Zero-Shot Instance Segmentation](#zsis)
- [Open-Vocabulary Object Detection](#ovd)
    - [Region-Aware Training](#ovd-rat)
    - [Pseudo-Labeling](#ovd-pl)
    - [Knowledge Distillation](#ovd-kd)
    - [Transfer Learning](#ovd-tl)
- [Open-Vocabulary Segmentation](#ovs)
    - [Open-Vocabulary Semantic Segmentation](#ovss)
        - [Region-Aware Training](#ovss-rat)
        - [Pseudo-Labeling](#ovss-pl)
        - [Knowledge Distillation](#ovss-kd)
        - [Transfer Learning](#ovss-tl)
    - [Open-Vocabulary Instance Segmentation](#ovis)
        - [Region-Aware Training](#ovis-rat)
        - [Pseudo-Labeling](#ovis-pl)
        - [Knowledge Distillation](#ovis-kd)
    - [Open-Vocabulary Panoptic Segmentation](#ovps)
        - [Region-Aware Training](#ovps-rat)
        - [Knowledge Distillation](#ovps-kd)
        - [Transfer Learning](#ovps-tl)
- [Open-Vocabulary 3D Scene Understanding](#ov3d)
    - [Open-Vocabulary 3D Detection](#ov3d-det)
    - [Open-Vocabulary 3D Segmentation](#ov3d-seg)
        - [Open-Vocabulary 3D Semantic Segmentation](#ov3d-seg-sem)
        - [Open-Vocabulary 3D Instance Segmentation](#ov3d-seg-ins)
    - [NeRF and 3DGS based](#ov3d-nerf-3dgs)
- [Open-Vocabulary Video Understanding](#ovvu)
    - [Open-Vocabulary Video Instance Segmentation](#ovvu-seg-ins)
- [Acknowledgement](#ack)

<a id="zsd"></a>
## Zero-Shot Object Detection

<a id="zsd-vssm"></a>
### Visual-Semantic Space Mapping

|Venue|Paper Abbr|Full Title|Project|
|:-:|:-:|:-:|:-:|
|ECCV'18|[ZSDv1](https://arxiv.org/abs/1804.04340)|Zero-Shot Object Detection|N/A|
|ACCV'18 & IJCV'20|[ZSDv2](https://arxiv.org/abs/1803.06049)|Zero-Shot Object Detection: Learning to Simultaneously Recognize and Localize Novel Concepts|N/A|
|AAAI'20|[CA-ZSR](https://arxiv.org/abs/1904.09320)|Context-Aware Zero-Shot Recognition|[Code](https://github.com/ruotianluo/Context-aware-ZSR)|
|AAAI'19|[ZSD-TD](https://ojs.aaai.org/index.php/AAAI/article/view/4891)|Zero-Shot Object Detection with Textual Descriptions|N/A|
|ACCV'20|[BLC](https://arxiv.org/abs/2010.04502)|Background Learnable Cascade for Zero-Shot Object Detection|[Code](https://github.com/zhengye1995/BLC)|
|ICCV'19|[TL-ZSD](https://openaccess.thecvf.com/content_ICCV_2019/html/Rahman_Transductive_Learning_for_Zero-Shot_Object_Detection_ICCV_2019_paper.html)|Transductive Learning for Zero-Shot Object Detection|N/A|
|arXiv'23|[SSB](https://arxiv.org/abs/2302.07319)|Frustratingly Simple but Effective Zero-shot Detection and Segmentation: Analysis and a Strong Baseline|N/A|
|WACV'20|[MS-Zero](https://openaccess.thecvf.com/content_WACV_2020/papers/Gupta_A_Multi-Space_Approach_to_Zero-Shot_Object_Detection_WACV_2020_paper.pdf)|A Multi-Space Approach to Zero-Shot Object Detection|N/A|
|TCSVT'19|[ZS-YOLO](https://ieeexplore.ieee.org/abstract/document/8642945)|Zero Shot Detection|N/A|
|AAAI'21|[DPIF](https://ojs.aaai.org/index.php/AAAI/article/view/16295)|Inference Fusion with Associative Semantics for Unseen Object Detection|[Code](https://github.com/Lppy/DPIF)|
|TPAMI'21|[ContrastZSD](https://arxiv.org/abs/2109.06062)|Semantics-Guided Contrastive Network for Zero-Shot Object detection|N/A|
|IJCAI'20|[ZSD-CNN](https://www.ijcai.org/proceedings/2020/126)|Zero-Shot Object Detection via Learning an Embedding from Semantic Space to Visual Space|N/A|

<a id="zsd-nvfs"></a>
### Novel Visual Feature Synthesis

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|CVPR'20|[DELO](https://arxiv.org/abs/1911.07933)|Dont Even Look Once: Synthesizing Features for Zero-Shot Detection|N/A|
|ACCV'20|[SU](https://arxiv.org/abs/2010.09425)|Synthesizing the Unseen for Zero-shot Object Detection|[Code](https://github.com/nasir6/zero_shot_detection)|
|AAAI'20|[GTNet](https://arxiv.org/abs/2001.06812)|GTNet: Generative Transfer Network for Zero-Shot Object Detection|[Code](https://github.com/X-BrainLab/GTNet)|
|CVPR'22|[RRFS](https://arxiv.org/abs/2201.00103)|Robust Region Feature Synthesizer for Zero-Shot Object Detection|[Code](https://github.com/HPL123/RRFS)|

<a id="zss"></a>
## Zero-Shot Segmentation

<a id="zsss"></a>
### Zero-Shot Semantic Segmentation

<a id="zsss-vssm"></a>
#### Visual-Semantic Space Mapping

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|CVPR'20|[SPNet](https://ieeexplore.ieee.org/document/8953827)|Semantic Projection Network for Zero- and Few-Label Semantic Segmentation|[Code](https://github.com/subhc/SPNet)|
|NeurIPS'20|[ULZSS](https://proceedings.neurips.cc/paper/2020/hash/f73b76ce8949fe29bf2a537cfa420e8f-Abstract.html)|Uncertainty-Aware Learning for Zero-Shot Semantic Segmentation|[Code](https://github.com/feinanshan/ULZSS)|
|ICCV'21|[JoEm](https://arxiv.org/abs/2108.06536)|Exploiting a Joint Embedding Space for Generalized Zero-Shot Semantic Segmentation|[Code](https://github.com/cvlab-yonsei/JoEm)|
|ICCVW'19|[VM](https://ieeexplore.ieee.org/document/9022071)|Zero-Shot Semantic Segmentation via Variational Mapping|N/A|
|ICCV'21|[PMOSR](https://ieeexplore.ieee.org/document/9709966)|Prototypical Matching and Open Set Rejection for Zero-Shot Semantic Segmentation|N/A|

<a id="zsss-nvfs"></a>
#### Novel Visual Feature Synthesis

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|NeurIPS'19|[ZS3Net](https://arxiv.org/abs/1906.00817)|Zero-Shot Semantic Segmentation|[Code](https://github.com/valeoai/ZS3)|
|NeurIPS'20|[CSRL](https://proceedings.neurips.cc/paper/2020/hash/7504adad8bb96320eb3afdd4df6e1f60-Abstract.html)|Consistent Structural Relation Learning for Zero-Shot Segmentation|N/A|
|MM'20|[CaGNet](https://arxiv.org/abs/2008.06893)|Context-aware Feature Generation for Zero-shot Semantic Segmentation|[Code](https://github.com/bcmi/CaGNet-Zero-Shot-Semantic-Segmentation)|
|ICCV'21|[SIGN](https://arxiv.org/abs/2108.12517)|SIGN: Spatial-information Incorporated Generative Network for Generalized Zero-shot Semantic Segmentation|[Code](https://github.com/cplusx/SIGN)|

<a id="zsis"></a>
### Zero-Shot Instance Segmentation

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|CVPR'21|[ZSIS](https://arxiv.org/abs/2104.06601)|Zero-Shot Instance Segmentation|[Code](https://github.com/zhengye1995/Zero-shot-Instance-Segmentation)|

<a id="ovd"></a>
## Open-Vocabulary Object Detection

<a id="ovd-rat"></a>
### Region-Aware Training

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|CVPR'21|[OVR-CNN](https://arxiv.org/abs/2011.10678)|Open-Vocabulary Object Detection Using Captions|[Code](https://github.com/alirezazareian/ovr-cnn)|
|GCPR'22|[LocOv](https://arxiv.org/abs/2205.06160)|Localized Vision-Language Matching for Open-vocabulary Object Detection|[Code](https://github.com/lmb-freiburg/locov)|
|arXiv'23|[MMC-Det](https://arxiv.org/abs/2308.15846)|Exploring Multi-Modal Contextual Knowledge for Open-Vocabulary Object Detection|N/A|
|NeurIPS'22|[DetCLIP](https://arxiv.org/abs/2209.09407)|DetCLIP: Dictionary-Enriched Visual-Concept Paralleled Pre-training for Open-world Detection|N/A|
|CVPR'23|[DetCLIPv2](https://arxiv.org/abs/2304.04514)|DetCLIPv2: Scalable Open-Vocabulary Object Detection Pre-training via Word-Region Alignment|N/A|
|CVPR'24|[DetCLIPv3](https://arxiv.org/abs/2404.09216)|DetCLIPv3: Towards Versatile Generative Open-vocabulary Object Detection|N/A|
|AAAI'24|[WSOVOD](https://arxiv.org/abs/2312.12437)|Weakly Supervised Open-Vocabulary Object Detection|[Code](https://github.com/HunterJ-Lin/WSOVOD)|
|CVPR'23|[RO-ViT](https://arxiv.org/abs/2305.07011)|Region-Aware Pretraining for Open-Vocabulary Object Detection with Vision Transformers
|N/A|
|ICCV'23|[CFM-ViT](https://arxiv.org/abs/2309.00775)|Contrastive Feature Masking Open-Vocabulary Vision Transformer|N/A|
|ICCV'23|[DITO](https://arxiv.org/abs/2310.00161)|Detection-Oriented Image-Text Pretraining for Open-Vocabulary Detection|[Code](https://github.com/google-research/google-research/tree/master/fvlm/dito)|
|ICLR'23|[VLDet](https://arxiv.org/abs/2211.14843)|Learning Object-Language Alignments for Open-Vocabulary Object Detection|[Code](https://github.com/clin1223/VLDet)|
|ICCV'23|[GOAT](https://openaccess.thecvf.com/content/ICCV2023/papers/Wang_Open-Vocabulary_Object_Detection_With_an_Open_Corpus_ICCV_2023_paper.pdf)|Open-Vocabulary Object Detection With an Open Corpus
|N/A|
|ECCV'22|[OV-DETR](https://arxiv.org/abs/2203.11876)|Open-Vocabulary DETR with Conditional Matching[Code](https://github.com/yuhangzang/OV-DETR)|
|arXiv'23|[Prompt-OVD](https://arxiv.org/abs/2303.14386)|Prompt-Guided Transformers for End-to-End Open-Vocabulary Object Detection|N/A|
|CVPR'23|[CORA](https://arxiv.org/abs/2303.13076)|CORA: Adapting CLIP for Open-Vocabulary Detection with Region Prompting and Anchor Pre-Matching|N/A|
|ICCV'23|[EdaDet](https://arxiv.org/abs/2309.01151)|EdaDet: Open-Vocabulary Object Detection Using Early Dense Alignment|[Code](https://chengshiest.github.io/edadet/)|
|ICCV'21|[MDETR](https://arxiv.org/abs/2104.12763)|MDETR: Modulated Detection for End-to-End Multi-Modal Understanding|[Code](https://github.com/ashkamath/mdetr)|
|ECCV'22|[MAVL](https://arxiv.org/abs/2111.11430)|Class-agnostic Object Detection with Multi-modal Transformer|[Code](https://github.com/mmaaz60/mvits_for_class_agnostic_od)|
|NeurIPS'24|[MQ-Det](https://arxiv.org/abs/2305.18980)|Multi-modal Queried Object Detection in the Wild|[Code](https://github.com/YifanXu74/MQ-Det)|
|CVPR'24|[YOLO-World](https://www.yoloworld.cc/)|Real-Time Open-Vocabulary Object Detection|[Code](https://github.com/AILab-CVC/YOLO-World)|
|MM'23|[SGDN](http://arxiv.org/abs/2307.03339)|Open-Vocabulary Object Detection via Scene Graph Discovery|N/A|
|CVPR'24|[USE](https://openaccess.thecvf.com/content/CVPR2024/html/Wang_USE_Universal_Segment_Embeddings_for_Open-Vocabulary_Image_Segmentation_CVPR_2024_paper.html)|USE: Universal Segment Embeddings for Open-Vocabulary Image Segmentation|N/A|
|ICLR'25|[CCKT-Det](https://openreview.net/pdf?id=JU9oHs7ivN)|Cyclic Contrastive Knowledge Transfer for Open-Vocabulary Object Detection|[Code](https://github.com/ZCHUHan/CCKT-Det)|

<a id="ovd-pl"></a>
### Pseudo-Labeling

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|CVPR'22|[RegionCLIP](https://arxiv.org/abs/2112.09106)|RegionCLIP: Region-based Language-Image Pretraining|[Code](https://github.com/microsoft/RegionCLIP)|
|ECCV'22|[VL-PLM](https://arxiv.org/abs/2207.08954)|Exploiting Unlabeled Data with Vision and Language Models for Object Detection|[Code](https://github.com/xiaofeng94/VL-PLM)|
|CVPR'22|[GLIP](https://arxiv.org/pdf/2112.03857.pdf)|Grounded Language-Image Pre-training|[Code](https://github.com/microsoft/GLIP)|
|NeurIPS'22|[GLIPv2](https://arxiv.org/pdf/2206.05836.pdf)|GLIPv2: Unifying Localization and VL
Understanding
|[Code](https://github.com/microsoft/GLIP)|
|arXiv'23|[Grounding-DINO](https://arxiv.org/abs/2303.05499)|Grounding DINO: Marrying DINO with Grounded Pre-Training for Open-Set Object Detection|[Code](https://github.com/IDEA-Research/GroundingDINO)|
|ECCV'22|[PromptDet](https://arxiv.org/abs/2203.16513)|PromptDet: Towards Open-vocabulary Detection using Uncurated Images|[Code](https://github.com/fcjian/PromptDet)|
|arXiv'23|[SAS-Det](https://arxiv.org/abs/2308.06412)|Taming Self-Training for Open-Vocabulary Object Detection|[Code](https://github.com/xiaofeng94/sas-det)|
|ECCV'22|[PB-OVD](https://arxiv.org/abs/2111.09452)|Open Vocabulary Object Detection with Pseudo Bounding-Box Labels|[Code](https://github.com/salesforce/PB-OVD)|
|AAAI'24|[CLIM](https://arxiv.org/abs/2312.11376)|CLIM: Contrastive Language-Image Mosaic for Region Representation|[Code](https://github.com/wusize/CLIM)|
|arXiv'22|[VTP-OVD](https://arxiv.org/abs/2211.00849)|Fine-grained Visual-Text Prompt-Driven Self-Training for Open-Vocabulary Object Detection|N/A|
|AAAI'24|[ProxyDet](https://arxiv.org/abs/2312.07266)|ProxyDet: Synthesizing Proxy Novel Classes via Classwise Mixup for Open-Vocabulary Object Detection|[Code](https://github.com/clovaai/ProxyDet)|
|NeurIPS'23|[CoDet](https://arxiv.org/abs/2310.16667)|CoDet: Co-Occurrence Guided Region-Word Alignment for Open-Vocabulary Object Detection|[Code](https://github.com/cvmi-lab/codet)|
|ECCV'22|[Detic](https://arxiv.org/abs/2201.02605)|Detecting Twenty-thousand Classes using Image-level Supervision|[Code](https://github.com/facebookresearch/Detic)|
|ICML'23|[MMC](https://arxiv.org/abs/2306.05493)|Multi-Modal Classifiers for Open-Vocabulary Object Detection|[Code](https://github.com/prannaykaul/mm-ovod)|
|arXiv'23|[3Ways](https://arxiv.org/abs/2303.13518)|Three ways to improve feature alignment for open vocabulary detectio|N/A|
|arXiv'23|[PLAC](https://arxiv.org/abs/2312.02103)|Learning Pseudo-Labeler beyond Noun Concepts for Open-Vocabulary Object Detection|N/A|
|arXiv'23|[PCL](https://arxiv.org/abs/2303.13040)|Open-Vocabulary Object Detection using Pseudo Caption Labels
|N/A|
|NeurIPS'24|[OWLv2](arxiv.org/abs/2306.09683)|Scaling Open-Vocabulary Object Detection|[Code](https://github.com/google-research/scenic/tree/main/scenic/projects/owl_vit)|

<a id="ovd-kd"></a>
### Knowledge Distillation

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|ICLR'22|[ViLD](https://arxiv.org/abs/2104.13921)|Open-vocabulary Object Detection via Vision and Language Knowledge Distillation|[Code](https://github.com/tensorflow/tpu/tree/master/models/official/detection/projects/vild)|
|ICDMW'22|[ZSD-YOLO](https://arxiv.org/abs/2109.12066)|Zero-shot Object Detection Through Vision-Language Embedding Alignment|[Code](https://github.com/Johnathan-Xie/ZSD-YOLO)|
|WACV'24|[LP-OVOD](https://arxiv.org/abs/2310.17109)|LP-OVOD: Open-Vocabulary Object Detection by Linear Probing|[Code](https://github.com/VinAIResearch/LP-OVOD)|
|arXiv'23|[EZSD](https://arxiv.org/abs/2303.12145)|Efficient Feature Distillation for Zero-shot Annotation Object Detection|[Code](https://github.com/dragonlzm/EZAD)|
|AAAI'24|[SIC-CADS](https://arxiv.org/abs/2312.10439)|Simple Image-level Classification Improves Open-vocabulary Object Detection|[Code](https://github.com/mala-lab/sic-cads)|
|CVPR'23|[BARON](https://arxiv.org/abs/2302.13996)|Aligning Bag of Regions for Open-Vocabulary Object Detection|[Code](https://github.com/wusize/ovdet)|
|CVPR'23|[OADP](https://arxiv.org/abs/2303.05892)|Object-Aware Distillation Pyramid for Open-Vocabulary Object Detection|[Code](https://github.com/LutingWang/OADP)|
|arXiv'23|[GridCLIP](https://arxiv.org/abs/2303.09252)|GridCLIP: One-Stage Object Detection by Grid-Level CLIP Representation Learning|N/A|
|NeurIPS'22|[RKDWTF](https://arxiv.org/abs/2207.03482)|Bridging the Gap between Object and Image-level Representations for Open-Vocabulary Detection|[Code](https://github.com/hanoonaR/object-centric-ovd)|
|ICCV'23|[DK-DETR](https://openaccess.thecvf.com/content/ICCV2023/html/Li_Distilling_DETR_with_Visual-Linguistic_Knowledge_for_Open-Vocabulary_Object_Detection_ICCV_2023_paper.html)|Distilling DETR with Visual-Linguistic Knowledge for Open-Vocabulary Object Detection|[Code](https://github.com/hikvision-research/opera)|
|CVPR'22|[HierKD](https://arxiv.org/abs/2203.10593)|Open-Vocabulary One-Stage Detection with Hierarchical Visual-Language Knowledge Distillation|[Code](https://github.com/mengqiDyangge/HierKD)|
|CVPR'22|[DetPro](https://arxiv.org/abs/2203.14940)|Learning to Prompt for Open-Vocabulary Object Detection with Vision-Language Model|[Code](https://github.com/dyabel/detpro)|
|arXiv'23|[CLIPSelf](https://arxiv.org/abs/2310.01403)|CLIPSelf: Vision Transformer Distills Itself for Open-Vocabulary Dense Prediction|[Code](https://github.com/wusize/CLIPSelf)|
|CVPR'24|[SAMP](https://openaccess.thecvf.com/content/CVPR2024/html/Zhao_Scene-adaptive_and_Region-aware_Multi-modal_Prompt_for_Open_Vocabulary_Object_Detection_CVPR_2024_paper.html)|Scene-adaptive and Region-aware Multi-modal Prompt for Open Vocabulary Object Detection|N/A|
|IJCV'24|[OV-DAR](https://link.springer.com/article/10.1007/s11263-024-02144-1)|OV-DAR: Open-Vocabulary Object Detection and Attributes Recognition|N/A|
|CVPR'24|[LBP](https://openaccess.thecvf.com/content/CVPR2024/html/Li_Learning_Background_Prompts_to_Discover_Implicit_Knowledge_for_Open_Vocabulary_CVPR_2024_paper.html)|Learning Background Prompts to Discover Implicit Knowledge for Open Vocabulary Object Detection|N/A|

<a id="ovd-tl"></a>
### Transfer Learning

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|ECCV'22|[OWL-ViT](https://arxiv.org/abs/2205.06230)|Simple Open-Vocabulary Object Detection with Vision Transformers|[Code](https://github.com/google-research/scenic/tree/main/scenic/projects/owl_vit)|
|CVPR'23|[UniDetector](https://arxiv.org/abs/2303.11749)|Detecting Everything in the Open World: Towards Universal Object Detection|[Code](https://github.com/zhenyuw16/UniDetector)|
|ICLR'23|[F-VLM](https://arxiv.org/abs/2209.15639)|F-VLM: Open-Vocabulary Object Detection upon Frozen Vision and Language Models|[Code](https://github.com/google-research/google-research/tree/master/fvlm)|
|CVPR'23|[ScaleDet](https://arxiv.org/abs/2306.04849)|ScaleDet: A Scalable Multi-Dataset Object Detector|N/A|
|ICCV'23|[OpenSeed](https://arxiv.org/abs/2303.08131)|A Simple Framework for Open-Vocabulary Segmentation and Detection|[Code](https://github.com/IDEA-Research/OpenSeeD)|
|arXiv'23|[DRR](https://arxiv.org/abs/2309.00227)|What Makes Good Open-Vocabulary Detector: A Disassembling Perspective|N/A|
|arXiv'23|[Sambor](https://arxiv.org/abs/2312.03628)|Boosting Segment Anything Model Towards Open-Vocabulary Learning|[Code](https://github.com/ucas-vg/Sambor)|
|AAAI'25|[LAE-DINO](https://arxiv.org/abs/2408.09110)|Locate Anything on Earth: Advancing Open-Vocabulary Object Detection for Remote Sensing Community|[Code](https://github.com/jaychempan/LAE-DINO)|

<a id="ovs"></a>
## Open-Vocabulary Segmentation

<a id="ovss"></a>
### Open-Vocabulary Semantic Segmentation

<a id="ovss-rat"></a>
#### Region-Aware Training

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|ECCV'22|[OpenSeg](https://arxiv.org/abs/2112.12143)|Scaling Open-Vocabulary Image Segmentation with Image-Level Labels|N/A|
|arXiv'23|[SLIC](https://arxiv.org/abs/2310.13355)|SILC: Improving Vision Language Pretraining with Self-Distillation|N/A|
|CVPR'22|[GroupViT](https://arxiv.org/abs/2202.11094)|GroupViT: Semantic Segmentation Emerges from Text Supervision|[Code](https://github.com/NVlabs/GroupViT)|
|ECCV'22|[ViL-Seg](https://arxiv.org/abs/2207.08455)|Open-world Semantic Segmentation via Contrasting and Clustering Vision-Language Embedding|N/A|
|ICML'23|[SegCLIP](https://arxiv.org/abs/2211.14813)|SegCLIP: Patch Aggregation with Learnable Centers for Open-Vocabulary Semantic Segmentation|[Code](https://github.com/ArrowLuo/SegCLIP)|
|CVPR'23|[OVSegmentor](https://arxiv.org/abs/2301.09121)|Learning Open-vocabulary Semantic Segmentation Models From Natural Language Supervision|[Code](https://github.com/Jazzcharles/OVSegmentor/)|
|CVPR'23|[PACL](https://arxiv.org/abs/2212.04994)|Open Vocabulary Semantic Segmentation with Patch Aligned Contrastive Learning|N/A|
|CVPR'23|[TCL](https://arxiv.org/abs/2212.00785)|Learning to Generate Text-grounded Mask for Open-world Semantic Segmentation from Only Image-Text Pairs
|[Code](https://github.com/kakaobrain/tcl)|
|ECCV'22|[SimSeg](https://arxiv.org/abs/2112.14757)|A Simple Baseline for Open-Vocabulary Semantic Segmentation with Pre-trained Vision-language Model|[Code](https://github.com/MendelXu/zsseg.baseline)|

<a id="ovss-pl"></a>
#### Pseudo-Labeling

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|ECCV'22|[TTD](https://link.springer.com/chapter/10.1007/978-3-031-25063-7_4)|Open-Vocabulary Semantic Segmentation Using Test-Time Distillation|N/A|

<a id="ovss-kd"></a>
#### Knowledge Distillation

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|arXiv'23|[GKC](https://arxiv.org/abs/2303.09181)|Global Knowledge Calibration for Fast Open-Vocabulary Segmentation|N/A|
|arXiv'23|[SAM-CLIP](https://arxiv.org/abs/2310.15308)|SAM-CLIP: Merging Vision Foundation Models towards Semantic and Spatial Understanding|N/A|
|ICCV'23|[ZeroSeg](https://ieeexplore.ieee.org/document/10378186)|Exploring Open-Vocabulary Semantic Segmentation from CLIP Vision Encoder Distillation Only|[Code](https://github.com/facebookresearch/ZeroSeg)|

<a id="ovss-tl"></a>
#### Transfer Learning

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|ICLR'22|[LSeg](https://arxiv.org/abs/2201.03546)|Language-driven Semantic Segmentation|[Code](https://github.com/isl-org/lang-seg)|
|CVPR'23|[SAZS](https://openaccess.thecvf.com/content/CVPR2023/html/Liu_Delving_Into_Shape-Aware_Zero-Shot_Semantic_Segmentation_CVPR_2023_paper.html)|Delving Into Shape-Aware Zero-Shot Semantic Segmentation|[Code](https://github.com/Liuxinyv/SAZS)|
|MM'23|[CEL](https://arxiv.org/abs/2301.07336)|Class Enhancement Losses with Pseudo Labels for Zero-shot Semantic Segmentation|N/A|
|CVPR'22|[ZegFormer](https://arxiv.org/abs/2112.07910)|Decoupling Zero-Shot Semantic Segmentation|[Code](https://github.com/dingjiansw101/ZegFormer)|
|NeurIPS'22|[ReCo](https://arxiv.org/abs/2206.07045)|ReCo: Retrieve and Co-segment for Zero-shot Transfer|[Project](https://www.robots.ox.ac.uk/~vgg/research/reco/)|
|arXiv'23|[SCAN](https://arxiv.org/abs/2312.04089)|Open-Vocabulary Segmentation with Semantic-Assisted Calibration|N/A|
|ECCV'22|[ZSSeg](https://arxiv.org/abs/2112.14757)|A Simple Baseline for Open-Vocabulary Semantic Segmentation with Pre-trained Vision-language Model|[Code](https://github.com/MendelXu/zsseg.baseline)|
|ECCV'22|[MaskCLIP](https://arxiv.org/abs/2112.01071)|Extract Free Dense Labels from CLIP|[Code](https://github.com/chongzhou96/MaskCLIP)|
|arXiv'23|[CLIP-DINOiser](https://arxiv.org/abs/2312.12359)|CLIP-DINOiser: Teaching CLIP a few DINO tricks for open-vocabulary semantic segmentation|[Code](https://github.com/wysoczanska/clip_dinoiser)|
|PRCV'23|[MVP-SEG](https://arxiv.org/abs/2304.06957)|MVP-SEG: Multi-View Prompt Learning for Open-Vocabulary Semantic Segmentation|N/A|
|arXiv'23|[OVDiff](https://arxiv.org/abs/2306.09316)|Diffusion Models for Zero-Shot Open-Vocabulary Segmentation|[Project](https://www.robots.ox.ac.uk/~vgg/research/ovdiff/)|
|WACV'24|[FOSSIL](https://openaccess.thecvf.com/content/WACV2024/html/Barsellotti_FOSSIL_Free_Open-Vocabulary_Semantic_Segmentation_Through_Synthetic_References_Retrieval_WACV_2024_paper.html)|FOSSIL: Free Open-Vocabulary Semantic Segmentation Through Synthetic References Retrieval|N/A|
|NeurIPS'24|[POMP](https://arxiv.org/abs/2304.04704)|Prompt Pre-Training with Twenty-Thousand Classes for Open-Vocabulary Visual Recognition|[Code](https://github.com/amazon-science/prompt-pretraining)|
|NeurIPS'24|[AttrSeg](https://arxiv.org/abs/2309.00096)|AttrSeg: Open-Vocabulary Semantic Segmentation via Attribute Decomposition-Aggregation|N/A|
|arXiv'23|[PnP-OVSS](https://arxiv.org/abs/2311.17095)|Emergent Open-Vocabulary Semantic Segmentation from Off-the-shelf Vision-Language Models|[Code](https://github.com/letitiabanana/PnP-OVSS)|
|arXiv'23|[TagAlign](https://arxiv.org/abs/2312.14149)|TagAlign: Improving Vision-Language Alignment with Multi-Tag Classification|[Project](https://qinying-liu.github.io/Tag-Align/)|
|arXiv'23|[SelfSeg](https://arxiv.org/abs/2312.04539)|Auto-Vocabulary Semantic Segmentation|N/A|
|CVPR'22|[DenseCLIP](https://arxiv.org/abs/2112.01518)|DenseCLIP: Language-Guided Dense Prediction with Context-Aware Prompting|[Code](https://github.com/raoyongming/DenseCLIP)|
|CVPR'23|[OVSeg](https://arxiv.org/abs/2210.04150)|Open-Vocabulary Semantic Segmentation with Mask-adapted CLIP|[Code](https://github.com/facebookresearch/ov-seg)|
|arXiv'23|[CAT-Seg](https://arxiv.org/abs/2303.11797)|CAT-Seg: Cost Aggregation for Open-Vocabulary Semantic Segmentation|[Code](https://github.com/KU-CVLAB/CAT-Seg)|
|arXiv'23|[SED](https://arxiv.org/abs/2311.15537)|SED: A Simple Encoder-Decoder for Open-Vocabulary Semantic Segmentation|[Code](https://github.com/xb534/SED)|
|NeurIPS'23|[MAFT](https://openreview.net/forum?id=K1Uzj8tuwd)|Learning Mask-aware CLIP Representations for Zero-Shot Segmentation|[Code](https://github.com/jiaosiyu1999/MAFT)|
|arXiv'23|[TagCLIP](https://arxiv.org/abs/2304.07547)|TagCLIP: Improving Discrimination Ability of Open-Vocabulary Semantic Segmentation|N/A|
|CVPR'23|[ZegCLIP](https://openaccess.thecvf.com/content/CVPR2023/html/Zhou_ZegCLIP_Towards_Adapting_CLIP_for_Zero-Shot_Semantic_Segmentation_CVPR_2023_paper.html)|ZegCLIP: Towards Adapting CLIP for Zero-Shot Semantic Segmentation|[Code](https://github.com/ZiqinZhou66/ZegCLIP.git)|
|CVPR'22|[CLIPSeg](https://arxiv.org/abs/2112.10003)|Image Segmentation Using Text and Image Prompts|[Code](https://github.com/timojl/clipseg)|
|CVPR'23|[SAN](https://arxiv.org/abs/2302.12242)|Side Adapter Network for Open-Vocabulary Semantic Segmentation|[Code](https://github.com/MendelXu/SAN)|
|arXiv'23|[CLIP Surgery](https://arxiv.org/abs/2304.05653)|CLIP Surgery for Better Explainability with Enhancement in Open-Vocabulary Tasks|[Code](https://github.com/xmed-lab/CLIP_Surgery)|
|arXiv'23|[CaR](https://arxiv.org/abs/2312.07661)|CLIP as RNN: Segment Countless Visual Concepts without Training Endeavor|[Project](https://torrvision.com/clip_as_rnn/)|
|arXiv'24|[Cascade-CLIP](https://arxiv.org/abs/2406.00670)|Cascade-CLIP: Cascaded Vision-Language Embeddings Alignment for Zero-Shot Semantic Segmentation|[Code](https://github.com/HVision-NKU/Cascade-CLIP)|
|arXiv'24|[OpenDAS](https://arxiv.org/abs/2405.20141)|OpenDAS: Domain Adaptation for Open-Vocabulary Segmentation|[Project](https://goncayilmaz.github.io/opendas/)|
|arXiv'24|[H-CLIP](https://arxiv.org/pdf/2405.18840)|Parameter-efficient Fine-tuning in Hyperspherical
Space for Open-vocabulary Semantic Segmentation|N/A|

<a id="ovis"></a>
### Open-Vocabulary Instance Segmentation

<a id="ovis-rat"></a>
#### Region-Aware Training

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|ICCV'23|[CGG](https://arxiv.org/abs/2301.00805)|Betrayed by Captions: Joint Caption Grounding and Generation for Open Vocabulary Instance Segmentation|[Code](https://github.com/jianzongwu/betrayed-by-captions)|
|CVPR'23|[D2Zero](https://henghuiding.github.io/D2Zero/)|Semantic-Promoted Debiasing and Background Disambiguation for Zero-Shot Instance Segmentation|[Code](https://github.com/heshuting555/D2Zero)|

<a id="ovis-pl"></a>
#### Pseudo-Labeling

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|CVPR'23|[XPM](https://arxiv.org/abs/2111.12698)|Open-Vocabulary Instance Segmentation via Robust Cross-Modal Pseudo-Labeling|[Code](https://github.com/hbdat/cvpr22_cross_modal_pseudo_labeling)|
|CVPR'23|[Mask-free OVIS](https://arxiv.org/abs/2303.16891)|Mask-free OVIS: Open-Vocabulary Instance Segmentation without Manual Mask Annotations|[Code](https://github.com/Vibashan/Maskfree-OVIS)|
|arXiv'23|[MosaicFusion](https://arxiv.org/abs/2309.13042)|MosaicFusion: Diffusion Models as Data Augmenters for Large Vocabulary Instance Segmentation|[Code](https://github.com/Jiahao000/MosaicFusion)|

<a id="ovis-kd"></a>
#### Knowledge Distillation

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|arXiv'24|[OV-SAM](https://arxiv.org/abs/2401.02955)|Open-Vocabulary SAM: Segment and Recognize Twenty-thousand Classes Interactively|[Code](https://github.com/HarborYuan/ovsam)|

<a id="ovps"></a>
### Open-Vocabulary Panoptic Segmentation

<a id="ovps-rat"></a>
#### Region-Aware Training

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|arXiv'24|[Uni-OVSeg](https://arxiv.org/abs/2402.08960)|Open-Vocabulary Segmentation with Unpaired Mask-Text Supervision|[Code](https://github.com/DerrickWang005/Uni-OVSeg.pytorch)|
|CVPR'23|[X-Decoder](https://arxiv.org/abs/2212.11270)|Generalized Decoding for Pixel, Image, and Language|[Code](https://github.com/microsoft/X-Decoder/tree/main)|
|CVPR'24|[APE](https://arxiv.org/abs/2312.02153)|Learning active tactile perception through belief-space control|[Code](https://github.com/shenyunhang/APE)|

<a id="ovps-kd"></a>
#### Knowledge Distillation

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|CVPR'23|[PADing](https://henghuiding.github.io/PADing/)|Primitive Generation and Semantic-related Alignment for Universal Zero-Shot Segmentation|[Code](https://github.com/heshuting555/PADing)|

<a id="ovps-tl"></a>
#### Transfer Learning

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|NeurIPS'23|[FC-CLIP](https://arxiv.org/abs/2308.02487)|Convolutions Die Hard: Open-Vocabulary Segmentation with Single Frozen Convolutional CLIP|[Code](https://github.com/bytedance/fc-clip)|
|CVPR'23|[FreeSeg](https://arxiv.org/abs/2303.17225)|FreeSeg: Unified, Universal and Open-Vocabulary Image Segmentation|[Project](https://freeseg.github.io/)|
|arXiv'24|[PosSAM](https://arxiv.org/abs/2403.09620)|PosSAM: Panoptic Open-vocabulary Segment Anything|[Project](https://vibashan.github.io/possam-web/)|
|ICCV'23|[MasQCLIP](https://openaccess.thecvf.com/content/ICCV2023/papers/Xu_MasQCLIP_for_Open-Vocabulary_Universal_Image_Segmentation_ICCV_2023_paper.pdf)|MasQCLIP for Open-Vocabulary Universal Image Segmentation|[Project](https://masqclip.github.io/)|
|CVPR'23|[OMG-Seg](https://arxiv.org/abs/2401.10229)|OMG-Seg: Is One Model Good Enough For All Segmentation?|[Code](https://github.com/lxtGH/OMG-Seg)|
|arXiv'23|[Semantic-SAM](https://arxiv.org/abs/2307.04767)|Semantic-SAM: Segment and Recognize Anything at Any Granularity|[Code](https://github.com/UX-Decoder/Semantic-SAM)|
|CVPR'23|[ODISE](https://arxiv.org/abs/2303.04803)|Open-Vocabulary Panoptic Segmentation with Text-to-Image Diffusion Models|[Code](https://github.com/NVlabs/ODISE)|
|NeurIPS'23|[HIPIE](https://arxiv.org/abs/2307.00764)|Hierarchical Open-vocabulary Universal Image Segmentation|[Code](https://github.com/berkeley-hipie/HIPIE)|
|ICML'23|[MaskCLIP](https://arxiv.org/abs/2208.08984)|Open-Vocabulary Universal Image Segmentation with MaskCLIP|[Project](https://maskclip.github.io/)|
|ICCV'23|[OPSNet](https://arxiv.org/abs/2303.11324)|Open-vocabulary Panoptic Segmentation with Embedding Modulation|N/A|

<a id="ov3d"></a>
## Open-Vocabulary 3D Scene Understanding

<a id="ov3d-det"></a>
### Open-Vocabulary 3D Detection

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|CVPR'23|[OV-3DET](https://arxiv.org/abs/2304.00788v2)|Open-Vocabulary Point-Cloud Object Detection without 3D Annotation|[Code](https://github.com/lyhdet/OV-3DET)|
|AAAI'24|[FM-OV3D](https://arxiv.org/abs/2312.14465)|FM-OV3D: Foundation Model-based Cross-modal Knowledge Blending for Open-Vocabulary 3D Detection|[Code](https://github.com/dmzhang0425/FM-OV3D)|
|arXiv'23|[OpenSight](https://arxiv.org/abs/2312.08876)|OpenSight: A Simple Open-Vocabulary Framework for LiDAR-Based Object Detection|N/A|
|NeurIPS'23|[CoDA](https://arxiv.org/abs/2310.02960)|CoDA: Collaborative Novel Box Discovery and Cross-modal Alignment for Open-vocabulary 3D Object Detection|[Code](https://github.com/yangcaoai/CoDA_NeurIPS2023)|
|arXiv'23|[L3Det](https://arxiv.org/abs/2309.09456)|Object2Scene: Putting Objects in Context for Open-Vocabulary 3D Detection|N/A|

<a id="ov3d-seg"></a>
### Open-Vocabulary 3D Segmentation

<a id="ov3d-seg-sem"></a>
#### Open-Vocabulary 3D Semantic Segmentation

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|arXiv'21|[SeCondPoint](https://arxiv.org/abs/2107.00430)|Language-Level Semantics Conditioned 3D Point Cloud Segmentation|N/A|
|3DV'21|[3DGenZ](https://arxiv.org/abs/2108.06230)|Generative Zero-Shot Learning for Semantic Segmentation of 3D Point Clouds|[Code](https://github.com/valeoai/3DGenZ)|
|CVPR'23|[OpenScene](https://arxiv.org/abs/2211.15654)|OpenScene: 3D Scene Understanding with Open Vocabularies|[Project](https://pengsongyou.github.io/openscene)|
|CVPR'23|[PLA](https://arxiv.org/abs/2211.16312)|PLA: Language-Driven Open-Vocabulary 3D Scene Understanding
|[Code](https://dingry.github.io/projects/PLA)|
|arXiv'23|[RegionPLC](https://arxiv.org/abs/2304.00962)|RegionPLC: Regional Point-Language Contrastive Learning for Open-World 3D Scene Understanding|[Project](https://jihanyang.github.io/projects/RegionPLC)|

<a id="ov3d-seg-ins"></a>
#### Open-Vocabulary 3D Instance Segmentation

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|NeurIPS'23|[OpenMask3D](https://arxiv.org/abs/2306.13631)|OpenMask3D: Open-Vocabulary 3D Instance Segmentation|[Project](https://openmask3d.github.io/)|
|CVPR'24|[MaskClustering](https://arxiv.org/abs/2401.07745)|MaskClustering: View Consensus based Mask Graph Clustering for Open-Vocabulary 3D Instance Segmentation|[Project](https://pku-epic.github.io/MaskClustering/)|
|arXiv'23|[OpenIns3D](https://arxiv.org/abs/2309.00616)|OpenIns3D: Snap and Lookup for 3D Open-vocabulary Instance Segmentation|[Project](https://zheninghuang.github.io/OpenIns3D/)|
|arXiv'23|[Open3DIS](https://arxiv.org/abs/2312.10671)|Open3DIS: Open-Vocabulary 3D Instance Segmentation with 2D Mask Guidance|[Project](https://open3dis.github.io)|
|arXiv'24|[OpenSU3D](https://arxiv.org/abs/2407.14279)|OpenSU3D: Open World 3D Scene Understanding using Foundation Models|[Project](https://opensu3d.github.io/)|
|arXiv'24|[Search3D](https://arxiv.org/abs/2409.18431)|Search3D: Hierarchical Open-Vocabulary 3D Segmentation|N/A|
<!-- |CVPR'23|[CLIP2Scene](https://arxiv.org/abs/2301.04926)|[Code](https://github.com/runnanchen/CLIP2Scene)|
|2023|ICCVW|[CLIP-FO3D](https://arxiv.org/abs/2303.04748)|N/A|
|arXiv'24|[UniM-OV3D](https://arxiv.org/abs/2401.11395)|[Code](https://github.com/hithqd/UniM-OV3D)|
|arXiv'22|[Open-Vocabulary 3D Detection via Image-level Class and Debiased Cross-modal Contrastive Learning](https://arxiv.org/abs/2207.01987)|N/A| -->

<a id="ov3d-nerf-3dgs"></a>
### NeRF and 3DGS based

NeRF ([Neural Radiance Field](https://dl.acm.org/doi/abs/10.1145/3503250)) and 3DGS ([3D Gaussian Splatting](https://arxiv.org/abs/2308.04079)) are hot topics for novel view synthesis in a holistic scene. They leverage multi-view consistency learning inherently imposed in the 3D model to help 2D image segmentation or directly perform 3D semantic segmentation over points (voxel or gaussian) in the scene.

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|ICCV'21|[Semantic-NeRF](https://openaccess.thecvf.com/content/ICCV2021/html/Zhi_In-Place_Scene_Labelling_and_Understanding_With_Implicit_Scene_Representation_ICCV_2021_paper.html?ref=https://githubhelp.com)|In-Place Scene Labelling and Understanding With Implicit Scene Representation|[Code](https://github.com/Harry-Zhi/semantic_nerf)|
|NeurIPS'22|[FFD](https://proceedings.neurips.cc/paper_files/paper/2022/hash/93f250215e4889119807b6fac3a57aec-Abstract-Conference.html)|Decomposing NeRF for Editing via Feature Field Distillation|[Code](https://github.com/pfnet-research/distilled-feature-fields)|
|arXiv'23|[Gaussian Grouping](https://arxiv.org/abs/2312.00732)|Gaussian Grouping: Segment and Edit Anything in 3D Scenes|[Code](https://github.com/lkeab/gaussian-grouping)|
|ICCV'23|[LERF](https://openaccess.thecvf.com/content/ICCV2023/html/Kerr_LERF_Language_Embedded_Radiance_Fields_ICCV_2023_paper.html?trk=public_post_comment-text)|LERF: Language Embedded Radiance Fields|[Project](https://lerf.io)|
|NeurIPS'23|[3DOVS](https://proceedings.neurips.cc/paper_files/paper/2023/hash/a76b693f36916a5ed84d6e5b39a0dc03-Abstract-Conference.html)|Weakly Supervised 3D Open-vocabulary Segmentation|[Code](https://github.com/Kunhao-Liu/3D-OVS)|
|arXiv'24|[OpenGaussian](https://arxiv.org/abs/2406.02058)|OpenGaussian: Towards Point-Level 3D Gaussian-based Open Vocabulary Understanding|[Project](https://3d-aigc.github.io/OpenGaussian/)|
|arXiv'24|[OV-NeRF](https://arxiv.org/abs/2402.04648)|OV-NeRF: Open-vocabulary Neural Radiance Fields with Vision and Language Foundation Models for 3D Semantic Understanding|[Code](https://github.com/pcl3dv/OV-NeRF)|
|arXiv'24|[Semantic Gaussians](https://arxiv.org/abs/2403.15624)|Semantic Gaussians: Open-Vocabulary Scene Understanding with 3D Gaussian Splatting|[Project](https://semantic-gaussians.github.io/)|
|arXiv'24|[FMGS](https://arxiv.org/abs/2401.01970)|FMGS: Foundation Model Embedded 3D Gaussian Splatting for Holistic 3D Scene Understanding|[Project](https://xingxingzuo.github.io/fmgs/)|
|CVPR'24|[LEGaussians](https://openaccess.thecvf.com/content/CVPR2024/html/Shi_Language_Embedded_3D_Gaussians_for_Open-Vocabulary_Scene_Understanding_CVPR_2024_paper.html)|Language Embedded 3D Gaussians for Open-Vocabulary Scene Understanding|[Code](https://github.com/buaavrcg/LEGaussians)|
|CVPR'24|[LangSplat](https://openaccess.thecvf.com/content/CVPR2024/html/Qin_LangSplat_3D_Language_Gaussian_Splatting_CVPR_2024_paper.html)|LangSplat: 3D Language Gaussian Splatting|[Project](https://langsplat.github.io/)|
|CVPR'24|[Feature 3DGS](https://openaccess.thecvf.com/content/CVPR2024/html/Zhou_Feature_3DGS_Supercharging_3D_Gaussian_Splatting_to_Enable_Distilled_Feature_CVPR_2024_paper.html)|Feature 3DGS: Supercharging 3D Gaussian Splatting to Enable Distilled Feature Fields|[Code](https://github.com/ShijieZhou-UCLA/feature-3dgs)|

<a id="ovvu"></a>
## Open-Vocabulary Video Understanding

<a id="ovvu-seg-ins"></a>
### Open-Vocabulary Video Instance Segmentation

|Venue|Paper Abbr|Paper Title|Project|
|:-:|:-:|:-:|:-:|
|ICCV'23|[OV2Seg](https://arxiv.org/abs/2304.01715)|Towards Open-Vocabulary Video Instance Segmentation|[Code](https://github.com/haochenheheda/LVVIS)|
|arXiv'23|[OpenVIS](https://arxiv.org/abs/2305.16835)|OpenVIS: Open-vocabulary Video Instance Segmentation|[Code](https://github.com/sennnnn/OpenVIS)|
|arXiv'24|[BriVIS](https://arxiv.org/abs/2401.09732)|Instance Brownian Bridge as Texts for Open-vocabulary Video Instance Segmentation|[Code](https://github.com/sennnnn/OpenVIS)|

<!-- |arXiv'23|[Segment Everything Everywhere All at Once](https://arxiv.org/abs/2304.06718)|[Code](https://github.com/UX-Decoder/Segment-Everything-Everywhere-All-At-Once)|
|arXiv'23|[Exploring Open-Vocabulary Semantic Segmentation without Human Labels](https://arxiv.org/abs/2306.00450)|N/A|
|arXiv'23|[DaTaSeg](https://arxiv.org/abs/2306.01736)|N/A|
|ICCV'23|[Diffumask](https://arxiv.org/abs/2303.11681)|[Project](https://weijiawu.github.io/DiffusionMask/)|
|ICCV'23|[Guiding Text-to-Image Diffusion Model Towards Grounded Generation](https://arxiv.org/abs/2301.05221)|[Project](https://lipurple.github.io/Grounded_Diffusion/)|
|NeurIPS'23|[Uncovering Prototypical Knowledge for Weakly Open-Vocabulary Semantic Segmentation](https://arxiv.org/abs/2310.19001)|[Code](https://github.com/Ferenas/PGSeg)|
|arXiv'23|[Grounding Everything: Emerging Localization Properties in Vision-Language Transformers](https://arxiv.org/abs/2312.00878)|[Code](https://github.com/WalBouss/GEM)| -->
