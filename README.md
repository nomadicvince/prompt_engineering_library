# 🧠 Prompt Engineering Library

A curated collection of reusable, optimized prompts and templates for building powerful LLM-based applications.

---

## Overview

This repository serves as a library of production-ready prompts for AI models such as:

- OpenAI (GPT-4, GPT-3.5)
- Anthropic (Claude)
- Mistral
- Cohere
- Open-source LLMs (LLaMA, Falcon, etc.)

Whether you're a developer, writer, researcher, or prompt engineer, this repo offers organized templates and tools to enhance LLM performance across various domains.

---


## ✨ Features

- Modular solo & multi-agent prompt templates
- Support for RAG (Retrieval-Augmented Generation)
- Categorized by use case: education, marketing, legal, support, etc.
- Includes prompt testing, scoring, and optimization tools
- Designed for integration with LangChain, CrewAI, and more

---

## 🚀 Getting Started

1. **Clone the repo**:

   ```bash
   git clone https://github.com/yourusername/prompt-engineering-library.git
   cd prompt-engineering-library
   ```

2. **Browse prompts** under `/solo_agents`, `/multi_agents`, or `/patterns`.

3. **Run optimizer (optional)**:

   ```bash
   python tools/prompt_optimizer.py --input examples/marketing_email.md
   ```

---

## 📦 Prompt Categories

- `solo_agents/`: Standalone LLM tasks (e.g., summarizer, translator, QA bot)
- `multi_agents/`: Agent collaboration flows
- `patterns/`: Prompt structures (e.g., chain-of-thought, roleplay, system loops)
- `examples/`: Real-world prompt applications

---

## 🧪 Model Compatibility

Most prompts are tested with GPT-4 but work well with Claude, Mistral, and open LLMs. Each `.md` file includes a compatibility note.

---

## 🤝 Contributing

We welcome contributions!

- Fork the repo
- Create a feature branch
- Add prompts or improvements
- Submit a pull request

Please see `CONTRIBUTING.md` for style guides and testing tips.

---

## 📄 License

MIT License. See `LICENSE` for details.

---

> *Prompt engineering is how we speak the language of machines. Craft intentionally.*