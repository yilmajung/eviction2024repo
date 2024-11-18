# Hotspots of Eviction: 
## Guiding Dual-Track Policy Intervention with Spatial Analysis

### Description
This study investigates the spatial structure of eviction filings at the Census Block Group (CBG) level to determine if high eviction rates are due to neighborhood characteristics or other factors like landlords' practices. We addressed three research questions: 1) the relationship between eviction filings due to nonpayment of rent and neighborhood characteristics, 2) the differences between eviction filings due to nonpayment and those for other reasons, and 3) the extent to which high rates of eviction filings in certain CBGs can be attributed to neighborhood characteristics versus unexplained spatial effects. We used Restricted Spatial Generalized Linear Mixed Models (RSGLMMs) with Hamiltonian Monte Carlo (HMC) sampling to estimate neighborhood fixed effects and spatial random effects, using data from Dallas County. This repository includes all the code used for the study. For privacy and security issues, we are not sharing our original dataset here, but only two processed datasets: ```/data/acs_evic_data_wo_zero_pop.csv``` and ```/data/acs_evic_data_np_wo_zero_pop.csv```.

This study was accepted for the *Special Session on Understanding New Markets by Data Science, Social Science, and Economics* at the *IEEE International Conference on Big Data 2024* (*BigData 2024*). The manuscript is available [here](https://pike.psu.edu/publications/bigdata24-evict.pdf).

### How to Use
We used two programming languages: Python and R. Python was primarily used for data mining and processing (and EDA), while R was utilized for HMC sampling (via Stan). If you want to review the entire process from scratch, please follow these steps in order.

1. Collect the neighborhood characteristics per CBG from the American Community Survey using ```acs_api_query.py```
2. Collect the amenity information through OpenStreetMap (Overpass) API using ```count_amenity_01mile.py``` and ```amenity_data_cleansing.ipynb```
3. Do EDA and data processing using ```sglmm_analysis.ipynb```
4. Conduct SGLMM with HMC sampling using ```SGLMM_eviction6_amenity.R``` and ```slgmm_orthog_eff_small.stan```
5. Visualize the results using ```results_visualization_amenity.R```

The same process can be applied to the experiment of the prepandemic era.

### Dependency Issue
Please refer to ```evic_env.yml ```.
