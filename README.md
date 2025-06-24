# plant-its-chimera-detection
EN: VSEARCH-based pipeline for chimera detection in plant ITS sequences 
ES: Pipeline con VSEARCH para detección de quimeras en secuencias ITS de plantas

# Plant ITS Chimera Detection Pipeline

## 🔬 Overview
Automated workflow for detecting chimeric sequences in plant Internal Transcribed Spacer (ITS) regions using:
- **VSEARCH v2.23.0** for chimera checking
- **UNITE Database** (Viridiplantae subset) as reference
- **SeqKit** for taxonomic filtering

## 🚀 Quick Start
```bash
git clone https://github.com/Andreinabenjmz/plant-its-chimera-detection.git
cd plant-its-chimera-detection
conda env create -f environment.yml
conda activate chimera-detection
bash scripts/detect_chimeras.sh -i your_sequences.fasta -o results
```

## 📚 Documentation
- [Full workflow explanation](docs/tutorial_en.pdf)
- [Parameters configuration](config/paths.cfg)

[Ver en español](README_ES.md)
