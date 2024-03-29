# RNA-seq-demo
Galaxy based RNA-seq workflow from data transfer to gene expression and Functional Gene Enrichment annotations (FGSEA)

This tutorial will help you submit a sample RNA-seq workflow using the [Pilot GlobusGenomics instance](https://pilot1.globusgenomics.org).

## Data
The sample workflow uses data from [Bioproject PRJNA378660](https://www.ncbi.nlm.nih.gov/bioproject/?term=PRJNA378660). It is composed of 9 samples (5 control, 4 cases). The input files are compressed fastq files and they have previously been uploaded to our instance to prevent additional data upload to the instance. Typically, the user could use the EBI SRA upload tool by indicating the bioproject accession number to get the data.

## Workflow
There are two workflows that the user should import into their account. The [first]( https://pilot1.globusgenomics.org/u/arodri7/w/master-hisat2-limma-wf---for-demo---version2-imported-from-uploaded-file) manages the submission of the individual samples through [alignment and feature counts]( https://pilot1.globusgenomics.org/u/arodri7/w/hisat2-stringtie-ballgown-databag-phase1-imported-from-uploaded-file). The workflow uses HISAT2 for alignment of the raw reads and featureCounts for read summarization. Once the individual samples have been analyzed, the main workflow gathers the results and performs differential expression analysis using LIMMA. Finally, the workflow performs a functional gene enrichment analysis. The outputs for the workflow are tables for the differentially expressed genes, tables for the enriched workflows, plots, alignment and summarization files.

## Steps
The following are the list of steps to follow to start the analysis on the instance.
1. Log on to the [pilot1 instance](https://pilot1.globusgenomics.org).
2. Import the workflow "[MASTER-HISAT2-LIMMA-WF - FOR Demo - version2](https://pilot1.globusgenomics.org/u/arodri7/w/master-hisat2-limma-wf---for-demo---version2-imported-from-uploaded-file)" by clicking on the link and then clicking on "Import" icon. <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/ImportImage.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/ImportImage.png" width="100" height="50" alt="importWorkflow"/>
3. Import the workflow "[HISAT2-StringTie-BallGown-DATABAG-Phase1](https://pilot1.globusgenomics.org/u/arodri7/w/hisat2-stringtie-ballgown-databag-phase1-imported-from-uploaded-file)" by clicking on the link and then clicking on "Import" icon.
    * Make sure when you import the workflow, the name of your workflow is "HISAT2-StringTie-BallGown-DATABAG-Phase1". If it's not, please go ahead and rename the workflow.
      1. Click on the workflow of interest.
      2. Select "Rename" option.
      3. Rename the workflow to exactly "HISAT2-StringTie-BallGown-DATABAG-Phase1".
      <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/RenameWorkflow.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/RenameWorkflow.png" width="300" height="225" alt="importWorkflow"/>
4. If you have not created an API key before, please create one now.
    1. Click on the "User" menu link and then on "Preferences".
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/UserMenu.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/UserMenu.png" width="600" height="150" alt="importWorkflow"/>
    2. Click on "Manage API Key" link.
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/manageAPI.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/manageAPI.png" width="400" height="150" alt="importWorkflow"/>
    3. Click on "Create new key" link.
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/createAPI.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/createAPI.png" width="400" height="50" alt="importWorkflow"/>
5. You will need to import the data to your history. We have published a history called "[RNA-seq-demo-raw-data](https://pilot1.globusgenomics.org/u/arodri7/h/rna-seq-demo-raw-data)". You can follow the link and import it to your own environment by clicking on the "import" link. You will need to make this your active history:
    1. Go to the main page of the [pilot1 instance](https://pilot1.globusgenomics.org).
    2. Click on the gear icon at the top of the history panel.
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/gearIcon.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/gearIcon.png" width="200" height="50" alt="importWorkflow"/>
    3. Select the "Saved histories" link.
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/savedHistories.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/savedHistories.png" width="150" height="250" alt="importWorkflow"/>
    4. Select the history you have just imported "RNA-seq-demo-raw-data" and click "Switch" link.
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/switchHistory.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/switchHistory.png" width="300" height="250" alt="importWorkflow"/>
6. Now you should be ready to submit the workflow.
    1. Go to the "Workflows" link on top of the page.
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/workflowsMenu.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/workflowsMenu.png" width="400" height="50" alt="importWorkflow"/>
    2. Select the workflow "MASTER-HISAT2-LIMMA-WF - FOR Demo - version2" and click on "Run".
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/workflowsRun.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/workflowsRun.png" width="400" height="300" alt="importWorkflow"/>
    3. Fill in the appropriate inputs.
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/workflowsParams.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/workflowsParams.png" width="1000" height="1000" alt="importWorkflow"/>
    4. Submit the workflow by clicking on "Run Workflow".
    5. Wait a while for your results.
    <br><img src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/workflowsSubmitted.png" data-canonical-src="https://github.com/arodri7/RNA-seq-demo/blob/master/images/workflowsSubmitted.png" width="500" height="400" alt="importWorkflow"/>

    
## Outputs
The following are the main outputs you should see:
1. Bag object of the BAM files and summarization files for each sample. You can view each sample summarization file by browsing your "Saved histories".
2. Differentially expressed list of genes using LIMMA R package.
3. Functional gene set enrichment analysis using the FGSEA R package.
  
