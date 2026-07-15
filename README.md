# Sherpa Korean ASR assets

This repository publishes the runtime and model assets for the on-device Korean
streaming ASR demo at `https://nokdupark.github.io`.

The deployment workflow downloads the official
`sherpa-onnx-streaming-zipformer-korean-2024-06-16` archive, retains the
official int8 encoder and joiner together with the official FP32 decoder, and
splits the large encoder into files below GitHub's 100 MB Git object limit.
Each published model file also gets a Brotli-compressed `.br` companion for
smaller browser downloads; the website prefers the `.br` file and falls back to
the raw asset when needed.

The runtime is built without pthreads or preloaded model data so it can run on
GitHub Pages, which cannot supply COOP/COEP headers. The website downloads the
assets from this project Pages site and initializes them in the browser.

The model is licensed under the upstream model's Apache-2.0 terms. See the
upstream Sherpa-ONNX project and model documentation for details.
