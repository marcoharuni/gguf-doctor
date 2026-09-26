# GGUF Doctor

Inspect, validate, and explore `.gguf` model files — in your terminal or entirely in your browser, with nothing ever uploaded to a server.

GGUF Doctor is stricter than a lenient viewer. It rejects truncated downloads, misaligned tensor offsets, and impossible tensor shapes before they crash an inference engine three hours in.

---

## Two ways to use it

### 1. Browser (no install)

Open the GitHub Pages site:

**https://marcoharuni.github.io/gguf-doctor/**

Drop a `.gguf` file from your device, or paste a Hugging Face URL.

- **Local files** never leave your device. The parser runs entirely in JavaScript.
- **Remote URLs** use HTTP Range requests — only the header and tensor index are fetched, never the weights.

Nothing is uploaded, logged, or sent anywhere.

### 2. CLI (build from source)

```bash
cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build
./build/minilmc show model.gguf
./build/minilmc info model.gguf token_embd.weight
