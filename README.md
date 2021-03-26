# CalidadAI: Audit Assist System

CalidadAI, a software startup, has processed the regulations from the U.S. Food and Drug Administration (FDA) and generated questions appropriate for the FDA and private company inspectors to use during their audits. Many other regulatory bodies exist, such Health Canada (HC), European Medical Agency (EMEA) etc. Using the FDA regulations as a training set, CalidadAI wants to employ Natural Language Processing techniques to generate questions for the foreign regulatory agencies by determining semantic equivalence between regulations defined by the foreign agencies and the FDA.

The primary focus of the application is to automate and ease the process of pharmaceutical auditing. The end users of the application are in two folds. Firstly, the system can be used for pharmaceutical companies to perform internal audits. Not only does this help monitor companies’ internal processes but helps to prepare for FDA audits. Secondly, it can be used by third party auditors who conduct inspection for pharmaceutical companies and manufacturing facilities.

## Data Labelling
The algorithm used to determine matching regulations uses textual descriptions as its inputs. These descriptions are cleaned as mentioned in the previous section. To lay the foundation for the algorithm, a suitable embedding and a distance or similarity measure need to be determined. These cleaned descriptions should be converted to vectors for the machine to understand the information stored in them and run the algorithm to determine semantic equivalence between these regulations. This vectorization is achieved using embedding models.

### Find Health Canada regulations similar to FDA regulations
Suitable embedding (DistilBERT) and similarity measure (pairwise cosine similarity) to be used is determined and is applied on the dataset to generate corresponding labels. The base dataset is FDA Regulations data, and the corresponding Health Canada regulations should be matched using the labelling algorithm.

### Find FDA regulations similar to Health Canada regulations
The base dataset is the Health Canada Regulations data and the corresponding FDA regulations should be matched using the labelling algorithm. The algorithm to check for similar regulations will result in a similarity score between the two regulations (Health Canada regulation under consideration and an FDA regulation under inspection) and the index of the matched target sentence (FDA regulation). Using these indices, the corresponding FDA regulations details can be populated.

Finding the regulations which are similar to each other and determining their similarity score is executed in two directions i.e., FDA regulations are matched to Health Canada regulations and vice-versa. This is done to ensure every regulation in the dataset have a corresponding match. Additionally, this two-way match helps to find correlation between the prediction of both results thereby creating a layer of sanity check to investigate the matches in both directions.

## Optimization for Precision
Please find the details [here].


Analysis on my [Medium]!

[Medium]:https://sheetalkalburgi.medium.com/
