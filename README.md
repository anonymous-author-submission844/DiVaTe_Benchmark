# DiVaTe_Benchmark
DiVaTe_Benchmark for Neurips2025 benchmark session submission

## Overview

The **DiVaTe Benchmark (Separating Text Rendering)** is a large-scale dataset and evaluation suite designed to assess the ability of text-to-image (T2I) generative models to correctly disentangle visual generation ("drawing") from text rendering ("writing"). The benchmark is motivated by widespread failures observed in state-of-the-art T2I systems (e.g., GPT-Image-1, Stable Diffusion, Midjourney) when prompted to generate images that contain both visual content and embedded textual content. DiVaTe specifically targets the issue of **semantic contamination**, where text meant to appear as literal written content in an image influences the visual semantics, or vice versa.

DiVaTe includes over **5,000 structured prompts** designed to probe a model's ability to accurately and cleanly separate these two modalities.

## Dataset Structure

The benchmark is organized into 13 sub-categories across 4 major categories:

### Category 1: Neutral Surface Text Rendering (1,000 prompts)

* Goal: Render text on a neutral surface without semantic interference.
* Example: *A painting of a blank wall. There is a text 'cloud' written on it.*

### Category 2: Semantic Conflicts (1,300 prompts)

* Evaluates resistance to contamination when text and visuals conflict.
* **2.1 Object–Word Conflict (400 prompts)**: *A sketch of a fox. There is a caption 'whale' written on it.*
* **2.2 Shape/Color Conflict (600 prompts)**: *A sketch of yellow pants. There is a text 'white' written on it.*
* **2.3 Texture/Material Conflict (300 prompts)**: *A picture of rubber boots. There is a caption 'glass' written on it.*

### Category 3: Compatible Attribute Alignment (1,800 prompts)

* Visual and textual content are semantically aligned.
* **3.1 Physical Attributes (300 prompts)**: *A drawing of a man. There is a text 'blue eyes' written on it.*
* **3.2 Actions/Expressions (300 prompts)**: *A painting of taxi-driver. There is a text 'sleeping' written on it.*
* **3.3 Job(300 prompts)**: *A painting of a man. There is a text 'Doctor' written on it.*
* **3.4 Object + Object Description (300 prompts)**: *A sketch of a spider. There is a label 'next to the fence' written on it.*
* **3.5 Environment (300 prompts)**: *A photo of a cat. There is a caption 'mountain' written on it.*
* **3.3 Relationships (150 prompts)**: *A painting of a student and a woman. There is a caption 'parent and child' written between them.*
* **3.7 Brand/Affiliation (150 prompts)**: *A drawing of a glass cup. There is a caption 'Coca-Cola' written on it.*

### Category 4: Counterfactual Grounding (900 prompts)

* Text and visuals are intentionally contradictory.
* **4.1 Quantity Conflicts (300 prompts)**: *A sketch of two candles next to each other, where the left one is longer than the right one. The longer one has a label '10cm', and the shorter one has a label '1m' on it.*
* **4.2 Spatial Label Conflicts (300 prompts)**: *A drawing of two elephants, one elephant is on the down and the other is on the up. The one on the down has a word 'up', and the one on the up has a word 'down' on it.*
* **4.3 Numerical Contradictions (300 prompts)**: *A sketch of 9 plates. There is a word '1 plate' written on it.*

## Prompt Generation

Prompts were created using template-based generation:

* **Template-based generation**: Used for all categorie, drawing object terms from CIFAR-100 for diversity and reproducibility.
* **Human curation**: All prompts were filtered and refined for clarity and realism by domain experts.

## Evaluation Protocol

The benchmark supports four types of evaluation metrics:

* **OCR Accuracy**: Measures legibility and correctness of rendered text.
* **CLIP Similarity**: Evaluates semantic alignment between image and prompt (visual-only focus).
* **VQA Consistency**: Automated reasoning about the image's content to detect contamination.
* **Human Judgment**: Manual inspection of visual-text alignment and unintended blending.

## Applications

DiVaTe is ideal for researchers and developers aiming to:

* Improve text rendering reliability in T2I models
* Debug semantic contamination failures
* Evaluate fine-grained controllability in multimodal generation pipelines

## Citation

(Will be added upon publication)

## License

(Details will be added)
