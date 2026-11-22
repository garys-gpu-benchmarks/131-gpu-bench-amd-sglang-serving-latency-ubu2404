# Results: 131 SGLang Serving Latency Benchmark

**Main goal:** Measure SGLang concurrent serving latency percentiles under load  
**Tools:** Every profile starts sglang.launch_server with Mistral-7B-v0.3, then bench_serving.py

Reference results from the validation run on the system shown in each section (recorded 2026-11-22). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 24.04.5 LTS · kernel 6.8.0-149-generic · driver 7.1.9.31600000
- **Run:** 2026-11-22T12:03:23Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 07:12 · benchmark 00:10 · whole run 08:44
- **Source:** run 131_20261122_120323
- **Command:** `bash run_benchmark.sh --smoke --dtype bfloat16 --input-len 64 --output-len 16 --max-total-tokens 1024 --model-name mistralai/Mistral-7B-v0.3 --max-concurrency 2 --max-running-requests 2 --num-prompts 2`

| # | Metric | Result |
|---|---|---|
| 1 | E2E latency p50, client-observed from send, ms (end_to_end_request_latency_p50_msec) | 319.80702399960137 |
| 2 | TTFT p50, client-observed from send, ms (ttft_p50_msec) | 38.592849999986356 |
| 3 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 17.563054666667693 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 17.58868400065694 |
| 5 | Request throughput (request_throughput_requests_sec) | 6.2404039358560315 |
<!-- /profile:smoke -->
