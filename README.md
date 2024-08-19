# ViT-Implementation

Implemented a Vision Transformer from famous paper 'An Image is Worth 16x16 Images'. Implemented the Attention and Multi-Head Attention mechanisms from scratch in PyTorch.

This is a simplified PyTorch implementation of the paper [An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale](https://arxiv.org/abs/2010.11929). The goal of this project is to provide a simple and easy-to-understand implementation. The code is not optimized for speed and is not intended to be used for production.

Check out [this post](https://medium.com/towards-data-science/implementing-vision-transformer-vit-from-scratch-3e192c6155f0) for step-by-step guide on implementing ViT in detail.

## Usage

Dependencies:
- PyTorch 1.13.1 ([install instructions](https://pytorch.org/get-started/locally/))
- torchvision 0.14.1 ([install instructions](https://pytorch.org/get-started/locally/))
- matplotlib 3.7.1 to generate plots for model inspection


## Results

The model was trained on the CIFAR-10 dataset for 100 epochs with a batch size of 256. The learning rate was set to 0.01 and no learning rate schedule was used. The model config was used to train the model:


The model is much smaller than the original ViT models from the paper (which has at least 12 layers and hidden size of 768) as I just want to illustrate how the model works rather than achieving state-of-the-art performance.

These are some results of the model:

![](/assets/metrics.png)
*Train loss, test loss and accuracy of the model during training.*

The model was able to achieve 75.5% accuracy on the test set after 100 epochs of training.

![](/assets/attention.png)
*Attention maps of the model for different test images*

You can see that the model's attentions are able to capture the objects from different classes pretty well. It learned to focus on the objects and ignore the background.

These visualizations are generated using the notebook `inspect.ipynb`.


