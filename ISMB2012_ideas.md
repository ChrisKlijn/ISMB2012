<link href="style.css" rel="stylesheet"></link>

## Ideas from ISMB 2012

##### Finding subpopulations in cell lines/tumors, perhaps using copy number data?

Using LOH or loss from the Illumina 2.5M array we may define regions of LOH and copy number loss. These should have homozygous mutations only. Any heterozygous mutations in these regions may point to subclonal populations.

This is currently investigated by the BC cancer people. Maybe we can also do this for our clinical samples

Another idea might be to mix different cell lines to create a synthetic dataset of subclonal populations and see how we can detect the mixing coefficient using genomic features. 

Determination of a specific subclonal population is very significant, as they might give rise to resistance. For example, a sub population of met amplified cells gives rise to EGFR resistance. Looking in the met locus, if a region of different copy number can actually be found, the allele frequency might give hints toward subclonality.

It would also be really cool to visualize the population with regards to spatial distribution. This has never been really answered: How are the different populations located in relation to each other in the tumor mass.

The 21 breast cancers show a great way of determining subpopulations based on WGS data, where it is possible to find chromosomes that are lost or gained in specific subgroups in the data. However, it is impossible to determine which chromosomes co-segregated (is the chr. 7 loss only in the subset of cells that also lost chr 13?). If one would be able to generate single cell barcoded reads to exactly deconvolve the mixtcure. 



##### Advantages of whole genome sequencing

Many people are ignoring whole genome genome data in favor of Exome sequencing. We should try to leverage the advantages of WGS:

- Accurate SV detection
- Sequence at the breakpoints, pointing towards repair pathways 

##### Current downsides of sequencing

Mapping causes a lot of errors, and restricts our efforts to detect variants in all their forms. Filtering can get you some way, but it could be better restart and approach the problem from a different angle.