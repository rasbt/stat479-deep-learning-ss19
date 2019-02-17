## PyTorch Loss-Input Confusion (Cheatsheet)

- `torch.nn.functional.binary_cross_entropy` takes sigmoid outputs as inputs
- `torch.nn.functional.binary_cross_entropy_with_logits` takes logits as inputs 
- `torch.nn.functional.cross_entropy` takes logits as inputs
- `torch.nn.functional.nll_loss` is like `cross_entropy` but takes log-probabilities (log-softmax) outputs as inputs
