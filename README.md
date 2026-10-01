# Kaghaz (کاغذ)

**A private, local-language assistant for understanding official paperwork.**

Millions of people sign contracts and ignore notices because the language is dense and professional help is out of reach. Kaghaz lets anyone paste a document and get a plain-language explanation in their own language, with every claim linked to the exact sentence it came from.

**Demo login:** `demo` / `demo123`

## What the MVP does

- Extracts key **dates, durations, and amounts** from the document
- Flags **risky clauses**: auto-renewal, penalties and late fees, forfeited deposits, one-sided termination or entry rights, price increases, and waivers of rights
- Explains each flag in **English or Urdu**
- Shows a **next-steps checklist**
- **Cites the source sentence** for every point; click a citation to highlight it in the original text
- **Reads the summary aloud** using the browser's speech synthesis
- Runs **entirely in the browser**; nothing is uploaded or stored

## How to use it

1. Open the demo link and sign in with the demo credentials.
2. Click **Load sample rental contract**, or paste your own text, or upload a `.txt` file.
3. Click **Explain this document**.
4. Switch language with the dropdown at the top right.

## Current limitations

This is a front-end prototype, not the finished product.

- Analysis is **rule-based** (regular expressions), not an LLM, so it can miss clauses or over-flag
- No OCR yet, so photos of documents are not supported
- Urdu output covers the built-in explanations only, not free-form translation
- The login is a **demo gate**, not real authentication
- It explains documents; it does **not** give legal advice

## Roadmap

| Stage | Goal |
|-------|------|
| 1 | OCR (PaddleOCR / docTR) so users can photograph a document |
| 2 | Local LLM (Qwen / Llama / Mistral, quantized) for explanations, grounded in the source text |
| 3 | Translation (NLLB-200) and speech (Whisper, Piper) for more languages and voice input |
| 4 | Citation verifier and cross-check against the rule-based extractor to suppress unsupported claims |
| 5 | Knowledge base of local rules and clause patterns (Qdrant / pgvector) |
| 6 | Pilots with legal-aid clinics and community groups, plus an evaluation benchmark |

## Planned open-source stack

PaddleOCR, docTR, Tesseract, Unstructured, llama.cpp, vLLM, NLLB-200, Whisper, Piper, Qdrant, pgvector, FastAPI, LangGraph, Next.js, Ragas, promptfoo.

## Run it locally

It is a single static file. Download `index.html` and open it in any modern browser. No build step or dependencies.

## License

MIT
