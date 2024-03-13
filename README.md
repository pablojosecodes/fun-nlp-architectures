# fun-nlp-architectures

Let's try some text generation architectures and apply them to various tasks

# N-gram language model
It's a pretty simple concept! Just take n-grams that appear in text and use that stored data to generate new words based on the following mechanism
- $p(w_3|w_1, w_2) = \frac{\textit{count}(w_1,w_2, w_3)}{\textit{count}(w_1, w_2)}$

Essentially, sample from a distribution based on conditional probabilities, and hold the Markov assumption.


## Neural language model?
Instead of an n-gram language model, we could build a neural language model. 

Pros:
- Distributed representations instead of n-grams's very sparse representations
- No need for exceedingly large storage
- Captures semantic similarity to some degree

Cons: small fixed window + no symmetry/shared weights

Insead, we can use recurrent models

# RNNs
These just do repeated sampling:
- Feed in start token
- Take the sampled word from given state, embed, feed into next timestep as $x_t$ 
- Until EOS token

This means you now have
- Symmetry
- Potential for variable input sequence 

