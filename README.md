<h1 align="center">Ubaid Ur Rehman</h1>

<p align="center">
  <b>AI / Machine Learning Engineer</b> — models from <i>research notebook</i> → <i>evaluated pipeline</i> → <i>running in production, on a server or on a microcontroller.</i>
</p>

<p align="center">
  <i>A good product today has two halves: the software and the AI. I build both.</i>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/ubaid-ur-rehman-422212177/">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:ubaidfr404786@gmail.com">
    <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <img src="https://img.shields.io/badge/Lille,%20France-3B4D61?style=for-the-badge&logo=googlemaps&logoColor=white" />
  <img src="https://img.shields.io/badge/Open%20to%202026%20roles-2E8B57?style=for-the-badge" />
</p>

---

### Where I am right now

**ML Engineer Intern — Edge AI @ CRIStAL Laboratory (FOX Team), Lille**
I design a tiny time-series model that **classifies and explains itself in one pass**, small enough for an edge device — and stays explainable after compression. **ICLR submission in preparation**; I'll link it when it's public.

**In parallel:** [AI Support Platform](https://github.com/ubaidur404786/ai-support-platform) — building a production-style AI backend from an empty folder, one version per measured limitation.

### Education

| | |
| :-- | :-- |
| **MSc Data Science & AI** — Université Côte d'Azur | 2024 – 2026 |
| **BSc Software Engineering** — CUST Islamabad · **Bronze Medalist (3rd / 93)** | 2018 – 2022 |

Before the Master's: **2 years shipping AI features into mobile apps with 200K+ downloads.** I didn't learn deployment from a tutorial — I learned it from users filing bug reports.

---

## At a glance

<table>
<tr>
<td width="33%" valign="top">

### 📈 Time Series & Edge AI

Interpretable classifiers, deployed and verified on microcontrollers.

→ [EdgeBench](https://github.com/ubaidur404786/edgebench): ESP32-S3 output **bit-exact** with the laptop

</td>
<td width="33%" valign="top">

### 🏗️ Software Eng. & AI Systems

Backend architecture for AI workloads — API, serving, scaling, observability.

→ [AI Support Platform](https://github.com/ubaidur404786/ai-support-platform): v0 shipped, load-tested to its **GIL ceiling**

</td>
<td width="33%" valign="top">

### 🧠 LLMs & Agents

RAG, text-to-SQL, routing, fine-tuning — and evaluating all of it.

→ [RAG Eval Framework](https://github.com/ubaidur404786/deep_eval_pipeline) · [live demo](https://rag-eval-framework.streamlit.app)

</td>
</tr>
<tr>
<td width="33%" valign="top">

### 🧬 Biomedical & Scientific ML

High-dimensional, noisy lab data with heavy batch effects.

→ LC-MS bacteria ID: **32% → 82%**

</td>
<td width="33%" valign="top">

### 👁️ Computer Vision

Detection, segmentation, fine-grained classification, generative models.

→ [Smart Aquaponics](https://github.com/ubaidur404786/Smart-Aquaponic-System) · PlantCLEF 2025

</td>
<td width="33%" valign="top">

### ⚙️ ML Engineering

Tracking, tuning, export, containers, CI gates, serving.

→ MLflow · Optuna · ONNX · TFLite Micro · Docker

</td>
</tr>
</table>

---

## 📈 Time Series & Edge AI

Models that are accurate, explainable, and small enough to run on a **$10 chip** — with proof the chip agrees with the laptop.

| Project | |
| :-- | :-- |
| **[EdgeBench](https://github.com/ubaidur404786/edgebench)** ⭐ | PyTorch → ONNX → TFLite INT8 → **TFLite Micro on ESP32-S3**, parity-checked at every step. Board reproduces host outputs exactly. Measuring found a 192 KB model needs **547 KB RAM on a 512 KB chip** — the kind of thing parameter counts hide. CI regression gate, 67 tests |
| **[edge32_gunpoint](https://github.com/ubaidur404786/edge32_gunpoint)** | Quantized model verified **sample by sample** on-device (UCR GunPoint) |
| **[ml-impulse-edge-esp32](https://github.com/ubaidur404786/ml-impulse-edge-esp32)** | TinyML with Edge Impulse — PC and MCU agree on **150/150 samples** |
| **[MILLET — ECG5000](https://github.com/ubaidur404786/millet_ecg)** | Multiple Instance Learning + InceptionTime → **per-segment explanations** |
| **[InterpGN — ECG](https://github.com/ubaidur404786/health-interpretable-ts)** | Interpretable-by-design classification for clinical data |
| **[Signal Pre-Processing](https://github.com/ubaidur404786/signal-pre-processing-in-deep-learning)** | Reusable signal → feature toolkit |

`1D-CNN` `TCN` `InceptionTime` `SEA-Net` `INT8 quantization` `TFLite Micro` `ESP-IDF` `Edge Impulse` `C/C++`

---

## 🏗️ Software Engineering & AI Systems

Four years of my degree was software engineering. I don't want to be the person who hands over a `.pt` file and walks away.

**[AI Support Platform](https://github.com/ubaidur404786/ai-support-platform)** — an AI support system built one version at a time. Each version starts from a stated problem; nothing enters the stack until the previous design has a *measured* limitation that justifies it. Branches stay as engineering history.

**v0 shipped:** FastAPI + in-process classifier, Dockerised, 16 tests (mostly failure paths), 3 ADRs. Load testing found throughput pinned at ~80 req/s no matter the concurrency — CPU-bound inference serialising on the GIL. That measurement, not a preference, is what justifies worker processes and then a separate model service.

*Next: modular monolith → PostgreSQL → async workers → RAG → model service → observability → rollout.*
📖 Full write-ups, ADRs and numbers live [in the repo](https://github.com/ubaidur404786/ai-support-platform).

**Also:** 2 years of mobile AI product work (200K+ downloads) · Flask · React · Streamlit · Kotlin · Flutter · REST API design

---

## 🧠 LLMs & Agents

| Project | |
| :-- | :-- |
| **[RAG Evaluation Framework](https://github.com/ubaidur404786/deep_eval_pipeline)** · [demo](https://rag-eval-framework.streamlit.app) | Judge-based eval harness decoupled from the app under test — 26 adversarial cases, 4 metrics, 3 models under one judge. **Found a shared failure that was a retrieval bug, not a model choice** |
| **[TelcoAssist](https://github.com/ubaidur404786/telco-assist)** | Router + text-to-SQL + RAG; model chosen by measurement — **100% SQL execution, router and hit-rate@3** |
| **SAP KBA Fine-Tuning** *(SAP, Sophia Antipolis)* | QLoRA domain tuning + knowledge graph + semantic clustering |
| **[Agent Patterns](https://github.com/ubaidur404786/langchain-practice)** | Reference repo: tool calling, ReAct, LangGraph state machines |

`RAG` `text-to-SQL` `LLM routing` `QLoRA` `knowledge graphs` `LangChain/LangGraph` `Chroma` `LLM-as-judge` `golden datasets`

---

## 🧬 Biomedical & 👁️ Computer Vision

| Project | |
| :-- | :-- |
| **LC-MS Bacteria Recognition** *(UCA × CHU Laval)* | 28 species, heavy batch effects → VAE + denoising AE + BERNN-style correction. **32% → 82% accuracy** · [report](https://drive.google.com/file/d/1XCciQaTciJ-t0IniXQb7DSlyLy0K1yMR/view?usp=sharing) |
| **PlantCLEF 2025** | Multi-label species ID under occlusion — CNN + ViT, hierarchical taxonomy, uncertainty estimation |
| **[Smart Aquaponic System](https://github.com/ubaidur404786/Smart-Aquaponic-System)** | IoT sensors + CNN disease detection + Android app with live alerts |
| **[DCGAN Face Synthesizer](https://github.com/ubaidur404786/gan-ai)** | Generative face synthesis from scratch |

`YOLOv8` `Faster R-CNN` `U-Net` `ViT` `OpenCV` `OCR` `medical & agricultural imaging`

---

## How I work

```text
data audit → baseline first → track experiments (MLflow) from day one
           → evaluate → tune (Optuna) → compress (quantize / ONNX / TFLite)
           → verify parity → containerize → gate regressions in CI
           → serve (FastAPI / React / Android / Streamlit / MCU firmware)
           → measure again on the real device
```

I'd rather ship a **92% model that runs on an MCU** than a 95% model that lives in a notebook forever. Same principle for LLM and backend systems: **measure before choosing, ground before generating, test the failure cases before calling anything production-ready.** When the evaluation contradicts what I expected, I publish that too.

---

## Toolbox

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![HuggingFace](https://img.shields.io/badge/🤗%20Transformers-FFD21E?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)

![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![TFLite Micro](https://img.shields.io/badge/TFLite%20Micro-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32--S3-E7352C?style=flat-square&logo=espressif&logoColor=white)
![Edge Impulse](https://img.shields.io/badge/Edge%20Impulse-3B47C4?style=flat-square)
![C++](https://img.shields.io/badge/C/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)

---

## Currently learning & building

* [x] **CI regression gates for ML** — EdgeBench fails the build if accuracy, flash or RAM drift from baseline
* [ ] **Production AI backend** — AI Support Platform: v0 load-tested, v1 next
* [ ] **Tracing & cost observability for LLMs** — I can score a run; not yet a per-node latency and token-cost breakdown
* [ ] **Fitting SEA-Net into internal SRAM** — needs a narrower encoder, which means retraining
* [ ] **Kubernetes at scale** · **RL agents** (Gymnasium) · **a multi-agent GenAI SaaS**
* [ ] **First-author publication** — ICLR submission in preparation

I'm early in my career and I know which boxes I haven't ticked. What I bring is speed: I learned TFLite Micro because a model had to run on a chip, knowledge graphs because SAP needed them, batch-effect correction because a hospital's data demanded it, LLM evaluation because I refused to ship a chatbot I could only defend with vibes.

**Give me the problem and I'll close the gap.**

---

<p align="center">
  <b>Open to ML / AI Engineer roles from 2026 — France, EU, or remote.</b><br>
  <a href="mailto:ubaidfr404786@gmail.com">ubaidfr404786@gmail.com</a> · 🇬🇧 English (fluent) · 🇫🇷 French (learning)
</p>
