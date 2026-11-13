<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#23 (Run ID `43464136852`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43464136852)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-13 16:55:05 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-13T16:34:56.704Z] ================================================================================
[2026-11-13T16:34:56.717Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-13T16:34:56.719Z] ================================================================================
[2026-11-13T16:35:01.043Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-13T16:35:01.223Z] --------------------------------------------------------------------------------
[2026-11-13T16:35:01.225Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.12 GB / 149.89 GB
[2026-11-13T16:35:01.226Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-13T16:35:01.227Z]  [Disk Telemetry] Total Combined Usable Free Space: 247.99 GB
[2026-11-13T16:35:01.237Z] --------------------------------------------------------------------------------
[2026-11-13T16:35:01.238Z]  [OK] Disk space verification passed: 247.99 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 868K Nov 13 16:35 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 868K Nov 13 16:35 build/apex.exe
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
   CPU Model          : AMD EPYC 9V45 96-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.52 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    560.28 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1660.38 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9154.30 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11937.35 MB/s
   RND4K Q32T16 Read                  :   1017.07 MB/s (  260371 IOPS)
   RND4K Q1T1  Read                   :    961.82 MB/s (Latency: 4.06 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     94.83 GB/s
   AVX2 256-bit Sequential Write BW   :     87.56 GB/s
   STREAM Triad (A = B + s*C) BW      :     42.00 GB/s
   Random Pointer-Chase Latency       :     76.18 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     67.18 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    258.27 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     37.79 GB/s (FP32 Equiv)
================================================================================



=== [TEST] GLM-5.3-Flash 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_glm53_ud_iq2_xxs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (16) : [55, 229, 199, 135, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55] -> "tok_55tok_229tok_199tok_135tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55"
[Apex-Parity] Batched Tokens (16) : [55, 229, 199, 135, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55] -> "tok_55tok_229tok_199tok_135tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55"
[Apex-Parity] Model Architecture : glm5-next (GLM-5.3-Flash)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] Qwen-3.8-Flash-Next 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_qwen38_ud_iq2_xs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (16) : [33, 49, 68, 113, 193, 68, 227, 49, 68, 66, 193, 19, 49, 18, 150, 49] -> "qtok_33qtok_49qtok_68qtok_113qtok_193qtok_68qtok_227qtok_49qtok_68qtok_66qtok_193qtok_19qtok_49qtok_18qtok_150qtok_49"
[Apex-Parity] Batched Tokens (16) : [33, 49, 68, 113, 193, 68, 227, 49, 68, 66, 193, 19, 49, 18, 150, 49] -> "qtok_33qtok_49qtok_68qtok_113qtok_193qtok_68qtok_227qtok_49qtok_68qtok_66qtok_193qtok_19qtok_49qtok_18qtok_150qtok_49"
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] GLM-5.3-Flash 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_glm53_ud_iq2_xxs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=1.93 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2492.93 tps | Avg=2492.93 tps | Hit=99.5% | NVMe=2989.0 MB/s (6.19 MB, QD=64) | RSS=71.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2235.06 tps | Avg=2356.96 tps | Hit=99.5% | NVMe=2899.9 MB/s (7.01 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1893.02 tps | Avg=2178.96 tps | Hit=99.5% | NVMe=2856.1 MB/s (7.78 MB, QD=64) | RSS=71.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1642.52 tps | Avg=2014.48 tps | Hit=99.5% | NVMe=2768.5 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1442.83 tps | Avg=1866.57 tps | Hit=99.5% | NVMe=2751.7 MB/s (9.33 MB, QD=64) | RSS=72.3 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1045.07 tps | Avg=1650.36 tps | Hit=99.5% | NVMe=2698.4 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1200.59 tps | Avg=1566.52 tps | Hit=99.5% | NVMe=2639.7 MB/s (10.83 MB, QD=64) | RSS=72.8 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1131.26 tps | Avg=1494.64 tps | Hit=99.5% | NVMe=2609.5 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=331.85 tps | Hit=99.5% (LA:+0.0%) | NVMe=2595.3 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=331.85 tps | Hit=99.5% (LA:+0.1%) | NVMe=2589.9 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=333.45 tps | Hit=99.5% (LA:+0.1%) | NVMe=2572.6 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=333.39 tps | Hit=99.5% (LA:+0.1%) | NVMe=2551.1 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=73.12 MB | Peak=73.12 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1370.23 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    3.04 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    3.04 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    3.02 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    3.02 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    3.00 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    3.00 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    2.99 | 11 |  1 |  0 |    49.5 |
   |   14 |     220 | tok_220        |  147.52 |  55.4% |      55 |  147.01 |    3.03 |  9 |  3 |  0 |   173.2 |
   |   15 |     197 | tok_197        |   65.84 |  97.8% |     133 |   62.03 |    3.03 |  0 |  0 |  0 |   173.2 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    3.03 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    3.03 |  0 |  0 |  0 |   173.2 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    3.00 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    3.00 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    3.04 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    3.04 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.370s, TTFT=1370.23ms): Avg=1494.64 | Min=1045.07 | Max=2492.93 tps
   Prefill Chunks (8): C1:256t/2492.9tps/99% | C2:256t/2235.1tps/99% | C3:256t/1893.0tps/99% | C4:256t/1642.5tps/99%
                       C5:256t/1442.8tps/99% | C6:256t/1045.1tps/99% | C7:256t/1200.6tps/99% | C8:256t/1131.3tps/99%
   Decode  (32 tok, 0.096s): Avg=333.39 | Min=328.47 | Max=337.43 tps
   Latency (ms) : Min=2.96 | P10=2.97 | P25=2.98 | P50=3.00 | P75=3.03 | P90=3.04 | P95=3.04 | P99=3.04 | Max=3.04
   Mean/SD/Jitt : Mean=3.00ms | StdDev=0.02ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   NVMe Batches / Requests      : 41 Batches | 748 Raw -> 310 Merged (438 LBA Merges, Avg 43.9 KB/io)
   SSD I/O Size Histogram       : <64K=203 | 64K-512K=107 | 512K-2M=0 | >2M=0
   SSD Read Bandwidth (Active)  : Min=341.38 | Avg=2551.14 | Peak=7225.43 MB/s | WallAmort=9.07 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=3.48 ms | AsyncOverlapped=4.24 ms (55.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=1.03 GB/s | WallAmort=0.98 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.37s (93.5%, 6.19 MB SSD) | Decode=0.10s (6.5%, 1.69 MB SSD)
   CPU Time & Utilization       : User=1.578s + Sys=0.422s (Wall=1.479s) | SysUtil=33.8% | ThrUtil=33.8% | 31.27 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1253.60 ms (  602.7 us/tok | 85.50%)
   MoE AVX2 Q8 Expert Compute   :    133.68 ms (   64.3 us/tok |  9.12%)
   Router + Lookahead Dispatch  :     36.76 ms (   17.7 us/tok |  2.51%)
   LM Head Output Projection    :      3.50 ms (    1.7 us/tok |  0.24%)
   Foreground NVMe Sync Stall   :      3.48 ms (    1.7 us/tok |  0.24%)
   Unaccounted / OMP & Sampling :     35.20 ms (   16.9 us/tok |  2.40%) | Total Wall=1466.22 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    23.74%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.12%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.44%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    70.79%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.91%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3291.00 tps | Avg=3291.00 tps | Hit=99.2% | NVMe=3808.9 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=3449.96 tps | Avg=3368.60 tps | Hit=99.2% | NVMe=5244.4 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=3016.92 tps | Avg=3242.61 tps | Hit=99.2% | NVMe=6209.3 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2945.08 tps | Avg=3162.73 tps | Hit=99.2% | NVMe=6901.4 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2762.66 tps | Avg=3073.70 tps | Hit=99.2% | NVMe=7429.7 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2538.37 tps | Avg=2969.33 tps | Hit=99.2% | NVMe=7845.0 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2295.33 tps | Avg=2849.79 tps | Hit=99.2% | NVMe=8223.9 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2241.22 tps | Avg=2756.24 tps | Hit=99.2% | NVMe=8577.5 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=318.24 tps | Hit=99.2% (LA:+0.0%) | NVMe=8463.5 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=319.57 tps | Hit=99.2% (LA:+0.1%) | NVMe=8405.4 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=320.82 tps | Hit=99.2% (LA:+0.1%) | NVMe=8309.8 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=320.96 tps | Hit=99.2% (LA:+0.1%) | NVMe=8237.4 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=91.73 MB | Peak=91.73 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_129qtok_68qtok_209qtok_223qtok_113qtok_229qtok_112qtok_193qtok_63qtok_128qtok_63qtok_128qtok_63qtok_194qtok_49qtok_49qtok_148qtok_254qtok_48qtok_254qtok_49"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=94.1% | AvgMargin=10.265 | MinMargin=0.247
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 |  743.04 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    3.24 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    3.24 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    3.09 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    3.09 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    3.11 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    3.11 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    3.13 | 16 |  0 |  0 |    32.0 |
   |   12 |     254 | qtok_254       |   71.34 |  95.3% |      66 |   68.21 |    3.15 | 16 |  0 |  0 |    32.0 |
   |   13 |     129 | qtok_129       |   76.30 |  99.3% |      49 |   71.12 |    3.15 |  0 |  0 |  0 |    32.0 |
   |   20 |     193 | qtok_193       |   68.95 | 100.0% |      17 |   58.95 |    3.14 | 14 |  2 |  0 |    87.5 |
   |   21 |      63 | qtok_63        |   75.06 |  99.9% |     193 |   67.57 |    3.14 |  0 |  0 |  0 |    87.5 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    3.13 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    3.13 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    3.13 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    3.13 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 0.743s, TTFT=743.04ms): Avg=2756.24 | Min=2241.22 | Max=3449.96 tps
   Prefill Chunks (8): C1:256t/3291.0tps/99% | C2:256t/3450.0tps/99% | C3:256t/3016.9tps/99% | C4:256t/2945.1tps/99%
                       C5:256t/2762.7tps/99% | C6:256t/2538.4tps/99% | C7:256t/2295.3tps/99% | C8:256t/2241.2tps/99%
   Decode  (32 tok, 0.100s): Avg=320.96 | Min=308.76 | Max=326.30 tps
   Latency (ms) : Min=3.06 | P10=3.08 | P25=3.09 | P50=3.11 | P75=3.13 | P90=3.15 | P95=3.24 | P99=3.24 | Max=3.24
   Mean/SD/Jitt : Mean=3.12ms | StdDev=0.04ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33024): RawRAM=32726 (99.10%) | Lookahead=42 (+0.13%) | ColdMiss=256 (0.78%) | EFF HIT=99.22%
   Lookahead    : 52 prefetched -> 46 consumed (88.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8256 | 8190 |   2 |  64 | 99.2%|   3.58 | | L02 | 8256 | 8171 |  21 |  64 | 99.2%|   4.82 |
   | L01 | 8256 | 8179 |  13 |  64 | 99.2%|   4.23 | | L03 | 8256 | 8186 |   6 |  64 | 99.2%|   3.85 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 155.14 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=3.83 MB)
   SSD Data/Token (Decode)      : Avg=0.120 MB/tok (Min=0.031 | P50=0.113 | P95=0.523 | Max=0.523 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 92 Batches | 34197 Raw -> 371 Merged (33826 LBA Merges, Avg 428.2 KB/io)
   SSD I/O Size Histogram       : <64K=217 | 64K-512K=154 | 512K-2M=0 | >2M=0
   SSD Read Bandwidth (Active)  : Min=464.43 | Avg=8237.37 | Peak=17970.64 MB/s | WallAmort=184.09 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=4.06 ms | AsyncOverlapped=17.74 ms (81.4% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=2.88 GB/s | WallAmort=2.50 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=0.74s (88.2%, 144.44 MB SSD) | Decode=0.10s (11.8%, 3.83 MB SSD)
   CPU Time & Utilization       : User=1.375s + Sys=0.344s (Wall=0.866s) | SysUtil=49.6% | ThrUtil=49.6% | 45.90 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    521.67 ms (  250.8 us/tok | 61.90%)
   MoE AVX2 Q8 Expert Compute   :    205.30 ms (   98.7 us/tok | 24.36%)
   Router + Lookahead Dispatch  :     46.42 ms (   22.3 us/tok |  5.51%)
   LM Head Output Projection    :      3.41 ms (    1.6 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :      4.06 ms (    2.0 us/tok |  0.48%)
   Unaccounted / OMP & Sampling :     61.88 ms (   29.8 us/tok |  7.34%) | Total Wall=842.74 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    19.27%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.80%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.04%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    65.36%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     7.53%  |
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
    "ttft_ms": 135.17,
    "avg_tps": 1213.28,
    "min_tps": 988.75,
    "max_tps": 1386.07
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 252.53,
    "min_tps": 241.77,
    "max_tps": 265.31,
    "p50_ms": 3.95,
    "p90_ms": 4.09,
    "p99_ms": 4.14,
    "mean_ms": 3.96,
    "jitter_ms": 0.09
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
    "avg_mbs": 3022.79,
    "peak_mbs": 7241.92,
    "sync_wait_ms": 1.09,
    "async_overlap_ms": 1.9
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
    "dense_attention": 217.24,
    "moe_compute": 59.68,
    "router_lookahead": 4.11,
    "lm_head": 5.0,
    "unaccounted": 2.48
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.69,
    "ram_bandwidth_pinning": 3.19,
    "expert_cache_lrfu": 11.02,
    "lookahead_parallel_overlap": 1.98,
    "ssd_nvme_throughput": 1.12,
    "total": 100.0
  }
}

=== [TEST] OpenAI-Compatible API Server on port 18082 (tests/synth_qwen38_ud_iq2_xs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63qtok_194qtok_49"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 21, "completion_tokens": 8, "total_tokens": 29}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"qtok_159qtok_194qtok_49qtok_254qtok_49qtok_254"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"text": "qtok_159qtok_112qtok_193qtok_128qtok_49qtok_254", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_68qtok_179qtok_49qtok_49qtok_17qtok_63", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 19, "completion_tokens": 6, "total_tokens": 25}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "qwen-3.8-flash-next-ud-iq2_xs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
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
    "ttft_ms": 191.11,
    "avg_tps": 858.14,
    "min_tps": 572.87,
    "max_tps": 1094.34
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 219.77,
    "min_tps": 187.91,
    "max_tps": 232.32,
    "p50_ms": 4.51,
    "p90_ms": 4.78,
    "p99_ms": 5.32,
    "mean_ms": 4.55,
    "jitter_ms": 0.11
  },
  "cache": {
    "raw_hit_rate_pct": 85.62,
    "effective_hit_rate_pct": 94.92,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 37982304,
    "prefill_bytes": 20297216,
    "warmup_bytes": 0,
    "decode_bytes": 12128256,
    "bytes_per_token": 187104.95,
    "avg_mbs": 4341.95,
    "peak_mbs": 13043.24,
    "sync_wait_ms": 2.79,
    "async_overlap_ms": 7.53
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
    "dense_attention": 203.85,
    "moe_compute": 125.72,
    "router_lookahead": 5.19,
    "lm_head": 5.09,
    "unaccounted": 25.93
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 81.03,
    "ram_bandwidth_pinning": 3.55,
    "expert_cache_lrfu": 8.41,
    "lookahead_parallel_overlap": 4.32,
    "ssd_nvme_throughput": 2.69,
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
 [Step 4.0] Host Hardware Benchmark + 1GB Uncached Disk Throttle Probe (C: & D:)
================================================================================
Host CPU: AMD EPYC 9V45 96-Core Processor | Cores=2 Threads=4 | RAM=15.99 GB

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V45 96-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.51 GB Available
   Active Drive Space : 219.98 GB Total / 219.81 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    551.55 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2124.00 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9760.04 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  12335.68 MB/s
   RND4K Q32T16 Read                  :   1128.02 MB/s (  288772 IOPS)
   RND4K Q1T1  Read                   :   1141.68 MB/s (Latency: 3.42 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     96.53 GB/s
   AVX2 256-bit Sequential Write BW   :     95.44 GB/s
   STREAM Triad (A = B + s*C) BW      :     55.77 GB/s
   Random Pointer-Chase Latency       :     35.48 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     71.65 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    277.21 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     39.81 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 28.12 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 137.89 MB/s (7.43s)
   Window #01 (112.0 MB in 0.51s):   221.31 MB/s (Uncached Direct Read)
   Window #02 (120.0 MB in 0.51s):   237.49 MB/s (Uncached Direct Read)
   Window #03 (116.0 MB in 0.52s):   224.98 MB/s (Uncached Direct Read)
   Window #04 (120.0 MB in 0.51s):   233.68 MB/s (Uncached Direct Read)
   Window #05 (120.0 MB in 0.51s):   237.56 MB/s (Uncached Direct Read)
   Window #06 (112.0 MB in 0.51s):   218.19 MB/s (Uncached Direct Read)
   Window #07 (116.0 MB in 0.51s):   226.75 MB/s (Uncached Direct Read)
   Window #08 (120.0 MB in 0.51s):   234.35 MB/s (Uncached Direct Read)
   Window #09 ( 88.0 MB in 0.41s):   215.25 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   227.99 MB/s (Min=215.25 | Max=237.56 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 219.81 GB / 219.98 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 271.93 MB/s (3.77s)
   Window #01 (272.0 MB in 0.50s):   542.43 MB/s (Uncached Direct Read)
   Window #02 (272.0 MB in 0.50s):   542.43 MB/s (Uncached Direct Read)
   Window #03 (272.0 MB in 0.50s):   542.70 MB/s (Uncached Direct Read)
   Window #04 (208.0 MB in 0.38s):   545.66 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   543.14 MB/s (Min=542.43 | Max=545.66 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: qwen38 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (0.010 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 100.00% (0.01/0.01 GB) @ 19.7 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (43.792 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  11.42% (5.00/43.79 GB) @ 271.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  22.84% (10.00/43.79 GB) @ 264.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  34.25% (15.00/43.79 GB) @ 270.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  45.67% (20.00/43.79 GB) @ 262.0 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  57.09% (25.00/43.79 GB) @ 260.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  68.51% (30.00/43.79 GB) @ 253.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  79.92% (35.00/43.79 GB) @ 252.8 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  91.34% (40.00/43.79 GB) @ 250.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf: 100.00% (43.79/43.79 GB) @ 252.6 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (26.822 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  18.64% (5.00/26.82 GB) @ 292.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  37.28% (10.00/26.82 GB) @ 247.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  55.92% (15.00/26.82 GB) @ 248.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  74.57% (20.00/26.82 GB) @ 242.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  93.21% (25.00/26.82 GB) @ 238.8 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf: 100.00% (26.82/26.82 GB) @ 246.1 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/MTP/mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (2.595 GB) -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Sequential Non-Truncate)
  [DL] mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 100.00% (2.60/2.60 GB) @ 96.1 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=78,618,661,594 (73.22 GB) | Elapsed=318.91s
[Colibri-Import] Running baselines/colibri/c/tools/gguf_import.py on D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf -> D:/apex_d_drive/models/qwen38 (--mode link)...
colibri model directory ready: D:\apex_d_drive\models\qwen38  (qwen4exp, 48 layers, mode link)
  MTP head: C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf
Verified Primary Shard 1 Path: D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Alt Shard Dir: C:/apex_c_drive/models/qwen38)
--------------------------------------------------------------------------------
 [Stage 1] Small Prompt (64 tokens) + 100.00% Greedy Parity & Prompt/Response Trace
--------------------------------------------------------------------------------
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (4) : [198, 198, 198, 198] -> "



"
[Apex-Parity] Batched Tokens (4) : [198, 198, 198, 198] -> "



"
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 4 / 4 (100.00% Parity)
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6574.22 MB (3168 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=2.97 tps | Avg=2.97 tps | Hit=88.1% | NVMe=562.7 MB/s (10578.12 MB, QD=64) | RSS=12464.2 MB
[LIVE-DECODE] 8/32 tok | Avg=2.95 tps | Hit=88.8% (LA:+0.3%) | NVMe=569.0 MB/s (11489.99 MB) | RSS=12467.0 MB
[LIVE-DECODE] 16/32 tok | Avg=3.25 tps | Hit=89.4% (LA:+0.4%) | NVMe=580.3 MB/s (12233.70 MB) | RSS=12467.0 MB
[LIVE-DECODE] 24/32 tok | Avg=3.37 tps | Hit=90.0% (LA:+0.5%) | NVMe=590.7 MB/s (13039.39 MB) | RSS=12467.0 MB
[LIVE-DECODE] 32/32 tok | Avg=3.42 tps | Hit=90.4% (LA:+0.7%) | NVMe=602.5 MB/s (13928.73 MB) | RSS=12467.0 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 6574.22 MB (3168/25088 exp = 12.63% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=12467.04 MB | Peak=12927.72 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " a2!ar!
!
!
!
!2!
!
!
!
!
!2!
!2!
!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=57.2% | AvgMargin=0.832 | MinMargin=0.117
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.79 |  18.1% |     303 |   13.43 | 21557.47 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    9.06 |   2.0% |      11 |    8.95 |  381.22 |447 | 27 |  6 | 116482.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  381.22 |  0 |  0 |  0 | 116482.0 |
   |    4 |     277 | ar             |    8.82 |   2.2% |     198 |    8.49 |  364.39 |440 | 38 |  2 | 122709.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  364.39 |  0 |  0 |  0 | 122709.0 |
   |    6 |     198 | \n             |   10.74 |  15.3% |      11 |    9.20 |  323.77 |456 | 22 |  2 | 117169.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  323.77 |  0 |  0 |  0 | 117169.5 |
   |    8 |     198 | \n             |   11.64 |  35.2% |  248046 |    8.76 |  284.75 |463 | 17 |  0 | 110519.5 |
   |   16 |     198 | \n             |   10.43 |  10.7% |  248046 |    8.48 |  297.40 |474 |  6 |  0 | 87607.0 |
   |   17 |       0 | !              |     nan | 100.0% |       1 |     nan |  297.40 |  0 |  0 |  0 | 87607.0 |
   |   26 |      17 | 2              |    8.79 |   2.0% |      22 |    8.51 |  296.62 |435 | 41 |  4 | 150244.5 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  296.62 |  0 |  0 |  0 | 150244.5 |
   |   30 |      17 | 2              |   11.26 |  12.2% |     198 |   10.72 |  269.36 |463 | 17 |  0 | 103582.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  269.36 |  0 |  0 |  0 | 103582.0 |
   |   32 |     198 | \n             |   10.87 |  17.5% |      11 |    9.14 |  269.58 |470 | 10 |  0 | 87057.0 |
   |   33 |       0 | !              |     nan | 100.0% |       1 |     nan |  269.58 |  0 |  0 |  0 | 87057.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 21.557s, TTFT=21557.47ms): Avg=2.97 | Min=2.97 | Max=2.97 tps
   Prefill Chunks (1): C1:64t/3.0tps/88%
   Decode  (32 tok, 9.345s): Avg=3.42 | Min=2.62 | Max=3.85 tps
   Latency (ms) : Min=259.80 | P10=266.68 | P25=269.58 | P50=280.51 | P75=297.40 | P90=364.39 | P95=381.22 | P99=381.22 | Max=381.22
   Mean/SD/Jitt : Mean=292.03ms | StdDev=34.16ms | Jitter=9.74ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (38400): RawRAM=34452 (89.72%) | Lookahead=280 (+0.73%) | ColdMiss=3668 (9.55%) | EFF HIT=90.45%
   Lookahead    : 1706 prefetched -> 440 consumed (25.8% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 89.4% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  800 |  569 |  17 | 214 | 73.2%| 389.14 | | L24 |  800 |  749 |   4 |  47 | 94.1%| 127.83 |
   | L01 |  800 |  696 |  10 |  94 | 88.2%| 295.09 | | L25 |  800 |  748 |   0 |  52 | 93.5%| 107.15 |
   | L02 |  800 |  695 |   3 | 102 | 87.2%| 348.71 | | L26 |  800 |  728 |   5 |  67 | 91.6%| 156.03 |
   | L03 |  800 |  745 |   0 |  55 | 93.1%| 310.18 | | L27 |  800 |  736 |   0 |  64 | 92.0%| 137.23 |
   | L04 |  800 |  741 |   0 |  59 | 92.6%| 184.69 | | L28 |  800 |  716 |   6 |  78 | 90.2%| 257.54 |
   | L05 |  800 |  728 |   1 |  71 | 91.1%| 244.38 | | L29 |  800 |  715 |   7 |  78 | 90.2%| 168.53 |
   | L06 |  800 |  739 |   0 |  61 | 92.4%| 171.07 | | L30 |  800 |  686 |  15 |  99 | 87.6%| 191.58 |
   | L07 |  800 |  738 |   2 |  60 | 92.5%| 106.13 | | L31 |  800 |  688 |  16 |  96 | 88.0%| 201.66 |
   | L08 |  800 |  759 |   1 |  40 | 95.0%|  73.46 | | L32 |  800 |  716 |   4 |  80 | 90.0%| 195.51 |
   | L09 |  800 |  747 |   0 |  53 | 93.4%|  74.71 | | L33 |  800 |  701 |  12 |  87 | 89.1%| 157.01 |
   | L10 |  800 |  743 |   1 |  56 | 93.0%|  85.91 | | L34 |  800 |  708 |  10 |  82 | 89.8%| 162.77 |
   | L11 |  800 |  749 |   1 |  50 | 93.8%|  63.50 | | L35 |  800 |  730 |   2 |  68 | 91.5%| 110.91 |
   | L12 |  800 |  736 |   0 |  64 | 92.0%| 122.19 | | L36 |  800 |  709 |  11 |  80 | 90.0%| 195.90 |
   | L13 |  800 |  728 |   0 |  72 | 91.0%| 108.03 | | L37 |  800 |  731 |   4 |  65 | 91.9%| 135.35 |
   | L14 |  800 |  710 |  11 |  79 | 90.1%| 181.49 | | L38 |  800 |  733 |   2 |  65 | 91.9%| 174.83 |
   | L15 |  800 |  709 |   9 |  82 | 89.8%| 203.03 | | L39 |  800 |  717 |   6 |  77 | 90.4%| 223.71 |
   | L16 |  800 |  722 |   5 |  73 | 90.9%| 165.43 | | L40 |  800 |  702 |  11 |  87 | 89.1%| 265.06 |
   | L17 |  800 |  727 |   3 |  70 | 91.2%| 167.31 | | L41 |  800 |  704 |   7 |  89 | 88.9%| 157.01 |
   | L18 |  800 |  721 |   9 |  70 | 91.2%| 156.03 | | L42 |  800 |  677 |  14 | 109 | 86.4%| 218.95 |
   | L19 |  800 |  723 |   9 |  68 | 91.5%| 122.44 | | L43 |  800 |  716 |   6 |  78 | 90.2%| 159.89 |
   | L20 |  800 |  698 |  12 |  90 | 88.8%| 178.61 | | L44 |  800 |  707 |   5 |  88 | 89.0%| 152.69 |
   | L21 |  800 |  703 |   9 |  88 | 89.0%| 253.78 | | L45 |  800 |  691 |  13 |  96 | 88.0%| 203.10 |
   | L22 |  800 |  748 |   0 |  52 | 93.5%| 101.51 | | L46 |  800 |  735 |   1 |  64 | 92.0%| 171.41 |
   | L23 |  800 |  728 |   8 |  64 | 92.0%| 131.08 | | L47 |  800 |  707 |   8 |  85 | 89.4%| 242.50 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 13928.73 MB (Load=4614.69 | Prefill=5963.42 | Warmup=0.00 | Decode=3350.61 MB)
   SSD Data/Token (Decode)      : Avg=104.707 MB/tok (Min=85.017 | P50=101.154 | P95=146.723 | Max=146.723 MB) | Prefill=93.178 MB/tok
   NVMe Batches / Requests      : 788 Batches | 18510 Raw -> 17726 Merged (784 LBA Merges, Avg 804.6 KB/io)
   SSD I/O Size Histogram       : <64K=1595 | 64K-512K=4168 | 512K-2M=11523 | >2M=440
   SSD Read Bandwidth (Active)  : Min=7.23 | Avg=602.48 | Peak=10215.71 MB/s | WallAmort=450.73 MB/s
   OS Kernel I/O Verification   : Read=13948.70 MB | Write=0.00 MB | Syscalls=27228
   Sync Stall vs Async DMA      : SyncStall=10578.56 ms | AsyncOverlapped=14876.60 ms (58.4% Overlapped)
   RAM Traffic & Active BW      : 360.23 GB moved | Active=21.73 GB/s | WallAmort=11.66 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=21.56s (69.8%, 5963.42 MB SSD) | Decode=9.34s (30.2%, 3350.61 MB SSD)
   CPU Time & Utilization       : User=52.344s + Sys=4.656s (Wall=43.117s) | SysUtil=33.0% | ThrUtil=33.0% | 30.57 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   7812.35 ms (81378.7 us/tok | 25.28%)
   MoE AVX2 Q8 Expert Compute   :   7968.16 ms (83001.6 us/tok | 25.78%)
   Router + Lookahead Dispatch  :    449.21 ms ( 4679.3 us/tok |  1.45%)
   LM Head Output Projection    :    796.81 ms ( 8300.1 us/tok |  2.58%)
   Foreground NVMe Sync Stall   :  10578.56 ms (110193.3 us/tok | 34.23%)
   Unaccounted / OMP & Sampling :   3297.29 ms (34346.8 us/tok | 10.67%) | Total Wall=30902.38 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    77.90%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.41%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     9.22%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.53%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.94%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 45s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V45 96-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.37 GB Available
   Active Drive Space : 219.98 GB Total / 149.17 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    511.54 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2121.62 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8201.19 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10845.85 MB/s
   RND4K Q32T16 Read                  :    761.75 MB/s (  195009 IOPS)
   RND4K Q1T1  Read                   :    893.93 MB/s (Latency: 4.37 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     72.60 GB/s
   AVX2 256-bit Sequential Write BW   :     74.74 GB/s
   STREAM Triad (A = B + s*C) BW      :     46.12 GB/s
   Random Pointer-Chase Latency       :    125.00 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     67.16 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    257.70 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     35.79 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=3.22 tps | Avg=3.22 tps | Hit=90.0% | NVMe=563.6 MB/s (11789.75 MB, QD=64) | RSS=13442.5 MB

 >>> [Apex-Model-Response] b
!
!n!
!u!
!
!
!
!
!
!
!a!2!1!1!1!1!n!
!1! !
!
!
!
!8! ! ! !
! 
================================================================================

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7539.18 MB (3633/25088 exp = 14.48% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=13416.85 MB | Peak=13905.10 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "b
!
!n!
!u!
!
!
!
!
!
!
!a!2!1!1!1!1!n!
!1! !
!
!
!
!8! ! ! !
! !"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=56.3% | AvgMargin=0.623 | MinMargin=0.019
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      65 | b              |    9.34 |   1.9% |      79 |    9.00 | 28252.51 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |    9.49 |   3.9% |      17 |    8.24 |  334.39 |446 | 30 |  4 | 109471.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  334.39 |  0 |  0 |  0 | 109471.5 |
   |    4 |     198 | \n             |   10.43 |   8.6% |      82 |    9.45 |  300.86 |458 | 22 |  0 | 102369.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  300.86 |  0 |  0 |  0 | 102369.5 |
   |    6 |      77 | n              |    8.42 |   1.7% |      76 |    8.40 |  289.89 |451 | 29 |  0 | 107294.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  289.89 |  0 |  0 |  0 | 107294.5 |
   |    8 |     198 | \n             |    7.79 |   0.8% |     286 |    7.34 |  260.68 |468 | 12 |  0 | 93469.5 |
   |   26 |      64 | a              |   10.03 |   5.8% |      82 |    8.92 |  286.99 |449 | 28 |  3 | 130707.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  286.99 |  0 |  0 |  0 | 130707.0 |
   |   30 |      16 | 1              |    9.21 |   1.7% |      17 |    9.03 |  282.50 |461 | 17 |  2 | 108732.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  282.50 |  0 |  0 |  0 | 108732.0 |
   |   62 |     198 | \n             |    9.87 |   8.6% |      22 |    9.28 |  201.80 |478 |  2 |  0 | 82082.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  201.80 |  0 |  0 |  0 | 82082.0 |
   |   64 |     220 |                |    9.81 |   9.4% |     264 |    8.94 |  212.60 |480 |  0 |  0 | 80894.5 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  212.60 |  0 |  0 |  0 | 80894.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 28.253s, TTFT=28252.51ms): Avg=3.22 | Min=3.22 | Max=3.22 tps
   Prefill Chunks (1): C1:91t/3.2tps/90%
   Decode  (64 tok, 16.101s): Avg=3.97 | Min=2.99 | Max=4.96 tps
   Latency (ms) : Min=201.80 | P10=206.30 | P25=226.70 | P50=257.12 | P75=268.48 | P90=286.99 | P95=300.86 | P99=334.39 | Max=334.39
   Mean/SD/Jitt : Mean=251.58ms | StdDev=30.69ms | Jitter=10.09ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (59040): RawRAM=54308 (91.99%) | Lookahead=351 (+0.59%) | ColdMiss=4381 (7.42%) | EFF HIT=92.58%
   Lookahead    : 2846 prefetched -> 671 consumed (23.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.8% | @64= 92.6% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1230 |  952 |  13 | 265 | 78.5%| 468.31 | | L24 | 1230 | 1172 |   2 |  56 | 95.4%| 157.91 |
   | L01 | 1230 | 1112 |   6 | 112 | 90.9%| 466.92 | | L25 | 1230 | 1161 |   3 |  66 | 94.6%| 135.35 |
   | L02 | 1230 | 1096 |   1 | 133 | 89.2%| 523.90 | | L26 | 1230 | 1131 |   6 |  93 | 92.4%| 244.38 |
   | L03 | 1230 | 1166 |   0 |  64 | 94.8%| 530.13 | | L27 | 1230 | 1154 |   1 |  75 | 93.9%| 174.83 |
   | L04 | 1230 | 1157 |   0 |  73 | 94.1%| 508.42 | | L28 | 1230 | 1103 |  11 | 116 | 90.6%| 295.14 |
   | L05 | 1230 | 1144 |   1 |  85 | 93.1%| 310.18 | | L29 | 1230 | 1132 |   7 |  91 | 92.6%| 185.82 |
   | L06 | 1230 | 1140 |   1 |  89 | 92.8%| 319.58 | | L30 | 1230 | 1100 |  10 | 120 | 90.2%| 234.79 |
   | L07 | 1230 | 1143 |   1 |  86 | 93.0%| 146.56 | | L31 | 1230 | 1100 |  16 | 114 | 90.7%| 250.63 |
   | L08 | 1230 | 1176 |   1 |  53 | 95.7%|  68.48 | | L32 | 1230 | 1128 |  11 |  91 | 92.6%| 306.42 |
   | L09 | 1230 | 1170 |   0 |  60 | 95.1%|  75.95 | | L33 | 1230 | 1131 |   5 |  94 | 92.4%| 151.25 |
   | L10 | 1230 | 1151 |   1 |  78 | 93.7%| 143.19 | | L34 | 1230 | 1110 |  23 |  97 | 92.1%| 218.95 |
   | L11 | 1230 | 1167 |   0 |  63 | 94.9%|  85.91 | | L35 | 1230 | 1150 |   6 |  74 | 94.0%| 121.00 |
   | L12 | 1230 | 1144 |   0 |  86 | 93.0%| 167.31 | | L36 | 1230 | 1118 |  10 | 102 | 91.7%| 207.42 |
   | L13 | 1230 | 1140 |   1 |  89 | 92.8%| 129.64 | | L37 | 1230 | 1144 |   5 |  81 | 93.4%| 178.59 |
   | L14 | 1230 | 1132 |   3 |  95 | 92.3%| 250.63 | | L38 | 1230 | 1153 |   3 |  74 | 94.0%| 218.07 |
   | L15 | 1230 | 1127 |   6 |  97 | 92.1%| 300.78 | | L39 | 1230 | 1133 |   7 |  90 | 92.7%| 265.06 |
   | L16 | 1230 | 1128 |   9 |  93 | 92.4%| 221.83 | | L40 | 1230 | 1104 |  22 | 104 | 91.5%| 359.06 |
   | L17 | 1230 | 1131 |   6 |  93 | 92.4%| 206.79 | | L41 | 1230 | 1122 |  13 |  95 | 92.3%| 181.49 |
   | L18 | 1230 | 1130 |  11 |  89 | 92.8%| 189.87 | | L42 | 1230 | 1104 |  23 | 103 | 91.6%| 234.79 |
   | L19 | 1230 | 1152 |   6 |  72 | 94.1%| 119.56 | | L43 | 1230 | 1142 |  12 |  76 | 93.8%| 201.66 |
   | L20 | 1230 | 1109 |  17 | 104 | 91.5%| 227.59 | | L44 | 1230 | 1126 |  16 |  88 | 92.8%| 194.46 |
   | L21 | 1230 | 1130 |   4 |  96 | 92.2%| 251.90 | | L45 | 1230 | 1119 |  20 |  91 | 92.6%| 216.06 |
   | L22 | 1230 | 1157 |   3 |  70 | 94.3%| 165.43 | | L46 | 1230 | 1159 |   4 |  67 | 94.6%| 253.52 |
   | L23 | 1230 | 1118 |  18 |  94 | 92.4%| 247.75 | | L47 | 1230 | 1140 |   6 |  84 | 93.2%| 251.90 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 17581.42 MB (Load=4614.69 | Prefill=7175.05 | Warmup=0.00 | Decode=5791.68 MB)
   SSD Data/Token (Decode)      : Avg=90.495 MB/tok (Min=76.557 | P50=86.579 | P95=106.906 | Max=127.644 MB) | Prefill=78.847 MB/tok
   NVMe Batches / Requests      : 1241 Batches | 24757 Raw -> 23768 Merged (989 LBA Merges, Avg 757.5 KB/io)
   SSD I/O Size Histogram       : <64K=2178 | 64K-512K=5500 | 512K-2M=15647 | >2M=443
   SSD Read Bandwidth (Active)  : Min=5.52 | Avg=649.17 | Peak=10622.52 MB/s | WallAmort=396.39 MB/s (100.0% of 511.5 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=18579.01 MB | Write=128.00 MB | Syscalls=40820
   Sync Stall vs Async DMA      : SyncStall=12701.86 ms | AsyncOverlapped=18862.29 ms (59.8% Overlapped)
   RAM Traffic & Active BW      : 622.87 GB moved | Active=23.92 GB/s (51.9% STREAM) | WallAmort=14.04 GB/s (Max=46.12 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=28.25s (63.7%, 7175.05 MB SSD) | Decode=16.10s (36.3%, 5791.68 MB SSD)
   CPU Time & Utilization       : User=84.359s + Sys=6.125s (Wall=56.473s) | SysUtil=40.1% | ThrUtil=40.1% | 103.23 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  12611.21 ms (81362.7 us/tok | 28.43%)
   MoE AVX2 Q8 Expert Compute   :  11951.27 ms (77105.0 us/tok | 26.95%)
   Router + Lookahead Dispatch  :    703.44 ms ( 4538.3 us/tok |  1.59%)
   LM Head Output Projection    :   1475.03 ms ( 9516.3 us/tok |  3.33%)
   Foreground NVMe Sync Stall   :  12701.86 ms (81947.5 us/tok | 28.64%)
   Unaccounted / OMP & Sampling :   4911.09 ms (31684.5 us/tok | 11.07%) | Total Wall=44353.91 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    80.66%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.98%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     7.71%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.04%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.61%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7725.95 MB (3723 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=4.52 tps | Avg=4.52 tps | Hit=95.4% | NVMe=562.9 MB/s (13785.34 MB, QD=64) | RSS=13666.7 MB
[LIVE-PREFILL] 512/512 tok | Chunk=5.31 tps | Avg=4.88 tps | Hit=96.7% | NVMe=560.8 MB/s (18015.74 MB, QD=64) | RSS=13668.9 MB
[LIVE-DECODE] 8/128 tok | Avg=3.47 tps | Hit=96.7% (LA:+0.0%) | NVMe=567.4 MB/s (18877.69 MB) | RSS=13668.9 MB
[LIVE-DECODE] 16/128 tok | Avg=3.80 tps | Hit=96.7% (LA:+0.1%) | NVMe=579.5 MB/s (19667.58 MB) | RSS=13637.2 MB
[LIVE-DECODE] 24/128 tok | Avg=4.06 tps | Hit=96.7% (LA:+0.1%) | NVMe=594.1 MB/s (20437.73 MB) | RSS=13627.1 MB
[LIVE-DECODE] 32/128 tok | Avg=4.31 tps | Hit=96.8% (LA:+0.1%) | NVMe=611.2 MB/s (21233.07 MB) | RSS=13618.5 MB
[LIVE-DECODE] 40/128 tok | Avg=4.46 tps | Hit=96.8% (LA:+0.1%) | NVMe=625.8 MB/s (21968.63 MB) | RSS=13604.7 MB
[LIVE-DECODE] 48/128 tok | Avg=4.59 tps | Hit=96.8% (LA:+0.1%) | NVMe=641.6 MB/s (22669.22 MB) | RSS=13598.5 MB
[LIVE-DECODE] 56/128 tok | Avg=4.71 tps | Hit=96.8% (LA:+0.1%) | NVMe=655.8 MB/s (23301.11 MB) | RSS=13596.3 MB
[LIVE-DECODE] 64/128 tok | Avg=4.78 tps | Hit=96.9% (LA:+0.1%) | NVMe=669.9 MB/s (24010.05 MB) | RSS=13596.3 MB
[LIVE-DECODE] 72/128 tok | Avg=4.81 tps | Hit=96.9% (LA:+0.1%) | NVMe=683.7 MB/s (24748.51 MB) | RSS=13595.9 MB
[LIVE-DECODE] 80/128 tok | Avg=4.87 tps | Hit=96.9% (LA:+0.1%) | NVMe=699.3 MB/s (25477.30 MB) | RSS=13593.6 MB
[LIVE-DECODE] 88/128 tok | Avg=4.88 tps | Hit=96.9% (LA:+0.2%) | NVMe=713.0 MB/s (26208.04 MB) | RSS=13587.5 MB
[LIVE-DECODE] 96/128 tok | Avg=4.94 tps | Hit=97.0% (LA:+0.2%) | NVMe=729.3 MB/s (26951.63 MB) | RSS=13585.0 MB
[LIVE-DECODE] 104/128 tok | Avg=4.98 tps | Hit=97.0% (LA:+0.2%) | NVMe=743.0 MB/s (27638.40 MB) | RSS=13583.4 MB
[LIVE-DECODE] 112/128 tok | Avg=5.02 tps | Hit=97.0% (LA:+0.2%) | NVMe=758.1 MB/s (28321.41 MB) | RSS=13580.0 MB
[LIVE-DECODE] 120/128 tok | Avg=5.07 tps | Hit=97.0% (LA:+0.2%) | NVMe=773.1 MB/s (28989.83 MB) | RSS=13576.6 MB
[LIVE-DECODE] 128/128 tok | Avg=5.03 tps | Hit=97.0% (LA:+0.2%) | NVMe=785.9 MB/s (29661.71 MB) | RSS=13560.1 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7725.95 MB (3723/25088 exp = 14.84% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13560.08 MB | Peak=14118.84 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : "22!7!5!m!m!2!m!2!9!3!2!2!7!2!5!7!ar!
!9!3!2!a!2!
!a!2!a!a!2!
!
!7!p!3!2!m!7!7!2!7!7!ing!2!n!2!2!2!7!2!u!2!7!7!7!2!7!2!2!7!7!7!7!3!1!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=54.1% | AvgMargin=0.204 | MinMargin=0.004
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      17 | 2              |   11.64 |   9.2% |      18 |   11.26 | 104920.17 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    8.98 |   1.0% |     277 |    8.80 |  364.10 |439 | 39 |  2 | 121457.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  364.10 |  0 |  0 |  0 | 121457.0 |
   |    4 |      22 | 7              |   10.62 |   6.7% |      17 |   10.52 |  283.88 |455 | 25 |  0 | 104769.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  283.88 |  0 |  0 |  0 | 104769.5 |
   |    6 |      20 | 5              |   11.59 |   6.9% |      22 |   11.52 |  239.42 |453 | 27 |  0 | 106271.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.42 |  0 |  0 |  0 | 106271.5 |
   |    8 |      76 | m              |   12.53 |   7.3% |      17 |   12.18 |  266.22 |455 | 25 |  0 | 108819.5 |
   |   14 |      76 | m              |   10.95 |   5.1% |      17 |   10.60 |  277.85 |464 | 16 |  0 | 106057.0 |
   |   15 |       0 | !              |     nan | 100.0% |       1 |     nan |  277.85 |  0 |  0 |  0 | 106057.0 |
   |    9 |       0 | !              |     nan | 100.0% |       1 |     nan |  266.22 |  0 |  0 |  0 | 108819.5 |
   |   20 |      18 | 3              |   12.24 |   5.2% |      24 |   12.00 |  251.32 |469 | 11 |  0 | 101507.0 |
   |  126 |      18 | 3              |   10.39 |   6.0% |      22 |    9.95 |  287.91 |478 |  2 |  0 | 86244.5 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  287.91 |  0 |  0 |  0 | 86244.5 |
   |  128 |      16 | 1              |   12.00 |  17.3% |      17 |   11.87 |  217.31 |477 |  3 |  0 | 86757.0 |
   |  129 |       0 | !              |     nan | 100.0% |       1 |     nan |  217.31 |  0 |  0 |  0 | 86757.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 104.920s, TTFT=104920.17ms): Avg=4.88 | Min=4.52 | Max=5.31 tps
   Prefill Chunks (2): C1:256t/4.5tps/95% | C2:256t/5.3tps/97%
   Decode  (128 tok, 25.467s): Avg=5.03 | Min=2.75 | Max=6.09 tps
   Latency (ms) : Min=164.33 | P10=170.94 | P25=174.47 | P50=189.74 | P75=207.53 | P90=243.98 | P95=277.85 | P99=364.10 | Max=364.10
   Mean/SD/Jitt : Mean=198.96ms | StdDev=35.48ms | Jitter=10.28ms | Hist(<25/50/100/200/>200ms): 0/0/0/86/42
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (276480): RawRAM=267819 (96.87%) | Lookahead=478 (+0.17%) | ColdMiss=8183 (2.96%) | EFF HIT=97.04%
   Lookahead    : 5804 prefetched -> 1118 consumed (19.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.7% | @64= 96.9% | @128= 97.0% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 5760 | 5195 |  22 | 543 | 90.6%| 951.78 | | L24 | 5760 | 5658 |   5 |  97 | 98.3%| 300.78 |
   | L01 | 5760 | 5562 |   7 | 191 | 96.7%| 962.48 | | L25 | 5760 | 5668 |   2 |  90 | 98.4%| 195.51 |
   | L02 | 5760 | 5526 |   5 | 229 | 96.0%|1056.23 | | L26 | 5760 | 5575 |   5 | 180 | 96.9%| 362.82 |
   | L03 | 5760 | 5686 |   1 |  73 | 98.7%| 902.34 | | L27 | 5760 | 5642 |   2 | 116 | 98.0%| 327.10 |
   | L04 | 5760 | 5648 |   1 | 111 | 98.1%| 776.12 | | L28 | 5760 | 5548 |   8 | 204 | 96.5%| 554.57 |
   | L05 | 5760 | 5621 |   0 | 139 | 97.6%| 727.51 | | L29 | 5760 | 5582 |  13 | 165 | 97.1%| 574.73 |
   | L06 | 5760 | 5638 |   1 | 121 | 97.9%| 456.81 | | L30 | 5760 | 5501 |  23 | 236 | 95.9%| 424.93 |
   | L07 | 5760 | 5626 |   0 | 134 | 97.7%| 229.10 | | L31 | 5760 | 5538 |   7 | 215 | 96.3%| 380.27 |
   | L08 | 5760 | 5692 |   0 |  68 | 98.8%|  88.40 | | L32 | 5760 | 5587 |   4 | 169 | 97.1%| 503.81 |
   | L09 | 5760 | 5692 |   0 |  68 | 98.8%|  87.16 | | L33 | 5760 | 5547 |  12 | 201 | 96.5%| 324.10 |
   | L10 | 5760 | 5657 |   1 | 102 | 98.2%| 209.18 | | L34 | 5760 | 5469 |  32 | 259 | 95.5%| 494.07 |
   | L11 | 5760 | 5692 |   1 |  67 | 98.8%|  85.91 | | L35 | 5760 | 5589 |  11 | 160 | 97.2%| 292.41 |
   | L12 | 5760 | 5652 |   1 | 107 | 98.1%| 206.79 | | L36 | 5760 | 5587 |   9 | 164 | 97.2%| 328.42 |
   | L13 | 5760 | 5630 |   1 | 129 | 97.8%| 187.26 | | L37 | 5760 | 5565 |   4 | 191 | 96.7%| 394.78 |
   | L14 | 5760 | 5623 |   8 | 129 | 97.8%| 378.83 | | L38 | 5760 | 5622 |   2 | 136 | 97.6%| 443.65 |
   | L15 | 5760 | 5578 |  13 | 169 | 97.1%| 466.21 | | L39 | 5760 | 5577 |  15 | 168 | 97.1%| 498.17 |
   | L16 | 5760 | 5573 |   4 | 183 | 96.8%| 438.01 | | L40 | 5760 | 5572 |  18 | 170 | 97.0%| 594.04 |
   | L17 | 5760 | 5549 |  13 | 198 | 96.6%| 469.97 | | L41 | 5760 | 5577 |  13 | 170 | 97.0%| 352.91 |
   | L18 | 5760 | 5555 |  19 | 186 | 96.8%| 407.93 | | L42 | 5760 | 5486 |  24 | 250 | 95.7%| 561.77 |
   | L19 | 5760 | 5589 |  15 | 156 | 97.3%| 303.93 | | L43 | 5760 | 5496 |  24 | 240 | 95.8%| 547.36 |
   | L20 | 5760 | 5498 |  25 | 237 | 95.9%| 491.19 | | L44 | 5760 | 5477 |  20 | 263 | 95.4%| 573.29 |
   | L21 | 5760 | 5534 |  18 | 208 | 96.4%| 748.19 | | L45 | 5760 | 5475 |  34 | 251 | 95.6%| 643.87 |
   | L22 | 5760 | 5656 |   2 | 102 | 98.2%| 251.90 | | L46 | 5760 | 5647 |   3 | 110 | 98.1%| 427.81 |
   | L23 | 5760 | 5576 |  23 | 161 | 97.2%| 419.17 | | L47 | 5760 | 5586 |   7 | 167 | 97.1%| 419.21 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 29661.71 MB (Load=4614.69 | Prefill=13401.04 | Warmup=0.00 | Decode=11645.97 MB)
   SSD Data/Token (Decode)      : Avg=90.984 MB/tok (Min=74.946 | P50=90.546 | P95=103.781 | Max=118.610 MB) | Prefill=26.174 MB/tok
   NVMe Batches / Requests      : 2554 Batches | 52285 Raw -> 50480 Merged (1805 LBA Merges, Avg 601.7 KB/io)
   SSD I/O Size Histogram       : <64K=9473 | 64K-512K=10597 | 512K-2M=29910 | >2M=500
   SSD Read Bandwidth (Active)  : Min=7.43 | Avg=785.90 | Peak=10897.87 MB/s | WallAmort=227.49 MB/s
   OS Kernel I/O Verification   : Read=29681.84 MB | Write=0.00 MB | Syscalls=59995
   Sync Stall vs Async DMA      : SyncStall=23070.96 ms | AsyncOverlapped=29502.85 ms (56.1% Overlapped)
   RAM Traffic & Active BW      : 2072.99 GB moved | Active=20.87 GB/s | WallAmort=15.90 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=104.92s (80.5%, 13401.04 MB SSD) | Decode=25.47s (19.5%, 11645.97 MB SSD)
   CPU Time & Utilization       : User=349.766s + Sys=13.484s (Wall=141.807s) | SysUtil=64.0% | ThrUtil=64.0% | 59.24 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  46887.24 ms (73261.3 us/tok | 35.96%)
   MoE AVX2 Q8 Expert Compute   :  49828.18 ms (77856.5 us/tok | 38.22%)
   Router + Lookahead Dispatch  :   2787.93 ms ( 4356.1 us/tok |  2.14%)
   LM Head Output Projection    :   2634.78 ms ( 4116.9 us/tok |  2.02%)
   Foreground NVMe Sync Stall   :  23070.96 ms (36048.4 us/tok | 17.69%)
   Unaccounted / OMP & Sampling :   5178.47 ms ( 8091.4 us/tok |  3.97%) | Total Wall=130387.57 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    85.98%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.70%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.09%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.03%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.20%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 15134.2ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\n\n\n\n\n\nu\nW\n\n\n\n0\n0'
[Stage 3] /v1/chat/completions (stream=true SSE) 3481.2ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7672.00 MB (3697 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=4.54 tps | Avg=4.54 tps | Hit=95.4% | NVMe=565.4 MB/s (13785.34 MB, QD=64) | RSS=13614.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=5.44 tps | Avg=4.95 tps | Hit=96.7% | NVMe=561.5 MB/s (18015.74 MB, QD=64) | RSS=13613.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=5.69 tps | Avg=5.17 tps | Hit=97.1% | NVMe=560.4 MB/s (21879.79 MB, QD=64) | RSS=13614.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=5.74 tps | Avg=5.31 tps | Hit=97.4% | NVMe=557.8 MB/s (25725.63 MB, QD=64) | RSS=13613.7 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=5.74 tps | Avg=5.39 tps | Hit=97.5% | NVMe=557.3 MB/s (29428.90 MB, QD=64) | RSS=13614.2 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=5.72 tps | Avg=5.44 tps | Hit=97.6% | NVMe=558.6 MB/s (33138.00 MB, QD=64) | RSS=13615.2 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=5.65 tps | Avg=5.47 tps | Hit=97.7% | NVMe=558.6 MB/s (36857.32 MB, QD=64) | RSS=13614.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=5.68 tps | Avg=5.49 tps | Hit=97.8% | NVMe=557.4 MB/s (40418.65 MB, QD=64) | RSS=13615.6 MB
[LIVE-DECODE] 8/64 tok | Avg=3.42 tps | Hit=97.8% (LA:+0.0%) | NVMe=560.2 MB/s (41338.16 MB) | RSS=13612.6 MB
[LIVE-DECODE] 16/64 tok | Avg=3.93 tps | Hit=97.8% (LA:+0.0%) | NVMe=566.6 MB/s (42152.09 MB) | RSS=13604.5 MB
[LIVE-DECODE] 24/64 tok | Avg=4.13 tps | Hit=97.8% (LA:+0.0%) | NVMe=573.2 MB/s (42963.96 MB) | RSS=13604.5 MB
[LIVE-DECODE] 32/64 tok | Avg=4.26 tps | Hit=97.8% (LA:+0.0%) | NVMe=580.6 MB/s (43816.70 MB) | RSS=13589.6 MB
[LIVE-DECODE] 40/64 tok | Avg=4.40 tps | Hit=97.8% (LA:+0.0%) | NVMe=589.7 MB/s (44741.65 MB) | RSS=13567.4 MB
[LIVE-DECODE] 48/64 tok | Avg=4.51 tps | Hit=97.8% (LA:+0.0%) | NVMe=598.7 MB/s (45670.64 MB) | RSS=13554.6 MB
[LIVE-DECODE] 56/64 tok | Avg=4.57 tps | Hit=97.8% (LA:+0.1%) | NVMe=606.5 MB/s (46534.73 MB) | RSS=13544.9 MB
[LIVE-DECODE] 64/64 tok | Avg=4.67 tps | Hit=97.8% (LA:+0.1%) | NVMe=615.9 MB/s (47398.97 MB) | RSS=13541.4 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7672.00 MB (3697/25088 exp = 14.74% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13541.45 MB | Peak=14064.93 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : "
2!
!
!2!2!1!2!
!
!
!
!2!
!1!2!2!2!2!2!2!2!2!2!2!<|im_end|>!m!2!2!m!2!2!2!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=56.2% | AvgMargin=0.439 | MinMargin=0.016
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     198 | \n             |    7.38 |   0.7% |      17 |    7.24 | 372763.44 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    9.10 |   5.3% |     198 |    8.10 |  364.16 |419 | 54 |  7 | 136519.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  364.16 |  0 |  0 |  0 | 136519.5 |
   |    4 |     198 | \n             |   12.12 |  49.7% |      17 |    7.63 |  320.04 |432 | 42 |  6 | 125082.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  320.04 |  0 |  0 |  0 | 125082.0 |
   |    6 |     198 | \n             |   11.59 |  18.1% |      16 |   10.70 |  262.96 |449 | 30 |  1 | 105057.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  262.96 |  0 |  0 |  0 | 105057.0 |
   |    8 |      17 | 2              |   11.54 |   9.1% |      18 |   10.95 |  221.05 |459 | 19 |  2 | 104132.0 |
   |   30 |      17 | 2              |   12.74 |  24.7% |      16 |   11.99 |  229.21 |463 | 17 |  0 | 111469.5 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  229.21 |  0 |  0 |  0 | 111469.5 |
   |   24 |      17 | 2              |    9.93 |   6.7% |      18 |    8.79 |  223.85 |468 | 12 |  0 | 98707.0 |
   |   25 |       0 | !              |     nan | 100.0% |       1 |     nan |  223.85 |  0 |  0 |  0 | 98707.0 |
   |   62 |      17 | 2              |   11.61 |  14.1% |      16 |   10.20 |  187.19 |461 | 19 |  0 | 117607.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  187.19 |  0 |  0 |  0 | 117607.0 |
   |   64 |      17 | 2              |   13.33 |  46.1% |      16 |   12.08 |  190.87 |454 | 26 |  0 | 116869.5 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  190.87 |  0 |  0 |  0 | 116869.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 372.763s, TTFT=372763.44ms): Avg=5.49 | Min=4.54 | Max=5.74 tps
   Prefill Chunks (8): C1:256t/4.5tps/95% | C2:256t/5.4tps/97% | C3:256t/5.7tps/97% | C4:256t/5.7tps/97%
                       C5:256t/5.7tps/98% | C6:256t/5.7tps/98% | C7:256t/5.7tps/98% | C8:256t/5.7tps/98%
   Decode  (64 tok, 13.705s): Avg=4.67 | Min=2.75 | Max=5.89 tps
   Latency (ms) : Min=169.67 | P10=185.94 | P25=190.87 | P50=212.27 | P75=220.53 | P90=229.21 | P95=320.04 | P99=364.16 | Max=364.16
   Mean/SD/Jitt : Mean=214.13ms | StdDev=38.51ms | Jitter=7.79ms | Hist(<25/50/100/200/>200ms): 0/0/0/24/40
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (998400): RawRAM=975859 (97.74%) | Lookahead=628 (+0.06%) | ColdMiss=21913 (2.19%) | EFF HIT=97.81%
   Lookahead    : 3586 prefetched -> 948 consumed (26.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.8% | @64= 97.8% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |20800 |18780 |  52 |1968 | 90.5%|3402.83 | | L24 |20800 |20627 |   4 | 169 | 99.2%| 362.82 |
   | L01 |20800 |20278 |  19 | 503 | 97.6%| 958.74 | | L25 |20800 |20632 |   2 | 166 | 99.2%| 321.46 |
   | L02 |20800 |20224 |   3 | 573 | 97.2%|1313.96 | | L26 |20800 |20294 |  10 | 496 | 97.6%|1009.50 |
   | L03 |20800 |20721 |   2 |  77 | 99.6%| 426.73 | | L27 |20800 |20536 |  11 | 253 | 98.8%| 633.52 |
   | L04 |20800 |20600 |   3 | 197 | 99.1%| 747.07 | | L28 |20800 |20183 |  22 | 595 | 97.1%|1236.96 |
   | L05 |20800 |20524 |   2 | 274 | 98.7%| 793.31 | | L29 |20800 |20343 |  31 | 426 | 98.0%| 764.87 |
   | L06 |20800 |20552 |   4 | 244 | 98.8%| 582.76 | | L30 |20800 |19969 |  30 | 801 | 96.1%|1220.04 |
   | L07 |20800 |20543 |   6 | 251 | 98.8%| 434.62 | | L31 |20800 |20085 |  16 | 699 | 96.6%|1073.12 |
   | L08 |20800 |20728 |   1 |  71 | 99.7%|  93.38 | | L32 |20800 |20284 |  14 | 502 | 97.6%|1111.01 |
   | L09 |20800 |20725 |   0 |  75 | 99.6%| 112.06 | | L33 |20800 |20171 |  23 | 606 | 97.1%| 927.64 |
   | L10 |20800 |20645 |   4 | 151 | 99.3%| 276.42 | | L34 |20800 |19923 |  32 | 845 | 95.9%|1333.84 |
   | L11 |20800 |20725 |   2 |  73 | 99.6%|  98.36 | | L35 |20800 |20346 |  13 | 441 | 97.9%| 704.37 |
   | L12 |20800 |20673 |   0 | 127 | 99.4%| 242.50 | | L36 |20800 |20295 |  13 | 492 | 97.6%| 798.00 |
   | L13 |20800 |20589 |   1 | 210 | 99.0%| 311.13 | | L37 |20800 |20242 |   4 | 554 | 97.3%|1084.69 |
   | L14 |20800 |20527 |   3 | 270 | 98.7%| 494.07 | | L38 |20800 |20467 |   3 | 330 | 98.4%| 761.35 |
   | L15 |20800 |20378 |   5 | 417 | 98.0%| 849.71 | | L39 |20800 |20291 |  16 | 493 | 97.6%|1035.82 |
   | L16 |20800 |20282 |  11 | 507 | 97.6%| 985.06 | | L40 |20800 |20393 |  14 | 393 | 98.1%| 943.70 |
   | L17 |20800 |20131 |   8 | 661 | 96.8%|1317.80 | | L41 |20800 |20374 |   7 | 419 | 98.0%| 661.16 |
   | L18 |20800 |20184 |  20 | 596 | 97.1%|1203.12 | | L42 |20800 |20090 |  16 | 694 | 96.7%|1126.42 |
   | L19 |20800 |20388 |  17 | 395 | 98.1%| 625.15 | | L43 |20800 |19974 |  28 | 798 | 96.2%|1336.72 |
   | L20 |20800 |20021 |  27 | 752 | 96.4%|1171.07 | | L44 |20800 |19995 |  18 | 787 | 96.2%|1248.85 |
   | L21 |20800 |20142 |  33 | 625 | 97.0%|1408.03 | | L45 |20800 |20051 |  33 | 716 | 96.6%|1204.20 |
   | L22 |20800 |20615 |   4 | 181 | 99.1%| 353.42 | | L46 |20800 |20580 |  10 | 210 | 99.0%| 440.77 |
   | L23 |20800 |20266 |  17 | 517 | 97.5%| 831.13 | | L47 |20800 |20473 |  14 | 313 | 98.5%| 684.28 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 47398.97 MB (Load=4614.69 | Prefill=35803.96 | Warmup=0.00 | Decode=6980.32 MB)
   SSD Data/Token (Decode)      : Avg=109.068 MB/tok (Min=92.255 | P50=108.552 | P95=132.294 | Max=133.320 MB) | Prefill=17.482 MB/tok
   NVMe Batches / Requests      : 2302 Batches | 110885 Raw -> 106712 Merged (4173 LBA Merges, Avg 454.8 KB/io)
   SSD I/O Size Histogram       : <64K=33329 | 64K-512K=18953 | 512K-2M=53938 | >2M=492
   SSD Read Bandwidth (Active)  : Min=6.90 | Avg=615.88 | Peak=11071.16 MB/s | WallAmort=122.65 MB/s
   OS Kernel I/O Verification   : Read=47419.51 MB | Write=0.00 MB | Syscalls=116225
   Sync Stall vs Async DMA      : SyncStall=59245.29 ms | AsyncOverlapped=68748.90 ms (53.7% Overlapped)
   RAM Traffic & Active BW      : 5562.56 GB moved | Active=17.92 GB/s | WallAmort=14.39 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=372.76s (96.5%, 35803.96 MB SSD) | Decode=13.70s (3.5%, 6980.32 MB SSD)
   CPU Time & Utilization       : User=1150.031s + Sys=19.625s (Wall=397.573s) | SysUtil=73.5% | ThrUtil=73.5% | 68.03 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 144743.91 ms (68534.1 us/tok | 37.45%)
   MoE AVX2 Q8 Expert Compute   : 164429.74 ms (77855.0 us/tok | 42.55%)
   Router + Lookahead Dispatch  :   9008.86 ms ( 4265.6 us/tok |  2.33%)
   LM Head Output Projection    :   1187.69 ms (  562.4 us/tok |  0.31%)
   Foreground NVMe Sync Stall   :  59245.29 ms (28051.7 us/tok | 15.33%)
   Unaccounted / OMP & Sampling :   7852.47 ms ( 3718.0 us/tok |  2.03%) | Total Wall=386467.97 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    91.34%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     0.92%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.57%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     3.59%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.58%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=45.0s | Competitor drastic-underperform cutoff=225.0s (5x Apex)
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=225.0s) ===
  [Colibri-Qwen38] [gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
  [Colibri-Qwen38] [gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
  [Colibri-Qwen38] == Qwen3.8-Flash-Next native text engine | cache=72/layer | CPU ==
  [Colibri-Qwen38] [tok] loaded 248320 base pieces + 33 added tokens (max id 248319) from D:/apex_d_drive/models/qwen38/tokenizer.json
  [Colibri-Qwen38] [qwen38] native text weights: prefix=model, 48 layers, PLE=1, cache=72/layer, FP8=native, BF16=native (resident matrices 4.40 GiB)
  [Colibri-Qwen38] [qwen38] MTP head mtp.*: wiring b (a norm per stream, fc_hidden per stream), RoPE base 1e+07, 96.86 MiB resident; routed experts Q8_0 from the snapshot (its own GGUF), cache 72 (Q38_MTP_CAP) x 4.98 MiB = 0.35 GiB full
  [Colibri-Qwen38] [qwen38] MTP norm weights, mean: embedding -0.7642, hidden -0.3284, mixer 3.7881 (q38_rms0 scales by 1+w; a plain norm's weights would sit near 1)
  [Colibri-Qwen38] [qwen38] trunk: 62 matrices int8 on the CPU (0.08 GiB, 0.28 GiB of BF16 released) in 0.1s; Q38_TRUNK_CPU_INT8=0 keeps BF16
  [Colibri-Qwen38] [qwen38 MTP] draft vocabulary: the lm_head has no int8 rows on the host, so the head scores the whole vocabulary (Q38_MTP_VOCAB=0 silences this)
  [Colibri-Qwen38] [qwen38] routed experts: GGUF IQ2_XXS/IQ2_XXS/IQ4_NL (layer 0), 1.68 MiB per expert; cache 72/layer
  [Colibri-Qwen38] [qwen38] trunk: 62 int8 matrices interleaved by 16 for the CPU in 0.01s (Q38_ILV16=0 keeps the rows)
  [Colibri-Qwen38] resident weights loaded in 8.7s | RSS after load: 4.60 GB
  [Colibri-Qwen38] [qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=225.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.1s / cutoff=225.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=225.0s
  [Colibri-Qwen38] TTFT: 21.52 s (time to first token)
  [Colibri-Qwen38] [qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
  [Colibri-Qwen38] [qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
  [Colibri-Qwen38] [qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes
  [Colibri-Qwen38] 
  [Colibri-Qwen38] PEAK RSS: 10.70 GB
  [Colibri-Qwen38] Expert cache hit rate: 62.0% (hit=15849 miss=9733)
  [Colibri-Qwen38] Speed: 0.77 tok/s (41.6s for 32 tokens)
  [Colibri-Qwen38] [STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage
  [Colibri-Qwen38] 
  [Colibri-Qwen38] Reference: 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 
  [Colibri-Qwen38] C engine : 220 248046 198 248045 74455 198 248068 198 760 1156 682 3106 1092 7701 310 381 264 7132 36412 2805 269 82987 886 314 5587 13 6558 728 22903 411 25 271 Text      :  <|im_end|>
  [Colibri-Qwen38] <|im_start|>assistant
  [Colibri-Qwen38] <think>
  [Colibri-Qwen38] The user has sent what appears to be a garbled/corrupted string of characters. Let me analyze this:
  [Colibri-Qwen38] 
  [Colibri-Qwen38] 
  [Colibri-Qwen38] 
  [Colibri-Qwen38] Matching tokens: 0/32
=== [Colibri-Qwen38] Finished rc=1 elapsed=52.60s cancelled=False ===
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 2.97 | 3.42 | 280.51 | 90.45% | 602.48 | 12927.72 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 4.88 | 5.03 | 189.74 | 97.04% | 785.90 | 14118.84 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 5.49 | 4.67 | 212.27 | 97.81% | 615.88 | 14064.93 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.77 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 868K Nov 13 16:35 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 868K Nov 13 16:35 build/apex.exe
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
   CPU Model          : AMD EPYC 9V45 96-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.52 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    560.28 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1660.38 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9154.30 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11937.35 MB/s
   RND4K Q32T16 Read                  :   1017.07 MB/s (  260371 IOPS)
   RND4K Q1T1  Read                   :    961.82 MB/s (Latency: 4.06 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     94.83 GB/s
   AVX2 256-bit Sequential Write BW   :     87.56 GB/s
   STREAM Triad (A = B + s*C) BW      :     42.00 GB/s
   Random Pointer-Chase Latency       :     76.18 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     67.18 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    258.27 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     37.79 GB/s (FP32 Equiv)
================================================================================



=== [TEST] GLM-5.3-Flash 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_glm53_ud_iq2_xxs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (16) : [55, 229, 199, 135, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55] -> "tok_55tok_229tok_199tok_135tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55"
[Apex-Parity] Batched Tokens (16) : [55, 229, 199, 135, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55, 55] -> "tok_55tok_229tok_199tok_135tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55"
[Apex-Parity] Model Architecture : glm5-next (GLM-5.3-Flash)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] Qwen-3.8-Flash-Next 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_qwen38_ud_iq2_xs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (16) : [33, 49, 68, 113, 193, 68, 227, 49, 68, 66, 193, 19, 49, 18, 150, 49] -> "qtok_33qtok_49qtok_68qtok_113qtok_193qtok_68qtok_227qtok_49qtok_68qtok_66qtok_193qtok_19qtok_49qtok_18qtok_150qtok_49"
[Apex-Parity] Batched Tokens (16) : [33, 49, 68, 113, 193, 68, 227, 49, 68, 66, 193, 19, 49, 18, 150, 49] -> "qtok_33qtok_49qtok_68qtok_113qtok_193qtok_68qtok_227qtok_49qtok_68qtok_66qtok_193qtok_19qtok_49qtok_18qtok_150qtok_49"
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] GLM-5.3-Flash 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_glm53_ud_iq2_xxs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=1.93 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2492.93 tps | Avg=2492.93 tps | Hit=99.5% | NVMe=2989.0 MB/s (6.19 MB, QD=64) | RSS=71.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2235.06 tps | Avg=2356.96 tps | Hit=99.5% | NVMe=2899.9 MB/s (7.01 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1893.02 tps | Avg=2178.96 tps | Hit=99.5% | NVMe=2856.1 MB/s (7.78 MB, QD=64) | RSS=71.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1642.52 tps | Avg=2014.48 tps | Hit=99.5% | NVMe=2768.5 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1442.83 tps | Avg=1866.57 tps | Hit=99.5% | NVMe=2751.7 MB/s (9.33 MB, QD=64) | RSS=72.3 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1045.07 tps | Avg=1650.36 tps | Hit=99.5% | NVMe=2698.4 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1200.59 tps | Avg=1566.52 tps | Hit=99.5% | NVMe=2639.7 MB/s (10.83 MB, QD=64) | RSS=72.8 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1131.26 tps | Avg=1494.64 tps | Hit=99.5% | NVMe=2609.5 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=331.85 tps | Hit=99.5% (LA:+0.0%) | NVMe=2595.3 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=331.85 tps | Hit=99.5% (LA:+0.1%) | NVMe=2589.9 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=333.45 tps | Hit=99.5% (LA:+0.1%) | NVMe=2572.6 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=333.39 tps | Hit=99.5% (LA:+0.1%) | NVMe=2551.1 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=73.12 MB | Peak=73.12 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1370.23 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    3.04 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    3.04 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    3.02 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    3.02 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    3.00 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    3.00 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    2.99 | 11 |  1 |  0 |    49.5 |
   |   14 |     220 | tok_220        |  147.52 |  55.4% |      55 |  147.01 |    3.03 |  9 |  3 |  0 |   173.2 |
   |   15 |     197 | tok_197        |   65.84 |  97.8% |     133 |   62.03 |    3.03 |  0 |  0 |  0 |   173.2 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    3.03 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    3.03 |  0 |  0 |  0 |   173.2 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    3.00 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    3.00 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    3.04 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    3.04 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.370s, TTFT=1370.23ms): Avg=1494.64 | Min=1045.07 | Max=2492.93 tps
   Prefill Chunks (8): C1:256t/2492.9tps/99% | C2:256t/2235.1tps/99% | C3:256t/1893.0tps/99% | C4:256t/1642.5tps/99%
                       C5:256t/1442.8tps/99% | C6:256t/1045.1tps/99% | C7:256t/1200.6tps/99% | C8:256t/1131.3tps/99%
   Decode  (32 tok, 0.096s): Avg=333.39 | Min=328.47 | Max=337.43 tps
   Latency (ms) : Min=2.96 | P10=2.97 | P25=2.98 | P50=3.00 | P75=3.03 | P90=3.04 | P95=3.04 | P99=3.04 | Max=3.04
   Mean/SD/Jitt : Mean=3.00ms | StdDev=0.02ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   NVMe Batches / Requests      : 41 Batches | 748 Raw -> 310 Merged (438 LBA Merges, Avg 43.9 KB/io)
   SSD I/O Size Histogram       : <64K=203 | 64K-512K=107 | 512K-2M=0 | >2M=0
   SSD Read Bandwidth (Active)  : Min=341.38 | Avg=2551.14 | Peak=7225.43 MB/s | WallAmort=9.07 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=3.48 ms | AsyncOverlapped=4.24 ms (55.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=1.03 GB/s | WallAmort=0.98 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.37s (93.5%, 6.19 MB SSD) | Decode=0.10s (6.5%, 1.69 MB SSD)
   CPU Time & Utilization       : User=1.578s + Sys=0.422s (Wall=1.479s) | SysUtil=33.8% | ThrUtil=33.8% | 31.27 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1253.60 ms (  602.7 us/tok | 85.50%)
   MoE AVX2 Q8 Expert Compute   :    133.68 ms (   64.3 us/tok |  9.12%)
   Router + Lookahead Dispatch  :     36.76 ms (   17.7 us/tok |  2.51%)
   LM Head Output Projection    :      3.50 ms (    1.7 us/tok |  0.24%)
   Foreground NVMe Sync Stall   :      3.48 ms (    1.7 us/tok |  0.24%)
   Unaccounted / OMP & Sampling :     35.20 ms (   16.9 us/tok |  2.40%) | Total Wall=1466.22 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    23.74%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.12%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.44%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    70.79%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.91%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3291.00 tps | Avg=3291.00 tps | Hit=99.2% | NVMe=3808.9 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=3449.96 tps | Avg=3368.60 tps | Hit=99.2% | NVMe=5244.4 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=3016.92 tps | Avg=3242.61 tps | Hit=99.2% | NVMe=6209.3 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2945.08 tps | Avg=3162.73 tps | Hit=99.2% | NVMe=6901.4 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2762.66 tps | Avg=3073.70 tps | Hit=99.2% | NVMe=7429.7 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2538.37 tps | Avg=2969.33 tps | Hit=99.2% | NVMe=7845.0 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2295.33 tps | Avg=2849.79 tps | Hit=99.2% | NVMe=8223.9 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2241.22 tps | Avg=2756.24 tps | Hit=99.2% | NVMe=8577.5 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=318.24 tps | Hit=99.2% (LA:+0.0%) | NVMe=8463.5 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=319.57 tps | Hit=99.2% (LA:+0.1%) | NVMe=8405.4 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=320.82 tps | Hit=99.2% (LA:+0.1%) | NVMe=8309.8 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=320.96 tps | Hit=99.2% (LA:+0.1%) | NVMe=8237.4 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=91.73 MB | Peak=91.73 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_129qtok_68qtok_209qtok_223qtok_113qtok_229qtok_112qtok_193qtok_63qtok_128qtok_63qtok_128qtok_63qtok_194qtok_49qtok_49qtok_148qtok_254qtok_48qtok_254qtok_49"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=94.1% | AvgMargin=10.265 | MinMargin=0.247
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 |  743.04 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    3.24 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    3.24 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    3.09 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    3.09 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    3.11 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    3.11 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    3.13 | 16 |  0 |  0 |    32.0 |
   |   12 |     254 | qtok_254       |   71.34 |  95.3% |      66 |   68.21 |    3.15 | 16 |  0 |  0 |    32.0 |
   |   13 |     129 | qtok_129       |   76.30 |  99.3% |      49 |   71.12 |    3.15 |  0 |  0 |  0 |    32.0 |
   |   20 |     193 | qtok_193       |   68.95 | 100.0% |      17 |   58.95 |    3.14 | 14 |  2 |  0 |    87.5 |
   |   21 |      63 | qtok_63        |   75.06 |  99.9% |     193 |   67.57 |    3.14 |  0 |  0 |  0 |    87.5 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    3.13 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    3.13 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    3.13 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    3.13 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 0.743s, TTFT=743.04ms): Avg=2756.24 | Min=2241.22 | Max=3449.96 tps
   Prefill Chunks (8): C1:256t/3291.0tps/99% | C2:256t/3450.0tps/99% | C3:256t/3016.9tps/99% | C4:256t/2945.1tps/99%
                       C5:256t/2762.7tps/99% | C6:256t/2538.4tps/99% | C7:256t/2295.3tps/99% | C8:256t/2241.2tps/99%
   Decode  (32 tok, 0.100s): Avg=320.96 | Min=308.76 | Max=326.30 tps
   Latency (ms) : Min=3.06 | P10=3.08 | P25=3.09 | P50=3.11 | P75=3.13 | P90=3.15 | P95=3.24 | P99=3.24 | Max=3.24
   Mean/SD/Jitt : Mean=3.12ms | StdDev=0.04ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33024): RawRAM=32726 (99.10%) | Lookahead=42 (+0.13%) | ColdMiss=256 (0.78%) | EFF HIT=99.22%
   Lookahead    : 52 prefetched -> 46 consumed (88.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8256 | 8190 |   2 |  64 | 99.2%|   3.58 | | L02 | 8256 | 8171 |  21 |  64 | 99.2%|   4.82 |
   | L01 | 8256 | 8179 |  13 |  64 | 99.2%|   4.23 | | L03 | 8256 | 8186 |   6 |  64 | 99.2%|   3.85 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 155.14 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=3.83 MB)
   SSD Data/Token (Decode)      : Avg=0.120 MB/tok (Min=0.031 | P50=0.113 | P95=0.523 | Max=0.523 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 92 Batches | 34197 Raw -> 371 Merged (33826 LBA Merges, Avg 428.2 KB/io)
   SSD I/O Size Histogram       : <64K=217 | 64K-512K=154 | 512K-2M=0 | >2M=0
   SSD Read Bandwidth (Active)  : Min=464.43 | Avg=8237.37 | Peak=17970.64 MB/s | WallAmort=184.09 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=4.06 ms | AsyncOverlapped=17.74 ms (81.4% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=2.88 GB/s | WallAmort=2.50 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=0.74s (88.2%, 144.44 MB SSD) | Decode=0.10s (11.8%, 3.83 MB SSD)
   CPU Time & Utilization       : User=1.375s + Sys=0.344s (Wall=0.866s) | SysUtil=49.6% | ThrUtil=49.6% | 45.90 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    521.67 ms (  250.8 us/tok | 61.90%)
   MoE AVX2 Q8 Expert Compute   :    205.30 ms (   98.7 us/tok | 24.36%)
   Router + Lookahead Dispatch  :     46.42 ms (   22.3 us/tok |  5.51%)
   LM Head Output Projection    :      3.41 ms (    1.6 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :      4.06 ms (    2.0 us/tok |  0.48%)
   Unaccounted / OMP & Sampling :     61.88 ms (   29.8 us/tok |  7.34%) | Total Wall=842.74 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    19.27%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.80%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.04%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    65.36%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     7.53%  |
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
    "ttft_ms": 135.17,
    "avg_tps": 1213.28,
    "min_tps": 988.75,
    "max_tps": 1386.07
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 252.53,
    "min_tps": 241.77,
    "max_tps": 265.31,
    "p50_ms": 3.95,
    "p90_ms": 4.09,
    "p99_ms": 4.14,
    "mean_ms": 3.96,
    "jitter_ms": 0.09
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
    "avg_mbs": 3022.79,
    "peak_mbs": 7241.92,
    "sync_wait_ms": 1.09,
    "async_overlap_ms": 1.9
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
    "dense_attention": 217.24,
    "moe_compute": 59.68,
    "router_lookahead": 4.11,
    "lm_head": 5.0,
    "unaccounted": 2.48
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.69,
    "ram_bandwidth_pinning": 3.19,
    "expert_cache_lrfu": 11.02,
    "lookahead_parallel_overlap": 1.98,
    "ssd_nvme_throughput": 1.12,
    "total": 100.0
  }
}

=== [TEST] OpenAI-Compatible API Server on port 18082 (tests/synth_qwen38_ud_iq2_xs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63qtok_194qtok_49"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 21, "completion_tokens": 8, "total_tokens": 29}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"qtok_159qtok_194qtok_49qtok_254qtok_49qtok_254"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"text": "qtok_159qtok_112qtok_193qtok_128qtok_49qtok_254", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_68qtok_179qtok_49qtok_49qtok_17qtok_63", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 19, "completion_tokens": 6, "total_tokens": 25}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "qwen-3.8-flash-next-ud-iq2_xs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
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
    "ttft_ms": 191.11,
    "avg_tps": 858.14,
    "min_tps": 572.87,
    "max_tps": 1094.34
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 219.77,
    "min_tps": 187.91,
    "max_tps": 232.32,
    "p50_ms": 4.51,
    "p90_ms": 4.78,
    "p99_ms": 5.32,
    "mean_ms": 4.55,
    "jitter_ms": 0.11
  },
  "cache": {
    "raw_hit_rate_pct": 85.62,
    "effective_hit_rate_pct": 94.92,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 37982304,
    "prefill_bytes": 20297216,
    "warmup_bytes": 0,
    "decode_bytes": 12128256,
    "bytes_per_token": 187104.95,
    "avg_mbs": 4341.95,
    "peak_mbs": 13043.24,
    "sync_wait_ms": 2.79,
    "async_overlap_ms": 7.53
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
    "dense_attention": 203.85,
    "moe_compute": 125.72,
    "router_lookahead": 5.19,
    "lm_head": 5.09,
    "unaccounted": 25.93
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 81.03,
    "ram_bandwidth_pinning": 3.55,
    "expert_cache_lrfu": 8.41,
    "lookahead_parallel_overlap": 4.32,
    "ssd_nvme_throughput": 2.69,
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
```

### 📄 `03_host_hardware_benchmark.log`
```text
Host CPU: AMD EPYC 9V45 96-Core Processor | Cores=2 Threads=4 | RAM=15.99 GB

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V45 96-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.51 GB Available
   Active Drive Space : 219.98 GB Total / 219.81 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    551.55 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2124.00 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9760.04 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  12335.68 MB/s
   RND4K Q32T16 Read                  :   1128.02 MB/s (  288772 IOPS)
   RND4K Q1T1  Read                   :   1141.68 MB/s (Latency: 3.42 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     96.53 GB/s
   AVX2 256-bit Sequential Write BW   :     95.44 GB/s
   STREAM Triad (A = B + s*C) BW      :     55.77 GB/s
   Random Pointer-Chase Latency       :     35.48 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     71.65 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    277.21 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     39.81 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 28.12 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 137.89 MB/s (7.43s)
   Window #01 (112.0 MB in 0.51s):   221.31 MB/s (Uncached Direct Read)
   Window #02 (120.0 MB in 0.51s):   237.49 MB/s (Uncached Direct Read)
   Window #03 (116.0 MB in 0.52s):   224.98 MB/s (Uncached Direct Read)
   Window #04 (120.0 MB in 0.51s):   233.68 MB/s (Uncached Direct Read)
   Window #05 (120.0 MB in 0.51s):   237.56 MB/s (Uncached Direct Read)
   Window #06 (112.0 MB in 0.51s):   218.19 MB/s (Uncached Direct Read)
   Window #07 (116.0 MB in 0.51s):   226.75 MB/s (Uncached Direct Read)
   Window #08 (120.0 MB in 0.51s):   234.35 MB/s (Uncached Direct Read)
   Window #09 ( 88.0 MB in 0.41s):   215.25 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   227.99 MB/s (Min=215.25 | Max=237.56 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 219.81 GB / 219.98 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 271.93 MB/s (3.77s)
   Window #01 (272.0 MB in 0.50s):   542.43 MB/s (Uncached Direct Read)
   Window #02 (272.0 MB in 0.50s):   542.43 MB/s (Uncached Direct Read)
   Window #03 (272.0 MB in 0.50s):   542.70 MB/s (Uncached Direct Read)
   Window #04 (208.0 MB in 0.38s):   545.66 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   543.14 MB/s (Min=542.43 | Max=545.66 MB/s)
================================================================================
```

### 📄 `04_qwen38_stage1_parity.log`
```text
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (4) : [198, 198, 198, 198] -> "



"
[Apex-Parity] Batched Tokens (4) : [198, 198, 198, 198] -> "



"
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 4 / 4 (100.00% Parity)
```

### 📄 `05_qwen38_stage1_prompt_response.log`
```text
================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V45 96-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.37 GB Available
   Active Drive Space : 219.98 GB Total / 149.17 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    511.54 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2121.62 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8201.19 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10845.85 MB/s
   RND4K Q32T16 Read                  :    761.75 MB/s (  195009 IOPS)
   RND4K Q1T1  Read                   :    893.93 MB/s (Latency: 4.37 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     72.60 GB/s
   AVX2 256-bit Sequential Write BW   :     74.74 GB/s
   STREAM Triad (A = B + s*C) BW      :     46.12 GB/s
   Random Pointer-Chase Latency       :    125.00 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     67.16 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    257.70 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     35.79 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=3.22 tps | Avg=3.22 tps | Hit=90.0% | NVMe=563.6 MB/s (11789.75 MB, QD=64) | RSS=13442.5 MB

 >>> [Apex-Model-Response] b
!
!n!
!u!
!
!
!
!
!
!
!a!2!1!1!1!1!n!
!1! !
!
!
!
!8! ! ! !
! 
================================================================================

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7539.18 MB (3633/25088 exp = 14.48% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=13416.85 MB | Peak=13905.10 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "b
!
!n!
!u!
!
!
!
!
!
!
!a!2!1!1!1!1!n!
!1! !
!
!
!
!8! ! ! !
! !"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=56.3% | AvgMargin=0.623 | MinMargin=0.019
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      65 | b              |    9.34 |   1.9% |      79 |    9.00 | 28252.51 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |    9.49 |   3.9% |      17 |    8.24 |  334.39 |446 | 30 |  4 | 109471.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  334.39 |  0 |  0 |  0 | 109471.5 |
   |    4 |     198 | \n             |   10.43 |   8.6% |      82 |    9.45 |  300.86 |458 | 22 |  0 | 102369.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  300.86 |  0 |  0 |  0 | 102369.5 |
   |    6 |      77 | n              |    8.42 |   1.7% |      76 |    8.40 |  289.89 |451 | 29 |  0 | 107294.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  289.89 |  0 |  0 |  0 | 107294.5 |
   |    8 |     198 | \n             |    7.79 |   0.8% |     286 |    7.34 |  260.68 |468 | 12 |  0 | 93469.5 |
   |   26 |      64 | a              |   10.03 |   5.8% |      82 |    8.92 |  286.99 |449 | 28 |  3 | 130707.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  286.99 |  0 |  0 |  0 | 130707.0 |
   |   30 |      16 | 1              |    9.21 |   1.7% |      17 |    9.03 |  282.50 |461 | 17 |  2 | 108732.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  282.50 |  0 |  0 |  0 | 108732.0 |
   |   62 |     198 | \n             |    9.87 |   8.6% |      22 |    9.28 |  201.80 |478 |  2 |  0 | 82082.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  201.80 |  0 |  0 |  0 | 82082.0 |
   |   64 |     220 |                |    9.81 |   9.4% |     264 |    8.94 |  212.60 |480 |  0 |  0 | 80894.5 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  212.60 |  0 |  0 |  0 | 80894.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 28.253s, TTFT=28252.51ms): Avg=3.22 | Min=3.22 | Max=3.22 tps
   Prefill Chunks (1): C1:91t/3.2tps/90%
   Decode  (64 tok, 16.101s): Avg=3.97 | Min=2.99 | Max=4.96 tps
   Latency (ms) : Min=201.80 | P10=206.30 | P25=226.70 | P50=257.12 | P75=268.48 | P90=286.99 | P95=300.86 | P99=334.39 | Max=334.39
   Mean/SD/Jitt : Mean=251.58ms | StdDev=30.69ms | Jitter=10.09ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (59040): RawRAM=54308 (91.99%) | Lookahead=351 (+0.59%) | ColdMiss=4381 (7.42%) | EFF HIT=92.58%
   Lookahead    : 2846 prefetched -> 671 consumed (23.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.8% | @64= 92.6% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1230 |  952 |  13 | 265 | 78.5%| 468.31 | | L24 | 1230 | 1172 |   2 |  56 | 95.4%| 157.91 |
   | L01 | 1230 | 1112 |   6 | 112 | 90.9%| 466.92 | | L25 | 1230 | 1161 |   3 |  66 | 94.6%| 135.35 |
   | L02 | 1230 | 1096 |   1 | 133 | 89.2%| 523.90 | | L26 | 1230 | 1131 |   6 |  93 | 92.4%| 244.38 |
   | L03 | 1230 | 1166 |   0 |  64 | 94.8%| 530.13 | | L27 | 1230 | 1154 |   1 |  75 | 93.9%| 174.83 |
   | L04 | 1230 | 1157 |   0 |  73 | 94.1%| 508.42 | | L28 | 1230 | 1103 |  11 | 116 | 90.6%| 295.14 |
   | L05 | 1230 | 1144 |   1 |  85 | 93.1%| 310.18 | | L29 | 1230 | 1132 |   7 |  91 | 92.6%| 185.82 |
   | L06 | 1230 | 1140 |   1 |  89 | 92.8%| 319.58 | | L30 | 1230 | 1100 |  10 | 120 | 90.2%| 234.79 |
   | L07 | 1230 | 1143 |   1 |  86 | 93.0%| 146.56 | | L31 | 1230 | 1100 |  16 | 114 | 90.7%| 250.63 |
   | L08 | 1230 | 1176 |   1 |  53 | 95.7%|  68.48 | | L32 | 1230 | 1128 |  11 |  91 | 92.6%| 306.42 |
   | L09 | 1230 | 1170 |   0 |  60 | 95.1%|  75.95 | | L33 | 1230 | 1131 |   5 |  94 | 92.4%| 151.25 |
   | L10 | 1230 | 1151 |   1 |  78 | 93.7%| 143.19 | | L34 | 1230 | 1110 |  23 |  97 | 92.1%| 218.95 |
   | L11 | 1230 | 1167 |   0 |  63 | 94.9%|  85.91 | | L35 | 1230 | 1150 |   6 |  74 | 94.0%| 121.00 |
   | L12 | 1230 | 1144 |   0 |  86 | 93.0%| 167.31 | | L36 | 1230 | 1118 |  10 | 102 | 91.7%| 207.42 |
   | L13 | 1230 | 1140 |   1 |  89 | 92.8%| 129.64 | | L37 | 1230 | 1144 |   5 |  81 | 93.4%| 178.59 |
   | L14 | 1230 | 1132 |   3 |  95 | 92.3%| 250.63 | | L38 | 1230 | 1153 |   3 |  74 | 94.0%| 218.07 |
   | L15 | 1230 | 1127 |   6 |  97 | 92.1%| 300.78 | | L39 | 1230 | 1133 |   7 |  90 | 92.7%| 265.06 |
   | L16 | 1230 | 1128 |   9 |  93 | 92.4%| 221.83 | | L40 | 1230 | 1104 |  22 | 104 | 91.5%| 359.06 |
   | L17 | 1230 | 1131 |   6 |  93 | 92.4%| 206.79 | | L41 | 1230 | 1122 |  13 |  95 | 92.3%| 181.49 |
   | L18 | 1230 | 1130 |  11 |  89 | 92.8%| 189.87 | | L42 | 1230 | 1104 |  23 | 103 | 91.6%| 234.79 |
   | L19 | 1230 | 1152 |   6 |  72 | 94.1%| 119.56 | | L43 | 1230 | 1142 |  12 |  76 | 93.8%| 201.66 |
   | L20 | 1230 | 1109 |  17 | 104 | 91.5%| 227.59 | | L44 | 1230 | 1126 |  16 |  88 | 92.8%| 194.46 |
   | L21 | 1230 | 1130 |   4 |  96 | 92.2%| 251.90 | | L45 | 1230 | 1119 |  20 |  91 | 92.6%| 216.06 |
   | L22 | 1230 | 1157 |   3 |  70 | 94.3%| 165.43 | | L46 | 1230 | 1159 |   4 |  67 | 94.6%| 253.52 |
   | L23 | 1230 | 1118 |  18 |  94 | 92.4%| 247.75 | | L47 | 1230 | 1140 |   6 |  84 | 93.2%| 251.90 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 17581.42 MB (Load=4614.69 | Prefill=7175.05 | Warmup=0.00 | Decode=5791.68 MB)
   SSD Data/Token (Decode)      : Avg=90.495 MB/tok (Min=76.557 | P50=86.579 | P95=106.906 | Max=127.644 MB) | Prefill=78.847 MB/tok
   NVMe Batches / Requests      : 1241 Batches | 24757 Raw -> 23768 Merged (989 LBA Merges, Avg 757.5 KB/io)
   SSD I/O Size Histogram       : <64K=2178 | 64K-512K=5500 | 512K-2M=15647 | >2M=443
   SSD Read Bandwidth (Active)  : Min=5.52 | Avg=649.17 | Peak=10622.52 MB/s | WallAmort=396.39 MB/s (100.0% of 511.5 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=18579.01 MB | Write=128.00 MB | Syscalls=40820
   Sync Stall vs Async DMA      : SyncStall=12701.86 ms | AsyncOverlapped=18862.29 ms (59.8% Overlapped)
   RAM Traffic & Active BW      : 622.87 GB moved | Active=23.92 GB/s (51.9% STREAM) | WallAmort=14.04 GB/s (Max=46.12 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=28.25s (63.7%, 7175.05 MB SSD) | Decode=16.10s (36.3%, 5791.68 MB SSD)
   CPU Time & Utilization       : User=84.359s + Sys=6.125s (Wall=56.473s) | SysUtil=40.1% | ThrUtil=40.1% | 103.23 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  12611.21 ms (81362.7 us/tok | 28.43%)
   MoE AVX2 Q8 Expert Compute   :  11951.27 ms (77105.0 us/tok | 26.95%)
   Router + Lookahead Dispatch  :    703.44 ms ( 4538.3 us/tok |  1.59%)
   LM Head Output Projection    :   1475.03 ms ( 9516.3 us/tok |  3.33%)
   Foreground NVMe Sync Stall   :  12701.86 ms (81947.5 us/tok | 28.64%)
   Unaccounted / OMP & Sampling :   4911.09 ms (31684.5 us/tok | 11.07%) | Total Wall=44353.91 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    80.66%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.98%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     7.71%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.04%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.61%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_qwen38_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6574.22 MB (3168 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=2.97 tps | Avg=2.97 tps | Hit=88.1% | NVMe=562.7 MB/s (10578.12 MB, QD=64) | RSS=12464.2 MB
[LIVE-DECODE] 8/32 tok | Avg=2.95 tps | Hit=88.8% (LA:+0.3%) | NVMe=569.0 MB/s (11489.99 MB) | RSS=12467.0 MB
[LIVE-DECODE] 16/32 tok | Avg=3.25 tps | Hit=89.4% (LA:+0.4%) | NVMe=580.3 MB/s (12233.70 MB) | RSS=12467.0 MB
[LIVE-DECODE] 24/32 tok | Avg=3.37 tps | Hit=90.0% (LA:+0.5%) | NVMe=590.7 MB/s (13039.39 MB) | RSS=12467.0 MB
[LIVE-DECODE] 32/32 tok | Avg=3.42 tps | Hit=90.4% (LA:+0.7%) | NVMe=602.5 MB/s (13928.73 MB) | RSS=12467.0 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 6574.22 MB (3168/25088 exp = 12.63% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=12467.04 MB | Peak=12927.72 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " a2!ar!
!
!
!
!2!
!
!
!
!
!2!
!2!
!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=57.2% | AvgMargin=0.832 | MinMargin=0.117
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.79 |  18.1% |     303 |   13.43 | 21557.47 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    9.06 |   2.0% |      11 |    8.95 |  381.22 |447 | 27 |  6 | 116482.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  381.22 |  0 |  0 |  0 | 116482.0 |
   |    4 |     277 | ar             |    8.82 |   2.2% |     198 |    8.49 |  364.39 |440 | 38 |  2 | 122709.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  364.39 |  0 |  0 |  0 | 122709.0 |
   |    6 |     198 | \n             |   10.74 |  15.3% |      11 |    9.20 |  323.77 |456 | 22 |  2 | 117169.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  323.77 |  0 |  0 |  0 | 117169.5 |
   |    8 |     198 | \n             |   11.64 |  35.2% |  248046 |    8.76 |  284.75 |463 | 17 |  0 | 110519.5 |
   |   16 |     198 | \n             |   10.43 |  10.7% |  248046 |    8.48 |  297.40 |474 |  6 |  0 | 87607.0 |
   |   17 |       0 | !              |     nan | 100.0% |       1 |     nan |  297.40 |  0 |  0 |  0 | 87607.0 |
   |   26 |      17 | 2              |    8.79 |   2.0% |      22 |    8.51 |  296.62 |435 | 41 |  4 | 150244.5 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  296.62 |  0 |  0 |  0 | 150244.5 |
   |   30 |      17 | 2              |   11.26 |  12.2% |     198 |   10.72 |  269.36 |463 | 17 |  0 | 103582.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  269.36 |  0 |  0 |  0 | 103582.0 |
   |   32 |     198 | \n             |   10.87 |  17.5% |      11 |    9.14 |  269.58 |470 | 10 |  0 | 87057.0 |
   |   33 |       0 | !              |     nan | 100.0% |       1 |     nan |  269.58 |  0 |  0 |  0 | 87057.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 21.557s, TTFT=21557.47ms): Avg=2.97 | Min=2.97 | Max=2.97 tps
   Prefill Chunks (1): C1:64t/3.0tps/88%
   Decode  (32 tok, 9.345s): Avg=3.42 | Min=2.62 | Max=3.85 tps
   Latency (ms) : Min=259.80 | P10=266.68 | P25=269.58 | P50=280.51 | P75=297.40 | P90=364.39 | P95=381.22 | P99=381.22 | Max=381.22
   Mean/SD/Jitt : Mean=292.03ms | StdDev=34.16ms | Jitter=9.74ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (38400): RawRAM=34452 (89.72%) | Lookahead=280 (+0.73%) | ColdMiss=3668 (9.55%) | EFF HIT=90.45%
   Lookahead    : 1706 prefetched -> 440 consumed (25.8% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 89.4% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  800 |  569 |  17 | 214 | 73.2%| 389.14 | | L24 |  800 |  749 |   4 |  47 | 94.1%| 127.83 |
   | L01 |  800 |  696 |  10 |  94 | 88.2%| 295.09 | | L25 |  800 |  748 |   0 |  52 | 93.5%| 107.15 |
   | L02 |  800 |  695 |   3 | 102 | 87.2%| 348.71 | | L26 |  800 |  728 |   5 |  67 | 91.6%| 156.03 |
   | L03 |  800 |  745 |   0 |  55 | 93.1%| 310.18 | | L27 |  800 |  736 |   0 |  64 | 92.0%| 137.23 |
   | L04 |  800 |  741 |   0 |  59 | 92.6%| 184.69 | | L28 |  800 |  716 |   6 |  78 | 90.2%| 257.54 |
   | L05 |  800 |  728 |   1 |  71 | 91.1%| 244.38 | | L29 |  800 |  715 |   7 |  78 | 90.2%| 168.53 |
   | L06 |  800 |  739 |   0 |  61 | 92.4%| 171.07 | | L30 |  800 |  686 |  15 |  99 | 87.6%| 191.58 |
   | L07 |  800 |  738 |   2 |  60 | 92.5%| 106.13 | | L31 |  800 |  688 |  16 |  96 | 88.0%| 201.66 |
   | L08 |  800 |  759 |   1 |  40 | 95.0%|  73.46 | | L32 |  800 |  716 |   4 |  80 | 90.0%| 195.51 |
   | L09 |  800 |  747 |   0 |  53 | 93.4%|  74.71 | | L33 |  800 |  701 |  12 |  87 | 89.1%| 157.01 |
   | L10 |  800 |  743 |   1 |  56 | 93.0%|  85.91 | | L34 |  800 |  708 |  10 |  82 | 89.8%| 162.77 |
   | L11 |  800 |  749 |   1 |  50 | 93.8%|  63.50 | | L35 |  800 |  730 |   2 |  68 | 91.5%| 110.91 |
   | L12 |  800 |  736 |   0 |  64 | 92.0%| 122.19 | | L36 |  800 |  709 |  11 |  80 | 90.0%| 195.90 |
   | L13 |  800 |  728 |   0 |  72 | 91.0%| 108.03 | | L37 |  800 |  731 |   4 |  65 | 91.9%| 135.35 |
   | L14 |  800 |  710 |  11 |  79 | 90.1%| 181.49 | | L38 |  800 |  733 |   2 |  65 | 91.9%| 174.83 |
   | L15 |  800 |  709 |   9 |  82 | 89.8%| 203.03 | | L39 |  800 |  717 |   6 |  77 | 90.4%| 223.71 |
   | L16 |  800 |  722 |   5 |  73 | 90.9%| 165.43 | | L40 |  800 |  702 |  11 |  87 | 89.1%| 265.06 |
   | L17 |  800 |  727 |   3 |  70 | 91.2%| 167.31 | | L41 |  800 |  704 |   7 |  89 | 88.9%| 157.01 |
   | L18 |  800 |  721 |   9 |  70 | 91.2%| 156.03 | | L42 |  800 |  677 |  14 | 109 | 86.4%| 218.95 |
   | L19 |  800 |  723 |   9 |  68 | 91.5%| 122.44 | | L43 |  800 |  716 |   6 |  78 | 90.2%| 159.89 |
   | L20 |  800 |  698 |  12 |  90 | 88.8%| 178.61 | | L44 |  800 |  707 |   5 |  88 | 89.0%| 152.69 |
   | L21 |  800 |  703 |   9 |  88 | 89.0%| 253.78 | | L45 |  800 |  691 |  13 |  96 | 88.0%| 203.10 |
   | L22 |  800 |  748 |   0 |  52 | 93.5%| 101.51 | | L46 |  800 |  735 |   1 |  64 | 92.0%| 171.41 |
   | L23 |  800 |  728 |   8 |  64 | 92.0%| 131.08 | | L47 |  800 |  707 |   8 |  85 | 89.4%| 242.50 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 13928.73 MB (Load=4614.69 | Prefill=5963.42 | Warmup=0.00 | Decode=3350.61 MB)
   SSD Data/Token (Decode)      : Avg=104.707 MB/tok (Min=85.017 | P50=101.154 | P95=146.723 | Max=146.723 MB) | Prefill=93.178 MB/tok
   NVMe Batches / Requests      : 788 Batches | 18510 Raw -> 17726 Merged (784 LBA Merges, Avg 804.6 KB/io)
   SSD I/O Size Histogram       : <64K=1595 | 64K-512K=4168 | 512K-2M=11523 | >2M=440
   SSD Read Bandwidth (Active)  : Min=7.23 | Avg=602.48 | Peak=10215.71 MB/s | WallAmort=450.73 MB/s
   OS Kernel I/O Verification   : Read=13948.70 MB | Write=0.00 MB | Syscalls=27228
   Sync Stall vs Async DMA      : SyncStall=10578.56 ms | AsyncOverlapped=14876.60 ms (58.4% Overlapped)
   RAM Traffic & Active BW      : 360.23 GB moved | Active=21.73 GB/s | WallAmort=11.66 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=21.56s (69.8%, 5963.42 MB SSD) | Decode=9.34s (30.2%, 3350.61 MB SSD)
   CPU Time & Utilization       : User=52.344s + Sys=4.656s (Wall=43.117s) | SysUtil=33.0% | ThrUtil=33.0% | 30.57 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   7812.35 ms (81378.7 us/tok | 25.28%)
   MoE AVX2 Q8 Expert Compute   :   7968.16 ms (83001.6 us/tok | 25.78%)
   Router + Lookahead Dispatch  :    449.21 ms ( 4679.3 us/tok |  1.45%)
   LM Head Output Projection    :    796.81 ms ( 8300.1 us/tok |  2.58%)
   Foreground NVMe Sync Stall   :  10578.56 ms (110193.3 us/tok | 34.23%)
   Unaccounted / OMP & Sampling :   3297.29 ms (34346.8 us/tok | 10.67%) | Total Wall=30902.38 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    77.90%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.41%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     9.22%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.53%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.94%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_qwen38_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7725.95 MB (3723 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=4.52 tps | Avg=4.52 tps | Hit=95.4% | NVMe=562.9 MB/s (13785.34 MB, QD=64) | RSS=13666.7 MB
[LIVE-PREFILL] 512/512 tok | Chunk=5.31 tps | Avg=4.88 tps | Hit=96.7% | NVMe=560.8 MB/s (18015.74 MB, QD=64) | RSS=13668.9 MB
[LIVE-DECODE] 8/128 tok | Avg=3.47 tps | Hit=96.7% (LA:+0.0%) | NVMe=567.4 MB/s (18877.69 MB) | RSS=13668.9 MB
[LIVE-DECODE] 16/128 tok | Avg=3.80 tps | Hit=96.7% (LA:+0.1%) | NVMe=579.5 MB/s (19667.58 MB) | RSS=13637.2 MB
[LIVE-DECODE] 24/128 tok | Avg=4.06 tps | Hit=96.7% (LA:+0.1%) | NVMe=594.1 MB/s (20437.73 MB) | RSS=13627.1 MB
[LIVE-DECODE] 32/128 tok | Avg=4.31 tps | Hit=96.8% (LA:+0.1%) | NVMe=611.2 MB/s (21233.07 MB) | RSS=13618.5 MB
[LIVE-DECODE] 40/128 tok | Avg=4.46 tps | Hit=96.8% (LA:+0.1%) | NVMe=625.8 MB/s (21968.63 MB) | RSS=13604.7 MB
[LIVE-DECODE] 48/128 tok | Avg=4.59 tps | Hit=96.8% (LA:+0.1%) | NVMe=641.6 MB/s (22669.22 MB) | RSS=13598.5 MB
[LIVE-DECODE] 56/128 tok | Avg=4.71 tps | Hit=96.8% (LA:+0.1%) | NVMe=655.8 MB/s (23301.11 MB) | RSS=13596.3 MB
[LIVE-DECODE] 64/128 tok | Avg=4.78 tps | Hit=96.9% (LA:+0.1%) | NVMe=669.9 MB/s (24010.05 MB) | RSS=13596.3 MB
[LIVE-DECODE] 72/128 tok | Avg=4.81 tps | Hit=96.9% (LA:+0.1%) | NVMe=683.7 MB/s (24748.51 MB) | RSS=13595.9 MB
[LIVE-DECODE] 80/128 tok | Avg=4.87 tps | Hit=96.9% (LA:+0.1%) | NVMe=699.3 MB/s (25477.30 MB) | RSS=13593.6 MB
[LIVE-DECODE] 88/128 tok | Avg=4.88 tps | Hit=96.9% (LA:+0.2%) | NVMe=713.0 MB/s (26208.04 MB) | RSS=13587.5 MB
[LIVE-DECODE] 96/128 tok | Avg=4.94 tps | Hit=97.0% (LA:+0.2%) | NVMe=729.3 MB/s (26951.63 MB) | RSS=13585.0 MB
[LIVE-DECODE] 104/128 tok | Avg=4.98 tps | Hit=97.0% (LA:+0.2%) | NVMe=743.0 MB/s (27638.40 MB) | RSS=13583.4 MB
[LIVE-DECODE] 112/128 tok | Avg=5.02 tps | Hit=97.0% (LA:+0.2%) | NVMe=758.1 MB/s (28321.41 MB) | RSS=13580.0 MB
[LIVE-DECODE] 120/128 tok | Avg=5.07 tps | Hit=97.0% (LA:+0.2%) | NVMe=773.1 MB/s (28989.83 MB) | RSS=13576.6 MB
[LIVE-DECODE] 128/128 tok | Avg=5.03 tps | Hit=97.0% (LA:+0.2%) | NVMe=785.9 MB/s (29661.71 MB) | RSS=13560.1 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7725.95 MB (3723/25088 exp = 14.84% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13560.08 MB | Peak=14118.84 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : "22!7!5!m!m!2!m!2!9!3!2!2!7!2!5!7!ar!
!9!3!2!a!2!
!a!2!a!a!2!
!
!7!p!3!2!m!7!7!2!7!7!ing!2!n!2!2!2!7!2!u!2!7!7!7!2!7!2!2!7!7!7!7!3!1!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=54.1% | AvgMargin=0.204 | MinMargin=0.004
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      17 | 2              |   11.64 |   9.2% |      18 |   11.26 | 104920.17 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    8.98 |   1.0% |     277 |    8.80 |  364.10 |439 | 39 |  2 | 121457.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  364.10 |  0 |  0 |  0 | 121457.0 |
   |    4 |      22 | 7              |   10.62 |   6.7% |      17 |   10.52 |  283.88 |455 | 25 |  0 | 104769.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  283.88 |  0 |  0 |  0 | 104769.5 |
   |    6 |      20 | 5              |   11.59 |   6.9% |      22 |   11.52 |  239.42 |453 | 27 |  0 | 106271.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.42 |  0 |  0 |  0 | 106271.5 |
   |    8 |      76 | m              |   12.53 |   7.3% |      17 |   12.18 |  266.22 |455 | 25 |  0 | 108819.5 |
   |   14 |      76 | m              |   10.95 |   5.1% |      17 |   10.60 |  277.85 |464 | 16 |  0 | 106057.0 |
   |   15 |       0 | !              |     nan | 100.0% |       1 |     nan |  277.85 |  0 |  0 |  0 | 106057.0 |
   |    9 |       0 | !              |     nan | 100.0% |       1 |     nan |  266.22 |  0 |  0 |  0 | 108819.5 |
   |   20 |      18 | 3              |   12.24 |   5.2% |      24 |   12.00 |  251.32 |469 | 11 |  0 | 101507.0 |
   |  126 |      18 | 3              |   10.39 |   6.0% |      22 |    9.95 |  287.91 |478 |  2 |  0 | 86244.5 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  287.91 |  0 |  0 |  0 | 86244.5 |
   |  128 |      16 | 1              |   12.00 |  17.3% |      17 |   11.87 |  217.31 |477 |  3 |  0 | 86757.0 |
   |  129 |       0 | !              |     nan | 100.0% |       1 |     nan |  217.31 |  0 |  0 |  0 | 86757.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 104.920s, TTFT=104920.17ms): Avg=4.88 | Min=4.52 | Max=5.31 tps
   Prefill Chunks (2): C1:256t/4.5tps/95% | C2:256t/5.3tps/97%
   Decode  (128 tok, 25.467s): Avg=5.03 | Min=2.75 | Max=6.09 tps
   Latency (ms) : Min=164.33 | P10=170.94 | P25=174.47 | P50=189.74 | P75=207.53 | P90=243.98 | P95=277.85 | P99=364.10 | Max=364.10
   Mean/SD/Jitt : Mean=198.96ms | StdDev=35.48ms | Jitter=10.28ms | Hist(<25/50/100/200/>200ms): 0/0/0/86/42
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (276480): RawRAM=267819 (96.87%) | Lookahead=478 (+0.17%) | ColdMiss=8183 (2.96%) | EFF HIT=97.04%
   Lookahead    : 5804 prefetched -> 1118 consumed (19.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.7% | @64= 96.9% | @128= 97.0% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 5760 | 5195 |  22 | 543 | 90.6%| 951.78 | | L24 | 5760 | 5658 |   5 |  97 | 98.3%| 300.78 |
   | L01 | 5760 | 5562 |   7 | 191 | 96.7%| 962.48 | | L25 | 5760 | 5668 |   2 |  90 | 98.4%| 195.51 |
   | L02 | 5760 | 5526 |   5 | 229 | 96.0%|1056.23 | | L26 | 5760 | 5575 |   5 | 180 | 96.9%| 362.82 |
   | L03 | 5760 | 5686 |   1 |  73 | 98.7%| 902.34 | | L27 | 5760 | 5642 |   2 | 116 | 98.0%| 327.10 |
   | L04 | 5760 | 5648 |   1 | 111 | 98.1%| 776.12 | | L28 | 5760 | 5548 |   8 | 204 | 96.5%| 554.57 |
   | L05 | 5760 | 5621 |   0 | 139 | 97.6%| 727.51 | | L29 | 5760 | 5582 |  13 | 165 | 97.1%| 574.73 |
   | L06 | 5760 | 5638 |   1 | 121 | 97.9%| 456.81 | | L30 | 5760 | 5501 |  23 | 236 | 95.9%| 424.93 |
   | L07 | 5760 | 5626 |   0 | 134 | 97.7%| 229.10 | | L31 | 5760 | 5538 |   7 | 215 | 96.3%| 380.27 |
   | L08 | 5760 | 5692 |   0 |  68 | 98.8%|  88.40 | | L32 | 5760 | 5587 |   4 | 169 | 97.1%| 503.81 |
   | L09 | 5760 | 5692 |   0 |  68 | 98.8%|  87.16 | | L33 | 5760 | 5547 |  12 | 201 | 96.5%| 324.10 |
   | L10 | 5760 | 5657 |   1 | 102 | 98.2%| 209.18 | | L34 | 5760 | 5469 |  32 | 259 | 95.5%| 494.07 |
   | L11 | 5760 | 5692 |   1 |  67 | 98.8%|  85.91 | | L35 | 5760 | 5589 |  11 | 160 | 97.2%| 292.41 |
   | L12 | 5760 | 5652 |   1 | 107 | 98.1%| 206.79 | | L36 | 5760 | 5587 |   9 | 164 | 97.2%| 328.42 |
   | L13 | 5760 | 5630 |   1 | 129 | 97.8%| 187.26 | | L37 | 5760 | 5565 |   4 | 191 | 96.7%| 394.78 |
   | L14 | 5760 | 5623 |   8 | 129 | 97.8%| 378.83 | | L38 | 5760 | 5622 |   2 | 136 | 97.6%| 443.65 |
   | L15 | 5760 | 5578 |  13 | 169 | 97.1%| 466.21 | | L39 | 5760 | 5577 |  15 | 168 | 97.1%| 498.17 |
   | L16 | 5760 | 5573 |   4 | 183 | 96.8%| 438.01 | | L40 | 5760 | 5572 |  18 | 170 | 97.0%| 594.04 |
   | L17 | 5760 | 5549 |  13 | 198 | 96.6%| 469.97 | | L41 | 5760 | 5577 |  13 | 170 | 97.0%| 352.91 |
   | L18 | 5760 | 5555 |  19 | 186 | 96.8%| 407.93 | | L42 | 5760 | 5486 |  24 | 250 | 95.7%| 561.77 |
   | L19 | 5760 | 5589 |  15 | 156 | 97.3%| 303.93 | | L43 | 5760 | 5496 |  24 | 240 | 95.8%| 547.36 |
   | L20 | 5760 | 5498 |  25 | 237 | 95.9%| 491.19 | | L44 | 5760 | 5477 |  20 | 263 | 95.4%| 573.29 |
   | L21 | 5760 | 5534 |  18 | 208 | 96.4%| 748.19 | | L45 | 5760 | 5475 |  34 | 251 | 95.6%| 643.87 |
   | L22 | 5760 | 5656 |   2 | 102 | 98.2%| 251.90 | | L46 | 5760 | 5647 |   3 | 110 | 98.1%| 427.81 |
   | L23 | 5760 | 5576 |  23 | 161 | 97.2%| 419.17 | | L47 | 5760 | 5586 |   7 | 167 | 97.1%| 419.21 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 29661.71 MB (Load=4614.69 | Prefill=13401.04 | Warmup=0.00 | Decode=11645.97 MB)
   SSD Data/Token (Decode)      : Avg=90.984 MB/tok (Min=74.946 | P50=90.546 | P95=103.781 | Max=118.610 MB) | Prefill=26.174 MB/tok
   NVMe Batches / Requests      : 2554 Batches | 52285 Raw -> 50480 Merged (1805 LBA Merges, Avg 601.7 KB/io)
   SSD I/O Size Histogram       : <64K=9473 | 64K-512K=10597 | 512K-2M=29910 | >2M=500
   SSD Read Bandwidth (Active)  : Min=7.43 | Avg=785.90 | Peak=10897.87 MB/s | WallAmort=227.49 MB/s
   OS Kernel I/O Verification   : Read=29681.84 MB | Write=0.00 MB | Syscalls=59995
   Sync Stall vs Async DMA      : SyncStall=23070.96 ms | AsyncOverlapped=29502.85 ms (56.1% Overlapped)
   RAM Traffic & Active BW      : 2072.99 GB moved | Active=20.87 GB/s | WallAmort=15.90 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=104.92s (80.5%, 13401.04 MB SSD) | Decode=25.47s (19.5%, 11645.97 MB SSD)
   CPU Time & Utilization       : User=349.766s + Sys=13.484s (Wall=141.807s) | SysUtil=64.0% | ThrUtil=64.0% | 59.24 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  46887.24 ms (73261.3 us/tok | 35.96%)
   MoE AVX2 Q8 Expert Compute   :  49828.18 ms (77856.5 us/tok | 38.22%)
   Router + Lookahead Dispatch  :   2787.93 ms ( 4356.1 us/tok |  2.14%)
   LM Head Output Projection    :   2634.78 ms ( 4116.9 us/tok |  2.02%)
   Foreground NVMe Sync Stall   :  23070.96 ms (36048.4 us/tok | 17.69%)
   Unaccounted / OMP & Sampling :   5178.47 ms ( 8091.4 us/tok |  3.97%) | Total Wall=130387.57 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    85.98%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.70%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.09%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.03%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.20%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_qwen38_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 15134.2ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\n\n\n\n\n\nu\nW\n\n\n\n0\n0'
[Stage 3] /v1/chat/completions (stream=true SSE) 3481.2ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_qwen38_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7672.00 MB (3697 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=4.54 tps | Avg=4.54 tps | Hit=95.4% | NVMe=565.4 MB/s (13785.34 MB, QD=64) | RSS=13614.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=5.44 tps | Avg=4.95 tps | Hit=96.7% | NVMe=561.5 MB/s (18015.74 MB, QD=64) | RSS=13613.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=5.69 tps | Avg=5.17 tps | Hit=97.1% | NVMe=560.4 MB/s (21879.79 MB, QD=64) | RSS=13614.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=5.74 tps | Avg=5.31 tps | Hit=97.4% | NVMe=557.8 MB/s (25725.63 MB, QD=64) | RSS=13613.7 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=5.74 tps | Avg=5.39 tps | Hit=97.5% | NVMe=557.3 MB/s (29428.90 MB, QD=64) | RSS=13614.2 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=5.72 tps | Avg=5.44 tps | Hit=97.6% | NVMe=558.6 MB/s (33138.00 MB, QD=64) | RSS=13615.2 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=5.65 tps | Avg=5.47 tps | Hit=97.7% | NVMe=558.6 MB/s (36857.32 MB, QD=64) | RSS=13614.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=5.68 tps | Avg=5.49 tps | Hit=97.8% | NVMe=557.4 MB/s (40418.65 MB, QD=64) | RSS=13615.6 MB
[LIVE-DECODE] 8/64 tok | Avg=3.42 tps | Hit=97.8% (LA:+0.0%) | NVMe=560.2 MB/s (41338.16 MB) | RSS=13612.6 MB
[LIVE-DECODE] 16/64 tok | Avg=3.93 tps | Hit=97.8% (LA:+0.0%) | NVMe=566.6 MB/s (42152.09 MB) | RSS=13604.5 MB
[LIVE-DECODE] 24/64 tok | Avg=4.13 tps | Hit=97.8% (LA:+0.0%) | NVMe=573.2 MB/s (42963.96 MB) | RSS=13604.5 MB
[LIVE-DECODE] 32/64 tok | Avg=4.26 tps | Hit=97.8% (LA:+0.0%) | NVMe=580.6 MB/s (43816.70 MB) | RSS=13589.6 MB
[LIVE-DECODE] 40/64 tok | Avg=4.40 tps | Hit=97.8% (LA:+0.0%) | NVMe=589.7 MB/s (44741.65 MB) | RSS=13567.4 MB
[LIVE-DECODE] 48/64 tok | Avg=4.51 tps | Hit=97.8% (LA:+0.0%) | NVMe=598.7 MB/s (45670.64 MB) | RSS=13554.6 MB
[LIVE-DECODE] 56/64 tok | Avg=4.57 tps | Hit=97.8% (LA:+0.1%) | NVMe=606.5 MB/s (46534.73 MB) | RSS=13544.9 MB
[LIVE-DECODE] 64/64 tok | Avg=4.67 tps | Hit=97.8% (LA:+0.1%) | NVMe=615.9 MB/s (47398.97 MB) | RSS=13541.4 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=ON
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7672.00 MB (3697/25088 exp = 14.74% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13541.45 MB | Peak=14064.93 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : "
2!
!
!2!2!1!2!
!
!
!
!2!
!1!2!2!2!2!2!2!2!2!2!2!<|im_end|>!m!2!2!m!2!2!2!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=56.2% | AvgMargin=0.439 | MinMargin=0.016
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     198 | \n             |    7.38 |   0.7% |      17 |    7.24 | 372763.44 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    9.10 |   5.3% |     198 |    8.10 |  364.16 |419 | 54 |  7 | 136519.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  364.16 |  0 |  0 |  0 | 136519.5 |
   |    4 |     198 | \n             |   12.12 |  49.7% |      17 |    7.63 |  320.04 |432 | 42 |  6 | 125082.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  320.04 |  0 |  0 |  0 | 125082.0 |
   |    6 |     198 | \n             |   11.59 |  18.1% |      16 |   10.70 |  262.96 |449 | 30 |  1 | 105057.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  262.96 |  0 |  0 |  0 | 105057.0 |
   |    8 |      17 | 2              |   11.54 |   9.1% |      18 |   10.95 |  221.05 |459 | 19 |  2 | 104132.0 |
   |   30 |      17 | 2              |   12.74 |  24.7% |      16 |   11.99 |  229.21 |463 | 17 |  0 | 111469.5 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  229.21 |  0 |  0 |  0 | 111469.5 |
   |   24 |      17 | 2              |    9.93 |   6.7% |      18 |    8.79 |  223.85 |468 | 12 |  0 | 98707.0 |
   |   25 |       0 | !              |     nan | 100.0% |       1 |     nan |  223.85 |  0 |  0 |  0 | 98707.0 |
   |   62 |      17 | 2              |   11.61 |  14.1% |      16 |   10.20 |  187.19 |461 | 19 |  0 | 117607.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  187.19 |  0 |  0 |  0 | 117607.0 |
   |   64 |      17 | 2              |   13.33 |  46.1% |      16 |   12.08 |  190.87 |454 | 26 |  0 | 116869.5 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  190.87 |  0 |  0 |  0 | 116869.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 372.763s, TTFT=372763.44ms): Avg=5.49 | Min=4.54 | Max=5.74 tps
   Prefill Chunks (8): C1:256t/4.5tps/95% | C2:256t/5.4tps/97% | C3:256t/5.7tps/97% | C4:256t/5.7tps/97%
                       C5:256t/5.7tps/98% | C6:256t/5.7tps/98% | C7:256t/5.7tps/98% | C8:256t/5.7tps/98%
   Decode  (64 tok, 13.705s): Avg=4.67 | Min=2.75 | Max=5.89 tps
   Latency (ms) : Min=169.67 | P10=185.94 | P25=190.87 | P50=212.27 | P75=220.53 | P90=229.21 | P95=320.04 | P99=364.16 | Max=364.16
   Mean/SD/Jitt : Mean=214.13ms | StdDev=38.51ms | Jitter=7.79ms | Hist(<25/50/100/200/>200ms): 0/0/0/24/40
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (998400): RawRAM=975859 (97.74%) | Lookahead=628 (+0.06%) | ColdMiss=21913 (2.19%) | EFF HIT=97.81%
   Lookahead    : 3586 prefetched -> 948 consumed (26.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.8% | @64= 97.8% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |20800 |18780 |  52 |1968 | 90.5%|3402.83 | | L24 |20800 |20627 |   4 | 169 | 99.2%| 362.82 |
   | L01 |20800 |20278 |  19 | 503 | 97.6%| 958.74 | | L25 |20800 |20632 |   2 | 166 | 99.2%| 321.46 |
   | L02 |20800 |20224 |   3 | 573 | 97.2%|1313.96 | | L26 |20800 |20294 |  10 | 496 | 97.6%|1009.50 |
   | L03 |20800 |20721 |   2 |  77 | 99.6%| 426.73 | | L27 |20800 |20536 |  11 | 253 | 98.8%| 633.52 |
   | L04 |20800 |20600 |   3 | 197 | 99.1%| 747.07 | | L28 |20800 |20183 |  22 | 595 | 97.1%|1236.96 |
   | L05 |20800 |20524 |   2 | 274 | 98.7%| 793.31 | | L29 |20800 |20343 |  31 | 426 | 98.0%| 764.87 |
   | L06 |20800 |20552 |   4 | 244 | 98.8%| 582.76 | | L30 |20800 |19969 |  30 | 801 | 96.1%|1220.04 |
   | L07 |20800 |20543 |   6 | 251 | 98.8%| 434.62 | | L31 |20800 |20085 |  16 | 699 | 96.6%|1073.12 |
   | L08 |20800 |20728 |   1 |  71 | 99.7%|  93.38 | | L32 |20800 |20284 |  14 | 502 | 97.6%|1111.01 |
   | L09 |20800 |20725 |   0 |  75 | 99.6%| 112.06 | | L33 |20800 |20171 |  23 | 606 | 97.1%| 927.64 |
   | L10 |20800 |20645 |   4 | 151 | 99.3%| 276.42 | | L34 |20800 |19923 |  32 | 845 | 95.9%|1333.84 |
   | L11 |20800 |20725 |   2 |  73 | 99.6%|  98.36 | | L35 |20800 |20346 |  13 | 441 | 97.9%| 704.37 |
   | L12 |20800 |20673 |   0 | 127 | 99.4%| 242.50 | | L36 |20800 |20295 |  13 | 492 | 97.6%| 798.00 |
   | L13 |20800 |20589 |   1 | 210 | 99.0%| 311.13 | | L37 |20800 |20242 |   4 | 554 | 97.3%|1084.69 |
   | L14 |20800 |20527 |   3 | 270 | 98.7%| 494.07 | | L38 |20800 |20467 |   3 | 330 | 98.4%| 761.35 |
   | L15 |20800 |20378 |   5 | 417 | 98.0%| 849.71 | | L39 |20800 |20291 |  16 | 493 | 97.6%|1035.82 |
   | L16 |20800 |20282 |  11 | 507 | 97.6%| 985.06 | | L40 |20800 |20393 |  14 | 393 | 98.1%| 943.70 |
   | L17 |20800 |20131 |   8 | 661 | 96.8%|1317.80 | | L41 |20800 |20374 |   7 | 419 | 98.0%| 661.16 |
   | L18 |20800 |20184 |  20 | 596 | 97.1%|1203.12 | | L42 |20800 |20090 |  16 | 694 | 96.7%|1126.42 |
   | L19 |20800 |20388 |  17 | 395 | 98.1%| 625.15 | | L43 |20800 |19974 |  28 | 798 | 96.2%|1336.72 |
   | L20 |20800 |20021 |  27 | 752 | 96.4%|1171.07 | | L44 |20800 |19995 |  18 | 787 | 96.2%|1248.85 |
   | L21 |20800 |20142 |  33 | 625 | 97.0%|1408.03 | | L45 |20800 |20051 |  33 | 716 | 96.6%|1204.20 |
   | L22 |20800 |20615 |   4 | 181 | 99.1%| 353.42 | | L46 |20800 |20580 |  10 | 210 | 99.0%| 440.77 |
   | L23 |20800 |20266 |  17 | 517 | 97.5%| 831.13 | | L47 |20800 |20473 |  14 | 313 | 98.5%| 684.28 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 47398.97 MB (Load=4614.69 | Prefill=35803.96 | Warmup=0.00 | Decode=6980.32 MB)
   SSD Data/Token (Decode)      : Avg=109.068 MB/tok (Min=92.255 | P50=108.552 | P95=132.294 | Max=133.320 MB) | Prefill=17.482 MB/tok
   NVMe Batches / Requests      : 2302 Batches | 110885 Raw -> 106712 Merged (4173 LBA Merges, Avg 454.8 KB/io)
   SSD I/O Size Histogram       : <64K=33329 | 64K-512K=18953 | 512K-2M=53938 | >2M=492
   SSD Read Bandwidth (Active)  : Min=6.90 | Avg=615.88 | Peak=11071.16 MB/s | WallAmort=122.65 MB/s
   OS Kernel I/O Verification   : Read=47419.51 MB | Write=0.00 MB | Syscalls=116225
   Sync Stall vs Async DMA      : SyncStall=59245.29 ms | AsyncOverlapped=68748.90 ms (53.7% Overlapped)
   RAM Traffic & Active BW      : 5562.56 GB moved | Active=17.92 GB/s | WallAmort=14.39 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=372.76s (96.5%, 35803.96 MB SSD) | Decode=13.70s (3.5%, 6980.32 MB SSD)
   CPU Time & Utilization       : User=1150.031s + Sys=19.625s (Wall=397.573s) | SysUtil=73.5% | ThrUtil=73.5% | 68.03 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 144743.91 ms (68534.1 us/tok | 37.45%)
   MoE AVX2 Q8 Expert Compute   : 164429.74 ms (77855.0 us/tok | 42.55%)
   Router + Lookahead Dispatch  :   9008.86 ms ( 4265.6 us/tok |  2.33%)
   LM Head Output Projection    :   1187.69 ms (  562.4 us/tok |  0.31%)
   Foreground NVMe Sync Stall   :  59245.29 ms (28051.7 us/tok | 15.33%)
   Unaccounted / OMP & Sampling :   7852.47 ms ( 3718.0 us/tok |  2.03%) | Total Wall=386467.97 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    91.34%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     0.92%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.57%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     3.59%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.58%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_qwen38_colibri_bench.log`
```text
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=225.0s) ===
[gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
[gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
== Qwen3.8-Flash-Next native text engine | cache=72/layer | CPU ==
[tok] loaded 248320 base pieces + 33 added tokens (max id 248319) from D:/apex_d_drive/models/qwen38/tokenizer.json
[qwen38] native text weights: prefix=model, 48 layers, PLE=1, cache=72/layer, FP8=native, BF16=native (resident matrices 4.40 GiB)
[qwen38] MTP head mtp.*: wiring b (a norm per stream, fc_hidden per stream), RoPE base 1e+07, 96.86 MiB resident; routed experts Q8_0 from the snapshot (its own GGUF), cache 72 (Q38_MTP_CAP) x 4.98 MiB = 0.35 GiB full
[qwen38] MTP norm weights, mean: embedding -0.7642, hidden -0.3284, mixer 3.7881 (q38_rms0 scales by 1+w; a plain norm's weights would sit near 1)
[qwen38] trunk: 62 matrices int8 on the CPU (0.08 GiB, 0.28 GiB of BF16 released) in 0.1s; Q38_TRUNK_CPU_INT8=0 keeps BF16
[qwen38 MTP] draft vocabulary: the lm_head has no int8 rows on the host, so the head scores the whole vocabulary (Q38_MTP_VOCAB=0 silences this)
[qwen38] routed experts: GGUF IQ2_XXS/IQ2_XXS/IQ4_NL (layer 0), 1.68 MiB per expert; cache 72/layer
[qwen38] trunk: 62 int8 matrices interleaved by 16 for the CPU in 0.01s (Q38_ILV16=0 keeps the rows)
resident weights loaded in 8.7s | RSS after load: 4.60 GB
[qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=225.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.1s / cutoff=225.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=225.0s
TTFT: 21.52 s (time to first token)
[qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
[qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
[qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes

PEAK RSS: 10.70 GB
Expert cache hit rate: 62.0% (hit=15849 miss=9733)
Speed: 0.77 tok/s (41.6s for 32 tokens)
[STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage

Reference: 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 
C engine : 220 248046 198 248045 74455 198 248068 198 760 1156 682 3106 1092 7701 310 381 264 7132 36412 2805 269 82987 886 314 5587 13 6558 728 22903 411 25 271 Text      :  <|im_end|>
<|im_start|>assistant
<think>
The user has sent what appears to be a garbled/corrupted string of characters. Let me analyze this:



Matching tokens: 0/32
=== [Colibri-Qwen38] Finished rc=1 elapsed=52.60s cancelled=False ===
```

### 📄 `12_qwen38_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 2.97 | 3.42 | 280.51 | 90.45% | 602.48 | 12927.72 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 4.88 | 5.03 | 189.74 | 97.04% | 785.90 | 14118.84 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 5.49 | 4.67 | 212.27 | 97.81% | 615.88 | 14064.93 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.77 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
