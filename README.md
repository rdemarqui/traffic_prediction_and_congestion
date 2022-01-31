## Traffic and congestion prediction on LTE networks
![Alt text](images/cellular-network.png?raw=true "Tower")

### Overview
To handle the dramatic increase in data volume and better serve their customers, mobile network operators need to design and manage network architectures according to the required demand.
A nationwide cellular mobile network contains tens of thousands of base stations. Estimating the traffic increment and consequent congestion of each of these elements can become an arduous and imprecise task, and can lead to incorrect investment decisions. An automation of this methodology means greater speed and standardization of decision making, serving as a great help to both the technical and marketing areas.

### Objectives
Build a solution capable of predicting long term (3 months) cell traffic and congestion.

### Tecnologies Used
* Facebook Prophet
* Pandas 1.4.0
* Scikit-learn 1.0.2

### About the Data

### Methodolgy
The methodology implemented was adapted from a solution proposed by Chmieliauskas & Guršnys (2019).
The regression tool used was Facebook Prophet, developed by Facebook's data science team. Through the grid search method, were identified the hyperparameters that most influenced the algorithm's performance, and based on this result, ten configurations were created to be applied to the entire dataset.

The full implementation can be found [here](https://github.com/rdemarqui/traffic_prediction_and_congestion/blob/main/traffic_prediction_congestion.ipynb)


### Results and Conclusions
#### Cell Traffic
#### Cell Congestion

### References
* Capozzi, F., Piro, G., Grieco, L.A., Boggia, G., & Camarda, P. (2013). Downlink packet scheduling in LTE cellular networks: Key design issues and a survey. IEEE Communications Surveys and Tutorials 15, 678–700.
* Chmieliauskas, D., & Gursnys, D. (2019). LTE Cell Traffic Grow and Congestion Forecasting. In 2019 Open Conference of Electrical, Electronic and Information Sciences, EStream 2019 - Proceedings, (Institute of Electrical and Electronics Engineers Inc.)
* FaceBook Research (2017). Prophet: forecasting at scale. https://research.fb.com/blog/2017/02/prophet-forecasting-at-scale/
* Rafferty, G. (2021). Forecasting Time Series Data with Facebook Prophet. Birmingham, Packt Publishing Ltd.
