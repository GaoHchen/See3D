<div align='center'>
<!-- <img src="assets/logo.jpg" alt="logo" style="zoom:0.5%;" /> -->

<h2>You See it, You Got it: Learning 3D Creation on Pose-Free Videos at Scale</h2>

[Baorui Ma*](https://mabaorui.github.io), [Huachen Gao*](https://gaohchen.github.io/), [Haoge Deng*](https://github.com/Bitterdhg/), [Zhengxiong Luo](https://greatlog.github.io/), [Tiejun Huang](https://scholar.google.com/citations?user=knvEK4AAAAAJ&hl=en), [Lulu Tang†](https://scholar.google.com/citations?authuser=1&user=o2fG4xUAAAAJ), [Xinlong Wang†](https://www.xloong.wang/)

[Beijing Academy of Artificial Intelligence, BAAI](https://www.baai.ac.cn/english.html)<br>
<sup>*</sup> Equal Contribution, <sup>†</sup> Corresponding Author

🤗 If you find See3D useful, **please help ⭐ this repo**, which is important to Open-Source projects. Thanks!

## [Paper](https://arxiv.org/abs/2412.06699/) | [Project Page](https://vision.baai.ac.cn/see3d/) | [Models](https://drive.google.com/drive/folders/1uz4NtAtYYiV53dYlJ_I78fVzqxUBk-Fb?usp=sharing/) | [Dataset]()

</div>
We present <strong>See3D</strong>, a visual-conditional multi-view diffusion model trained on large-scale Internet videos for open-world 3D creation. The model aims to </strong>Get</strong> 3D knowledge by solely <strong>Seeing</strong> the visual contents from the vast and rapidly growing video data --- <em>You See it, You Got it</em>. To achieve this, we first scale up the training data using a proposed data curation pipeline that automatically filters out multi-view inconsistencies and insufficient observations from source videos. This results in a high-quality, richly diverse, large-scale dataset of multi-view images, termed <strong>WebVi3D</strong>, containing 320M frames from 16M video clips. Nevertheless, learning generic 3D priors from videos without explicit 3D geometry or camera pose annotations is nontrivial, and annotating poses for web-scale videos is prohibitively expensive. To eliminate the need for pose conditions, we introduce an innovative <em>visual-condition</em> - a purely 2D-inductive visual signal generated by adding time-dependent noise to the masked video data. Finally, we introduce a novel visual-conditional 3D generation framework by integrating <strong>See3D</strong> into a warping-based pipeline for high-fidelity 3D generation. Our numerical and visual comparisons on single and sparse reconstruction benchmarks show that <strong>See3D</strong>, trained on cost-effective and scalable video data, achieves notable zero-shot and open-world generation capabilities, markedly outperforming models trained on costly and constrained 3D datasets. Additionally, our model naturally supports other image-conditioned 3D creation tasks, such as 3D editing, without further fine-tuning.



![](assets/teaser.jpg)
Benefiting from the proposed web-scale dataset **WebVi3D**, **See3D** enables both object- and scene-level 3D creation, including sparse-view-to-3D, (text-) image-to-3D, and 3D editing. It can also be used for Gaussian Splatting to extract meshes or render images.

### Highlights

- We present **See3D**, a scalable visual-conditional MVD model for open-world 3D creation, which can be trained on web-scale video collections without pose annotations.
- We curate **WebVi3D**, a multi-view images dataset containing static scenes with sufficient multi-view observations, and establish an automated pipeline for video data curation to train the MVD model.
- We introduce a novel warping-based 3D generation framework with **See3D**, which supports long-sequence generation with complex camera trajectories.
- We achieve state-of-the-art results in single and sparse views reconstruction, demonstrating remarkable zero-shot and open-world generation capability, offering a novel perspective on scalable 3D generation.

## News
**[12/10/2024]**
We have released the pretrained models and inference code. You can download models and example test data [here](https://drive.google.com/drive/folders/1uz4NtAtYYiV53dYlJ_I78fVzqxUBk-Fb?usp=sharing/)

## Installation
```sh
git clone https://github.com/baaivision/See3D.git
cd See3D

pip install -r requirements.txt
```

## Inference Code
We provide inference code for multi-view generation based on single-view and sparse-view inputs. Please add or remove the `--super_resolution` parameter according to your needs. The multi-view super-resolution model will upscale the default 512 resolution to a consistent 1024 resolution across multiple views, which requires more inference time and GPU memory. Please download the example test data [here](https://drive.google.com/drive/folders/1uz4NtAtYYiV53dYlJ_I78fVzqxUBk-Fb?usp=sharing/) and put it in the `dataset` folder.
### Generation Based on Single View Input
```sh
bash single_infer.sh
```
### Generation Based on Sparse Views Input
```sh
bash sparse_infer.sh
```

## ToDo List
- [x] Release pretrained models.
- [x] Release inference code.
- [ ] Release training scripts.
- [ ] Release data curation pipeline from Internet Video.
- [ ] Release 3D generation framework utilizing the warping-based pipeline.
- [ ] Release the evaluation code.

## Acknowledgement

See3D is built using the awesome open-source projects: [Stable Diffusion](https://github.com/Stability-AI/stablediffusion), [MVDream](https://github.com/bytedance/MVDream), [ViewCrafter](https://github.com/Drexubery/ViewCrafter/tree/main), [FrozenRecon](https://github.com/aim-uofa/FrozenRecon)

Thanks to the maintainers of these projects for their contribution to the community!

## Citation

If you find See3D helpful, please consider citing:

```
@inproceedings{Ma2024See3D,
    title = {You See it, You Got it: Learning 3D Creation on Pose-Free Videos at Scale},
    author = {Baorui Ma and Huachen Gao and Haoge Deng and Zhengxiong Luo and Tiejun Huang and Lulu Tang and Xinlong Wang},
    journal={arXiv preprint arXiv:2412.06699},
    year={2024}
}
```