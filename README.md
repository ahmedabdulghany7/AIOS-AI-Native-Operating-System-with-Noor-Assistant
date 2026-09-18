# AIOS – AI-Native Operating System with Noor Assistant 🤖

> An intelligent Ubuntu-based operating system powered by AI agents and natural language interaction.

---

# NOOR OS

NOOR OS is an AI-native desktop environment built on top of the Linux kernel and Ubuntu 22.04. It addresses the "Interface Gap" of traditional operating systems by shifting from manual, fragmented navigation to an intent-based execution model. The system operates entirely offline, resolving cloud AI privacy concerns by executing powerful models directly on consumer hardware. 

Developed as a graduation project at the Egyptian Chinese University, NOOR OS introduces a secure, autonomous agent integrated into a complete operating environment.

## ✨ Core Capabilities

*   **Natural Language Interface:** Interact with your OS in both Arabic and English without memorizing commands.
*   **Autonomous AI Agent:** Features over 20 built-in tools for managing files, processes, shell execution, packages, and network settings.
*   **100% Local Execution:** Zero internet or cloud dependency, ensuring absolute data privacy.
*   **Complete Desktop Shell:** Includes a window manager, file manager, terminal, and 13+ built-in AI-powered applications (such as Noor Vision, Noor Reader, and Noor Media).

## 🏗️ System Architecture

NOOR OS operates across a specialized four-layer architecture:

1.  **Layer 3 - Desktop Shell & Apps:** Frontend built with Electron 31, React 18, Next.js, and Zustand, supporting Arabic RTL and xterm.js terminal interfaces.
2.  **Layer 2 - AI Backend & Agent Engine:** Powered by Python 3.11, FastAPI, SQLite (via SQLModel), and FAISS for vector storage and indexing.
3.  **Layer 1 - Local AI Runtime:** Utilizes Ollama for local LLM inference (Qwen2.5:7b for text), nomic-embed for RAG pipelines, OpenAI Whisper for voice processing, and Tesseract 5 for OCR.
4.  **Layer 0 - OS Foundation:** Grounded on Ubuntu 22.04 LTS, managing hardware acceleration (CUDA/ROCm), PAM authentication, PolicyKit, and NetworkManager.

## 🧠 Multimodal RAG Pipeline

The operating system natively supports Retrieval-Augmented Generation (RAG) and multimodal inputs:
*   **Knowledge Ingestion:** Extracts text from uploaded documents, chunks data, generates embeddings, and indexes them in a FAISS Vector Database.
*   **Image Input:** Processed via Tesseract OCR.
*   **Voice Input:** Transcribed efficiently using Whisper Speech-to-Text.
*   **Video Input:** Audio is extracted via FFmpeg and transcribed via Whisper.

## 🛡️ Zero-Trust Security & Privacy

Granting an AI access to a shell requires strict guardrails. NOOR OS implements a Defense-in-Depth model:

*   **GenAI DLP Guard:** Intercepts every prompt to detect and redact PII, API keys, and block prompt injections in real-time.
*   **Execution Controls:** Root actions demand native Linux authentication (PAM/PolicyKit), and destructive shell commands (like `rm -rf`) are statically neutralized.
*   **Safe-Path Resolver:** Sandboxes the AI, hard-blocking access to files outside of designated home or media directories.
*   **Noor Browser Privacy Shield:** Built-in defenses block WebRTC IP leaks, mask Canvas/WebGL/AudioContext fingerprints, and enforce Encrypted DNS.

## 📱 Mobile Companion (Flutter)

A cross-platform Flutter mobile application acts as a remote control for the desktop environment over local Wi-Fi.

*   **Cryptographic Mobile Trust:** Ephemeral pairing via QR codes utilizing 256-bit tokens and a strict 300-second Time-To-Live (TTL).
*   **Features:** Provides a remote keyboard/trackpad, live screen viewing, an AI chat interface, and a Human-in-the-Loop "Agent Approval Panel" for sensitive operations.

## 🚀 Deliverables & Future Work

**Current Deliverables:** 
Available as a Bootable Live ISO (amd64), complete with a local LLM inference engine, automated CI/CD build pipeline, and a multi-provider AI framework.

**Future Roadmap:**
*   **GPU Acceleration:** Enabling robust NVIDIA CUDA and AMD ROCm support for 3x to 5x faster inference.
*   **On-Device Fine-Tuning:** Allowing users to fine-tune models locally on private data.
*   **Persistent Installation:** Expanding beyond a live USB to full disk installation with encrypted home directories.
*   **Arabic-First UI & Voice:** Full Arabic/English speech-to-text input and comprehensive RTL typography across all apps.


---
---

