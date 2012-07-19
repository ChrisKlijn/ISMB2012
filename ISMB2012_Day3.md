<link href="style.css" rel="stylesheet"></link>

# ISMB 2012 - Long Beach
## Main conference - Day 2

### Workshop - From Postdoc to Principal Investigator
#### Applying
##### Florian Markowitz, CRUK

The speaker gives a general overview on how to structure your career. The first advise is to do a post doc. If you do a second post doc, although keep it short. Make sure it is an independent position.

The speaker then goes on to gave some tips on structuring your CV. Clear structure, most important information on the first page and never longer than 4 pages. The level of excitement in a letter of recommendation varies per country, make sure to tweak this.

Third section is 'be unique'. Keep your research statement short and focus on your research questions and not the tools you apply. Also, be confident, use strong words. If you expand this statement make a list of statements that define the work you did in the various position. Also, end with some short term projects for the future and add some long-term projects that show vision. One question you might get in interview is 'What is the name of your next research grant'.

The fourth statement regards the teaching statement. In a research position teaching should be presented as important, but it shouldn't be the main objective.

The fifth statement is: Find a mentor. Find a person who is a little ahead of you, to give you advice regarding making some decision. Sixth: be part of a network. Be proactive and speak to people. Seventh: think globally, apply everywhere, don't limit yourself. Eight: Enjoy the ride, don't stress and daydream. The speaker applied to 50 places, and only got 5 invites for an interview. Ninth: be lucky. Tenth: No new shoes.

#### Interviewing, deciding, negotiation. 
##### Gary Bader, University of Toronto

First question: are you sure you want to do this? Make sure you like what professors do. (ie. grant writing)

Interviews are generally 1-2 days, a seminar, 'chalk talk', meetings, dinner. Do talk science, don't talk politics (university politics or national politics). Do your homework, learn about the research of the people you will meet. Make sure you are a good fit, learn about the environment. Weigh the options between university, research institute or hospital. The speaker makes the point often that it is important to decide what you find important, it is possibility of tenure, collaborations in the institute, do you want to work in a hospital, do you want access to students?

Prepare for the question: 'What would be the first thing you do when you start?'. 

In general, you will start with an amount of money to start up your lab, and are then expected to write grants to be self-sufficient. This will be part of the negotiation. So prepare a start-up budget and include it in the negotiation. Think about computers, personnel, extra's, justification, space and amount of people. Check personal salary, and see what other people make. Think about benefits, housing, moving allowance. 

****

### Special session Computational methods for elucidating nuclear structure and dynamics
#### Using Game Engines to Build Cloud-Based 3D Genome Browsers
##### Jijun Tang, University of South Carolina

The author works on both computational biology and computer game development. This work tries to cross-over between the two worlds and use a game engine to visualize biological data. They wanted to develop this visualization to be available cross-platform, and web-based. Also, to visualize genome structures it had to be real-time, and 3d and it needs to handle large datasets. Game engines are very suitable for these requirements. They chose Unity3D as their engine.

To make the data visualizable, they had to implement some transformations on it (octree, Level of Detail). The front end is cloud-based, so any annotations you make might propagate to other users. The result allows you to fly through the nucleus of a cell and examine the chomosomal organization. 

****

### Late Breaking Research
#### Matrix geometry determines optimal cancer migration strategy and modulates response to therapeutic agents 
##### Melda Tozluoglu, CRUK Londen

The subject of this talk is cell motility. They developed a multi-scale model of single cell motility. Their model consists of a physical spring model of the membrane and the nucleus. They parameterization is based on experimental results on spreading and serum activated cells. The goals are then, once the model is trained, to challenge the cell with different matrix geometries.

The different matrix geometries showed different advantages for either a rigidly spreading cell or a blebbing membrane cell. If a cell has both options, it will use the best suited mode (spreading or blebbing). This also works in a simulated extra cellular environment and the model movement resembled actual cell movement as filmed. Their model also predicted quite accurately cell motility profiles under drug treatment.

#### Single Sample Expression-Anchored Mechanisms Predict Survival in Head and Neck Cancer
##### Yves Lussier

The main take-home of this talk is that mechanism-anchored (so focused on the mechanism) expression classifiers are feasible. This in contrast to the often used association-based expression classifiers, which are based on downstream, non-causal features.

This work is inspired by Joan Massague, who advocated the use of biologically meaningful gene expression signatures, as long as they retain their prognostic benefit. The approach of the speaker is to look for overlap between genes in a gene expression signature given a Protein-Protein Interaction (PPI) network. Their approach is called [FAIME](http://www.ncbi.nlm.nih.gov/pubmed/22291585). They claim this method is more interpretable, while having the same performance as diagnostic mathods.

#### Exploring the subclonal architecture of breast cancer
##### David Wedge, CGP Sanger Center

This talk discusses the paper on 21 whole genomes of breast cancer that was published recently in Cell. The author wants to focus on the advantages of whole genome sequencing compared to Exome sequencing, focussing the subclonal fraction of the tumor and the evolution of the genome in this population. 

Looking at single variants and copy number aberrations you can time the events leading to the final state in which the tumor was measured. Once you split the mutations in early and late events you can see different types of mutations showing up. 

To detect low-frequency sub clonal population they leverage the 1000 genomes project SNP inputation to find string together SNP calls and their copy number status. This allowed them to color a cloud of logR values according to their original chromosome. To look for sub-chromosomal subclonal deletions they use a hierarchical Dirichlet process to find these. More information should be in the paper.

They use a similar approach to find the clusters in the point-mutation space. Using presence of a SNP on reads together with a mutation, they can phase the mutations as well. 

#### The landscape of Somatic Structure Variations in Human Cancer Genomes
##### Lixing Yang, Harvard Medical School

The speaker starts discussing the various mutation-type distributions for different types of cancer. Certain tumor types have a specific mutation type associated with then, for example in melanoma and lung cancer. A similar signature exists at the breakpoints of structural variants. Structural variations generally carry a footprint of certain repair processes that caused it. 

The author created a program called 'Meerkat' to investigate the junctions of structural variants. Once the breakpoint is found, the original repair mechanism can be determined. They have applied this algorithm to a collection of diverse cancer samples and their paired germline. For somatic events no clear enrichment for given aberration was found for the given indications. Some individual samples do show an abundance of a given aberration type and repair process type.
