## Introduction
  As a widely used loss function in deep face recognition, the softmax loss cannot guarantee that the minimum positive sample-to-class similarity is larger than the maximum negative sample-to-class similarity. As a result, no unified threshold is available to separate positive sample-to-class pairs from negative sample-to-class pairs. To bridge this gap, we design a UCE (Unified Cross-Entropy) loss for face recognition model training, which is built on the vital constraint that all the positive sample-to-class similarities shall be larger than the negative ones. Our UCE loss can be integrated with margins for a further performance boost. The face recognition model trained with the proposed UCE loss, UniFace, was ntensively evaluated using a number of popular public datasets like MFR, IJB-C, LFW, CFPFP, AgeDB, and MegaFace. Experimental results show that our approach outperforms SOTA methods like SphereFace, CosFace, ArcFace, Partial FC, etc. Especially, till the submission of this work (Mar. 8, 2023), the proposed UniFace achieves the highest TAR@MR-All on the academic track of the MFR-ongoing challenge. 
## Demo Video



https://github.com/weXiaolo/UniFace-Unified-Cross-Entropy-Loss-for-Deep-Face-Recognition/assets/74287249/05d8549e-8c4b-48cb-bacb-e00ae447eedc



## Get started

**Requirement: [PyTorch](https://pytorch.org/get-started/previous-versions/) >= 1.8.1**

1. **Prepare dataset**

    Download [CASIA-Webface](https://drive.google.com/file/d/1KxNCrXzln0lal3N4JiYl9cFOIhT78y1l/view?usp=sharing) preprocessed by [insightface](https://github.com/deepinsight/insightface/blob/master/recognition/_datasets_/README.md).
    ```console
    unzip faces_webface_112x112.zip
    ```

2. **Train model**

    Modify the 'data_path' in [train.py](train.py) (Line 57)

    Select and uncomment the 'loss' in [backbone.py](backbone.py) (Line 67)
    ```console
    python train.py
    ```

4. **Test model**
    ```console
    python pytorch2onnx.py
    zip model.zip model.onnx
    ```
 


