# Utility-Based Context-Aware Multi-Agent Recommendation System for Energy Efficiency in Residential Buildings

![results](/agents.jpg)

A digital companion to the research paper 

```
Valentyna Riabchuk, Leon Hagel, Felix Germaine, and Alona Zharova (2022). 
Utility-Based Context-Aware Multi-Agent Recommendation System for Energy Efficiency in Residential Buildings. 
arXiv preprint. DOI: doi.org/10.48550/arXiv.2205.02704.
```
The paper is available at: [arXiv](https://doi.org/10.48550/arXiv.2205.02704)

## Summary 

A significant part of CO2 emissions is due to high electricity consumption in residential buildings. Using load shifting can help to improve the households’ energy efficiency. To nudge changes in energy consumption behavior, simple but powerful architectures are vital. 

We summarize the contributions of this paper as follows. 
1. We propose a novel utility-based context-aware multi-agent recommendation system generating device usage recommendations for energy efficiency via load shifting in residential buildings. 
2. We suggest a framework for the performance evaluation of the device usage recommendation system. 
3. To our knowledge, we are the first to provide a formalization of the task for the device usage recommendations for load shifting.

As a utility-based recommender system, it models user preferences depending on habitual device usage patterns, user availability, and device usage costs. As a context-aware system, it requires an external hourly electricity price signal and appliance-level energy consumption data. Due to a multi-agent architecture, it provides flexibility and allows for adjustments and further enhancements. 

We provide a statistically grounded solution for predicting user availability to make recommendations when the user is at home and available for recommendations. The approach also uses a probability of the device usage on a given day to decide whether to recommend or not. As a result, our recommender system flexibly adapts to actual usage patterns or changing usage behavior. Moreover, it can provide multiple recommendations per week for frequently used devices and few (or none) for infrequently used ones. In addition, the provided algorithm allows calculating costs with higher precision since the system takes into account devices’ load profiles to compute an overall estimation of the usage costs. In other words, it considers not only the electricity price at the device’s starting hour but also the costs for the following usage hours, given the multihour device’s usage duration.

The empirical analysis aims to quantify how much a user can save by utilizing our recommender system. To achieve this, we create recommendations, determine the acceptability of the recommendations and calculate the energy costs for running the devices with and without recommendations to receive the potential energy cost saving. The results show that the system can provide energy cost savings of 18% and more for most studied households if the user implements all recommendations

We provide a comprehensive tutorial in Jupyter Notebook with code in Python for all the steps described in this paper and beyond.

**Keywords:** recommendation system, energy efficiency, load shifting, energy consumption behavior.

## Data

We use the REFIT Electrical Load Measurements data ([Murray et al., 2017](https://www.nature.com/articles/sdata2016122)) to analyze our recommender system. The data contains the energy consumption of nine different devices used in 20 households in the United Kingdom from 2013 to 2015. 

For the day-ahead prices provided by the Price Agent, we access the online database for industry day-ahead prices for the United Kingdom ([ENTSO-E, 2015](https://transparency.entsoe.eu/transmission-domain/r2/dayAheadPrices/show)). 

## Setup

The REFIT data files can be accessed using the following link: https://www.doi.org/10.15129/9ab14b0e-19ac-4279-938f-27f643078cec.

After downloading the clean household data needs to be copied to ./data

## Project structure
````
├── README.txt                                                  # this readme file
│
├── agents.jpg                                                  # figure of the multi-agent architecture
│
├── code.                                                       # agent notebooks + .py scripts
│   ├── Activity_Agent.ipynb
│   ├── Evaluation_Agent.ipynb
│   ├── Load_Agent.ipynb
│   ├── Preparation_Agent.ipynb
│   ├── Price_Agent.ipynb
│   ├── Recommendation_Agent.ipynb
│   ├── Usage_Agent.ipynb
│   ├── agents.py
│   └── helper_functions.py
│
├── data                                                        # REFIT household data, price data, REFIT readme
│   ├── CLEAN_House1.csv                                            # household data (Murray et al., 2017, household 1 to 10) 
│   ├── [...]                                                       # is not included, however required for evaluation
│   ├── CLEAN_House10.csv                                           
│   ├── REFIT_Readme.txt
│   └── Day-ahead Prices_201501010000-201601010000.csv              # day-ahead prices provided by ENTSO-E, n.d.
│
│
└── export                                                      # path for exporting configurations and intermediate results
    ├── 1_config.json                                               # configurations used for evaluating households 1 to 10
    ├── [...]
    └── 10_config.json
````

## Citation

If you use this code in your research, please cite our [paper](https://doi.org/10.48550/arXiv.2205.02704).

```
@misc{RHGZ2022,
  title = {Utility-Based Context-Aware Multi-Agent Recommendation System for Energy Efficiency in Residential Buildings},
  author = {Riabchuk, Valentyna and Hagel, Leon and Germaine, Felix and Zharova, Alona},
  publisher = {arXiv},
  year = {2022},
  doi = {10.48550/ARXIV.2205.02704}  
}
```

## Contact
- Alona Zharova, alona.zharova@hu-berlin.de
