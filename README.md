# nanoGPT
This is a decoder-only transformer model.  
The dataset is a 1 MB text file, which is all Shakespeare's work.  
The model was trained on a character level.  
The task of the model is to generate Shakespeare-like text.

## model architecture  
This model implemented the following architecture highlighted in red boxes from the original Transformer paper:  
![image](https://github.com/GuilinXie/nanoGPT/assets/43485626/275004ee-7a37-4fd2-830b-01937f08f461)

## model's hyperparameters  
| N  | $`d_{model}`$ | $`d_{ff}`$ | h | $`d_k`$ | $`d_v`$ | $`P_{drop}`$ | train steps | params |  
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |  
| 6  | 64  | 256  | 6  | 8  | 8  | 0.2  | 5000  | Content Cell  |  

Notes: explanation of the hyperparameters
|hyperparameters|meaning|
|---------------|--------|
|N| _number of blocks stacking together as the decoder_  
|$`d_{model}`$| _embedding size_  
|$`d_{ff}`$| _feed forward's hidden size_  
|h| _number of heads_  
|$`d_k`$| _dimension of keys_  
|$`d_v`$| _dimension of values_  
|$`P_{drop}`$| _dropout rate_  
|train steps| _steps trained for the model_  
|params| _number of the models' parameters_  

## Limitation
The generation result looks roughly like Shakespeare's, but the sentences and words don't make much sense.  
One problem might be that the dataset is too small, so we can scale up the dataset.  
Another problem can be that the model was trained on character-level vocabulary, and we may do sub-word level for improvement.  
Finally, we can also tune the model's hyperparameters to make a deeper network with more hidden units to increase the expression power.  

# Reference:
1.	Andrej Karpathy: Let’s build GPT: from scratch, in code, spelled out.  https://www.youtube.com/watch?v=kCc8FmEb1nY&t=878s
2.	Paper: Attention is all you need  https://arxiv.org/abs/1706.03762
3.	Jay Alammar: The Illustrated Transformer  https://jalammar.github.io/illustrated-transformer/
4.	Harvardnlp: The Annotated Transformer  https://nlp.seas.harvard.edu/2018/04/03/attention.html
5.	Pytorch documentation:  https://pytorch.org/docs/stable/index.html
