<link href="style.css" rel="stylesheet"></link>

# ISMB 2012 - Long Beach
## Main conference - Day 2

### Keynote 3
#### Analysis of transcriptome structure and chromatin landscapes.
##### Barbara Wold, Cal-Tech

###### Intro to transciptomics

The speaker first went into the history of transcriptomics, starting when just the general pool of RNA was measured in the 80s (where estimates of number of genes and expression level were remarkably accurate). Though the 90s she ends in the current era, that of high-throughput sequencing efforts. 

The speaker discussed several issues that currently plague RNA sequencing. One is the long-range contiguity, where the read lengths of current platforms is very much smaller than the wide distribution of mRNA lengths. Furthermore, RNA integrity influences the coverage on the RNA with the 5' exons being under-represented. If this integrity is different in compared samples, you get false differential expression. Due to RNA secondary structure, random priming in cDNA construction leads to very disparate read distributions.

###### Lessons from the ENCODE project

She then shifted into their work on the ENCODE project, where they examined several cell lines originating from different tissues. They examined alternative splicing in this dataset. She shows an example of alternative splicing via alternate promoters for protocadherin alpha. They applied Cufflinks for this analysis. This was mainly used to see if they could recover this use of alternative promoters, and it worked. The next subject was BHLHE40, where they discovered three new gene models. 

Finding new gene models is also affected by some problems. For example the 3' end is underrepresented, and that makes it difficult to estimate the exons and alternative transcription at that end. She again makes the point that longer reads would help very much here. Further, if you increase the data you will saturate the known junctions, but you will continuously identify novel junctions. 

Next she states that we are now able to find most, if not all, poly-A transcripts. Splicing appears inherently noisy, but the cell seem to be able to tolerate rare aberrant transcripts. This might be due to reactivity of RNA polymerase. The problem is that one gene's noise is another gene's signal, separated by orders of magnitude of transcription level. She states that novel transcript detection might be best suited for rare purified cell types and cancer. Finally, she poses a challenge: get Ribo-free RNA from FFPE material, which will be a leap forward for diagnostic application of RNA sequencing.

###### Applied RNA seq

She shows one example of FFPE sequencing from the group of Chuck Perou, where they sequenced FGFR2 (a relatively large gene). They show that they are able to recover the whole transcriptome, including intronic RNA, from the FGFR2 gene. Because poly-A pulldown does not work in FFPE you use a ribo-free method which give all RNA in the cell. How to handle that is another challenge of data analysis in transcriptomics. 

She then shoew an applied study in AML using RNAseq where they discovered a new way of producing a PML-RARA fusion, which influenced clinical direction. She then promotes RNAseq as a viable clinical diagnostic tools, which is able to see more than simple DNA sequencing.

###### Single cell poly-A-RNA-seq

Single cell sequencing of RNA is pretty difficult. The RNA catching should be perfect to capture the lowly expressed mRNAs. Unfortunately, you will catch only around 10-20%, meaning that mRNA with < 20 copies will be sampled stochastically. They applied low cell number sequencing of, for example, HSCs. The coverage plots for these experiments look relatively nice. The FPKMs of libraries deteriorate the more you dilute towards single cells. They have reasonable replicate correlation when looking at 30 cell pools. One on one cells even have a not completely terrible correlation.

She then shows an example of single cell sequencing in iPS cells. They show clustering of different cell types that is coherent to a certain degree and they find a gene involved in reprogramming. Next she quickly glosses over some studies in laser-capture micro-dissection studies on neurons.

###### Visualization of chromatin data

