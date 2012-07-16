<link href="style.css" rel="stylesheet"></link>

# ISMB 2012 - Long Beach
## Main conference - Day 1

### Keynote 1
#### Seeing forward by looking back
##### Richard Lathrop, Lawrence Hunter

The keynote that opened the conference is in honor of the 20th anniversary of the ISMB, so it contains more of a historical overview than direct science. It is presented by two of the founding board members of the ISCB.

Richard Lathrop gave an overview of the beginnings of computational biology, going from preceding meetings and presence of computational biology in literature in the 80s and 90s. Lawrence Hunter took over, and tries to sketch a vision on the future of computational biology. 

As his background is in AI, he focuses on its history in computational biology. He predicts that the first true AI 'mind' will be one that thinks about molecular biology. In this fashion, it appears the IBM **Jeopardy** AI 'Watson' will be applied to biomedicine. One thing that makes molecular biology very amenable for AI, is the fact that almost all knowledge is available to machines, in the form of texts, databases etc. This touches on his own work in ontologies and mechanistic explanation of knowledge. He then goes onto some more in-depth discussion of his own work on 'interestingness', which is an automatic evaluation of explanation and judgment statements.

### Keynote 2 (Overton award)
#### Data integration for understanding dynamic biological systems
##### Ziv Bar-Joseph, Carnegie Mellon

The keynote started with a historical overview of his career, where he pointed out that now is a good time to start computational biology. His main work focuses on dynamic networks and temporal data. Recently the has started working on de novo RNA assembly and crowd sourcing for protein interaction annotation.

He then goes on to expose the different work that he has been doing on the different levels of high throughput time-series experiments (Experimental design -> data analysis -> pattern recognition -> models and system). He will go in depth on models and systems in time series. His particular interest has been gene regulation in a time-dependent manner. Most high-throughput data is static, so it is difficult to introduce the time dimension.

