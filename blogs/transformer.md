# Attention is all you need

- It is the introductory paper for transformer architecture.
- Introduced in 2017

### What is a transformer why is it so special?
Transformer is an Encoder Decoder architecture. It is a seq2seq model and hence can be used for tasks where we want to deal with sequencial data. We can use it for tasks like translation, speech to text, text generation, image generation etc. What makes it better than LSTM, RNN and GRU is the self attention mechanism.

### What is self-attention? more importantly what is attention in general?
Attention mechanism was first inroduced in 2015 for machine translation. 
Basic Attention:
1. Hard and Soft Attention [2015]
    - Built using Importance weightning
    1. Hard Attention: learn attention weights in { 0, 1 }
        - Cons: Non-differntiability
    2. Soft Attention: learn attention weights in [ 0, 1 ]
        - Cons: Expensive computation

<img src="https://glassboxmedicine.files.wordpress.com/2019/08/soft-vs-hard-attention.png?w%25253D616" alt="Hard and Soft attention" width="400"/>


2. Local and Global Attention [2015]
    1. Global Attention: Input to attention model is from all the sequence till now.
    2. Local Attention: Input is usually a very small window of the sequence.

#### Self Attention
- Main building blaock that made the transformer model work very well. 
- To understand self attention we can break it into a search retrival problem where
    - for a given query <b>"q"</b> 
    - we need to find the set of keys <b>"k"</b>
    - with value <b>"v"</b>
- These three vectors are drawn from same source. for ex q=k=v=x
    -   In transformer these are obtained by applying differnt linear transformation to x
- Attention = <b> ∑ sim(q,k) * v </b>

<img src="https://production-media.paperswithcode.com/method_collections/SCALDE.png" alt="Attention Block" width="400"/>

For understanding Key Query and Value vectors also see [notes](/notes/kqv_notes.pdf)