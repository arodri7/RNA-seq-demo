# RNA-seq-demo
Galaxy based RNA-seq workflow from data transfer to gene expression and Functional Gene Enrichment annotations (FGSEA)

This tutorial will help you submit a sample RNA-seq workflow using the [Pilot GlobusGenomics instance](https://pilot1.globusgenomics.org).

## Data
The sample workflow uses data from [Bioproject PRJNA378660](https://www.ncbi.nlm.nih.gov/bioproject/?term=PRJNA378660). It is composed of 9 samples (5 control, 4 cases). The input files are compressed fastq files and they have previously been uploaded to our instance to prevent additional data upload to the instance. Typically, the user could use the EBI SRA upload tool by indicating the bioproject accession number to get the data.

## Workflow
There are two workflows that the user should import into their account. The [first]( https://pilot1.globusgenomics.org/u/arodri7/w/master-hisat2-limma-wf---for-demo---version2-imported-from-uploaded-file) manages the submission of the individual samples through [alignment and feature counts]( https://pilot1.globusgenomics.org/u/arodri7/w/hisat2-stringtie-ballgown-databag-phase1-imported-from-uploaded-file). The workflow uses HISAT2 for alignment of the raw reads and featureCounts for read summarization. Once the individual samples have been analyzed, the main workflow gathers the results and performs differential expression analysis using LIMMA. Finally, the workflow performs a functional gene enrichment analysis. 
