# CS343 Graph Data Science Project

## Node Classification and Link Prediction in Bibliographic Data

### Group Tasks:
Node Classification: Author Classification (Sajal Fatima)

Link Prediction: Citation Recommendation (Shaaf Farooque)

## Overview

This project explores graph-based machine learning on a bibliographic dataset using Neo4j and Python. We focused on two key tasks:
Author Classification: Predicting the research domain of an author using their co-authorship graph.
Citation Recommendation: Predicting potential citations for a paper using citation networks and graph-based link prediction.
We constructed a knowledge graph from CSV-based metadata (authors, papers, topics, journals, references) and applied ML pipelines to derive meaningful predictions.

## Dataset Description
The dataset consists of:

* authors.csv: Author metadata
* journal.csv: Journal metadata
* paper.csv: Paper metadata
* topic.csv: Topics
* paper_journal.csv: Paper-journal relationship
* paper_topic.csv: Paper-topic relationship
* paper_reference.csv: Citation links between papers

## Project Workflow

### 1. Data Preprocessing
Loaded CSVs and cleaned missing/duplicate data.
Normalized entities (authors, papers, journals, topics).
Merged relational mappings (e.g., paper_topic.csv) for future use.

### 2. Graph Construction
Built a property graph using Neo4j.
Nodes: Author, Paper, Topic, Journal
Relationships: WROTE, CITES, PUBLISHED_IN, HAS_TOPIC, CO_AUTHOR

### 3. Node Classification – Author Domain Prediction
Constructed author embeddings from their neighborhood (e.g., co-authors, topics).
Trained a classification model (e.g., LightGBM) to predict research domain/topic ID of authors.
Evaluation metrics: Accuracy, F1-score, Precision, Recall.

### 4. Link Prediction – Citation Recommendation
Treated the citation graph as directed.
Used Neo4j to extract paper-paper citation relationships (existing and candidate).
Engineered structural graph features (e.g., common neighbors, adamic adar).
Trained ML model (LightGBM) to predict if one paper should cite another.
Addressed class imbalance using SMOTE on training set.
Evaluation metrics: ROC-AUC, Precision, Recall, F1-score.

## Results

| Task                    | Model               | ROC-AUC | Precision | Recall | Comments                                           |
| ----------------------- | ------------------- | ------- | --------- | ------ | -------------------------------------------------- |
| Author Classification   | DATA                | DATA    | DATA      | DATA   | lorem ipsum                                        |
| Citation Recommendation | LightGBM (baseline) | 0.53    | 0.97      | 0.06   | High precision but very low recall;                |
| Citation Recommendation | LightGBM (features) | 0.69    | 0.90      | 0.37   | Feature inclusion improves recall moderately;      |


## Reproducibility

### Prerequisites
* Python 3.8+
* Neo4j Desktop
* Jupyter Notebook / VS Code
* Python Libraries: py2neo ,pandas ,networkx ,numpy ,scikit-learn ,lightgbm ,random ,matplotlib ,seaborn ,imbalanced-learn (imblearn)

### Setup Instructions

1. Clone the repo
2. Install mentioned python libraries

```python
pip install <library>
```
3. get data from https://github.com/habib-university/cs343-project/
4. Load the CSVs into dataset_cleaning.ipynb and store the cleaned datasets into a folder named Data inside the repository
5. Create database on neo4j
6. Modify the database config to have following:

```neo4j config
server.directories.import=F:/Node-Classification-and-Link-Prediction-Project/Data (replace with the root folder where the CSVs exist)
dbms.security.allow_csv_import_from_file_urls=true
```

7. copy and paste LoadDataScript.txt and run it as a neo4j query
8. open any notebook and run

## Report Structure (Not yet submitted)
(To be updated)

## Team Members & Contributions
| Name                   | Task                                                |
| -------------          | --------------------------------------------------- |
|   Shaaf Farooque       | Citation recommendation, README                     |
|   Sajal Fatima         | Author classification, Dataset Cleaning             |

## Citation

```
@article{10.1162/qss_a_00163,
    author = {Rothenberger, Liane and Pasta, Muhammad Qasim and Mayerhoffer, Daniel},
    title = "{Mapping and impact assessment of phenomenon-oriented research fields: The example of migration research}",
    journal = {Quantitative Science Studies},
    volume = {2},
    number = {4},
    pages = {1466-1485},
    year = {2021},
    month = {12},
    issn = {2641-3337},
    doi = {10.1162/qss_a_00163},
    url = {https://doi.org/10.1162/qss_a_00163}
}
```