He introduces [DREM Dynamic Regulation Events Miner](http://www.sb.cs.cmu.edu/drem/msb.html), where he combines time-series data with static data to 'elevate' the static data to a temporally described information source. The way they do this is to use an Input-Output HMM, where the static information is an additional probability constraint on the HMM. This can then be used to assess rewiring of the cell, by changing the static interactions.

In regulatory networks it is always they question: who regulates the regulators? These are usually the top genes of the signaling pathways. The next step for the DREM program was to introduce the signaling pathways next to the transcription factor information. This was quite a complex procedure, but it works under a set of assumptions. He shows an example of the HOG pathway in yeast.

A human application of their approach was tested in the context of viral infection. They found that several strains of Flu and SARS targeted the same regulatory networks. This network was reasonable predictive of RNAi screens done in the same infection setting.

****

## Late breaking research - Day 1
### Daniela Bornigen, University of Leuven
#### Computational approach to associate protein (mutations), tissue and phenotype

To this end they use protein complex information and gene expression data. They use protein information on a protein complex level, using the inWeb network. For gene expression, they use data from 128 tissues, which they subset (based on number of replicates) to 36 tissue under normal conditions. For a given protein complex they calculate co-expression of its substituents to see if a complex is active in a given tissue.

Then, using mutation data, they assess which tissue will be most affected if the hub-protein in a complex is mutated. They have a gold standard of known tissue-complex association that they use to validate their predictions. In general some tissues preformed better than other, which they claim is due to heterogeneity of the tissues. As a positive example the speaker showed mutation in the LMNA (Lamin) protein complex in skin and heart, and linked them to Progeria's disease which is associated with this complex. They also show an NF-K-B link to prostate, although this result was on the low end of their results score.

### Tammy Cheng, CRUK LRI
#### Quantifying the Systemic Consequences of Point Mutations in Proteins through Pathway Dynamics and Protein Structures, 

This is a talk about mutation impact prediction. They use protein structural information to estimate the impact on the protein. They calculate the average effect of a mutation for all possible structural conformation and use an analytical model of the protein function. As far as I gather, this doesn't work genome wide but requires a differential equation system of the pathway where the protein works. 

As an example the speaker presented mutations in Cdk1 Cyclin complexes in fission yeast, using an analytical description of their function. They look at the effect on rate constants of the mutation and give the mutation a systemic impact factor. Their second example is in the MAPK pathway for several congenital diseases. 

### Inanc Birol, Michael Smith Genome Sciences Centre - BC Cancer Agency
#### Assembly of RNAseq to detect novel poly-A sites

The focus of the study is the mRNA cleavage at the poly-A site. They studied this in and AML dataset. The reason for this dataset is that 27% of the patients carry an NPM1 mutation, a gene that works in poly-A processing. This affects the 3' UTR, which in turn affects miRNA regulation of NPM1 target genes. 

They reconstruct the 3' UTR using Trans-ABYSS assembly of the transcripts. The assembled transcripts are mapped back to the genome. Then they examine those for poly-A cleavage sites. The data the use is quite high depth, 350-500 Mreads. They find that variants in the hexamer motifs cause differential UTR lengths in various genes. This includes not only the destruction of the cleavage motif but also the creation of cleavage sites.

Many of the variants in the cleavage motifs that are not found in DNA data show the canonical A-I motif, possibly representing RNA editing. 

****

## Workshop Track Computational Drug Repositioning and Systems Pharmacology
### Russ Altman, Stanford University (Bioengineering, Genetics, Medicine, CS)
#### Drug interactions as markers for repurposing opportunities

The main focus of the lab of R. Altman is molecular and cellular effects of drugs. They use:

1. Structural and molecular data
2. Expression data
3. Text information 
4. Population and clinical data

The question is: can you use protein co-structures with drugs to predict new effects. They use a system called FEATURE that is a statistical description of a compound binding pocket. This allows similarity searches using the physiochemical characteristics, instead of just the conformation ([Liu & Altman, PLoS Comp Bio 2011](http://www.ploscompbiol.org/article/info%3Adoi%2F10.1371%2Fjournal.pcbi.1002326)). This might find new potential binding proteins for a given compound. 

On the expression side, they did ICA (Independent Component Analysis - not explained) on all 20k GEO datasets. They found 450 components that explain variability in all expression datasets. They used these component in a differential expression study (instead of genes) in a differential drug treatment study. Using the components that appear to be significant they can define new treatment domains according to the GEO datasets that enrich for those components as well. 

The third approach is using PubMed for text mining studies. They identify sentences that link genes drugs and diseases and extract the information from them and store that in a standardized vocabulary. Examining the standardized network that flows from that information, and that network can be used to predict drug-drug interactions by finding drugs that both work on the same gene/protein.

The final data source they use is FDA and Electronic Patient Records to correlate adverse events in clinical trials to cluster drugs. Not only could they find correlated single drugs, but also combinations of drugs that have an adverse effect only in combination. 

### Pankaj Agarwal, GSK - Director Drug Repositioning Computational Biology
#### Can Computational Biology Deliver Systematic Drug Repositioning?

The speaker starts with introducing drug repurposing and finding correct indications in which to use a drug. There is a large spectrum of data that can be used to identify new clues for retargetting drugs. 

He starts out with discussing GWAS studies to reposition drugs. He intersected the genes known to have a genetic association and genes that are targets of an industry pipeline. There are 155 GWAS-implicated genes, of which 63 genes were implicated in the same indication where the drug was designed. But for 92 there was a discrepancy, and some of these may be a new repositioned target of the drug. An example for which this worked was Denosumab, originally designed for osteoporosis and targeting RANKL. This gene appeared to be involved in ulcerative colitis and Crohn's disease.

Next topic is the connectivity map. This collection of gene expression signatures is a classic way of doing drug repurposing. He showed several examples where papers showed associated of a certain phenotype with known drug response signatures. GSK is using this in a larger networked approach, but the specifics were not very clear. It seemed more that they didn't find any good validable results.

He continues about using the side effect data to correlate drugs and conditions. The reasoning they try to construct is: what is a common side effect for a drug used for a certain gene; any other drug that causes the same side effects might be used in that disease.

Then there are two very small unclear parts about gene network overlap in which the method is not very clear.

### Yves Lussier, University of Chicago
#### Rescuing targeted compounds with combination therapy and protein interactions models.

The introduction start with network medicine, where the speaker makes that point that functional annotation is disjoint from the disease-gene interaction network. His point is that it is necessary to understand the mechanism of a gene/disease to understand the drug action on it, and therefore also to repurpose drugs to new diseases.

He then goes on to stress that a _mesophenotype_ needs to be defined to fill the gap between the actual influence (genetics, drugs etc) and the clinical phenotype. Unfortunately the talk was relatively vague here. An example of a mesophenotype is the well known heamophelia mutation, where the mutation has the mesophenotype called 'deregulated coagualtion pathway' and a phenotype of hemophelia.

From this point on the talk is really hard to follow, but mainly talks about [Lee et al, PLoS Computational Biology 2010](http://www.ncbi.nlm.nih.gov/pubmed/20369013).
