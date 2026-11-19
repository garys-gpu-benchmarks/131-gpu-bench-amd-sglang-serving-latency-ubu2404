# Results: 131 SGLang Serving Latency Benchmark

**Main goal:** Measure SGLang concurrent serving latency percentiles under load  
**Tools:** Every profile starts sglang.launch_server with Mistral-7B-v0.3, then bench_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_148 · recorded 2026-11-19). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 24.04.5 LTS · kernel 6.8.0-149-generic · driver 7.1.9.31600000
- **Run:** 2026-11-19T15:42:05Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 07:40 · benchmark 00:09 · whole run 09:18
- **Source:** run 131_20261119_154205
- **Command:** `bash run_benchmark.sh --smoke --dtype bfloat16 --input-len 64 --output-len 16 --max-total-tokens 1024 --model-name mistralai/Mistral-7B-v0.3 --max-concurrency 2 --max-running-requests 2 --num-prompts 2`

| # | Metric | Result |
|---|---|---|
| 1 | E2E latency p50, client-observed from send, ms (end_to_end_request_latency_p50_msec) | 354.69406099946355 |
| 2 | TTFT p50, client-observed from send, ms (ttft_p50_msec) | 43.06715799975791 |
| 3 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 19.45669833330612 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 19.288614000288362 |
| 5 | Request throughput (request_throughput_requests_sec) | 5.62823297486211 |
<!-- /profile:smoke -->
