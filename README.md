<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#20 (Run ID `43426193189`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43426193189)
- **Status**: **CANCELLED**
- **Timestamp**: `2026-11-13 14:16:33 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-13T12:33:42.887Z] ================================================================================
[2026-11-13T12:33:42.903Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-13T12:33:42.905Z] ================================================================================
[2026-11-13T12:33:47.759Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-13T12:33:47.949Z] --------------------------------------------------------------------------------
[2026-11-13T12:33:47.950Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.12 GB / 149.89 GB
[2026-11-13T12:33:47.951Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-13T12:33:47.952Z]  [Disk Telemetry] Total Combined Usable Free Space: 247.99 GB
[2026-11-13T12:33:48.025Z] --------------------------------------------------------------------------------
[2026-11-13T12:33:48.026Z]  [OK] Disk space verification passed: 247.99 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 860K Nov 13 12:34 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 860K Nov 13 12:34 build/apex.exe
 [Step 2] Running Pre-Flight Unit, Greedy Parity & OpenAI API Stress Verification...
[gen_synthetic_gguf] Wrote tests/synth_glm53_ud_iq2_xxs.gguf (6748.6 KB)
[gen_synthetic_gguf] Wrote tests/synth_qwen38_ud_iq2_xs.gguf (9282.8 KB)

=== [TEST] Pre-Flight Host Hardware Benchmark: ./apex.exe hwtest ===

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.47 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    613.24 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2301.15 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9879.90 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11388.96 MB/s
   RND4K Q32T16 Read                  :    717.43 MB/s (  183663 IOPS)
   RND4K Q1T1  Read                   :    850.38 MB/s (Latency: 4.59 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     78.31 GB/s
   AVX2 256-bit Sequential Write BW   :     68.67 GB/s
   STREAM Triad (A = B + s*C) BW      :     37.38 GB/s
   Random Pointer-Chase Latency       :     55.62 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.64 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.36 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     27.26 GB/s (FP32 Equiv)
================================================================================



=== [TEST] GLM-5.3-Flash 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_glm53_ud_iq2_xxs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : glm5-next (GLM-5.3-Flash)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] Qwen-3.8-Flash-Next 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_qwen38_ud_iq2_xs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] GLM-5.3-Flash 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_glm53_ud_iq2_xxs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=1.93 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1941.88 tps | Avg=1941.88 tps | Hit=99.5% | NVMe=2173.1 MB/s (6.19 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1674.64 tps | Avg=1798.39 tps | Hit=99.5% | NVMe=2117.8 MB/s (7.01 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1458.38 tps | Avg=1668.71 tps | Hit=99.5% | NVMe=2072.3 MB/s (7.78 MB, QD=64) | RSS=71.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1268.35 tps | Avg=1546.65 tps | Hit=99.5% | NVMe=2021.0 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1150.16 tps | Avg=1446.90 tps | Hit=99.5% | NVMe=1980.8 MB/s (9.33 MB, QD=64) | RSS=72.3 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1024.16 tps | Avg=1353.77 tps | Hit=99.5% | NVMe=1953.3 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=963.79 tps | Avg=1279.79 tps | Hit=99.5% | NVMe=1929.0 MB/s (10.83 MB, QD=64) | RSS=72.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=879.68 tps | Avg=1210.94 tps | Hit=99.5% | NVMe=1907.2 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=276.71 tps | Hit=99.5% (LA:+0.0%) | NVMe=1850.4 MB/s (12.43 MB) | RSS=73.2 MB
[LIVE-DECODE] 16/32 tok | Avg=277.99 tps | Hit=99.5% (LA:+0.1%) | NVMe=1826.6 MB/s (13.10 MB) | RSS=73.2 MB
[LIVE-DECODE] 24/32 tok | Avg=278.26 tps | Hit=99.5% (LA:+0.1%) | NVMe=1794.0 MB/s (13.25 MB) | RSS=73.2 MB
[LIVE-DECODE] 32/32 tok | Avg=278.37 tps | Hit=99.5% (LA:+0.1%) | NVMe=1783.8 MB/s (13.30 MB) | RSS=73.2 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 4L, H=256, V=256 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 16 Exp/Lyr (Top-4, 64 Total) | 4 Threads | QD=64 | Shards=1 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 0.01 GB GGUF | 0.00 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=3.48 MB | KV/State=25.37 MB (14080 B/tok)
   LRFU Cache / Staging Ring    : 1.93 MB (40/64 exp = 62.50% pinned) | Staging=3.09 MB
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=73.17 MB | Peak=73.17 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "tok_55tok_55tok_175tok_55tok_39tok_55tok_36tok_246tok_68tok_55tok_246tok_86tok_68tok_220tok_197tok_246tok_228tok_246tok_228tok_86tok_68tok_86tok_236tok_246tok_229tok_246tok_229tok_246tok_229tok_246tok_229tok_21tok_246"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=96.8% | AvgMargin=13.103 | MinMargin=0.511
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1691.24 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    3.69 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    3.69 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    3.66 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    3.66 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    3.57 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    3.57 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    3.54 | 11 |  1 |  0 |    49.5 |
   |   26 |     246 | tok_246        |  195.41 | 100.0% |      54 |  174.46 |    3.63 | 12 |  0 |  0 |     0.0 |
   |   27 |     229 | tok_229        |  171.70 | 100.0% |      70 |  154.45 |    3.63 |  0 |  0 |  0 |     0.0 |
   |   22 |      86 | tok_86         |  191.40 |  93.7% |     246 |  188.70 |    3.60 | 12 |  0 |  0 |     0.0 |
   |   23 |     236 | tok_236        |  139.26 |  98.6% |     246 |  135.00 |    3.60 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    3.57 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    3.57 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    3.56 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    3.56 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.691s, TTFT=1691.24ms): Avg=1210.94 | Min=879.68 | Max=1941.88 tps
   Prefill Chunks (8): C1:256t/1941.9tps/99% | C2:256t/1674.6tps/99% | C3:256t/1458.4tps/99% | C4:256t/1268.3tps/99%
                       C5:256t/1150.2tps/99% | C6:256t/1024.2tps/99% | C7:256t/963.8tps/99% | C8:256t/879.7tps/99%
   Decode  (32 tok, 0.115s): Avg=278.37 | Min=271.27 | Max=282.71 tps
   Latency (ms) : Min=3.54 | P10=3.56 | P25=3.57 | P50=3.59 | P75=3.60 | P90=3.66 | P95=3.69 | P99=3.69 | Max=3.69
   Mean/SD/Jitt : Mean=3.59ms | StdDev=0.04ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (24768): RawRAM=24618 (99.39%) | Lookahead=22 (+0.09%) | ColdMiss=128 (0.52%) | EFF HIT=99.48%
   Lookahead    : 28 prefetched -> 22 consumed (78.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L01 | 8256 | 8213 |   7 |  36 | 99.6%|   2.08 | | L03 | 8256 | 8212 |   0 |  44 | 99.5%|   2.32 |
   | L02 | 8256 | 8193 |  15 |  48 | 99.4%|   3.14 | |     |      |      |     |     |      |        |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 13.30 MB (Load=5.42 | Prefill=6.19 | Warmup=0.00 | Decode=1.69 MB)
   SSD Data/Token (Decode)      : Avg=0.053 MB/tok (Min=0.000 | P50=0.024 | P95=0.314 | Max=0.314 MB) | Prefill=0.003 MB/tok
   NVMe Batches / Requests      : 41 Batches | 748 Reads | 438 LBA Merges (Avg 18.2 KB/req)
   SSD Read Bandwidth           : Avg=1783.81 MB/s | Peak=6721.15 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=4.78 ms | AsyncOverlapped=6.39 ms (57.2% Overlapped)
   RAM Traffic & Effective BW   : 1.43 GB moved | Eff=0.79 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=2.344s + Sys=0.547s (Wall=1.824s) | SysUtil=39.6% | ThrUtil=39.6% | 36.66 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1526.19 ms (  733.7 us/tok | 84.50%)
   MoE AVX2 Q8 Expert Compute   :    179.28 ms (   86.2 us/tok |  9.93%)
   Router + Lookahead Dispatch  :     47.29 ms (   22.7 us/tok |  2.62%)
   LM Head Output Projection    :      4.09 ms (    2.0 us/tok |  0.23%)
   Foreground NVMe Sync Stall   :      4.78 ms (    2.3 us/tok |  0.26%)
   Unaccounted / OMP & Sampling :     44.58 ms (   21.4 us/tok |  2.47%) | Total Wall=1806.20 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    26.68%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.18%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.49%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    68.36%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.29%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2658.47 tps | Avg=2658.47 tps | Hit=99.2% | NVMe=3065.4 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2580.54 tps | Avg=2618.92 tps | Hit=99.2% | NVMe=4088.3 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2128.96 tps | Avg=2432.33 tps | Hit=99.2% | NVMe=4654.4 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2233.65 tps | Avg=2379.42 tps | Hit=99.2% | NVMe=5061.7 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2084.84 tps | Avg=2314.03 tps | Hit=99.2% | NVMe=5379.5 MB/s (97.14 MB, QD=64) | RSS=90.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1936.23 tps | Avg=2241.14 tps | Hit=99.2% | NVMe=5635.8 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1754.41 tps | Avg=2155.70 tps | Hit=99.2% | NVMe=5832.9 MB/s (133.27 MB, QD=64) | RSS=91.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1669.88 tps | Avg=2080.06 tps | Hit=99.2% | NVMe=5973.8 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=253.68 tps | Hit=99.2% (LA:+0.0%) | NVMe=5826.5 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=254.67 tps | Hit=99.2% (LA:+0.1%) | NVMe=5742.6 MB/s (153.44 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=255.08 tps | Hit=99.2% (LA:+0.1%) | NVMe=5613.0 MB/s (154.78 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=255.27 tps | Hit=99.2% (LA:+0.1%) | NVMe=5515.0 MB/s (155.58 MB) | RSS=91.8 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 4L, H=256, V=256 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 16 Exp/Lyr (Top-4, 80 Total) | 4 Threads | QD=64 | Shards=1 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 0.01 GB GGUF | 0.00 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4.70 MB | KV/State=22.85 MB (13824 B/tok)
   LRFU Cache / Staging Ring    : 2.17 MB (40/80 exp = 50.00% pinned) | Staging=3.47 MB
   Process RSS (Start/End/Peak) : Start=4.90 MB | End=91.80 MB | Peak=91.80 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_129qtok_68qtok_209qtok_223qtok_113qtok_229qtok_24qtok_229qtok_148qtok_209qtok_193qtok_146qtok_148qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=92.5% | AvgMargin=9.488 | MinMargin=0.056
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 |  984.59 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    3.98 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   94.59 | 100.0% |     177 |   84.92 |    3.98 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    3.94 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   85.06 |  99.7% |     177 |   78.63 |    3.94 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    3.93 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   82.87 |  99.7% |     129 |   77.18 |    3.93 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    3.92 | 16 |  0 |  0 |    32.0 |
   |   12 |      68 | qtok_68        |   61.65 |  99.4% |      36 |   56.59 |    3.95 | 12 |  4 |  0 |   143.0 |
   |   13 |     209 | qtok_209       |   83.06 |  79.9% |     127 |   81.55 |    3.95 |  0 |  0 |  0 |   143.0 |
   |   18 |     229 | qtok_229       |   80.70 | 100.0% |      33 |   70.24 |    3.92 | 10 |  6 |  0 |   170.8 |
   |   19 |     148 | qtok_148       |   68.09 |  43.4% |      67 |   67.82 |    3.92 |  0 |  0 |  0 |   170.8 |
   |   30 |     254 | qtok_254       |   71.22 |  99.9% |      66 |   64.31 |    3.91 | 14 |  2 |  0 |    87.5 |
   |   31 |      49 | qtok_49        |  125.25 | 100.0% |     177 |   99.98 |    3.91 |  0 |  0 |  0 |    87.5 |
   |   32 |     254 | qtok_254       |   71.45 |  98.0% |      66 |   67.49 |    3.94 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  131.17 | 100.0% |     129 |  104.87 |    3.94 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 0.985s, TTFT=984.59ms): Avg=2080.06 | Min=1669.88 | Max=2658.47 tps
   Prefill Chunks (8): C1:256t/2658.5tps/99% | C2:256t/2580.5tps/99% | C3:256t/2129.0tps/99% | C4:256t/2233.6tps/99%
                       C5:256t/2084.8tps/99% | C6:256t/1936.2tps/99% | C7:256t/1754.4tps/99% | C8:256t/1669.9tps/99%
   Decode  (32 tok, 0.125s): Avg=255.27 | Min=251.11 | Max=257.77 tps
   Latency (ms) : Min=3.88 | P10=3.89 | P25=3.91 | P50=3.91 | P75=3.94 | P90=3.95 | P95=3.98 | P99=3.98 | Max=3.98
   Mean/SD/Jitt : Mean=3.92ms | StdDev=0.03ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33024): RawRAM=32720 (99.08%) | Lookahead=48 (+0.15%) | ColdMiss=256 (0.78%) | EFF HIT=99.22%
   Lookahead    : 60 prefetched -> 54 consumed (90.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8256 | 8190 |   2 |  64 | 99.2%|   3.58 | | L02 | 8256 | 8170 |  22 |  64 | 99.2%|   4.72 |
   | L01 | 8256 | 8184 |   8 |  64 | 99.2%|   4.12 | | L03 | 8256 | 8176 |  16 |  64 | 99.2%|   4.39 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 155.58 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=4.28 MB)
   SSD Data/Token (Decode)      : Avg=0.134 MB/tok (Min=0.031 | P50=0.113 | P95=0.523 | Max=0.523 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 95 Batches | 34221 Reads | 33838 LBA Merges (Avg 4.7 KB/req)
   SSD Read Bandwidth           : Avg=5515.01 MB/s | Peak=10670.60 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=24.69 MB | Write=0.00 MB | Syscalls=400
   Sync Stall vs Async DMA      : SyncStall=6.43 ms | AsyncOverlapped=27.04 ms (80.8% Overlapped)
   RAM Traffic & Effective BW   : 2.10 GB moved | Eff=1.89 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=1.844s + Sys=0.266s (Wall=1.137s) | SysUtil=46.4% | ThrUtil=46.4% | 42.89 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    677.09 ms (  325.5 us/tok | 61.00%)
   MoE AVX2 Q8 Expert Compute   :    281.49 ms (  135.3 us/tok | 25.36%)
   Router + Lookahead Dispatch  :     64.11 ms (   30.8 us/tok |  5.78%)
   LM Head Output Projection    :      4.01 ms (    1.9 us/tok |  0.36%)
   Foreground NVMe Sync Stall   :      6.43 ms (    3.1 us/tok |  0.58%)
   Unaccounted / OMP & Sampling :     76.82 ms (   36.9 us/tok |  6.92%) | Total Wall=1109.94 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.51%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.18%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.31%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    64.38%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.62%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] OpenAI-Compatible API Server on port 18081 (tests/synth_glm53_ud_iq2_xxs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 21, "completion_tokens": 8, "total_tokens": 29}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"tok_55tok_55tok_55tok_55tok_55tok_55"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"text": "tok_246tok_55tok_55tok_55tok_55tok_55", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "tok_246tok_55tok_246tok_55tok_55tok_55", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 19, "completion_tokens": 6, "total_tokens": 25}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "glm-5.3-flash-ud-iq2_xxs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "tok_55tok_55tok_55tok_55tok_55tok_55"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
[Concurrent Stress Test]: 4/4 parallel client requests completed cleanly.
[llama.cpp Server Parity]: /props, /tokenize, /detokenize, /v1/embeddings passed.
[GET /v1/telemetry]: {
  "model_name": "GLM-5.3-Flash-UD-IQ2_XXS-Synthetic",
  "architecture": "glm5-next (GLM-5.3-Flash)",
  "quantization": "Unsloth UD-IQ2_XXS",
  "mtp_enabled": false,
  "dense_pinned_ram_bytes": 3037760,
  "kv_cache_ram_bytes": 21282816,
  "kv_bytes_per_token": 14080,
  "expert_cache_ram_bytes": 1622016,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 166.24,
    "avg_tps": 986.53,
    "min_tps": 801.3,
    "max_tps": 1117.97
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 209.78,
    "min_tps": 195.19,
    "max_tps": 215.21,
    "p50_ms": 4.74,
    "p90_ms": 4.86,
    "p99_ms": 5.12,
    "mean_ms": 4.77,
    "jitter_ms": 0.07
  },
  "cache": {
    "raw_hit_rate_pct": 96.47,
    "effective_hit_rate_pct": 97.91,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 8562752,
    "prefill_bytes": 2585088,
    "warmup_bytes": 0,
    "decode_bytes": 1419264,
    "bytes_per_token": 42181.04,
    "avg_mbs": 1664.44,
    "peak_mbs": 6793.48,
    "sync_wait_ms": 1.83,
    "async_overlap_ms": 4.03
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 272146688
  },
  "kernel_attribution_ms": {
    "dense_attention": 262.25,
    "moe_compute": 72.84,
    "router_lookahead": 5.67,
    "lm_head": 6.0,
    "unaccounted": 3.56
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 77.89,
    "ram_bandwidth_pinning": 2.49,
    "expert_cache_lrfu": 15.59,
    "lookahead_parallel_overlap": 2.5,
    "ssd_nvme_throughput": 1.53,
    "total": 100.0
  }
}

=== [TEST] OpenAI-Compatible API Server on port 18082 (tests/synth_qwen38_ud_iq2_xs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63qtok_194qtok_49"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 21, "completion_tokens": 8, "total_tokens": 29}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"qtok_159qtok_194qtok_49qtok_254qtok_49qtok_254"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"text": "qtok_223qtok_49qtok_68qtok_145qtok_49qtok_229", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_68qtok_179qtok_49qtok_49qtok_17qtok_63", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 19, "completion_tokens": 6, "total_tokens": 25}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "qwen-3.8-flash-next-ud-iq2_xs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
[Concurrent Stress Test]: 4/4 parallel client requests completed cleanly.
[llama.cpp Server Parity]: /props, /tokenize, /detokenize, /v1/embeddings passed.
[GET /v1/telemetry]: {
  "model_name": "Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic",
  "architecture": "qwen4exp (Qwen-3.8-Flash-Next)",
  "quantization": "Unsloth UD-IQ2_XS",
  "mtp_enabled": false,
  "dense_pinned_ram_bytes": 3738208,
  "kv_cache_ram_bytes": 19173376,
  "kv_bytes_per_token": 13824,
  "expert_cache_ram_bytes": 1818624,
  "ssd_offloaded_expert_bytes": 3653632,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 212.15,
    "avg_tps": 773.04,
    "min_tps": 557.48,
    "max_tps": 890.74
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 185.84,
    "min_tps": 167.82,
    "max_tps": 194.42,
    "p50_ms": 5.32,
    "p90_ms": 5.81,
    "p99_ms": 5.96,
    "mean_ms": 5.38,
    "jitter_ms": 0.12
  },
  "cache": {
    "raw_hit_rate_pct": 85.56,
    "effective_hit_rate_pct": 94.92,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 38047328,
    "prefill_bytes": 20297216,
    "warmup_bytes": 0,
    "decode_bytes": 12193280,
    "bytes_per_token": 187425.26,
    "avg_mbs": 2113.33,
    "peak_mbs": 8728.09,
    "sync_wait_ms": 5.13,
    "async_overlap_ms": 16.27
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 366830592
  },
  "kernel_attribution_ms": {
    "dense_attention": 236.6,
    "moe_compute": 137.27,
    "router_lookahead": 6.77,
    "lm_head": 6.1,
    "unaccounted": 30.14
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 72.97,
    "ram_bandwidth_pinning": 2.82,
    "expert_cache_lrfu": 13.69,
    "lookahead_parallel_overlap": 6.24,
    "ssd_nvme_throughput": 4.28,
    "total": 100.0
  }
}

ALL APEX INFERENCE V1 VERIFICATION TESTS PASSED 100.00%!
================================================================================
 [3.1] Cloning & Building JustVugg/colibri (https://github.com/JustVugg/colibri.git)
================================================================================
Cloning into 'colibri'...
gcc -D_FILE_OFFSET_BITS=64 -O3 -march=x86-64-v3 -fopenmp -Wall -Wextra -Wno-unused-parameter -Wno-misleading-indentation -Wno-unused-function -MMD -MP qwen38.c    -o qwen38.exe -lm -fopenmp -static -lpsapi
gcc -D_FILE_OFFSET_BITS=64 -O3 -march=x86-64-v3 -fopenmp -Wall -Wextra -Wno-unused-parameter -Wno-misleading-indentation -Wno-unused-function  -MMD -MP glm53.c    -o glm53.exe -lm -fopenmp -static -lpsapi 
================================================================================
 [3.2] Downloading Official Prebuilt llama.cpp AVX2 Windows Binaries
================================================================================
================================================================================
 [3.3] Cloning & Building ik_llama.cpp (CPU AVX2 Release)
================================================================================
Cloning into 'ik_llama'...
error: unable to create file examples/server/webui_llamacpp/src/lib/components/app/chat/ChatAttachments/ChatAttachmentsPreview/ChatAttachmentsPreviewCurrentItem/ChatAttachmentsPreviewCurrentItemUnavailable.svelte: Filename too long
fatal: unable to checkout working tree
warning: Clone succeeded, but checkout failed.
You can inspect what was checked out with 'git status'
and retry with 'git restore --source=HEAD :/'

-- Building for: Visual Studio 18 2026
-- The C compiler identification is MSVC 19.51.36260.0
-- The CXX compiler identification is MSVC 19.51.36260.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/Program Files/Microsoft Visual Studio/18/Enterprise/VC/Tools/MSVC/14.51.36231/bin/Hostx64/x64/cl.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/Program Files/Microsoft Visual Studio/18/Enterprise/VC/Tools/MSVC/14.51.36231/bin/Hostx64/x64/cl.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found Git: C:/Program Files/Git/ucrt64/bin/git.exe (found version "2.56.0.windows.4")
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Failed
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - not found
-- Found Threads: TRUE
-- Found OpenMP_C: -openmp (found version "2.0")
-- Found OpenMP_CXX: -openmp (found version "2.0")
-- Found OpenMP: TRUE (found version "2.0")
-- OpenMP found
-- Using optimized iqk matrix multiplications
-- Enabling IQK Flash Attention kernels
-- Including all IQK FA kernels
-- ccache found, compilation results will be cached. Disable with GGML_CCACHE=OFF.
-- CMAKE_SYSTEM_PROCESSOR: AMD64
-- CMAKE_GENERATOR_PLATFORM: 
-- x86 detected
CMake Warning at common/CMakeLists.txt:26 (message):
  Git index not found in git repository.


-- ARCH_FLAGS = 
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public/index.html.gz
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public_llamacpp/index_llamacpp.html.gz
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public_llamacpp/loading.html
-- Configuring done (19.0s)
-- Generating done (0.7s)
CMake Warning (unused-cli):
  Manually-specified variables were not used by the project:

    GGML_F16C


-- Build files have been written to: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build
MSBuild version 18.11.1-1.26513.3+940033be3 for .NET Framework

  1>Checking Build System
  Generating build details from Git
  -- Found Git: C:/Program Files/Git/ucrt64/bin/git.exe (found version "2.56.0.windows.4")
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/common/CMakeLists.txt
  build-info.cpp
  build_info.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\build_info.dir\Release\build_info.lib
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/ggml/src/CMakeLists.txt
  ggml.c
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(4020,13): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(4038,13): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25): warning C4477: 'fprintf' : format string '%ld' requires an argument of type 'long', but variadic argument 2 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 2 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 3 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 4 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 5 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 6 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 7 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 8 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 9 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
  ggml-alloc.c
  ggml-quants.c
C:\Program Files (x86)\Windows Kits\10\Include\10.0.26100.0\ucrt\assert.h(21,9): warning C4005: 'static_assert': macro redefinition [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  (compiling source file '../../../ggml/src/ggml-quants.c')
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-common.h(69,9):
      see previous definition of 'static_assert'
  
  ggml-aarch64.c
C:\Program Files (x86)\Windows Kits\10\Include\10.0.26100.0\ucrt\assert.h(21,9): warning C4005: 'static_assert': macro redefinition [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  (compiling source file '../../../ggml/src/ggml-aarch64.c')
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-common.h(69,9):
      see previous definition of 'static_assert'
  
  Generating Code...
  ggml-backend.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-backend.cpp(2124,30): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  ggml-moe-prefetch.cpp
  iqk_mul_mat.cpp
  iqk_kda.cpp
  iqk_flash_attn.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(141,94): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(141,82): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(179,13): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(187,25): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(188,61): warning C4244: '=': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(196,38): warning C4244: '=': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(273,112): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(281,119): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(298,22): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(346,80): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(346,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(394,80): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(394,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(481,24): warning C4244: '=': conversion from 'uint64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_fa_576_512.cpp
  iqk_fa_512_512.cpp
  iqk_fa_320_256.cpp
  iqk_fa_192_128.cpp
  iqk_fa_192_192.cpp
  iqk_fa_256_256.cpp
  iqk_fa_128_128.cpp
  iqk_fa_96_96.cpp
  iqk_fa_64_64.cpp
  iqk_gemm_floats.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_floats.cpp(637,9): warning C4065: switch statement contains 'default' but no 'case' labels [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_kquants.cpp
  iqk_gemm_ktquants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(174,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(174,23):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(103,8):
          while compiling class template '`anonymous-namespace'::Trellis3'
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(216,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(266,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_iquants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(316,30): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(332,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(365,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_iqk_quants.cpp
  iqk_gemm_1bit.cpp
  Generating Code...
  Compiling...
  iqk_gemm_legacy_quants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_legacy_quants.cpp(2623,29): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_quantize.cpp
  iqk_cpu_ops.cpp
  Generating Code...
  Auto build dll exports
     Creating library D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/ggml/src/Release/ggml.lib and object D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/ggml/src/Release/ggml.exp
  ggml.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\ggml.dll
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/src/CMakeLists.txt
  llama.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(683,52): warning C4805: '!=': unsafe mix of type 'const int' and type 'const bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(714,52): warning C4805: '!=': unsafe mix of type 'int' and type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\a

... [TRUNCATED] ...

us/tok | 48.44%)
   Unaccounted / OMP & Sampling :  36657.06 ms (381844.4 us/tok | 19.99%) | Total Wall=183346.09 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    38.15%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    22.03%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    30.11%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.24%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.47%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 201s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.39 GB Available
   Active Drive Space : 219.98 GB Total / 126.94 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    592.87 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2364.96 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9209.03 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10962.85 MB/s
   RND4K Q32T16 Read                  :    692.74 MB/s (  177342 IOPS)
   RND4K Q1T1  Read                   :    786.60 MB/s (Latency: 4.97 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     69.55 GB/s
   AVX2 256-bit Sequential Write BW   :     62.61 GB/s
   STREAM Triad (A = B + s*C) BW      :     46.16 GB/s
   Random Pointer-Chase Latency       :     90.45 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.38 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.53 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.29 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.53 tps | Avg=0.53 tps | Hit=73.6% | NVMe=531.2 MB/s (51661.71 MB, QD=64) | RSS=13970.4 MB

 >>> [Apex-Model-Response] <think>
<think>
<th>
<thinking>
<thinking<th>
Let me user this question is a question about the user asks about "Explain why the why hybrid Gate why Gate DeltaNet Gate Net attention Net with Net MoE and E LB co-eco and sequential KB-1 sequential MB NV sequential NV
================================================================================

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM 5.3 Flash | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 45L, H=4096, V=154880 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 288 Exp/Lyr (Top-8, 12384 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 94.85 GB GGUF | 88.63 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=753.25 MB (33792 B/tok)
   LRFU Cache / Staging Ring    : 5559.38 MB (593/12384 exp = 4.79% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.71 MB | End=13454.79 MB | Peak=14037.62 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (70 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "<think>
<think>
<th>
<thinking>
<thinking<th>
Let me user this question is a question about the user asks about "Explain why the why hybrid Gate why Gate DeltaNet Gate Net attention Net with Net MoE and E LB co-eco and sequential KB-1 sequential MB NV sequential NV DMA"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=42.9% | AvgMargin=1.279 | MinMargin=0.023
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 131114.48 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   18.90 |  53.4% |   15724 |   18.74 | 2808.42 | 20 |232 | 84 | 1511936.0 |
   |    3 |     397 | >\n            |   12.80 |   6.2% |     318 |   12.73 | 2808.42 |  0 |  0 |  0 | 1511936.0 |
   |    4 |   13699 | <th            |   14.70 |  18.4% |     334 |   14.61 | 1898.60 |148 |128 | 60 | 1004448.0 |
   |    5 |     766 | ink            |   22.04 |  99.6% |     307 |   14.17 | 1898.60 |  0 |  0 |  0 | 1004448.0 |
   |    6 |     397 | >\n            |   12.54 |  13.7% |      29 |   12.50 | 2379.76 |137 |142 | 57 | 1019392.0 |
   |    7 |   13699 | <th            |   16.29 |  41.2% |     522 |   16.02 | 2379.76 |  0 |  0 |  0 | 1019392.0 |
   |    8 |     397 | >\n            |   17.08 |  39.3% |    1339 |   16.33 | 1392.31 |195 | 99 | 42 | 729984.0 |
   |   36 |   29136 |  Gate          |   15.35 |  36.3% |     479 |   14.86 | 2364.16 | 84 |165 | 87 | 1307712.0 |
   |   37 |    3170 |  why           |   16.44 |  65.8% |   34464 |   13.18 | 2364.16 |  0 |  0 |  0 | 1307712.0 |
   |   20 |    3405 |  question      |   16.21 |  30.6% |     374 |   15.58 | 2074.98 |108 |170 | 58 | 1149312.0 |
   |   21 |     374 |  is            |   15.85 |  19.4% |   15504 |   14.87 | 2074.98 |  0 |  0 |  0 | 1149312.0 |
   |   62 |   24384 |  NV            |   15.58 |  36.6% |   50665 |   15.35 | 1712.67 |147 |132 | 57 | 974848.0 |
   |   63 |   50665 |  sequential    |   14.36 |  20.5% |   25372 |   14.09 | 1712.67 |  0 |  0 |  0 | 974848.0 |
   |   64 |   24384 |  NV            |   17.08 |  41.8% |   25372 |   17.00 | 1698.18 |165 |116 | 55 | 920864.0 |
   |   65 |   25372 |  DMA           |   17.65 |  62.3% |   81911 |   16.44 | 1698.18 |  0 |  0 |  0 | 920864.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 131.114s, TTFT=131114.48ms): Avg=0.53 | Min=0.53 | Max=0.53 tps
   Prefill Chunks (1): C1:70t/0.5tps/74%
   Decode  (64 tok, 122.639s): Avg=0.52 | Min=0.36 | Max=0.73 tps
   Latency (ms) : Min=1365.02 | P10=1453.93 | P25=1875.12 | P50=1947.85 | P75=1991.61 | P90=2074.98 | P95=2379.76 | P99=2808.42 | Max=2808.42
   Mean/SD/Jitt : Mean=1916.24ms | StdDev=280.15ms | Jitter=103.85ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=21703 (63.33%) | Lookahead=4452 (+12.99%) | ColdMiss=8117 (23.68%) | EFF HIT=76.32%
   Lookahead    : 6853 prefetched -> 4452 consumed (65.0% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64= 76.3% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  391 | 215 | 210 | 74.3%|3054.69 | | L24 |  816 |  582 |  81 | 153 | 81.2%|2084.38 |
   | L04 |  816 |  370 | 121 | 325 | 60.2%|3981.88 | | L25 |  816 |  576 |  80 | 160 | 80.4%|2249.69 |
   | L05 |  816 |  382 | 144 | 290 | 64.5%|3687.19 | | L26 |  816 |  560 |  95 | 161 | 80.3%|2041.25 |
   | L06 |  816 |  398 | 162 | 256 | 68.6%|3435.62 | | L27 |  816 |  546 |  84 | 186 | 77.2%|2501.25 |
   | L07 |  816 |  469 | 135 | 212 | 74.0%|2918.12 | | L28 |  816 |  507 | 105 | 204 | 75.0%|2680.94 |
   | L08 |  816 |  446 | 126 | 244 | 70.1%|3320.62 | | L29 |  816 |  543 |  98 | 175 | 78.6%|2314.38 |
   | L09 |  816 |  443 | 118 | 255 | 68.8%|3234.38 | | L30 |  816 |  516 | 103 | 197 | 75.9%|2494.06 |
   | L10 |  816 |  424 | 152 | 240 | 70.6%|3234.38 | | L31 |  816 |  519 |  97 | 200 | 75.5%|2609.06 |
   | L11 |  816 |  492 | 110 | 214 | 73.8%|3571.88 | | L32 |  816 |  514 | 102 | 200 | 75.5%|2688.12 |
   | L12 |  816 |  503 | 114 | 199 | 75.6%|3123.88 | | L33 |  816 |  547 |  99 | 170 | 79.2%|2443.75 |
   | L13 |  816 |  532 |  83 | 201 | 75.4%|2458.12 | | L34 |  816 |  526 | 116 | 174 | 78.7%|2400.62 |
   | L14 |  816 |  505 | 101 | 210 | 74.3%|2839.06 | | L35 |  816 |  524 | 124 | 168 | 79.4%|2343.12 |
   | L15 |  816 |  528 |  91 | 197 | 75.9%|2515.62 | | L36 |  816 |  515 | 129 | 172 | 78.9%|2379.06 |
   | L16 |  816 |  512 |  99 | 205 | 74.9%|2637.81 | | L37 |  816 |  531 | 107 | 178 | 78.2%|2357.50 |
   | L17 |  816 |  531 |  87 | 198 | 75.7%|2666.56 | | L38 |  816 |  557 | 104 | 155 | 81.0%|2141.88 |
   | L18 |  816 |  599 |  60 | 157 | 80.8%|1926.25 | | L39 |  816 |  531 | 114 | 171 | 79.0%|2278.44 |
   | L19 |  816 |  570 |  79 | 167 | 79.5%|2070.00 | | L40 |  816 |  511 | 121 | 184 | 77.5%|2515.62 |
   | L20 |  816 |  612 |  56 | 148 | 81.9%|1883.12 | | L41 |  816 |  517 | 117 | 182 | 77.7%|2515.62 |
   | L21 |  816 |  589 |  66 | 161 | 80.3%|2105.94 | | L42 |  816 |  546 |  98 | 172 | 78.9%|2256.88 |
   | L22 |  816 |  600 |  70 | 146 | 82.1%|1962.19 | | L43 |  816 |  558 |  91 | 167 | 79.5%|2113.12 |
   | L23 |  816 |  578 |  78 | 160 | 80.4%|2055.62 | | L44 |  816 |  503 | 120 | 193 | 76.3%|3241.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 116789.27 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=65127.56 MB)
   SSD Data/Token (Decode)      : Avg=1017.618 MB/tok (Min=712.875 | P50=1043.438 | P95=1277.062 | Max=1476.500 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2551 Batches | 46571 Reads | 0 LBA Merges (Avg 2568.0 KB/req)
   SSD Read Bandwidth           : Avg=549.86 MB/s | Peak=4484.30 MB/s (100.0% of 592.9 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=117776.31 MB | Write=128.00 MB | Syscalls=58145
   Sync Stall vs Async DMA      : SyncStall=109713.77 ms | AsyncOverlapped=200149.76 ms (64.6% Overlapped)
   RAM Traffic & Effective BW   : 777.28 GB moved | Eff=3.06 GB/s (STREAM Triad Max=46.16 GB/s)
   CPU Time & Utilization       : User=256.984s + Sys=9.469s (Wall=270.816s) | SysUtil=24.6% | ThrUtil=24.6% | 55.72 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  32420.49 ms (241943.9 us/tok | 12.78%)
   MoE AVX2 Q8 Expert Compute   :  43439.00 ms (324171.6 us/tok | 17.12%)
   Router + Lookahead Dispatch  :    632.21 ms ( 4718.0 us/tok |  0.25%)
   LM Head Output Projection    :   1243.00 ms ( 9276.1 us/tok |  0.49%)
   Foreground NVMe Sync Stall   : 109713.77 ms (818759.5 us/tok | 43.24%)
   Unaccounted / OMP & Sampling :  66305.48 ms (494817.0 us/tok | 26.13%) | Total Wall=253753.95 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    35.34%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    24.92%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    30.77%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.36%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.61%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5653.12 MB (603 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.90 tps | Avg=0.90 tps | Hit=89.2% | NVMe=531.0 MB/s (74277.59 MB, QD=64) | RSS=14114.8 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.88 tps | Avg=0.89 tps | Hit=88.9% | NVMe=531.1 MB/s (145202.09 MB, QD=64) | RSS=14115.5 MB
[LIVE-DECODE] 2/128 tok | Avg=0.28 tps | Hit=88.9% (LA:+0.1%) | NVMe=531.4 MB/s (148490.09 MB) | RSS=13950.1 MB
[LIVE-DECODE] 4/128 tok | Avg=0.32 tps | Hit=88.9% (LA:+0.2%) | NVMe=531.7 MB/s (151125.27 MB) | RSS=13805.9 MB
[LIVE-DECODE] 6/128 tok | Avg=0.36 tps | Hit=88.8% (LA:+0.3%) | NVMe=532.1 MB/s (153469.40 MB) | RSS=13639.9 MB
[LIVE-DECODE] 8/128 tok | Avg=0.38 tps | Hit=88.8% (LA:+0.4%) | NVMe=532.6 MB/s (155649.65 MB) | RSS=13562.4 MB
[LIVE-DECODE] 10/128 tok | Avg=0.41 tps | Hit=88.8% (LA:+0.4%) | NVMe=533.1 MB/s (157599.27 MB) | RSS=13543.0 MB
[LIVE-DECODE] 12/128 tok | Avg=0.43 tps | Hit=88.8% (LA:+0.5%) | NVMe=533.6 MB/s (159647.71 MB) | RSS=13520.4 MB
[LIVE-DECODE] 14/128 tok | Avg=0.44 tps | Hit=88.8% (LA:+0.6%) | NVMe=534.1 MB/s (161641.52 MB) | RSS=13529.7 MB
[LIVE-DECODE] 16/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+0.6%) | NVMe=534.7 MB/s (163743.21 MB) | RSS=13529.7 MB
[LIVE-DECODE] 18/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+0.7%) | NVMe=534.3 MB/s (165782.65 MB) | RSS=13529.3 MB
[LIVE-DECODE] 20/128 tok | Avg=0.46 tps | Hit=88.7% (LA:+0.8%) | NVMe=534.8 MB/s (167775.09 MB) | RSS=13529.3 MB
[LIVE-DECODE] 22/128 tok | Avg=0.46 tps | Hit=88.7% (LA:+0.8%) | NVMe=535.2 MB/s (169944.15 MB) | RSS=13538.7 MB
[LIVE-DECODE] 24/128 tok | Avg=0.46 tps | Hit=88.7% (LA:+0.9%) | NVMe=535.5 MB/s (172122.77 MB) | RSS=13538.7 MB
[LIVE-DECODE] 26/128 tok | Avg=0.47 tps | Hit=88.7% (LA:+1.0%) | NVMe=535.8 MB/s (174170.09 MB) | RSS=13536.2 MB
[LIVE-DECODE] 28/128 tok | Avg=0.47 tps | Hit=88.6% (LA:+1.0%) | NVMe=535.8 MB/s (176170.84 MB) | RSS=13529.3 MB
[LIVE-DECODE] 30/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.1%) | NVMe=536.2 MB/s (177989.09 MB) | RSS=13548.0 MB
[LIVE-DECODE] 32/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.1%) | NVMe=536.7 MB/s (179686.46 MB) | RSS=13548.0 MB
[LIVE-DECODE] 34/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.2%) | NVMe=537.1 MB/s (181678.34 MB) | RSS=13548.0 MB
[LIVE-DECODE] 36/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.3%) | NVMe=537.4 MB/s (183836.27 MB) | RSS=13548.0 MB
[LIVE-DECODE] 38/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.3%) | NVMe=537.7 MB/s (185962.71 MB) | RSS=13539.9 MB
[LIVE-DECODE] 40/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.4%) | NVMe=538.0 MB/s (187879.15 MB) | RSS=13540.1 MB
[LIVE-DECODE] 42/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.5%) | NVMe=538.3 MB/s (189974.46 MB) | RSS=13540.2 MB
[LIVE-DECODE] 44/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.5%) | NVMe=538.7 MB/s (192302.02 MB) | RSS=13548.4 MB
[LIVE-DECODE] 46/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.6%) | NVMe=538.8 MB/s (194566.59 MB) | RSS=13548.4 MB
[LIVE-DECODE] 48/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.7%) | NVMe=539.1 MB/s (196637.02 MB) | RSS=13548.4 MB
[LIVE-DECODE] 50/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.7%) | NVMe=539.5 MB/s (198808.40 MB) | RSS=13548.1 MB
[LIVE-DECODE] 52/128 tok | Avg=0.50 tps | Hit=88.5% (LA:+1.8%) | NVMe=539.8 MB/s (200715.27 MB) | RSS=13548.1 MB
[LIVE-DECODE] 54/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+1.9%) | NVMe=540.1 MB/s (202490.02 MB) | RSS=13548.1 MB
[LIVE-DECODE] 56/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.0%) | NVMe=540.3 MB/s (204853.96 MB) | RSS=13548.0 MB
[LIVE-DECODE] 58/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.0%) | NVMe=540.6 MB/s (207062.65 MB) | RSS=13548.0 MB
[LIVE-DECODE] 60/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.1%) | NVMe=540.8 MB/s (208901.27 MB) | RSS=13548.0 MB
[LIVE-DECODE] 62/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.1%) | NVMe=541.2 MB/s (210775.34 MB) | RSS=13548.0 MB
[LIVE-DECODE] 64/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.2%) | NVMe=541.5 MB/s (212614.96 MB) | RSS=13529.3 MB
[LIVE-DECODE] 66/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.3%) | NVMe=541.8 MB/s (214711.09 MB) | RSS=13538.7 MB
[LIVE-DECODE] 68/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.3%) | NVMe=541.8 MB/s (216703.52 MB) | RSS=13548.1 MB
[LIVE-DECODE] 70/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.4%) | NVMe=542.0 MB/s (218583.77 MB) | RSS=13548.1 MB
[LIVE-DECODE] 72/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.5%) | NVMe=542.2 MB/s (220449.15 MB) | RSS=13548.1 MB
[LIVE-DECODE] 74/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.5%) | NVMe=542.5 MB/s (222329.52 MB) | RSS=13548.1 MB
[LIVE-DECODE] 76/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.6%) | NVMe=542.8 MB/s (224333.96 MB) | RSS=13538.7 MB
[LIVE-DECODE] 78/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.6%) | NVMe=543.0 MB/s (226278.59 MB) | RSS=13538.7 MB
[LIVE-DECODE] 80/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.7%) | NVMe=543.2 MB/s (228052.27 MB) | RSS=13538.7 MB
[LIVE-DECODE] 82/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.7%) | NVMe=543.4 MB/s (229578.77 MB) | RSS=13548.1 MB
[LIVE-DECODE] 84/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.7%) | NVMe=543.5 MB/s (231160.34 MB) | RSS=13548.0 MB
[LIVE-DECODE] 86/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.8%) | NVMe=543.6 MB/s (232828.46 MB) | RSS=13548.1 MB
[LIVE-DECODE] 88/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.8%) | NVMe=543.8 MB/s (234557.09 MB) | RSS=13548.1 MB
[LIVE-DECODE] 90/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.9%) | NVMe=544.0 MB/s (236348.09 MB) | RSS=13548.1 MB
[LIVE-DECODE] 92/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.9%) | NVMe=544.3 MB/s (238193.84 MB) | RSS=13548.1 MB
[LIVE-DECODE] 94/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.0%) | NVMe=544.5 MB/s (240147.96 MB) | RSS=13548.1 MB
[LIVE-DECODE] 96/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.0%) | NVMe=544.8 MB/s (241871.71 MB) | RSS=13548.1 MB
[LIVE-DECODE] 98/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.1%) | NVMe=544.9 MB/s (243673.84 MB) | RSS=13547.8 MB
[LIVE-DECODE] 100/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.1%) | NVMe=545.2 MB/s (245370.52 MB) | RSS=13538.7 MB
[LIVE-DECODE] 102/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.2%) | NVMe=545.3 MB/s (247108.46 MB) | RSS=13538.7 MB
[LIVE-DECODE] 104/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+3.2%) | NVMe=545.4 MB/s (248928.02 MB) | RSS=13548.1 MB
[LIVE-DECODE] 106/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+3.2%) | NVMe=545.6 MB/s (250821.21 MB) | RSS=13548.1 MB
[LIVE-DECODE] 108/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.3%) | NVMe=545.8 MB/s (252777.59 MB) | RSS=13548.0 MB
[LIVE-DECODE] 110/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.3%) | NVMe=546.0 MB/s (254556.02 MB) | RSS=13548.1 MB
[LIVE-DECODE] 112/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.4%) | NVMe=546.2 MB/s (256344.46 MB) | RSS=13540.1 MB
[LIVE-DECODE] 114/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.4%) | NVMe=546.3 MB/s (258227.52 MB) | RSS=13529.3 MB
[LIVE-DECODE] 116/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.5%) | NVMe=546.5 MB/s (259907.09 MB) | RSS=13538.7 MB
[LIVE-DECODE] 118/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.5%) | NVMe=546.6 MB/s (261633.65 MB) | RSS=13548.1 MB
[LIVE-DECODE] 120/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.6%) | NVMe=546.8 MB/s (263484.84 MB) | RSS=13548.1 MB
[LIVE-DECODE] 122/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.6%) | NVMe=546.9 MB/s (265425.65 MB) | RSS=13548.0 MB
[LIVE-DECODE] 124/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.7%) | NVMe=547.1 MB/s (267128.34 MB) | RSS=13548.0 MB
[LIVE-DECODE] 126/128 tok | Avg=0.55 tps | Hit=88.1% (LA:+3.7%) | NVMe=547.2 MB/s (268742.52 MB) | RSS=13548.0 MB
[LIVE-DECODE] 128/128 tok | Avg=0.55 tps | Hit=88.1% (LA:+3.7%) | NVMe=547.4 MB/s (270496.09 MB) | RSS=13540.9 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM 5.3 Flash | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 45L, H=4096, V=154880 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 288 Exp/Lyr (Top-8, 12384 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 94.85 GB GGUF | 88.63 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=753.25 MB (33792 B/tok)
   LRFU Cache / Staging Ring    : 5653.12 MB (603/12384 exp = 4.87% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.68 MB | End=13540.92 MB | Peak=14179.12 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : " single coal LBA-sorting coalesced QED LBA-sorted QD32 NVMe read and pass and register-blocked-blocked-blocked multi-blocked multi-row Q8_K GE pass. Explain why elimination PCIe amplification derive asymptotic throughput decode throughput.</think>In high-throughput Mixt-of- (Mo) model inference with NVMe offloading achieving token generation requires overlapping Gen PCIe Gen DMA transfers AVX compute pinned attention state recurrent state trunk cache pinned RAM expert cache locked RAM horizon router co prefetching over activations directly decode prefill long context tokens inverted expert gro..."
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=48.0% | AvgMargin=1.558 | MinMargin=0.009
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 573036.52 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   24.96 | 100.0% |    1062 |   16.43 | 3574.50 | 37 |166 |133 | 1683456.0 |
   |    3 |   39929 |  LB            |   17.75 |  78.0% |   33903 |   16.24 | 3574.50 |  0 |  0 |  0 | 1683456.0 |
   |    4 |      32 | A              |   14.08 |  30.6% |    1911 |   13.59 | 2615.53 | 81 |171 | 84 | 1349216.0 |
   |    5 |   46254 | -sort          |   18.02 |  42.5% |    1331 |   17.61 | 2615.53 |  0 |  0 |  0 | 1349216.0 |
   |    6 |     287 | ing            |   14.36 |  38.6% |   11492 |   11.93 | 2226.16 |114 |152 | 70 | 1200192.0 |
   |    7 |   11492 |  coal          |   16.09 |  54.1% |    1207 |   14.51 | 2226.16 |  0 |  0 |  0 | 1200192.0 |
   |    8 |    3300 | esc            |   18.05 |  93.7% |     642 |   13.98 | 1998.70 |127 |136 | 73 | 1116288.0 |
   |   56 |  154842 | </think>       |   14.32 |  56.1% |     641 |   13.02 | 2222.20 | 92 |172 | 72 | 1210336.0 |
   |   57 |     641 | In             |   15.30 |  41.7% |     565 |   13.90 | 2222.20 |  0 |  0 |  0 | 1210336.0 |
   |   44 |    3170 |  why           |   17.45 |  85.5% |     419 |   13.32 | 2157.38 |119 |141 | 76 | 1191712.0 |
   |   45 |   42687 |  elimination   |   15.17 |  16.8% |   21673 |   14.81 | 2157.38 |  0 |  0 |  0 | 1191712.0 |
   |  126 |     291 | ed             |   14.96 |  32.3% |    1207 |   14.08 | 1518.13 |191 | 88 | 57 | 826464.0 |
   |  127 |    9421 | -block         |   17.23 |  54.2% |    7299 |   15.51 | 1518.13 |  0 |  0 |  0 | 826464.0 |
   |  128 |    9421 | -block         |   14.61 |  29.9% |    1207 |   13.52 | 1595.50 |190 | 93 | 53 | 897824.0 |
   |  129 |     291 | ed             |   20.50 |  98.5% |   29819 |   14.11 | 1595.50 |  0 |  0 |  0 | 897824.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 573.037s, TTFT=573036.52ms): Avg=0.89 | Min=0.88 | Max=0.90 tps
   Prefill Chunks (2): C1:256t/0.9tps/89% | C2:256t/0.9tps/89%
   Decode  (128 tok, 234.100s): Avg=0.55 | Min=0.28 | Max=0.70 tps
   Latency (ms) : Min=1423.28 | P10=1565.39 | P25=1651.36 | P50=1761.35 | P75=1944.75 | P90=2120.47 | P95=2222.20 | P99=3574.50 | Max=3574.50
   Mean/SD/Jitt : Mean=1828.91ms | StdDev=305.95ms | Jitter=75.26ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=163160 (84.30%) | Lookahead=7250 (+3.75%) | ColdMiss=23126 (11.95%) | EFF HIT=88.05%
   Lookahead    : 12666 prefetched -> 7250 consumed (57.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 88.7% | @64= 88.4% | @128= 88.1% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3600 | 451 | 557 | 87.9%|7245.00 | | L24 | 4608 | 3993 | 117 | 498 | 89.2%|5225.31 |
   | L04 | 4608 | 3632 | 205 | 771 | 83.3%|8754.38 | | L25 | 4608 | 3952 | 129 | 527 | 88.6%|6037.50 |
   | L05 | 4608 | 3614 | 289 | 705 | 84.7%|8215.31 | | L26 | 4608 | 3977 | 140 | 491 | 89.3%|5311.56 |
   | L06 | 4608 | 3661 | 301 | 646 | 86.0%|7712.19 | | L27 | 4608 | 3873 | 134 | 601 | 87.0%|7029.38 |
   | L07 | 4608 | 3813 | 251 | 544 | 88.2%|6360.94 | | L28 | 4608 | 3891 | 157 | 560 | 87.8%|6087.81 |
   | L08 | 4608 | 3868 | 152 | 588 | 87.2%|6770.62 | | L29 | 4608 | 3914 | 158 | 536 | 88.4%|5987.19 |
   | L09 | 4608 | 3792 | 176 | 640 | 86.1%|7000.62 | | L30 | 4608 | 3900 | 170 | 538 | 88.3%|5721.25 |
   | L10 | 4608 | 3719 | 231 | 658 | 85.7%|7374.38 | | L31 | 4608 | 3821 | 139 | 648 | 85.9%|7144.38 |
   | L11 | 4608 | 3842 | 181 | 585 | 87.3%|8484.38 | | L32 | 4608 | 3824 | 166 | 618 | 86.6%|6720.31 |
   | L12 | 4608 | 3890 | 169 | 549 | 88.1%|6968.00 | | L33 | 4608 | 3889 | 167 | 552 | 88.0%|6555.00 |
   | L13 | 4608 | 3952 | 126 | 530 | 88.5%|5527.19 | | L34 | 4608 | 3900 | 209 | 499 | 89.2%|5699.69 |
   | L14 | 4608 | 3898 | 156 | 554 | 88.0%|6138.12 | | L35 | 4608 | 3863 | 211 | 534 | 88.4%|6008.75 |
   | L15 | 4608 | 3907 | 155 | 546 | 88.2%|5865.00 | | L36 | 4608 | 3841 | 245 | 522 | 88.7%|6095.00 |
   | L16 | 4608 | 3914 | 163 | 531 | 88.5%|5951.25 | | L37 | 4608 | 3902 | 180 | 526 | 88.6%|5714.06 |
   | L17 | 4608 | 3972 | 107 | 529 | 88.5%|5548.75 | | L38 | 4608 | 3897 | 181 | 530 | 88.5%|5886.56 |
   | L18 | 4608 | 4034 |  85 | 489 | 89.4%|5390.62 | | L39 | 4608 | 3906 | 161 | 541 | 88.3%|5721.25 |
   | L19 | 4608 | 4061 | 103 | 444 | 90.4%|4513.75 | | L40 | 4608 | 3923 | 171 | 514 | 88.8%|5591.88 |
   | L20 | 4608 | 3996 | 127 | 485 | 89.5%|5290.00 | | L41 | 4608 | 3885 | 197 | 526 | 88.6%|5994.38 |
   | L21 | 4608 | 3985 | 130 | 493 | 89.3%|5297.19 | | L42 | 4608 | 3960 | 137 | 511 | 88.9%|5361.88 |
   | L22 | 4608 | 4027 | 103 | 478 | 89.6%|5038.44 | | L43 | 4608 | 3974 | 155 | 479 | 89.6%|5261.25 |
   | L23 | 4608 | 4003 | 116 | 489 | 89.4%|5088.75 | | L44 | 4608 | 3895 | 149 | 564 | 87.8%|7612.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 270496.09 MB (Load=6361.84 | Prefill=138840.25 | Warmup=0.00 | Decode=125294.00 MB)
   SSD Data/Token (Decode)      : Avg=978.859 MB/tok (Min=763.250 | P50=958.219 | P95=1172.062 | Max=1644.000 MB) | Prefill=271.172 MB/tok
   NVMe Batches / Requests      : 5244 Batches | 109637 Reads | 0 LBA Merges (Avg 2526.4 KB/req)
   SSD Read Bandwidth           : Avg=547.40 MB/s | Peak=4580.36 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=270505.12 MB | Write=0.01 MB | Syscalls=113722
   Sync Stall vs Async DMA      : SyncStall=315759.20 ms | AsyncOverlapped=481881.65 ms (60.4% Overlapped)
   RAM Traffic & Effective BW   : 2783.29 GB moved | Eff=3.45 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=1308.297s + Sys=21.047s (Wall=823.902s) | SysUtil=40.3% | ThrUtil=40.3% | 37.31 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 172232.33 ms (269113.0 us/tok | 21.34%)
   MoE AVX2 Q8 Expert Compute   : 197827.86 ms (309106.0 us/tok | 24.51%)
   Router + Lookahead Dispatch  :   3117.31 ms ( 4870.8 us/tok |  0.39%)
   LM Head Output Projection    :   2489.33 ms ( 3889.6 us/tok |  0.31%)
   Foreground NVMe Sync Stall   : 315759.20 ms (493373.7 us/tok | 39.12%)
   Unaccounted / OMP & Sampling : 115710.49 ms (180797.6 us/tok | 14.34%) | Total Wall=807136.53 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    59.81%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.50%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    17.34%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.97%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.38%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 111101.9ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='\nSummarize LBACoalesce in one sentence.\nSummarize LB'
[Stage 3] /v1/chat/completions (stream=true SSE) 44673.2ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5409.38 MB (577 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=0.91 tps | Avg=0.91 tps | Hit=89.2% | NVMe=533.2 MB/s (74277.59 MB, QD=64) | RSS=13871.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=0.84 tps | Avg=0.87 tps | Hit=88.9% | NVMe=532.7 MB/s (145295.52 MB, QD=64) | RSS=13871.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=88.9% | NVMe=532.3 MB/s (214799.34 MB, QD=64) | RSS=13871.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=88.9% | NVMe=532.3 MB/s (283922.65 MB, QD=64) | RSS=13871.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=0.88 tps | Avg=0.88 tps | Hit=89.0% | NVMe=532.2 MB/s (352711.65 MB, QD=64) | RSS=13871.1 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=89.0% | NVMe=532.2 MB/s (420869.27 MB, QD=64) | RSS=13871.1 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=89.0% | NVMe=531.8 MB/s (488245.34 MB, QD=64) | RSS=13871.1 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=89.1% | NVMe=531.7 MB/s (554073.90 MB, QD=64) | RSS=13871.9 MB
[LIVE-DECODE] 2/64 tok | Avg=0.40 tps | Hit=89.1% (LA:+0.0%) | NVMe=531.8 MB/s (556479.90 MB) | RSS=13876.5 MB
[LIVE-DECODE] 4/64 tok | Avg=0.36 tps | Hit=89.1% (LA:+0.0%) | NVMe=531.8 MB/s (559379.21 MB) | RSS=13621.3 MB
[LIVE-DECODE] 6/64 tok | Avg=0.39 tps | Hit=89.1% (LA:+0.1%) | NVMe=531.9 MB/s (561775.40 MB) | RSS=13529.8 MB
[LIVE-DECODE] 8/64 tok | Avg=0.41 tps | Hit=89.1% (LA:+0.1%) | NVMe=532.1 MB/s (564116.40 MB) | RSS=13419.4 MB
[LIVE-DECODE] 10/64 tok | Avg=0.42 tps | Hit=89.1% (LA:+0.1%) | NVMe=532.2 MB/s (566273.09 MB) | RSS=13363.4 MB
[LIVE-DECODE] 12/64 tok | Avg=0.43 tps | Hit=89.1% (LA:+0.1%) | NVMe=532.4 MB/s (568477.52 MB) | RSS=13323.9 MB
[LIVE-DECODE] 14/64 tok | Avg=0.44 tps | Hit=89.0% (LA:+0.1%) | NVMe=532.5 MB/s (570583.40 MB) | RSS=13310.9 MB
[LIVE-DECODE] 16/64 tok | Avg=0.45 tps | Hit=89.0% (LA:+0.2%) | NVMe=532.7 MB/s (572697.09 MB) | RSS=13295.2 MB
[LIVE-DECODE] 18/64 tok | Avg=0.45 tps | Hit=89.0% (LA:+0.2%) | NVMe=532.9 MB/s (574993.90 MB) | RSS=13295.2 MB
[LIVE-DECODE] 20/64 tok | Avg=0.46 tps | Hit=89.0% (LA:+0.2%) | NVMe=533.0 MB/s (577239.46 MB) | RSS=13295.2 MB
[LIVE-DECODE] 22/64 tok | Avg=0.46 tps | Hit=89.0% (LA:+0.2%) | NVMe=533.2 MB/s (579315.46 MB) | RSS=13295.2 MB
[LIVE-DECODE] 24/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.2%) | NVMe=533.3 MB/s (581565.90 MB) | RSS=13295.2 MB
[LIVE-DECODE] 26/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=533.5 MB/s (583846.09 MB) | RSS=13304.5 MB
[LIVE-DECODE] 28/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=533.6 MB/s (586124.40 MB) | RSS=13304.6 MB
[LIVE-DECODE] 30/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=533.8 MB/s (588219.21 MB) | RSS=13304.6 MB
[LIVE-DECODE] 32/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=533.9 MB/s (590308.34 MB) | RSS=13304.5 MB
[LIVE-DECODE] 34/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.3%) | NVMe=534.0 MB/s (592218.65 MB) | RSS=13304.5 MB
[LIVE-DECODE] 36/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.1 MB/s (594383.96 MB) | RSS=13304.5 MB
[LIVE-DECODE] 38/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.2 MB/s (596320.09 MB) | RSS=13295.2 MB
[LIVE-DECODE] 40/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.3 MB/s (598268.96 MB) | RSS=13295.2 MB
[LIVE-DECODE] 42/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.5 MB/s (600236.02 MB) | RSS=13304.5 MB
[LIVE-DECODE] 44/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.6 MB/s (602103.02 MB) | RSS=13304.5 MB
[LIVE-DECODE] 46/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.6 MB/s (603994.84 MB) | RSS=13304.5 MB
[LIVE-DECODE] 48/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.8 MB/s (606210.34 MB) | RSS=13304.5 MB
[LIVE-DECODE] 50/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.5%) | NVMe=534.9 MB/s (608237.40 MB) | RSS=13304.5 MB
[LIVE-DECODE] 52/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=535.0 MB/s (610643.96 MB) | RSS=13304.5 MB
[LIVE-DECODE] 54/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.5%) | NVMe=535.1 MB/s (612746.71 MB) | RSS=13304.5 MB
[LIVE-DECODE] 56/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.5%) | NVMe=535.3 MB/s (614623.27 MB) | RSS=13304.6 MB
[LIVE-DECODE] 58/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.5%) | NVMe=535.5 MB/s (616607.90 MB) | RSS=13304.5 MB
[LIVE-DECODE] 60/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.6%) | NVMe=535.6 MB/s (618617.27 MB) | RSS=13304.5 MB
[LIVE-DECODE] 62/64 tok | Avg=0.50 tps | Hit=88.9% (LA:+0.6%) | NVMe=535.7 MB/s (620700.65 MB) | RSS=13304.5 MB
[LIVE-DECODE] 64/64 tok | Avg=0.50 tps | Hit=88.9% (LA:+0.6%) | NVMe=535.8 MB/s (622629.59 MB) | RSS=13304.5 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM 5.3 Flash | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 45L, H=4096, V=154880 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 288 Exp/Lyr (Top-8, 12384 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 94.85 GB GGUF | 88.63 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=753.25 MB (33792 B/tok)
   LRFU Cache / Staging Ring    : 5409.38 MB (577/12384 exp = 4.66% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.67 MB | End=13304.49 MB | Peak=13972.89 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : " high-throughput Mixtures of Mixtures-of-Expert (MoE) language inference with NVMe offloading achieving low-lat token generation requires overlapping Genie DMAand compute DMA transfers AVX compute attention dense recurrent attention recurrent state trunking Window cachehoriz dual lookahead coactivation preching% of activations direct RAM without CPU execution"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=43.9% | AvgMargin=1.572 | MinMargin=0.007
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    1550 |  high          |   25.48 | 100.0% |     279 |   13.45 | 2317204.97 |  0 |  0 |  0 |     0.0 |
   |    2 |   42503 | -through       |   27.04 | 100.0% |   63308 |   16.24 | 2505.53 |130 |105 |101 | 1231872.0 |
   |    3 |     628 | put            |   23.73 |  99.6% |   19183 |   17.58 | 2505.53 |  0 |  0 |  0 | 1231872.0 |
   |    4 |   19183 |  Mix           |   17.39 |  84.5% |   19705 |   14.33 | 2992.51 | 39 |215 | 82 | 1484448.0 |
   |    5 |   18482 | tures          |   16.37 |  54.3% |      68 |   15.04 | 2992.51 |  0 |  0 |  0 | 1484448.0 |
   |    6 |     315 |  of            |   13.92 |  18.4% |    8667 |   13.83 | 2215.47 |107 |152 | 77 | 1226848.0 |
   |    7 |   19183 |  Mix           |   18.45 |  89.7% |   57687 |   15.44 | 2215.47 |  0 |  0 |  0 | 1226848.0 |
   |    8 |   18482 | tures          |   16.65 |  62.5% |    4974 |   14.96 | 2134.19 |119 |142 | 75 | 1198592.0 |
   |   52 |   18547 |  dual          |   14.99 |  20.4% |   86025 |   14.43 | 2263.02 |107 |149 | 80 | 1232160.0 |
   |   53 |   86025 |  lookahead     |   13.07 |   7.8% |    9270 |   12.69 | 2263.02 |  0 |  0 |  0 | 1232160.0 |
   |    9 |    8667 | -of            |   17.27 |  47.5% |     315 |   17.04 | 2134.19 |  0 |  0 |  0 | 1198592.0 |
   |   18 |     448 |  with          |   16.53 |  65.9% |    4128 |   13.64 | 2089.10 |129 |132 | 75 | 1175968.0 |
   |   62 |   21984 |  RAM           |   16.11 |  41.3% |   33742 |   15.25 | 1922.08 |142 |124 | 70 | 1066688.0 |
   |   63 |    2041 |  without       |   15.58 |  48.8% |   28891 |   13.67 | 1922.08 |  0 |  0 |  0 | 1066688.0 |
   |   64 |   13931 |  CPU           |   16.17 |  32.7% |   11315 |   14.94 | 1812.69 |140 |147 | 49 | 987616.0 |
   |   65 |   11315 |  execution     |   14.77 |  16.3% |   15289 |   14.61 | 1812.69 |  0 |  0 |  0 | 987616.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2317.205s, TTFT=2317204.97ms): Avg=0.88 | Min=0.84 | Max=0.91 tps
   Prefill Chunks (8): C1:256t/0.9tps/89% | C2:256t/0.8tps/89% | C3:256t/0.9tps/89% | C4:256t/0.9tps/89%
                       C5:256t/0.9tps/89% | C6:256t/0.9tps/89% | C7:256t/0.9tps/89% | C8:256t/0.9tps/89%
   Decode  (64 tok, 127.177s): Avg=0.50 | Min=0.33 | Max=0.59 tps
   Latency (ms) : Min=1681.23 | P10=1772.89 | P25=1821.36 | P50=1930.95 | P75=2067.43 | P90=2215.47 | P95=2505.53 | P99=2992.51 | Max=2992.51
   Mean/SD/Jitt : Mean=1987.14ms | StdDev=250.24ms | Jitter=81.67ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (698880): RawRAM=617457 (88.35%) | Lookahead=4156 (+0.59%) | ColdMiss=77267 (11.06%) | EFF HIT=88.94%
   Lookahead    : 6991 prefetched -> 4156 consumed (59.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 89.0% | @64= 88.9% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |16640 |14180 | 235 |2225 | 86.6%|17681.25 | | L24 |16640 |14844 |  58 |1738 | 89.6%|13390.31 |
   | L04 |16640 |14248 | 115 |2277 | 86.3%|18033.44 | | L25 |16640 |14824 |  75 |1741 | 89.5%|13749.69 |
   | L05 |16640 |14217 | 164 |2259 | 86.4%|17882.50 | | L26 |16640 |14811 |  74 |1755 | 89.5%|13577.19 |
   | L06 |16640 |14237 | 182 |2221 | 86.7%|17710.00 | | L27 |16640 |14701 |  93 |1846 | 88.9%|14633.75 |
   | L07 |16640 |14509 | 155 |1976 | 88.1%|15740.62 | | L28 |16640 |14703 |  92 |1845 | 88.9%|14439.69 |
   | L08 |16640 |14500 | 101 |2039 | 87.7%|16100.00 | | L29 |16640 |14798 |  96 |1746 | 89.5%|13685.00 |
   | L09 |16640 |14513 |  99 |2028 | 87.8%|16121.56 | | L30 |16640 |14702 | 105 |1833 | 89.0%|14224.06 |
   | L10 |16640 |14364 | 136 |2140 | 87.1%|16905.00 | | L31 |16640 |14729 |  61 |1850 | 88.9%|14583.44 |
   | L11 |16640 |14688 | 135 |1817 | 89.1%|19031.25 | | L32 |16640 |14675 |  99 |1866 | 88.8%|14727.19 |
   | L12 |16640 |14742 | 103 |1795 | 89.2%|16565.75 | | L33 |16640 |14852 |  87 |1701 | 89.8%|13591.56 |
   | L13 |16640 |14916 |  84 |1640 | 90.1%|12800.94 | | L34 |16640 |14768 | 109 |1763 | 89.4%|13720.94 |
   | L14 |16640 |15019 |  80 |1541 | 90.7%|12276.25 | | L35 |16640 |14701 | 120 |1819 | 89.1%|14245.62 |
   | L15 |16640 |15110 |  88 |1442 | 91.3%|11485.62 | | L36 |16640 |14669 | 119 |1852 | 88.9%|14461.25 |
   | L16 |16640 |14940 |  86 |1614 | 90.3%|12700.31 | | L37 |16640 |14703 |  89 |1848 | 88.9%|14195.31 |
   | L17 |16640 |14795 |  62 |1783 | 89.3%|13792.81 | | L38 |16640 |14689 |  98 |1853 | 88.9%|14310.31 |
   | L18 |16640 |14917 |  53 |1670 | 90.0%|13002.19 | | L39 |16640 |14602 | 118 |1920 | 88.5%|14892.50 |
   | L19 |16640 |14875 |  60 |1705 | 89.8%|13052.50 | | L40 |16640 |14678 |  89 |1873 | 88.7%|14389.38 |
   | L20 |16640 |14829 |  64 |1747 | 89.5%|13512.50 | | L41 |16640 |14645 | 110 |1885 | 88.7%|14763.12 |
   | L21 |16640 |14927 |  57 |1656 | 90.0%|12865.62 | | L42 |16640 |14752 |  86 |1802 | 89.2%|13879.06 |
   | L22 |16640 |14886 |  71 |1683 | 89.9%|13102.81 | | L43 |16640 |14767 |  99 |1774 | 89.3%|13828.75 |
   | L23 |16640 |14804 |  69 |1767 | 89.4%|13656.25 | | L44 |16640 |14628 |  80 |1932 | 88.4%|17579.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 622629.59 MB (Load=6361.84 | Prefill=547712.06 | Warmup=0.00 | Decode=68555.69 MB)
   SSD Data/Token (Decode)      : Avg=1071.183 MB/tok (Min=933.500 | P50=1052.938 | P95=1203.281 | Max=1449.656 MB) | Prefill=267.438 MB/tok
   NVMe Batches / Requests      : 3857 Batches | 254534 Reads | 0 LBA Merges (Avg 2504.9 KB/req)
   SSD Read Bandwidth           : Avg=535.77 MB/s | Peak=4610.77 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=622638.62 MB | Write=0.01 MB | Syscalls=258593
   Sync Stall vs Async DMA      : SyncStall=1058811.32 ms | AsyncOverlapped=1150274.23 ms (52.1% Overlapped)
   RAM Traffic & Effective BW   : 7358.13 GB moved | Eff=3.01 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=4654.391s + Sys=47.688s (Wall=2460.010s) | SysUtil=47.8% | ThrUtil=47.8% | 44.20 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 629680.50 ms (298144.2 us/tok | 25.76%)
   MoE AVX2 Q8 Expert Compute   : 674518.08 ms (319374.1 us/tok | 27.59%)
   Router + Lookahead Dispatch  :  10408.78 ms ( 4928.4 us/tok |  0.43%)
   LM Head Output Projection    :   1251.54 ms (  592.6 us/tok |  0.05%)
   Foreground NVMe Sync Stall   : 1058811.32 ms (501331.1 us/tok | 43.32%)
   Unaccounted / OMP & Sampling :  69711.71 ms (33007.4 us/tok |  2.85%) | Total Wall=2444381.93 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    68.20%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     7.69%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    14.01%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.24%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.86%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=201.0s | Competitor drastic-underperform cutoff=1005.0s (5x Apex)
=== [Colibri-GLM53] CMD: ./baselines/colibri/c/glm53.exe --model D:/apex_d_drive/models/glm53 --ids 1,8,15,22,29,36,43,50,57,64,71,78,85,92,99,106,113,120,127,134,141,148,155,162,169,176,183,190,197,204,211,218,225,232,239,246,253,260,267,274,281,288,295,302,309,316,323,330,337,344,351,358,365,372,379,386,393,400,407,414,421,428,435,442 --greedy 64 32 (5x cutoff=1005.0s) ===
  [Colibri-GLM53] [gguf] D:\apex_d_drive\models\glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: glm5-next, 4 part(s), 38435 tensors under the checkpoint's names (1283 renamed, 129 fused expert tensors split per expert, 0 kept as named), read in place
  [Colibri-GLM53] glm53: GGUF experts interleaved by 16 rows on 3 of 42 layers (G53_ILV16=0: the file's rows)
  [COMP-LIVE] Colibri-GLM53: elapsed=15.0s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=30.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=45.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=60.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=75.2s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=95.7s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=110.8s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=125.8s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=141.2s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=156.2s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=171.2s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=186.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=201.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=216.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=231.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=246.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=261.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=276.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=291.4s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=306.5s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=321.6s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=337.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=352.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=367.4s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=382.8s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=397.9s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=412.9s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=428.4s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=443.5s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=458.7s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=473.8s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=488.9s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=504.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=519.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=534.5s / cutoff=1005.0s
  [Colibri-GLM53] [STATS] 43008 selections across 6945 distinct experts -> D:/apex_d_drive/models/glm53/.coli_usage
  [Colibri-GLM53] teacher_forcing 5556 335 11 15 15 22 22 22 22 36 57 22 36 64 9 154850 154850 154850 123 121 127967 127501 243 104 253 237 154842 1986 197 220 220 0 220 154827 154827 154827 154827 220 83 220 274 220 220 274 295 83 279 8 220 1 1 2776 72 83 84 365 13 220 220 220 320 83 220 220
  [Colibri-GLM53] greedy 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330
  [Colibri-GLM53] decode 64 token in 420.8s = 0.152 tok/s (6.6 s/token)
  [Colibri-GLM53] experts hits 15425 miss 11249 bytes 111319384064
=== [Colibri-GLM53] Finished rc=0 elapsed=539.10s cancelled=False ===
=== [ik_llama.cpp] CMD: baselines/ik_llama/build\bin\Release\llama-bench.exe -m D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf -p 64 -n 32 -t 4 -r 1 (5x cutoff=1005.0s) ===
  [COMP-LIVE] ik_llama.cpp: elapsed=15.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=30.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=45.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=60.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=75.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=90.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=105.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=120.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=135.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=150.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=165.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=180.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=195.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=210.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=225.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=240.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=255.3s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=270.3s / cutoff=1005.0s
  [ik_llama.cpp] | model                          |       size |     params | backend    | threads |          test |              t/s |
  [ik_llama.cpp] | ------------------------------ | ---------: | ---------: | ---------- | ------: | ------------: | ---------------: |
  [ik_llama.cpp] | glm5next 312B.A17B IQ2_XXS - 2.0625 bpw |  92.43 GiB |   313.51 B | CPU        |       4 |          pp64 |      0.76 ± 0.00 |
  [COMP-LIVE] ik_llama.cpp: elapsed=285.3s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=300.3s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=315.3s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=330.5s / cutoff=1005.0s
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 860K Nov 13 12:34 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 860K Nov 13 12:34 build/apex.exe
 [Step 2] Running Pre-Flight Unit, Greedy Parity & OpenAI API Stress Verification...
[gen_synthetic_gguf] Wrote tests/synth_glm53_ud_iq2_xxs.gguf (6748.6 KB)
[gen_synthetic_gguf] Wrote tests/synth_qwen38_ud_iq2_xs.gguf (9282.8 KB)

=== [TEST] Pre-Flight Host Hardware Benchmark: ./apex.exe hwtest ===

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.47 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    613.24 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2301.15 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9879.90 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11388.96 MB/s
   RND4K Q32T16 Read                  :    717.43 MB/s (  183663 IOPS)
   RND4K Q1T1  Read                   :    850.38 MB/s (Latency: 4.59 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     78.31 GB/s
   AVX2 256-bit Sequential Write BW   :     68.67 GB/s
   STREAM Triad (A = B + s*C) BW      :     37.38 GB/s
   Random Pointer-Chase Latency       :     55.62 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.64 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.36 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     27.26 GB/s (FP32 Equiv)
================================================================================



=== [TEST] GLM-5.3-Flash 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_glm53_ud_iq2_xxs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : glm5-next (GLM-5.3-Flash)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] Qwen-3.8-Flash-Next 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_qwen38_ud_iq2_xs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] GLM-5.3-Flash 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_glm53_ud_iq2_xxs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=1.93 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1941.88 tps | Avg=1941.88 tps | Hit=99.5% | NVMe=2173.1 MB/s (6.19 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1674.64 tps | Avg=1798.39 tps | Hit=99.5% | NVMe=2117.8 MB/s (7.01 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1458.38 tps | Avg=1668.71 tps | Hit=99.5% | NVMe=2072.3 MB/s (7.78 MB, QD=64) | RSS=71.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1268.35 tps | Avg=1546.65 tps | Hit=99.5% | NVMe=2021.0 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1150.16 tps | Avg=1446.90 tps | Hit=99.5% | NVMe=1980.8 MB/s (9.33 MB, QD=64) | RSS=72.3 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1024.16 tps | Avg=1353.77 tps | Hit=99.5% | NVMe=1953.3 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=963.79 tps | Avg=1279.79 tps | Hit=99.5% | NVMe=1929.0 MB/s (10.83 MB, QD=64) | RSS=72.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=879.68 tps | Avg=1210.94 tps | Hit=99.5% | NVMe=1907.2 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=276.71 tps | Hit=99.5% (LA:+0.0%) | NVMe=1850.4 MB/s (12.43 MB) | RSS=73.2 MB
[LIVE-DECODE] 16/32 tok | Avg=277.99 tps | Hit=99.5% (LA:+0.1%) | NVMe=1826.6 MB/s (13.10 MB) | RSS=73.2 MB
[LIVE-DECODE] 24/32 tok | Avg=278.26 tps | Hit=99.5% (LA:+0.1%) | NVMe=1794.0 MB/s (13.25 MB) | RSS=73.2 MB
[LIVE-DECODE] 32/32 tok | Avg=278.37 tps | Hit=99.5% (LA:+0.1%) | NVMe=1783.8 MB/s (13.30 MB) | RSS=73.2 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 4L, H=256, V=256 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 16 Exp/Lyr (Top-4, 64 Total) | 4 Threads | QD=64 | Shards=1 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 0.01 GB GGUF | 0.00 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=3.48 MB | KV/State=25.37 MB (14080 B/tok)
   LRFU Cache / Staging Ring    : 1.93 MB (40/64 exp = 62.50% pinned) | Staging=3.09 MB
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=73.17 MB | Peak=73.17 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "tok_55tok_55tok_175tok_55tok_39tok_55tok_36tok_246tok_68tok_55tok_246tok_86tok_68tok_220tok_197tok_246tok_228tok_246tok_228tok_86tok_68tok_86tok_236tok_246tok_229tok_246tok_229tok_246tok_229tok_246tok_229tok_21tok_246"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=96.8% | AvgMargin=13.103 | MinMargin=0.511
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1691.24 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    3.69 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    3.69 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    3.66 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    3.66 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    3.57 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    3.57 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    3.54 | 11 |  1 |  0 |    49.5 |
   |   26 |     246 | tok_246        |  195.41 | 100.0% |      54 |  174.46 |    3.63 | 12 |  0 |  0 |     0.0 |
   |   27 |     229 | tok_229        |  171.70 | 100.0% |      70 |  154.45 |    3.63 |  0 |  0 |  0 |     0.0 |
   |   22 |      86 | tok_86         |  191.40 |  93.7% |     246 |  188.70 |    3.60 | 12 |  0 |  0 |     0.0 |
   |   23 |     236 | tok_236        |  139.26 |  98.6% |     246 |  135.00 |    3.60 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    3.57 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    3.57 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    3.56 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    3.56 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.691s, TTFT=1691.24ms): Avg=1210.94 | Min=879.68 | Max=1941.88 tps
   Prefill Chunks (8): C1:256t/1941.9tps/99% | C2:256t/1674.6tps/99% | C3:256t/1458.4tps/99% | C4:256t/1268.3tps/99%
                       C5:256t/1150.2tps/99% | C6:256t/1024.2tps/99% | C7:256t/963.8tps/99% | C8:256t/879.7tps/99%
   Decode  (32 tok, 0.115s): Avg=278.37 | Min=271.27 | Max=282.71 tps
   Latency (ms) : Min=3.54 | P10=3.56 | P25=3.57 | P50=3.59 | P75=3.60 | P90=3.66 | P95=3.69 | P99=3.69 | Max=3.69
   Mean/SD/Jitt : Mean=3.59ms | StdDev=0.04ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (24768): RawRAM=24618 (99.39%) | Lookahead=22 (+0.09%) | ColdMiss=128 (0.52%) | EFF HIT=99.48%
   Lookahead    : 28 prefetched -> 22 consumed (78.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L01 | 8256 | 8213 |   7 |  36 | 99.6%|   2.08 | | L03 | 8256 | 8212 |   0 |  44 | 99.5%|   2.32 |
   | L02 | 8256 | 8193 |  15 |  48 | 99.4%|   3.14 | |     |      |      |     |     |      |        |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 13.30 MB (Load=5.42 | Prefill=6.19 | Warmup=0.00 | Decode=1.69 MB)
   SSD Data/Token (Decode)      : Avg=0.053 MB/tok (Min=0.000 | P50=0.024 | P95=0.314 | Max=0.314 MB) | Prefill=0.003 MB/tok
   NVMe Batches / Requests      : 41 Batches | 748 Reads | 438 LBA Merges (Avg 18.2 KB/req)
   SSD Read Bandwidth           : Avg=1783.81 MB/s | Peak=6721.15 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=4.78 ms | AsyncOverlapped=6.39 ms (57.2% Overlapped)
   RAM Traffic & Effective BW   : 1.43 GB moved | Eff=0.79 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=2.344s + Sys=0.547s (Wall=1.824s) | SysUtil=39.6% | ThrUtil=39.6% | 36.66 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1526.19 ms (  733.7 us/tok | 84.50%)
   MoE AVX2 Q8 Expert Compute   :    179.28 ms (   86.2 us/tok |  9.93%)
   Router + Lookahead Dispatch  :     47.29 ms (   22.7 us/tok |  2.62%)
   LM Head Output Projection    :      4.09 ms (    2.0 us/tok |  0.23%)
   Foreground NVMe Sync Stall   :      4.78 ms (    2.3 us/tok |  0.26%)
   Unaccounted / OMP & Sampling :     44.58 ms (   21.4 us/tok |  2.47%) | Total Wall=1806.20 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    26.68%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.18%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.49%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    68.36%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.29%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2658.47 tps | Avg=2658.47 tps | Hit=99.2% | NVMe=3065.4 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2580.54 tps | Avg=2618.92 tps | Hit=99.2% | NVMe=4088.3 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2128.96 tps | Avg=2432.33 tps | Hit=99.2% | NVMe=4654.4 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2233.65 tps | Avg=2379.42 tps | Hit=99.2% | NVMe=5061.7 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2084.84 tps | Avg=2314.03 tps | Hit=99.2% | NVMe=5379.5 MB/s (97.14 MB, QD=64) | RSS=90.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1936.23 tps | Avg=2241.14 tps | Hit=99.2% | NVMe=5635.8 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1754.41 tps | Avg=2155.70 tps | Hit=99.2% | NVMe=5832.9 MB/s (133.27 MB, QD=64) | RSS=91.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1669.88 tps | Avg=2080.06 tps | Hit=99.2% | NVMe=5973.8 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=253.68 tps | Hit=99.2% (LA:+0.0%) | NVMe=5826.5 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=254.67 tps | Hit=99.2% (LA:+0.1%) | NVMe=5742.6 MB/s (153.44 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=255.08 tps | Hit=99.2% (LA:+0.1%) | NVMe=5613.0 MB/s (154.78 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=255.27 tps | Hit=99.2% (LA:+0.1%) | NVMe=5515.0 MB/s (155.58 MB) | RSS=91.8 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 4L, H=256, V=256 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 16 Exp/Lyr (Top-4, 80 Total) | 4 Threads | QD=64 | Shards=1 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 0.01 GB GGUF | 0.00 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4.70 MB | KV/State=22.85 MB (13824 B/tok)
   LRFU Cache / Staging Ring    : 2.17 MB (40/80 exp = 50.00% pinned) | Staging=3.47 MB
   Process RSS (Start/End/Peak) : Start=4.90 MB | End=91.80 MB | Peak=91.80 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_129qtok_68qtok_209qtok_223qtok_113qtok_229qtok_24qtok_229qtok_148qtok_209qtok_193qtok_146qtok_148qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=92.5% | AvgMargin=9.488 | MinMargin=0.056
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 |  984.59 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    3.98 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   94.59 | 100.0% |     177 |   84.92 |    3.98 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    3.94 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   85.06 |  99.7% |     177 |   78.63 |    3.94 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    3.93 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   82.87 |  99.7% |     129 |   77.18 |    3.93 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    3.92 | 16 |  0 |  0 |    32.0 |
   |   12 |      68 | qtok_68        |   61.65 |  99.4% |      36 |   56.59 |    3.95 | 12 |  4 |  0 |   143.0 |
   |   13 |     209 | qtok_209       |   83.06 |  79.9% |     127 |   81.55 |    3.95 |  0 |  0 |  0 |   143.0 |
   |   18 |     229 | qtok_229       |   80.70 | 100.0% |      33 |   70.24 |    3.92 | 10 |  6 |  0 |   170.8 |
   |   19 |     148 | qtok_148       |   68.09 |  43.4% |      67 |   67.82 |    3.92 |  0 |  0 |  0 |   170.8 |
   |   30 |     254 | qtok_254       |   71.22 |  99.9% |      66 |   64.31 |    3.91 | 14 |  2 |  0 |    87.5 |
   |   31 |      49 | qtok_49        |  125.25 | 100.0% |     177 |   99.98 |    3.91 |  0 |  0 |  0 |    87.5 |
   |   32 |     254 | qtok_254       |   71.45 |  98.0% |      66 |   67.49 |    3.94 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  131.17 | 100.0% |     129 |  104.87 |    3.94 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 0.985s, TTFT=984.59ms): Avg=2080.06 | Min=1669.88 | Max=2658.47 tps
   Prefill Chunks (8): C1:256t/2658.5tps/99% | C2:256t/2580.5tps/99% | C3:256t/2129.0tps/99% | C4:256t/2233.6tps/99%
                       C5:256t/2084.8tps/99% | C6:256t/1936.2tps/99% | C7:256t/1754.4tps/99% | C8:256t/1669.9tps/99%
   Decode  (32 tok, 0.125s): Avg=255.27 | Min=251.11 | Max=257.77 tps
   Latency (ms) : Min=3.88 | P10=3.89 | P25=3.91 | P50=3.91 | P75=3.94 | P90=3.95 | P95=3.98 | P99=3.98 | Max=3.98
   Mean/SD/Jitt : Mean=3.92ms | StdDev=0.03ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33024): RawRAM=32720 (99.08%) | Lookahead=48 (+0.15%) | ColdMiss=256 (0.78%) | EFF HIT=99.22%
   Lookahead    : 60 prefetched -> 54 consumed (90.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8256 | 8190 |   2 |  64 | 99.2%|   3.58 | | L02 | 8256 | 8170 |  22 |  64 | 99.2%|   4.72 |
   | L01 | 8256 | 8184 |   8 |  64 | 99.2%|   4.12 | | L03 | 8256 | 8176 |  16 |  64 | 99.2%|   4.39 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 155.58 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=4.28 MB)
   SSD Data/Token (Decode)      : Avg=0.134 MB/tok (Min=0.031 | P50=0.113 | P95=0.523 | Max=0.523 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 95 Batches | 34221 Reads | 33838 LBA Merges (Avg 4.7 KB/req)
   SSD Read Bandwidth           : Avg=5515.01 MB/s | Peak=10670.60 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=24.69 MB | Write=0.00 MB | Syscalls=400
   Sync Stall vs Async DMA      : SyncStall=6.43 ms | AsyncOverlapped=27.04 ms (80.8% Overlapped)
   RAM Traffic & Effective BW   : 2.10 GB moved | Eff=1.89 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=1.844s + Sys=0.266s (Wall=1.137s) | SysUtil=46.4% | ThrUtil=46.4% | 42.89 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    677.09 ms (  325.5 us/tok | 61.00%)
   MoE AVX2 Q8 Expert Compute   :    281.49 ms (  135.3 us/tok | 25.36%)
   Router + Lookahead Dispatch  :     64.11 ms (   30.8 us/tok |  5.78%)
   LM Head Output Projection    :      4.01 ms (    1.9 us/tok |  0.36%)
   Foreground NVMe Sync Stall   :      6.43 ms (    3.1 us/tok |  0.58%)
   Unaccounted / OMP & Sampling :     76.82 ms (   36.9 us/tok |  6.92%) | Total Wall=1109.94 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.51%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.18%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.31%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    64.38%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.62%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] OpenAI-Compatible API Server on port 18081 (tests/synth_glm53_ud_iq2_xxs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 21, "completion_tokens": 8, "total_tokens": 29}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"tok_55tok_55tok_55tok_55tok_55tok_55"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"text": "tok_246tok_55tok_55tok_55tok_55tok_55", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "tok_246tok_55tok_246tok_55tok_55tok_55", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 19, "completion_tokens": 6, "total_tokens": 25}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "glm-5.3-flash-ud-iq2_xxs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "tok_55tok_55tok_55tok_55tok_55tok_55"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
[Concurrent Stress Test]: 4/4 parallel client requests completed cleanly.
[llama.cpp Server Parity]: /props, /tokenize, /detokenize, /v1/embeddings passed.
[GET /v1/telemetry]: {
  "model_name": "GLM-5.3-Flash-UD-IQ2_XXS-Synthetic",
  "architecture": "glm5-next (GLM-5.3-Flash)",
  "quantization": "Unsloth UD-IQ2_XXS",
  "mtp_enabled": false,
  "dense_pinned_ram_bytes": 3037760,
  "kv_cache_ram_bytes": 21282816,
  "kv_bytes_per_token": 14080,
  "expert_cache_ram_bytes": 1622016,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 166.24,
    "avg_tps": 986.53,
    "min_tps": 801.3,
    "max_tps": 1117.97
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 209.78,
    "min_tps": 195.19,
    "max_tps": 215.21,
    "p50_ms": 4.74,
    "p90_ms": 4.86,
    "p99_ms": 5.12,
    "mean_ms": 4.77,
    "jitter_ms": 0.07
  },
  "cache": {
    "raw_hit_rate_pct": 96.47,
    "effective_hit_rate_pct": 97.91,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 8562752,
    "prefill_bytes": 2585088,
    "warmup_bytes": 0,
    "decode_bytes": 1419264,
    "bytes_per_token": 42181.04,
    "avg_mbs": 1664.44,
    "peak_mbs": 6793.48,
    "sync_wait_ms": 1.83,
    "async_overlap_ms": 4.03
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 272146688
  },
  "kernel_attribution_ms": {
    "dense_attention": 262.25,
    "moe_compute": 72.84,
    "router_lookahead": 5.67,
    "lm_head": 6.0,
    "unaccounted": 3.56
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 77.89,
    "ram_bandwidth_pinning": 2.49,
    "expert_cache_lrfu": 15.59,
    "lookahead_parallel_overlap": 2.5,
    "ssd_nvme_throughput": 1.53,
    "total": 100.0
  }
}

=== [TEST] OpenAI-Compatible API Server on port 18082 (tests/synth_qwen38_ud_iq2_xs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63qtok_194qtok_49"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 21, "completion_tokens": 8, "total_tokens": 29}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"qtok_159qtok_194qtok_49qtok_254qtok_49qtok_254"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"text": "qtok_223qtok_49qtok_68qtok_145qtok_49qtok_229", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_68qtok_179qtok_49qtok_49qtok_17qtok_63", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 19, "completion_tokens": 6, "total_tokens": 25}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "qwen-3.8-flash-next-ud-iq2_xs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
[Concurrent Stress Test]: 4/4 parallel client requests completed cleanly.
[llama.cpp Server Parity]: /props, /tokenize, /detokenize, /v1/embeddings passed.
[GET /v1/telemetry]: {
  "model_name": "Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic",
  "architecture": "qwen4exp (Qwen-3.8-Flash-Next)",
  "quantization": "Unsloth UD-IQ2_XS",
  "mtp_enabled": false,
  "dense_pinned_ram_bytes": 3738208,
  "kv_cache_ram_bytes": 19173376,
  "kv_bytes_per_token": 13824,
  "expert_cache_ram_bytes": 1818624,
  "ssd_offloaded_expert_bytes": 3653632,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 212.15,
    "avg_tps": 773.04,
    "min_tps": 557.48,
    "max_tps": 890.74
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 185.84,
    "min_tps": 167.82,
    "max_tps": 194.42,
    "p50_ms": 5.32,
    "p90_ms": 5.81,
    "p99_ms": 5.96,
    "mean_ms": 5.38,
    "jitter_ms": 0.12
  },
  "cache": {
    "raw_hit_rate_pct": 85.56,
    "effective_hit_rate_pct": 94.92,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 38047328,
    "prefill_bytes": 20297216,
    "warmup_bytes": 0,
    "decode_bytes": 12193280,
    "bytes_per_token": 187425.26,
    "avg_mbs": 2113.33,
    "peak_mbs": 8728.09,
    "sync_wait_ms": 5.13,
    "async_overlap_ms": 16.27
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 366830592
  },
  "kernel_attribution_ms": {
    "dense_attention": 236.6,
    "moe_compute": 137.27,
    "router_lookahead": 6.77,
    "lm_head": 6.1,
    "unaccounted": 30.14
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 72.97,
    "ram_bandwidth_pinning": 2.82,
    "expert_cache_lrfu": 13.69,
    "lookahead_parallel_overlap": 6.24,
    "ssd_nvme_throughput": 4.28,
    "total": 100.0
  }
}

ALL APEX INFERENCE V1 VERIFICATION TESTS PASSED 100.00%!
```

### 📄 `02_competitors_setup.log`
```text
================================================================================
 [3.1] Cloning & Building JustVugg/colibri (https://github.com/JustVugg/colibri.git)
================================================================================
Cloning into 'colibri'...
gcc -D_FILE_OFFSET_BITS=64 -O3 -march=x86-64-v3 -fopenmp -Wall -Wextra -Wno-unused-parameter -Wno-misleading-indentation -Wno-unused-function -MMD -MP qwen38.c    -o qwen38.exe -lm -fopenmp -static -lpsapi
gcc -D_FILE_OFFSET_BITS=64 -O3 -march=x86-64-v3 -fopenmp -Wall -Wextra -Wno-unused-parameter -Wno-misleading-indentation -Wno-unused-function  -MMD -MP glm53.c    -o glm53.exe -lm -fopenmp -static -lpsapi 
================================================================================
 [3.2] Downloading Official Prebuilt llama.cpp AVX2 Windows Binaries
================================================================================
================================================================================
 [3.3] Cloning & Building ik_llama.cpp (CPU AVX2 Release)
================================================================================
Cloning into 'ik_llama'...
error: unable to create file examples/server/webui_llamacpp/src/lib/components/app/chat/ChatAttachments/ChatAttachmentsPreview/ChatAttachmentsPreviewCurrentItem/ChatAttachmentsPreviewCurrentItemUnavailable.svelte: Filename too long
fatal: unable to checkout working tree
warning: Clone succeeded, but checkout failed.
You can inspect what was checked out with 'git status'
and retry with 'git restore --source=HEAD :/'

-- Building for: Visual Studio 18 2026
-- The C compiler identification is MSVC 19.51.36260.0
-- The CXX compiler identification is MSVC 19.51.36260.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/Program Files/Microsoft Visual Studio/18/Enterprise/VC/Tools/MSVC/14.51.36231/bin/Hostx64/x64/cl.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/Program Files/Microsoft Visual Studio/18/Enterprise/VC/Tools/MSVC/14.51.36231/bin/Hostx64/x64/cl.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found Git: C:/Program Files/Git/ucrt64/bin/git.exe (found version "2.56.0.windows.4")
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Failed
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - not found
-- Found Threads: TRUE
-- Found OpenMP_C: -openmp (found version "2.0")
-- Found OpenMP_CXX: -openmp (found version "2.0")
-- Found OpenMP: TRUE (found version "2.0")
-- OpenMP found
-- Using optimized iqk matrix multiplications
-- Enabling IQK Flash Attention kernels
-- Including all IQK FA kernels
-- ccache found, compilation results will be cached. Disable with GGML_CCACHE=OFF.
-- CMAKE_SYSTEM_PROCESSOR: AMD64
-- CMAKE_GENERATOR_PLATFORM: 
-- x86 detected
CMake Warning at common/CMakeLists.txt:26 (message):
  Git index not found in git repository.


-- ARCH_FLAGS = 
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public/index.html.gz
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public_llamacpp/index_llamacpp.html.gz
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public_llamacpp/loading.html
-- Configuring done (19.0s)
-- Generating done (0.7s)
CMake Warning (unused-cli):
  Manually-specified variables were not used by the project:

    GGML_F16C


-- Build files have been written to: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build
MSBuild version 18.11.1-1.26513.3+940033be3 for .NET Framework

  1>Checking Build System
  Generating build details from Git
  -- Found Git: C:/Program Files/Git/ucrt64/bin/git.exe (found version "2.56.0.windows.4")
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/common/CMakeLists.txt
  build-info.cpp
  build_info.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\build_info.dir\Release\build_info.lib
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/ggml/src/CMakeLists.txt
  ggml.c
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(4020,13): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(4038,13): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25): warning C4477: 'fprintf' : format string '%ld' requires an argument of type 'long', but variadic argument 2 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 2 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 3 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 4 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 5 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 6 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 7 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 8 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 9 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
  ggml-alloc.c
  ggml-quants.c
C:\Program Files (x86)\Windows Kits\10\Include\10.0.26100.0\ucrt\assert.h(21,9): warning C4005: 'static_assert': macro redefinition [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  (compiling source file '../../../ggml/src/ggml-quants.c')
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-common.h(69,9):
      see previous definition of 'static_assert'
  
  ggml-aarch64.c
C:\Program Files (x86)\Windows Kits\10\Include\10.0.26100.0\ucrt\assert.h(21,9): warning C4005: 'static_assert': macro redefinition [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  (compiling source file '../../../ggml/src/ggml-aarch64.c')
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-common.h(69,9):
      see previous definition of 'static_assert'
  
  Generating Code...
  ggml-backend.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-backend.cpp(2124,30): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  ggml-moe-prefetch.cpp
  iqk_mul_mat.cpp
  iqk_kda.cpp
  iqk_flash_attn.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(141,94): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(141,82): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(179,13): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(187,25): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(188,61): warning C4244: '=': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(196,38): warning C4244: '=': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(273,112): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(281,119): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(298,22): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(346,80): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(346,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(394,80): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(394,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(481,24): warning C4244: '=': conversion from 'uint64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_fa_576_512.cpp
  iqk_fa_512_512.cpp
  iqk_fa_320_256.cpp
  iqk_fa_192_128.cpp
  iqk_fa_192_192.cpp
  iqk_fa_256_256.cpp
  iqk_fa_128_128.cpp
  iqk_fa_96_96.cpp
  iqk_fa_64_64.cpp
  iqk_gemm_floats.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_floats.cpp(637,9): warning C4065: switch statement contains 'default' but no 'case' labels [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_kquants.cpp
  iqk_gemm_ktquants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(174,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(174,23):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(103,8):
          while compiling class template '`anonymous-namespace'::Trellis3'
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(216,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(266,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_iquants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(316,30): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(332,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(365,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_iqk_quants.cpp
  iqk_gemm_1bit.cpp
  Generating Code...
  Compiling...
  iqk_gemm_legacy_quants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_legacy_quants.cpp(2623,29): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_quantize.cpp
  iqk_cpu_ops.cpp
  Generating Code...
  Auto build dll exports
     Creating library D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/ggml/src/Release/ggml.lib and object D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/ggml/src/Release/ggml.exp
  ggml.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\ggml.dll
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/src/CMakeLists.txt
  llama.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(683,52): warning C4805: '!=': unsafe mix of type 'const int' and type 'const bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(714,52): warning C4805: '!=': unsafe mix of type 'int' and type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4219,35): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4228,31): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4246,35): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4501,26): warning C4018: '>=': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4505,72): warning C4018: '>=': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4848,58): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4960,37): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details. [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(5035,45): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details. [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(8053,65): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9544,29): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9559,29): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9747,60): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9667,9): warning C4297: 'llama_init_from_model': function assumed not to throw an exception but does [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9667,9):
      __declspec(nothrow), throw(), noexcept(true), or noexcept was specified on the function
  
  llama-spec-features.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-spec-features.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-spec-features.cpp')
  
  llama-spec-features-dflash.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-spec-features-dflash.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-spec-features-dflash.cpp')
  
  llama-dflash.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-dflash.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-dflash.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-dflash.cpp(533,122): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-dsv4.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-dsv4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-dsv4.cpp')
  
  llama-vocab.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-vocab.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-vocab.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(680,82): warning C4267: '=': conversion from 'size_t' to 'llm_symbol::index', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(683,61): warning C4267: '=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(784,25): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(784,25): warning C4267: 'initializing': conversion from 'size_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(1352,55): warning C4267: 'argument': conversion from 'size_t' to 'llama_token', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(1357,31): warning C4267: 'argument': conversion from 'size_t' to 'llama_token', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(2922,26): warning C4244: 'return': conversion from 'long' to 'uint8_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(2927,26): warning C4244: 'return': conversion from 'long' to 'uint8_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(3097,74): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(3100,70): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(3889,20): warning C4267: 'return': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-grammar.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-grammar.cpp(605,37): warning C4267: 'initializing': conversion from 'size_t' to 'uint32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-sampling.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(31,20): warning C4244: '=': conversion from 'time_t' to 'uint32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(42,23): warning C4267: '=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(138,23): warning C4267: '=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(411,33): warning C4244: '=': conversion from 'double' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(415,34): warning C4244: '/=': conversion from 'double' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(461,24): warning C4267: '=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(599,27): warning C4244: 'initializing': conversion from 'float' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(599,27): warning C4244: 'initializing': conversion from 'float' to 'const int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(619,61): warning C4244: 'argument': conversion from 'const int32_t' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(989,38): warning C4244: '=': conversion from 'float' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(1012,31): warning C4244: 'initializing': conversion from 'double' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(1241,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-mmap.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-mmap.cpp(120,89): warning C4267: 'argument': conversion from 'size_t' to 'DWORD', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-mmap.cpp(143,99): warning C4267: 'argument': conversion from 'size_t' to 'DWORD', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-model-loader.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-model-loader.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-model-loader.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(472,29): warning C4267: '=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1332,32): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1332,32): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1415,26): warning C4244: 'initializing': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1415,26): warning C4244: 'initializing': conversion from 'const int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1416,26): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1416,26): warning C4267: 'initializing': conversion from 'size_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1427,88): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1460,22): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1460,22): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267: 'argument': conversion from 'size_t' to 'const _Ty', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267:             _Ty=int32_t [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1485,87): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1971,61): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267: '=': conversion from 'size_t' to 'T', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267:             T=unsigned int [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1934,96):
          see reference to function template instantiation 'bool llama_model_loader::get_arr_n<unsigned int>(const std::string &,unsigned int &,bool)' being compiled
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244: '=': conversion from 'const int64_t' to 'OT', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:             OT=uint32_t [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1033,12):
          see reference to function template instantiation 'bool llama_model_loader::get_key<uint32_t>(const std::string &,T &,const bool)' being compiled
          with
          [
              T=uint32_t
          ]
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,42):
          see reference to class template instantiation 'GGUFMeta::GKV<uint32_t>' being compiled
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(194,21):
          while compiling class template member function 'bool GGUFMeta::GKV<uint32_t>::set(const gguf_context *,const int,T &,const llama_model_kv_override *)'
          with
          [
              T=uint32_t
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(204,13):
              see the first reference to 'GGUFMeta::GKV<uint32_t>::set' in 'GGUFMeta::GKV<uint32_t>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(208,13):
              see the first reference to 'GGUFMeta::GKV<uint32_t>::set' in 'GGUFMeta::GKV<uint32_t>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,22):
              see the first reference to 'GGUFMeta::GKV<uint32_t>::set' in 'llama_model_loader::get_key'
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(195,17):
          see reference to function template instantiation 'bool GGUFMeta::GKV<uint32_t>::try_override<T>(OT &,const llama_model_kv_override *)' being compiled
          with
          [
              T=uint32_t,
              OT=uint32_t
          ]
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244: '=': conversion from 'const int64_t' to 'OT', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:             OT=int [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(441,9):
          see reference to function template instantiation 'bool llama_model_loader::get_key<int>(const std::string &,T &,const bool)' being compiled
          with
          [
              T=int
          ]
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,42):
          see reference to class template instantiation 'GGUFMeta::GKV<int>' being compiled
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(194,21):
          while compiling class template member function 'bool GGUFMeta::GKV<int>::set(const gguf_context *,const int,T &,const llama_model_kv_override *)'
          with
          [
              T=int
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(204,13):
              see the first reference to 'GGUFMeta::GKV<int>::set' in 'GGUFMeta::GKV<int>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(208,13):
              see the first reference to 'GGUFMeta::GKV<int>::set' in 'GGUFMeta::GKV<int>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,22):
              see the first reference to 'GGUFMeta::GKV<int>::set' in 'llama_model_loader::get_key'
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(195,17):
          see reference to function template instantiation 'bool GGUFMeta::GKV<int>::try_override<T>(OT &,const llama_model_kv_override *)' being compiled
          with
          [
              T=int,
              OT=int
          ]
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244: '=': conversion from 'const int64_t' to 'OT', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:             OT=uint16_t [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(385,86):
          see reference to class template instantiation 'GGUFMeta::GKV<uint16_t>' being compiled
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(194,21):
          while compiling class template member function 'bool GGUFMeta::GKV<uint16_t>::set(const gguf_context *,const int,T &,const llama_model_kv_override *)'
          with
          [
              T=uint16_t
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(204,13):
              see the first reference to 'GGUFMeta::GKV<uint16_t>::set' in 'GGUFMeta::GKV<uint16_t>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(208,13):
              see the first reference to 'GGUFMeta::GKV<uint16_t>::set' in 'GGUFMeta::GKV<uint16_t>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,22):
              see the first reference to 'GGUFMeta::GKV<uint16_t>::set' in 'llama_model_loader::get_key'
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(195,17):
          see reference to function template instantiation 'bool GGUFMeta::GKV<uint16_t>::try_override<T>(OT &,const llama_model_kv_override *)' being compiled
          with
          [
              T=uint16_t,
              OT=uint16_t
          ]
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244: '=': conversion from 'const double' to 'T', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244:             T=float [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1926,35):
          see reference to function template instantiation 'bool llama_model_loader::get_key<float>(llm_kv,float &,bool)' being compiled
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(964,12):
          see reference to function template instantiation 'bool llama_model_loader::get_key<T>(const std::string &,T &,const bool)' being compiled
          with
          [
              T=float
          ]
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,42):
          see reference to class template instantiation 'GGUFMeta::GKV<T>' being compiled
          with
          [
              T=float
          ]
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(194,21):
          while compiling class template member function 'bool GGUFMeta::GKV<T>::set(const gguf_context *,const int,T &,const llama_model_kv_override *)'
          with
          [
              T=float
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(204,13):
              see the first reference to 'GGUFMeta::GKV<T>::set' in 'GGUFMeta::GKV<T>::set'
          with
          [
              T=float
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(208,13):
              see the first reference to 'GGUFMeta::GKV<T>::set' in 'GGUFMeta::GKV<T>::set'
          with
          [
              T=float
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,22):
              see the first reference to 'GGUFMeta::GKV<T>::set' in 'llama_model_loader::get_key'
          with
          [
              T=float
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(964,12):
              see the first reference to 'llama_model_loader::get_key' in 'llama_model_loader::get_key'
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(195,17):
          see reference to function template instantiation 'bool GGUFMeta::GKV<T>::try_override<T>(T &,const llama_model_kv_override *)' being compiled
          with
          [
              T=float
          ]
  
  llama-load-tensors.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchma

... [TRUNCATED MIDDLE FOR README LIMIT] ...

_v41::<lambda_3>::operator ()<llama_context::dsv4_runtime::comp_context>(const _T1 &) const' being compiled
          with
          [
              _T1=llama_context::dsv4_runtime::comp_context
          ]
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2504,64): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2629,74): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2798,59): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2853,27): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2853,27): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_openpangu.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_openpangu.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_openpangu.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(269,77): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(292,56): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(354,54): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(375,93): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(537,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(550,63): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(678,73): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(759,57): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(813,47): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(1186,28): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(1186,28): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_glm4.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_glm4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_glm4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(17,62): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(17,49): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(43,40): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(43,40): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(70,72): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(72,72): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(170,36): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(170,36): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(217,71): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(220,65): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(297,62): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(297,49): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(392,40): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(392,40): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_bitnet.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bitnet.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bitnet.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bitnet.cpp(64,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bitnet.cpp(71,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bitnet.cpp(189,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bitnet.cpp(196,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_cohere2.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_cohere2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_cohere2.cpp')
  
  build_cohere2_moe.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_cohere2_moe.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_cohere2_moe.cpp')
  
  Generating Code...
  Compiling...
  build_t5.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_t5.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_t5.cpp')
  
  build_jais.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_jais.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_jais.cpp')
  
  build_chatglm.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_chatglm.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_chatglm.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_chatglm.cpp(50,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_chatglm.cpp(57,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_dots1.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_dots1.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_dots1.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_dots1.cpp(50,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_dots1.cpp(59,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_ernie45.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_ernie45.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_ernie45.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_ernie45.cpp(63,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_ernie45.cpp(66,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_hunyuan.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_hunyuan.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_hunyuan.cpp')
  
  build_mimo2.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_mimo2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_mimo2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_mimo2.cpp(26,36): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_mimo2.cpp(26,36): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_flint.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_flint.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_flint.cpp')
  
  build_openai.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_openai.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_openai.cpp')
  
  build_bailingmoe2.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bailingmoe2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bailingmoe2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(27,36): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(27,36): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(30,62): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(30,49): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(50,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(52,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_bailingmoe3.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bailingmoe3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bailingmoe3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe3.cpp(31,58): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe3.cpp(31,51): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_glm5next.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_glm5next.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_glm5next.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm5next.cpp(44,60): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm5next.cpp(176,55): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm5next.cpp(198,63): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_raon1.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_raon1.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_raon1.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_raon1.cpp(45,78): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_raon1.cpp(45,71): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_raon1.cpp(248,97): warning C4244: 'argument': conversion from 'int64_t' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_xing4.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_xing4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_xing4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_xing4.cpp(21,60): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_xing4.cpp(123,94): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_xing4.cpp(124,94): warning C4244: 'argument': conversion from 'int64_t' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_minimaxm2.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_minimaxm2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_minimaxm2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(88,33): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(89,33): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(98,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(100,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(223,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(226,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_minimaxm3.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_minimaxm3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_minimaxm3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm3.cpp(21,61): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_smollm3.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_smollm3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_smollm3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_smollm3.cpp(45,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_smollm3.cpp(49,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_spark2_5.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_spark2_5.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_spark2_5.cpp')
  
  Generating Code...
  Auto build dll exports
     Creating library D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/src/Release/llama.lib and object D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/src/Release/llama.exp
  llama.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\llama.dll
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/common/CMakeLists.txt
  chat-auto-parser-generator.cpp
  chat-auto-parser-helpers.cpp
  chat-diff-analyzer.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat-diff-analyzer.cpp(762,25): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat-diff-analyzer.cpp(763,25): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat-diff-analyzer.cpp(805,54): warning C4267: '-=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat-diff-analyzer.cpp(806,53): warning C4267: '+=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  chat-peg-parser.cpp
  common.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\common.cpp(1083,30): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details. [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  sampling.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(303,20): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(303,20): warning C4267: 'initializing': conversion from 'size_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267: '=': conversion from 'size_t' to '_Ty', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267:             _Ty=int [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(800,31): warning C4267: 'argument': conversion from 'size_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(939,5): warning C4804: '+=': unsafe use of type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(945,5): warning C4804: '-=': unsafe use of type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(968,30): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(981,34): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(986,34): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1075,27): warning C4267: '+=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1079,27): warning C4267: '+=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1115,29): warning C4267: '-=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1116,47): warning C4267: '=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1154,25): warning C4267: '-=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  console.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\console.cpp(253,30): warning C4267: 'initializing': conversion from 'size_t' to 'DWORD', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\console.cpp(407,28): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  json-partial.cpp
  llguidance.cpp
  json-schema-to-grammar.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(97,46): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(97,37): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(112,50): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(112,41): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(173,20): warning C4244: 'initializing': conversion from 'int64_t' to 'char', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(192,29): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(203,33): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(498,60): warning C4101: 'e': unreferenced local variable [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(809,72): warning C4101: 'e': unreferenced local variable [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  train.cpp
  log.cpp
  ngram-cache.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-cache.cpp(20,51): warning C4244: 'argument': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-cache.cpp(212,31): warning C4267: 'initializing': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-cache.cpp(212,31): warning C4267: 'initializing': conversion from 'size_t' to 'const int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  ngram-map.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(158,58): warning C4267: '=': conversion from 'size_t' to 'uint32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(169,24): warning C4267: 'initializing': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267: '=': conversion from 'size_t' to '_Ty', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267:             _Ty=std::_Vbase [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267: '=': conversion from 'size_t' to '_Ty', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267:             _Ty=std::_Vbase [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  peg-parser.cpp
  speculative.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(496,76): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(564,54): warning C4267: 'argument': conversion from 'size_t' to 'llama_pos', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(576,32): warning C4267: 'initializing': conversion from 'size_t' to 'llama_pos', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(576,32): warning C4267: 'initializing': conversion from 'size_t' to 'const llama_pos', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(1269,77): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(2571,59): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  spec-tuner.cpp
  unicode.cpp
  ngram-mod.cpp
  suffix-tree.cpp
  Generating Code...
  Compiling...
  regex-partial.cpp
  reasoning-budget.cpp
  chat.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat.cpp(52,32): warning C4101: 'e': unreferenced local variable [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat.cpp(3132,70): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat.cpp(3145,49): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  lexer.cpp
  parser.cpp
  runtime.cpp
  value.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\jinja\value.cpp(738,28): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\jinja\value.cpp(738,28): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  string.cpp
  caps.cpp
  Generating Code...
sampling.obj : warning LNK4006: "struct common_reasoning_budget_ctx * __cdecl common_reasoning_budget_init(struct llama_vocab const *,class std::vector<int,class std::allocator<int> > const &,class std::vector<int,class std::allocator<int> > const &,class std::vector<int,class std::allocator<int> > const &,int,enum common_reasoning_budget_state)" (?common_reasoning_budget_init@@YAPEAUcommon_reasoning_budget_ctx@@PEBUllama_vocab@@AEBV?$vector@HV?$allocator@H@std@@@std@@11HW4common_reasoning_budget_state@@@Z) already defined in reasoning-budget.obj; second definition ignored [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
sampling.obj : warning LNK4006: "enum common_reasoning_budget_state __cdecl common_reasoning_budget_get_state(struct common_reasoning_budget_ctx const *)" (?common_reasoning_budget_get_state@@YA?AW4common_reasoning_budget_state@@PEBUcommon_reasoning_budget_ctx@@@Z) already defined in reasoning-budget.obj; second definition ignored [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  common.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\Release\common.lib
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/llama-bench/CMakeLists.txt
  llama-bench.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(480,30): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details. [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\examples\llama-bench\llama-bench.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(1573,31): warning C4267: '=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\examples\llama-bench\llama-bench.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(93,13): warning C4244: 'initializing': conversion from 'double' to 'size_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\examples\llama-bench\llama-bench.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(93,13):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(1503,18):
          see reference to function template instantiation 'T stdev<size_t>(const std::vector<size_t,std::allocator<size_t>> &)' being compiled
          with
          [
              T=size_t
          ]
  
  llama-bench.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\llama-bench.exe
MSBuild version 18.11.1-1.26513.3+940033be3 for .NET Framework

  build_info.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\build_info.dir\Release\build_info.lib
  Auto build dll exports
  ggml.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\ggml.dll
  Auto build dll exports
  llama.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\llama.dll
  common.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\Release\common.lib
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/main/CMakeLists.txt
  main.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\main\main.cpp(518,19): warning C4804: '>': unsafe use of type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\examples\main\llama-cli.vcxproj]
  llama-cli.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\llama-cli.exe
```

### 📄 `03_host_hardware_benchmark.log`
```text
================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.27 GB Available
   Active Drive Space : 219.98 GB Total / 219.29 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    589.12 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2479.09 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9646.11 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11090.80 MB/s
   RND4K Q32T16 Read                  :    710.81 MB/s (  181968 IOPS)
   RND4K Q1T1  Read                   :    806.48 MB/s (Latency: 4.84 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     81.09 GB/s
   AVX2 256-bit Sequential Write BW   :     74.26 GB/s
   STREAM Triad (A = B + s*C) BW      :     49.12 GB/s
   Random Pointer-Chase Latency       :     57.02 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.93 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.78 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.81 GB/s (FP32 Equiv)
================================================================================
```

### 📄 `04_glm53_stage1_parity.log`
```text
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : glm5-next (GLM-5.3-Flash)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 4 / 4 (100.00% Parity)
```

### 📄 `05_glm53_stage1_prompt_response.log`
```text
================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.39 GB Available
   Active Drive Space : 219.98 GB Total / 126.94 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    592.87 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2364.96 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9209.03 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10962.85 MB/s
   RND4K Q32T16 Read                  :    692.74 MB/s (  177342 IOPS)
   RND4K Q1T1  Read                   :    786.60 MB/s (Latency: 4.97 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     69.55 GB/s
   AVX2 256-bit Sequential Write BW   :     62.61 GB/s
   STREAM Triad (A = B + s*C) BW      :     46.16 GB/s
   Random Pointer-Chase Latency       :     90.45 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.38 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.53 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.29 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.53 tps | Avg=0.53 tps | Hit=73.6% | NVMe=531.2 MB/s (51661.71 MB, QD=64) | RSS=13970.4 MB

 >>> [Apex-Model-Response] <think>
<think>
<th>
<thinking>
<thinking<th>
Let me user this question is a question about the user asks about "Explain why the why hybrid Gate why Gate DeltaNet Gate Net attention Net with Net MoE and E LB co-eco and sequential KB-1 sequential MB NV sequential NV
================================================================================

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM 5.3 Flash | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 45L, H=4096, V=154880 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 288 Exp/Lyr (Top-8, 12384 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 94.85 GB GGUF | 88.63 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=753.25 MB (33792 B/tok)
   LRFU Cache / Staging Ring    : 5559.38 MB (593/12384 exp = 4.79% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.71 MB | End=13454.79 MB | Peak=14037.62 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (70 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "<think>
<think>
<th>
<thinking>
<thinking<th>
Let me user this question is a question about the user asks about "Explain why the why hybrid Gate why Gate DeltaNet Gate Net attention Net with Net MoE and E LB co-eco and sequential KB-1 sequential MB NV sequential NV DMA"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=42.9% | AvgMargin=1.279 | MinMargin=0.023
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 131114.48 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   18.90 |  53.4% |   15724 |   18.74 | 2808.42 | 20 |232 | 84 | 1511936.0 |
   |    3 |     397 | >\n            |   12.80 |   6.2% |     318 |   12.73 | 2808.42 |  0 |  0 |  0 | 1511936.0 |
   |    4 |   13699 | <th            |   14.70 |  18.4% |     334 |   14.61 | 1898.60 |148 |128 | 60 | 1004448.0 |
   |    5 |     766 | ink            |   22.04 |  99.6% |     307 |   14.17 | 1898.60 |  0 |  0 |  0 | 1004448.0 |
   |    6 |     397 | >\n            |   12.54 |  13.7% |      29 |   12.50 | 2379.76 |137 |142 | 57 | 1019392.0 |
   |    7 |   13699 | <th            |   16.29 |  41.2% |     522 |   16.02 | 2379.76 |  0 |  0 |  0 | 1019392.0 |
   |    8 |     397 | >\n            |   17.08 |  39.3% |    1339 |   16.33 | 1392.31 |195 | 99 | 42 | 729984.0 |
   |   36 |   29136 |  Gate          |   15.35 |  36.3% |     479 |   14.86 | 2364.16 | 84 |165 | 87 | 1307712.0 |
   |   37 |    3170 |  why           |   16.44 |  65.8% |   34464 |   13.18 | 2364.16 |  0 |  0 |  0 | 1307712.0 |
   |   20 |    3405 |  question      |   16.21 |  30.6% |     374 |   15.58 | 2074.98 |108 |170 | 58 | 1149312.0 |
   |   21 |     374 |  is            |   15.85 |  19.4% |   15504 |   14.87 | 2074.98 |  0 |  0 |  0 | 1149312.0 |
   |   62 |   24384 |  NV            |   15.58 |  36.6% |   50665 |   15.35 | 1712.67 |147 |132 | 57 | 974848.0 |
   |   63 |   50665 |  sequential    |   14.36 |  20.5% |   25372 |   14.09 | 1712.67 |  0 |  0 |  0 | 974848.0 |
   |   64 |   24384 |  NV            |   17.08 |  41.8% |   25372 |   17.00 | 1698.18 |165 |116 | 55 | 920864.0 |
   |   65 |   25372 |  DMA           |   17.65 |  62.3% |   81911 |   16.44 | 1698.18 |  0 |  0 |  0 | 920864.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 131.114s, TTFT=131114.48ms): Avg=0.53 | Min=0.53 | Max=0.53 tps
   Prefill Chunks (1): C1:70t/0.5tps/74%
   Decode  (64 tok, 122.639s): Avg=0.52 | Min=0.36 | Max=0.73 tps
   Latency (ms) : Min=1365.02 | P10=1453.93 | P25=1875.12 | P50=1947.85 | P75=1991.61 | P90=2074.98 | P95=2379.76 | P99=2808.42 | Max=2808.42
   Mean/SD/Jitt : Mean=1916.24ms | StdDev=280.15ms | Jitter=103.85ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=21703 (63.33%) | Lookahead=4452 (+12.99%) | ColdMiss=8117 (23.68%) | EFF HIT=76.32%
   Lookahead    : 6853 prefetched -> 4452 consumed (65.0% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64= 76.3% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  391 | 215 | 210 | 74.3%|3054.69 | | L24 |  816 |  582 |  81 | 153 | 81.2%|2084.38 |
   | L04 |  816 |  370 | 121 | 325 | 60.2%|3981.88 | | L25 |  816 |  576 |  80 | 160 | 80.4%|2249.69 |
   | L05 |  816 |  382 | 144 | 290 | 64.5%|3687.19 | | L26 |  816 |  560 |  95 | 161 | 80.3%|2041.25 |
   | L06 |  816 |  398 | 162 | 256 | 68.6%|3435.62 | | L27 |  816 |  546 |  84 | 186 | 77.2%|2501.25 |
   | L07 |  816 |  469 | 135 | 212 | 74.0%|2918.12 | | L28 |  816 |  507 | 105 | 204 | 75.0%|2680.94 |
   | L08 |  816 |  446 | 126 | 244 | 70.1%|3320.62 | | L29 |  816 |  543 |  98 | 175 | 78.6%|2314.38 |
   | L09 |  816 |  443 | 118 | 255 | 68.8%|3234.38 | | L30 |  816 |  516 | 103 | 197 | 75.9%|2494.06 |
   | L10 |  816 |  424 | 152 | 240 | 70.6%|3234.38 | | L31 |  816 |  519 |  97 | 200 | 75.5%|2609.06 |
   | L11 |  816 |  492 | 110 | 214 | 73.8%|3571.88 | | L32 |  816 |  514 | 102 | 200 | 75.5%|2688.12 |
   | L12 |  816 |  503 | 114 | 199 | 75.6%|3123.88 | | L33 |  816 |  547 |  99 | 170 | 79.2%|2443.75 |
   | L13 |  816 |  532 |  83 | 201 | 75.4%|2458.12 | | L34 |  816 |  526 | 116 | 174 | 78.7%|2400.62 |
   | L14 |  816 |  505 | 101 | 210 | 74.3%|2839.06 | | L35 |  816 |  524 | 124 | 168 | 79.4%|2343.12 |
   | L15 |  816 |  528 |  91 | 197 | 75.9%|2515.62 | | L36 |  816 |  515 | 129 | 172 | 78.9%|2379.06 |
   | L16 |  816 |  512 |  99 | 205 | 74.9%|2637.81 | | L37 |  816 |  531 | 107 | 178 | 78.2%|2357.50 |
   | L17 |  816 |  531 |  87 | 198 | 75.7%|2666.56 | | L38 |  816 |  557 | 104 | 155 | 81.0%|2141.88 |
   | L18 |  816 |  599 |  60 | 157 | 80.8%|1926.25 | | L39 |  816 |  531 | 114 | 171 | 79.0%|2278.44 |
   | L19 |  816 |  570 |  79 | 167 | 79.5%|2070.00 | | L40 |  816 |  511 | 121 | 184 | 77.5%|2515.62 |
   | L20 |  816 |  612 |  56 | 148 | 81.9%|1883.12 | | L41 |  816 |  517 | 117 | 182 | 77.7%|2515.62 |
   | L21 |  816 |  589 |  66 | 161 | 80.3%|2105.94 | | L42 |  816 |  546 |  98 | 172 | 78.9%|2256.88 |
   | L22 |  816 |  600 |  70 | 146 | 82.1%|1962.19 | | L43 |  816 |  558 |  91 | 167 | 79.5%|2113.12 |
   | L23 |  816 |  578 |  78 | 160 | 80.4%|2055.62 | | L44 |  816 |  503 | 120 | 193 | 76.3%|3241.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 116789.27 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=65127.56 MB)
   SSD Data/Token (Decode)      : Avg=1017.618 MB/tok (Min=712.875 | P50=1043.438 | P95=1277.062 | Max=1476.500 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2551 Batches | 46571 Reads | 0 LBA Merges (Avg 2568.0 KB/req)
   SSD Read Bandwidth           : Avg=549.86 MB/s | Peak=4484.30 MB/s (100.0% of 592.9 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=117776.31 MB | Write=128.00 MB | Syscalls=58145
   Sync Stall vs Async DMA      : SyncStall=109713.77 ms | AsyncOverlapped=200149.76 ms (64.6% Overlapped)
   RAM Traffic & Effective BW   : 777.28 GB moved | Eff=3.06 GB/s (STREAM Triad Max=46.16 GB/s)
   CPU Time & Utilization       : User=256.984s + Sys=9.469s (Wall=270.816s) | SysUtil=24.6% | ThrUtil=24.6% | 55.72 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  32420.49 ms (241943.9 us/tok | 12.78%)
   MoE AVX2 Q8 Expert Compute   :  43439.00 ms (324171.6 us/tok | 17.12%)
   Router + Lookahead Dispatch  :    632.21 ms ( 4718.0 us/tok |  0.25%)
   LM Head Output Projection    :   1243.00 ms ( 9276.1 us/tok |  0.49%)
   Foreground NVMe Sync Stall   : 109713.77 ms (818759.5 us/tok | 43.24%)
   Unaccounted / OMP & Sampling :  66305.48 ms (494817.0 us/tok | 26.13%) | Total Wall=253753.95 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    35.34%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    24.92%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    30.77%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.36%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.61%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_glm53_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5221.88 MB (557 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.54 tps | Avg=0.54 tps | Hit=73.8% | NVMe=532.0 MB/s (47437.59 MB, QD=64) | RSS=13629.8 MB
[LIVE-DECODE] 2/32 tok | Avg=0.35 tps | Hit=73.8% (LA:+1.0%) | NVMe=533.2 MB/s (50472.02 MB) | RSS=13599.9 MB
[LIVE-DECODE] 4/32 tok | Avg=0.38 tps | Hit=74.0% (LA:+1.9%) | NVMe=534.2 MB/s (52820.71 MB) | RSS=13485.8 MB
[LIVE-DECODE] 6/32 tok | Avg=0.39 tps | Hit=74.1% (LA:+2.8%) | NVMe=535.1 MB/s (55295.09 MB) | RSS=13380.2 MB
[LIVE-DECODE] 8/32 tok | Avg=0.43 tps | Hit=74.3% (LA:+3.5%) | NVMe=536.8 MB/s (57293.02 MB) | RSS=13343.2 MB
[LIVE-DECODE] 10/32 tok | Avg=0.44 tps | Hit=74.5% (LA:+4.2%) | NVMe=538.6 MB/s (59354.02 MB) | RSS=13283.1 MB
[LIVE-DECODE] 12/32 tok | Avg=0.45 tps | Hit=74.7% (LA:+5.0%) | NVMe=540.0 MB/s (61595.34 MB) | RSS=13230.2 MB
[LIVE-DECODE] 14/32 tok | Avg=0.47 tps | Hit=74.8% (LA:+5.7%) | NVMe=541.8 MB/s (63562.27 MB) | RSS=13189.6 MB
[LIVE-DECODE] 16/32 tok | Avg=0.49 tps | Hit=75.0% (LA:+6.1%) | NVMe=542.8 MB/s (65121.40 MB) | RSS=13183.5 MB
[LIVE-DECODE] 18/32 tok | Avg=0.48 tps | Hit=75.1% (LA:+6.7%) | NVMe=543.7 MB/s (67543.59 MB) | RSS=13161.5 MB
[LIVE-DECODE] 20/32 tok | Avg=0.48 tps | Hit=75.2% (LA:+7.3%) | NVMe=544.3 MB/s (69636.27 MB) | RSS=13116.1 MB
[LIVE-DECODE] 22/32 tok | Avg=0.49 tps | Hit=75.4% (LA:+7.9%) | NVMe=545.1 MB/s (71636.15 MB) | RSS=13107.9 MB
[LIVE-DECODE] 24/32 tok | Avg=0.49 tps | Hit=75.4% (LA:+8.4%) | NVMe=546.0 MB/s (73899.02 MB) | RSS=13107.9 MB
[LIVE-DECODE] 26/32 tok | Avg=0.49 tps | Hit=75.5% (LA:+8.9%) | NVMe=547.0 MB/s (76036.21 MB) | RSS=13107.9 MB
[LIVE-DECODE] 28/32 tok | Avg=0.49 tps | Hit=75.5% (LA:+9.2%) | NVMe=547.6 MB/s (78130.84 MB) | RSS=13107.9 MB
[LIVE-DECODE] 30/32 tok | Avg=0.49 tps | Hit=75.6% (LA:+9.6%) | NVMe=548.3 MB/s (80132.84 MB) | RSS=13107.9 MB
[LIVE-DECODE] 32/32 tok | Avg=0.50 tps | Hit=75.7% (LA:+9.9%) | NVMe=548.7 MB/s (82005.96 MB) | RSS=13107.9 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM 5.3 Flash | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 45L, H=4096, V=154880 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 288 Exp/Lyr (Top-8, 12384 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 94.85 GB GGUF | 88.63 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=753.25 MB (33792 B/tok)
   LRFU Cache / Staging Ring    : 5221.88 MB (557/12384 exp = 4.50% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.82 MB | End=13107.92 MB | Peak=13698.38 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " a 1-bit... More
[1. More highlights…
In
In a1-bit quantized 1-bit quantized 1-bitized 1-bit"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=36.8% | AvgMargin=1.757 | MinMargin=0.015
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 119193.33 |  0 |  0 |  0 |     0.0 |
   |    2 |     220 |                |   14.20 |   9.2% |   24923 |   14.18 | 2864.00 | 19 |227 | 90 | 1553632.0 |
   |    3 |      16 | 1              |   18.33 |  26.6% |      19 |   17.27 | 2864.00 |  0 |  0 |  0 | 1553632.0 |
   |    4 |   15245 | -bit           |   13.67 |  13.4% |      13 |   13.56 | 2361.46 | 79 |202 | 55 | 1202528.0 |
   |    5 |    1112 | ...            |   13.59 |   8.9% |    1565 |   13.29 | 2361.46 |  0 |  0 |  0 | 1202528.0 |
   |    6 |    4398 |  More          |   11.74 |   8.2% |     508 |   10.90 | 2383.80 | 73 |207 | 56 | 1266880.0 |
   |    7 |     198 | \n             |   11.62 |   6.7% |     271 |   11.49 | 2383.80 |  0 |  0 |  0 | 1266880.0 |
   |    8 |      58 | [              |   13.68 |   7.4% |     785 |   13.10 | 1798.52 |118 |175 | 43 | 1022944.0 |
   |   18 |      16 | 1              |   14.79 |  37.1% |       8 |   12.48 | 2374.09 | 86 |187 | 63 | 1240160.0 |
   |   19 |   15245 | -bit           |   24.00 |  99.8% |    1455 |   16.07 | 2374.09 |  0 |  0 |  0 | 1240160.0 |
   |   24 |   15245 | -bit           |   14.65 |  22.8% |     198 |   14.42 | 2059.88 |110 |162 | 64 | 1158592.0 |
   |   25 |   10267 |  quant         |   20.95 |  97.4% |     220 |   15.80 | 2059.88 |  0 |  0 |  0 | 1158592.0 |
   |   30 |    1506 | ized           |   16.47 |  78.5% |   10267 |   12.96 | 1819.29 |136 |131 | 69 | 1025024.0 |
   |   31 |     220 |                |   19.68 |  90.4% |      16 |   16.01 | 1819.29 |  0 |  0 |  0 | 1025024.0 |
   |   32 |      16 | 1              |   15.37 |  33.8% |      19 |   14.89 | 1739.18 |153 |119 | 64 | 959040.0 |
   |   33 |   15245 | -bit           |   25.55 | 100.0% |    1455 |   16.54 | 1739.18 |  0 |  0 |  0 | 959040.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 119.193s, TTFT=119193.33ms): Avg=0.54 | Min=0.54 | Max=0.54 tps
   Prefill Chunks (1): C1:64t/0.5tps/74%
   Decode  (32 tok, 64.153s): Avg=0.50 | Min=0.35 | Max=0.70 tps
   Latency (ms) : Min=1423.75 | P10=1722.07 | P25=1819.29 | P50=1936.22 | P75=2361.46 | P90=2383.80 | P95=2864.00 | P99=2864.00 | Max=2864.00
   Mean/SD/Jitt : Mean=2004.77ms | StdDev=333.54ms | Jitter=128.21ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=17664 (65.71%) | Lookahead=2672 (+9.94%) | ColdMiss=6544 (24.35%) | EFF HIT=75.65%
   Lookahead    : 3711 prefetched -> 2672 consumed (72.0% util) | Warmup >=75%:15t, >=85%:-1t
   Trajectory   : @16= 75.0% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  327 | 102 | 211 | 67.0%|2249.69 | | L24 |  640 |  457 |  49 | 134 | 79.1%|1473.44 |
   | L04 |  640 |  315 |  72 | 253 | 60.5%|2680.94 | | L25 |  640 |  443 |  53 | 144 | 77.5%|1681.88 |
   | L05 |  640 |  316 |  76 | 248 | 61.2%|2623.44 | | L26 |  640 |  452 |  69 | 119 | 81.4%|1437.50 |
   | L06 |  640 |  345 |  89 | 206 | 67.8%|2285.62 | | L27 |  640 |  436 |  65 | 139 | 78.3%|1602.81 |
   | L07 |  640 |  386 |  84 | 170 | 73.4%|1983.75 | | L28 |  640 |  431 |  67 | 142 | 77.8%|1653.12 |
   | L08 |  640 |  384 |  71 | 185 | 71.1%|2041.25 | | L29 |  640 |  423 |  65 | 152 | 76.2%|1760.94 |
   | L09 |  640 |  363 |  70 | 207 | 67.7%|2235.31 | | L30 |  640 |  430 |  58 | 152 | 76.2%|1660.31 |
   | L10 |  640 |  360 |  78 | 202 | 68.4%|2256.88 | | L31 |  640 |  419 |  60 | 161 | 74.8%|1732.19 |
   | L11 |  640 |  406 |  61 | 173 | 73.0%|2465.62 | | L32 |  640 |  407 |  77 | 156 | 75.6%|1796.88 |
   | L12 |  640 |  410 |  64 | 166 | 74.1%|2177.50 | | L33 |  640 |  445 |  54 | 141 | 78.0%|1588.44 |
   | L13 |  640 |  429 |  51 | 160 | 75.0%|1768.12 | | L34 |  640 |  449 |  65 | 126 | 80.3%|1487.81 |
   | L14 |  640 |  439 |  43 | 158 | 75.3%|1696.25 | | L35 |  640 |  431 |  72 | 137 | 78.6%|1588.44 |
   | L15 |  640 |  438 |  47 | 155 | 75.8%|1660.31 | | L36 |  640 |  429 |  67 | 144 | 77.5%|1638.75 |
   | L16 |  640 |  437 |  65 | 138 | 78.4%|1681.88 | | L37 |  640 |  402 |  85 | 153 | 76.1%|1854.38 |
   | L17 |  640 |  442 |  54 | 144 | 77.5%|1660.31 | | L38 |  640 |  432 |  67 | 141 | 78.0%|1610.00 |
   | L18 |  640 |  461 |  47 | 132 | 79.4%|1516.56 | | L39 |  640 |  428 |  74 | 138 | 78.4%|1602.81 |
   | L19 |  640 |  458 |  53 | 129 | 79.8%|1480.62 | | L40 |  640 |  444 |  56 | 140 | 78.1%|1552.50 |
   | L20 |  640 |  455 |  42 | 143 | 77.7%|1595.62 | | L41 |  640 |  428 |  62 | 150 | 76.6%|1703.44 |
   | L21 |  640 |  464 |  49 | 127 | 80.2%|1430.31 | | L42 |  640 |  456 |  53 | 131 | 79.5%|1459.06 |
   | L22 |  640 |  467 |  46 | 127 | 80.2%|1415.94 | | L43 |  640 |  447 |  72 | 121 | 81.1%|1523.75 |
   | L23 |  640 |  438 |  55 | 147 | 77.0%|1588.44 | | L44 |  640 |  435 |  63 | 142 | 77.8%|1968.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 82005.96 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=34568.38 MB)
   SSD Data/Token (Decode)      : Avg=1080.262 MB/tok (Min=779.562 | P50=1047.312 | P95=1517.219 | Max=1517.219 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1313 Batches | 32315 Reads | 0 LBA Merges (Avg 2598.6 KB/req)
   SSD Read Bandwidth           : Avg=548.73 MB/s | Peak=4638.75 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=82014.99 MB | Write=0.00 MB | Syscalls=36351
   Sync Stall vs Async DMA      : SyncStall=88816.70 ms | AsyncOverlapped=137407.61 ms (60.7% Overlapped)
   RAM Traffic & Effective BW   : 487.81 GB moved | Eff=2.66 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=194.828s + Sys=6.734s (Wall=198.374s) | SysUtil=25.4% | ThrUtil=25.4% | 23.50 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  24678.12 ms (257063.7 us/tok | 13.46%)
   MoE AVX2 Q8 Expert Compute   :  31923.97 ms (332541.3 us/tok | 17.41%)
   Router + Lookahead Dispatch  :    632.27 ms ( 6586.2 us/tok |  0.34%)
   LM Head Output Projection    :    637.98 ms ( 6645.6 us/tok |  0.35%)
   Foreground NVMe Sync Stall   :  88816.70 ms (925173.9 us/tok | 48.44%)
   Unaccounted / OMP & Sampling :  36657.06 ms (381844.4 us/tok | 19.99%) | Total Wall=183346.09 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    38.15%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    22.03%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    30.11%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.24%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.47%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_glm53_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5653.12 MB (603 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.90 tps | Avg=0.90 tps | Hit=89.2% | NVMe=531.0 MB/s (74277.59 MB, QD=64) | RSS=14114.8 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.88 tps | Avg=0.89 tps | Hit=88.9% | NVMe=531.1 MB/s (145202.09 MB, QD=64) | RSS=14115.5 MB
[LIVE-DECODE] 2/128 tok | Avg=0.28 tps | Hit=88.9% (LA:+0.1%) | NVMe=531.4 MB/s (148490.09 MB) | RSS=13950.1 MB
[LIVE-DECODE] 4/128 tok | Avg=0.32 tps | Hit=88.9% (LA:+0.2%) | NVMe=531.7 MB/s (151125.27 MB) | RSS=13805.9 MB
[LIVE-DECODE] 6/128 tok | Avg=0.36 tps | Hit=88.8% (LA:+0.3%) | NVMe=532.1 MB/s (153469.40 MB) | RSS=13639.9 MB
[LIVE-DECODE] 8/128 tok | Avg=0.38 tps | Hit=88.8% (LA:+0.4%) | NVMe=532.6 MB/s (155649.65 MB) | RSS=13562.4 MB
[LIVE-DECODE] 10/128 tok | Avg=0.41 tps | Hit=88.8% (LA:+0.4%) | NVMe=533.1 MB/s (157599.27 MB) | RSS=13543.0 MB
[LIVE-DECODE] 12/128 tok | Avg=0.43 tps | Hit=88.8% (LA:+0.5%) | NVMe=533.6 MB/s (159647.71 MB) | RSS=13520.4 MB
[LIVE-DECODE] 14/128 tok | Avg=0.44 tps | Hit=88.8% (LA:+0.6%) | NVMe=534.1 MB/s (161641.52 MB) | RSS=13529.7 MB
[LIVE-DECODE] 16/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+0.6%) | NVMe=534.7 MB/s (163743.21 MB) | RSS=13529.7 MB
[LIVE-DECODE] 18/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+0.7%) | NVMe=534.3 MB/s (165782.65 MB) | RSS=13529.3 MB
[LIVE-DECODE] 20/128 tok | Avg=0.46 tps | Hit=88.7% (LA:+0.8%) | NVMe=534.8 MB/s (167775.09 MB) | RSS=13529.3 MB
[LIVE-DECODE] 22/128 tok | Avg=0.46 tps | Hit=88.7% (LA:+0.8%) | NVMe=535.2 MB/s (169944.15 MB) | RSS=13538.7 MB
[LIVE-DECODE] 24/128 tok | Avg=0.46 tps | Hit=88.7% (LA:+0.9%) | NVMe=535.5 MB/s (172122.77 MB) | RSS=13538.7 MB
[LIVE-DECODE] 26/128 tok | Avg=0.47 tps | Hit=88.7% (LA:+1.0%) | NVMe=535.8 MB/s (174170.09 MB) | RSS=13536.2 MB
[LIVE-DECODE] 28/128 tok | Avg=0.47 tps | Hit=88.6% (LA:+1.0%) | NVMe=535.8 MB/s (176170.84 MB) | RSS=13529.3 MB
[LIVE-DECODE] 30/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.1%) | NVMe=536.2 MB/s (177989.09 MB) | RSS=13548.0 MB
[LIVE-DECODE] 32/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.1%) | NVMe=536.7 MB/s (179686.46 MB) | RSS=13548.0 MB
[LIVE-DECODE] 34/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.2%) | NVMe=537.1 MB/s (181678.34 MB) | RSS=13548.0 MB
[LIVE-DECODE] 36/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.3%) | NVMe=537.4 MB/s (183836.27 MB) | RSS=13548.0 MB
[LIVE-DECODE] 38/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.3%) | NVMe=537.7 MB/s (185962.71 MB) | RSS=13539.9 MB
[LIVE-DECODE] 40/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.4%) | NVMe=538.0 MB/s (187879.15 MB) | RSS=13540.1 MB
[LIVE-DECODE] 42/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.5%) | NVMe=538.3 MB/s (189974.46 MB) | RSS=13540.2 MB
[LIVE-DECODE] 44/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.5%) | NVMe=538.7 MB/s (192302.02 MB) | RSS=13548.4 MB
[LIVE-DECODE] 46/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.6%) | NVMe=538.8 MB/s (194566.59 MB) | RSS=13548.4 MB
[LIVE-DECODE] 48/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.7%) | NVMe=539.1 MB/s (196637.02 MB) | RSS=13548.4 MB
[LIVE-DECODE] 50/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.7%) | NVMe=539.5 MB/s (198808.40 MB) | RSS=13548.1 MB
[LIVE-DECODE] 52/128 tok | Avg=0.50 tps | Hit=88.5% (LA:+1.8%) | NVMe=539.8 MB/s (200715.27 MB) | RSS=13548.1 MB
[LIVE-DECODE] 54/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+1.9%) | NVMe=540.1 MB/s (202490.02 MB) | RSS=13548.1 MB
[LIVE-DECODE] 56/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.0%) | NVMe=540.3 MB/s (204853.96 MB) | RSS=13548.0 MB
[LIVE-DECODE] 58/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.0%) | NVMe=540.6 MB/s (207062.65 MB) | RSS=13548.0 MB
[LIVE-DECODE] 60/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.1%) | NVMe=540.8 MB/s (208901.27 MB) | RSS=13548.0 MB
[LIVE-DECODE] 62/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.1%) | NVMe=541.2 MB/s (210775.34 MB) | RSS=13548.0 MB
[LIVE-DECODE] 64/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.2%) | NVMe=541.5 MB/s (212614.96 MB) | RSS=13529.3 MB
[LIVE-DECODE] 66/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.3%) | NVMe=541.8 MB/s (214711.09 MB) | RSS=13538.7 MB
[LIVE-DECODE] 68/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.3%) | NVMe=541.8 MB/s (216703.52 MB) | RSS=13548.1 MB
[LIVE-DECODE] 70/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.4%) | NVMe=542.0 MB/s (218583.77 MB) | RSS=13548.1 MB
[LIVE-DECODE] 72/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.5%) | NVMe=542.2 MB/s (220449.15 MB) | RSS=13548.1 MB
[LIVE-DECODE] 74/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.5%) | NVMe=542.5 MB/s (222329.52 MB) | RSS=13548.1 MB
[LIVE-DECODE] 76/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.6%) | NVMe=542.8 MB/s (224333.96 MB) | RSS=13538.7 MB
[LIVE-DECODE] 78/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.6%) | NVMe=543.0 MB/s (226278.59 MB) | RSS=13538.7 MB
[LIVE-DECODE] 80/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.7%) | NVMe=543.2 MB/s (228052.27 MB) | RSS=13538.7 MB
[LIVE-DECODE] 82/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.7%) | NVMe=543.4 MB/s (229578.77 MB) | RSS=13548.1 MB
[LIVE-DECODE] 84/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.7%) | NVMe=543.5 MB/s (231160.34 MB) | RSS=13548.0 MB
[LIVE-DECODE] 86/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.8%) | NVMe=543.6 MB/s (232828.46 MB) | RSS=13548.1 MB
[LIVE-DECODE] 88/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.8%) | NVMe=543.8 MB/s (234557.09 MB) | RSS=13548.1 MB
[LIVE-DECODE] 90/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.9%) | NVMe=544.0 MB/s (236348.09 MB) | RSS=13548.1 MB
[LIVE-DECODE] 92/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.9%) | NVMe=544.3 MB/s (238193.84 MB) | RSS=13548.1 MB
[LIVE-DECODE] 94/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.0%) | NVMe=544.5 MB/s (240147.96 MB) | RSS=13548.1 MB
[LIVE-DECODE] 96/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.0%) | NVMe=544.8 MB/s (241871.71 MB) | RSS=13548.1 MB
[LIVE-DECODE] 98/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.1%) | NVMe=544.9 MB/s (243673.84 MB) | RSS=13547.8 MB
[LIVE-DECODE] 100/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.1%) | NVMe=545.2 MB/s (245370.52 MB) | RSS=13538.7 MB
[LIVE-DECODE] 102/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+3.2%) | NVMe=545.3 MB/s (247108.46 MB) | RSS=13538.7 MB
[LIVE-DECODE] 104/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+3.2%) | NVMe=545.4 MB/s (248928.02 MB) | RSS=13548.1 MB
[LIVE-DECODE] 106/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+3.2%) | NVMe=545.6 MB/s (250821.21 MB) | RSS=13548.1 MB
[LIVE-DECODE] 108/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.3%) | NVMe=545.8 MB/s (252777.59 MB) | RSS=13548.0 MB
[LIVE-DECODE] 110/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.3%) | NVMe=546.0 MB/s (254556.02 MB) | RSS=13548.1 MB
[LIVE-DECODE] 112/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.4%) | NVMe=546.2 MB/s (256344.46 MB) | RSS=13540.1 MB
[LIVE-DECODE] 114/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.4%) | NVMe=546.3 MB/s (258227.52 MB) | RSS=13529.3 MB
[LIVE-DECODE] 116/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.5%) | NVMe=546.5 MB/s (259907.09 MB) | RSS=13538.7 MB
[LIVE-DECODE] 118/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.5%) | NVMe=546.6 MB/s (261633.65 MB) | RSS=13548.1 MB
[LIVE-DECODE] 120/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.6%) | NVMe=546.8 MB/s (263484.84 MB) | RSS=13548.1 MB
[LIVE-DECODE] 122/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.6%) | NVMe=546.9 MB/s (265425.65 MB) | RSS=13548.0 MB
[LIVE-DECODE] 124/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.7%) | NVMe=547.1 MB/s (267128.34 MB) | RSS=13548.0 MB
[LIVE-DECODE] 126/128 tok | Avg=0.55 tps | Hit=88.1% (LA:+3.7%) | NVMe=547.2 MB/s (268742.52 MB) | RSS=13548.0 MB
[LIVE-DECODE] 128/128 tok | Avg=0.55 tps | Hit=88.1% (LA:+3.7%) | NVMe=547.4 MB/s (270496.09 MB) | RSS=13540.9 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM 5.3 Flash | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 45L, H=4096, V=154880 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 288 Exp/Lyr (Top-8, 12384 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 94.85 GB GGUF | 88.63 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=753.25 MB (33792 B/tok)
   LRFU Cache / Staging Ring    : 5653.12 MB (603/12384 exp = 4.87% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.68 MB | End=13540.92 MB | Peak=14179.12 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : " single coal LBA-sorting coalesced QED LBA-sorted QD32 NVMe read and pass and register-blocked-blocked-blocked multi-blocked multi-row Q8_K GE pass. Explain why elimination PCIe amplification derive asymptotic throughput decode throughput.</think>In high-throughput Mixt-of- (Mo) model inference with NVMe offloading achieving token generation requires overlapping Gen PCIe Gen DMA transfers AVX compute pinned attention state recurrent state trunk cache pinned RAM expert cache locked RAM horizon router co prefetching over activations directly decode prefill long context tokens inverted expert gro..."
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=48.0% | AvgMargin=1.558 | MinMargin=0.009
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 573036.52 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   24.96 | 100.0% |    1062 |   16.43 | 3574.50 | 37 |166 |133 | 1683456.0 |
   |    3 |   39929 |  LB            |   17.75 |  78.0% |   33903 |   16.24 | 3574.50 |  0 |  0 |  0 | 1683456.0 |
   |    4 |      32 | A              |   14.08 |  30.6% |    1911 |   13.59 | 2615.53 | 81 |171 | 84 | 1349216.0 |
   |    5 |   46254 | -sort          |   18.02 |  42.5% |    1331 |   17.61 | 2615.53 |  0 |  0 |  0 | 1349216.0 |
   |    6 |     287 | ing            |   14.36 |  38.6% |   11492 |   11.93 | 2226.16 |114 |152 | 70 | 1200192.0 |
   |    7 |   11492 |  coal          |   16.09 |  54.1% |    1207 |   14.51 | 2226.16 |  0 |  0 |  0 | 1200192.0 |
   |    8 |    3300 | esc            |   18.05 |  93.7% |     642 |   13.98 | 1998.70 |127 |136 | 73 | 1116288.0 |
   |   56 |  154842 | </think>       |   14.32 |  56.1% |     641 |   13.02 | 2222.20 | 92 |172 | 72 | 1210336.0 |
   |   57 |     641 | In             |   15.30 |  41.7% |     565 |   13.90 | 2222.20 |  0 |  0 |  0 | 1210336.0 |
   |   44 |    3170 |  why           |   17.45 |  85.5% |     419 |   13.32 | 2157.38 |119 |141 | 76 | 1191712.0 |
   |   45 |   42687 |  elimination   |   15.17 |  16.8% |   21673 |   14.81 | 2157.38 |  0 |  0 |  0 | 1191712.0 |
   |  126 |     291 | ed             |   14.96 |  32.3% |    1207 |   14.08 | 1518.13 |191 | 88 | 57 | 826464.0 |
   |  127 |    9421 | -block         |   17.23 |  54.2% |    7299 |   15.51 | 1518.13 |  0 |  0 |  0 | 826464.0 |
   |  128 |    9421 | -block         |   14.61 |  29.9% |    1207 |   13.52 | 1595.50 |190 | 93 | 53 | 897824.0 |
   |  129 |     291 | ed             |   20.50 |  98.5% |   29819 |   14.11 | 1595.50 |  0 |  0 |  0 | 897824.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 573.037s, TTFT=573036.52ms): Avg=0.89 | Min=0.88 | Max=0.90 tps
   Prefill Chunks (2): C1:256t/0.9tps/89% | C2:256t/0.9tps/89%
   Decode  (128 tok, 234.100s): Avg=0.55 | Min=0.28 | Max=0.70 tps
   Latency (ms) : Min=1423.28 | P10=1565.39 | P25=1651.36 | P50=1761.35 | P75=1944.75 | P90=2120.47 | P95=2222.20 | P99=3574.50 | Max=3574.50
   Mean/SD/Jitt : Mean=1828.91ms | StdDev=305.95ms | Jitter=75.26ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=163160 (84.30%) | Lookahead=7250 (+3.75%) | ColdMiss=23126 (11.95%) | EFF HIT=88.05%
   Lookahead    : 12666 prefetched -> 7250 consumed (57.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 88.7% | @64= 88.4% | @128= 88.1% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3600 | 451 | 557 | 87.9%|7245.00 | | L24 | 4608 | 3993 | 117 | 498 | 89.2%|5225.31 |
   | L04 | 4608 | 3632 | 205 | 771 | 83.3%|8754.38 | | L25 | 4608 | 3952 | 129 | 527 | 88.6%|6037.50 |
   | L05 | 4608 | 3614 | 289 | 705 | 84.7%|8215.31 | | L26 | 4608 | 3977 | 140 | 491 | 89.3%|5311.56 |
   | L06 | 4608 | 3661 | 301 | 646 | 86.0%|7712.19 | | L27 | 4608 | 3873 | 134 | 601 | 87.0%|7029.38 |
   | L07 | 4608 | 3813 | 251 | 544 | 88.2%|6360.94 | | L28 | 4608 | 3891 | 157 | 560 | 87.8%|6087.81 |
   | L08 | 4608 | 3868 | 152 | 588 | 87.2%|6770.62 | | L29 | 4608 | 3914 | 158 | 536 | 88.4%|5987.19 |
   | L09 | 4608 | 3792 | 176 | 640 | 86.1%|7000.62 | | L30 | 4608 | 3900 | 170 | 538 | 88.3%|5721.25 |
   | L10 | 4608 | 3719 | 231 | 658 | 85.7%|7374.38 | | L31 | 4608 | 3821 | 139 | 648 | 85.9%|7144.38 |
   | L11 | 4608 | 3842 | 181 | 585 | 87.3%|8484.38 | | L32 | 4608 | 3824 | 166 | 618 | 86.6%|6720.31 |
   | L12 | 4608 | 3890 | 169 | 549 | 88.1%|6968.00 | | L33 | 4608 | 3889 | 167 | 552 | 88.0%|6555.00 |
   | L13 | 4608 | 3952 | 126 | 530 | 88.5%|5527.19 | | L34 | 4608 | 3900 | 209 | 499 | 89.2%|5699.69 |
   | L14 | 4608 | 3898 | 156 | 554 | 88.0%|6138.12 | | L35 | 4608 | 3863 | 211 | 534 | 88.4%|6008.75 |
   | L15 | 4608 | 3907 | 155 | 546 | 88.2%|5865.00 | | L36 | 4608 | 3841 | 245 | 522 | 88.7%|6095.00 |
   | L16 | 4608 | 3914 | 163 | 531 | 88.5%|5951.25 | | L37 | 4608 | 3902 | 180 | 526 | 88.6%|5714.06 |
   | L17 | 4608 | 3972 | 107 | 529 | 88.5%|5548.75 | | L38 | 4608 | 3897 | 181 | 530 | 88.5%|5886.56 |
   | L18 | 4608 | 4034 |  85 | 489 | 89.4%|5390.62 | | L39 | 4608 | 3906 | 161 | 541 | 88.3%|5721.25 |
   | L19 | 4608 | 4061 | 103 | 444 | 90.4%|4513.75 | | L40 | 4608 | 3923 | 171 | 514 | 88.8%|5591.88 |
   | L20 | 4608 | 3996 | 127 | 485 | 89.5%|5290.00 | | L41 | 4608 | 3885 | 197 | 526 | 88.6%|5994.38 |
   | L21 | 4608 | 3985 | 130 | 493 | 89.3%|5297.19 | | L42 | 4608 | 3960 | 137 | 511 | 88.9%|5361.88 |
   | L22 | 4608 | 4027 | 103 | 478 | 89.6%|5038.44 | | L43 | 4608 | 3974 | 155 | 479 | 89.6%|5261.25 |
   | L23 | 4608 | 4003 | 116 | 489 | 89.4%|5088.75 | | L44 | 4608 | 3895 | 149 | 564 | 87.8%|7612.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 270496.09 MB (Load=6361.84 | Prefill=138840.25 | Warmup=0.00 | Decode=125294.00 MB)
   SSD Data/Token (Decode)      : Avg=978.859 MB/tok (Min=763.250 | P50=958.219 | P95=1172.062 | Max=1644.000 MB) | Prefill=271.172 MB/tok
   NVMe Batches / Requests      : 5244 Batches | 109637 Reads | 0 LBA Merges (Avg 2526.4 KB/req)
   SSD Read Bandwidth           : Avg=547.40 MB/s | Peak=4580.36 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=270505.12 MB | Write=0.01 MB | Syscalls=113722
   Sync Stall vs Async DMA      : SyncStall=315759.20 ms | AsyncOverlapped=481881.65 ms (60.4% Overlapped)
   RAM Traffic & Effective BW   : 2783.29 GB moved | Eff=3.45 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=1308.297s + Sys=21.047s (Wall=823.902s) | SysUtil=40.3% | ThrUtil=40.3% | 37.31 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 172232.33 ms (269113.0 us/tok | 21.34%)
   MoE AVX2 Q8 Expert Compute   : 197827.86 ms (309106.0 us/tok | 24.51%)
   Router + Lookahead Dispatch  :   3117.31 ms ( 4870.8 us/tok |  0.39%)
   LM Head Output Projection    :   2489.33 ms ( 3889.6 us/tok |  0.31%)
   Foreground NVMe Sync Stall   : 315759.20 ms (493373.7 us/tok | 39.12%)
   Unaccounted / OMP & Sampling : 115710.49 ms (180797.6 us/tok | 14.34%) | Total Wall=807136.53 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    59.81%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.50%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    17.34%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.97%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.38%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_glm53_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 111101.9ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='\nSummarize LBACoalesce in one sentence.\nSummarize LB'
[Stage 3] /v1/chat/completions (stream=true SSE) 44673.2ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_glm53_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5409.38 MB (577 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=0.91 tps | Avg=0.91 tps | Hit=89.2% | NVMe=533.2 MB/s (74277.59 MB, QD=64) | RSS=13871.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=0.84 tps | Avg=0.87 tps | Hit=88.9% | NVMe=532.7 MB/s (145295.52 MB, QD=64) | RSS=13871.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=88.9% | NVMe=532.3 MB/s (214799.34 MB, QD=64) | RSS=13871.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=88.9% | NVMe=532.3 MB/s (283922.65 MB, QD=64) | RSS=13871.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=0.88 tps | Avg=0.88 tps | Hit=89.0% | NVMe=532.2 MB/s (352711.65 MB, QD=64) | RSS=13871.1 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=89.0% | NVMe=532.2 MB/s (420869.27 MB, QD=64) | RSS=13871.1 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=89.0% | NVMe=531.8 MB/s (488245.34 MB, QD=64) | RSS=13871.1 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=0.89 tps | Avg=0.88 tps | Hit=89.1% | NVMe=531.7 MB/s (554073.90 MB, QD=64) | RSS=13871.9 MB
[LIVE-DECODE] 2/64 tok | Avg=0.40 tps | Hit=89.1% (LA:+0.0%) | NVMe=531.8 MB/s (556479.90 MB) | RSS=13876.5 MB
[LIVE-DECODE] 4/64 tok | Avg=0.36 tps | Hit=89.1% (LA:+0.0%) | NVMe=531.8 MB/s (559379.21 MB) | RSS=13621.3 MB
[LIVE-DECODE] 6/64 tok | Avg=0.39 tps | Hit=89.1% (LA:+0.1%) | NVMe=531.9 MB/s (561775.40 MB) | RSS=13529.8 MB
[LIVE-DECODE] 8/64 tok | Avg=0.41 tps | Hit=89.1% (LA:+0.1%) | NVMe=532.1 MB/s (564116.40 MB) | RSS=13419.4 MB
[LIVE-DECODE] 10/64 tok | Avg=0.42 tps | Hit=89.1% (LA:+0.1%) | NVMe=532.2 MB/s (566273.09 MB) | RSS=13363.4 MB
[LIVE-DECODE] 12/64 tok | Avg=0.43 tps | Hit=89.1% (LA:+0.1%) | NVMe=532.4 MB/s (568477.52 MB) | RSS=13323.9 MB
[LIVE-DECODE] 14/64 tok | Avg=0.44 tps | Hit=89.0% (LA:+0.1%) | NVMe=532.5 MB/s (570583.40 MB) | RSS=13310.9 MB
[LIVE-DECODE] 16/64 tok | Avg=0.45 tps | Hit=89.0% (LA:+0.2%) | NVMe=532.7 MB/s (572697.09 MB) | RSS=13295.2 MB
[LIVE-DECODE] 18/64 tok | Avg=0.45 tps | Hit=89.0% (LA:+0.2%) | NVMe=532.9 MB/s (574993.90 MB) | RSS=13295.2 MB
[LIVE-DECODE] 20/64 tok | Avg=0.46 tps | Hit=89.0% (LA:+0.2%) | NVMe=533.0 MB/s (577239.46 MB) | RSS=13295.2 MB
[LIVE-DECODE] 22/64 tok | Avg=0.46 tps | Hit=89.0% (LA:+0.2%) | NVMe=533.2 MB/s (579315.46 MB) | RSS=13295.2 MB
[LIVE-DECODE] 24/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.2%) | NVMe=533.3 MB/s (581565.90 MB) | RSS=13295.2 MB
[LIVE-DECODE] 26/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=533.5 MB/s (583846.09 MB) | RSS=13304.5 MB
[LIVE-DECODE] 28/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=533.6 MB/s (586124.40 MB) | RSS=13304.6 MB
[LIVE-DECODE] 30/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=533.8 MB/s (588219.21 MB) | RSS=13304.6 MB
[LIVE-DECODE] 32/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=533.9 MB/s (590308.34 MB) | RSS=13304.5 MB
[LIVE-DECODE] 34/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.3%) | NVMe=534.0 MB/s (592218.65 MB) | RSS=13304.5 MB
[LIVE-DECODE] 36/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.1 MB/s (594383.96 MB) | RSS=13304.5 MB
[LIVE-DECODE] 38/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.2 MB/s (596320.09 MB) | RSS=13295.2 MB
[LIVE-DECODE] 40/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.3 MB/s (598268.96 MB) | RSS=13295.2 MB
[LIVE-DECODE] 42/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.5 MB/s (600236.02 MB) | RSS=13304.5 MB
[LIVE-DECODE] 44/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.6 MB/s (602103.02 MB) | RSS=13304.5 MB
[LIVE-DECODE] 46/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.6 MB/s (603994.84 MB) | RSS=13304.5 MB
[LIVE-DECODE] 48/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.4%) | NVMe=534.8 MB/s (606210.34 MB) | RSS=13304.5 MB
[LIVE-DECODE] 50/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.5%) | NVMe=534.9 MB/s (608237.40 MB) | RSS=13304.5 MB
[LIVE-DECODE] 52/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=535.0 MB/s (610643.96 MB) | RSS=13304.5 MB
[LIVE-DECODE] 54/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.5%) | NVMe=535.1 MB/s (612746.71 MB) | RSS=13304.5 MB
[LIVE-DECODE] 56/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.5%) | NVMe=535.3 MB/s (614623.27 MB) | RSS=13304.6 MB
[LIVE-DECODE] 58/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.5%) | NVMe=535.5 MB/s (616607.90 MB) | RSS=13304.5 MB
[LIVE-DECODE] 60/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.6%) | NVMe=535.6 MB/s (618617.27 MB) | RSS=13304.5 MB
[LIVE-DECODE] 62/64 tok | Avg=0.50 tps | Hit=88.9% (LA:+0.6%) | NVMe=535.7 MB/s (620700.65 MB) | RSS=13304.5 MB
[LIVE-DECODE] 64/64 tok | Avg=0.50 tps | Hit=88.9% (LA:+0.6%) | NVMe=535.8 MB/s (622629.59 MB) | RSS=13304.5 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : GLM 5.3 Flash | glm5-next (GLM-5.3-Flash) | Unsloth UD-IQ2_XXS
   Dimensions / Kernel Path     : 45L, H=4096, V=154880 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 288 Exp/Lyr (Top-8, 12384 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 94.85 GB GGUF | 88.63 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=753.25 MB (33792 B/tok)
   LRFU Cache / Staging Ring    : 5409.38 MB (577/12384 exp = 4.66% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.67 MB | End=13304.49 MB | Peak=13972.89 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : " high-throughput Mixtures of Mixtures-of-Expert (MoE) language inference with NVMe offloading achieving low-lat token generation requires overlapping Genie DMAand compute DMA transfers AVX compute attention dense recurrent attention recurrent state trunking Window cachehoriz dual lookahead coactivation preching% of activations direct RAM without CPU execution"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=43.9% | AvgMargin=1.572 | MinMargin=0.007
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    1550 |  high          |   25.48 | 100.0% |     279 |   13.45 | 2317204.97 |  0 |  0 |  0 |     0.0 |
   |    2 |   42503 | -through       |   27.04 | 100.0% |   63308 |   16.24 | 2505.53 |130 |105 |101 | 1231872.0 |
   |    3 |     628 | put            |   23.73 |  99.6% |   19183 |   17.58 | 2505.53 |  0 |  0 |  0 | 1231872.0 |
   |    4 |   19183 |  Mix           |   17.39 |  84.5% |   19705 |   14.33 | 2992.51 | 39 |215 | 82 | 1484448.0 |
   |    5 |   18482 | tures          |   16.37 |  54.3% |      68 |   15.04 | 2992.51 |  0 |  0 |  0 | 1484448.0 |
   |    6 |     315 |  of            |   13.92 |  18.4% |    8667 |   13.83 | 2215.47 |107 |152 | 77 | 1226848.0 |
   |    7 |   19183 |  Mix           |   18.45 |  89.7% |   57687 |   15.44 | 2215.47 |  0 |  0 |  0 | 1226848.0 |
   |    8 |   18482 | tures          |   16.65 |  62.5% |    4974 |   14.96 | 2134.19 |119 |142 | 75 | 1198592.0 |
   |   52 |   18547 |  dual          |   14.99 |  20.4% |   86025 |   14.43 | 2263.02 |107 |149 | 80 | 1232160.0 |
   |   53 |   86025 |  lookahead     |   13.07 |   7.8% |    9270 |   12.69 | 2263.02 |  0 |  0 |  0 | 1232160.0 |
   |    9 |    8667 | -of            |   17.27 |  47.5% |     315 |   17.04 | 2134.19 |  0 |  0 |  0 | 1198592.0 |
   |   18 |     448 |  with          |   16.53 |  65.9% |    4128 |   13.64 | 2089.10 |129 |132 | 75 | 1175968.0 |
   |   62 |   21984 |  RAM           |   16.11 |  41.3% |   33742 |   15.25 | 1922.08 |142 |124 | 70 | 1066688.0 |
   |   63 |    2041 |  without       |   15.58 |  48.8% |   28891 |   13.67 | 1922.08 |  0 |  0 |  0 | 1066688.0 |
   |   64 |   13931 |  CPU           |   16.17 |  32.7% |   11315 |   14.94 | 1812.69 |140 |147 | 49 | 987616.0 |
   |   65 |   11315 |  execution     |   14.77 |  16.3% |   15289 |   14.61 | 1812.69 |  0 |  0 |  0 | 987616.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2317.205s, TTFT=2317204.97ms): Avg=0.88 | Min=0.84 | Max=0.91 tps
   Prefill Chunks (8): C1:256t/0.9tps/89% | C2:256t/0.8tps/89% | C3:256t/0.9tps/89% | C4:256t/0.9tps/89%
                       C5:256t/0.9tps/89% | C6:256t/0.9tps/89% | C7:256t/0.9tps/89% | C8:256t/0.9tps/89%
   Decode  (64 tok, 127.177s): Avg=0.50 | Min=0.33 | Max=0.59 tps
   Latency (ms) : Min=1681.23 | P10=1772.89 | P25=1821.36 | P50=1930.95 | P75=2067.43 | P90=2215.47 | P95=2505.53 | P99=2992.51 | Max=2992.51
   Mean/SD/Jitt : Mean=1987.14ms | StdDev=250.24ms | Jitter=81.67ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (698880): RawRAM=617457 (88.35%) | Lookahead=4156 (+0.59%) | ColdMiss=77267 (11.06%) | EFF HIT=88.94%
   Lookahead    : 6991 prefetched -> 4156 consumed (59.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 89.0% | @64= 88.9% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |16640 |14180 | 235 |2225 | 86.6%|17681.25 | | L24 |16640 |14844 |  58 |1738 | 89.6%|13390.31 |
   | L04 |16640 |14248 | 115 |2277 | 86.3%|18033.44 | | L25 |16640 |14824 |  75 |1741 | 89.5%|13749.69 |
   | L05 |16640 |14217 | 164 |2259 | 86.4%|17882.50 | | L26 |16640 |14811 |  74 |1755 | 89.5%|13577.19 |
   | L06 |16640 |14237 | 182 |2221 | 86.7%|17710.00 | | L27 |16640 |14701 |  93 |1846 | 88.9%|14633.75 |
   | L07 |16640 |14509 | 155 |1976 | 88.1%|15740.62 | | L28 |16640 |14703 |  92 |1845 | 88.9%|14439.69 |
   | L08 |16640 |14500 | 101 |2039 | 87.7%|16100.00 | | L29 |16640 |14798 |  96 |1746 | 89.5%|13685.00 |
   | L09 |16640 |14513 |  99 |2028 | 87.8%|16121.56 | | L30 |16640 |14702 | 105 |1833 | 89.0%|14224.06 |
   | L10 |16640 |14364 | 136 |2140 | 87.1%|16905.00 | | L31 |16640 |14729 |  61 |1850 | 88.9%|14583.44 |
   | L11 |16640 |14688 | 135 |1817 | 89.1%|19031.25 | | L32 |16640 |14675 |  99 |1866 | 88.8%|14727.19 |
   | L12 |16640 |14742 | 103 |1795 | 89.2%|16565.75 | | L33 |16640 |14852 |  87 |1701 | 89.8%|13591.56 |
   | L13 |16640 |14916 |  84 |1640 | 90.1%|12800.94 | | L34 |16640 |14768 | 109 |1763 | 89.4%|13720.94 |
   | L14 |16640 |15019 |  80 |1541 | 90.7%|12276.25 | | L35 |16640 |14701 | 120 |1819 | 89.1%|14245.62 |
   | L15 |16640 |15110 |  88 |1442 | 91.3%|11485.62 | | L36 |16640 |14669 | 119 |1852 | 88.9%|14461.25 |
   | L16 |16640 |14940 |  86 |1614 | 90.3%|12700.31 | | L37 |16640 |14703 |  89 |1848 | 88.9%|14195.31 |
   | L17 |16640 |14795 |  62 |1783 | 89.3%|13792.81 | | L38 |16640 |14689 |  98 |1853 | 88.9%|14310.31 |
   | L18 |16640 |14917 |  53 |1670 | 90.0%|13002.19 | | L39 |16640 |14602 | 118 |1920 | 88.5%|14892.50 |
   | L19 |16640 |14875 |  60 |1705 | 89.8%|13052.50 | | L40 |16640 |14678 |  89 |1873 | 88.7%|14389.38 |
   | L20 |16640 |14829 |  64 |1747 | 89.5%|13512.50 | | L41 |16640 |14645 | 110 |1885 | 88.7%|14763.12 |
   | L21 |16640 |14927 |  57 |1656 | 90.0%|12865.62 | | L42 |16640 |14752 |  86 |1802 | 89.2%|13879.06 |
   | L22 |16640 |14886 |  71 |1683 | 89.9%|13102.81 | | L43 |16640 |14767 |  99 |1774 | 89.3%|13828.75 |
   | L23 |16640 |14804 |  69 |1767 | 89.4%|13656.25 | | L44 |16640 |14628 |  80 |1932 | 88.4%|17579.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 622629.59 MB (Load=6361.84 | Prefill=547712.06 | Warmup=0.00 | Decode=68555.69 MB)
   SSD Data/Token (Decode)      : Avg=1071.183 MB/tok (Min=933.500 | P50=1052.938 | P95=1203.281 | Max=1449.656 MB) | Prefill=267.438 MB/tok
   NVMe Batches / Requests      : 3857 Batches | 254534 Reads | 0 LBA Merges (Avg 2504.9 KB/req)
   SSD Read Bandwidth           : Avg=535.77 MB/s | Peak=4610.77 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=622638.62 MB | Write=0.01 MB | Syscalls=258593
   Sync Stall vs Async DMA      : SyncStall=1058811.32 ms | AsyncOverlapped=1150274.23 ms (52.1% Overlapped)
   RAM Traffic & Effective BW   : 7358.13 GB moved | Eff=3.01 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=4654.391s + Sys=47.688s (Wall=2460.010s) | SysUtil=47.8% | ThrUtil=47.8% | 44.20 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 629680.50 ms (298144.2 us/tok | 25.76%)
   MoE AVX2 Q8 Expert Compute   : 674518.08 ms (319374.1 us/tok | 27.59%)
   Router + Lookahead Dispatch  :  10408.78 ms ( 4928.4 us/tok |  0.43%)
   LM Head Output Projection    :   1251.54 ms (  592.6 us/tok |  0.05%)
   Foreground NVMe Sync Stall   : 1058811.32 ms (501331.1 us/tok | 43.32%)
   Unaccounted / OMP & Sampling :  69711.71 ms (33007.4 us/tok |  2.85%) | Total Wall=2444381.93 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    68.20%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     7.69%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    14.01%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.24%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.86%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_glm53_colibri_bench.log`
```text
=== [Colibri-GLM53] CMD: ./baselines/colibri/c/glm53.exe --model D:/apex_d_drive/models/glm53 --ids 1,8,15,22,29,36,43,50,57,64,71,78,85,92,99,106,113,120,127,134,141,148,155,162,169,176,183,190,197,204,211,218,225,232,239,246,253,260,267,274,281,288,295,302,309,316,323,330,337,344,351,358,365,372,379,386,393,400,407,414,421,428,435,442 --greedy 64 32 (5x cutoff=1005.0s) ===
[gguf] D:\apex_d_drive\models\glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: glm5-next, 4 part(s), 38435 tensors under the checkpoint's names (1283 renamed, 129 fused expert tensors split per expert, 0 kept as named), read in place
glm53: GGUF experts interleaved by 16 rows on 3 of 42 layers (G53_ILV16=0: the file's rows)
  [COMP-LIVE] Colibri-GLM53: elapsed=15.0s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=30.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=45.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=60.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=75.2s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=95.7s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=110.8s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=125.8s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=141.2s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=156.2s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=171.2s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=186.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=201.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=216.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=231.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=246.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=261.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=276.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=291.4s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=306.5s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=321.6s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=337.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=352.1s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=367.4s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=382.8s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=397.9s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=412.9s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=428.4s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=443.5s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=458.7s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=473.8s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=488.9s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=504.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=519.3s / cutoff=1005.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=534.5s / cutoff=1005.0s
[STATS] 43008 selections across 6945 distinct experts -> D:/apex_d_drive/models/glm53/.coli_usage
teacher_forcing 5556 335 11 15 15 22 22 22 22 36 57 22 36 64 9 154850 154850 154850 123 121 127967 127501 243 104 253 237 154842 1986 197 220 220 0 220 154827 154827 154827 154827 220 83 220 274 220 220 274 295 83 279 8 220 1 1 2776 72 83 84 365 13 220 220 220 320 83 220 220
greedy 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330
decode 64 token in 420.8s = 0.152 tok/s (6.6 s/token)
experts hits 15425 miss 11249 bytes 111319384064
=== [Colibri-GLM53] Finished rc=0 elapsed=539.10s cancelled=False ===
```

### 📄 `11b_glm53_ik_llama_bench.log`
```text
=== [ik_llama.cpp] CMD: baselines/ik_llama/build\bin\Release\llama-bench.exe -m D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf -p 64 -n 32 -t 4 -r 1 (5x cutoff=1005.0s) ===
  [COMP-LIVE] ik_llama.cpp: elapsed=15.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=30.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=45.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=60.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=75.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=90.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=105.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=120.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=135.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=150.1s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=165.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=180.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=195.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=210.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=225.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=240.2s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=255.3s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=270.3s / cutoff=1005.0s
| model                          |       size |     params | backend    | threads |          test |              t/s |
| ------------------------------ | ---------: | ---------: | ---------- | ------: | ------------: | ---------------: |
| glm5next 312B.A17B IQ2_XXS - 2.0625 bpw |  92.43 GiB |   313.51 B | CPU        |       4 |          pp64 |      0.76 ± 0.00 |
  [COMP-LIVE] ik_llama.cpp: elapsed=285.3s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=300.3s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=315.3s / cutoff=1005.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=330.5s / cutoff=1005.0s
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
