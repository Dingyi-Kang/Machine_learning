[logo]: https://github.com/AladdinPerzon/Machine-Learning-Collection/blob/master/ML/others/logo/youtube_logo.png


# Machine_learning

- [Basic](basic/)
  * [Basic concepts](basic/basic.md)
  * [Overfitting](basic/overfitting.md)
  * [Choosing parameter -- cross validation](basic/crossValidation.md)
  * [Supervised learning and upsupervised learning](basic/supervisedLearningUnsupervisedLearning.md)
  * [Linear algebra basic](basic/linearAlgebra.md)
  * [Linear Classifier](basic/classifier.md)
  * [How to get matrix inverse] (basic/inverseMatrix)
  * [What is batch vs epoch and the trade-off when choosing size of batch size](basic/batch.md)
  * [Cosine similarity](basic/cosineSimilarity.md)
- [Feature Engineering](feature/)
  * [Why normalize/standarlize predict feature can be important as well when loss function is MAS (espeically for RNN)](feature/standarlize.md)
- [Linear Regression](linearReg/)
  * [Intro to Linear Regression](basic/linearRegression.md)
  * [Minimize cost function -- gradient descrent](linearReg/gradientDescrent.md)
  * [How to derive the Normal Equation](basic/deriveNormalEquation.md)
  * [Matrix calculus and Normal Equation](basic/matrixCalculus.md)
  * [Polynominal and basis functions](linearReg/basisFunctions.md)
  * [Locally weighted Linear Regression](linearReg/localWeighted.md)
  * [Regularized Least Squares, aka. Regulaeized Linear Regression](linearReg/regulaized.md)
  * [Bias-Variance Tradeoff](linearReg/bias-variance.md)
  * [Bayesian Model Comparison/Selection](linearReg/bayesian.md)
- [Matrix Calculus, Derivative and Backpropagation](mathDeriv/)
  * [Matrix derivative of linear combination layer and activation "layer"](mathDeriv/matrixDerivative.md)
  * [Derivative of cross entropy and softmax](mathDeriv/crossE.md)
  * [Derivative of sigmoid and tanh](mathDeriv/tanh.md)
  * [Derivative of Mean Absolute Error](mathDeriv/MAE.md)
- [Neural Networks](neuralNetworks/)
  * [Chain rule](neuralNetworks/ChainRule.md)
  * [Excellent tutorial of Gradient Descent](neuralNetworks/GradientDescent.md)
  * [Backpropagation](neuralNetworks/backPropagation.md)
- [Midterm Review](review.md)
  * [Review 1](review.md)
  * [Review 2](review2.md)
- [Deep Learning](DL/)
  * [Transformer](DL/transformer.md)
  * [OOM Issue](DL/OOM.md)
