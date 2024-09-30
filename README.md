<div align="center">
  <h1>Traffic and congestion prediction on LTE networks</h1>
</div>

<p align="center">
<img src="images\cellular-network.png" class="center" width="45%"/>
</p>

### Overview
<p align="justify">
To handle the dramatic increase in data volume and better serve their customers, mobile network operators need to design and manage network architectures according to the required demand.
A nationwide cellular mobile network contains tens of thousands of base stations. Estimating the traffic increment and consequent congestion of each of these elements can become an arduous and imprecise task, and can lead to incorrect investment decisions. An automation of this methodology means greater speed and standardization of decision-making, serving as a great help to both the technical and marketing areas.

<p align="justify">
The purpose of this work was to to provide a replicable code for the <a href="https://paperswithcode.com/">paperswithcode</a>, based on a study done by D. Chmieliauskas and D. Guršnys, called "LTE Cell Traffic Grow and Congestion Forecasting". For more details, go to: https://paperswithcode.com/paper/lte-cell-traffic-grow-and-congestion.

### Objectives
<p align="justify">
Build a solution capable of predicting long-term (28 days) cell traffic and congestion.

### Technologies Used
* `python 3.9.16`
* `prophet 1.1.5`
* `pandas 1.4.0`
* `sklearn 1.0.2`
* `scipy 1.10.1`
* `numpy 1.23.5`
* `matplotlib 3.7.1`
* `seaborn 0.12.2`

### About the Data
<p align="justify">
The results presented in this work were generated using real data from a cellular network. However, due to compliance reasons, the original data cannot be shared. Instead, a noised sample of the data is available for full code execution.

### Methodology
<p align="justify">
The methodology implemented was adapted from a solution proposed by Chmieliauskas & Guršnys (2019), divided into two parts. Firstly it was necessary to predict <b>cell data traffic</b> and then the <b>cell congestion</b> through PRB (physical resource block) usage.

#### Cell Traffic
<p align="justify">
The regression tool used was Facebook Prophet, developed by Facebook's data science team. Three different configurations for the hyperparameters of yearly, monthly, and daily seasonality were tested, with the latter being split between weekdays and weekends. The performance was evaluated using the sMAPE, EVS, and R2 metrics.

#### Cell Congestion
<p align="justify">
A good KPI for measuring cell congestion is measuring PRB usage, which is limited radio resources that are allocated according to user demand - a good explanation can be obtained from Capozzi, et al (2013). After predicting the network traffic, it was possible to estimate PRB usage through a linear correlation, due to the high correlation between these two variables.

The full code implementation can be found [here](https://github.com/rdemarqui/traffic_prediction_and_congestion/blob/main/LTE_Cell_Traffic_Grow_and_Congestion_Forecasting.ipynb)

### Results and Conclusions
<p align="justify">
As stated at the beginning of this work, the main objective of this work is to replicate the work done by D. Chmieliauskas and D. Guršnys in order to make the code available on paperswithcode.com. Some improvements were suggested throughout the code, such as data transformation through box-cox, the utilization of 1.5-year data history to capture annual seasonality, the differentiation of data between weekdays and weekends to better capture individual cell characteristics, and finally, the use of the sMAPE indicator due to its robustness to outliers. 

<p align="justify">
The results obtained in this work were not satisfactory; however, since there was no tuning performed, it is possible to improve them. The methodology was applied to predict traffic congestion in LTE access network elements, but it can be easily adapted to other technologies, such as 5G, or to other components of the mobile network, such as core elements and data transmission, with the understanding and adaptation of the specificities of the new problem.

### References
* Capozzi, F., Piro, G., Grieco, L.A., Boggia, G., & Camarda, P. (2013). Downlink packet scheduling in LTE cellular networks: Key design issues and a survey. IEEE Communications Surveys and Tutorials 15, 678–700.
* Chmieliauskas, D., & Gursnys, D. (2019). LTE Cell Traffic Grow and Congestion Forecasting. In 2019 Open Conference of Electrical, Electronic and Information Sciences, EStream 2019 - Proceedings, (Institute of Electrical and Electronics Engineers Inc.)
* Tofallis, Chris (2015). A better measure of relative prediction accuracy for model selection and model estimation. Journal of the Operational Research Society
* FaceBook Research (2017). Prophet: forecasting at scale. https://research.fb.com/blog/2017/02/prophet-forecasting-at-scale/
* Rafferty, G. (2021). Forecasting Time Series Data with Facebook Prophet. Birmingham, Packt Publishing Ltd.
