# Jump Intelligence (JI): Supplementary Materials

This repository contains supplementary datasets and materials for the paper:

**Jump Intelligence (JI): A Mechanism-Aware Lens for Diagnosing the Structure of Scientific Discovery from Literature-Only Signals**

**Author**: Shoichi Manabe  
**Affiliation**: Independent Researcher, Tokyo, Japan  
**Contact**: s.manabe1987@gmail.com

---

## 📄 Preprint

**OSF Preprints**: [https://doi.org/10.31219/osf.io/xxxxx](https://doi.org/10.31219/osf.io/xxxxx)  
**Version**: v2 (2026-01-07) - Added corresponding author contact information  
**License**: CC-BY 4.0 International

---

## 📊 Datasets

This repository includes seven CSV datasets used in the Jump Intelligence study:

### Primary Evaluation Datasets

1. **`1.CuPB_mTJS2_dataset.csv`**  
   Cu–Prussian Blue predictions (n=99)  
   Materials science case study

2. **`2.graphene_dye_mTJS2_dataset.csv`**  
   Graphene–dye predictions (n=58)  
   Materials science case study

3. **`3.drug_repurposing_mTJS2_dataset.csv`**  
   Alzheimer's drug repurposing predictions (n=93)  
   Biomedicine case study

### Validation Datasets

4. **`4.adversarial_anchors.csv`**  
   Adversarial testing with inverted principles

5. **`5.linguistic_variants.csv`**  
   Linguistic robustness validation

6. **`6.baseline_vocabulary.csv`**  
   Baseline vocabulary for comparison

7. **`7.nested_cv_results.csv`**  
   Nested cross-validation results (δ=0.59±0.13)

---

## 📁 Data Format

All CSV files follow the same structure:

| Column | Description |
|--------|-------------|
| `material` | Material/compound name |
| `lambda_signature` | λ signature value (balancing parameter) |
| `JI_score` | Jump Intelligence score (mTJS2) |
| `discovery_year` | Year of discovery (if applicable) |
| `citation_count` | Citation count (if applicable) |

---

## 🔧 Usage

### Python Example

```python
import pandas as pd

# Load Cu-Pb dataset
df = pd.read_csv('1.CuPB_mTJS2_dataset.csv')

# Display first 5 rows
print(df.head())

# Filter high-λ Bridging Leaps (λ > 2.5)
bridging_leaps = df[df['lambda_signature'] > 2.5]
print(f"Bridging Leaps: {len(bridging_leaps)} cases")

# Filter low-λ Hierarchical Leaps (λ < 1.0)
hierarchical_leaps = df[df['lambda_signature'] < 1.0]
print(f"Hierarchical Leaps: {len(hierarchical_leaps)} cases")
