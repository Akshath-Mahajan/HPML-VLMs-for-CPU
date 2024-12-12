# Adapting VLMs for Edge Devices

## Description

This project focuses on adapting large-scale Vision-Language Models (VLMs) like LLAVA for deployment on edge devices. The challenge lies in the resource-intensive nature of such models, which limits their practical use on consumer-grade hardware. The solution involves compressing LLAVA into a lightweight model, TinyLLaVA, using techniques such as knowledge distillation, quantization, and compilation.

### Key Contributions:
- Distilled LLAVA into TinyLLaVA, using:
  - **MobileNetV3**: Efficient image feature extraction.
  - **DistillGPT2**: Lightweight language generation.
- Applied post-training quantization for further compression.
- Compiled the model using TorchScript for optimized runtime.

---

## Project Milestones and Completion Status

| **Milestone**                     | **Status**             |
|-----------------------------------|------------------------|
| Distillation of LLAVA into TinyLLaVA | ✅ Completed           |
| Implementation of CLIP Knowledge Distillation | ✅ Completed           |
| Joint Distillation Pipeline       | ✅ Completed           |
| Post-training Quantization        | ✅ Completed           |
| Model Compilation using TorchScript | ✅ Completed           |

---

## Repository and Code Structure


```
HPML-VLMs-for-CPU/
├── models/                      # Model definition files
├── LLAVA_Initialization.ipynb   # LLaVA initialization exploration notebook
├── LLAVA_KD.ipynb               # LLaVA knowledge distillation notebook
├── TinyLLaVA - CPU Benchmark.ipynb # Benchmarking notebook for TinyLLaVA on CPU
├── TinyLLaVA_DownstreamTask.ipynb # Evaluation notebook for downstream tasks
├── clip_to_mobilenet_kd.ipynb   # CLIP to MobileNet knowledge distillation pipeline
├── evaluation_log.txt           # Logs from evaluation runs
├── llava_log.txt                # Logs from LLAVA initialization
├── llm_log.txt                  # Logs from language model training
```

---

## Example Commands to Execute the Code

### 1. Train the TinyLLaVA Model
```bash
Simply run jupyter notebooks
```

---

## Results and Observations

## Main Results

- **Model Compression & Efficiency:**
  - TinyLLaVA is **98.8% smaller** than LLAVA, enabling deployment on resource-constrained devices.
  - Achieves a **390x speedup** compared to LLAVA on edge devices.

- **Inference Performance:**
  - Achieves real-time performance with **20-30 FPS** on a **2-core AMD EPYC 7B12 CPU**.

- **Downstream Task Success:**
  - Fine-tuned on the COCO Image Captioning dataset for **3 epochs**.
  - Achieved a perplexity score of **1.13**, with predictions closely matching reference captions.

- **Generalization:**
  - Demonstrates practical deployment on low-power devices without significant loss in performance.
  - Instruction fine-tuning provides a robust initialization for downstream tasks.

## Observations and Conclusion
- **Performance**: TinyLLaVA achieves high fidelity to LLAVA with minimal loss in accuracy.
- **Efficiency**: The combined use of distillation, quantization, and compilation enables the deployment of VLMs on edge devices effectively.

For more details, visit the [GitHub Repository](https://github.com/Akshath-Mahajan/HPML-VLMs-for-CPU).
