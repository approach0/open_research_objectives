- [x] Visualize ColBERT token scores
  - [ ] Remove query augment and re-train

![image](https://user-images.githubusercontent.com/1407530/185572159-50aadbc9-3da2-4f12-83f3-306ad7f2ebf6.png)

A few explorations:
- [ ] Better further pretraining 
  - [ ] compare ELECTRA objective (contain more objectives and shown effective in downstream retrieval [1])
  - [ ] compare CoT-MAE autoencoder (compared to the Condenser, its CLS is used only to unmask remote context words, and the decoder does not depend on encoder lower layers [2])
  - [ ] scheduled warmup
- [ ]  ColBERT Contextual embeddings and CLS compression (alternatively, convert dense vectors to lexical/sparse vectors and compress, e.g., aggregator?)
  - [ ]  reduce dimension using robust PCA [4] (better in dealing with noise), and compare it against linear pooling and PCA.
  - [ ]  try to detect dimension importance, prune them in dot product by mutual info
  - [ ]  transform representation by rate reduction [3]
- [ ] better hybrid with structure search
  - [ ] train click-log models to guide/gate 3 passes, i.e., math structure, text word bm25, and dense retriever. Expected to be better than linear fusion.
- [ ]  [optional] train a cross encoder and do distillation?
  - [ ]  previous models using existing labels do not show too much advantage. I can verify these if time permits.

[1] https://arxiv.org/pdf/2207.02578.pdf

[2] https://arxiv.org/pdf/2208.07670.pdf

[3] https://arxiv.org/abs/2105.10446

[4] https://arxiv.org/abs/0912.3599
