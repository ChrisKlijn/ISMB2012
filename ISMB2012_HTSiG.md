<link href="style.css" rel="stylesheet"></link>

# ISMB 2012 - Long Beach 2012

## High-throughput sequencing special interest group

### Keynote Stanley Nelson - UCLA
#### Clinical Implications of Next Generation Sequencing

The speaker went into Exome sequencing first as a part of clinical diagnostics, listing its advantages and disadvantages. Some interesting points:

- 96% disease causing genes are captured
- CG depletion in capture

As clinical pipeline, they have a rigorous tested, certified and 'calcified' pipeline to get consistent result. They have found quite a bit of causal genes to many different genetic diseases.

Turn-around is around 4-12 weeks, and costs $ 6,500 for a trio (mother, father, child). Around 50% of the time they can provide a valid diagnosis, half of those involve a new gene mutation previously unknown. The speaker continued to expose on several case studies where Exome sequencing showed causal mutation in some developmental issues.The author shows a case where the exome sequencing changed the diagnosis from ALS to a more rare disease, according to a homozygous mutation found in a known causal gene. 

He exposed a paper [Willer et al, Nat Genetics 2012](http://www.ncbi.nlm.nih.gov/pubmed/22522420) where the clinical sequencing and the research side worked together. This paper found a novel complementation group for Walker-Warburg syndrome. Mainly, the combination of research and clinical diagnostics allowed for the characterization of the novel complementation group, which needed the experiments to validate. 

There are still technical challenges to the work. Alignment issues cause false positive SNPs. Regions of repeats are still difficult to characterize. 

****

### Small Talks Friday Morning

#### Andrew Roth (BC Cancer - PI: Shorab Shah)
##### Inferring cellular frequency of somatic mutations from NGS data

The authors attempt to asses the cellular frequency of mutations, besides the allelic frequency of mutations. This tackles the problem on how to determine sub clonal populations of mutations. They propose a targeted deep sequencing method:

1. Whole genome seq
2. Identify mutations
3. Use targeted PCR to amplify mutations
4. Ultra deep sequencing of targeted mutations

This still prevents the direct assessment of the cellular frequency of mutation. The assumption that can be used to solve this problem is that cellular frequency is induced by specific subpopulations. So use a Bayesian approach, which has priors based on copy number etc, to try to determine mutation carrying subpopulation. 

The model that they use (Bayesian, with a Dirichlet prior), is very dependent on high depth of sequencing. In the end their results seem underwhelming. No clear conclusions were drawn and it didn't seem that they were able to see very distinct populations. 

#### Tabrez Mohammad - San Antonio
##### RNAseq and ExomeSeq in two Ewing's Sarcoma cell lines that show differential drug resistance

They study Ewing's Sarcoma, which carries the canonical EWS/FLI1 fusion protein. Apparently there are different types of fusions, type 1 and type 2 with different clinical outcome. Unfortunately, the study doesn't seem very good. They assessed RNAseq gene expression after micro-tubule poisons in two cell lines carrying type 2 fusion genes. Some genes were differently expressed, but that didn't really add any information.

The Exome seq data seemed even weirdly assessed.

#### Sangwoo Kim (UCSD)
##### Mutation calling in tumor-normal pair, controlling for normal contamination in the tumor

They want to define the joint probability matrix of the variation given a frequency of normal contamination. Their tool is called VIRMID. The algorithm relies on recursive learning of the contamination factor (alpha) given a list of variant calls and their reads.

They tested their algorithm against GATK, JointSVNMix and Strelka. On simulated data they showed that they are able to estimate alpha very well, but showed bias in high and low ranges. They fixed this and ran the test. In conclusion in 50% contamination and less, all tools work really well but VIRMID starts to outperform the rest above 50% normal contamination.

They remain relatively unclear whether the tool actually performs better in a real dataset.

#### Roman Yelenski, Foundation Medicine
##### Finding amplifications and deletions in highly stromally contaminated tumors

Current, in clinical practice, finding clinically relevant amplifications and deletions are assessed using IHC and FISH, while there are 100s of known target genes for these alterations. This company looks to determine, with diagnostic quality, the amplification and deletion status of target genes using Exome sequencing data. 

I lost the author a bit on the methods, but I guess they use the allele frequency in combination with copy number segmentation to call the amplifications and deletions. It is not clear to me how they finally call the alteration (threshold, likelihood?).They performed equally to the clinical assessment, but they tested only 4 genes (which defeats their 100s of genes argument). 



