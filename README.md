# MVTamperBench Dataset

## Overview

**MVTamperBench** is a robust benchmark designed to evaluate Vision-Language Models (VLMs) against adversarial video tampering effects. It leverages the diverse and well-structured MVBench dataset, systematically augmented with four distinct tampering techniques:

1. **Masking**: Overlays a black rectangle on a 1-second segment, simulating visual data loss.
2. **Repetition**: Repeats a 1-second segment, introducing temporal redundancy.
3. **Rotation**: Rotates a 1-second segment by 180 degrees, introducing spatial distortion.
4. **Substitution**: Replaces a 1-second segment with a random clip from another video, disrupting the temporal and contextual flow.

The tampering effects are applied to the end of each video to ensure consistent evaluation across models.

---

## Dataset Details

The MVTamperBench dataset is built upon the **MVBench dataset**, a widely recognized collection used in video-language evaluation. It features a broad spectrum of content to ensure robust model evaluation, including:

- **Content Diversity**: Spanning a variety of objects, activities, and settings.
- **Temporal Dynamics**: Videos with temporal dependencies for coherence testing.
- **Benchmark Utility**: Recognized datasets enabling comparisons with prior work.

### Incorporated Datasets

The MVTamperBench dataset integrates videos from several sources, each contributing unique characteristics:

| Dataset Name         | Primary Scene Type and Unique Characteristics                          |
|----------------------|-------------------------------------------------------------------------|
| STAR      | Indoor actions and object interactions                               |
| PAXION    | Real-world scenes with nuanced actions                              |
| Moments in Time (MiT) V1 | Indoor/outdoor scenes across varied contexts            |
| FunQA     | Humor-focused, creative, real-world events                          |
| CLEVRER   | Simulated scenes for object movement and reasoning                  |
| Perception Test  | First/third-person views for object tracking                    |
| Charades-STA   | Indoor human actions and interactions                              |
| MoVQA     | Diverse scenes for scene transition comprehension                   |
| VLN-CE       | Indoor navigation from agent perspective                            |
| TVQA     | TV show scenes for episodic reasoning                               |

### Dataset Expansion

The original MVBench dataset contains 3,699 videos, which have been systematically expanded through tampering effects, resulting in a total of **14,796 videos**. This ensures:

- **Diversity**: Varied adversarial challenges for robust evaluation.
- **Volume**: Sufficient data for training and testing.

Below is a visual representation of the tampered video length distribution:

![Tampered Video Length Distribution](path/to/tampered_video_length_distribution.png "Distribution of tampered video lengths")

---

## Benchmark Construction

MVTamperBench is built with modularity, scalability, and reproducibility at its core:

- **Modularity**: Each tampering effect is implemented as a reusable class, allowing for easy adaptation.
- **Scalability**: Supports customizable tampering parameters, such as location and duration.
- **Integration**: Fully compatible with VLMEvalKit, enabling seamless evaluations of tampering robustness alongside general VLM capabilities.

By maintaining consistent tampering duration (1 second) and location (ending of the video), MVTamperBench ensures fair and comparable evaluations across models.

---

## Download Dataset

You can access the MVTamperBench dataset directly from the Hugging Face repository:

[Download MVTamperBench Dataset](https://huggingface.co/datasets/Srikant86/MVTamperBench)

---

## How to Use

1. Clone the Hugging Face repository:
   ```bash
   git clone (https://huggingface.co/datasets/Srikant86/MVTamperBench)
   cd mvtamperbench
   ```

2. Load the dataset using the Hugging Face `datasets` library:
   ```python
   from datasets import load_dataset

   dataset = load_dataset("mvtamperbench")
   ```

3. Explore the dataset structure and metadata:
   ```python
   print(dataset["train"])
   ```

4. Utilize the dataset for tampering detection tasks, model evaluation, and more.

---

## Citation

If you use MVTamperBench in your research, please cite:

```bibtex
@misc{agarwal2024mvtamperbenchevaluatingrobustnessvisionlanguage,
      title={MVTamperBench: Evaluating Robustness of Vision-Language Models}, 
      author={Amit Agarwal and Srikant Panda and Angeline Charles and Bhargava Kumar and Hitesh Patel and Priyanranjan Pattnayak and Taki Hasan Rafi and Tejaswini Kumar and Dong-Kyu Chae},
      year={2024},
      eprint={2412.19794},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2412.19794}, 
}
```

---

## License

MVTamperBench is released under the MIT License. See `LICENSE` for details.
