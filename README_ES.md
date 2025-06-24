# Pipeline de Detección de Quimeras para ITS de Plantas

## 🔍 Descripción
Workflow automatizado para validar secuencias ITS de plantas usando:
- **VSEARCH v2.27.0** con algoritmo UCHIME
- Base de datos **UNITE+INSD Viridiplantae**
- Validación de calidad para depósito en GenBank

## 🚀 Instalación Rápida
```bash
git clone https://github.com/tuusuario/plant-its-chimera-detection.git
cd plant-its-chimera-detection
conda env create -f environment.yml
conda activate chimera-detection
```

## ⚙️ Ejecución
```bash
bash scripts/detect_chimeras.sh -i tus_secuencias.fasta -o resultados
```

## 📊 Resultados
| Archivo | Descripción |
|---------|-------------|
| `nonchimeras.fasta` | Secuencias validadas |
| `chimeras.fasta` | Secuencias descartadas |
| `chimera_report.tsv` | Scores detallados |

[Ver en inglés](README.md)
