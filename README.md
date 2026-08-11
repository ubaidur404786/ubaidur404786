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

## What I actually do

<table>
<tr>
<td width="25%" valign="top">

### 📈 Time Series

Interpretable classification (MILLET, InterpGN), 1D-CNN, TCN, InceptionTime, signal→feature pipelines, sensor & ECG data.

</td>
<td width="25%" valign="top">

### 👁️ Computer Vision

YOLOv8, Faster R-CNN, U-Net segmentation, Vision Transformers, medical & agricultural imaging, OCR.

</td>
<td width="25%" valign="top">

### 🧠 LLMs & Agents

RAG, text-to-SQL, LLM routing, QLoRA fine-tuning, knowledge graphs, LangChain / LangGraph, tool orchestration, LLM evaluation and reliability testing.

</td>
<td width="25%" valign="top">

### ⚙️ ML Engineering

Docker, MLflow, Optuna, Git/GitHub workflows, ONNX & TFLite export, quantization, pruning, Flask/React serving.

</td>
</tr>
</table>

---

## Selected work

| Project                                                                                                     | Problem                                                   | Result                                                                                                                                                                                                                                           |
| :---------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **[TelcoAssist](https://github.com/ubaidur404786/telco-assist)**                                            | Support questions need different sources and reasoning    | Router + text-to-SQL + RAG over SQLite/support documents; evaluated free LLMs on golden datasets and selected **Llama 3.3 70B** based on measured performance — **100% SQL execution accuracy, 100% router accuracy, 100% retrieval hit-rate@3** |
| **[MILLET — ECG5000 Interpretability](https://github.com/ubaidur404786/millet_ecg)**                        | Time-series models are accurate but opaque                | Multiple Instance Learning + InceptionTime giving per-segment explanations                                                                                                                                                                       |
| **[InterpGN — ECG Interpretability](https://github.com/ubaidur404786/health-interpretable-ts)**             | Clinicians need to see *why*                              | Interpretable-by-design classification pipeline                                                                                                                                                                                                  |
| **LC-MS Bacteria Recognition** *(UCA × CHU Laval)*                                                          | 28 species, high-dimensional spectra, heavy batch effects | VAE + denoising AE + BERNN-style correction, Optuna/MLflow tuned — **32% → 82% accuracy** · [report](https://drive.google.com/file/d/1XCciQaTciJ-t0IniXQb7DSlyLy0K1yMR/view?usp=sharing)                                                         |
| **SAP KBA Fine-Tuning (QLoRA)** *(SAP, Sophia Antipolis)*                                                   | Technical support questions buried in KB articles         | Domain-tuned LLM + knowledge graph + semantic clustering for retrieval                                                                                                                                                                           |
| **[LangChain / Agent Patterns](https://github.com/ubaidur404786/langchain-practice)**                       | —                                                         | Structured reference repo on tool calling, ReAct, LangGraph state machines                                                                                                                                                                       |
| **PlantCLEF 2025**                                                                                          | Multi-label species ID under occlusion & lighting shift   | CNN + ViT pipelines, hierarchical taxonomy modeling, uncertainty estimation                                                                                                                                                                      |
| **[Smart Aquaponic System](https://github.com/ubaidur404786/Smart-Aquaponic-System)**                       | Farmers can't monitor crops continuously                  | IoT sensors + CNN disease detection + Android app with live alerts                                                                                                                                                                               |
| **[DCGAN Face Synthesizer](https://github.com/ubaidur404786/gan-ai)**                                       | —                                                         | Generative face synthesis from scratch                                                                                                                                                                                                           |
| **[Signal Pre-Processing for DL](https://github.com/ubaidur404786/signal-pre-processing-in-deep-learning)** | —                                                         | Reusable signal→feature transformation toolkit                                                                                                                                                                                                   |

---

## How I work

```text
data audit  →  baseline first  →  experiment tracking (MLflow) from day one
            →  evaluate        →  tune (Optuna)
            →  compress (quantize / prune / ONNX / TFLite)
            →  containerize (Docker)
            →  serve (Flask / React / Android / Streamlit)
            →  measure again on the real device
```

I'd rather ship a **92% model that runs in 8 MB on an MCU** than a 95% model that lives in a notebook forever.

For LLM systems, I follow the same principle: **measure before choosing, ground before generating, and test failure cases before calling it production-ready.**

---

## Toolbox

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square\&logo=python\&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square\&logo=pytorch\&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square\&logo=tensorflow\&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square\&logo=scikitlearn\&logoColor=white)
![HuggingFace](https://img.shields.io/badge/🤗%20Transformers-FFD21E?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square\&logo=langchain\&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square\&logo=opencv\&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square\&logo=onnx\&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square\&logo=docker\&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square\&logo=mlflow\&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square\&logo=git\&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square\&logo=kotlin\&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square\&logo=flutter\&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square\&logo=react\&logoColor=61DAFB)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square\&logo=flask\&logoColor=white)

---

## Currently learning & building

Because the gaps are worth naming out loud:

* [ ] **Kubernetes + CI/CD for ML** — I containerize well; orchestration at scale is my next step
* [ ] **Reinforcement learning agents** (Gymnasium) — beyond supervised settings
* [ ] **A multi-agent generative AI SaaS** — end to end, my own infrastructure
* [ ] **First-author publication** from the CRIStAL edge-AI research

I'm early in my career and I know exactly which boxes I haven't ticked yet. What I bring instead is speed: I learned TFLite quantization because an app needed it, knowledge graphs because SAP needed it, batch-effect correction because a Canadian hospital's data demanded it, and LLM evaluation because TelcoAssist needed a model that was measured rather than guessed at.

**Give me the problem and I'll close the gap.**

---

<p align="center">
  <b>Open to ML / AI Engineer roles from 2026 — France, EU, or remote.</b><br>
  <a href="mailto:ubaidfr404786@gmail.com">ubaidfr404786@gmail.com</a> · 🇬🇧 English (fluent) · 🇫🇷 French (learning)
</p>
