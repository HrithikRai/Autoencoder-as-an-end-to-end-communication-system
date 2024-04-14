# Autoencoder-as-an-end-to-end-communication-system
![](images/autoencoder.png)
#### Project summarized below, for detailed description alongwith theoritical background refer [here](autoencoder_project_description.pdf)
In this project, we train an autoencoder for information transmission over an end-to-end communication system, where the encoder will  replace the transmitter tasks such as modulation and coding along with adding redundancy and  the decoder will replace the receiver tasks such as demodulation and decoding. In the end we will compare our Autoencoder’s performance with different Modulation schemes like QPSK and 8PSK.
![](images/autoencoder_design.png)

The goal of a communication system is to deliver a certain message (text, audio, image, 
video, etc.) to the destination over a noisy physical channel (copper wire, optical fiber, EM wave 
radiation, etc.). Digital communication systems are communication systems that use digital 
sequence (typically binary digits, that is, bits) as an interface between the source coding part 
and the channel coding part. 

When handling the complexity of optimization for new wireless applications with high 
degrees of freedom, these systems often fail. The reason being their probabilistic approaches to 
infer the source message. Deep learning displays a promising potential when it comes to 
addressing this challenge via data-driven solutions. 

Instead of traversing through a rigid pre-planned design, new generations of wireless 
systems empowered by deep learning can learn from data and optimize their performance. 
These smart communication systems take aid from several trivial machine learning tasks like 
detection, classification, and prediction.

## Objectives: 

1. To train an Autoencoder for Information Transmission at different hyperparameter tunings 
and represent it as a standalone end-to-end communication system.
2. To build the parts of the Autoencoder such that they replace the components of a
conventional communication system.
3. Performing Hyperparameter tuning to ensure optimal reconstruction of outputs.
4. Comparing the performance of the autoencoder with different Modulation Schemes.

# The following objectives are taken care of in the below code.

## Optimizers used for performance comparision - ADAM, Gradient Descent and RMSProp
![](images/code.png)

### Observations :

![](images/performance_table.png)
➢ The autoencoder’s BLER is lower than that of QPSK and 8PSK over the whole SNR range
with ADAM optimizer, while RMSprop was lower only in higher batch sizes, and 
Gradient Decent was the worst in all cases.

➢ It can be seen that optimizing the encoder and decoder together is how we can force 
the autoencoder to extract only the features that are necessary and characterize the 
input data to store it in the bottleneck layer (i.e., where the smaller and dense 
representations are).
16

➢ We have observed that instead of optimizing the individual blocks of a conventional 
communication system (i.e., synchronization, symbol estimation, error correction, 
channel coding, modulation, etc.) we can use the autoencoder's optimization for the 
reconstruction loss.

➢ Future works in the field might include channel generalization by scaling from a simple 
AWGN model to more complex real-world channels.

