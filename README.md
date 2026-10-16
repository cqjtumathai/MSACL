# MSACL: Multi-domain Latent Semantic Mining with Augmentation-free Contrastive Learning for Multimodal Recommendation

## Requirements
```text
python = 3.8.20
pytorch = 2.1.2
torch-geometric = 2.6.1
torchvision = 0.16.2
numpy = 1.24.2
scipy = 1.10.1
pandas = 1.5.3
tqdm = 4.64.1
pyyaml = 6.0
lmdb = 1.4.1
matplotlib = 3.7.1
Pillow = 10.0.0
```

## Datasets
We evaluate MSACL on three public multimodal recommendation datasets: Baby, Sports, and Clothing.

The processed datasets and pre-extracted multimodal features can be downloaded from:

[Baby/Sports/Clothing](https://drive.google.com/drive/folders/1tU4IxYbLXMkp_DbIOPGvCry16uPvolLk)

Please place the downloaded datasets under the `data/` directory:

```text
data/
├── baby/
├── sports/
└── clothing/
```

| Dataset  | # Users | # Items | # Interactions | Sparsity | Modality        |
|----------|---------|---------|----------------|----------|-----------------|
| Baby     | 19,445  | 7,050   | 160,792        | 99.88%   | Visual, Textual |
| Sports   | 35,598  | 18,357  | 296,337        | 99.95%   | Visual, Textual |
| Clothing | 39,387  | 23,033  | 278,677        | 99.97%   | Visual, Textual |

Following previous multimodal recommendation studies, we use publicly released pre-extracted multimodal features:

- Visual feature dimension: 4096
- Textual feature dimension: 384

## Training
The recommended hyperparameters for Baby, Sports, and Clothing are provided in three dataset-specific files:

- `src/configs/model/MSACL-baby-dataset.yaml`
- `src/configs/model/MSACL-sports-dataset.yaml`
- `src/configs/model/MSACL-clothing-dataset.yaml`

The configuration file is loaded automatically according to the dataset specified by `-d`, so no manual editing is required. Please run the following commands from the `src/` directory:

### **Baby**

```bash
python main.py -m MSACL -d baby
```

### **Sports**

```bash
python main.py -m MSACL -d sports
```

### **Clothing**

```bash
python main.py -m MSACL -d clothing
```

Please make sure that the dataset specified by `-d` corresponds to an existing configuration file in `src/configs/model/`.


