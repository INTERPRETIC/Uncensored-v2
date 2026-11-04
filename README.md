<p align="center">
  <a href="https://interpretic.ai"><img src="https://interpretic.ai/brand/og.png" width="720" alt="INTERPRETIC AI"></a>
</p>

# Uncensored-v2

Open-weight Qwen models with political censorship removed. Safety refusals and general capability stay close to the base model. Vision and thinking mode are kept. Apache 2.0.

## Results

| Model | Political censorship | Harmful requests refused | Capability |
|---|---|---|---|
| Qwen3.8-27B-Uncensored-v2 | 98 → 4 of 113 | 100 → 95 of 100 | GPQA Diamond 89.2 → 86.4 |
| Qwen3.5-4B-Uncensored-v2 | 47 → 11 of 51 | 99 → 93 of 100 | MMLU 72.7 → 72.3 |

Base model → Uncensored-v2 (BF16). Political censorship is measured on the 115 politically sensitive Chinese-language questions of Pan & Xu (2026). Questions the base model does not know are excluded: 2 for 27B, 64 for 4B. Harmful requests: AdvBench subset. Full methods and per-format numbers are on each model card.

## Downloads

**Qwen3.8-27B-Uncensored-v2** · [collection](https://huggingface.co/collections/InterpreticAI/qwen38-27b-uncensored-6ae8ffb96fa75188fedf1c34)

| Format | Size | Runtime |
|---|---|---|
| [BF16](https://huggingface.co/InterpreticAI/Qwen3.8-27B-Uncensored-v2) | 55.6 GB | vLLM, Transformers |
| [FP8](https://huggingface.co/InterpreticAI/Qwen3.8-27B-Uncensored-v2-FP8) | 30.9 GB | vLLM |
| [GGUF Q4_K_M](https://huggingface.co/InterpreticAI/Qwen3.8-27B-Uncensored-v2-GGUF) | 16.8 GB | llama.cpp, LM Studio |
| [GGUF IQ3_XXS](https://huggingface.co/InterpreticAI/Qwen3.8-27B-Uncensored-v2-IQ3_XXS-GGUF) | 10.5 GB | llama.cpp, LM Studio · one 12 GB GPU |

**Qwen3.5-4B-Uncensored-v2** · [collection](https://huggingface.co/collections/InterpreticAI/qwen35-4b-uncensored-6ae8ffbaa8c5f6550fac074d)

| Format | Size | Runtime |
|---|---|---|
| [BF16](https://huggingface.co/InterpreticAI/Qwen3.5-4B-Uncensored-v2) | 9.3 GB | vLLM, Transformers |
| [GGUF Q4_K_M](https://huggingface.co/InterpreticAI/Qwen3.5-4B-Uncensored-v2-GGUF) | 2.8 GB | llama.cpp, LM Studio |
| [GGUF IQ3_XXS Browser](https://huggingface.co/InterpreticAI/Qwen3.5-4B-Uncensored-v2-Browser-GGUF) | 1.9 GB | in-browser (WebGPU / WebAssembly), phones |

## Quick start

```bash
# LM Studio
lms get interpretic/qwen3.8-27b-uncensored-v2
lms get interpretic/qwen3.5-4b-uncensored-v2

# vLLM
vllm serve InterpreticAI/Qwen3.8-27B-Uncensored-v2 --reasoning-parser qwen3

# llama.cpp (12 GB GPU)
llama-server -m Qwen3.8-27B-Uncensored-v2-IQ3_XXS.gguf -ngl 999 -c 32768 --jinja
```

## Limitations

The political evaluation covers Chinese-language questions only. A substantive answer is not necessarily a correct one; verify factual claims independently.

## Links

[interpretic.ai](https://interpretic.ai) · [Hugging Face](https://huggingface.co/InterpreticAI) · [LM Studio Hub](https://lmstudio.ai/interpretic) · [X @INTERPRETIC](https://x.com/INTERPRETIC) · [Discord](https://discord.gg/DqS9kU8Qbw)

## Reference

Pan, J., & Xu, X. (2026). Political censorship in large language models originating from China. *PNAS Nexus*, 5(2), pgag013. https://doi.org/10.1093/pnasnexus/pgag013
