## Hyperparametertuning_Pytorch

This repository contains code to perform some of the data augmentation mentioned in the [Bag of Tricks for Image Classification with Convolutional Neural Networks](https://arxiv.org/abs/1812.01187).The augementation performed are:

* Learning Rate warmup
* Fp16
* Mixup 
* Zero Gamma
* No bias Decay

The dataset chosen are [Imagenette](https://s3.amazonaws.com/fast-ai-imageclas/imagenette2.tgz) and [Imagewoof2](https://s3.amazonaws.com/fast-ai-imageclas/imagewoof2.tgz) which are a subset of Imagenet Dataset.The two known architecture Resnet50 and Mobilenet_v2 were chosen to carry out the described Data augmentation.

The framework used for implementation is [Pytorch](https://pytorch.org/) and we used the freely available platform Google Colab to produce the results using its GPU for computation.



## Results:



## Instructions to Run the code:

1.Open Google Collaboratory and in the upload notebook section  ,select Github and use the following [URl](https://github.com/NNFLgroup31/Resnet50-Hyperparametertuning).

2.Select the Data Augmentation method you want to refer depicted by file name.

3.Go to Change runtime type and select GPU.

4.(Optional)Enter the Model name and modify the path of the file being saved as preferred.

5.Model Selection:
  
   * Resnet-50
  
  Uncomment: 
#model=torchvision.models.resnet50(pretrained=False)      #model.fc=nn.Linear(2048,10,bias=True)
  
   * Mobilenet_v2
  
  Uncomment: 
#model=torchvision.models.mobilenet_v2(pretrained=False) #model._modules['classifier']._modules['1']=nn.Linear(1280,10,bias=True)

6.Dataset Selection:
  
   * Imagnette2:
    Uncommment:
    !wget https://s3.amazonaws.com/fast-ai-imageclas/imagenette2.tgz
    !tar -xvzf  'imagenette2.tgz'
    
   * Imagewoof2:
     Uncomment:
     !wget https://s3.amazonaws.com/fast-ai-imageclas/imagewoof2.tgz
     !tar -xvzf  'imagewoof2.tgz' 
  
 7.Now you can run the program after doing the required changes.After every epoch Losses,Accuracy are saved along with Model,Optimizer   and Scheduler State.
 
 8.Sometimes Runtime gets disconnected,in order to restart from the last epoch use Checkpoint mentioned in the program and load the Model,Optimizer,Scheduler states.



   
      
    
