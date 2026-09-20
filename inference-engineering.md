# Inference Engineering — Study Tracker

Source: [inferenceengineering.tech](https://inferenceengineering.tech/) — based on *Inference Engineering* by Philip Kiely (Baseten Books, 2026).

Tick a box when you finish a topic. In the rendered GitHub view you can click the checkbox; or edit this file and change `[ ]` to `[x]`.

---

## Preface — Why Inference Engineering Matters

- [ ] [Preface](https://inferenceengineering.tech/chapters/preface/)

## Chapter 0 — Inference: The Three Layers

- [ ] [Chapter overview](https://inferenceengineering.tech/chapters/inference/)
- [ ] The Inference Lifecycle
- [ ] The Three Layers
- [ ] Runtime
  - [ ] The Software Stack
  - [ ] Model Performance Techniques
- [ ] Infrastructure
- [ ] Tooling & Developer Experience
- [ ] Book Roadmap

## Chapter 1 — Prerequisites: Before You Optimize

- [ ] [Chapter overview](https://inferenceengineering.tech/chapters/prerequisites/)
- [ ] Scale and Specialization (shared vs dedicated inference)
- [ ] About Your App
  - [ ] AI-Native Applications
  - [ ] Online vs Offline
  - [ ] Consumer vs B2B
- [ ] Model Selection
  - [ ] Model Evaluation (evals)
  - [ ] Fine-Tuning for Domain-Specific Quality
  - [ ] Distillation
- [ ] Measuring Latency and Throughput
  - [ ] TTFT and TPS
  - [ ] ISL and OSL
  - [ ] Latency Percentiles (P50/P90/P95/P99)
  - [ ] End-to-End Metrics

## Chapter 2 — Models: Architecture and Bottlenecks

- [ ] [Chapter overview](https://inferenceengineering.tech/chapters/models/)
- [ ] Neural Networks
  - [ ] Linear Layers and Matmul
  - [ ] Activation Functions
- [ ] LLM Inference Mechanics
  - [ ] Tokens and tokenization
  - [ ] Prefill vs Decode
  - [ ] LLM Architecture (config.json, variants)
  - [ ] Transformer Blocks
  - [ ] Attention (Q/K/V, multi-head, self vs cross)
  - [ ] Mixture of Experts (MoE)
- [ ] Image Generation Inference
  - [ ] Diffusion pipeline (text encoder, denoiser, VAE)
  - [ ] Image generation model architecture
  - [ ] Few-step image generation models
  - [ ] Video generation
- [ ] Calculating Inference Bottlenecks
  - [ ] Ops:Byte Ratio and Arithmetic Intensity
  - [ ] LLM inference bottlenecks (prefill/decode)
  - [ ] Image generation inference bottlenecks
- [ ] Optimizing Attention

## Chapter 3 — Hardware: GPUs and Accelerators

- [ ] [Chapter overview](https://inferenceengineering.tech/chapters/hardware/)
- [ ] GPU Architecture
  - [ ] Compute units (CUDA cores, Tensor cores, SFU) & FLOPS
  - [ ] Memory and Caches (VRAM, HBM, L1/L2)
- [ ] GPU Architecture Generations
  - [ ] Hopper (H100, H200)
  - [ ] Ada Lovelace (L4, L40)
  - [ ] Blackwell (B200, B300)
  - [ ] Rubin (HBM4, CPX)
  - [ ] Grace and Vera CPUs
- [ ] Instances
  - [ ] Multi-GPU Instances (NVLink, NVSwitch, InfiniBand)
  - [ ] Multi-Instance GPUs (MIG)
- [ ] Other Datacenter Accelerators
- [ ] Local Inference
  - [ ] Desktop inference (Apple Silicon, llama.cpp, MLX)
  - [ ] Mobile inference

## Chapter 4 — Software: From CUDA to Inference Engines

- [ ] [Chapter overview](https://inferenceengineering.tech/chapters/software/)
- [ ] CUDA
  - [ ] CUDA kernels for inference
  - [ ] Kernel selection
  - [ ] Kernel fusion
- [ ] Deep Learning Frameworks
  - [ ] PyTorch and `torch.compile`
  - [ ] Model file formats (safetensors, ONNX)
  - [ ] ONNX Runtime and TensorRT
  - [ ] Transformers and Diffusers
- [ ] Inference Engines
  - [ ] vLLM
  - [ ] SGLang
  - [ ] TensorRT-LLM
- [ ] NVIDIA Dynamo (orchestration, KV-cache-aware routing, disaggregated serving)
- [ ] Performance Benchmarking

## Chapter 5 — Techniques: Optimization Deep Dives

- [ ] [Chapter overview](https://inferenceengineering.tech/chapters/techniques/)
- [ ] Quantization
  - [ ] Number formats (FP16/BF16/FP8/FP4/MXFP8/NVFP4)
  - [ ] Quantization approaches and component sensitivity
  - [ ] Measuring quality impact
- [ ] Speculative Decoding
  - [ ] Draft-Target Speculation
  - [ ] Medusa
  - [ ] EAGLE
  - [ ] N-gram Speculation
- [ ] Caching
  - [ ] Prefix Caching and KV Cache Re-Use
  - [ ] Where to Store the KV Cache
  - [ ] Cache-Aware Routing
- [ ] Model Parallelism
  - [ ] Tensor Parallelism (TP)
  - [ ] Expert Parallelism (EP)
  - [ ] Pipeline Parallelism (PP)
- [ ] Disaggregation

## Chapter 6 — Modalities: Beyond Text

- [ ] [Chapter overview](https://inferenceengineering.tech/chapters/modalities/)
- [ ] Vision Language Models
  - [ ] Video processing for VLMs
  - [ ] Omni-modal models
- [ ] Embedding Models
- [ ] ASR Models
  - [ ] Single-chunk optimization
  - [ ] Long file optimization (RTF)
  - [ ] Diarization
- [ ] TTS Models
  - [ ] Speech-to-speech models
- [ ] Image Generation Models
  - [ ] Kernel optimization
  - [ ] Concurrent text encoder / VAE
- [ ] Video Generation Models

## Chapter 7 — Production: Ship It

- [ ] [Chapter overview](https://inferenceengineering.tech/chapters/production/)
- [ ] Containerization
  - [ ] Dependency management
  - [ ] NIMs (NVIDIA Inference Microservices)
- [ ] Autoscaling
  - [ ] Concurrency and batch sizing
  - [ ] Cold starts
  - [ ] Routing, load balancing, and queueing
  - [ ] Scale to zero
- [ ] Multi-Cloud Capacity Management
  - [ ] GPU procurement (reserved / on-demand / spot)
  - [ ] Building for reliability (active-active / active-passive)
- [ ] Testing and Deployment
  - [ ] Zero-downtime deployment (blue-green, canary)
  - [ ] Cost estimation
  - [ ] Observability
- [ ] Client Code
  - [ ] Client latency overhead
  - [ ] Asynchronous inference
  - [ ] Streaming and protocol support (HTTP, SSE, WebSockets, gRPC)

## Interactive Exercises

- [ ] [VRAM Calculator](https://inferenceengineering.tech/exercises/vram-calculator/)
- [ ] [Arithmetic Intensity Calculator](https://inferenceengineering.tech/exercises/arithmetic-intensity/)
- [ ] [GPU Selection Advisor](https://inferenceengineering.tech/exercises/gpu-advisor/)
- [ ] [Model-to-Hardware Recommender](https://inferenceengineering.tech/exercises/hardware-recommender/)
- [ ] [KV Cache Sizing Calculator](https://inferenceengineering.tech/exercises/kv-cache-sizing/)
- [ ] [Quantization Quality Estimator](https://inferenceengineering.tech/exercises/quantization-estimator/)
- [ ] [Speculative Decoding Simulator](https://inferenceengineering.tech/exercises/speculative-decoding/)

## Learning Paths

- [ ] [Getting Started](https://inferenceengineering.tech/paths/getting-started/) (~3 hrs)
- [ ] [Infrastructure Architect](https://inferenceengineering.tech/paths/architect/) (~4 hrs)
- [ ] [Performance Optimizer](https://inferenceengineering.tech/paths/optimizer/) (~4 hrs)

## Cheat Sheets

- [ ] [Inference](https://inferenceengineering.tech/cheat-sheets/inference/)
- [ ] [Prerequisites](https://inferenceengineering.tech/cheat-sheets/prerequisites/)
- [ ] [Models](https://inferenceengineering.tech/cheat-sheets/models/)
- [ ] [Hardware](https://inferenceengineering.tech/cheat-sheets/hardware/)
- [ ] [Software](https://inferenceengineering.tech/cheat-sheets/software/)
- [ ] [Techniques](https://inferenceengineering.tech/cheat-sheets/techniques/)
- [ ] [Modalities](https://inferenceengineering.tech/cheat-sheets/modalities/)
- [ ] [Production](https://inferenceengineering.tech/cheat-sheets/production/)
