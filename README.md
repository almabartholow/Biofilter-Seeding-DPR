# Biofilter-Seeding-DPR

A comprehensive bioinformatics analysis pipeline for studying biofilter seeding of advanced treated wastewater using 16S rRNA gene sequencing and flow cytometry data analysis.

## Project Overview

This project focuses on analyzing microbial communities in annular reactor simulated distribution systems, specifically examining systems fed with advanced treated wastewater to study the impact of direct potable reuse on distribution system community composition. The analysis combines 16S rRNA gene sequencing data with flow cytometry (FCM) measurements to provide insights into microbial growth, diversity, and community structure.

## Project Structure

```
Biofilter-Seeding-DPR/
├── README.md                           # This file
├── ATP_FCM_Analysis.ipynb             # ATP and Flow Cytometry analysis
├── 16S_dada2.Rmd                      # DADA2 pipeline for 16S rRNA analysis
├── Seeding_16S_decontam.ipynb         # Contamination removal analysis
└── Seeding_16S_Analysis.ipynb         # Main 16S analysis notebook
```

## Analysis Components

### 1. ATP and Flow Cytometry Analysis (`ATP_FCM_Analysis.ipynb`)
- **ATP Measurements**: Total and intaracellular activity measurements
- **Flow Cytometry**: Total and intact cell counting 
- **Data Analysis**: Comparing biomass metrics across sample types and phases 

### 2. 16S rRNA Gene Sequencing Analysis (`16S_dada2.Rmd`)
- **DADA2 Pipeline**: Complete amplicon sequence variant (ASV) inference
- **Quality Control**: Read filtering, trimming, error rate learning, and chimera removal
- **Taxonomic Assignment**: Using SILVA database for taxonomic classification

### 3. Contamination Removal (`Seeding_16S_decontam.ipynb`)
- **Decontamination**: Removal of potential contaminants using the `decontam` package
- **Quality Assessment**: Evaluation of contamination levels
- **Data Cleaning**: Preparation of clean datasets for downstream analysis

### 4. Main 16S Analysis (`Seeding_16S_Analysis.ipynb`)
- **Community Composition**: Taxonomic profiling (including opportunistic pathogens) and visualization
- **Diversity Analysis**: Richness, evenness, and phylogenetic diversity
- **Statistical Analysis**: Differential abundance testing and community comparisons
- **Data Integration**: Absolute abundance calculation by multiplying 16S relative abundance with flow cytometry cell counts
- **Visualization**: Comprehensive plotting of community data

## Key Features

- **Comprehensive Pipeline**: End-to-end analysis from raw sequencing data to publication-ready figures
- **Quality Control**: Multiple quality assessment steps throughout the pipeline
- **Reproducible Analysis**: Well-documented code with clear parameter settings
- **Statistical Rigor**: Appropriate statistical tests for microbial community data
- **Visualization**: Rich plotting capabilities for data exploration and presentation

## Key Dependencies

### R Packages
- `phyloseq` - Microbial community analysis
- `dada2` - ASV inference and quality filtering
- `decontam` - Contamination removal
- `ggplot2` - Data visualization
- `vegan` - Community ecology analysis
- `DESeq2` - Differential abundance analysis
- `Biostrings` - DNA sequence manipulation
- `DECIPHER` - Sequence alignment and clustering
- `dplyr` - Data manipulation
- `tidyr` - Data tidying
- `microViz` - Additional microbial analysis tools

### Python Packages
- Standard scientific computing stack (pandas, numpy, matplotlib, seaborn)
- Jupyter notebook environment

## Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd Biofilter-Seeding-DPR
   ```

2. **Install R dependencies**:
   ```r
   # Install Bioconductor packages
   if (!requireNamespace("BiocManager", quietly = TRUE))
       install.packages("BiocManager")
   BiocManager::install(c("phyloseq", "dada2", "decontam", "Biostrings", "DECIPHER", "DESeq2"))

   # Install CRAN packages
   install.packages(c("ggplot2", "vegan", "dplyr", "tidyr", "microViz", "RColorBrewer"))
   ```

3. **Install Python dependencies**:
   ```bash
   pip install jupyter pandas numpy matplotlib seaborn scipy scikit-learn
   ```

## Usage

### 1. ATP and Flow Cytometry Analysis
1. Prepare your ATP and FCM csv data files
2. Run `ATP_FCM_Analysis.ipynb` for physiological measurements
3. Integrate results with 16S data for comprehensive analysis

### 2. 16S rRNA DADA2 Pipeline
1. Place your FASTQ files in the appropriate directory
2. Update file paths in `16S_dada2.Rmd`
3. Run the DADA2 pipeline to generate ASV table and taxonomy in phyloseq object

### 3. 16S rRNA Decontamination and Analysis
1. Run `Seeding_16S_decontam.ipynb` to identify and remove contaminants with appropriate method
2. Use the cleaned dataset for subsequent analyses
3. Proceed with downstream analysis in `Seeding_16S_Analysis.ipynb`


## Data Requirements

### Input Data
- **16S rRNA sequencing data**: Paired-end FASTQ files
- **Metadata**: Sample information including treatment groups, time points, etc.
- **Reference databases**: SILVA database for taxonomic assignment
- **ATP measurements**: Cellular ATP concentration data
- **Flow cytometry data**: Cell count and characterization data

### Output Data
- **ASV table**: Amplicon sequence variant abundance matrix
- **Taxonomy table**: Taxonomic assignments for each ASV
- **Phyloseq object**: Integrated data structure for analysis
- **Visualizations**: Publication-ready plots and figures
- **Statistical results**: Diversity metrics, differential abundance results

## Analysis Workflow

1. **Data Preprocessing**
   - Quality filtering and trimming of raw sequences
   - Error rate learning and denoising
   - Chimera removal

2. **Taxonomic Analysis**
   - ASV inference using DADA2
   - Taxonomic assignment using SILVA
   - Contamination removal

3. **Community Analysis**
   - Alpha and beta diversity calculations
   - Community composition analysis
   - Statistical comparisons between groups

4. **Data Integration**
   - Absolute abundance calculation by integrating 16S relative abundance with flow cytometry cell counts
   - Pathogen risk assessment using absolute abundance estimates

## Results and Outputs

The pipeline generates:
- **Diversity plots**: Richness, evenness, and phylogenetic diversity
- **Community composition**: Taxonomic bar plots and heatmaps
- **Ordination plots**: PCoA and NMDS for community structure
- **Statistical summaries**: Diversity metrics and significance tests
- **Publication figures**: High-quality plots for manuscripts

## Acknowledgments

This analysis pipeline was developed based on code and methods from Dr. Rose Kantor's work on microbiome analyses of an advanced water treatment plant. We thank them for sharing their codebase and analytical approaches.

## Contact

For questions about this analysis pipeline, please contact the project maintainer Alma Bartholow.


*Last updated: October 2025*