- [RNN](RNN/)
  * [Build RNN from scratch with numpy](RNN/scracthNumpy.md)
  * [Build RNN from scratch with pyTorh nn and optim](RNN/scracthPytorch.md)
  * [Gradient Clipping](RNN/gradientClipping.md)
  * [Build LSTM cell from scratch with pytorch](RNN/lstmCell.md)
  * [Back propagate the gradients](RNN/backPropagation.md)
  * [Back truncate]
  * [LSTM -- clearly explained](https://www.youtube.com/watch?v=YCzL96nL7j0)
- [CNN](CNN/)
  * [Apply same CNN to a sequential data -- TimeDistributed layer](CNN/timeDistributed.md)
- [Natural Language Processing](NLP/)
  * [Word embedding](NLP/wordEmbedding.md)
  * [Another good tutorial using concrete examples explain word2Vec/word embedding](https://www.youtube.com/watch?v=hQwFeIupNP0)
  * [Sequence to sequence -- multiple LSTM cells, Stacked LSTM, context vector, encoder, decoder, tearching forcing](NLP/seq2Seq.md)
  * [Attention](NLP/attention.md)
- [Reinforcement Learning](RL/)
  * [What is RL](RL/whatIsRL.md)
  * [Policy: deterministic vs. stochastic](RL/differentPolicy.md)
  * [DPG and DDPG](RL/DPG_DDPG.md)
  * [Continuous action domains/space](RL/continuousActions.md)
  * [Value-based vs policy-based](RL/valueVsPloicy.md)
  * [Actor-Critic method -- the combination of the both value-based and policy based](RL/actor-critic.md)
  * [Proximal Policy Optimization -- PPO](RL/PPO.md)
  * [Algorithm can be used for just discrete action, continuous actions, and both](RL/table.md)
  * [Types of OpenAI Gym Spaces](RL/space.md)
  * [Great intro tutorial to RL (using API of stable-baseline3) -- clearly explained different notions of OpenAI gym](RL/valueBased.md)
  * [Deep Q learning](RL/deepQ.md)
- [PyTorch](PyTorch/)
  * [How to install PyTorch supporting GPU in Conda](PyTorch/config.md)
  * [Excellent tutorials on writing backpropobation code in different customed level using Pytorch](PyTorch/backPro.md)
  * [How to reshape or add additional dimention -- unsqueeze()](PyTorch/reshape.md)
  * [Transpose a matrix](PyTorch/transpose.md)
  * [Different ways of matrix multiplication](PyTorch/mul.md)
  * [Hamilton product -- element by element product](PyTorch/hamilton.md)
  * [Outer product](PyTorch/outer.md)
- [Tensor Flow](tf/)
  * [TF1 : Link to Standfor CS20 Deep Learning with Tensorflow course](http://web.stanford.edu/class/cs20si/syllabus.html)
  * [TF1: Graph and session](tf/graphSession.md)
  * [TF1: Constant, variable, operation and placeholder](tf/basic.md)
  * [tf.function](tf/tfFunction.md)
  * [TensorFlow Tutorial](https://www.youtube.com/watch?v=5Ym-dOS9ssA&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb)
  * [Tutorial1: Basic: tensor, oprations, indexing, reshaping](tf/tutorial_basic.md)
  * [![Youtube Link][logo]](https://youtu.be/pAhPiF3yiXI) &nbsp; [Tutorial 2 - Sequential vs functional model, sparseCategoryCrossEntropy](tf/models.md)
  * [![Youtube Link][logo]](https://www.youtube.com/watch?v=WAciKiDP2bo&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb&index=4) &nbsp; [Tutorial 3 - CNN using Sequential and functional model -- using BatchNormalization](tf/CNN.md)
  * [![Youtube Link][logo]](https://www.youtube.com/watch?v=kJSUq1PLmWg&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb&index=5) &nbsp; [Tutorial 4 - Regularization-- L2, dropout, and BatchNormalization](tf/regularization1.md) 
  * [![Youtube Link][logo]](https://www.youtube.com/watch?v=Ogvd787uJO8&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb&index=6) &nbsp; [Tutorial 5 - Using RNN and bidirectionLSTM in vision](tf/RNN.md)
  * [![Youtube Link][logo]](https://www.youtube.com/watch?v=gRRGr_tJnAA&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb&index=7) &nbsp; [Tutorial 6 - A bi-labels example using functional model](tf/functionalModel.md)
  * [![Youtube Link][logo]](https://www.youtube.com/watch?v=WcZ_1IAH_nM&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb&index=8) &nbsp; [Tutorial 7 -The power of model subclass -- implementing a ResNet-like network](tf/subclassModel.md)
  * [![Youtube Link][logo]](https://www.youtube.com/watch?v=cKMJDkWSDnY&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb&index=9) &nbsp; [Tutorial 8 - build custom layers](tf/customLayers.md)
  * [![Youtube Link][logo]](https://www.youtube.com/watch?v=idus3KO6Wic&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb&index=10) &nbsp; [Tutorial 9 - save and load weights vs save and load entire model](tf/saveLoad.md)
  * [![Youtube Link][logo]](https://www.youtube.com/watch?v=WJZoywOG1cs&list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb&index=11) &nbsp; [Tutorial 10 - pretrain and finetuning -- looking for pretained models in TF Hub](tf/pretrain.md)
  
  * [Deep Learning with TensorFlow Tutorial with more application practice](https://www.youtube.com/watch?v=Mubj_fqiAv8&list=PLeo1K3hjS3uu7CxAacxVndI4bE_o3BDtO)
 
- [Python and Numpy](Numpy/)
  * [asmatrix](Numpy/asmatrix.md)
  * [Advanced indexing in numpy](Numpy/indexing.md)
  * [Element-by-element multiplication (Hamilton product) is different from dot product](Numpy/hamilton.md)
  * [zip](Numpy/zip.md)
  * [tf.concat(, axis=0)](Numpy/concat.md)
  
- [Remote Server](server/)
  * [Anaconda](server/conda.md)
  * [Tmux](server/mutex.md)
  * [Screen]
