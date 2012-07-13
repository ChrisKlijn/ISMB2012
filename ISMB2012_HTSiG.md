<link href="style.css" rel="stylesheet"></link>

# ISMB 2012 - Long Beach

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

#### Andrew Roth, BC Cancer - PI: Shorab Shah
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

#### Sangwoo Kim, UCSD
##### Mutation calling in tumor-normal pair, controlling for normal contamination in the tumor

They want to define the joint probability matrix of the variation given a frequency of normal contamination. Their tool is called VIRMID. The algorithm relies on recursive learning of the contamination factor (alpha) given a list of variant calls and their reads.

They tested their algorithm against GATK, JointSVNMix and Strelka. On simulated data they showed that they are able to estimate alpha very well, but showed bias in high and low ranges. They fixed this and ran the test. In conclusion in 50% contamination and less, all tools work really well but VIRMID starts to outperform the rest above 50% normal contamination.

They remain relatively unclear whether the tool actually performs better in a real dataset.

#### Roman Yelenski, Foundation Medicine
##### Finding amplifications and deletions in highly stromally contaminated tumors

Current, in clinical practice, finding clinically relevant amplifications and deletions are assessed using IHC and FISH, while there are 100s of known target genes for these alterations. This company looks to determine, with diagnostic quality, the amplification and deletion status of target genes using Exome sequencing data. 

I lost the author a bit on the methods, but I guess they use the allele frequency in combination with copy number segmentation to call the amplifications and deletions. It is not clear to me how they finally call the alteration (threshold, likelihood?).They performed equally to the clinical assessment, but they tested only 4 genes (which defeats their 100s of genes argument). 

****

### Small Talks Friday Afternoon

#### Michael Brown, Pacific Biosciences
##### Sequencing of HIV genome

Current methods employ single genome amplification (SGA) to determine the sequence of a single HIV viral particle. It is important to sequence them one by one as they have a high mutation rate and might consist of many different populations in the same patient. They use the PAC-bio system to try to do this more efficiently. 

Using the PAC bio system they can read an entire 9k HIV genome at once. Measuring many of these genomes they can use sequence similarity measures they can do clustering and infer different populations present in the patient. This is obviously much less labor-intensive than the SGA. As the Pac-Bio system has an error rate at 15% they need to do consensus sequence calling within the different clusters. Although this will cancel random errors, it is unclear how they would deal with systematic errors.

In general, they manage to do some nice thing in HIV diagnostics. Unfortunately, they still have to jump through some hoops to correct the 15% error rate. It does seem that PAC bio has some good applications in pathogen sequencing, if you are interested in population sequencing. A question about the fact that on average the polymerase in the PacBio tech dies after 1000 bases due to photo damage shows that most of these reads are way out in the tail of the size distribution. Also, they apparently stopped stripe-reads (strobing the laser to get paired 100 bp reads), but they didn't explain why they stopped.

#### Alexi Gritsenko, Delft University of Technology
##### GRASS: scaffolding NGS data

Scaffolding is the process of ordering and organizing contigs that originate from assembly. They transform the scaffolding problem into an optimization problem, where they want to maximize the number of satisfied constraints that arise from linking PE-sequencing data.

The optimization problem is difficult to solve using integer programming (which would give the optimal solution), so they apply an EM-type algorithm. Finally they us a heuristic-driven overlap alignment to concatenate overlapping contigs (or choose to keep them separate).

In the end, they validate on a series of prokaryotic genomes, where GRASS outperforms other scaffolding programs on number of scaffolds and number of breakpoints. No indication how this would work on larger, more complex genomes.

#### Ali Mortazavi UC Irvine
##### RNA editing in ENCODE cell lines

The speaker talked about two types of cell lines, ones with resequencing data and ones without resequencing. The ENCODE project is a collection of many different data types from a groups of samples. The study focused on finding RNA editing. 

The data is 14 different human cell lines, RNA sequenced at 100x coverage. The canonical RNA editing step is A-I, where the I will be read as a G during sequencing. Most of RNA editing takes place into Alu-Alu duplexes between UTR and introns via a protein called ADAR1. 

To find editing they set several thresholds on the variants: 

- 10% variant frequency
- At least one read on either strands
- Remove known SNPSs

They want to maximize finding novel SNPs. Interestingly is that most non A-to-G were in 1-5 bp near an intron. This is a problem of mappers unwilling to map short overhangs across splice junctions. They eliminated all variants near splice junctions. They also filtered agains variants present in the genome

After all filtering ~85% are A-G variants, with the other variants being present in very low number. There were a little more T-C variants, but these were anti-sense transcription events of A-G variants. 

As they didn't have high depth resequenced genomes for some cell lines, they were able to use the control sample of Chip-Seq data to filter many variants as present in DNA, as the non-binding DNA in a Chip-Seq experiment is generally from expressed genes. Interesting idea.

Finally, they conclude that most RNA editing events are canonical A-G, and some conclusion on making sure you don't use old sequencing data with sequence biases. To bad they did not go into more biological implications of RNAediting (as most seemed to be associated with repeats), except mentioning it seems to happen more frequently in cell death-associated genes.






