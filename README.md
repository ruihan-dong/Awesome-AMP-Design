# Awesome-AMP-Design
Designing antimicrobial peptides (AMPs) is awesome. A list of relevant works (with comments).

🧨 Last Update 25-01-27

❗**NOTE**: All comments below are personal opinions. Issues and discussions are welcome via github or emailing me at dongruihan_at_stu.pku.edu.cn

### Contents

- [Preprints](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#preprints)
- [Comprehensive works](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#comprehensive-works-with-comments)
- [Review](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#review)
- [Generators](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#generators)
- [Predictors](https://github.com/ruihan-dong/Awesome-AMP-Design?tab=readme-ov-file#predictors)

### Preprints

- *Painting Peptides with Antimicrobial Potency through Deep Reinforcement Learning (bioRxiv 2025)*
    - 🎈Our latest work
    - AMPainter is a reinforcement learning-based framework for the evolutionary design of AMPs. It can evolve AMPs from known AMPs, membrane-active signal peptides, and random sequences with an experimental hit rate exceeding 70%.
    - AMPainter relies solely on our antimicrobial score predictor to select sequences, rather than using a series of manually designed filter criteria.
    
- *Unveiling the evolution of antimicrobial peptides in gut microbes via foundation model-powered framework (bioRixv 2025 | [code](https://github.com/zjlab-BioGene/AMP-SEMiner))*
    - The model is the fine-tuned ESM-2. Structure clustering and conservation analysis are included.
- *Discovery of antibiotics in the archaeome using deep learning (bioRxiv 2025 | [code](https://gitlab.com/machine-biology-group-public/apex-pathogen))*
- *Venomics AI: a computational exploration of global venoms for antibiotic discovery (bioRxiv 2025)*
- *Design of multimodal antibiotics against intracellular infections using deep learning (bioRxiv 2024 | [code](https://gitlab.com/machine-biology-group-public/apex_duo))*
    - Multimodal represents cell-penetration and AMP - Did they consider that many known AMPs are already cell-penetration peptides?
    - The training set of cell-penetration predictor is weird - added toxic peptides into the negative set
    - I like Fig. 4A because it’s direct to see residues that contributed to antimicrobial activity as well as toxicity. Btw, the x-axis label should be F1A instead of A1F (same for other sites)
- *A generative artificial intelligence approach for antibiotic optimization (bioRxiv 2024 | [code](https://github.com/Yimeng-Zeng/APEXGo))*
- *De novo multi-mechanism antimicrobial peptide design via multimodal deep learning (bioRxiv 2024)*
    - A really complex model with structures and limited strain/mechanism labels.
- *A Multi-Property Optimizing Generative Adversarial Network for de novo Antimicrobial*
*Peptide Design (bioRxiv 2024 | [code](https://github.com/23AIBox/MPOGAN))*
    - Not many experiments. I think it’s good to test positive and negative controls in MIC tests.
- *Discovery of antimicrobial peptides targeting Acinetobacter baumannii via a pre-trained and finetuned few-shot learning-based pipeline (Research Square 2024)*
    - The subsequent work of Nat Biomed Eng 2023, focusing on *A.baumannii*.
- *A foundation model approach to guide antimicrobial peptide design in the era of artificial intelligence driven scientific discovery (arXiv 2024 | [code](https://github.com/jkwang93/AMP-Designer))*
    - Looks like a twin of MCMG.
    - The application case of *P. acnes* is interesting and useful.
- *HMAMP: Hypervolume-Driven Multi-Objective Antimicrobial Peptides Design (arXiv 2024)*
- *MoFormer: Multi-objective Antimicrobial Peptide Generation Based on Conditional Transformer Joint Multi-modal Fusion Descriptor (arXiv 2024)*
- *Key-cutting machine: A novel optimization framework for tailored protein*
*and peptide design (bioRxiv 2025)*

---

### Comprehensive works (with comments)

*in silico* mining/generation + *in vitro/in vivo* validations

- *Explainable deep learning and virtual evolution identifies antimicrobial peptides with activity against multidrug-resistant human pathogens (Nat Microbial 2025 | [code](https://github.com/MicroResearchLab/AMP-potency-prediction-EvoGradient))*
    - The ensemble model is simple (and perhaps referred to NBT 2022), but the details are appreciated:
        - Adding a loss focusing on precision
        - Randomly removing the starting ‘M’ of negative sequences from Uniprot
        - Transferred the layer of classifier to the regressor
    - For the gradient-based explanation and evolution, two AMPs with known analogs were used for validation (but it looks like this part was from a reviewer). And the motif recognition part is useful.
    - Six peptides were tested with N/C-amidation. But only one peptide went through animal tests and mechanism tests.
    - Maybe the unfortunate part is ‘virtual evolution’. It’s not very clear how to choose initial sequences and their evolved results. The sequences and mutations in this process can also be discussed.
      
- *Screening and identification of antimicrobial peptides from the gut microbiome of cockroach Blattella germanica (Microbiome 2025 | [code](https://github.com/ChenSizhe13893461199/Fast-AMPs-Discovery-Projects))*
    - It’s interesting to find modifications between the biorxiv version and the published version. For example, AF2 structure of AMP1 in biorxiv is an alpha-helix and AF3 structure is a beta-sheet.
    - I think the cell-free synthesis screening is meaningless - it’s easy to test 5 chemically synthesized peptides. I guess this part is added following the Nat Commun paper.
    
- *ProT-Diff: A Modularized and Efficient Strategy for De Novo Generation of Antimicrobial Peptide Sequences by Integrating Protein Language and Diffusion Models (Adv Sci 2024)*
    - Diffusion in ProtT5 embedding space. Success rate is high for a generative model (44/45).
- *Bioprospecting of culturable marine biofilm bacteria for novel antimicrobial peptides (iMeta 2024 | [code](https://github.com/FAFFASS/AMP_prediction))*
- *A Foundation Model Identifies Broad-Spectrum Antimicrobial Peptides against Drug-Resistant Bacterial Infection (Nat Commun 2024 | [code](https://github.com/jimmyrate/deepAMP))*
    - Using ‘degenerative pairs’ to fine-tune a VAE to modify AMP of interest is creative.
    - An important limitation is that the users have to fine-tune a model case-by-case for each peptide of interest.
- *Deep mutational scanning and machine learning for the analysis of antimicrobial-peptide features driving membrane selectivity (Nat Biomed Eng 2024)*
    - It’s really important to focus on the membrane selectivity of AMPs. In this work, they proposed a method (dmSLAY) to measure this feature of protegrin-1 variants and find some new variants with good specificity.
    - But I’m curious why this article can be published on NBE. For example, figure 2 is hard to analyze and draw a conclusion between secondary structure and MIC.
- *Discovery of antimicrobial peptides in the global microbiome with machine learning (Cell 2024)*
    - I’m not familiar with genome analysis but no doubt this part is the highlight of this article.
- *Mining human microbiomes reveals an untapped source of peptide antibiotics (Cell 2024)*
    - People always like large-scale works and the potential mining space of AMPs remains scarce after these two cell papers.
    - We found some missing figure legends in Figures S4 and S5.
- *Deep-learning-enabled antibiotic discovery through molecular de-extinction (Nat Biomed Eng 2024 | [code](https://gitlab.com/machine-biology-group-public/apex))*
    - I have been thinking for quite a while about how to build a multi-task MIC predictor on different bacterial species with scarce data. It’s an advantage for the de la Fuente group to do this work (APEX) on their in-house data though its accuracy is limited.
    - Molecular de-extinction is also a great concept.
- *Exploring the repository of de novo designed bifunctional antimicrobial peptides through deep learning (eLife 2024 | [code](https://github.com/ruihan-dong/GAN-for-AMP-Design))*
    - 🎈This work is part of my undergraduate thesis.
    - Revised version (not updated in eLife yet) [bioRxiv](https://www.biorxiv.org/content/10.1101/2024.02.23.581845v2): 24 generated peptides have been tested. All these peptides are antibacterial (inhibiting multi-resistant A.baumannii) and about 60% showed antiviral activity on HSV-1 virus. Several peptides got MICs of less than 1 uM against MDRAB.
    - However, the pipeline of selecting bifunctional peptides is not clear. The MD simulation parts are very preliminary.
- *Cell-free biosynthesis combined with deep learning accelerates de novo-development of*
*antimicrobial peptides (Nat Commun 2023 | [code](https://github.com/amirpandi/Deep_AMP))*
    - The cell-free system is attractive.
    - They used 3 versions of VAE generator and different sequence selection rules. AF2 structures in Fig. 2 are a little messy and maybe plddt should be shown here. Fig. 4 looks good and ESKAPE pathogens were used for MIC tests.
- *Discovering highly potent antimicrobial peptides with deep generative model HydrAMP (Nat Commun 2023 | [code](https://github.com/szczurek-lab/hydramp))*
    - In my view, the most important contribution of HydrAMP is that they used a VAE to do both ‘analog generation’ and ‘unconstrained generation’ and showed experimentally validated analogs. Unfortunately, no validation results of unconstrained generated sequences were shown.
    - HydrAMP set two levels of conditions (AMP and MIC classifier). But the intra-connection of the two conditions was not considered and some cases with MIC label 1 and AMP label 0 can be found.
- *Designing antimicrobial peptides using deep learning and molecular dynamic simulations (Brief Bioinformatics 2023 | [code](https://github.com/gc-js/Antimicrobial-peptide-generation))*
    - Using SeqGAN to design AMPs is a good trial.
- *Identification of potent antimicrobial peptides via a machine-learning pipeline that mines the entire space of peptide sequences (Nat Biomed Eng 2023)*
    - The authors established a pipeline of selection, classification, ranking, and regression. It’s impressive that they experimentally compared different combinations of these steps.
    - I sometimes worry that the more steps a pipeline uses, the more bias each step introduces.
- *Molecular de-extinction of ancient antimicrobial peptides enabled by machine learning (Cell Host & Microbe 2023 | [code](https://gitlab.com/machine-biology-group-public/pancleave))*
    - The authors used a protease prediction model to ‘cut’ fragments from ancient proteomes, which is better than random sliding windows.
    - The selection rules of AMP candidates are interesting, including human experts, conventional AMP classifiers, and even random choice.
- *Identification of antimicrobial peptides from the human gut microbiome using deep learning (Nat Biotechnol 2022 | [code](https://github.com/mayuefine/c_AMPs-prediction))*
    - An important work in the field of AMP mining/designing. You can see the impact of this paper in other papers such as the model framework, the figure style, etc.
- *Mining for encrypted peptide antibiotics in the human proteome (Nat Biomed Eng 2022)*

---

### Review

- *AI Methods for Antimicrobial Peptides: Progress and Challenges (Microbial Biotechnology 2025)*
- *Machine learning for antimicrobial peptide identification and design (Nat Rev Bio Eng 2024)*
- *Integrated computational approaches for advancing antimicrobial peptide development (Trends Pharmacol Sci 2024)*
- *Artificial intelligence-driven antimicrobial peptide discovery (Current Opinion in Structural Biology 2023)*
- *Progress and future of the computational design of antimicrobial peptides (AMPs): bio-inspired functional molecules (Digital Discovery 2023)*
- *Latent spaces for antimicrobial peptide design (Digital Discovery 2023)*
- *Deep generative models for peptide design (Digital Discovery 2022)*
- *Synthetic molecular evolution of antimicrobial peptides (Current Opinion in Biotechnology 2022)*
- *Comprehensive assessment of machine learning-based methods for predicting antimicrobial peptides (Brief Bioinformatics 2021)*
- *Computational Methods and Tools in Antimicrobial Peptide Research (J Chem Inf Model 2021)*

---

### Generators

- *Improving functional protein generation via foundation model-derived latent space likelihood optimization (AAAI 2025)*
    - Similar to knowledge distillation with hard and soft label losses.
    - As a conference paper, not many validations are included.
      
- *TG-CDDPM: text-guided antimicrobial peptides generation based on conditional denoising diffusion probabilistic model (Brief Bioinformatics 2025 | [code](https://github.com/JunhangCao/TG-CDDPM))*
- *Diff-AMP: tailored designed antimicrobial peptide framework with all-in-one generation, identification, prediction and optimization (Brief Bioinformatics 2024 | [code](https://github.com/wrab12/diff-amp))*
- *A Multi-Modal Contrastive Diffusion Model for Therapeutic Peptide Generation (AAAI 2024)*
    - Rosetta was used for building peptide structures…
    - ⁉️ The authors thought LPS belongs to protein and even did docking for validation. It looks like they knew little about AMP mechanisms even though they mentioned the major target of AMP is bacterial membrane… Their method can only generate peptide backbone coordinates but they used rigid docking mode with side chains from another tool…
- *AMP-Diffusion: Integrating Latent Diffusion with Protein Language Models for Antimicrobial Peptide Generation (NeurIPS 2023 GenAIBio workshop)*
- *Multi-CGAN: Deep Generative Model-Based Multiproperty Antimicrobial Peptide Design (J Chem Inf Model 2023 | [code](https://github.com/hqyu/Multi-CGAN))*
- *Evolutionary Multi-Objective Optimization in Searching for Various Antimicrobial Peptides (IEEE Comput Intell Mag 2023)*
- *Accelerating Antimicrobial Peptide Discovery with Latent Sequence-Structure Model (AAAI 2023)*
    - VQ-VAE
- *Application of a deep generative model produces novel and diverse functional peptides against microbial resistance (Comput Struct Biotechnol J 2022 | [code](https://github.com/AspirinCode/AMPTrans-lstm))*
- *Accelerated antimicrobial discovery via deep generative models and molecular dynamics*
*simulations (Nat Biomed Eng 2021)*
- *AMPGAN v2: Machine Learning-Guided Design of Antimicrobial Peptides (J Chem Inf Model 2021)*
- *PepVAE: Variational Autoencoder Framework for Antimicrobial Peptide Generation and Activity Prediction (Front Microbiol 2021)*

---

### Predictors

❗**NOTE**: I didn’t list all the relevant works here since there are so many AMP predictors. And I’m not working on AMP classifiers. 

- *deep-AMPpred: A Deep Learning Method for Identifying Antimicrobial Peptides and Their Functional Activities (J Chem Inf Model 2025 | [code](https://github.com/JunZhao-hash/deep-AMPpred))*
  
- *sAMP-VGG16: Force-field assisted image-based deep neural network prediction model for short antimicrobial peptides (Proteins 2025)*
    - I remember I saw this preprint two or three years ago. It’s interesting to use force field parameters as feature encodings.
- *An ensemble deep learning model for predicting minimum inhibitory concentrations of antimicrobial peptides against pathogenic bacteria (iScience 2024 | [code](https://github.com/chungcr/esAMPMIC))*
- *Screening antimicrobial peptides and probiotics using multiple deep learning and directed evolution strategies (Acta Pharm Sin B 2024)*
- *Predicting Antimicrobial Peptides Using ESMFold-Predicted Structures and ESM-2-Based Amino Acid Features with Graph Deep Learning (J Chem Inf Model 2024 | [code](https://github.com/cicese-biocom/esm-AxP-GDL))*
- *PGAT-ABPp: harnessing protein language models and graph attention networks for antibacterial peptide identification with remarkable accuracy (Bioinformatics 2024 | [code](https://github.com/moonseter/PGAT-ABPp))*
- *TP-LMMSG: a peptide prediction graph neural network incorporating flexible amino acid property representation (Brief Bioinformatics 2024 | [code](https://github.com/NanjunChen37/TP_LMMSG))*
- *iAMP-Attenpred: a novel antimicrobial peptide predictor based on BERT feature extraction method and CNN-BiLSTM-Attention combination model* (Brief Bioinformatics 2024 | [code](https://github.com/xingwxzz/iAMP-Attenpred))
- *DMAMP: A deep-learning model for detecting antimicrobial peptides and their multi-activities (IEEE TCBB 2024 | [code](https://github.com/guofei-tju/DMAMP))*
- *Fuse feeds as one: cross-modal framework for general identification of AMPs (Brief Bioinformatics 2024 | [code](https://github.com/William-Zhanng/SenseXAMP))*
    - Meaningful discussions and benchmarking on AMP datasets.
- *AMPpred-MFA: An Interpretable Antimicrobial Peptide Predictor with a Stacking Architecture, Multiple Features, and Multihead Attention (J Chem Inf Model 2023)*
    - It’s really interesting when I use their server to test some sequences, all predicted probabilities exceeded 0.99.
- *iAMPCN: a deep-learning approach for identifying antimicrobial peptides and their functional activities (Brief Bioinformatics 2023 | [code](https://github.com/joy50706/iAMPCN))*
- *Artificial intelligence-based model for predicting the minimum inhibitory concentration of antibacterial peptides against ESKAPEE pathogens (IEEE JBHI 2023)*
- *A deep learning method for predicting the minimum inhibitory concentration of antimicrobial peptides against Escherichia coli using Multi-Branch-CNN and Attention (mSystems 2023 | [code](https://github.com/jieluyan/MBC-Attention))*
    - One of a few works on MIC value regression.
- *Integrating transformer and imbalanced multi-label learning to identify antimicrobial peptides and their functional activities (Bioinformatics 2022 | [code](https://github.com/BiOmicsLab/TransImbAMP))*
    - Multi-label classification.
- *AMP-BERT: Prediction of antimicrobial peptide function based on a BERT model (Prot Sci 2022 | [code](https://github.com/GIST-CSBL/AMP-BERT))*
    - Direct fine-tuning on ProtBert. Nice visualizations.
- *sAMPpred-GAT: prediction of antimicrobial peptide by graph attention network and predicted peptide structure (Bioinformatics 2022 | [code](https://github.com/HongWuL/sAMPpred-GAT))*
    - The first AMP predictor with predicted peptide structures (contact map from trRosetta as graph edges)
    - We usually think structural information are not useful since short peptides have simple 3D structures (helix/sheet/loop, maybe secondary structure info is enough), and current structure predictors cannot distinguish the solution/membrane environment. Also, AMPs may oligomerize to function.
