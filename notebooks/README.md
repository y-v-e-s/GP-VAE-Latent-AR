# Notebooks

Exploratory notebooks for GP-VAE latent autoregression experiments.


### TCN-seq-1
This repository implements a causal dilated TCN encoder (Temporal Convolutional Network). The encoder is built as a stack of causal 1D convolutions with increasing dilation factors (e.g., 1, 2, 4, 8, 16), organized into residual blocks combining normalization, depthwise-separable convolutions, GLU nonlinearities, dropout, Squeeze-and-Excite, and DropPath. Causality is enforced through left padding with compensatory cropping, which strictly prevents any information leakage from future time steps. There is no temporal resolution change throughout the network (no pooling, no stride, no downsampling/upsampling): the sequence length is preserved end-to-end, characterizing a stacked TCN architecture.


### TCN-seq-2
This variant uses a causal dilated Temporal Convolutional Network (TCN) encoder for sequence modeling. The encoder is built as a residual stack of 1D causal convolutions with increasing dilations (e.g., 1, 2, 4, 8, 16), implemented with depthwise-separable convolutions, GLU activations, dropout, Squeeze-and-Excite, and DropPath. Causality is enforced via left padding followed by cropping, preventing any information leakage from future tokens. The temporal resolution is preserved throughout the network (no stride, pooling, or down/up-sampling), so the sequence length remains unchanged end-to-end.


### TCN-seq-3
This implementation uses a **causal dilated Temporal Convolutional Network (TCN)** as the encoder. The encoder stacks repeated stages (`n_pyramid`) of **causal 1D convolution blocks** with increasing dilations (e.g., `1, 2, 4, 8`), so the receptive field grows while the **sequence length T is preserved end-to-end**. Causality is enforced through **left padding followed by cropping**, preventing any information leakage from future tokens.

### TCN-seq-4
The encoder is built as a **causal dilated temporal convolutional network (TCN)**. It consists of stacked residual blocks based on **causal 1D convolutions with increasing dilation factors** (e.g., 1, 2, 4, 8), which progressively enlarge the temporal receptive field while preserving the original sequence length. Causality is enforced through left padding with compensatory cropping, ensuring that each time step only depends on past information.

Multiple stacks of such dilated convolutional blocks are applied sequentially, forming a deep hierarchical composition of temporal features at a fixed temporal resolution. This design allows the model to capture long-range dependencies efficiently while maintaining parallel computation across time steps.

### TCN-para-1

This repository implements a research prototype of a **GP-VAE language model** where **temporal structure is carried by a latent Gaussian Process**, not by token-level autoregression.

Tokens are decoded **in parallel** with no token-level autoregression; long-range dependencies are instead captured by the latent process.

The latent GP trajectory can be sampled **sequentially** (via Gaussian conditioning) or **in parallel** (via a single Cholesky factorization); both target the same joint distribution.

The encoder is a **stacked dilated causal TCN** (no pooling or downsampling), not a pyramidal architecture.

### TCN-para-2
**“Causal dilated convolutional encoder (TCN-style) with GLU gating.”**

The encoder is **TCN-style**.

It uses **causal dilated 1D convolutions** with residual connections and a dilation schedule (1, 2, 4, 8), which is the core principle of Temporal Convolutional Networks (TCNs).

The blocks are repeated several times to increase depth and receptive field, but **there is no temporal downsampling or multi-resolution hierarchy**. Therefore, the encoder is *not pyramidal* in the strict sense.

Each block uses **GLU gating** and LayerNorm instead of the canonical two-convolution TCN block.


