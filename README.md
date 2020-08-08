# DL-Model-pruning

- > Pruning is a technique of reducing Model size for making it memory efficient without loosing the accuracy of the actual model.

- > Pruning is required as models are getting very large , they becomes a problem while deploying process.

- > I have performed some approaches for pruning my model and compared their results on the basis of
     
     Accuracy ,
     
     Size of the model without Zipping it ,
     
     Size of the model after zipping and
     
     Time taken for evaluation(Inference time).

[ Dataset used is Cifar-10 Dataset ]

[ Method 1 ] - Using Tensorflow Optimization Kit

 = > Model is pruned and stripped for compressing the size of the model.(Results are shown in jupyter Notebook )
 = > First approach - Pruning the whole network model to 80% Sparsity.
 = > Second approach - Pruning only Dense layers of the Network Model.

[Method 2] - Weight Pruning - Using Rankdata()

 = > Rank the weights in weight matrix of every layer according to their Magnitude and setting the lowest n% to Zero. (here i have taken n == 20% ,because we are doing it in every layer and also my model is not that big so it can loose knowledge and accuracy can be lost with higher value)
 
[Method 3] - Neuron Pruning - L2 norm

= > Calculating L2 norm of every column of the weight matrix and replacing smallest n% to Zero. (here i  have gone till n=40% of sparsity )
= > Sparsing should be done in steps otherwise it will damage the model accuracy.


“After that I have Compared all the results i got from different approaches and also visualized those comparison with respect to effect on accuracy , Sizes and Inference time.”

##Reference

https://www.tensorflow.org/model_optimization/guide/pruning/pruning_with_keras

https://towardsdatascience.com/pruning-deep-neural-network-56cae1ec5505
