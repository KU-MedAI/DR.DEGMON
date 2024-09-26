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

**Step 1**. Create a dataset that matches DEGs with drug response data. In this study, the L1000 level5 data (https://clue.io/)was matched with CTRP data (https://portals.broadinstitute.org/ctrp.v2.1/). The detailed process can be found in the  paper. This dataset serves as the input data for the model, where DEGs are the input features and cell viability is the output value. While this study mainly utilized CTRP, other drug response databases such as GDSC, PRISM, and NCI60 can also be used to construct similar datasets.

**Step 2**. Download matrices containing the connectivity information of GO terms. 

For this purpose, we provide three matrix files:
1. A matrix that provides the connectivity information between GO terms. 
2. A matrix that provides information about the level each GO term belongs to.

The above two matrices will be processed and used according to the GO term levels you want to use.

3. A matrix that provides the connectivity information between genes and GO terms. The gene list in the matrix must be matched with the gene list contained in the input DEGs. (Full genes version & selected genes version are both uploaded) 

They are used to design the architecture of the DR.DEGMON. 

[Connection Data](https://zenodo.org/records/13837156?token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6IjFjMjI0NDM2LWMyNTAtNGQ3MC1hNDYzLTBmMWZhY2UzYmFmZSIsImRhdGEiOnt9LCJyYW5kb20iOiIxMTI2MTBiNmNlOTNhZjczNGNlYmQxNTA5YWY4YjM4NSJ9.8TuFSUY4WQWMl5srNh0SEk-VyM9iuWY4v9UMu20C7Pe773YDoX9qfPJ757KXE0R8hBpC35AsxlaV7A4UY518Gw)


*The data for step 2 was originally provided by Deep GoNet. (Bourgeais, V., Zehraoui, F., Ben Hamdoune, M., & Hanczar, B. (2021). Deep GONet: Self-explainable deep neural network based on Gene Ontology for phenotype prediction from gene expression data. BMC Bioinformatics, 22(10), 455. https://doi.org/10.1186/s12859-021-04370-7)*

# Usage
The manuscript for DR.DEGMON can be found DR.DEGMON.ipynb

DR.DEGMON incorporates L2 regularization during training, applying prior biological knowledge to the deep learning model. The recommended lambda value for the L2 regularization is 0.0001, but users can adjust it to find the optimal value.

In this study, the model was analyzed using layer-wise relevance propagation, and the results can be found in the paper's Results section of the paper. As this model incorporates prior biological knowledge, it provides more meaningful insights into model interpretation, which can be used to elucidate the MoA of compounds or to discover biomarkers.

# Contact
If you have any question regard our study, please contact us (mjjeon@korea.ac.kr)

# Funding
This work was supported by the National Research Foundation of Korea Grant (NRF2022R1F1A1070111) and MSIT (Ministry of Science and ICT), Korea, under the ICAN (ICT Challenge and Advanced Network of HRD) program (IITP-2024-RS2022-00156439, IITP-2024-RS-2024-00438263) supervised by the IITP (Institute of Information & Communications Technology Planning & Evaluation)
