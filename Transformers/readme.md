### Transformer A High-Level Look
 
                     
   <img src="./docs_assets/t.png" width="440" height="240"/> 
                       
The transformer block contain encoding component, a decoding component as depicted below

   <img src="./docs_assets/t2.png" width="440" height="240"/> 
                     
The encoding component is a stack of encoders (the paper stacks six of them on top of each other as per official paper). The decoding component is a stack of decoders of the same number.

   <img src="./docs_assets/t3.png" width="440" height="240"/> 
   
All Encoders are identical in structure .Each encoder in broken in two layers 1. Feed forward Neural Network 2. Attention layer

   <img src="./docs_assets/t4.png" width="440" height="240"/> 
   
The input is given to the encoder self attention layer and output of self attention layer is fed to the feed forward neural network .The exact feed forward neural network is applied to each position(each word in sentence)

The Decoder has both the encoder layers but it has encoder-decoder attention layer in between . which helps the decoder to focus on relevent parts of the input sentence  

  <img src="./docs_assets/t5.png" width="440" height="240"/> 


Each sentence as a input conveted in to vector for using word embedding algorithms and the given as list of vectors each of the size 512 inputs to the Attention layer of encoder .The size of this list is hyperparameter we can set – basically it would be the length of the longest sentence in our training dataset.

After embeding words in squence(vector) each of them flows through each of the two layers of the encoder.

One key property of the Transformer, which is that the word in each position flows through its own path in the encoder. There are dependencies between these paths in the self-attention layer. The feed-forward layer does not have those dependencies, however, and thus the various paths can be executed in parallel while flowing through the feed-forward layer.

As we’ve mentioned already, an encoder receives a list of vectors as input. It processes this list by passing these vectors into a ‘self-attention’ layer, then into a feed-forward neural network, then sends out the output upwards to the next encoder.

   <img src="./docs_assets/t6.png" width="440" height="240"/> 
   
   
   
  # Self-Attention
