# Awesome-AMP-Design
A list of articles and available codes of designing antimicrobial peptides (with comments).

🚧 **Last Update** 26-02-04

❗**NOTE**: All comments below are personal opinions. Issues and discussions are welcome via github or emailing me at dongruihan_at_stu.pku.edu.cn

## Contents

- [Preprints](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#preprints)

### 2026
- [Comprehensive works](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#comprehensive-works-with-comments)
- [Review](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#review)
- [Generators](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#generators)
- [Predictors](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#predictors)

### 2025
- [Comprehensive works](https://github.com/ruihan-dong/Awesome-AMP-Design/blob/main/2025.md#comprehensive-works)
- [Review](https://github.com/ruihan-dong/Awesome-AMP-Design/blob/main/2025.md#review)
- [Generators](https://github.com/ruihan-dong/Awesome-AMP-Design/blob/main/2025.md#generators)
- [Predictors](https://github.com/ruihan-dong/Awesome-AMP-Design/blob/main/2025.md#predictors)

### Before 2025
- [Comprehensive works](https://github.com/ruihan-dong/Awesome-AMP-Design/blob/main/before2025.md#comprehensive-works)
- [Review](https://github.com/ruihan-dong/Awesome-AMP-Design/blob/main/before2025.md#review)
- [Generators](https://github.com/ruihan-dong/Awesome-AMP-Design/blob/main/before2025.md#generators)
- [Predictors](https://github.com/ruihan-dong/Awesome-AMP-Design/blob/main/before2025.md#predictors)


## Preprints

- *A global deep-sea small protein atlas reveals a reservoir of noncanonical antimicrobial peptides (**bioRxiv 2025**)*
    - A mining work with highlights in new proteome sources. MIC results are not impressive, with lots of >125.
    - Interestingly, the author concludes the intracellular mechanism of their mined AMPs instead of membrane-disrupting. On the one hand, it’s really ‘unconventional AMPs’ as a new finding. On the other hand, the main advantage of AMPs is their low likelihood of inducing resistance, which is due to the membrane-lytic mechanism. So what is the advantage of non-lytic AMPs?

- *ClsDiff-AMP30: Generating Antimicrobial Peptides by a Classifier Guidance Noise Predictor (**bioRxiv 2025** | [code](https://github.com/jieluyan/ClsDiff-AMP30))*

- *A Global Discovery of Antimicrobial Peptides in Deep-Sea Microbiomes Driven by an ESM-2 and Transformer-based Dual-Engine Framework (**bioRxiv 2025** | [code](https://github.com/Li-Lab-SJTU/XAMP))*
  - A new source (deep sea microbiomes). Unfortunately, there is no experimental validation.

- *PepCompass: Navigating peptide embedding spaces using Riemannian Geometry (**arXiv 2025**)*

- *A deep reinforcement learning platform for antibiotic discovery (**arXiv 2025**)*
    - ❓“However, reinforcement learning has not yet been applied for antibiotic design”——RL has been widely used in small molecule design. For AMP generation, SeqGAN (essentially RL) has been used in several models, and RR-ADS (*J Med Chem 2025*) was published before my AMPainter (*Adv Sci 2025*). AMP-Designer also used RL to fine-tune the peptide generation model, which has been cited by them.
    - APEX model itself is a MIC regressor. However, in this article they retrained a binary classifier ApexMIC for AMPs with high and low MIC. Why don’t they use regressor as rewards directly?
    - The exp. success rate is great (100%), even though there were still lots of screening rules.
    - I was confused by the supplementary figures 10-13 since these figs were not referred in the manuscript. They can only show the limitation of predicted MIC values.
 
- *PepSeek: Universal Functional Peptide Discovery with Cooperation Between Specialized Deep Learning Models and Large Language Model (**bioRxiv 2025**)*
    - Using general LLM like DeepSeek to predict MIC is beyond my recognition… As observed from Fig 2g, it’s true that the PCC value of proposed model is higher than other models, but all the predicted values are integers. Is that what we need?
    - Reward function of reinforcement learning model is really complex. How can we define the optimal value of each physicochemical property?
    - Experimental sections are for AMPs rather than different kinds of functional peptides.
      
- *Predicting and generating antibiotics against future pathogens with ApexOracle (**arXiv 2025** | [code](https://github.com/DragonDescentZerotsu/ApexOracle))*
    - An upgrade of their APEX MIC predictor, with strain genome and text.

- *Targeted AMP generation through controlled diffusion with efficient embeddings (**arXiv 2025**)*
    - A conditioned diffusion model OmegAMP.

- *ProtFlow: Fast Protein Sequence Design via Flow Matching on Compressed Protein Language Model Embeddings (**arXiv 2025**)*
    - A flow-matching generative model with AMP generation as a task.

- *Proteasome-derived antimicrobial peptides discovered via deep learning (**bioRxiv 2025**)*

- *Design of multimodal antibiotics against intracellular infections using deep learning (**bioRxiv 2024** | [code](https://gitlab.com/machine-biology-group-public/apex_duo))*
    - Multimodal represents cell-penetration and AMP - Did they consider that many known AMPs are already cell-penetration peptides?
    - The training set of cell-penetration predictor is weird - added toxic peptides into the negative set
    - I like Fig. 4A because it’s direct to see residues that contributed to antimicrobial activity as well as toxicity. Btw, the x-axis label should be F1A instead of A1F (same for other sites)
- *A generative artificial intelligence approach for antibiotic optimization (**bioRxiv 2024** | [code](https://github.com/Yimeng-Zeng/APEXGo))*
- *De novo multi-mechanism antimicrobial peptide design via multimodal deep learning (**bioRxiv 2024**)*
    - A really complex model with structures and limited strain/mechanism labels.

- *Discovery of antimicrobial peptides targeting Acinetobacter baumannii via a pre-trained and finetuned few-shot learning-based pipeline (**Research Square 2024**)*
    - The subsequent work of *Nat Biomed Eng* 2023, focusing on *A.baumannii*.
- *Design guidelines for α-helical peptides that self-assemble into transmembrane barrel pores killing antibiotic-resistant bacteria (**bioRxiv 2022**)*


## Comprehensive works (with comments)

*in silico* mining/generation + *in vitro/in vivo* validations

- *Proteome-Mining and Chemical Activation of Hidden Bioactive Fragments as Antimicrobial Assemblies (**JACS 2026**)*
   - An application of TransSAFP (*Nat Mater 2025*).

- *Identification of antimicrobial peptides from ancient gut microbiomes (**Nat Commun 2026** | [code](https://github.com/ChenSizhe13893461199/AMPLiT))*
  - An application of AMPidentifier (*Microbiome 2025*). 

- *AI-Based D-Amino Acid Substitution for Optimizing Antimicrobial Peptides to Treat Multidrug-Resistant Bacterial Infection (**Adv Sci 2026** |[code](https://github.com/EricwanAR/DAminoMuta))*
    - A great perspective to approach the L/D-peptide issue. Collecting D-peptide data from the literature is a challenging task. The statistic in Fig 2B presents the low efficiency of experimental search well, but I didn’t find the detailed sequence and MIC data of ‘D-scan’ and ‘random’. Are they from the R2 test set?
    - ‘SMILES’ should not be ‘SMILE’ in Fig 2D and in text. ‘SMILE image’ is a strange term because the molecule images are their chemical structures. They can be transformed from SMILES but they are not the images of SMILES strings. Btw, I have always been confused by some works like ImageMol or VideoMol…The structural images aren’t unique for each molecule.
    - Experiments are comprehensive. I think there are two points to improve: 1) The improved stability induced by D-AA was not highlighted. The stability was not tested with HPLC or LC-MS directly. 2) Only 2 L-peptides with top 10 D-variants were measured. Maybe testing 10 L-peptides with their top 1 or 2 D-variants can show the ability of their predictor better.

- *AI-guided precise design of antimicrobial polymers through high-throughput screening technology on an automated platform (**Bioact. Mater. 2026**)*

- *AI agent-based discovery of D-enantiomeric antimicrobial peptides against multidrug-resistant bacterial infection (**Biomaterials 2026** |[code](https://github.com/kangluoyao/PeptiD-Agent))*
  - D-AMP is a good topic with scarce data. However, designing all-D peptides is pretty easy when you already have lots of L-peptides... What's the rationale of using an LLM to design sequences?
  - I'm curious how the author extracted the embedding of D-peptide from ESM2? ESM cannot handle D-peptide. It's just the feature of L-peptide. Again, I don't think it's reliable to predict their activity using LLM.
  - Too redundant figures in Fig. 1. These regression scatter plots can only say their MIC prediction is inaccurate.


## Review

- *Reviewing the Artificial Intelligence Boost for Accelerating the Development of Novel Antimicrobial Peptides (**J Appl Microbiol 2026**)*


## Generators



## Predictors

❗**NOTE**: I didn’t list all the relevant works here since there are so many AMP predictors. And I’m not working on AMP classifiers.

- *Motion as a Language: Transformer-Based Classification of Antimicrobial Peptide Conformational Dynamics (**JCTC 2026**)*
  - I'm surprised that this kind of work can be published in JCTC...

- *PepGraphormer: An ESM-GAT hybrid deep learning framework for antimicrobial peptide prediction (**J Cheminformatics 2026** | [code](https://github.com/lincubator/PepGraphormer))*
  
