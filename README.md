# Light Implementation on Model Compression 
- Duke BME-590-02 Biomedical Machine Learning Final Project
- A practice to understand the effect of model compression under keras/tensorflow environment
- Original paper: DEEP COMPRESSION: COMPRESSING DEEP NEURAL NETWORKS WITH PRUNING, TRAINED QUANTIZATION AND HUFFMAN CODING
 [click here](https://github.com/songhan/Deep-Compression-AlexNet/blob/master)
- In BME_Project_3_Model_Compression.ipynb [click here](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/BME_Project_3_Model_Compression.ipynb), 3-stage model compression pipeline is implemented 
   1. pruning 
   2. quantization 
   3. huffman coding 


## Experiemental Setting
DenseNet100-12 from scratch <br>
- number of convolutional layers: 100 <br>
- growth rate = 12  <br>
- used on Cifar10, Cifar100 and SVHN datasets [click here to see densenet official git repo](https://github.com/liuzhuang13/DenseNet/blob/master)
- implemented using keras
- train, save and load pretrained weights [densenet_100_12_pretrained.h5](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/densenet_100_12_pretrained.h5) 

## Results
Results on direct pruning on the pretrained model [all checkpoints are saved here](https://github.com/MyWhiteCastle/BME-590-Project3/tree/master/direct%20pruning%20checkpoints)<br>
![direct pruning](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/results/Direct%20Pruning%20corrected.png "direct pruning")

Results on iterative pruning on the pretrained model [all checkpoints are saved here](https://github.com/MyWhiteCastle/BME-590-Project3/tree/master/iterative%20pruning%20checkpoints) <br>
![iterative pruning](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/results/Iterative%20Pruning.png "iterative pruning")

Results on model compression rate after applying iterative pruning and quantization on the pretrained model
![compression rate table](https://github.com/MyWhiteCastle/BME-590-Project3/blob/master/results/compression_rate_table.png "compression rate table")

## Highlights
The results show that iteraitve pruning helps to slim the model while keep the model performance. For example, the pruned model with 70% sparsity can achieve 68% accuracy. The hyperparameters (epochs, learning rate, etc.) in the experiment are set the same for all sparsity levels. However, one can always tune those hyperparameters based on the sparsity level accordingly.

Direct pruning hurts the model performance but if retraining (i.e., fine-tuning) could be applied afterwards (only update the non-zero weights), the model performance evaluated in accuracy here will recover according to the paper. 

As there is concern that the pruned model might have difficulty recovering from direct pruning, iterative pruning is commonly applied in real cases. Here tensorflow provides us with a ready-to-go package Magnitude-based weight pruning with Keras ([click here](https://www.tensorflow.org/model_optimization/guide/pruning/pruning_with_keras?authuser=1)) so that we can use directly to practice iterative pruning but with the caution that it is only compatible with tf 1.x version. 

Quantization preserves the model performance using a technique called weight sharing. Weight sharing is implemented by K-means algorithm using sklearn package. Huffman coding will not affect the model performance and it is coded for each layer in the .ipynb file. 

## Thanks
Duke ECE 590-10 Yiran Chen and Hai Li Lecture 13 slides on Model Compression <br>
Duke BME 590-02 Ouwen Huang and Xiling Shen <br>
