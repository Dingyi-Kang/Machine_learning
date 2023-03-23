by default, pyTorch support CPU only will be installed.


In order to enable GPU, need to install Cudnn and cudatoolkit first. The article below is about enabling TensorFlow using GPU. But the pre-steps are common and intro to concepts of CUDA is good.

https://medium.com/analytics-vidhya/solution-to-tensorflow-2-not-using-gpu-119fb3e04daa

Besides, you may need to remove privous pytorch before you install the new one supporting GPU

What's more, the most updatest version may not be supported for your environment. In my case, installing the previous version works for me. Please refer to this website.

https://pytorch.org/get-started/previous-versions/


I use this one
<img width="1066" alt="image" src="https://user-images.githubusercontent.com/81428296/227381896-3526f988-7a59-43df-b103-430c2cb2a093.png">


And the result of pytorch config is:

<img width="600" alt="image" src="https://user-images.githubusercontent.com/81428296/227382197-5abaeaf4-0f87-4368-a02d-eef3d233377b.png">


