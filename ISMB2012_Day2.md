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

### Keynote 4
#### Progress, challenges and opportunities in population genome sequencing
##### Richard Durbin, Sanger Institute

Identical twins show that there is a strong role of genetics in health and human variation. The direct way to look at genetics is to sequence genomes, which has become easier in the last decade. The speaker predicts millions of sequenced genomes to be done by 2020.

###### 1000 Genomes

The speaker poses the question whether a reference genome is the right way to keep comparing genetics, or whether a richer representation is needed. He then goes on to describe the 1000 genomes project. The aims of the projects are, interestingly enough, to sequence 2500 people, with a 95% accuracy for the 1% frequency SNPs. Phase one was completed in 2011 where they analyzed 1100 samples. The new 2500 samples set selected a large group of new populations. For these samples they plan to do 4x WGS and deep exome data. Currently, the phase 1 series has 38.9M variants, 1.4M indels and 14K large deletions.

Due to the pooling of samples, they are capable of detecting with 99% accuracy any variant that is present at a rate of 1%. Genotyping data is less effective, but improves if LD is taken into account. The speaker then continued on some of the issues the 1000 genomes faces. Many are due to errors in sequencing:

1. Base call errors (independent per sequencing platform)
2. Sampling error, not all samples are investigated equally deep
3. Mapping errors, the source of most errors

###### Assembly-based variant detection

Mapping errors are highly dependent and cause almost all the problems. One way they solved this is by chucking regions where there were too many variants too close. They use filters to solve these issues, but the best solution is to change the reference. He is of the opinion that we should move to an assembly-based approach. He proposes to use the Burrows-Wheeler transform methods in a combined assembly/mapping approach. To this end he utilizes the FM index in an assembly approach, implemented in an algorithm called SGA.

The application of assembly in detection of variation would be in an approach of reference free variation detection. The way they do it is by just assembling the differences between samples. Taking unique k-mers for a given sample in comparative assemblies and reconstructing the graph around those unique nodes in the De Bruijn graph. 

They detect new indels, but fail to find all SNPs in a validation set of data. Although the current approach is not viable yet, it will be valuable to put more efforts in developing reference-free assembly methods. 

###### Regulation of gene expression

The speaker then changes subjects: the next part will be about gene regulation. the first example is small RNAs that regulate mRNAs. They examined small RNA QTLs and found 14 small RNAs regulated in _cis_ with a SNP. Of these 14, 8 are also eQTLs for genes. 4 of them were significant in a BMI GWAS. However, there is no direct correlation between miRNA and mRNA expression levels. 

His final topic is an analysis of CTCF binding sites on 60 1000-genomes samples. They find several QTLs with the binding sites. There is an enrichment of these QTLs directly in the motif for binding of CTCF (25%). However, 75% is not in the motif themselves, so they are looking for other DNA features influencing CTCF binding.

###### Bank of iPS cells

There is a new project started by the Wellcome trust to establish a UK human iPS cell bank from 500 normal people and 500 people suffering from a mono-genic disease. The problem with iPS is the generation of new mutations, however according to a clonogenic test there are between 1-5 new mutations in the generation of the lines. iPS cells also cluster by ES state, not by tissue of origin in RNAseq data. Different cell lines do show different ability to differentiate. This is a good system to examine genetic influences on differentiation.  

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

****

## Special Session - Bioinformatic Integration of Diverse Experimental Data Sources

### Network biology
#### Trey Ideker, UCSD

Network biology goes from genotype to phenotype via a mode (the network), where the intermediate model is constructed/annotated from a diverse collection of data types. The networks can be actively 'colored' by certain datatypes to find functional submodules. 

An example is an RNAi dataset in the context of HIV infection. By looking for local enrichment for RNAi phenotypes in the network, mechanisms can be found that work in HIV infection. Another example is mapping genetic synthetic lethal interactions on a physical interaction network. 

The rest of the talk will be on NeXO (Network Extracted Ontologies). The statement he poses is that clustering of data is flat, or modular. But there is a general hierarchy in biology. (proteins -> subunits -> complexes -> pathways -> cellular programs). This is evident in the organisation of the Gene Ontology (GO) classes. The challenge the speaker poses is: can we cluster a network in a hierarchical manner? 

Interestingly, in GO terms, especially smaller leaf terms, there is already a large enrichment of interacting proteins. Now, he looks to find ontologies directly from the network. They do this with an altered algorithm for social network mapping, which they call NeXO. They then map the GO terms from the human annotated GO to the network GO. Basically, the network ontology is good at recapitulation of cellular component GO part, but not molecular function or biological function. This additional annotation results in a much more informative network than the single PPI network.

### Unsupervised clustering methods in systems biology and systems pharmacology
#### Avi Ma'ayan, Mount Sinai 

The speaker will focus on two subjects:

1. Expression2Kinases
2. Sets2Networks and Genes2FANs

The speaker starts with the introduction of a set of web-based tools, PPI, Genes2Networks, ChEA, KEA. These are then combined into an analysis of protein kinases that regulate transcription factors (ie. examine the upstream components of differentially expressed genes). They call this approach Genes2Kinases. They apply this data to the L1000 data (mini-microarrays that are very cheap to run). The ruslt of this analysis is a bit vague to me.

Genes2FANs is a tool to examine enrichment in networks that are constructed from Broad-produced gnee enrichment set lists, so-called GMT files. They have web-interface to do these studies. 

The speaker went on to introduce a lot of different ways to construct networks, including collaborator networks etx.

****

## Special Session - Celebrating Science Together: ISMB 20 Years and NIGMS 50th anniversary special session

### Linking genes to traits efficiently
#### Ed Marcotte

The classic way to link genes to a trait is to look in the local network neighborhood to find genes that are close to a gene that is known to be associated. Evolution guides the way in these cases, where plant data is driven by yeast and animal data. The speakers' research basically focuses on defining small modules of genes that harbor a functional relationship, but in different organisms lead to different phenotypes when disrupted. These modules are called 'phenologs'.

An example of this is a SOX13 knock out in fish induces strong angiogenesis defects, and it has the same function in human endothelial genes, but was identified in yeast where its knock out causes lovastatin sensitivity. They take this result back to yeast and examine other genes that are involved in lovastatin resistance and find new drugs that might work as angiogenesis inhibitors in higher organisms. They find one such example for a compound that was approved in another indication 40 years ago. 

