# Try to understand the algorithm, usage and implementation
<img width="729" alt="image" src="https://user-images.githubusercontent.com/81428296/188335849-b103b3c7-411f-4ed4-b4d9-54f5363c513d.png">
<img width="991" alt="image" src="https://user-images.githubusercontent.com/81428296/188335855-b7bfd4a7-2b96-4afe-b14c-79b134adc305.png">

# What is machine leanring?
<img width="1817" alt="image" src="https://user-images.githubusercontent.com/81428296/188335983-beffab20-1469-45f5-892e-ce91fa38730b.png">

# ML vocabulary
<img width="1608" alt="image" src="https://user-images.githubusercontent.com/81428296/188336155-58b78f76-5814-4476-9ca9-15c193a4943b.png">
<img width="1644" alt="image" src="https://user-images.githubusercontent.com/81428296/188336172-735b0bec-b443-4e78-be78-4b9f57a6b53e.png">
<img width="1782" alt="image" src="https://user-images.githubusercontent.com/81428296/188336204-0b6d3526-de50-478f-99e8-f134949107ab.png">

# Choose parameter
<img width="1775" alt="image" src="https://user-images.githubusercontent.com/81428296/188337886-621a0ed8-2008-4dec-beb8-c10946d6ac56.png">
## while trainning set is used to adjust the weights of features/neural networks,

## Validation set is used to pick the best parameters or the best model to use. For example, you create 3 different models with different parameters, you choose the one working best on the validation set

## while testing set is only used to know how accurate your model is. You cannot use trainning set to measure accuracy/performance since your model might have memorized some training data. Also, you cannot use validation set since you choose the model based on its performance on validation data which creates model bias. You cannot know if the chanaging parameter in this chosed model is the right move or the model just perform better in the validation set. If the performance on validation set is way different the actual performance on testing set, you should start over from scratch.     
<img width="1269" alt="image" src="https://user-images.githubusercontent.com/81428296/188355856-4d346035-6c5f-4b70-8f16-f05f5299fecd.png">
