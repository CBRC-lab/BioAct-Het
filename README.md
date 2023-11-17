# BioAct-Het: Heterogeneous siamese neural network for bioactivity prediction using novel bioactivity representation 
![Graphical abstract](https://github.com/ph-mehdi/BioAct-Het/blob/main/Figures/4-Graphical%20abstract.png)
Drug failure during experimental procedures due to low bioactivity is a major problem, and predicting bioactivity classes during lead optimization can reduce the risk of failure and enhance the compound bioactivities. Recent studies have shown a relationship between the chemical structure of compounds and their bioactivity, i.e., structure-activity relationship (SAR). However, these studies often overlook the complex relationship between drugs and bioactivity, which involves multiple factors beyond chemical structure alone. To address this issue, we propose the BioAct-Het model which utilizes a heterogenous siamese neural network to find the complex relationship between drugs and bioactivity classes by bringing them into a unified latent space. In this study, we not only define a novel representation for the bioactivity classes named Bio-Prof, but also, we improve the original datasets of bioactivities to address data scarcity. These both ideas cause our model outperformers previous models. The evaluation of BioAct-Het is based on three strategies: association-based, bioactivity class-based, and compound-based. The association-based strategy focuses on supervised learning classification, while the bioactivity class-based strategy adopts a retrospective studies evaluation approach. In contrast, the compound-based strategy is more similar to the concept of meta-learning than the other two strategies.  

# Requirements
We used Python 3.7 and Keras with Tensorflow back-end to develop the main Heterogeneous Siamese Model. To represent the chemical structure of compounds, we use the pre-trained GCN models. To do so, two different models are extracted from the DGL and DGL-Life library named GCN-canonical and GCN-AttentiveFP which have been pre-trained on the intended bioactivity using either canonical featurization or AttentiveFP featurization of atoms, respectively.  RDKit was used to pre-process the SMILEs Strings and access SMILEs fingerprints.

In order to get started you will need:
* Python 3.7
* Keras 2.4.3
* DGL-Life
  * GCN-AttentiveFP
  * GCN-canonical
* RDKit
* Torch 1.13.1
* Tensorflow 2.3.0
* Numpy
* Pandas
* Matbplotlib
  
# Our Approach
This study proposes a new method called BioAct-Het, which aims to determine the likelihood of association between a compound and a bioactivity class, rather than learning the similarity between two compounds, which can be complicated due to relationship challenge. BioAct-Het exploits a heterogeneous siamese neural network  to map chemical compounds and bioactivity classes into a unified latent space that is capable of representing bioactivity classes based on related compounds. The performance of BioAct-Het is evaluated using both supervised learning and meta-learning approaches on three databases: SIDER, Tox21, and MUV.

The main contributions of BioAct-Het are listed as follows:
* To construct the dataset, the proposed model considers a compound – bioactivity class pair (<d,b>) as a positive pair if d activates b and a negative pair otherwise (see section Data preparation).
* To define the problem, we introduce a novel bioactivity representation model, which takes into account the role of bioactivities (see section Data representation).
* To model the complex relationship between compounds and bioactivity classes, we aim at learning a unified latent space via a heterogeneous SNN (see section BioAct-Het model).
* To infer the association between a chemical compound and a bioactivity class, the paper computes the likelihood of association between the compound and the given bioactivity in the unified latent space instead of relying solely on the similarity between two chemical compounds, as is done in previous studies (see section BioAct-Het model).
![Graphical abstract](https://github.com/ph-mehdi/BioAct-Het/blob/main/Figures/4-Graphical%20abstract.png)

# Distribution analysis of chemical compound representation
To assess the effectiveness of the proposed model in bringing compounds with similar bioactivity classes closer together in the latent space, we conduct an experiment to visualize the distribution of chemical compounds before and after applying BioAct-Het, using T-distributed stochastic neighbor embedding 35 (t-SNE) technique. Specifically, Figure 5-A shows the distribution of chemical compound representations extracted from pre-trained GCN-AttentiveFP on the SIDER before training the BioAct-Het model, while Figure 5-B shows their distribution after training with the SIDER database.
![Figure 5-A](https://github.com/ph-mehdi/BioAct-Het/blob/main/Plots/4-T-SNE%20Train%20data.png)
![Figure 5-B](https://github.com/ph-mehdi/BioAct-Het/blob/main/Plots/5-T-SNE%20Test%20Data.png)

# Corresponding and Authors
### Corresponding author
*  Fatemeh Zare-Mirakabad __ Computational Biology Research Center (CBRC), Mathematics and Computer Science Faculty, Amir Kabir University of Technology, Tehran, Iran. Email: f.zare@aut.ac.ir.
### Authors
* M.Paykan Heyrati__ Computational Biology Research Center (CBRC), Mathematics and Computer Science Faculty, Amir Kabir University of Technology, Tehran, Iran. Email: mehdi.paykan.heyrati@gmail.com , m.paykan.heyrati@aut.ac.ir
* Zahra Ghorbanali __ Computational Biology Research Center (CBRC), Mathematics and Computer Science Faculty, Amir Kabir University of Technology, Tehran, Iran. Email: z_ghorbanali@aut.ac.ir
* Mohammad Akbari __ Mathematics and Computer Science Faculty, Amir Kabir University of Technology, Tehran, Iran. Email: akbari.maaut.ac.ir
* Ghasem Pishgahi __ Students' Scientific Research Center (SSRC), Tehran University of Medical Sciences, Tehran, Iran.Email: ghpishgahi@gmail.com
 
 
