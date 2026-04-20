# Fashion MNIST GAN — Generative Adversarial Network for Fashion Image Synthesis

- Student Name   : Temur Rustamov
- Student Number : C00280204
- Module         : Data Science & Machine Learning 2

# Diary:
This notebook primarily covers the following topics from the module:
- Chapter 5: Artificial Neural Networks (1, 2, 3)
  - I worked with The Generator and Discriminator are both deep neural networks built with Keras. From ANN concepts I worked with layers,
          activations, loss functions, backpropagation, and the Adam optimiser.
  - The custom training loop subclassed Model shows advanced ANN training
          beyond simple model.fit(), including manual gradient computation with
          tf.GradientTape.

- Chapter 6: Deep Learning — CNNs (Convolutional Neural Networks)
        - I worked with The Discriminator which is a CNN classifier (Conv2D layers extracting spatial
          features from images and classifying them as real or fake).

- Chapter 7: Generative Models
        - GANs are a key generative model paradigm. This implementation shows
          adversarial training where two networks compete. The generator learns to
          produce realistic images while the discriminator learns to distinguish
          real from fake. This extends beyond supervised learning into generative
          deep learning.


# Why TensorFlow / Keras?

1. TensorFlow is one of the two dominant deep learning
   frameworks (alongside PyTorch). It is backed by Google and widely used in
   both industry and academia.

2. TensorFlow includes Keras as its official high-level
   API. Keras provides the Sequential model API, which allows us to build neural
   networks.
3.  GANs require alternating training of two networks with
   different loss functions, which is not possible with a standard model.fit()
   call. TensorFlow's subclassed Model approach handles this elegantly.


# Why Fashion MNIST?

1. It is a drop in replacement for MNIST but is more challenging since it contains clothing items
    rather than handwritten digits.

2. It is a standard benchmark for generative models.

# Why a GAN architecture?

1. Two networks generator and discriminator are trained
   simultaneously in minmax.

2. The generator learns to produce new, images without explicit labels.

3. Both networks use convolutional layers showing CNNs
   in both classification and generation contexts.

# Key findings:
- The GAN successfully learned to generate fashion item images after 20 epochs of training on 60,000 grayscale images. 
- The generated outputs which is generated_grid.png shows bag/tote-like shapes with visible structural consistency so the model converged on a dominant mode rather than generating diverse clothing categories, which is a classic GAN behavior called mode collapse. 
- The images are blurry but structurally recognizable, which is expected for a simple DCGAN at 28×28 resolution.
- The training was healthy overall: discriminator loss settled near 0.7  and generator loss stabilized in the 0.5–0.6 range by the final epochs, indicating a reasonable adversarial balance.
# Dairy Logging:

## Loaded the dataset Date: 04/03
Loaded the Fashion MNIST training data.
Checked one sample image and label to confirm the dataset loaded correctly.

## Viewed sample images Date: 04/03
Displayed a few raw Fashion MNIST images.
This helped confirm the images were correct and suitable for training.

## Preprocessed the data Date: 04/03
Normalised image values from 0–255 to 0–1.
Removed labels because GAN training only needs images.
Result:
The dataset was prepared for neural network training.

## Built the data pipeline Date: 04/03

Used caching, shuffling, batching, prefetching for that.
Result:
Training data became faster and more efficient to use.

## Built the generator Date: 04/03
Created the generator model.
What it does?
It takes random noise and tries to create fake fashion images.

## Built the discriminator Date: 04/03
Created the discriminator model.
What it does?
It checks whether an image is real or fake.

## Checked model shapes Date: 08/03
Tested the generator and discriminator with sample input.
Result:
The generator produced images of the correct size, and the discriminator returned a single output for each image.

## Set loss functions and optimisers Date: 08/03
Used Adam optimiser and Binary Cross Entropy loss.
Result:
Both networks were ready for adversarial training.

## Built the GAN training loop Date: 08/03
Created a custom GAN class with a custom train_step().
What it does?
It trains the discriminator and generator one after the other in each batch.


## Trained the GAN Date: 09/03
Trained the GAN on Fashion MNIST.
Result:
The generator gradually learned to create fashion-like grayscale images.

## Reviewed & saved results Date: 09/03
Plotted discriminator loss and generator loss.
Generated a grid of sample images from the trained generator.
Saved the generator and discriminator models as .h5 files.
Result:
The output images showed that the model learned visual patterns from the dataset.

# References
1. Goodfellow, I. et al. (2014). Generative Adversarial Networks.
   arXiv:1406.2661. https://arxiv.org/abs/1406.2661

2. Radford, A., Metz, L. & Chintala, S. (2016). Unsupervised Representation
   Learning with Deep Convolutional Generative Adversarial Networks (DCGAN).
   arXiv:1511.06434. https://arxiv.org/abs/1511.06434

3. Salimans, T. et al. (2016). Improved Techniques for Training GANs.
   arXiv:1606.03498. https://arxiv.org/abs/1606.03498

4. Machine Learning Course from Andrew Ng
https://www.coursera.org/specializations/machine-learning-introduction?utm_medium=sem&utm_source=gg&utm_campaign=b2c_emea_machine-learning-introduction_stanford_ftcof_specializations_cx_dr_bau_gg_sem_pr_s1_en_m_hyb_23-12_x&campaignid=20858198833&adgroupid=160248022715&device=c&keyword=andrew%20ng%20machine%20learning%20certification&matchtype=p&network=g&devicemodel=&creativeid=724572967819&assetgroupid=&targetid=kwd-834934671809&extensionid=&placement=&gad_source=1&gad_campaignid=20858198833&gbraid=0AAAAADdKX6Zzp5Mu5xfEmcoT-Ks6jiJTX&gclid=CjwKCAjwspPOBhB9EiwATFbi5Op0GW-OvU1o49W_bQ_ePfWFn6LLgdf1rQP27S8t0cEpX7i0vkoFThoCr_4QAvD_BwE