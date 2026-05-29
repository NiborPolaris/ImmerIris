[![Conference](https://img.shields.io/badge/CVPR-2026-brightgreen)](#citation)
[![arXiv](https://img.shields.io/badge/arXiv-2510.10113-b31b1b.svg)](https://arxiv.org/abs/2510.10113)
[![Presentation](https://img.shields.io/badge/CVPR%202026-Oral-gold)](#overview)
[![Recognition](https://img.shields.io/badge/Award-Candidate-red)](#overview)
[![Type](https://img.shields.io/badge/Project-Dataset%20%26%20Benchmark-blue)](#overview)
[![Task](https://img.shields.io/badge/Task-Iris%20Recognition-orange)](#benchmark)

# ImmerIris
This repository presents **ImmerIris**, a large-scale public iris dataset and benchmark for **off-axis** and **unconstrained** recognition in immersive XR applications.

**📄 Paper:** [ImmerIris on arXiv](https://arxiv.org/abs/2510.10113)  
**🏆 Status:** **CVPR 2026 Oral** and **Award Candidate**

<p align="center">
  <a href="https://arxiv.org/abs/2510.10113">📄 Paper</a> |
  <a href="https://drive.google.com/file/d/1j8oTcBEyCh4KMu3-Gn5gbxvG_fI6jdOP/view?usp=drive_link">⬇️ Benchmark Protocol</a> |
  <a href="#citation">📌 Citation</a>
</p>

<p align="center">
  <img src="assets/teaser.png" alt="ImmerIris teaser" width="100%">
</p>

## 🌍 Overview
Traditional iris recognition usually assumes frontal capture, controlled lighting, and cooperative users. In immersive applications, however, headset-mounted cameras observe the eye from the side while users naturally change gaze direction and interact in dynamic scenes.

**ImmerIris** is built to study this setting directly. It provides realistic off-axis ocular images, challenging quality variations, and a benchmark that exposes where current iris recognition systems fail under immersive conditions.

Our paper is available on arXiv: [https://arxiv.org/abs/2510.10113](https://arxiv.org/abs/2510.10113). The work was selected as a **CVPR 2026 Oral** presentation and is also an **Award Candidate**.

## ✨ Highlights
- 👁️ **499,791 ocular images** collected from **546 subjects**.
- VR **headset-based capture** with side-mounted near-infrared cameras.
- 🧭 Acquisition covers **9 gaze positions** and **11 brightness conditions**.
- ⚠️ Around **42% challenging samples** with realistic degradations.
- 📏 Includes **8 evaluation protocols** for immersive iris recognition.

## 📚 Dataset
ImmerIris is designed around real XR capture conditions rather than laboratory-style iris collection.

### 🔍 Key Properties
- **Headset acquisition**: ocular images are captured from a consumer HMD in an immersive setup.
- **Off-axis gaze variation**: subjects fixate on a `3 x 3` gaze grid, creating strong geometric variation.
- **Open-scene quality issues**: samples include occlusion, dilation, reflection, extreme gaze, and motion blur.

<p align="center">
  <img src="assets/fig_2.png" alt="Traditional vs immersive iris recognition" width="90%">
</p>

<p align="center">
  <img src="assets/fig_8.png" alt="Headset acquisition setup" width="90%">
</p>

## 🧹 Cleaning and Annotation
The dataset pipeline removes severe capture failures, keeps normal-quality samples, and scores images across multiple quality dimensions. These annotations support both isolated-factor analysis and realistic combined-condition protocols.

Factors considered in the benchmark include:
- eyelid and eyelash occlusion
- pupil dilation
- illumination change
- gaze variation
- specular reflection
- motion blur

<p align="center">
  <img src="assets/fig_10.png" alt="Cleaning and quality assessment pipeline" width="90%">
</p>

## 🎯 Benchmark
ImmerIris defines **8 protocols** to evaluate immersive iris recognition.

**⬇️ Benchmark protocol download:** [Google Drive](https://drive.google.com/file/d/1j8oTcBEyCh4KMu3-Gn5gbxvG_fI6jdOP/view?usp=drive_link)

### 🧪 Isolated Protocols
- **Occlusion**: tests partially covered iris texture.
- **Dilation**: measures changes caused by pupil expansion.
- **Light**: evaluates low- and high-brightness variation.
- **Gaze**: focuses on geometry changes across gaze directions.

### 🧩 Combined Protocols
- **Control**: off-axis capture with fixed gaze and normal-quality samples.
- **Fix**: fixed gaze with realistic degradations.
- **Select**: natural gaze while excluding the most extreme directions.
- **Any**: fully unconstrained pairing for open-scene immersive recognition.

You can download the released **benchmark protocol files** from the link above.

## 🛠️ Method: NormFree
Along with the benchmark, we present **NormFree**, a normalization-free recognition pipeline.

Instead of first unwrapping iris texture into a normalized strip, NormFree:
- crops the iris region with a robust bounding box
- learns features directly from the cropped image
- uses a face-recognition-style backbone with an angular-margin objective

This simpler design remains competitive under immersive capture conditions, especially when conventional normalization-based methods degrade.

<p align="center">
  <img src="assets/fig_11.png" alt="NormFree pipeline" width="90%">
</p>

## 📈 Results
Existing normalization-based methods degrade noticeably as the evaluation protocols become less constrained. **NormFree** ranks first or second in most verification settings and remains strong for identification tasks.

<p align="center">
  <img src="assets/result_1.png" alt="Verification results on combined protocols" width="48%">
  <img src="assets/result_2.png" alt="Verification results on isolated protocols" width="48%">
</p>

## 🖼️ Sample Gallery
<p align="center">
  <img src="assets/fig_1.png" alt="Ocular image gallery" width="90%">
</p>

<p align="center">
  <img src="assets/fig_7.png" alt="Additional ocular image samples" width="90%">
</p>

## 🔓 Dataset Access
The repository page and website indicate that public release is managed through a formal application process for research use.

At the moment, the dataset access entry is marked as **Coming Soon** in the project page. When the official access form or download link is available, you can add it here, for example:

```md
## Download
[Dataset Access Form](YOUR_LINK_HERE)
```

<a id="citation"></a>

## 📌 Citation
If you use **ImmerIris** in your research, please cite:

```bibtex
@inproceedings{mi2026immeriris,
  title     = {ImmerIris: A Large-Scale Dataset and Benchmark for Off-Axis and Unconstrained Iris Recognition in Immersive Applications},
  author    = {Mi, Yuxi and Yuan, Qiuyang and Zhong, Zhizhou and Zhao, Xuan and Zhou, Jiaogen and Zhu, Fubao and Guan, Jihong and Zhou, Shuigeng},
  booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  year      = {2026}
}
```
