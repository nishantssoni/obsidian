2025-10-01 21:29

Status:

Tags:

[Youtube Link](https://youtu.be/bCz4OMemCcA?si=dSIkzMWFgtPt86Ov)

---

### The problems with RNN (among Others)
1. **Slow Computation for Long Sequences:**
	 RNNs process sequences step-by-step, which is slow for long inputs since steps can’t be done in parallel. Transformers use self-attention to process all parts of a sequence simultaneously, making computation much faster and more efficient[citation].[ibm](https://www.ibm.com/think/topics/transformer-model)
2. **Vanishing or Exploding Gradients**:
    RNNs suffer from gradients that either shrink or grow too much during training, hurting learning especially for long sequences. Transformers avoid this by connecting all positions directly, preventing these gradient issues and enabling stable training[citation].[superdatascience](https://www.superdatascience.com/blogs/recurrent-neural-networks-rnn-the-vanishing-gradient-problem)
3. **Difficulty Accessing Long-Term Information**  :
    RNNs forget older information over time due to their sequential nature, making it hard to capture long-range dependencies. Transformers use self-attention to relate all parts of the input directly, so they can easily use information from anywhere in the sequence[citation].[kolena](https://www.kolena.com/guides/transformer-vs-rnn-4-key-differences-and-how-to-choose/)
    

![[Pasted image 20250514135125.png]]
The left block is encoder and the right block is decoder.
### 1. input Embeddings
![[Pasted image 20250514135246.png]]
- first we convert to a input ids and than into embedding which is then fed further

```python
class InputEmbedding(nn.Module):
	def __init__(self, d_model: int,vocab_size: int):
		super().__init__()
		self.d_model = d_model
		self.embedding = nn.Embedding(vocab_size, d_model)

	def forward(self, x):
		return self.embedding(x) * math.sqrt(self.d_model)
```
- d_model is the dimension of the model which is 512 in the paper
- nn.Embedding is torch.nn function which gives always a same embedding for the same parameter so it is basically a embeddig function
- in paper there is written that the forward layer is multiplied by $\sqrt{ d_{model} }$

### 2.Positional Encoding 
![[Pasted image 20250514142108.png]]
- here we add another same dimension vector which tells about the position of the word in the sentence.
```python
class PositionalEncoding(nn.Module):
def __init__(self, d_model: int, seq_len: int, dropout: float =0.1):

	super().__init__()
	self.d_model = d_model # embedding dimension
	self.seq_len = seq_len # sequence length (number of tokens)
	self.dropout = nn.Dropout(p=dropout) # to avoid overfitting
```

![[Pasted image 20250514143240.png]]
- we use above formula to encode the position given in the paper
- sin for even and cos for odd
- we use log it give slightly different number than the formula but it will more stable for the computer and model will eventually learn throughout the time.

```python
class PositionalEncoding(nn.Module):
	def __init__(self, d_model: int, seq_len: int, dropout: float = 0.1):
	
		super().__init__()
		self.d_model = d_model # embedding dimension
		self.seq_len = seq_len # sequence length (number of tokens)
		self.dropout = nn.Dropout(p=dropout) # to avoid overfitting
	
	# create a matrix of shape (seq_len, d_model)
		pe = torch.zeros(seq_len, d_model)
		
		# calculate the positional encoding
		# crate a vecotr of shape (seq_len, 1)
		position = torch.arange(0, seq_len, dtype=torch.float).unsqueeze(1)
		div_term = torch.exp(torch.arange(0, d_model, 2).float() * (-math.log(10000.0) / d_model))
		
		# apply the positional encoding
		pe[:, 0, 0::2] = torch.sin(position * div_term)
		pe[:, 0, 1::2] = torch.cos(position * div_term)
		
		# we will have batch of sentences so we need to unsqueeze the positional encoding
		# shape (1, seq_len, d_model)
		pe = pe.unsqueeze(0)
		
		# register the buffer
		self.register_buffer('pe', pe)
	
	def forward(self, x):
		# add the positional encoding and didn't train it
		x = x + self.pe[:, :x.shape[1], :].requires_grad_(False)
		return self.dropout(x)
```