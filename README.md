# tiny_netdissect

A step by step reproduction of **Network Dissection: Quantifying Interpretability of Deep Visual Representations** (Bau, Zhou, Khosla, Oliva, Torralba, CVPR 2017).

## The article

Network Dissection measures how interpretable the units of a convolutional network are. Every unit is treated as a binary segmenter and compared with pixel annotations of 1 197 visual concepts from the Broden dataset. A unit whose masks overlap a concept with IoU above 0.04 is a detector for that concept, and a layer is summarized by its number of unique detected concepts.

Paper: [arXiv:1704.05796](https://arxiv.org/abs/1704.05796), [CVPR 2017 open access](https://openaccess.thecvf.com/content_cvpr_2017/html/Bau_Network_Dissection_Quantifying_CVPR_2017_paper.html), local copy [`Network_dissection.pdf`](Network_dissection.pdf). Original code: [CSAILVision/NetDissect](https://github.com/CSAILVision/NetDissect).

## Plan

The method is rebuilt one step at a time, one notebook per step, each with a small side by side comparison:

1. the Broden dataset and how its labels are stored
2. units and their activation maps, read with forward hooks
3. concepts as pixel masks
4. the per unit threshold that turns a map into a mask
5. upsampling unit maps to mask resolution, anchored at receptive field centers

## Citation

D. Bau, B. Zhou, A. Khosla, A. Oliva, A. Torralba. *Network Dissection: Quantifying Interpretability of Deep Visual Representations*. Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2017, pp. 6541-6549.

```bibtex
@InProceedings{Bau_2017_CVPR,
  author    = {Bau, David and Zhou, Bolei and Khosla, Aditya and Oliva, Aude and Torralba, Antonio},
  title     = {Network Dissection: Quantifying Interpretability of Deep Visual Representations},
  booktitle = {Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
  month     = {July},
  year      = {2017},
  pages     = {6541--6549}
}
```
