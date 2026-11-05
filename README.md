# llama-cpp-cpu-bench
Benchmark Qwen2.5-3B-Instruct inference on CPU using llama.cpp. Conduct multi-thread controlled experiments, collect prefill and decode token throughput metrics, analyze CPU parallelism bottlenecks, record test scripts, raw CSV data and performance observation notes for LLM deployment learning.
# llama-cpp-cpu-bench
Benchmark Qwen2.5-3B-Instruct inference on CPU using llama.cpp.

## Overview
This is a reproducible CPU-only LLM inference benchmark project for deployment learning.
We use Qwen2.5-3B-Instruct with Q4_K_M quantization as test model, sweep different CPU thread configurations, measure **prefill** and **decode** token throughput, and explore common bottlenecks on CPU environment: thread scheduling overhead, memory bandwidth limitation, cache contention and parallelism saturation.

All test shell scripts, raw CSV benchmark data, command records and analysis notes are stored in this repo.

## Environment
- Framework: llama.cpp
- Model: Qwen2.5-3B-Instruct (Q4_K_M GGUF)
- Hardware: CPU only
- OS: Linux

## Metrics
- Prefill throughput: tokens/s (context processing)
- Decode throughput: tokens/s (token generation)
- Thread count: variable sweep (4 / 8 / 12 / ...)

## Quick Start
```bash
# Clone this repo
git clone https://github.com/tianhaozhao1205-dotcom/llama-cpp-cpu-bench.git
cd llama-cpp-cpu-bench

# Run benchmark sweep
bash bench_sweep.sh
