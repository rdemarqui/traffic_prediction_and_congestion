## Traffic and congestion prediction on LTE networks
<p align="center">
<img src="images\cellular-network.png" class="center" width="45%"/>
</p>

### Overview
To handle the dramatic increase in data volume and better serve their customers, mobile network operators need to design and manage network architectures according to the required demand.
A nationwide cellular mobile network contains tens of thousands of base stations. Estimating the traffic increment and consequent congestion of each of these elements can become an arduous and imprecise task, and can lead to incorrect investment decisions. An automation of this methodology means greater speed and standardization of decision making, serving as a great help to both the technical and marketing areas.

The purpose of this work was to to provide a replicable code for the [paperswithcode.com](https://paperswithcode.com/), based on study done by D. Chmieliauskas and D. Guršnys, called "LTE Cell Traffic Grow and Congestion Forecasting,". For more details, go to: https://paperswithcode.com/paper/lte-cell-traffic-grow-and-congestion.

### Objectives
Build a solution capable of predicting long term (3 months) cell traffic and congestion.

### Tecnologies Used
* `python 3.9.16`
* `fbprophet 0.7.1`
* `pandas 1.4.0`
* `sklearn 1.0.2`
* `scipy 1.10.1`
* `numpy 1.23.5`
* `matplotlib 3.7.1`
* `seaborn 0.12.2`

### About the Data
The study and results were made with data collected from a real network of an certain city. Unfortunately it's not possible to share it.

### Methodology
The methodology implemented was adapted from a solution proposed by Chmieliauskas & Guršnys (2019), divided in two parts. Firstly it was necessary to predict **cell data traffic** and then the **cell congestion** through PRB (physical resource block) usage.

#### Cell Traffic
The regression tool used was Facebook Prophet, developed by Facebook's data science team. Through the grid search method, were identified the hyperparameters that most influenced the algorithm's performance, and based on this result, ten configurations were created to be applied to the entire dataset.

#### Cell Congestion
A good KPI for measuring cell congestion is measuring PRB usage, which are limited radio resources that are allocated according to user demand - a good explanation can be obtained in Capozzi, et al (2013). After predicting the netowrk traffic, it's possible to estimate PRB usage through a linear correlation, due to high correlation between these two variables.

The full implementation can be found [here](https://github.com/rdemarqui/traffic_prediction_and_congestion/blob/main/LTE_Cell_Traffic_Grow_and_Congestion_Forecasting.ipynb)

### Results and Conclusions
As stated at the beginning of this work, the main objective of this work is to replicate the work done by D. Chmieliauskas and D. Guršnys in order to make the code available on paperswithcode.com. Some improvements were suggested throughout the code, such as data transformation through box-cox, the utilization of a 1.5-year data history to capture annual seasonality, the differentiation of data between weekdays and weekends to better capture individual cell characteristics, and finally, the use of the sMAPE indicator due to its robustness to outliers. The results obtained in this work were not satisfactory; however, since there was no tuning performed, it is possible to improve them.

### References
* Capozzi, F., Piro, G., Grieco, L.A., Boggia, G., & Camarda, P. (2013). Downlink packet scheduling in LTE cellular networks: Key design issues and a survey. IEEE Communications Surveys and Tutorials 15, 678–700.
* Chmieliauskas, D., & Gursnys, D. (2019). LTE Cell Traffic Grow and Congestion Forecasting. In 2019 Open Conference of Electrical, Electronic and Information Sciences, EStream 2019 - Proceedings, (Institute of Electrical and Electronics Engineers Inc.)
* Tofallis, Chris (2015). A better measure of relative prediction accuracy for model selection and model estimation. Journal of the Operational Research Society
* FaceBook Research (2017). Prophet: forecasting at scale. https://research.fb.com/blog/2017/02/prophet-forecasting-at-scale/
* Rafferty, G. (2021). Forecasting Time Series Data with Facebook Prophet. Birmingham, Packt Publishing Ltd.
