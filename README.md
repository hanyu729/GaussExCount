# GaussExCount: Text-Guided Gaussian Mask Exemplar for Zero-Shot Counting
# 1. GaussExCount
Recently, zero-shot counting has gained increasing attention, where text prompts are used to flexibly specify counting objects. However, text descriptions are inherently abstract and lack sufficient detail to capture fine-grained visual characteristics, severely limiting model performance. To address this issue, we propose GaussExCount, a text-guided Gaussian-masked exemplar framework for zero-shot counting. It constructs visual exemplars in feature space to overcome the limitations of purely text prompts. Specifically, a Contrastive Score Modulation Module (CSMM) performs fine-grained alignment between image features and multi-category text tokens to construct dense semantic response maps, which are subsequently refined via spatial smoothing to obtain stable target responses. Based on the resulting high-response regions, an Exemplar Generation Module (EGM) predicts anisotropic Gaussian distributions to perform spatially weighted aggregation of local features, thereby generating exemplar representations. The generated exemplars capture multi-scale object structures, improving the model’s robustness in complex scenarios, particularly under interference from visually similar categories and high-density environments. Extensive experiments on multiple benchmark datasets demonstrate that the proposed method achieves superior generalization and counting accuracy compared with state-of-the-art approaches.

# 2. Result
| ![Image 1](https://github.com/hanyu729/GaussExCount/raw/main/Figs/fig1.png) |
|--------------------------------------------|
| *Figure 1: Visualization of multi-class counting results on the FSC-147 dataset. From top to bottom are the results produced by CountSE, T2ICount, and GaussExCount, respectively.*       |
As illustrated in the example containing cans and tomatoes, although the two object categories exhibit significant scale differences, they still share similar colors and local texture patterns, which can easily lead to category confusion. Nevertheless, GaussExCount is still able to accurately focus on the target regions corresponding to the text prompts while effectively suppressing interference from non-target categories. 
| ![Image 2](https://github.com/hanyu729/GaussExCount/raw/main/Figs/fig2.png) |
|--------------------------------------------|
| *Figure 2: Visualization of counting results on the AdaFishCount-Dataset and the ShanghaiTech Part A dataset. From top to bottom are the results produced by CountSE, T2ICount, and GaussExCount, respectively.*       |
In the high-density scenes of ShanghaiTech Part A, although a large number of distant persons occupy only a few pixels and are accompanied by severe occlusions and scale variations, GaussExCount still maintains reliable responses to these small-scale targets and achieves satisfactory counting accuracy. Furthermore, in the cage scenario of the AdaFishCount-Dataset, GaussExCount is able to effectively distinguish target fish from complex underwater backgrounds, whereas T2ICount tends to misclassify extensive background regions as target objects, resulting in severe counting errors.

# 3. Model
**For training/inference, please go to [here](https://github.com/hanyu729/GaussExCount/raw/main/GaussExCount/readme)**


