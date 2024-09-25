# DR.DEGMON
DR.DEGMON: Self-explainable deep neural network for drug-induced cell viability prediction incorporating differentially expressed genes and Gene Ontology


<img src="https://github.com/user-attachments/assets/f2a99ac4-aab7-4f89-b14e-51eeba98ff77" width="450" height="600"/>

# Abstract
Accurate cancer drug response prediction is essential for advancing cancer treatment strategies and drug development. With the growing availability of large-scale pharmacogenomics datasets, a lot of deep learning models have been proposed to predict cancer drug responses. However, the existing models often lack the interpretability to uncover novel biomedical insights, such as the mechanism of action (MoA) of drugs. In this study, we propose DR.DEGMON (Drug Response prediction using Differentially Expressed Genes with Multi-layer perceptron integrating gene Ontology Network), a self-explainable deep neural network designed to predict cell viability of pan-cancer cell lines in response to drug treatments using differentially expressed genes. It leverages biological prior knowledge by incorporating Gene Ontology (GO) into the hierarchical structure of a multi-layer perceptron. DR.DEGMON’s architecture enables the identification of key genes and GO terms that contribute to drug responses by Layer-wise Relevance Propagation (LRP), providing insights into the MoA of specific drugs. DR.DEGMON achieves a Pearson Correlation Coefficient of 0.8568 which outperforms baseline models. We also validated our model using external datasets and we employed LRP to obtain the relevance scores of input genes and nodes representing GO terms. DR.DEGMON not only offers high performance in predicting drug responses but also provides interpretable results. The integration of GO and the use of LRP enable the model to elucidate the underlying biological processes involved in drug response, making it a valuable tool for predicting outcomes and discovering new biomedical knowledge in cancer pharmacogenomics. This approach can offer both practical utility in drug development and a deeper understanding of cancer biology.

# Requirements

Tensorflow == 2.12.1  
Keras == 2.12.0  

# Data Preparing
You need to prepare two steps of data:

Step 1. A dataset that matches DEGs with drug response data. In this study, the L1000 level5 data ((https://clue.io/) and CTRP data (https://portals.broadinstitute.org/ctrp.v2.1/) were matched, and this process can be found in the paper. Ultimately, this serves as the input data for the model, where DEGs are the inputs and cell viability is the output. In addition to CTRP, various drug response databases such as GDSC, PRISM, and NCI60 can be used to build datasets.

Step 2. A matrix containing the connection information of GO terms. This determines the MLP structure of the model and also influences the L2 regularization of the loss function. This matrix contains connection information between GO terms at different levels, based on the input data (genes), and it is used to define the structure of the MLP.

For this purpose, we provide three matrix files:
1. A matrix containing the connection information between GO terms.
2. A matrix representing the levels of each GO term.
3. A matrix containing the connection information between DEGs (used as input) and GO terms at specific levels.

Depending on which levels of GO terms to use and the acquired DEG data, genes must be selected to construct the genes-GO term connection information.
*The data for step 2 was provided by Deep GoNet.

# Conclusion
DR.DEGMON constructed incorporates L2 regularization during training, applying prior biological knowledge to the deep learning model. The recommended lambda value for the L2 regularization is 0.0001, but users can adjust it to find the optimal value.

In this study, the model was analyzed using layer-wise relevance propagation, and the results can be found in the paper's Results section. As this model incorporates prior biological knowledge, it provides more meaningful insights into model interpretation, which can be used to elucidate the mechanism of action (MoA) of compounds or to discover biomarkers.

# Contact
If you have any question regard our study, please contact me (wtlim@korea.ac.kr)
