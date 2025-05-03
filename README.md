# CS343 Graph Data Science Project: Node Classification and Link Prediction in Bibliographic Data

This is a machine learning project by Shaaf Farooque and Sajal Fatima.

## Before you run

Modify the database config to have following:

```neo4j config
server.directories.import=F:/Node-Classification-and-Link-Prediction-Project/Data (replace with the root folder where the CSVs exist)
dbms.security.allow_csv_import_from_file_urls=true
```

## Usage

Run the provided LoadDataScript.txt file in neo4j browser.

## Dummy1


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
    url = {https://doi.org/10.1162/qss\_a\_00163},
    eprint = {https://direct.mit.edu/qss/article-pdf/2/4/1466/2007917/qss\_a\_00163.pdf},
}