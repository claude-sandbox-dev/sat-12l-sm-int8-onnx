# sat-12l-sm int8 ONNX

Browser-ready dynamic-int8 ONNX derivative of
[`segment-any-text/sat-12l-sm`](https://huggingface.co/segment-any-text/sat-12l-sm),
used by the Shadow Chrome extension for local sentence-boundary detection.

## Provenance

- Upstream model: `segment-any-text/sat-12l-sm`
- Upstream revision: `d70c72a9331b2d5a9e82baad00c64964a23a09bb`
- Upstream license: MIT
- Base tokenizer: `FacebookAI/xlm-roberta-base`
- Conversion script: `scripts/quantize-sat.py` in the ShadowingExtention repository
- ONNX SHA-256: `5aec8a356b4a269c2b5b856491583271da5bbe75983174f5775f1001e553f0ca`

The graph is rewritten to float32 before ONNX Runtime dynamic int8
quantization. Model behavior remains sentence-boundary classification; no
training data or user data is included.

## Files

The immutable `model-5aec8a35` release contains:

- `model_quantized.onnx`
- `config.json`
- `tokenizer.json`
- `tokenizer_config.json`
- `manifest.json` with byte sizes and SHA-256 digests

Clients should verify both the expected byte size and SHA-256 digest before
creating an inference session.

## Citation

Please cite the upstream
[`Segment any Text`](https://arxiv.org/abs/2406.16678) paper when using this
model in research.

## License

MIT. Copyright (c) 2024 Benjamin Minixhofer, Markus Frohmann, Igor Sterner.
See [LICENSE](LICENSE).
