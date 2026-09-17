<h1 align="center">Ubaid Ur Rehman</h1>

<p align="center">
  <b>AI / Machine Learning Engineer</b> — I take models from <i>research notebook</i> → <i>evaluated pipeline</i> → <i>running in production, on a server or on a microcontroller.</i>
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

Building **interpretable time-series classifiers that fit on microcontrollers**. I redesign CNN / TCN / Transformer architectures layer by layer, compress parameters without losing baseline accuracy, and keep the model explainable after compression. Findings currently being prepared for publication.

**MSc Data Science & AI** — Université Côte d'Azur · **BSc Software Engineering, Bronze Medalist** (3rd / 93) — CUST Islamabad

Before academia: **2 years shipping AI features into Android apps with 200K+ downloads.**

> That last line is the part I'd underline. I didn't learn deployment from a tutorial — I learned it from users filing bug reports.

---

## At a glance

| Domain | What I do | Strongest proof |
| :-- | :-- | :-- |
| 📈 **Time Series & Edge AI** | Interpretable classifiers, then deployed and verified on microcontrollers | [EdgeBench](https://github.com/ubaidur404786/edgebench) — PyTorch → ESP32-S3, board output **bit-exact** with the laptop |
| 🧠 **LLMs & Agents** | RAG, text-to-SQL, routing, fine-tuning — and evaluating all of it | [RAG Evaluation Framework](https://github.com/ubaidur404786/deep_eval_pipeline) · [live demo](https://rag-eval-framework.streamlit.app) |
| 🧬 **Biomedical & Scientific ML** | High-dimensional, noisy lab data with batch effects | LC-MS bacteria recognition — **32% → 82% accuracy** |
| 👁️ **Computer Vision** | Detection, segmentation, fine-grained classification | PlantCLEF 2025, Smart Aquaponic System |
| ⚙️ **ML Engineering** | Tracking, tuning, export, containers, CI, serving | MLflow · Optuna · ONNX · TFLite Micro · Docker · CI gates |

---

## 📈 Time Series & Edge AI

My main focus: models that are **accurate, explainable, and small enough to run on a $10 chip** — with proof that the chip gives the same answer as the laptop.

### Deploying to microcontrollers (ESP32-S3)

| Project | Problem | Result |
| :-- | :-- | :-- |
| **[EdgeBench](https://github.com/ubaidur404786/edgebench)** ⭐ | A model "fits" by parameter count, then fails on the real board | End-to-end pipeline **PyTorch → ONNX → TFLite INT8 → TFLite Micro on ESP32-S3**, with a parity check at every conversion step. Board reproduces host INT8 outputs **exactly (max diff 0.0)**. Measurement showed the 192 KB model needs **547 KB RAM on a 512 KB chip** — found by measuring, not guessing. Fixed an on-device crash (unsupported grouped convs) and an op missing from TFLM. CI regression gate, 67 unit tests, Docker |
| **[edge32_gunpoint](https://github.com/ubaidur404786/edge32_gunpoint)** | Does the quantized model on the chip match the original? | **PyTorch → TFLite INT8 → TensorFlow Lite Micro** on ESP32-S3, verified **sample by sample** on UCR GunPoint |
| **[ml-impulse-edge-esp32](https://github.com/ubaidur404786/ml-impulse-edge-esp32)** | Fast TinyML prototyping with an industry toolchain | UCR time-series classification on ESP32-S3 with **Edge Impulse** — PC and microcontroller agree on **150 / 150 samples** |

### Interpretable time-series classification

| Project | Problem | Result |
| :-- | :-- | :-- |
| **[MILLET — ECG5000](https://github.com/ubaidur404786/millet_ecg)** | Time-series models are accurate but opaque | Multiple Instance Learning + InceptionTime giving **per-segment explanations** |
| **[InterpGN — ECG](https://github.com/ubaidur404786/health-interpretable-ts)** | Clinicians need to see *why* | Interpretable-by-design classification pipeline |
| **[Signal Pre-Processing for DL](https://github.com/ubaidur404786/signal-pre-processing-in-deep-learning)** | Raw signals aren't model-ready | Reusable signal → feature transformation toolkit |

**Skills:** 1D-CNN · TCN · InceptionTime · SEA-Net · MILLET · InterpGN · INT8 post-training quantization · TFLite Micro · ESP-IDF · Edge Impulse · C/C++ firmware · memory & latency profiling

---

## 🧠 LLMs & Agents

| Project | Problem | Result |
| :-- | :-- | :-- |
| **[RAG Evaluation Framework](https://github.com/ubaidur404786/deep_eval_pipeline)** · [live demo](https://rag-eval-framework.streamlit.app) | "It looks right" is not a regression test | Reusable judge-based eval harness decoupled from the app under test — 26 adversarial golden cases, 4 reasoned metrics, 3 free models compared under one judge. **Surfaced shared failures that were a retrieval/prompt bug, not a model choice** |
| **[TelcoAssist](https://github.com/ubaidur404786/telco-assist)** | Support questions need different sources and reasoning | Router + text-to-SQL + RAG over SQLite/support docs; picked **Llama 3.3 70B** by measured performance — **100% SQL execution accuracy, 100% router accuracy, 100% retrieval hit-rate@3** |
| **SAP KBA Fine-Tuning (QLoRA)** *(SAP, Sophia Antipolis)* | Technical support answers buried in KB articles | Domain-tuned LLM + knowledge graph + semantic clustering for retrieval |
| **[LangChain / Agent Patterns](https://github.com/ubaidur404786/langchain-practice)** | — | Structured reference repo: tool calling, ReAct, LangGraph state machines |

**Skills:** RAG · text-to-SQL · LLM routing · QLoRA · knowledge graphs · LangChain / LangGraph · Chroma · golden datasets · LLM-as-judge · faithfulness & instruction-following metrics

---

## 🧬 Biomedical & Scientific ML

| Project | Problem | Result |
| :-- | :-- | :-- |
| **LC-MS Bacteria Recognition** *(UCA × CHU Laval)* | 28 species, high-dimensional spectra, heavy batch effects | VAE + denoising AE + BERNN-style correction, Optuna/MLflow tuned — **32% → 82% accuracy** · [report](https://drive.google.com/file/d/1XCciQaTciJ-t0IniXQb7DSlyLy0K1yMR/view?usp=sharing) |

---

## 👁️ Computer Vision & Generative Models

| Project | Problem | Result |
| :-- | :-- | :-- |
| **PlantCLEF 2025** | Multi-label species ID under occlusion & lighting shift | CNN + ViT pipelines, hierarchical taxonomy modeling, uncertainty estimation |
| **[Smart Aquaponic System](https://github.com/ubaidur404786/Smart-Aquaponic-System)** | Farmers can't monitor crops continuously | IoT sensors + CNN disease detection + Android app with live alerts |
| **[DCGAN Face Synthesizer](https://github.com/ubaidur404786/gan-ai)** | — | Generative face synthesis from scratch |

**Skills:** YOLOv8 · Faster R-CNN · U-Net · Vision Transformers · OpenCV · OCR · medical & agricultural imaging

---

## How I work

```text
data audit  →  baseline first  →  experiment tracking (MLflow) from day one
            →  evaluate        →  tune (Optuna)
            →  compress (quantize / prune / ONNX / TFLite)
            →  verify parity after every conversion
            →  containerize (Docker)  →  gate regressions in CI
            →  serve (Flask / React / Android / Streamlit / MCU firmware)
            →  measure again on the real device
```

I'd rather ship a **92% model that runs on an MCU** than a 95% model that lives in a notebook forever — and I measure before deciding a model needs to shrink at all.

For LLM systems, I follow the same principle: **measure before choosing, ground before generating, and test failure cases before calling it production-ready.** When the evaluation contradicts what I expected, I publish that too.

---

## Toolbox

**ML & Data**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![HuggingFace](https://img.shields.io/badge/🤗%20Transformers-FFD21E?style=flat-square)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)

**LLMs**
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![Chroma](https://img.shields.io/badge/Chroma-FF6B6B?style=flat-square)

**Edge AI & Embedded**
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![TFLite Micro](https://img.shields.io/badge/TFLite%20Micro-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32--S3-E7352C?style=flat-square&logo=espressif&logoColor=white)
![Edge Impulse](https://img.shields.io/badge/Edge%20Impulse-3B47C4?style=flat-square)
![C++](https://img.shields.io/badge/C/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)

**MLOps & Serving**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)

**Mobile**
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)

---

## Currently learning & building

Because the gaps are worth naming out loud:

* [x] **CI regression gates for ML** — EdgeBench fails the build if accuracy, flash or RAM drift from the frozen baseline
* [ ] **Kubernetes + CI/CD at scale** — I containerize and gate well; orchestration at scale is my next step
* [ ] **Tracing & cost observability for LLM systems** — I can score a run; I can't yet show you a per-node latency and token-cost breakdown. Next on the eval framework.
* [ ] **Fitting SEA-Net into internal SRAM** — EdgeBench proved it needs a narrower encoder or shorter window; that means retraining
* [ ] **Reinforcement learning agents** (Gymnasium) — beyond supervised settings
* [ ] **A multi-agent generative AI SaaS** — end to end, my own infrastructure
* [ ] **First-author publication** from the CRIStAL edge-AI research

I'm early in my career and I know exactly which boxes I haven't ticked yet. What I bring instead is speed: I learned TFLite quantization because an app needed it, TFLite Micro because a model had to run on a chip, knowledge graphs because SAP needed it, batch-effect correction because a Canadian hospital's data demanded it, and LLM evaluation because I refused to ship a chatbot I could only defend with vibes.

**Give me the problem and I'll close the gap.**

---

<p align="center">
  <b>Open to ML / AI Engineer roles from 2026 — France, EU, or remote.</b><br>
  <a href="mailto:ubaidfr404786@gmail.com">ubaidfr404786@gmail.com</a> · 🇬🇧 English (fluent) · 🇫🇷 French (learning)
</p>
