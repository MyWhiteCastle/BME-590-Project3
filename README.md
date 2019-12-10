# Light Implementation on Model Compression 
- Duke BME-590-Biomedical Machine Learning Final Project
- A practice to understand the effect of model compression under keras/tensorflow environment
- Original paper: DEEP COMPRESSION: COMPRESSING DEEP NEURAL NETWORKS WITH PRUNING, TRAINED QUANTIZATION AND HUFFMAN CODING
 [git repo](https://github.com/songhan/Deep-Compression-AlexNet/blob/master)

## Experiemental Setting
DenseNet100-12 from scratch <br>
- number of convolutional layers: 100 <br>
- growth rate = 12  <br>
- used on Cifar10, Cifar100 and SVHN datasets [git repo on densenet](https://github.com/liuzhuang13/DenseNet/blob/master)
- implemented using keras
- pretrained weights 

## Results
Results on direct pruning on the pretrained model <br>
![alt text] (https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/results/Direct%20Pruning%20corrected.png)



