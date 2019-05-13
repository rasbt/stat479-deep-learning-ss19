# STAT479: Deep Learning (Spring 2019)

**Instructor: Sebastian Raschka**

Lecture material for the STAT 479 Deep Learning course at University Wisconsin-Madison. For details, please see the course website at http://pages.stat.wisc.edu/~sraschka/teaching/stat479-ss2019/


## Course Calendar

Please see [http://pages.stat.wisc.edu/~sraschka/teaching/stat479-ss2019/#calendar](http://pages.stat.wisc.edu/~sraschka/teaching/stat479-ss2019/#calendar).

## Topic Outline

- History of neural networks and what makes deep learning different from “classic machine learning”
- Introduction to the concept of neural networks by connecting it to familiar concepts such as logistic regression and multinomial logistic regression (which can be seen as special cases: single-layer neural nets)
- Modeling and deriving non-convex loss function through computation graphs
- Introduction to automatic differentiation and PyTorch for efficient data manipulation using GPUs
- Convolutional neural networks for image analysis
- 1D convolutions for sequence analysis
- Sequence analysis with recurrent neural networks
- Generative models to sample from input distributions
  - Autoencoders
  - Variational autoencoders
  - Generative Adversarial Networks


## Material

- **L01: What are Machine Learning and Deep Learning? An Overview.** [[Slides](L01-intro/L01-intro_slides.pdf)]
- **L02: A Brief Summary of the History of Neural Networks and Deep Learning.** [[Slides](L02_dl-history/L02_dl-history_slides.pdf)]
- **L03: The Perceptron.** [[Slides](L03_perceptron/L03_perceptron_slides.pdf)] [[Code](L03_perceptron/code)]
- **L04: Linear Algebra for Deep Learning.** [[Slides](L04_linalg-dl/L04_linalg-dl_slides.pdf)]
- **L05: Fitting Neurons with Gradient Descent.** [[Slides](L05_grad-descent/L05_gradient-descent_slides.pdf)]  [[Code](L05_grad-descent/code)]
- **L06: Automatic Differentiation with PyTorch.** [[Slides](L06_pytorch/L06_pytorch_slides.pdf)]  [[Code](L06_pytorch/code)]
- **L07: Cloud Computing.** [[Slides](L07_cloud-computing/L07_cloud-computing_slides.pdf)] 
- **L08: Logistic Regression and Multi-class Classification** [[Slides](L08_logistic/L08_logistic_slides.pdf)] [[Code](L08_logistic/code)] 
- **L09: Multilayer Perceptrons** [[Slides](L09_mlp/L09_mlp_slides.pdf)]  [[Code](L09_mlp/code)] 
- **L10: Regularization** [[Slides](L10_regularization/L10_regularization_slides.pdf)]  [[Code](L10_regularization/code)] 
- **L11: Normalization and Weight Initialization** [[Slides](L11_weight-init/L11_weight-init_slides.pdf)] 
- **L12: Learning Rates and Optimization Algorithms** [[Slides](L12_optim/L12_optim_slides.pdf)] 
- **L13: Introduction to Convolutional Neural Networks** [[Slides (part 1)](L13_intro-cnn/L13_intro-cnn-part1_slides.pdf)] [[Slides (part 2)](L13_intro-cnn/L13_intro-cnn-part2_slides.pdf)]  [[Slides (part 3)](L13_intro-cnn/L13_intro-cnn-part3_slides.pdf)] 
- **L14: Introduction to Recurrent Neural Networks** [[Slides (part 1)](L14_intro-rnn/L14_intro-rnn-part1_slides.pdf) [Slides (part 2)](L14_intro-rnn/L14_intro-rnn-part2_slides.pdf)] [[Code](L14_intro-rnn/code)]
- **L15: Introduction to Autoencoders** [[Slides](L15_autoencoder/L15_autoencoder_slides.pdf)] [[Code](L15_autoencoder/code)]
- **L16: Variational Autoencoders** (skipped due to timing constraints)
- **L17: Generative Adversarial Networks** [[Slides](L17_gans/L17_gan_slides.pdf)] [[Code](L17_gans/code)]

<br>
<br>

#### Project Presentation Awards

Without exception, we had amazing project presentations this semester. Nonetheles, we have some winners the top 5 project presentations for each of the 3 categories, 
as determined by voting among the ~65 students:


**Best Oral Presentation:**

1. Saisharan Chimbiki, Grant Dakovich, Nick Vander Heyden (Creating Tweets inspired by Deepak Chopra), average score: 8.417

2. Josh Duchniak, Drew Huang, Jordan Vonderwell (Predicting Blog Authors’ Age and Gender), average score: 7.663

3. Sam Berglin, Jiahui Jiang, Zheming Lian (CNNs for 3D Image Classification), average score: 7.595

4. Christina Gregis, Wengie Wang, Yezhou Li (Music Genre Classification Based on Lyrics), average score: 7.588

5. Ping Yu, Ke Chen, Runfeng Yong (NLP on Amazon Fine Food Reviews) average score: 7.525



**Most Creative Project:**

1. Saisharan Chimbiki, Grant Dakovich, Nick Vander Heyden (Creating Tweets inspired by Deepak Chopra), average score: 8.313

2. Yien Xu, Boyang Wei, Jiongyi Cao (Judging a Book by its Cover: A Modern Approach), average score: 7.952

3. Xueqian Zhang, Yuhan Meng, Yuchen Zeng (Handwritten Math Symbol Recognization), average score: 7.919 

4. Jinhyung Ahn, Jiawen Chen, Lu Li (Diagnosing Plant Diseases from Images for Improving Agricultural Food Production), average score: 7.917

5. Poet Larsen, Reng Chiz Der, Noah Haselow (Convolutional Neural Networks for Audio Recognition), average score: 7.854



**Best Visualizations:**

1. Ping Yu, Ke Chen, Runfeng Yong (NLP on Amazon Fine Food Reviews), average score: 8.189

2. Xueqian Zhang, Yuhan Meng, Yuchen Zeng (Handwritten Math Symbol Recognization), average score: 8.153

3. Saisharan Chimbiki, Grant Dakovich, Nick Vander Heyden (Creating Tweets inspired by Deepak Chopra), average score: 7.677

4. Poet Larsen, Reng Chiz Der, Noah Haselow (Convolutional Neural Networks for Audio Recognition), average score: 7.656

5. Yien Xu, Boyang Wei, Jiongyi Cao (Judging a Book by its Cover: A Modern Approach), average score: 7.490