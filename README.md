# DR.DEGMON
DR.DEGMON: Self-explainable deep neural network for drug-induced cell viability prediction incorporating differentially expressed genes and Gene Ontology


<img src="https://github.com/user-attachments/assets/f2a99ac4-aab7-4f89-b14e-51eeba98ff77" width="450" height="600"/>

# Abstract
Background: Accurate cancer drug response prediction is essential for advancing cancer treatment strategies and drug development. With the growing availability of large-scale pharmacogenomics datasets, a lot of deep learning models have been proposed to predict cancer drug responses. However, the existing models often lack the interpretability to uncover novel biomedical insights, such as the mechanism of action (MoA) of drugs.
Results: In this study, we propose DR.DEGMON (Drug Response prediction using Differentially Expressed Genes with Multi-layer perceptron integrating gene Ontology Network), a self-explainable deep neural network designed to predict cell viability of pan-cancer cell lines in response to drug treatments using differentially expressed genes. It leverages biological prior knowledge by incorporating Gene Ontology (GO) into the hierarchical structure of a multi-layer perceptron. DR.DEGMON’s architecture enables the identification of key genes and GO terms that contribute to drug responses by Layer-wise Relevance Propagation (LRP), providing insights into the MoA of specific drugs. DR.DEGMON achieves a Pearson Correlation Coefficient of 0.8568 which outperforms baseline models. We also validated our model using external datasets and we employed LRP to obtain the relevance scores of input genes and nodes representing GO terms.
Conclusion: DR.DEGMON not only offers high performance in predicting drug responses but also provides interpretable results. The integration of GO and the use of LRP enable the model to elucidate the underlying biological processes involved in drug response, making it a valuable tool for predicting outcomes and discovering new biomedical knowledge in cancer pharmacogenomics. This approach can offer both practical utility in drug development and a deeper understanding of cancer biology.

# Requirements

Tensorflow == 2.12.1  
Keras == 2.12.0  

