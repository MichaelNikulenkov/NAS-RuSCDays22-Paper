# Regularization approach for accelerating Neural Architecture Search
Russian Supercomputing Days 2022 paper. This article introduces a new method that can improve convergence in NEAT-based NAS method using L1/L2 regularization during the evolution step.

# Reason behind research
Modern Artificial Neural networks utilizes vast topologies to become applicable to the vast majority of the ML problems. Such topologies have an enormous number of parameters nowadays, which make it easier to use, but harder to train and modify. With such a number of parameters, the usage of semi-automatic tools for building or adapting new models for new problems is vital for the whole industry. It makes it essential to optimize such methods like Neural Architecture Search (NAS) to efficiently utilize computational resources of the GPU and whole cluster. 

# Results
We developed and implemented a new type of optimization for Neuroevolution techniques that enables us to reduce the demands of computational power. The proposed technique utilizes L1 regularization for model simplification and distributing loss through this simplified model. 
- In the terms of power reduction, it leads to the more than 1.9 speedup in average Tab. 1. In some complex image classification tasks it grows better than some small one like MNIST. Such an effect can be explained by different search spaces and complexity of the resulting networks (in MNIST/CIFAR-10 the resulting networks have much less graph nodes and types of nodes than in Tiny ImageNet). 
- Such an approach was analyzed via parallel experiments on Polus clusters and in image classification problems we obtained not only negligible results in the terms of accuracy degradation, but also significant in the terms of FLOPS/iteration. 
- At some points like in Tiny ImageNet and CIFAR-100, the overall accuracy degradation is negative it means the resulting networks is better after augmentation than original one.

Paper: https://github.com/MichaelNikulenkov/NAS-RuSCDays22-Paper/blob/main/paper.pdf
