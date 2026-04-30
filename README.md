# Political Affiliation Detection in French Electoral Manifestos

A comparative study of TF-IDF and CamemBERT for classifying French *professions de foi* (electoral manifestos) into 6 political families, using the Archelec corpus (Sciences Po / Internet Archive, 1958–1993).

## Results

| Model | Input | Accuracy | Macro F1 |
|---|---|---|---|
| TF-IDF + LR | Original | 0.94 | 0.93 |
| CamemBERT | Original | 0.91 | 0.89 |
| TF-IDF + LR | Masked | 0.87 | 0.84 |
| CamemBERT | Masked | 0.90 | 0.87 |

## Data

The raw corpus is not included in this repository due to file size.

- **Option 1**: Download directly from our [Google Drive](https://drive.google.com/drive/folders/1-4iZKQgocfQzKyi1gxlUTTX4AyIKmSYb?usp=drive_link) and place as `data/archelec_avec_textes.csv`
- **Option 2**: Download the Archelec dataset from [Sciences Po](https://archelec.fr) and run Section 1 of the notebook to retrieve OCR texts (~90 min)

Then run Section 2 of the notebook to generate `data/archelec_final.csv` (~15,300 documents after filtering).

## Setup

```bash
pip install -r requirements.txt
```

CamemBERT fine-tuning requires a GPU. For full training, Google Colab with a T4 GPU is recommended (~45 min per run).

## Structure

```
archelec-NLP/
├── archelec_classification.ipynb   # Main notebook
├── figures/                        # Generated plots
├── paper/                          # NeurIPS-format report
├── NLP_rapport_SAIDI_Mehdi.pdf     # Data directory (files not included)
└── README.md
```

## Political families

| Family | N |
|---|---|
| Gauche radicale (PCF, LCR, …) | 6,579 |
| Gauche (PS, MRG, …) | 3,253 |
| Centre-droite (UDF, MRP, …) | 2,590 |
| Droite (RPR, …) | 1,395 |
| Extrême droite (FN, …) | 1,056 |
| Écologie (Verts, GE, …) | 427 |
