# 🌿 Pipeline de Detección de Quimeras para ITS de Plantas  

## 🔍 Resumen Científico  
Workflow bioinformático automatizado para validar secuencias del Espaciador Transcrito Interno (ITS) de plantas usando:  
- **VSEARCH v2.27.0** con algoritmo UCHIME  
- Base de datos de referencia **UNITE+INSD Viridiplantae**  
- Control de calidad para depósito en GenBank  

<p align="center">
  <img src="https://img.shields.io/badge/Idioma-Español-red" alt="Español">
  <a href="DOCS_EN.md">
    <img src="https://img.shields.io/badge/Ver_en_Inglés-blue" alt="English">
  </a>
</p>

## 🚀 Instalación Rápida  
```bash
# Clonar repositorio
git clone https://github.com/Andreinabenjmz/plant-its-chimera-detection.git
cd plant-its-chimera-detection

# Crear entorno Conda
conda env create -f environment.yml
conda activate chimera-detection
```

## ⚙️ Ejecutar Análisis  
```bash
bash scripts/detect_chimeras.sh -i tus_secuencias.fasta -o directorio_resultados
```

### Parámetros del Comando:  
| Parámetro | Descripción |  
|-----------|-------------|  
| `-i` | Archivo FASTA de entrada (secuencias ITS de plantas) |  
| `-o` | Directorio de salida para resultados |  

## 📊 Archivos de Salida  
| Archivo | Descripción |  
|------|-------------|  
| `nonchimeras.fasta` | Secuencias validadas no quiméricas |  
| `chimeras.fasta` | Secuencias quiméricas descartadas |  
| `chimera_report.tsv` | Puntuaciones y métricas detalladas |  

## 🔬 Ejemplo de Reporte  
```tsv
Secuencia          Puntuación  Estado  
>Muestra_1         0.12   No-quimera  
>Muestra_2         0.87   Quimera  
```

## 📚 Fundamentos Científicos  
### Metodología  
Las quimeras putativas se detectan mediante la implementación basada en referencia de UCHIME en VSEARCH contra un subconjunto curado de Viridiplantae de UNITE+INSD (v19.02.2025). Las secuencias con puntuación >0.5 se descartan.  

### Especificaciones de la Base de Datos  
- **UNITE+INSD v19.02.2025**:  
  - DOI: [10.15156/BIO/3301228](https://doi.org/10.15156/BIO/3301228)  
  - Contiene todas las secuencias ITS eucariotas de UNITE e INSDC  
  - Subconjunto Viridiplantae: 431,611 secuencias  

## 🧪 Probar con Datos de Ejemplo  
```bash
# Usar secuencia de ejemplo
bash scripts/detect_chimeras.sh -i samples/example_sequence.fasta -o resultados_prueba

# Verificar puntuación
awk '{print $1,$2}' resultados_prueba/chimera_report.tsv
```

## 📜 Cómo Citar  
Si usas este workflow en tu investigación:  
```bibtex
@software{plant_chimera_2025,
  author = {Bendayan, Andreina},
  title = {Plant ITS Chimera Detection Pipeline},
  year = {2025},
  publisher = {GitHub},
  journal = {Repositorio GitHub},
  howpublished = {\url{https://github.com/Andreinabenjmz/plant-its-chimera-detection}}
}
```

## ⚖️ Licencia  
[Licencia MIT](LICENSE) - Libre para uso académico y comercial con atribución

[Ver en inglés](DOCS_EN.md)