The final topic is using [Self-Organising Maps (SOMs)](http://en.wikipedia.org/wiki/Self-organizing_map) to visualize many different (chromatin) datatypes of the ENCODE project. They integrated 6 cell lines with 8 chromatin data types. This part of the story is very visual, where they map many heatmaps on an unfolded torus, and apply the SOM to generate ordered heatmaps. By comparing the resulting heatmaps for different chromatin marks overlaps and differences between marks can be found. 

****

## Late Breaking Research Day 2 

### Critical assessment of Genome Interpretation (CAGI)
#### Steven Brenner, Berkeley

This study is a benchmarking effort to assess whether it is feasible to estimate the impact of single nucleotide variants on the phenotype of the cell/organism. In general the speaker focuses on the direct predictors of mutation of a protein, life PolyPhen and SIFT. 

This study is a blind prediction assessment of a study where the effect on the phenotype is known, and the predictors are examined for their effectiveness. The goals are to determine the state of the art of the problme, where the bottlenecks are, which issues should be prioritized and leads into new approaches. 

The CAGI 2011 experiment was split into three parts: 

1. Challenge into different groups
2. Submission of different groups
3. Evaluation of the results

The speaker then focused on a single given challenge, on CBS amino acid mutations. The mutations were assessed for their functionality in wet lab experiments and the algorithms were tested against these results. The results are aggregated by Spearman rank correlations. A remarkable result is that for a certain algorithm training on COSMIC was worse than training on the CAGI 2010 results.

Although the SNAP algorithm was best on rank correlation, the predictions were quite noisy on a single case basis. And they were quite correlated with another good predictor, which indicates that a meta-predictor may not give much more information.

A case on RAD50 mutations, which is clinically relevant but only weakly associated with clinical output, showed some interesting results. The predictors on their own did relatively poorly (AUC = .54 as best results). But when given to the assessor, the combination of the predictor result with his knowledge was significant.

He spoke on a challenge where groups had to predict IC50s to drugs given mutations in a cell line. In general predictors did poorly, but there was a trend in the data showing that there is some progress on this problem.

He goes quickly goes through some other challenges, TP53 mutations, Personal Genome Project predictions, Chrohns disease, Asthma in identical twins and mouse phenotypes. In general, it shows that some challenges are solved reasonably well, but a lot needs to be done. No single algorithm is applicable everywhere, and analyses should be tailored to the application. 


### Chromatin Structure and Genomic Context Influence Mitochondrial DNA Insertion in Mammalian Nuclear Genome
#### Junko Tsuji, university of Tokyo

Nuclear Mitorchondrial DNA (NUMT) are copies of the mitochondrial DNA in the nuclear genome. They are found in almost every eukaryotic cell. Via DSBs in the nuclear enome MT DNA can be inserted. They can lead to cancer in some cases.

They use an altered BLAST approach to detect these insertions in the human genome. Their interest is to use them as 'molecular fossils' as the nuclear genome mutates more slowly than the active MT DNA. They find a number NUMTs in the genomes of human and related sequences. They go on to characterize these insertions based on their insertion sites. THey are inserted in a give motif, near retro-transposons, 'bendable' DNA and open chromatin regions. They have a [paper](http://nar.oxfordjournals.org/content/early/2012/07/03/nar.gks424.short) on this study.

### Computation with Chromatin Modifications
#### Barbara Bryant, Constellation Pharmaceuticals

The speaker states that chromatin itself is a computer. These chromatin computers can ba used to solve problems. The classical view of histone modification is changing the charge of a histone tail, openeing and closing the DNA. But is has emerged that the modifications are a code, placed by writer proteins and read by reader proteins. These readers and writers generally work in complexes of different enzymes.

They build a chromatin computational model consisting of an abstraction of the histone tail and called it the 'chromatin tape'. They model an enzyme that is able to read/write on several locations on this tape. THey use this model to solve the Hamilton path problem, a famous problem first solved using a DNA computer. 

As an extension of this, they are able to implement a Turning machine in chromatin 'computing' as well. The reason chromotin computer can be very quick is that there are many parallel states and other features of the cell (DNA-methylation, gene expression) can be features of a computation engine as well (got-statements, program input/output). Although really facinating, the talk lost me at describing the general solution on the Hamiltonian path. 

The eventual goal of the study is to see if any evidence of this computation system is found in real biology. A nice quote is: using static ChipSeq data to examine chromatin biology is like debugging a computer program by examining the average memory content of running a program.

### TF Target Identification based on CHIP seq data
#### Andreas Beyer, Biotec - TU Dresden

The motivation for the study was the disparity between ChipSeq data and RNA-expression data, and the evaluation of different methods that try to do target prediction of transcription factors.

In general there are two ways to evaluate peak-to-gene mapping methods. Parameterized window methods and non-parametric density-based approaches. THey set out to assess the effectivity of multiple methods on a variety of datasets. They validate on GO terms and differential expression between the TF knockout and the wild type for the top 500 genes.

The best performing method is the so-called 'ClosestPeak' method on the differential gene expression study. The best performing method on consistency and specificity is the 'ClosestGene' approach. 

The second part of the talk expands on the poor overlap between TF binding and resultant gene expression level. One of the reasons the speaker expands into is that strong TF targets respond very late to knock-down of the TF. He shows that this is indeed the case for strong targets of _Oct4_, with the majority of the genes responding after 24+ hours. So people should reconsider the timepoint of their measurement. 

This, combined with using the ClosestGene approach, which is agnostic to gene density, they are able to find better clustered groups of target genes. 





