# Awesome-AMP-Design
A list of articles and available codes of designing antimicrobial peptides (with comments).

🎇 **Last Update** 26-01-02

❗**NOTE**: All comments below are personal opinions. Issues and discussions are welcome via github or emailing me at dongruihan_at_stu.pku.edu.cn

## Contents

- [Preprints](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#preprints)
- [Comprehensive works](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#comprehensive-works-with-comments)
- [Review](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#review)
- [Generators](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#generators)
- [Predictors](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#predictors)



## Preprints

- *A global deep-sea small protein atlas reveals a reservoir of noncanonical antimicrobial peptides (**bioRxiv 2025**)*
    - A mining work with highlights in new proteome sources. MIC results are not impressive, with lots of >125.
    - Interestingly, the author concludes the intracellular mechanism of their mined AMPs instead of membrane-disrupting. On the one hand, it’s really ‘unconventional AMPs’ as a new finding. On the other hand, the main advantage of AMPs is their low likelihood of inducing resistance, which is due to the membrane-lytic mechanism. So what is the advantage of non-lytic AMPs?

- *ClsDiff-AMP30: Generating Antimicrobial Peptides by a Classifier Guidance Noise Predictor (**bioRxiv 2025** | [code](https://github.com/jieluyan/ClsDiff-AMP30))*

- *AI-driven discovery and optimization of antimicrobial peptides from extreme environments on global scale (**bioRxiv 2025** | [code](https://github.com/HUST-NingKang-Lab/SEGMA))*

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

- *AI agent-based discovery of D-enantiomeric antimicrobial peptides against multidrug-resistant bacterial infection (**Biomaterials 2026** |[code](https://github.com/kangluoyao/PeptiD-Agent))*
  - D-AMP is a good topic with scarce data. However, designing all-D peptides is pretty easy when you already have lots of L-peptides... What's the rationale of using an LLM to design sequences?
  - I'm curious how the author extracted the embedding of D-peptide from ESM2? ESM cannot handle D-peptide. It's just the feature of L-peptide. Again, I don't think it's reliable to predict their activity using LLM.
  - Too redundant figures in Fig. 1. These regression scatter plots can only say their MIC prediction is inaccurate.

- *Design of highly potent antibiofilm, antimicrobial peptides using explainable artificial intelligence (**J Chem Inf Model 2025** | [code](https://github.com/Laboratoire-de-Chemoinformatique/GTM_WAE))*
    - WAE from CLaSS and GTM (generative topology mapping) for antibiofilm and antimicrobial analogs. Data preparation is ambiguous.

- *Mechanism-driven screening of membrane-targeting and pore-forming antimicrobial peptides (**Adv Sci 2025** | [code](https://github.com/ComputBiophys/Pore-Forming_AMP_SVM))*
   - 🎈 Our group's work. The first predictor to recognize membrane-active AMPs, even though it was just an SVM.
   - Success rate is not high (39%).

- *Unveiling novel antimicrobial peptides from the ruminant gastrointestinal microbiomes: A deep learning-driven approach yields an anti-MRSA candidate (**J Adv Res 2025**）*
  - It's unusual that the authors set the maximum length to 300, which is significantly longer than peptides.
  - It looks like Fig. 1 refers to AMP-BERT. By the way, ProtBERT-BFD has been widely used in AMP-related works since AMP-BERT used it. Why did they not test other pretrained language models?
  - Comparison lacks some recent models as baselines.
  - It's interesting to see coarse-grained umbrella sampling to calculate the PMF of membrane penetration.

- *Rational screening of anti-E. coli peptides via GAT-MD integration leveraging foodborne antimicrobial sequence features (**Food Chem 2025**)*
  - Applications in food models are interesting.
  - Docking with common resistance targets is meaningless.
    
- *Tailored structured peptide design with a key-cutting machine approach (**Nat Mach Intell 2025** | [code](https://github.com/LabBiocomp/KCM))*
    - It's not a good idea to design AMP (or some short peptides) as a structure-based case. SSE of optimized AMPs cannot provide something new.

- *DLFea4AMPGen de novo design of antimicrobial peptides by integrating features learned from deep learning models (**Nat Commun 2025** | [code](https://github.com/hgao12345/DLFea4AMPGen))*
    - The anti-oxidative feature is a relatively rare aspect of AMPs.
    - Baselines are out of date. This is somehow understandable. I guess the initial submission date is earlier than the displayed received date. Usually, the model training was finished much earlier.
    - The main highlight of this article is the comprehensive SHAP analysis. As for the development of new AMPs, fixed-length (13AA is short) and fragment combinations hindered exploration in a larger space. The sequences of their candidate AMPs also showed this.
    - ❗The bioactivities of candidate peptides were tested with a single concentration (128 μM). Since they just contained 13 residues, their concentrations in μg/mL are even larger than 128. MICs of only 2 peptides were reported. The same strategy was adopted for hemolysis and cytotoxicity tests.

- *A generative artificial intelligence approach for the discovery of antimicrobial peptides against multidrug-resistant bacteria (**Nat Microbiol 2025** | [code](https://github.com/W1V1995/AMP_Project))*
    - The authors did classification (AMP and toxicity) and generation using the same GPT framework. Large-scale tested peptides (196) with a success rate of 73%.
    - The authors claimed that AMPSorter can handle unnatural AAs - It’s easy to adding tokens. But it’s difficult to generalize to new seqs with such a data insufficiency.
    - Mechanism experiments are sufficient, using a G- and a G+ drug-resistant strains. An RNA-seq data was also showed.
    - By the way, I prefer the preprint title (Large language models enable high-throughput mining and generation of antimicrobial peptides against clinical superbugs).
    - Some figure factors are directly from NBE 2023 or NBT 2022...

- *Deep Learning-Driven Discovery of Novel Antimicrobial Peptides from Large-Scale Protist Genomes and Experimental Characterization (**J Chem Inf Model 2025** | [code](https://github.com/liwenhaoj/protozoa_amp))*

- *Controllable Generation of Pathogen-Specific Antimicrobial Peptides Through Knowledge-Aware Prompt Diffusion Model (**Adv Sci 2025** | [code](https://github.com/wyky481l/KPPepGen))*
    - Developing pathogen-specific peptides is a good point. Actually, most known AMPs can inhibit various pathogens due to a unified mechanism. I guess it’s hard to design selective peptides with current peptide data.
    - ⁉️ I’m curious there were lots of docking results. **AMPs are usually associated with the membrane-disruptive mechanism**, which has been validated in many articles. However, they used protein-protein docking as the main validation approach in this article, even though they used an old TM_tend score (for transmembrane! and highly correlated with hydrophobicity) as a major comparative metric. **If generating specific target-binding AMPs is their aim, they should emphasize it.**
      - It’s true that some AMPs can bind to protein targets, and PBPs are common antibacterial targets. But they should not choose them as validated target structures with no specific concern. Diverse proteins can be peptide-binding targets, and they did not even mention the protein name of their docking target in the main text, as well as the reasons for choosing them. (I have to say, at least they didn't say ‘LPS is a protein’…)
      - I think it’s reasonable to assume that pathogen-specific AMPs are related to some protein targets of different species. However, the results in Fig 2 cannot say anything. What if other methods preferred membrane-active peptides with lower docking scores? Also, the difference in membrane composition can be attributed to specificity.
      - Btw, using trRosetta for peptide structure and ZDOCK for protein-peptide docking is out of date.
    - In experimental validation, it’s better to say focusing *E.coli* and *S.aureus* is because they are the top species in training data, instead of ‘clinically significant pathogens’. *A.baumannii, P.aeruginosa*, or else are much more significant.
      - 2000 sequences were generated as exp candidates. Anyway, at least it’s better than 50,000.
      - MIC indeed shows a certain degree of selectivity of these two bacteria, although activity levels are not impressive. And cell cytotoxicity is good.
      - In the MIC assay, peptides should not solute in DMSO since it is harmful to cells, which may affect the antimicrobial results. I didn’t see a blank control with DMSO in the methods description, and I hoped they used water.

- *Painting Peptides with Antimicrobial Potency through Deep Reinforcement Learning (**Adv Sci 2025** | [code](https://github.com/ComputBiophys/AMPainter))*
    - 🎈Our latest work
    - AMPainter is a reinforcement learning-based framework for the evolutionary design of AMPs. It can evolve AMPs from known AMPs, membrane-active signal peptides, and random sequences with an experimental hit rate exceeding 70%.
    - AMPainter relies solely on our antimicrobial score predictor to select sequences, rather than using a series of manually designed filter criteria.
 
- *EBAMP: An efficient de novo broad-spectrum antimicrobial peptide discovery framework (**Cell Rep 2025** | [code](https://github.com/xinxinsus/EBAMP))*
    - The only notable aspect is the large number of tested peptides (256). The success rate (37.5%) is low, even for generative models, yet they still provide a comparison table (Fig. 6M).
    - Meanwhile, generating 50,000 candidate peptides is too much to show the capacity of their model.
    - ❓ There are several highly similar sequences among their 256 peptides. Mode collapse is observed for generator, as there are some repeated seqs like ‘FKKFKKFKKFKKFKKFK’, ‘LKLKLKLKLK’, and ‘LALALALALA’. In addition, bsa132 peptide has been found in the DRAMP.

- *Generative latent diffusion language modeling yields anti-infective synthetic peptides (**Cell Biomaterials 2025** | [code](https://github.com/programmablebio/amp-diffusion))*
    - Experimental validation of the AMP-Diffusion model. Assembly line work.

- *From AI-driven sequence generation to molecular simulation: a comprehensive framework for antimicrobial peptide discovery (**J Chem Inf Model 2025**)*
    - Recently there are lots of GAN model for AMP, lol.
    - But this paper focus on a pipeline instead of its ‘naive’ GAN model. The authors designed three MD procedures to screen out AMP candidates, including peptide in water, membrane, and a larger membrane system. Why putting peptides in both sides of the membrane?
    - It’s good to provide both the positive (known AMP) and negative (non-AMP) controls for MD pipeline. According to my (limited) experience, it’s quite easy to pass MD2 (distance) while quite difficult to pass MD3 (water permeation). I have to say that running 2 us all-atom simulation is not suitable for screening.
    
- *Evaluation of LLM-generated peptide as foundation template for discovery of effective encrypted AMPs against clinical superbugs (**Microbiol Spectr 2025**)*
    - A successive work of AMPGenix (which is still on Research Square)
    - Using alignment to extract homologs with similar functions is a traditional approach. But here using generative template to extract ‘encrypted AMPs’ rather than screening out them raised an attractive concept, even though the generative model played no actual role.
    - Abundant experiments are mainly for only one peptide, PL-15.

- *Deep learning reveals antibiotics in the archaeal proteome (**Nat Microbiol 2025** | [code](https://gitlab.com/machine-biology-group-public/apex-pathogen))*
    - APEX 1.1

- *A Multi-Property Optimizing Generative Adversarial Network for de novo Antimicrobial Peptide Design (**Adv Sci 2025** | [code](https://github.com/23AIBox/MPOGAN))*
    - Add a figure for experments. I think it’s good to test positive and negative controls in MIC tests.
    - ❓ The numbers of sequences of each generative model are not consistent when comparing in Fig. 2. 
    - ❓ I think their experimental results can only partially reflect the generative capability of MPOGAN. They sampled up to 50,000 candidate seqs and used complex filtering rules, including several antimicrobial predictors, a toxicity predictor, as well as a large number of physicochemical rules and a well-defined length-based score. If we randomly sample 50,000 sequences using these rules, we can also get some good AMPs. 

- *Computational exploration of global venoms for antimicrobial discovery with Venomics artificial intelligence (**Nat Commun 2025**)*

- *Uncovering encrypted antimicrobial peptides in health-associated Lactobacillaceae by large-scale genomics and machine learning (**Microbiome 2025**)*
- *BroadAMP-GPT: AI-Driven generation of broad-spectrum antimicrobial peptides for combating multidrug-resistant ESKAPE pathogens (**Gut Microbes 2025** | [code](https://github.com/LYRHeidi/BroadAMP-GPT))*
    - Figure style looks like NBT 2022
    - ❓”*S. aureus ATCC 29,213, E. coli ATCC 25,922*” Is the comma introduced in proof reading procedure? They appeared many times throughout the article…
    - ❓Randomly select 15 peptides for experimental validation. The authors reported a success rate of 57%, but how was it calculated?
    - ❓Surprisingly, MIC prediction models are all classifiers for ‘low-MIC’ or ‘high-MIC’ groups. Why did authors choose different thresholds (16 μg/mL for *E.coli* and 32 μg/mL for *S.aureus*)? To balance positive and negative samples?
    - Two peptides were tested with several antibiotic-susceptible and antibiotic-resistant strains.
    - The x-axis label of Fig.5 d-e should not be ‘times’. The units of both x and y axis are missing.

- *Unveiling the evolution of antimicrobial peptides in gut microbes via foundation model-powered framework (**Cell Rep 2025** | [code](https://github.com/zjlab-BioGene/AMP-SEMiner))*
    - Develop a residue-level AMP predictor (fine-tuning ESM2) to directly mine encrypted AMPs from proteomes, instead of simply focusing on smORFs or proteolytic fragments. The computational validation is systematic.
    - In vitro successful rate of 9/20 is not that good. Btw the selection criteria are not very clear (similar to many other works), e.g., rule 1 (2+ Cys) covers rule 2 (3+ Cys).
    - Structural clustering confuses me since the short length limits the structural diversity of peptides. Peptides also exhibit flexible conformations under different environments. Can FoldSeek handle such short peptides well?
    - It’s interesting to analyze the adaptive evolution of AMPs interacting with the environment, and there are a lot of things that warrant further exploration.

- *Harnessing advanced computational approaches to design novel antimicrobial peptides against intracellular bacterial infections (**Bioactive Materials 2025**)*
    - A repurposing work for cell-penetrating peptides as AMPs. Only one effective peptide is reported, whose MIC values are not attracting.
    - A relatively complete MD study on pure POPC or POPG/POPE membranes.
    
- *CPL-Diff: A Diffusion Model for De Novo Design of Functional Peptide Sequences with Fixed Length (**Adv Sci 2025** | [code](https://github.com/luozhenjie1997/CPL-Diff))*
    - I’m really surprised fixed length control can be the main motivation of a sequence generation model in 2025 now…
    - The other motivation, to generate peptide with specific function, haven’t been validated in this paper. It is quite likely to generate AMPs with antibacterial, antiviral, and antifungal functions at the same time with only trained on AMP dataset. And this paper didn’t include any wet-lab validation of selectivity.
    - ⁉️ The authors might be influenced by MMCD to use docking validation. Again, LPS is not a protein… 1,3-beta-glucan is not the name of protein as well… What’s the meaning of docking a predicted peptide structure and a manually picked target?
    - Use pLDDT as an evaluation metric for AMP generation?
    - Some analysis figures are redundant.

- *Rapid Response Antimicrobial Peptide Design Strategy Driven by Meta-Learning for Emerging Drug-Resistant Pathogens (**J Med Chem 2025** | [code](https://github.com/lennonyu11234/Archeologist_RR-ADS))*
    - Font makes figures really difficult to read… The score legends of scatters and heatmaps are missing.
    - Meta learning and reinforcement learning (REINVENT), targeting MDRAB.

- *AI-Guided Design of Antimicrobial Peptide Hydrogels for Precise Treatment of Drug-resistant Bacterial Infections (**Adv Mater 2025**)*
    - An application of AMP-Designer (AMP-Hydrogel-Designer).
    - Cys is supported. But only one peptide is reported. 

- *De novo design of self-assembling peptides with antimicrobial activity guided by deep learning (**Nat Mater 2025** | [code](https://github.com/LiuHuayang27/TransSAFP))*
    - Introduces 11 N-terminal modification blocks for peptides.
    - Could not be claimed as ‘de novo design’ - it’s a screening process guided by a classifier, not generation.
    - ⁉️ No independent test set for the evaluation of fine-tuned model. Successful rate was only calculated on antimicrobial activity, even most sequences were known AMPs adding N-termial modifications.
    - I think the relationship between ‘self-assembling’ and ‘antimicrobial’ can be discussed more. In this article, these two features of most screened peptides have been validated separately. At least, this shows the effectiveness of their transfer learning strategy (pretrain on AMP and finetune on self-assembling peptide). As for p45, self-assembling events occur before binding to membranes. Then what’s its mechanism? Barrel-stave or toroidal-pore? Since we often think the oligomerization could be influenced by membrane environments, is there any difference for the peptides which can self-assemble in solution?

- *Machine learning-driven discovery of highly selective antifungal peptides containing non-canonical β-amino acids (**Chem Sci 2025** | [code](https://github.com/jdrichardson97/Peptide-GPR))*
    - Interactive computational and experimtental iteration with GPR model.
    - Building ML models for chemical modifications is the future trend.
      
- *Discovery of antimicrobial peptides with notable antibacterial potency by an LLM-based foundation model (**Sci Adv 2025** | [code](https://github.com/jkwang93/AMP-Designer))*
    - Looks like a twin of MCMG.
    - The application case of *P. acnes* is interesting and useful.
    - I prefer this article's originial title which highlighted the 'foundation model'. Their MIC results do not display 'notable antibacterial potency'. 

- *Deep Learning Combined with Quantitative Structure‒Activity Relationship Accelerates De Novo Design of Antifungal Peptides (**Adv Sci 2025** | [code](https://github.com/DongYin521/AFP_DL-QSARES))*

- *Artificial intelligence using a latent diffusion model enables the generation of diverse and potent antimicrobial peptides (**Sci Adv 2025** | [code](https://github.com/Wangyj2023/PepDiffusion))*
    - Generally, the article is well-written
    - Transformer VAE with latent diffusion, to generate antibacterial or antifungal peptides.
    - No description of clustering (only a sentence *“clustering based on their interactions with membranes”*. I didn’t find any other details in the methods section).
        - Something was missed in MD procedure: the initial conformation of peptide and membrane and the definition of peptide-membrane distance (why negative value means peptides away from membrane?)
        - The standard of selecting top 40 candidate peptides is ambiguous
    - *“The simulation results demonstrated that both peptides bind the lipid membrane in parallel, which is consistent with the toroidal pore model”* — how can authors draw this conclusion from a simulation system with only one peptide? Parallel binding is the first step of different membrane-lysis mechanisms, not only the barrel-stave but the toroidal pore models.

- *Explainable deep learning and virtual evolution identifies antimicrobial peptides with activity against multidrug-resistant human pathogens (**Nat Microbiol 2025** | [code](https://github.com/MicroResearchLab/AMP-potency-prediction-EvoGradient))*
    - The ensemble model is simple (and perhaps referred to NBT 2022), but the details are appreciated:
        - Adding a loss focusing on precision
        - Randomly removing the starting ‘M’ of negative sequences from Uniprot
        - Transferred the layer of classifier to the regressor
    - For the gradient-based explanation and evolution, two AMPs with known analogs were used for validation (but it looks like this part was from a reviewer). And the motif recognition part is useful.
    - Six peptides were tested with N/C-amidation. But only one peptide went through animal tests and mechanism tests.
    - Maybe the unfortunate part is ‘virtual evolution’. It’s not very clear how to choose initial sequences and their evolved results. The sequences and mutations in this process can also be discussed.
      
- *Screening and identification of antimicrobial peptides from the gut microbiome of cockroach Blattella germanica (**Microbiome 2025** | [code](https://github.com/ChenSizhe13893461199/Fast-AMPs-Discovery-Projects))*
    - It’s interesting to find modifications between the biorxiv version and the published version. For example, AF2 structure of AMP1 in biorxiv is an alpha-helix and AF3 structure is a beta-sheet.
    - I think the cell-free synthesis screening is meaningless - it’s easy to test 5 chemically synthesized peptides. I guess this part is added following the *Nat Commun* paper.
    
- *ProT-Diff: A Modularized and Efficient Strategy for De Novo Generation of Antimicrobial Peptide Sequences by Integrating Protein Language and Diffusion Models (**Adv Sci 2024**)*
    - Diffusion in ProtT5 embedding space. Success rate is high for a generative model (44/45).
- *Bioprospecting of culturable marine biofilm bacteria for novel antimicrobial peptides (**iMeta 2024** | [code](https://github.com/FAFFASS/AMP_prediction))*
- *A Foundation Model Identifies Broad-Spectrum Antimicrobial Peptides against Drug-Resistant Bacterial Infection (**Nat Commun 2024** | [code](https://github.com/jimmyrate/deepAMP))*
    - Using ‘degenerative pairs’ to fine-tune a VAE to modify AMP of interest is creative.
    - An important limitation is that the users have to fine-tune a model case-by-case for each peptide of interest.
- *Deep mutational scanning and machine learning for the analysis of antimicrobial-peptide features driving membrane selectivity (**Nat Biomed Eng 2024**)*
    - It’s really important to focus on the membrane selectivity of AMPs. In this work, they proposed a method (dmSLAY) to measure this feature of protegrin-1 variants and find some new variants with good specificity.
    - But I’m curious why this article can be published on NBE. For example, figure 2 is hard to analyze and draw a conclusion between secondary structure and MIC.
- *Computational Design of Pore-Forming Peptides with Potent Antimicrobial and Anticancer Activities (**J Med Chem 2024**)*
  - Design pore-forming AMPs based on coarse-grained MD simulations. 
- *Discovery of antimicrobial peptides in the global microbiome with machine learning (**Cell 2024**)*
    - I’m not familiar with genome analysis but no doubt this part is the highlight of this article.
- *Mining human microbiomes reveals an untapped source of peptide antibiotics (**Cell 2024**)*
    - People always like large-scale works and the potential mining space of AMPs remains scarce after these two cell papers.
    - We found some missing figure legends in Figures S4 and S5.
- *Deep-learning-enabled antibiotic discovery through molecular de-extinction (**Nat Biomed Eng 2024** | [code](https://gitlab.com/machine-biology-group-public/apex))*
    - I have been thinking for quite a while about how to build a multi-task MIC predictor on different bacterial species with scarce data. It’s an advantage for the de la Fuente group to do this work (APEX) on their in-house data though its accuracy is limited.
    - Molecular de-extinction is also a great concept.
- *Exploring the repository of de novo designed bifunctional antimicrobial peptides through deep learning (**eLife 2024** | [code](https://github.com/ruihan-dong/GAN-for-AMP-Design))*
    - 🎈This work is part of my undergraduate thesis.
    - 24 generated peptides have been tested. All these peptides are antibacterial (inhibiting multi-resistant A.baumannii) and about 60% showed antiviral activity on HSV-1 virus. Several peptides got MICs of less than 1 uM against MDRAB.
    - However, the pipeline of selecting bifunctional peptides is not clear. The MD simulation parts are very preliminary.
- *Cell-free biosynthesis combined with deep learning accelerates de novo-development of antimicrobial peptides (**Nat Commun 2023** | [code](https://github.com/amirpandi/Deep_AMP))*
    - The cell-free system is attractive.
    - They used 3 versions of VAE generator and different sequence selection rules. AF2 structures in Fig. 2 are a little messy and maybe plddt should be shown here. Fig. 4 looks good and ESKAPE pathogens were used for MIC tests.
- *Discovering highly potent antimicrobial peptides with deep generative model HydrAMP (**Nat Commun 2023** | [code](https://github.com/szczurek-lab/hydramp))*
    - In my view, the most important contribution of HydrAMP is that they used a VAE to do both ‘analog generation’ and ‘unconstrained generation’ and showed experimentally validated analogs. Unfortunately, no validation results of unconstrained generated sequences were shown.
    - HydrAMP set two levels of conditions (AMP and MIC classifier). But the intra-connection of the two conditions was not considered and some cases with MIC label 1 and AMP label 0 can be found.
- *Designing antimicrobial peptides using deep learning and molecular dynamic simulations (**Brief Bioinformatics 2023** | [code](https://github.com/gc-js/Antimicrobial-peptide-generation))*
    - Using SeqGAN to design AMPs is a good trial.
- *Identification of potent antimicrobial peptides via a machine-learning pipeline that mines the entire space of peptide sequences (**Nat Biomed Eng 2023**)*
    - The authors established a pipeline of selection, classification, ranking, and regression. It’s impressive that they experimentally compared different combinations of these steps.
    - I sometimes worry that the more steps a pipeline uses, the more bias each step introduces.
- *Molecular de-extinction of ancient antimicrobial peptides enabled by machine learning (**Cell Host & Microbe 2023** | [code](https://gitlab.com/machine-biology-group-public/pancleave))*
    - The authors used a protease prediction model to ‘cut’ fragments from ancient proteomes, which is better than random sliding windows.
    - The selection rules of AMP candidates are interesting, including human experts, conventional AMP classifiers, and even random choice.
- *Identification of antimicrobial peptides from the human gut microbiome using deep learning (**Nat Biotechnol 2022** | [code](https://github.com/mayuefine/c_AMPs-prediction))*
    - An important work in the field of AMP mining/designing. You can see the impact of this paper in other papers such as the model framework, the figure style, etc.
- *Mining for encrypted peptide antibiotics in the human proteome (**Nat Biomed Eng 2022**)*



## Review

- *AI-driven discovery and design of antimicrobial peptides (**Sci. China Technol. Sci. 2025**)*
- *Research Advance in the Development of Antimicrobial Peptides Using Deep Learning (**J Compt Chem 2025**)*
- *Antimicrobial peptides: structure, functions and translational applications (**Nat Rev Microbiol 2025**)*
- *Deep Learning in Antimicrobial Peptide Prediction (**J Chem Inf Model 2025**)*
- *AI-Driven Antimicrobial Peptide Discovery: Mining and Generation (**Acc. Chem. Res. 2025**)*
  - A review written by famous experts in current AMP area.
- *Machine Learning-Assisted Prediction and Generation of Antimicrobial Peptides (**Small Sci 2025**)*
- *From Membrane Composition to Antimicrobial Strategies: Experimental and Computational Approaches to AMP Design and Selectivity （**Small 2025**)*
- *Tutorial: guidelines for the use of machine learning methods to mine genomes and proteomes for antibiotic discovery (**Nat Protocols 2025**)*
- *Deep Learning for Antimicrobial Peptides: Computational Models and Databases (**J Chem Inf Model 2025**)*
- *Leveraging large language models for peptide antibiotic design (**Cell Rep Phys Sci 2025**)*
- *Challenges and applications of artificial intelligence in infectious diseases and antimicrobial resistance (**npj Antimicrob Resist 2025**)*
- *AI Methods for Antimicrobial Peptides: Progress and Challenges (**Microbial Biotechnology 2025**)*
- *Machine learning for antimicrobial peptide identification and design (**Nat Rev Bio Eng 2024**)*
- *Integrated computational approaches for advancing antimicrobial peptide development (**Trends Pharmacol Sci 2024**)*
- *Artificial intelligence-driven antimicrobial peptide discovery (**Current Opinion in Structural Biology 2023**)*
- *Progress and future of the computational design of antimicrobial peptides (AMPs): bio-inspired functional molecules (**Digital Discovery 2023**)*
- *Latent spaces for antimicrobial peptide design (**Digital Discovery 2023**)*
- *Deep generative models for peptide design (**Digital Discovery 2022**)*
- *Synthetic molecular evolution of antimicrobial peptides (**Current Opinion in Biotechnology 2022**)*
- *Comprehensive assessment of machine learning-based methods for predicting antimicrobial peptides (**Brief Bioinformatics 2021**)*
- *Computational Methods and Tools in Antimicrobial Peptide Research (**J Chem Inf Model 2021**)*



## Generators

- *A novel generative framework for designing pathogen-targeted antimicrobial peptides with programmable physicochemical properties (**PLoS Comput Biol 2025** | [code](https://github.com/David-WZhao/AMPGen))*
  - First, *E. coli* does not belong to ESKAPE…
  - I have to say it’s my first time seeing docking with the membrane. Since the author already knows how to build a membrane using CHARMM-GUI, why not run a simple MD simulation?
  - Btw, I’m also surprised my elife paper is cited for membrane composition... At least AMPredictor is worth being compared as an *E. coli* MIC predictor.
  - What’s the ‘AMP-MIC’ in table 2?
  - Pathogen-targeted AMP is a good point. I think it would be better to show selective activity towards the targeted bacteria (for example, the top 10 AMPs targeting *E. coli* have larger MIC against *S. aureus*). Anyway, I understand that a computational group might not have experimental conditions, but usually, just having predicted results isn't enough to convince readers.
  - Github page not exist?

- *Reinforcement learning with low-rank adaptation for targeted antimicrobial peptide design (**Brief Bioinformatics 2025** | [code](https://github.com/GIST-CSBL/AMP-RL))*

- *MOFormer: navigating the antimicrobial peptide design space with Pareto-based multi-objective transformer (**Brief Bioinformatics 2025** | [code](https://github.com/wl-wl/MOFormer/tree/master))*
  
- *Classifier-driven generative adversarial networks for enhanced antimicrobial peptide design (**Brief Bioinformatics 2025** | [code](https://github.com/aretiz/amp_de_novo_design_cdGAN))*
  - A simple modification of Feedback GAN by training the extra classifier at the same time (dual-discriminator GAN?).
  - FBGAN utilized DNA sequences to design AMPs, and this work did so. I think this step is somewhat redundant because we used chemical synthesis to produce AMPs rather than biological expression. Using cDNA increases the length and complexity.

- *AMPGP: Discovering Highly Effective Antimicrobial Peptides via Deep Learning (**J Chem Inf Model 2025** | [code](http://github.com/Wu0805/AMPgeneration-prediction))*

- *A Unified Peptide Generative Framework via a Weakly Order-Dependent Autoregressive Language Model and Lifelong Learning (**J Chem Inf Model 2025** | [code](https://github.com/ZhiweiNiepku/PepGenWL))*

- *From AI to action: Antimicrobial peptides engineered by generative adversarial networks (GANs)-A novel approach to combat resistant Bacteria (**Chem Eng J 2025** | [code](https://github.com/lsbnb/amp_gan))*
  
- *AMPGen: an evolutionary informationreserved and diffusion-driven generative model for de novo design of antimicrobial peptides (**Commun Biol 2025** | [code](https://github.com/xiyanxiongnico/AMPGen))*
  - The motivation is ‘hard to design such short peptides with flexible structures’. I think the introduction part lacks an overview of current AMP generation methods. Maybe AMPGen is just an application of EvoDiff.
  - Looks like the figure style is influenced by Nat Commun article (cell-free).
  - Results showed that MSA-conditional model performs the best.

- *HMAMP: Hypervolume-Driven Multi-Objective Antimicrobial Peptides Design (**J Med Chem 2025** | [code](https://github.com/wl-wl/HMAMP-main))*

- *SQ-DiffuPep: A multimodal information-guided quantitative latent diffusion model for antimicrobial peptide discovery (**Inform Fusion 2025** | [code](https://github.com/Zoigin/SQ-DiffuPep))*

- *A Conditional Denoising VAE-based Framework for Antimicrobial Peptides Generation with Preserving Desirable Properties (**Bioinformatics 2025** | [code](https://github.com/David-WZhao/PPGC-DVAE))*
  - Why put all the necessary results in SI?
  - Add a property preserving loss (MSE) when training VAE.

- *Directed Evolutionary of Peptides using Multi-Objective Zeroth-Order Optimization (**Brief Bioinformatics 2025** | [code](https://github.com/chen-bioinfo/PepZOO))*
  - PepZOO, ZOO for zeroth-order optimization (use VAE latent space)
  - Two tasks, AMP (being AMP and MIC activity) and AVP (target binding affinity and toxicity)
    - Two objects for AMP task should be designed more carefully. Why not toxicity or diversity? $$P_{AMP}$$ and $$P_{MIC}$$ are highly related and we only care about highly active ones.
  - A work following HydrAMP.

- *Improving functional protein generation via foundation model-derived latent space likelihood optimization (**AAAI 2025**)*
    - Similar to knowledge distillation with hard and soft label losses.
    - As a conference paper, not many validations are included.
      
- *TG-CDDPM: text-guided antimicrobial peptides generation based on conditional denoising diffusion probabilistic model (**Brief Bioinformatics 2025** | [code](https://github.com/JunhangCao/TG-CDDPM))*
- *Diff-AMP: tailored designed antimicrobial peptide framework with all-in-one generation, identification, prediction and optimization (**Brief Bioinformatics 2024** | [code](https://github.com/wrab12/diff-amp))*
- *A Multi-Modal Contrastive Diffusion Model for Therapeutic Peptide Generation (**AAAI 2024**)*
    - Rosetta was used for building peptide structures…
    - ⁉️ The authors thought LPS belongs to protein and even did docking for validation. It looks like they knew little about AMP mechanisms even though they mentioned the major target of AMP is bacterial membrane… Their method can only generate peptide backbone coordinates but they used rigid docking mode with side chains from another tool…
- *AMP-Diffusion: Integrating Latent Diffusion with Protein Language Models for Antimicrobial Peptide Generation (**NeurIPS 2023 GenAIBio workshop**)*
- *Multi-CGAN: Deep Generative Model-Based Multiproperty Antimicrobial Peptide Design (**J Chem Inf Model 2023** | [code](https://github.com/hqyu/Multi-CGAN))*
- *Evolutionary Multi-Objective Optimization in Searching for Various Antimicrobial Peptides (**IEEE Comput Intell Mag 2023**)*
- *Accelerating Antimicrobial Peptide Discovery with Latent Sequence-Structure Model (**AAAI 2023**)*
    - VQ-VAE
- *Application of a deep generative model produces novel and diverse functional peptides against microbial resistance (**Comput Struct Biotechnol J 2022** | [code](https://github.com/AspirinCode/AMPTrans-lstm))*
- *Accelerated antimicrobial discovery via deep generative models and molecular dynamics simulations (**Nat Biomed Eng 2021**)*
- *AMPGAN v2: Machine Learning-Guided Design of Antimicrobial Peptides (**J Chem Inf Model 2021**)*
- *PepVAE: Variational Autoencoder Framework for Antimicrobial Peptide Generation and Activity Prediction (**Front Microbiol 2021**)*



## Predictors

❗**NOTE**: I didn’t list all the relevant works here since there are so many AMP predictors. And I’m not working on AMP classifiers.

- *PlantAMP: A fine-tuned protein large language model for plant antimicrobial peptide prediction (**Plant Commun 2025** |[code](https://github.com/Chengzhi-Xie/PlantAMP))*

- *Long short-term memory-based deep learning model for the discovery of antimicrobial peptides targeting Mycobacterium tuberculosis (**Bioinform Adv 2025** | [code](https://github.com/linfeng-wang/TB-AMP-design))*

- *Pepxml: ESM2-based extreme multilabel classification of pathogen-targeted antimicrobial peptides (**Brief Bioinform 2025** | [code](https://github.com/YannanBin/PepXML))*
  - PepXML may not be a good name, as it is a file format in proteomics...

- *AI-Guided Discovery and Optimization of Antimicrobial Peptides Through Species-Aware Language Model (**Brief Bioinform 2025** | [code](https://github.com/GIST-CSBL/LLAMP))*
    - A species-aware MIC predictor from the AMP-BERT team, by adding genomes from different species
    - It's interesting that the authors didn't put experimental results in bioRxiv manuscript

- *AmpHGT: expanding prediction of antimicrobial activity in peptides containing non‑canonical amino acids using multi‑view constrained heterogeneous graph transformer (**BMC biology 2025** | [code](https://github.com/AledHe/AmpHGT))*
    - Sequence-level embedding is still extracted from ESM-2, with <mask> for NCAAs
    - ❓On plain AMP classification datasets, the proposed model cannot outperform any other methods
    - Using the ‘overlap’ NCAA dataset is meaningful

- *Multimodal geometric learning for antimicrobial peptide identification by leveraging alphafold2-predicted structures and surface features (**Brief Bioinform 2025** | [code](https://github.com/ggcameronnogg/SSFGM-Model))*
    - Add surface information from MaSIF

- *AMPCliff: Quantitative definition and benchmarking of activity cliffs in antimicrobial peptides (**J Adv Res 2025** | [code](https://github.com/Kewei2023/AMPCliff))*
  - Meaningful discussions.

- *BERT-AmPEP60: A BERT-Based Transfer Learning Approach to Predict the Minimum Inhibitory Concentrations of Antimicrobial Peptides for Escherichia coli and Staphylococcus aureus （**J Chem Inf Model 2025** | [code](https://github.com/janecai0714/AMP_regression_EC_SA))*
  - Regression on MIC against Ec and Sa
  - Has Ala/Lys scanning tests

- *Leveraging protein language models for robust antimicrobial peptide detection (**Methods 2025** | [code](https://github.com/lichaozhang2/PLAPD))*

- *Prediction of inhibitory peptides against E.coli with desired MIC value (**Sci Rep 2025**)*

- *MSCMamba: Prediction of Antimicrobial Peptide Activity Values by Fusing Multiscale Convolution with Mamba Module (**J Phys Chem B 2025**)*
    - As a regression model, they didn’t mention other regression works
    - Retrain other classifiers as regression models when benchmarking
    - Self-processed data from GRAMPA, but they didn't mention either the length distribution,  modifications, or logMIC label
    - Unfortunately, no available code or server

- *deep-AMPpred: A Deep Learning Method for Identifying Antimicrobial Peptides and Their Functional Activities (**J Chem Inf Model 2025** | [code](https://github.com/JunZhao-hash/deep-AMPpred))*
  
- *sAMP-VGG16: Force-field assisted image-based deep neural network prediction model for short antimicrobial peptides (**Proteins 2025**)*
    - I remember I saw this preprint two or three years ago. It’s interesting to use force field parameters as feature encodings.
- *An ensemble deep learning model for predicting minimum inhibitory concentrations of antimicrobial peptides against pathogenic bacteria (**iScience 2024** | [code](https://github.com/chungcr/esAMPMIC))*
- *iMFP-LG: Identification of Novel Multi-Functional Peptides by Using Protein Language Models and Graph-Based Deep Learning (**Genomics, proteomics & bioinformatics 2024** | [code](https://github.com/chen-bioinfo/iMFP-LG))*
  - Multifunctional prediction with graph node classification
  - Also have a screening and validation part
- *Screening antimicrobial peptides and probiotics using multiple deep learning and directed evolution strategies (**Acta Pharm Sin B 2024**)*
- *Predicting Antimicrobial Peptides Using ESMFold-Predicted Structures and ESM-2-Based Amino Acid Features with Graph Deep Learning (**J Chem Inf Model 2024** | [code](https://github.com/cicese-biocom/esm-AxP-GDL))*
- *PGAT-ABPp: harnessing protein language models and graph attention networks for antibacterial peptide identification with remarkable accuracy (**Bioinformatics 2024** | [code](https://github.com/moonseter/PGAT-ABPp))*
- *TP-LMMSG: a peptide prediction graph neural network incorporating flexible amino acid property representation (**Brief Bioinformatics 2024** | [code](https://github.com/NanjunChen37/TP_LMMSG))*
- *iAMP-Attenpred: a novel antimicrobial peptide predictor based on BERT feature extraction method and CNN-BiLSTM-Attention combination model (**Brief Bioinformatics 2024** | [code](https://github.com/xingwxzz/iAMP-Attenpred))*
- *DMAMP: A deep-learning model for detecting antimicrobial peptides and their multi-activities (**IEEE TCBB 2024** | [code](https://github.com/guofei-tju/DMAMP))*
- *Fuse feeds as one: cross-modal framework for general identification of AMPs (**Brief Bioinformatics 2024** | [code](https://github.com/William-Zhanng/SenseXAMP))*
    - Meaningful discussions and benchmarking on AMP datasets.
- *AMPpred-MFA: An Interpretable Antimicrobial Peptide Predictor with a Stacking Architecture, Multiple Features, and Multihead Attention (**J Chem Inf Model 2023**)*
    - It’s really interesting when I use their server to test some sequences, all predicted probabilities exceeded 0.99.
- *iAMPCN: a deep-learning approach for identifying antimicrobial peptides and their functional activities (**Brief Bioinformatics 2023** | [code](https://github.com/joy50706/iAMPCN))*
- *Artificial intelligence-based model for predicting the minimum inhibitory concentration of antibacterial peptides against ESKAPEE pathogens (**IEEE JBHI 2023**)*
- *A deep learning method for predicting the minimum inhibitory concentration of antimicrobial peptides against Escherichia coli using Multi-Branch-CNN and Attention (**mSystems 2023** | [code](https://github.com/jieluyan/MBC-Attention))*
    - One of a few works on MIC value regression.
- *Integrating transformer and imbalanced multi-label learning to identify antimicrobial peptides and their functional activities (**Bioinformatics 2022** | [code](https://github.com/BiOmicsLab/TransImbAMP))*
    - Multi-label classification.
- *AMP-BERT: Prediction of antimicrobial peptide function based on a BERT model (**Prot Sci 2022** | [code](https://github.com/GIST-CSBL/AMP-BERT))*
    - Direct fine-tuning on ProtBert. Nice visualizations.
- *sAMPpred-GAT: prediction of antimicrobial peptide by graph attention network and predicted peptide structure (**Bioinformatics 2022** | [code](https://github.com/HongWuL/sAMPpred-GAT))*
    - The first AMP predictor with predicted peptide structures (contact map from trRosetta as graph edges)
    - We usually think structural information are not useful since short peptides have simple 3D structures (helix/sheet/loop, maybe secondary structure info is enough), and current structure predictors cannot distinguish the solution/membrane environment. Also, AMPs may oligomerize to function.
