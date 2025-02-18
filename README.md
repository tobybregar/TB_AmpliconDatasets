# Generating OTU tables through AMPtk

### This code is written assuming the folder structure that follows.

### Download your zipped files into a Project folder and call that downloaded file “raw_data/sequencing” and don't forget to duplicate this into a private Zenodo repo!

```         
project_root/
│
├── raw_data/                  # Unmodified raw sequencing data
│   ├── sequencing/            # Raw FASTQ files
│   ├── reference/             # Reference genomes/databases 
│   └── README.md              # Documentation on raw data sources
│
├── processed_data/             # All cleaned & processed data
│   ├── met/              # Sample metadata files
│   │   ├── sequencing_id.txt  # Sequencing sample key
│   │   ├── metadata.csv       # Sample metadata (must match) 
│   │   └── README.md          # Metadata column descriptions
│   ├── taxonomies/            # Taxonomy databases or classifiers
│   ├── tables/                # Cleaned OTU/ASV tables for analysis
│   ├── logs/                  # Processing logs
│   ├── stats/                 # Quality filtering & read count 
│   └── README.md              # Summary of processed data
│
├── results/                    # Main output directory 
│   ├── amptk/                 # AMPtk-specific outputs
│   │   ├── otu_table.biom     # OTU table in BIOM format
│   │   ├── demux_reads.fq.gz  # Demultiplexed reads
│   │   ├── clustered_otus.fa  # Clustered OTUs
│   │   ├── filtered_otus.fa   # Filtered OTUs
│   │   ├── otu_table.txt      # Cleaned OTU table
│   │   ├── logs/              # AMPtk logs
│   ├── phyloseq/              # Phyloseq analysis outputs
│   │   ├── fungi_phyloseq.rds # Saved phyloseq object
│   │   ├── plots/             # Data visualization outputs
│   │   ├── tables/            # Summary tables from phyloseq
│   │   ├── logs/              # Processing logs
│   ├── figures/               # Final publication-ready plots
│   ├── logs/                  # Centralized error logs
│   └── README.md              # Summary of analysis outputs
│
├── scripts/                    # Analysis scripts
│   ├── 01_preprocessing.Rmd    # Read cleaning & QC
│   ├── 02_amptk_pipeline.Rmd   # OTU table generation (AMPtk)
│   ├── 03_phyloseq_analysis.Rmd # Community analysis & visualization
│   ├── 04_statistical_tests.Rmd # Statistical comparisons 
│   └── README.md               # Documentation for script workflow
│
├── config/                     # Configuration files for pipelines/tools
│   ├── amptk_params.yaml       # AMPtk pipeline parameters
│   ├── phyloseq_config.json    # Default settings for phyloseq analysis
│   ├── paths.yaml              # Paths to input/output directories
│   └── README.md               # Documentation for configuration files
│
├── AMPtk_OTU_Analysis.Rproj     # R Project file (renamed for clarity)
│
└── README.md                    # Project overview & setup 
```
