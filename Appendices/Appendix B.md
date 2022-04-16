# Appendix B: Computational Cost
To calculate the energy consumption of different DAPT strategies, the free tool [1] was used. The tool calculates the energy consumption based on the running time of the algorithm along with the hardware settings (number of GPUs used, cloud vs. the local server, location of the cloud server, etc.). The first step was to calculate the total running time for each DAPT strategy. Table B1 shows each strategy's phase-wise and total running time and energy consumption in Kilowatt-Hour (kWh). Other settings used for each strategy are given in Table B2. As all the experiments were conducted using the same hardware platform, the difference in energy consumption of these strategies is only because of their running time. 
<p align="center">
  <strong>Table B1:</strong> Running time (phase-wise and total) and energy consumption for each DAPT strategy
 </p>
 <p align="center">

|     Strategy Name    |     Phase    |     Epochs    |     Phase-Wise Running Time (Hours:Minutes)    |     Total Running Time (Hours:Minutes)    |     Energy Consumption (kWh)    |
|----------------------|--------------|---------------|------------------------------------------------|-------------------------------------------|---------------------------------|
|     ImageNet         |     -        |               |     0                                          |                                           |                                 |
|     ImageNet_F1B     |     -        |               |     0                                          |                                           |                                 |
|     ImageNet_F2B     |     -        |               |     0                                          |                                           |                                 |
|     DA_L1SB          |     1        |     1000      |     132:12.163                                 |     154:37.967                            |     67.93                       |
|                      |     2        |               |     22:25.804                                  |                                           |                                 |
|     DA_L2SB          |     1        |               |     132:12.163                                 |     159:39.529                            |     70.12                       |
|                      |     2        |               |     27:27.366                                  |                                           |                                 |
|     DA               |     1        |               |     132:12.163                                 |     215:56.988                            |     94.86                       |
|                      |     2        |               |     83:44.825                                  |                                           |                                 |
|     DA_TF_F1B        |     1        |               |     40:14.181                                  |     69:14.181                             |     30.41                       |
|                      |     2        |               |     29:00                                      |                                           |                                 |
|     DA_TF_F2B        |     1        |               |     68:17.844                                  |     128:7.572                             |     56.28                       |
|                      |     2        |               |     59:49.728                                  |                                           |                                 |
|     DA_L1SB_PFT      |     1        |               |     132:12.163                                 |     175:4.021                             |     76.90                       |
|                      |     2        |               |     14:56.916                                  |                                           |                                 |
|                      |     3        |               |     27:54.942                                  |                                           |                                 |
|     DA_L2SB_PFT      |     1        |               |     132:12.163                                 |     179:1.836                             |     78.64                       |
|                      |     2        |               |     18:54.731                                  |                                           |                                 |
|                      |     3        |               |     27:54.942                                  |                                           |                                 |


<p align="left">
  <strong>Table B2:</strong> Parameters for Green Algorithms tool [1]
 </p>
 

|     Parameter                                                                    |     Value                         |
|----------------------------------------------------------------------------------|-----------------------------------|
|     Type of   cores                                                              |     GPU                           |
|     Number of   GPUs                                                             |     1                             |
|     Model                                                                        |     TPU V2                        |
|     Memory   available (in GB)                                                   |     35                            |
|     Select   the platform used for the computations                              |     Cloud   computing             |
|                                                                                  |     Other                         |
|     Select   location                                                            |     North   America               |
|                                                                                  |     United   States of America    |
|                                                                                  |     Any                           |
|     Do you   know the real usage factor of your GPU?                             |     No                            |
|     Do you   know the Power Usage Efficiency (PUE) of your local data centre?    |     No                            |
|     Do you   want to use a Pragmatic Scaling Factor?                             |     No                            |


<p align="left">
  The performance of different strategies in relation to their computational cost (memory in terms of parameters and energy consumption in kWh) has been visualized in Fig. B1.
 </p>
 
  
  <img src="https://github.com/mehmoodyasar/Resource-Efficient-Domain-Adaptive-Pre-Training/blob/main/Appendices/Fig.%20B1.png">
<p align="center">
    <strong>Fig. B1:</strong> Performance comparison of different strategies in relation to their memory usage (parameters) and energy consumption
</p>

<p align="left">
  [1] L. Lannelongue, J. Grealey, and M. Inouye, "Green algorithms: Quantifying the carbon footprint of computation," Advanced Science, vol. 8, no. 12, p. 2100707, 2021.
 </p>
