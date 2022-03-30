# Resource efficient domain adaptive pre-training
This repository contains the complete code for reproducing the results of the study "Resource-efficient domain adaptive pre-training for medical images." Please download the arXiv pre-print of the study here.<br>
## General guidelines
Run the jupyter notebook files in the order suggested here. Also, run the cells from top to bottom within each notebook file. The tasks you need to perform to reproduce the results in the study are:
<ol>
    <li>Dataset preparation</li>
    <li>Domain adaptive pre-training (DAPT)</li>
    <li>Features extraction</li>
    <li>Downstream classification and evaluation</li>
    <li>Robustness check</li>
    <li>Visualization of the results</li>
</ol>

### 1. Dataset preparation
All the datasets are converted to .npy files (where each array element has the data type of float16). To do so, all the images/slices are read and stored inside NumPy arrays (images/slices of each class are stored in a different array). These arrays are saved as .npy files.
The code files -----, -------, -------, and ------ in the "Dataset preparation" folder contain code to save the datasets BraTS 2020 (T1 sequence), contrast-enhanced MRI (CE-MRI), Harvard Medical School (HMS), and Kaggle brain tumor type classification (Kaggle BTTC), respectively as .npy files.

### 2. Domain adaptive pre-training (DAPT)
The following table summarizes the training protocol for all the strategies for the DAPT (please see the paper for further details):
| Strategy Name   	| Architecture                 	| Total Parameters 	| Phase  	| Trainable Parameters 	| Epochs 	| Energy Consumption (kWh) 	|
|-----------------	|------------------------------	|------------------	|--------	|----------------------	|--------	|--------------------------	|
| ImageNet        	| ResNet50                     	|                  	| -      	| -                    	| -      	| -                        	|
| DA              	| ResNet50                     	| 23,589,761       	| 1      	| 2,049                	| 1000   	| 94.86                    	|
|                 	|                              	|                  	| 2      	| 23,483,521           	| 150    	|                          	|
| DA_L1SB         	| ResNet50                     	| 23,589,761       	| 1      	| 2,049                	| 1000   	| 67.93                    	|
|                 	|                              	|                  	| 2      	| 4,461,569            	| 150    	|                          	|
| DA_L2SB         	| ResNet50                     	| 23,589,761       	| 1      	| 2,049                	| 1000   	| 70.12                    	|
|                 	|                              	|                  	| 2      	| 8,921,089            	| 150    	|                          	|
| DA_L1SB_PFT     	| ResNet50                     	| 23,589,761       	| 1      	| 2,049                	| 1000   	| 76.90                    	|
|                 	|                              	|                  	| 2      	| 4,461,569            	| 100    	|                          	|
|                 	|                              	|                  	| 3      	| 23,483,521           	| 50     	|                          	|
| DA_L2SB_PFT     	| ResNet50                     	| 23,589,761       	| 1      	| 2,049                	| 1000   	| 78.64                    	|
|                 	|                              	|                  	| 2      	| 8,921,089            	| 100    	|                          	|
|                 	|                              	|                  	| 3      	| 23,483,521           	| 50     	|                          	|
| DA_TF_F1B       	| First One Block of ResNet50  	| 230,017          	| 1      	| 257                  	| 1000   	| 30.41                    	|
|                 	|                              	|                  	| 2      	| 224,129              	| 150    	|                          	|
| DA_TF_F2B       	| First Two Block of ResNet50  	| 1,460,609        	| 1      	| 513                  	| 1000   	| 56.28                    	|
|                 	|                              	|                  	| 2      	| 1,440,385            	| 150    	|                          	|
| ImageNet_TF_F1B 	| First One Block of ResNet50  	| 229,760          	| -      	| -                    	| -      	| -                        	|
| ImageNet_TF_F2B 	| First Two Blocks of ResNet50 	| 1,460,096        	| -      	| -                    	| -      	| -                        	|

The notebooks -----, -----, and ----- inside the folder "Domain adaptive pre-training (DAPT)" contains the code for DAPT phase 1, 2, and 3, respectively.

### 3. Features extraction
The notebook ------- inside the folder "Features extraction" contains the code for extracting features from all the domain-adaptively pre-trained models.

### 4. Downstream classification
The notebook ------- in the folder "Downstream classification" contains the brain disease classification and brain tumor type classification code.

### 5. Robustness check
The notebook ------- in the folder "Robustness check" contains the code to evaluate the robustness of models trained for the CE-MRI dataset for all the DAPT strategies.

### 6. Visualizations
Inside the  "Visualizations" folder, the notebook ------ contains the code to visualize the results. The checkpoints saved during the downstream classification and robustness check are utilized in this step.

## Note
Please feel free to contact me at yasar.mehmood111@gmail.com in case you encounter any problem while running the experiments.

## License
Released under the [CC BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/2.0/) license.
