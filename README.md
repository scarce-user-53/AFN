# Explainable and Interpretable Forecasts on Non-Smooth Multivariate Time Series for Responsible Gameplay

This is the official implementation of Explainable and Interpretable Forecasts on Non-Smooth Multivariate Time Series for Responsible Gameplay  _(under review at KDD 2024)_.

<img 
    src="img\AFN_architecture.jpg"
    alt="AFN Architecture" 
    style="height:400; margin-left:auto; margin-right:auto; display:block" 
/>
<div style="display:table; margin-left:auto; margin-right:auto"><p style="font-size:14pt; font-family:Verdana">AFN Architecture</p></div>
  
<br>

## Abstract
Multi-variate Time Series (MTS) forecasting has made large strides (with very negligible errors) through recent advancements in neural networks, e.g., Transformers. However, in critical situations like pre- dicting gaming overindulgence that affects one’s mental well-being; an accurate forecast without a contributing evidence (explanation) is irrelevant. Hence, it becomes important that the forecasts are Interpretable - intermediate representation of the forecasted trajectory is comprehensible; as well as Explainable - attentive input features and events are accessible for a personalized and timely intervention of players at risk. While the contributing state of the art research on interpretability primarily focuses on temporally-smooth single-process driven time series data, our online multi-player gameplay data demonstrates intractable temporal randomness due to intrinsic orthogonality between player’s game outcome and her intent to engage further. We introduce a novel deep Actionable Forecasting Network (AFN), which addresses the inter-dependent challenges associated with three exclusive objectives -   
1. Forecasting accuracy
2. Smooth comprehensible trajectory
3. Explanations via multi-dimensional input features while tackling the challenges introduced by our non-smooth temporal data, together in one single solution.   

AFN establishes a new benchmark via:  
1. Achieving 25% improvement on the MSE of the forecasts on player data in comparison to the SOM-VAE based SOTA network
2. Attributing unfavourable progression of a player’s time series to a specific future time step(s), with the premise of eliminating near-future overindulgent player volume by over 18% with player specific actionable inputs feature(s)
3. Pro-actively detecting over 23% (∼100% jump from SOTA) of the to-be overindulgent, players on an average, 4 weeks in advance.


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

## Prerequisites

In order to install and run the model, you will need a working Python 3 distribution, and optionally a NVIDIA GPU with CUDA and cuDNN installed.

## Installing

In order to install the model and run it, you have to follow these steps:

* Clone the repository, i.e. run `git clone https://github.com/scarce-user-53/AFN.git`
* Change into the directory, i.e. run `cd AFN`
* Extract the data from `data` folder: `tar -xvzf players_sample_data.tar.gz`
* Install the requirements, i.e. run `pip install -r requirements.txt`
* Change into the code directory, i.e. `cd src`

## Training
After successful installation, now you should be able to run the code on our players' gameplay time-series data. The command is: `python main.py`. 


### Train on other kinds of data 

If you want to train on other types of data (eg. ETT, WTH, ECL, etc.):  
1. First save the data csv file in the `data/` folder.  
2. Run `sh scripts/data_processing.sh` according to the chosen input/output lengths.  
3. The data will be dumped as `data/model_ready_data.h5`.  
4. Make the `filename` changes in the `config.json` file.  
5. Run `python main.py`.


## Acknowledgement
We highly appreciate the following works for their valuable code and data for time series forecasting:

https://github.com/Thinklab-SJTU/Crossformer

https://github.com/zhouhaoyi/Informer2020

https://github.com/ratschlab/dpsom

https://github.com/ratschlab/SOM-VAE
