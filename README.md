# LLPS-Score-Predicting-Protein-Phase-Separation-and-Biological-Function-from-Physicochemical-Features
Liquid-liquid phase separation (LLPS) has emerged as an important mechanism by which
cells organize biomolecules into dynamic, membrane-less condensates. These condensates
play a central role in regulating processes such as transcription, RNA metabolism, stress
response, and intracellular signaling. Because LLPS is influenced by subtle sequence-level
and physicochemical properties, identifying phase-separating proteins experimentally is
both time-consuming and difficult to scale across large proteomes. This creates a strong
need for computational methods that can predict LLPS propensity directly from amino
acid sequence information.

In this project, we aim to capture the hidden molecular grammar that governs phase
separation by treating protein sequences as biological text. To support this, we expanded
our data curation pipeline and constructed a balanced dataset of 6,289 protein sequences,
enabling more robust learning and better generalization across different protein classes.
Rather than relying only on manually designed rules, we combine explicit biochemical
features with learned sequence representations so that the model can leverage both known
biophysical signals and latent contextual patterns.

For representation learning, the protein sequences were tokenized into overlapping
3-grams and used to train a Word2Vec model. This allowed us to generate dense embed-
ding matrices that preserve local contextual relationships between amino acids, much like
word embeddings in natural language processing. These embeddings were then concate-
nated with explicit global features such as sequence length, GRAVY score, and LCR/IDR
fractions to form a comprehensive numerical representation of each protein. This hybrid
encoding captures both global composition and local sequential context, making it espe-
cially suitable for downstream deep learning.

We then feed these combined representations into a Convolutional Neural Network
(CNN). The convolutional layers are particularly well suited for this task because they
can slide across the embedded sequence space and automatically learn useful patterns
without manual feature selection. In this way, the model can detect motif-like structures,
residue dependencies, and short-range interaction patterns that may contribute to LLPS
behavior. With this approach, the model achieved an ROC-AUC of 0.982, showing that
sequence information alone contains strong signals relevant to phase separation.
