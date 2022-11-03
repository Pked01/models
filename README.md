#models
At training time, the model computes the embeddings eij of M utterances of fixed duration from N speakers. 
A speaker embedding ci is derived for each speaker. By computing average embedding across m utterances
The similarity matrix Sij,k is the result of the two-by-two comparison of all embeddings eij against every speaker embedding. 
This measure is the scaled cosine similarity: Sij,k = w · cos(eij , ck) + b = w · eij · ||ck||2 + b (2) where w and b are learnable parameters.

at inference time an utterance is split in segments of 1.6 seconds with an overlapping of 50%, and the encoder forwards each segment individually. The resulting outputs are averaged then normalized to produce the utterance embedding.
