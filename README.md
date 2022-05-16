# Utility-Based Context-Aware Multi-Agent Recommendation System for Energy Efficiency in Residential Buildings

[fig tba]
![results](/figures/agents.jpg)

A digital companion to the research paper 

```
**Valentyna Riabchuk, Leon Hagel, Felix Germaine, and Alona Zharova** (2022). 
Utility-Based Context-Aware Multi-Agent Recommendation System for Energy Efficiency in Residential Buildings. 
arXiv preprint. DOI: doi.org/10.48550/arXiv.2205.02704.
```
The paper is available at: [arXiv](https://doi.org/10.48550/arXiv.2205.02704)

- [Summary](#summary)
- [Repo structure](#repo-structure)
- [Data](#data)

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

## Repo structure

The repo has the following structure:

## Data

We use the REFIT Electrical Load Measurements data ([Murray et al., 2017](https://www.nature.com/articles/sdata2016122)) to analyze our recommender system. The data contains the energy consumption of nine different devices used in 20 households in the United Kingdom from 2013 to 2015. 

For the day-ahead prices provided by the Price Agent, we access the online database for industry day-ahead prices for the United Kingdom ([ENTSO-E, 2015](https://transparency.entsoe.eu/transmission-domain/r2/dayAheadPrices/show)). 
