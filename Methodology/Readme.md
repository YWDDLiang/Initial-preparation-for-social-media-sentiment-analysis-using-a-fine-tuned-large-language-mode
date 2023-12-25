# This research uses the following steps:
- 1. Collecting the historical time-series data of the monetary value of Aave, and the tweets with specific hashtags.
- 2. Data processing to organize the data into the format required by the model used in this study.
- 3. A combination of the llama2 model, LoRA method, and Alpaca-LoRA is used to analyze the price movements of the virtual currency.

Therefore, this study will first introduce the llama2 model, LoRA method, and Alpaca-LoRA, including the mathematical principles and advantages of using them. This study will also demonstrate the feasibility and innovativeness of this study by analyzing other literature and research in the field of virtual currency price analysis and prediction.

# llama2 model
The llama2 model is a model based on Google's transformer architecture, a self-attentive mechanism that is able to process input sequences while taking into account information from the global context, rather than relying solely on the local context. This property allows Llama2 to understand and generate complex linguistic structures and to perform better in natural language processing.
## Transformer architecture (Vaswani et al. 2017):
The architecture mainly contains the following features which ensure the advantages of the architecture when analyzing the global context.
1. Input Embeddings
- Position Encoding: Since the architecture does not have a loop structure to capture the positional information of the sequence, the architecture needs to add positional information to each input element through position encoding.
- Word Embeddings: maps each word in the input sequence to a high latitude vector space.
2. Multinomial Self-Attention Layer
- Self-attention mechanism: computes the context vector for each position of the input sequence, which in turn takes into account the information of the whole sequence. Attention weights are computed from three matrices: query, key and value, and these weights are weighted and averaged to generate a new representation.
- Multi-attention: In order to capture different contextual relationships, the self-attention mechanism is executed several times in parallel and the results are then stitched together.
3. Feed-Forward Neural Networks (FFNs):
- The output vector at each location passes through two linear layers with a nonlinear transformation between them using the ReLU activation function.
4. Residual Connections (RC):
- After each self-attention layer and feedforward neural network, a residual connection is added to help solve the problem of gradient vanishing in deep neural networks.
5. Layer Normalization:
- After the residual connections, a layer normalization operation is performed to stabilize the training process and accelerate convergence.
6. Encoder-Decoder structure:
- This architecture usually contains one or more encoder or decoder stacks. The encoder is responsible for extracting the semantic information of the input sequence and the decoder is used to generate the target sequence.
- All the layers of the encoder use the self-attention mechanism, while the first layer of the decoder uses the masked self-attention mechanism, which is designed to guarantee that the decoder cannot see future information, and the rest of the layers use the self-attention and the attention mechanism of the source sequence.
7. output Layer (Output Layer):
- The output of the decoder is passed through a linear layer and softmax function that generates a probability distribution of words for each position in the target sequence.

The advantage of the Transformer architecture is mainly the ability to ensure parallelization, that is, the ability to process entire sequences at the same time. This is reflected in the ability to recalculate the weights and change the overall result for each piece of information fed into the model. These features make the architecture excellent for natural language processing such as text generation and question and answer systems.

## Advantages of the Llama2 model:
- Open source: as an open source model, Llama 2 allows researchers and developers to freely use, modify, and optimize the model, which is very beneficial for driving innovation and application development.
- Large-scale training data: Large models are usually trained based on a large amount of training data, which helps to improve the model's generalization ability and recognition of complex patterns.
- Multi-tasking: Large models such as Llama 2 usually have strong transfer learning capabilities and are able to share knowledge and patterns across multiple tasks, thus achieving good performance on new tasks faster.

## Existing studies
Currently we are not able to find papers related to financial analysis using the Llama2 model in online repositories such as Google scholar, and there are cases of using other models in areas related to financial analysis using large language models, which will be covered in the literature.

# LoRA method
The LoRA approach is based on efficient and precise control of parameter updates for large pre-trained models. The core idea of this method is to represent the changes of model parameters through a low-rank matrix instead of directly updating all parameters in the model. In the fine-tuning process, LoRA introduces two low-rank matrices for the input weight matrix and the output weight matrix. The following is a detailed description of the LoRA logic.
## LoRA introduction
1. initialization and pre-training.
- LoRA first assumes that there is a large-scale model that has been pre-trained and that these models have been trained on large-scale generalized datasets to learn rich language representations.
2. low-rank matrix introduction:
- In the fine-tuning phase, LoRA does not directly update all the parameters. Instead, the method introduces two low-rank matrices.
3. parameter update strategy:
- For each linear layer in the original model, LoRA computes the fine-tuned weight matrix using the following mathematical formula:

W' = W + U @ V^T

where W is the weight matrix of the original model, W' is the fine-tuned weight matrix, and U and V are the low-rank matrices associated with that linear layer, respectively.
4. fixing and updating:
- During the fine-tuning process, LoRA fixes all parameters W of the original model and optimizes only the low-rank matrices U and V.
- This strategy allows the model to adapt to task-specific data by adjusting the low-rank matrices while maintaining most of the pre-training knowledge.
5. local adaptation and global impact:
- The low-rank matrix is used to change the global impact of the original weight matrix through the above equation.
6. resource efficiency and fast adaptation
- Since only two low-rank matrices need to be updated, LoRA significantly reduces the computational resource requirements and time costs during the fine-tuning of data parameters.
- In addition, due to its high parameter efficiency, LoRA is able to converge faster and adapt to task-specific data, and occasionally achieves good performance even with limited computational resources.
7. Parallelization capability
- LoRA is updated in a way that is independent of the structure of the original model, which allows it to improve the speed of fine-tuning in parallel computation.

Overall, the logic of LoRA lies in the efficient updating of the parameters of a large pre-trained model through the use of two low-rank matrices, while also maintaining the original structure of the model and most of the training knowledge. The advantage of this approach is the ability to quickly adapt to new tasks with limited resources and maintain a high level of performance.