# Conv_family  
This repository is task for comparison about Conv, Separable Conv, Group Conv using image classification

## Normal Convolution  
Params: k^2 * ic * oc + oc  
![img](https://github.com/kongbuhaja/Conv_family/assets/42567320/72973b60-503a-4fcb-9d6c-f2b37dd8525d)  


## Depthwise Convolution  
Params: k^2 * ic + ic  
![image](https://github.com/kongbuhaja/Conv_family/assets/42567320/c475aa0b-235b-4c48-bdd0-7c64f43b99f4)  

## Pointwise Convolution  
Params: ic * oc  
![image](https://github.com/kongbuhaja/Conv_family/assets/42567320/0ac4ad0a-4212-4811-b71c-5aa840e5ce89)  

## Separable Convolution (depthwise + pointwise)  
Params: k^2 * ic + ic * oc + oc  
![image](https://github.com/kongbuhaja/Conv_family/assets/42567320/8c54d243-84ed-4130-b5c4-67f133eefa0f)  

## Group Convolution  
Params: (k^2 * ic * oc)//g + oc  
![image](https://github.com/kongbuhaja/Conv_family/assets/42567320/634b43e9-e898-4d0e-90bc-be84033522d8)  

## Experiments
Model is based on ResNet18  

| **MNIST x 3c** | Size | ACC | Time |     
| ------------- | :---: | :------: | :------: |
| **Normal**  | 102.86KB | 98.00% | 0.1057s |  
| **Separable**  | 23.61KB(-77%) | 96.67%(-1.36%) | 0.0614s(-41.9%) |  
| **Group22**  | 16.85KB(-83%) | 96.32%(-1.71%) | 0.1349s(+27.6%) |  

| **CIFAR100 x 60c** | Size | ACC | Time |     
| ------------- | :---: | :------: | :------: |
| **Normal**  | 37.71MB | 59.10% | 0.0684s |  
| **Separable**  | 5.05MB(-86.6%) | 54.17%(-8.34%) | 0.0442s(-35.4%) |  
| **Group22**  | 0.49MB(-98.7%) | 39.92%(-32.4%) | 0.0555s(-18.9%) |  
