# Group Dropout

**Authors**: Yossi Elias, Roee Tal, Noamya Shani

**Led by:** Dr. Assaf Hoogi

## Project Goal
The goal of this project is to improve the dropout regularization technique used in neural networks (NN). Dropout is commonly used to prevent overfitting and enhance generalization in NN models. However, one limitation of dropout is its random nature, which can result in the dropout of important or influential neurons. This randomness can hinder the network's performance and its ability to learn complex patterns or capture critical information. 

The objective of our project is to develop a better implementation of dropout, introducing a novel technique called Group Dropout. Group Dropout involves selectively dropping out groups of neurons while keeping other groups active for specific classes. By doing so, we aim to improve the network's capacity to learn class-specific features and enhance its discrimination capabilities.

## Alternatives and Selected Approach
We explored different approaches to enhance dropout in neural networks. One option was to assign importance ratings to each neuron and drop the least important ones. Another approach involved selectively dropping neurons within groups for each class. After careful consideration, we chose to implement Group Dropout by entirely deactivating all neurons except the ones associated with the specific class. In making this decision, we drew inspiration from the concept of [Group Normalization](https://arxiv.org/pdf/1803.08494.pdf).

## Solution Description
To implement Group Dropout, we modified the dropout layer of a widely used neural network architecture designed for the CIFAR-10 dataset. This architecture already incorporated dropout, and we extended it with our Group Dropout technique. The CIFAR-10 dataset consists of ten classes, so we divided the neurons within the dropout layer into ten groups, each corresponding to one class.

During training, for each class, we deactivated with a specific probability all neurons in the dropout layer except the neuron associated with that specific class. For example, for class 0, we deactivated with a specific probability all neurons except the first 1/10 of the neurons within the dropout layer. This approach allows the neural network to focus on the relevant and informative neurons for each class, enabling the learning of distinct representations for each class.

By implementing Group Dropout, we aim to enhance the network's ability to capture class-specific features, resulting in improved classification performance and better utilization of the network's capacity. Group Dropout offers a more tailored and effective dropout strategy, contributing to enhanced learning and discrimination across different classes in the CIFAR-10 dataset.


