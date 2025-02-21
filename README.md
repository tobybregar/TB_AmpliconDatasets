# Generating OTU tables through AMPtk
<img src="images/3166CAF0-0BFF-4A7D-B8BB-D13DCCAE0705_1_105_c.jpeg" style="float:left; margin-right: 15px; width: 200px;">
<p> # Generating OTU tables through AMPtk </p>

1.  **Clone the repository** and rename it to match your project (e.g., `FungiFire`).

```{bash}
git clone https://github.com/UW-ForestMycobiomeLab/AmpliconDataSets.git MyProject
cd MyProject
```

2.  **Organize your raw sequencing data:**

    -   Copy your **unmodified raw sequencing data** into `data/raw_data/sequencing/`.

    -   Ensure your sequencing files are in `.fastq.gz` format and **unzipped** before processing.

3.  **Prepare your metadata file:**

    -   Place a metadata file inside `data/processed_data/metadata/`.

    -   This **must** be a `.csv` file.

    -   Sample names **must match** sequencing lane names exactly.

    -   Include other site-level metadata (e.g., sample ID, collection date, location).

4.  **Run the analysis pipeline:**

    -   The scripts will automatically generate required output files and folders (e.g., `intermediate_data/` and `processed_data/`).

    -   Run the scripts in `scripts/` sequentially:

5.  **Backup your data on Zenodo:**

    -   Duplicate your **raw data** files into a **private [Zenodo repository](https://zenodo.org/communities/uw-forestmycobiomelab/records?q=&l=list&p=1&s=10&sort=newest)** to ensure safety and accessibility.

    -   Once your analysis is complete, **upload processed data** to the same repository for archiving (data/processed).

**Happy analyzing! :)**

```         
project_root/
│
├── data/                         # Main data directory
│   ├── raw_data/                  # Unmodified raw sequencing data
│   │   ├── sequencing/            # Raw FASTQ files
│   │
│   ├── intermediate_data/      # Intermediate files from preprocessing
│   │   └──  amptk/             # AMPtk intermediate files
│   │   │   ├── demux_reads.fq.gz  # Demultiplexed reads
│   │   │   ├── clustered_otus.fa  # Clustered OTUs
│   │   │   ├── filtered_otus.fa   # Filtered OTUs
│   │   │   ├── logs/              # AMPtk logs
│   │   │   └── otu_tables/   # backup .biom file and .txt 
│   │
│   ├── processed_data/             # All cleaned & processed data
│   │   ├── metadata/               # Sample metadata files
│   │   │   └── metadata.csv            # Sample metadata (must match) 
│   │   ├── phyloseq/                   # Phyloseq-ready processed data
│   │   │   ├── STUDY_phyloseq_rare.rds # Rarefied dataset 
│   │   │   └── STUDY_phyloseq_unrarefied.rds #Dataset pre-rarefaction
│
├── fungaltraitsDB/    # Database for fungal trait information
│   └── FungalTraits_1.2_ver_16Dec_2020.csv #fungaltraits db
│
├── scripts/                        # Analysis scripts
│   ├── part1_amptk_phyloseq_pipeline.Rmd # OTU table generation 
│   └── part2_analysis.Rmd       #Quick-start analysis
│
├── figures/                  # General figures and exploratory plots
│   ├── exploratory/          # Preliminary data visualizations
│   ├── publication/          # Final figures for publications
│   ├── README.md             # Notes on results generation
│
├── AMPtk_OTU_Analysis.Rproj    # R Project file (renamed for clarity)
│
└── README.md  # Project overview & setup
```
