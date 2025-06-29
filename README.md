[![Español](https://img.shields.io/badge/LEER_EN_ESPAÑOL-red?style=for-the-badge)](README_ES.md)

# 🌿 Plant ITS Chimera Detection Pipeline  

## 🔍 Scientific Overview  
Automated bioinformatic workflow for validating plant Internal Transcribed Spacer (ITS) sequences using:  
- **VSEARCH v2.27.0** with UCHIME algorithm  
- **UNITE+INSD Viridiplantae** reference database  
- Quality control for GenBank submission  

## 🚀 Quick Installation  
```bash
# Clone repository
git clone https://github.com/yourusername/plant-its-chimera-detection.git
cd plant-its-chimera-detection

# Create Conda environment
conda env create -f environment.yml
conda activate chimera-detection
```

## ⚙️ Run Analysis  
```bash
bash scripts/detect_chimeras.sh -i your_sequences.fasta -o results_dir
```

### Command Parameters:  
| Parameter | Description |  
|-----------|-------------|  
| `-i` | Input FASTA file (plant ITS sequences) |  
| `-o` | Output directory for results |  

## 📊 Output Files  
| File | Description |  
|------|-------------|  
| `nonchimeras.fasta` | Validated non-chimeric sequences |  
| `chimeras.fasta` | Discarded chimeric sequences |  
| `chimera_report.tsv` | Detailed chimera scores and metrics |  

## 🔬 Example Report  
```tsv
Sequence          Score  Status  
>Sample_1         0.12   Non-chimera  
>Sample_2         0.87   Chimera  
```

## 📚 Scientific Background  
### Methodology  
Putative chimeras are detected using reference-based UCHIME implementation in VSEARCH against a curated Viridiplantae subset from UNITE+INSD (v19.02.2025). Sequences scoring >0.5 are discarded.  

### Database Specifications  
- **UNITE+INSD v19.02.2025**:  
  - DOI: [10.15156/BIO/3301228](https://doi.org/10.15156/BIO/3301228)  
  - Contains all eukaryotic ITS sequences from UNITE and INSDC  
  - Viridiplantae subset: 431,611 sequences  

## 🧪 Test with Sample Data  
```bash
# Use example sequence
bash scripts/detect_chimeras.sh -i samples/example_sequence.fasta -o test_results

# Check score
awk '{print $1,$2}' test_results/chimera_report.tsv
```

## 📜 How to Cite  
If you use this workflow in your research:  
```bibtex
@software{plant_chimera_2025,
  author = {Bendayan, Andreina},
  title = {Plant ITS Chimera Detection Pipeline},
  year = {2025},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/Andreinabenjmz/plant-its-chimera-detection}}
}
```

## ⚖️ License  
[MIT LICENSE](LICENSE.md) - Free for academic and commercial use with attribution
