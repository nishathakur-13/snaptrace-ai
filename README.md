# SnapTrace AI ⚡
> **Zero-Cloud, High-Throughput Forensic & Debugging Assistant Powered by Snapdragon® NPU**

[![Qualcomm AI Hub](https://img.shields.io/badge/Qualcomm-AI%20Hub-D31027)](https://aihub.qualcomm.com/)
[![Target Platform](https://img.shields.io/badge/Target-Snapdragon%20X%20Series%20%7C%20HP%20Omnibook-0078D4)](https://www.qualcomm.com/products/mobile/snapdragon/laptops)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

SnapTrace AI is an edge-native developer companion built specifically for **Snapdragon-powered HP PCs**. It monitors local system logs, terminal stack traces, real-time developer voice commands, and screen contexts **100% offline**, eliminating cloud latency, third-party data privacy risks, and heavy CPU/GPU power consumption.

---

## 🚀 Key Features

- **Zero-Cloud Architecture:** 100% on-device inference ensures complete privacy for sensitive codebase logic, API credentials, and enterprise telemetry.
- **Hexagon NPU Offloading:** Runs continuously in the background without causing CPU thermal throttling or spinning up laptop cooling fans.
- **Real-Time Forensic Debugging:** Continuously scans active terminal output buffers and trace logs to suggest immediate bug fixes and root-cause analyses.
- **Multimodal Developer Interaction:** Supports local voice commands and terminal screen snippet parsing via pre-quantized models from the Qualcomm AI Hub.

---

## 🛠️ Architecture & Qualcomm AI Hub Integration

SnapTrace AI leverages Qualcomm's official toolchain and execution providers to deliver ultra-low latency inference on Windows on Arm:
┌────────────────────────────────────────────────────────┐
│     Local Inputs (Microphone, System Logs, Screen)    │
└──────────────────────────┬─────────────────────────────┘
│
▼
┌────────────────────────────────────────────────────────┐
│       ExecuTorch / ONNX Runtime (QNN Execution)        │
└──────────────────────────┬─────────────────────────────┘
│
▼
┌────────────────────────────────────────────────────────┐
│     Qualcomm AI Hub Quantized Models (INT4/INT8)       │
│  • Llama-3.2-1B-Instruct (INT4) — Local Reasoning      │
│  • Whisper-Base (INT8)          — Real-time Audio      │
│  • MobileNet-V4 (INT8)          — OCR & Frame Parsing │
└──────────────────────────┬─────────────────────────────┘
│
▼
┌────────────────────────────────────────────────────────┐
│    Snapdragon Hexagon Tensor Processor (HTP / NPU)     │
└──────────────────────────┬─────────────────────────────┘


### Integrated AI Hub Models
1. **[Llama-3.2-1B-Instruct (INT4)](https://aihub.qualcomm.com/):** High-throughput localized LLM compiled for Hexagon HTP to reason over terminal errors.
2. **[Whisper-Base (INT8)](https://aihub.qualcomm.com/):** Low-latency speech recognition engine for hands-free developer debugging notes.
3. **[MobileNet-V4 (INT8)](https://aihub.qualcomm.com/):** Vision backbone for extracting code snippets and UI layout text directly from screen buffers.

---

## 💻 Tech Stack

- **Frontend / Shell:** Next.js + Electron / Tauri (Native Windows on Arm)
- **Runtime Backend:** C++ Native Addon bindings via `ONNXRuntime-QNN`
- **Execution Provider:** Qualcomm `QnnHtp.dll` / `QNNExecutionProvider`
- **Model Optimization:** Qualcomm AI Hub CLI (`qai-hub`)

---

## 📌 Submission Note

This repository is submitted as part of the **Snapdragon® AI Lab Build & Present Challenge**.
- **Participant:** Nisha Kumari
- **Project Name:** SnapTrace AI
- **Target Hardware:** Snapdragon-powered HP PCs (HP Omnibook Series)
