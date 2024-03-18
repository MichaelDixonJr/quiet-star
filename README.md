# Quiet-STaR

This project is implemented by simply patching the base Mistral implementation in Huggingface `transformers` using a new `modeling_mistral.py` and a new `configuration_mistral.py` and otherwise applying standard features. Our patches were applied to Huggingface's `transformers` version `4.37.0.dev0` -- we cannot guarantee that other changes to their implementation will not affect our implementation, so for reproducibility, we encourage using the same version.

One pitfall to be wary of: the model is not taught not to generate start and end thought tokens. Thus, when performing actual inference, it is necessary to mask these out.

We make an 8-thought-token ahead (including start and end tokens) model [available via Huggingface](https://huggingface.co/ezelikman/quietstar-8-ahead).
