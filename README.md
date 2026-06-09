# Flood Area Segmentation: U-Net vs U2-Net

> **Published Research** — This project is peer-reviewed and published in Springer LNNS.  
> 📄 [Read the Paper](https://link.springer.com/chapter/10.1007/978-981-97-8526-1_25)

## Overview

A comparative study of two deep learning architectures — **U-Net** and **U2-Net** — for semantic segmentation of flood-affected areas from aerial imagery. The project uses the [FloodNet dataset](https://github.com/BinaLab/FloodNet-Supervised_v1.0) and evaluates both models on their ability to accurately identify flooded regions for disaster response applications.

**Key Result:** U2-Net achieved **92% accuracy** vs U-Net's **86% accuracy** on the FloodNet dataset.

---

## Results

| Model   | Accuracy | Architecture Highlights |
|---------|----------|------------------------|
| U-Net   | 86%      | Encoder-decoder with skip connections |
| U2-Net  | **92%**  | Nested U-structure + Recurrent U-Block |

U2-Net's nested architecture captures finer spatial details and contextual nuances — critical for precise flood boundary delineation in aerial imagery.

---

## Architecture

### U-Net
- 6-level encoder-decoder with skip connections
- 256×256 input resolution
- Binary cross-entropy loss, Adam optimizer (lr=1e-4)
- Trained for 100 epochs, batch size 40

### U2-Net
- Nested U-structure for multi-scale feature extraction
- Recurrent U-Block for temporal/contextual dependencies
- Same training configuration for fair comparison

---

## Dataset

**FloodNet Dataset** — Aerial imagery for flood detection and segmentation.

Dataset download links are available in the [`Dataset/`](./Dataset/) folder of this repository (Google Drive links).

Dataset structure expected:
```
flood-area-segmentation/
├── Image/
│   └── images/
├── Mask/
│   └── masks/
└── metadata.csv
```

---

## Setup & Usage

### Requirements

```bash
pip install tensorflow keras numpy pandas matplotlib opencv-python
```

**Tested with:**
- Python 3.8+
- TensorFlow 2.x
- Keras 2.x

### Run

1. Clone the repository:
```bash
git clone https://github.com/AniruddhMukherjee/Unet-VS-U2net.git
cd Unet-VS-U2net
```

2. Download the dataset using links in `Dataset/` folder and place it as shown above.

3. Open and run the notebooks:
   - `ariel-image-segmentation-Unet.ipynb` — U-Net training and evaluation
   - `ariel-image-segmentation-U2net.ipynb` — U2-Net training and evaluation

> **Note:** Notebooks were originally run on Google Colab with Google Drive. Update the `data_dir` path in the notebooks to match your local setup.

---

## Publication

**Mukherjee, A.** — *"Improvement in Image Segmentation Using UNet and U2Net"*  
ICT4SD 2024 | Springer Lecture Notes in Networks and Systems (LNNS)  
🔗 [https://link.springer.com/chapter/10.1007/978-981-97-8526-1_25](https://link.springer.com/chapter/10.1007/978-981-97-8526-1_25)

---

## Project Structure

```
Unet-VS-U2net/
├── ariel-image-segmentation-Unet.ipynb    # U-Net implementation
├── ariel-image-segmentation-U2net.ipynb   # U2-Net implementation
├── Dataset/                                # Google Drive dataset links
└── README.md
```

---

## Author

**Aniruddh Mukherjee**  
M.Sc. INFOTECH — Universität Stuttgart  
[GitHub](https://github.com/AniruddhMukherjee) | [LinkedIn](https://linkedin.com/in/aniruddh-mukherjee)
