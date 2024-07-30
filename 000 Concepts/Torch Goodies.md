---
title: Torch Goodies
date:
  - 29-07-2024
time: 18:37
author: Luca Trautmann
tags:
  - None
series: PyTorch
🍙: いや
type: Appendix
formula: 
aliases: 
modified: 2024-07-30
---
# Torch Goodies
## Installation

```bash
pip3 install torch torchvision torchaudio
```

## Initialising Tensors
- `torch.zeros`: Creates a tensor filled with zeros
- `torch.ones`: Creates a tensor filled with ones
- `torch.rand`: Creates a tensor with random values uniformly sampled between 0 and 1
- `torch.randn`: Creates a tensor with random values sampled from a normal distribution with mean 0 and variance 1
- `torch.arange`: Creates a tensor containing the values $N, N+1, N+2, \ldots, M$
- `torch.Tensor` (input list): Creates a tensor from the list elements you provide 