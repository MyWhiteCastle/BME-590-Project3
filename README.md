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
- train, save and load pretrained weights [densenet_100_12_pretrained.h5](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/densenet_100_12_pretrained.h5) 

## Results
Results on direct pruning on the pretrained model [all checkpoints are saved here](https://github.com/MyWhiteCastle/BME-590-Project3/tree/master/direct%20pruning%20checkpoints)<br>
![direct pruning](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/results/Direct%20Pruning%20corrected.png "direct pruning")

Results on iterative pruning on the pretrained model [all checkpoints are saved here](https://github.com/MyWhiteCastle/BME-590-Project3/tree/master/iterative%20pruning%20checkpoints) <br>
![iterative pruning](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/results/Iterative%20Pruning.png "iterative pruning")

Results on model compression rate after applying iterative pruning and quantization on the pretrained model
![compression rate table](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/results/compression_rate_table.png "compression rate table")
