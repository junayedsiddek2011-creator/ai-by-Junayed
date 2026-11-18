# JUNAYED AI — Public Website (Free Static Hosting)

A public futuristic AI coding-chat website with **no paid API key**.

## Important: what "free + no API" means here

This version uses **WebLLM** to run the open Qwen2.5-Coder 0.5B model inside each visitor's own browser using WebGPU. The website itself can be hosted free as a static site. It does **not** run a shared public inference server.

Why this design: free static hosting does not provide a free always-on GPU/LLM server. Free hosted model spaces have restrictions, sleep/quotas, and may require account/plan eligibility. This browser-based design avoids a paid API and avoids paying for an AI server.

### Visitor requirements and limitations
- A recent browser with WebGPU support (typically current Chrome/Edge on supported hardware).
- First visit downloads approximately 945 MB of model files; allow time and data.
- The model is cached by the browser where supported; subsequent visits may load faster.
- Inference runs on the visitor's device. Low-powered devices may be slow or unsupported.
- No central chat database, accounts, or shared chat history are included.
- The website is public, but the AI will not work on every phone/computer because WebGPU support varies.

## Free deployment with GitHub Pages

1. Create/sign in to a GitHub account.
2. Create a **Public** repository, for example `junayed-ai`.
3. Upload `index.html` and `README.md` to the repository root.
4. Open repository **Settings → Pages**.
5. Under Build and deployment, choose **Deploy from a branch**.
6. Select branch `main` and folder `/ (root)`, then Save.
7. Wait for deployment. GitHub will show a public URL similar to `https://YOUR-USERNAME.github.io/junayed-ai/`.
8. Share that URL. Anyone can open the website; AI inference requires their browser/device to support WebGPU and download the model.

Official docs: https://docs.github.com/en/pages

## Local preview
You can open `index.html` in a local development server. For best results, use VS Code Live Server or run:
```bash
python -m http.server 8000
```
Then open `http://localhost:8000`.

## Model and runtime
- Runtime: WebLLM (`@mlc-ai/web-llm`) via ESM CDN
- Model: `Qwen2.5-Coder-0.5B-Instruct-q4f16_1-MLC`
- Model catalog: https://webllm.mlc.ai/models/
- WebLLM docs: https://webllm.mlc.ai/docs/

The model's own license and terms apply separately from this website wrapper. Check the model card before redistribution or commercial use.
