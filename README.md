<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#21 (Run ID `43451696418`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43451696418)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-13 15:52:11 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-13T15:20:56.370Z] ================================================================================
[2026-11-13T15:20:56.386Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-13T15:20:56.388Z] ================================================================================
[2026-11-13T15:21:02.734Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-13T15:21:02.908Z] --------------------------------------------------------------------------------
[2026-11-13T15:21:02.910Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.12 GB / 149.89 GB
[2026-11-13T15:21:02.911Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-13T15:21:02.912Z]  [Disk Telemetry] Total Combined Usable Free Space: 247.99 GB
[2026-11-13T15:21:02.924Z] --------------------------------------------------------------------------------
[2026-11-13T15:21:02.925Z]  [OK] Disk space verification passed: 247.99 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 865K Nov 13 15:21 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 865K Nov 13 15:21 build/apex.exe
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
   SEQ1M Direct Uncached NVMe Read    :    592.49 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2503.10 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9762.35 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11205.76 MB/s
   RND4K Q32T16 Read                  :    715.00 MB/s (  183041 IOPS)
   RND4K Q1T1  Read                   :    862.37 MB/s (Latency: 4.53 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     64.10 GB/s
   AVX2 256-bit Sequential Write BW   :     62.84 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.01 GB/s
   Random Pointer-Chase Latency       :     97.87 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.41 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    225.82 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     27.27 GB/s (FP32 Equiv)
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
[Apex-Parity] Serial  Tokens (16) : [49, 193, 68, 63, 223, 193, 128, 49, 49, 66, 67, 19, 49, 18, 49, 18] -> "qtok_49qtok_193qtok_68qtok_63qtok_223qtok_193qtok_128qtok_49qtok_49qtok_66qtok_67qtok_19qtok_49qtok_18qtok_49qtok_18"
[Apex-Parity] Batched Tokens (16) : [49, 193, 68, 63, 223, 193, 128, 49, 49, 66, 67, 19, 49, 18, 49, 18] -> "qtok_49qtok_193qtok_68qtok_63qtok_223qtok_193qtok_128qtok_49qtok_49qtok_66qtok_67qtok_19qtok_49qtok_18qtok_49qtok_18"
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] GLM-5.3-Flash 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_glm53_ud_iq2_xxs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=1.93 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1803.18 tps | Avg=1803.18 tps | Hit=99.5% | NVMe=2801.9 MB/s (6.19 MB, QD=64) | RSS=71.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1652.54 tps | Avg=1724.58 tps | Hit=99.5% | NVMe=2645.3 MB/s (7.01 MB, QD=64) | RSS=71.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1442.08 tps | Avg=1618.87 tps | Hit=99.5% | NVMe=2548.5 MB/s (7.78 MB, QD=64) | RSS=71.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1258.09 tps | Avg=1510.57 tps | Hit=99.5% | NVMe=2314.0 MB/s (8.61 MB, QD=64) | RSS=72.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1145.36 tps | Avg=1420.02 tps | Hit=99.5% | NVMe=2282.9 MB/s (9.33 MB, QD=64) | RSS=72.2 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1022.81 tps | Avg=1333.69 tps | Hit=99.5% | NVMe=2248.6 MB/s (10.06 MB, QD=64) | RSS=72.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=940.06 tps | Avg=1258.42 tps | Hit=99.5% | NVMe=2221.7 MB/s (10.83 MB, QD=64) | RSS=72.7 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=866.10 tps | Avg=1190.98 tps | Hit=99.5% | NVMe=2164.7 MB/s (11.60 MB, QD=64) | RSS=73.0 MB
[LIVE-DECODE] 8/32 tok | Avg=259.13 tps | Hit=99.5% (LA:+0.0%) | NVMe=2121.8 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=263.24 tps | Hit=99.5% (LA:+0.1%) | NVMe=2084.5 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=265.47 tps | Hit=99.5% (LA:+0.1%) | NVMe=2058.4 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=265.82 tps | Hit=99.5% (LA:+0.1%) | NVMe=2047.7 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=73.07 MB | Peak=73.07 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1719.59 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    3.97 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    3.97 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    3.94 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    3.94 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    3.81 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    3.81 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    3.71 | 11 |  1 |  0 |    49.5 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    3.78 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    3.78 |  0 |  0 |  0 |   173.2 |
   |   14 |     220 | tok_220        |  147.52 |  55.4% |      55 |  147.01 |    3.76 |  9 |  3 |  0 |   173.2 |
   |   15 |     197 | tok_197        |   65.84 |  97.8% |     133 |   62.03 |    3.76 |  0 |  0 |  0 |   173.2 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    3.82 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    3.82 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    3.75 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    3.75 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.720s, TTFT=1719.59ms): Avg=1190.98 | Min=866.10 | Max=1803.18 tps
   Prefill Chunks (8): C1:256t/1803.2tps/99% | C2:256t/1652.5tps/99% | C3:256t/1442.1tps/99% | C4:256t/1258.1tps/99%
                       C5:256t/1145.4tps/99% | C6:256t/1022.8tps/99% | C7:256t/940.1tps/99% | C8:256t/866.1tps/99%
   Decode  (32 tok, 0.120s): Avg=265.82 | Min=251.60 | Max=271.96 tps
   Latency (ms) : Min=3.68 | P10=3.70 | P25=3.71 | P50=3.72 | P75=3.81 | P90=3.94 | P95=3.97 | P99=3.97 | Max=3.97
   Mean/SD/Jitt : Mean=3.76ms | StdDev=0.08ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=442.67 | Avg=2047.70 | Peak=7022.47 MB/s | WallAmort=7.23 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=4.57 ms | AsyncOverlapped=5.45 ms (54.4% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.82 GB/s | WallAmort=0.78 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.72s (93.5%, 6.19 MB SSD) | Decode=0.12s (6.5%, 1.69 MB SSD)
   CPU Time & Utilization       : User=2.312s + Sys=0.469s (Wall=1.857s) | SysUtil=37.5% | ThrUtil=37.5% | 34.64 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1549.56 ms (  745.0 us/tok | 84.22%)
   MoE AVX2 Q8 Expert Compute   :    187.03 ms (   89.9 us/tok | 10.16%)
   Router + Lookahead Dispatch  :     47.83 ms (   23.0 us/tok |  2.60%)
   LM Head Output Projection    :      4.43 ms (    2.1 us/tok |  0.24%)
   Foreground NVMe Sync Stall   :      4.57 ms (    2.2 us/tok |  0.25%)
   Unaccounted / OMP & Sampling :     46.55 ms (   22.4 us/tok |  2.53%) | Total Wall=1839.97 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    23.77%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.21%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.46%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    71.22%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.34%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2597.45 tps | Avg=2597.45 tps | Hit=99.2% | NVMe=3306.4 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2541.26 tps | Avg=2569.05 tps | Hit=99.2% | NVMe=4338.9 MB/s (42.92 MB, QD=64) | RSS=89.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2247.75 tps | Avg=2452.20 tps | Hit=99.2% | NVMe=4904.3 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2163.13 tps | Avg=2372.93 tps | Hit=99.2% | NVMe=5269.9 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2055.19 tps | Avg=2301.76 tps | Hit=99.2% | NVMe=5573.4 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1893.63 tps | Avg=2221.94 tps | Hit=99.2% | NVMe=5793.9 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1675.73 tps | Avg=2123.08 tps | Hit=99.2% | NVMe=5942.9 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1658.94 tps | Avg=2051.34 tps | Hit=99.2% | NVMe=6109.4 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=242.37 tps | Hit=99.2% (LA:+0.0%) | NVMe=5991.6 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=245.26 tps | Hit=99.2% (LA:+0.1%) | NVMe=5930.0 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=245.72 tps | Hit=99.2% (LA:+0.1%) | NVMe=5830.0 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=245.91 tps | Hit=99.2% (LA:+0.1%) | NVMe=5750.4 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=91.71 MB | Peak=91.71 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_129qtok_68qtok_209qtok_223qtok_113qtok_229qtok_112qtok_193qtok_63qtok_128qtok_63qtok_128qtok_63qtok_194qtok_49qtok_49qtok_148qtok_254qtok_48qtok_254qtok_49"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=93.4% | AvgMargin=10.261 | MinMargin=0.202
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 |  998.37 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    4.19 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    4.19 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    4.14 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    4.14 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    4.11 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    4.11 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    4.06 | 16 |  0 |  0 |    32.0 |
   |   26 |     194 | qtok_194       |   71.13 | 100.0% |       2 |   54.96 |    4.07 | 12 |  4 |  0 |   147.0 |
   |   27 |      49 | qtok_49        |   67.58 |  99.9% |     209 |   61.01 |    4.07 |  0 |  0 |  0 |   147.0 |
   |   20 |     193 | qtok_193       |   68.69 | 100.0% |      17 |   59.53 |    4.07 | 14 |  2 |  0 |    87.5 |
   |   21 |      63 | qtok_63        |   75.06 |  99.9% |     193 |   67.57 |    4.07 |  0 |  0 |  0 |    87.5 |
   |   30 |     254 | qtok_254       |   58.92 |  92.7% |      49 |   56.39 |    4.06 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    4.06 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.75 |  64.8% |     229 |   52.56 |    4.04 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    4.04 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 0.998s, TTFT=998.37ms): Avg=2051.34 | Min=1658.94 | Max=2597.45 tps
   Prefill Chunks (8): C1:256t/2597.5tps/99% | C2:256t/2541.3tps/99% | C3:256t/2247.7tps/99% | C4:256t/2163.1tps/99%
                       C5:256t/2055.2tps/99% | C6:256t/1893.6tps/99% | C7:256t/1675.7tps/99% | C8:256t/1658.9tps/99%
   Decode  (32 tok, 0.130s): Avg=245.91 | Min=238.62 | Max=249.45 tps
   Latency (ms) : Min=4.01 | P10=4.02 | P25=4.04 | P50=4.06 | P75=4.07 | P90=4.14 | P95=4.19 | P99=4.19 | Max=4.19
   Mean/SD/Jitt : Mean=4.07ms | StdDev=0.04ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=446.08 | Avg=5750.41 | Peak=10546.52 MB/s | WallAmort=137.47 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=6.43 ms | AsyncOverlapped=25.74 ms (80.0% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=2.15 GB/s | WallAmort=1.86 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.00s (88.5%, 144.44 MB SSD) | Decode=0.13s (11.5%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.078s + Sys=0.312s (Wall=1.157s) | SysUtil=51.7% | ThrUtil=51.7% | 47.79 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    688.39 ms (  331.0 us/tok | 61.00%)
   MoE AVX2 Q8 Expert Compute   :    286.33 ms (  137.7 us/tok | 25.37%)
   Router + Lookahead Dispatch  :     63.27 ms (   30.4 us/tok |  5.61%)
   LM Head Output Projection    :      4.20 ms (    2.0 us/tok |  0.37%)
   Foreground NVMe Sync Stall   :      6.43 ms (    3.1 us/tok |  0.57%)
   Unaccounted / OMP & Sampling :     79.88 ms (   38.4 us/tok |  7.08%) | Total Wall=1128.50 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    20.63%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.02%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.24%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    65.48%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.63%  |
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
    "ttft_ms": 172.54,
    "avg_tps": 950.51,
    "min_tps": 785.51,
    "max_tps": 1073.85
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 202.26,
    "min_tps": 181.68,
    "max_tps": 208.94,
    "p50_ms": 4.91,
    "p90_ms": 5.17,
    "p99_ms": 5.5,
    "mean_ms": 4.94,
    "jitter_ms": 0.12
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
    "avg_mbs": 2177.27,
    "peak_mbs": 6578.95,
    "sync_wait_ms": 1.6,
    "async_overlap_ms": 2.83
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
    "dense_attention": 272.65,
    "moe_compute": 75.33,
    "router_lookahead": 5.8,
    "lm_head": 6.02,
    "unaccounted": 3.96
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 81.92,
    "ram_bandwidth_pinning": 2.52,
    "expert_cache_lrfu": 12.07,
    "lookahead_parallel_overlap": 2.25,
    "ssd_nvme_throughput": 1.24,
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
    "ttft_ms": 218.91,
    "avg_tps": 749.17,
    "min_tps": 533.79,
    "max_tps": 852.19
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 178.58,
    "min_tps": 172.02,
    "max_tps": 182.76,
    "p50_ms": 5.59,
    "p90_ms": 5.73,
    "p99_ms": 5.81,
    "mean_ms": 5.6,
    "jitter_ms": 0.06
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
    "avg_mbs": 2926.17,
    "peak_mbs": 7508.48,
    "sync_wait_ms": 4.16,
    "async_overlap_ms": 11.41
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
    "dense_attention": 246.73,
    "moe_compute": 142.31,
    "router_lookahead": 7.08,
    "lm_head": 6.02,
    "unaccounted": 31.01
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 78.4,
    "ram_bandwidth_pinning": 2.91,
    "expert_cache_lrfu": 10.21,
    "lookahead_parallel_overlap": 5.19,
    "ssd_nvme_throughput": 3.29,
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
 [Step 4.0] Built-In Windows Host Hardware Benchmark (winsat disk & winsat mem)
================================================================================
Host CPU: AMD EPYC 9V74 80-Core Processor | Cores=2 Threads=4 | RAM=15.99 GB
--- winsat disk -seq -read -drive c ---
Windows System Assessment Tool
Error: Unable to run inside of a Virtual Machine.  Please try again running directly on the native hardware.
--- winsat disk -seq -read -drive d ---
Windows System Assessment Tool
Error: Unable to run inside of a Virtual Machine.  Please try again running directly on the native hardware.
--- winsat disk -ran -read -drive d ---
Windows System Assessment Tool
Error: Unable to run inside of a Virtual Machine.  Please try again running directly on the native hardware.
--- winsat mem ---
Windows System Assessment Tool
Error: Unable to run inside of a Virtual Machine.  Please try again running directly on the native hardware.
================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: qwen38 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (0.010 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 100.00% (0.01/0.01 GB) @ 67.4 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (43.792 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  11.42% (5.00/43.79 GB) @ 310.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  22.84% (10.00/43.79 GB) @ 266.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  34.25% (15.00/43.79 GB) @ 252.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  45.67% (20.00/43.79 GB) @ 257.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  57.09% (25.00/43.79 GB) @ 259.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  68.51% (30.00/43.79 GB) @ 252.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  79.92% (35.00/43.79 GB) @ 252.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  91.34% (40.00/43.79 GB) @ 222.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf: 100.00% (43.79/43.79 GB) @ 227.4 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (26.822 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  18.64% (5.00/26.82 GB) @ 232.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  37.28% (10.00/26.82 GB) @ 227.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  55.92% (15.00/26.82 GB) @ 236.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  74.57% (20.00/26.82 GB) @ 235.8 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  93.21% (25.00/26.82 GB) @ 235.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf: 100.00% (26.82/26.82 GB) @ 243.8 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/MTP/mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (2.595 GB) -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Sequential Non-Truncate)
  [DL] mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 100.00% (2.60/2.60 GB) @ 30.0 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=78,618,661,594 (73.22 GB) | Elapsed=399.59s
[Colibri-Import] Running baselines/colibri/c/tools/gguf_import.py on D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf -> D:/apex_d_drive/models/qwen38 (--mode link)...
colibri model directory ready: D:\apex_d_drive\models\qwen38  (qwen4exp, 48 layers, mode link)
  MTP head: C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf
Verified Primary Shard 1 Path: D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Alt Shard Dir: C:/apex_c_drive/models/qwen38)
--------------------------------------------------------------------------------
 [Stage 1] Small Prompt (64 tokens) + 100.00% Greedy Parity & Prompt/Response Trace
--------------------------------------------------------------------------------
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (4) : [17, 21, 25, 17] -> "26:2"
[Apex-Parity] Batched Tokens (4) : [17, 21, 25, 17] -> "26:2"
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 4 / 4 (100.00% Parity)
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7196.78 MB (3468 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=1.70 tps | Avg=1.70 tps | Hit=79.7% | NVMe=527.1 MB/s (14858.61 MB, QD=64) | RSS=13120.5 MB
[LIVE-DECODE] 8/32 tok | Avg=1.95 tps | Hit=80.3% (LA:+1.8%) | NVMe=541.0 MB/s (17036.89 MB) | RSS=13127.1 MB
[LIVE-DECODE] 16/32 tok | Avg=2.32 tps | Hit=81.2% (LA:+2.9%) | NVMe=561.6 MB/s (18641.19 MB) | RSS=13091.0 MB
[LIVE-DECODE] 24/32 tok | Avg=2.48 tps | Hit=82.1% (LA:+3.4%) | NVMe=576.1 MB/s (19955.60 MB) | RSS=13085.1 MB
[LIVE-DECODE] 32/32 tok | Avg=2.64 tps | Hit=82.9% (LA:+3.7%) | NVMe=590.7 MB/s (21096.85 MB) | RSS=13073.6 MB

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
   LRFU Cache / Staging Ring    : 7196.78 MB (3468/25088 exp = 13.82% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=13073.65 MB | Peak=13550.32 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " 2!@!$!m! !! !! !! !! !! !! !! !! !!!! !! !!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=56.5% | AvgMargin=0.439 | MinMargin=0.031
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     220 |                |   15.43 |   8.4% |    2446 |   14.41 | 37718.98 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |   18.13 |  24.4% |      16 |   18.10 |  548.40 |241 |186 | 53 | 297232.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  548.40 |  0 |  0 |  0 | 297232.0 |
   |    4 |      31 | @              |   12.60 |   7.7% |      76 |   12.56 |  604.22 |235 |178 | 67 | 325719.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  604.22 |  0 |  0 |  0 | 325719.5 |
   |    6 |       3 | $              |   12.91 |  13.1% |      12 |   12.65 |  532.83 |262 |158 | 60 | 302784.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  532.83 |  0 |  0 |  0 | 302784.0 |
   |    8 |      76 | m              |   11.77 |   3.8% |   35716 |   11.70 |  370.87 |382 | 79 | 19 | 189544.5 |
   |   24 |     729 |  !             |   12.39 |  23.4% |       3 |   10.35 |  421.38 |424 | 56 |  0 | 151844.5 |
   |   25 |       0 | !              |     nan | 100.0% |       1 |     nan |  421.38 |  0 |  0 |  0 | 151844.5 |
   |   10 |     729 |  !             |   11.71 |   9.5% |    1088 |   10.91 |  377.22 |342 |122 | 16 | 220394.5 |
   |   11 |       0 | !              |     nan | 100.0% |       1 |     nan |  377.22 |  0 |  0 |  0 | 220394.5 |
   |   30 |     729 |  !             |   11.42 |   8.7% |     198 |   11.23 |  291.97 |435 | 45 |  0 | 134494.5 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  291.97 |  0 |  0 |  0 | 134494.5 |
   |   32 |     729 |  !             |   12.57 |  23.3% |   13682 |   10.85 |  293.12 |446 | 34 |  0 | 122669.5 |
   |   33 |       0 | !              |     nan | 100.0% |       1 |     nan |  293.12 |  0 |  0 |  0 | 122669.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 37.719s, TTFT=37718.98ms): Avg=1.70 | Min=1.70 | Max=1.70 tps
   Prefill Chunks (1): C1:64t/1.7tps/80%
   Decode  (32 tok, 12.103s): Avg=2.64 | Min=1.66 | Max=3.56 tps
   Latency (ms) : Min=281.01 | P10=291.97 | P25=320.76 | P50=350.58 | P75=421.38 | P90=548.40 | P95=604.22 | P99=604.22 | Max=604.22
   Mean/SD/Jitt : Mean=378.21ms | StdDev=95.82ms | Jitter=26.93ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (38400): RawRAM=30419 (79.22%) | Lookahead=1429 (+3.72%) | ColdMiss=6552 (17.06%) | EFF HIT=82.94%
   Lookahead    : 3172 prefetched -> 1589 consumed (50.1% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 81.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  800 |  537 |  26 | 237 | 70.4%| 443.04 | | L24 |  800 |  639 |  35 | 126 | 84.2%| 364.70 |
   | L01 |  800 |  605 |  23 | 172 | 78.5%| 398.44 | | L25 |  800 |  649 |  33 | 118 | 85.2%| 325.22 |
   | L02 |  800 |  599 |  16 | 185 | 76.9%| 534.01 | | L26 |  800 |  624 |  40 | 136 | 83.0%| 355.30 |
   | L03 |  800 |  698 |   8 |  94 | 88.2%| 332.74 | | L27 |  800 |  650 |  24 | 126 | 84.2%| 300.78 |
   | L04 |  800 |  654 |  11 | 135 | 83.1%| 415.04 | | L28 |  800 |  611 |  30 | 159 | 80.1%| 404.17 |
   | L05 |  800 |  622 |  17 | 161 | 79.9%| 407.93 | | L29 |  800 |  620 |  41 | 139 | 82.6%| 315.45 |
   | L06 |  800 |  611 |  23 | 166 | 79.2%| 415.45 | | L30 |  800 |  636 |  36 | 128 | 84.0%| 279.44 |
   | L07 |  800 |  599 |  25 | 176 | 78.0%| 394.19 | | L31 |  800 |  660 |  28 | 112 | 86.0%| 266.48 |
   | L08 |  800 |  645 |  31 | 124 | 84.5%| 216.65 | | L32 |  800 |  672 |  33 |  95 | 88.1%| 265.06 |
   | L09 |  800 |  658 |  27 | 115 | 85.6%| 192.99 | | L33 |  800 |  609 |  46 | 145 | 81.9%| 306.81 |
   | L10 |  800 |  633 |  30 | 137 | 82.9%| 229.10 | | L34 |  800 |  611 |  39 | 150 | 81.2%| 316.89 |
   | L11 |  800 |  638 |  34 | 128 | 84.0%| 236.57 | | L35 |  800 |  657 |  32 | 111 | 86.1%| 247.75 |
   | L12 |  800 |  608 |  31 | 161 | 79.9%| 389.14 | | L36 |  800 |  619 |  38 | 143 | 82.1%| 306.81 |
   | L13 |  800 |  598 |  56 | 146 | 81.8%| 325.54 | | L37 |  800 |  630 |  26 | 144 | 82.0%| 368.46 |
   | L14 |  800 |  616 |  51 | 133 | 83.4%| 308.25 | | L38 |  800 |  595 |  33 | 172 | 78.5%| 449.29 |
   | L15 |  800 |  667 |  19 | 114 | 85.8%| 345.90 | | L39 |  800 |  694 |  14 |  92 | 88.5%| 297.02 |
   | L16 |  800 |  670 |  32 |  98 | 87.8%| 265.06 | | L40 |  800 |  685 |  19 |  96 | 88.0%| 263.18 |
   | L17 |  800 |  645 |  35 | 120 | 85.0%| 319.58 | | L41 |  800 |  656 |  20 | 124 | 84.5%| 223.27 |
   | L18 |  800 |  603 |  39 | 158 | 80.2%| 428.61 | | L42 |  800 |  624 |  27 | 149 | 81.4%| 301.05 |
   | L19 |  800 |  655 |  41 | 104 | 87.0%| 253.52 | | L43 |  800 |  680 |  23 |  97 | 87.9%| 210.30 |
   | L20 |  800 |  615 |  38 | 147 | 81.6%| 303.93 | | L44 |  800 |  639 |  29 | 132 | 83.5%| 278.00 |
   | L21 |  800 |  608 |  40 | 152 | 81.0%| 432.37 | | L45 |  800 |  646 |  26 | 128 | 84.0%| 273.68 |
   | L22 |  800 |  575 |  39 | 186 | 76.8%| 490.65 | | L46 |  800 |  638 |  22 | 140 | 82.5%| 275.12 |
   | L23 |  800 |  678 |  23 |  99 | 87.6%| 221.83 | | L47 |  800 |  638 |  20 | 142 | 82.2%| 385.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 21096.85 MB (Load=4614.69 | Prefill=10243.92 | Warmup=0.00 | Decode=6238.24 MB)
   SSD Data/Token (Decode)      : Avg=194.945 MB/tok (Min=119.794 | P50=185.102 | P95=318.085 | Max=318.085 MB) | Prefill=160.061 MB/tok
   NVMe Batches / Requests      : 1297 Batches | 31560 Raw -> 30257 Merged (1303 LBA Merges, Avg 714.0 KB/io)
   SSD I/O Size Histogram       : <64K=1595 | 64K-512K=7504 | 512K-2M=20714 | >2M=444
   SSD Read Bandwidth (Active)  : Min=10.89 | Avg=590.72 | Peak=9804.07 MB/s | WallAmort=423.45 MB/s
   OS Kernel I/O Verification   : Read=21116.82 MB | Write=0.00 MB | Syscalls=39759
   Sync Stall vs Async DMA      : SyncStall=20462.86 ms | AsyncOverlapped=26994.42 ms (56.9% Overlapped)
   RAM Traffic & Active BW      : 360.23 GB moved | Active=14.61 GB/s | WallAmort=7.23 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=37.72s (75.7%, 10243.92 MB SSD) | Decode=12.10s (24.3%, 6238.24 MB SSD)
   CPU Time & Utilization       : User=77.953s + Sys=5.859s (Wall=62.473s) | SysUtil=33.5% | ThrUtil=33.5% | 31.02 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  11621.26 ms (121054.7 us/tok | 23.33%)
   MoE AVX2 Q8 Expert Compute   :  11739.16 ms (122282.9 us/tok | 23.56%)
   Router + Lookahead Dispatch  :    509.43 ms ( 5306.5 us/tok |  1.02%)
   LM Head Output Projection    :   1301.15 ms (13553.6 us/tok |  2.61%)
   Foreground NVMe Sync Stall   :  20462.86 ms (213154.8 us/tok | 41.07%)
   Unaccounted / OMP & Sampling :   4187.70 ms (43621.9 us/tok |  8.41%) | Total Wall=49821.55 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    66.84%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     8.33%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    14.64%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     6.43%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.76%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 65s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 14.69 GB Available
   Active Drive Space : 219.98 GB Total / 149.17 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    571.91 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2260.23 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9365.56 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10504.16 MB/s
   RND4K Q32T16 Read                  :    624.41 MB/s (  159850 IOPS)
   RND4K Q1T1  Read                   :    742.91 MB/s (Latency: 5.26 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     66.81 GB/s
   AVX2 256-bit Sequential Write BW   :     59.56 GB/s
   STREAM Triad (A = B + s*C) BW      :     42.05 GB/s
   Random Pointer-Chase Latency       :    102.93 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.40 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    223.39 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.21 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=1.78 tps | Avg=1.78 tps | Hit=79.2% | NVMe=534.1 MB/s (19602.76 MB, QD=64) | RSS=13615.7 MB

 >>> [Apex-Model-Response] <think>
!
!
!<|im_end|>!<|im_end|>!
!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   LRFU Cache / Staging Ring    : 7676.15 MB (3699/25088 exp = 14.74% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.70 MB | End=13502.75 MB | Peak=14018.57 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "<think>
!
!
!<|im_end|>!<|im_end|>!
!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=73.5% | AvgMargin=1.204 | MinMargin=0.120
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |  248068 | <think>        |   32.95 | 100.0% |  248045 |   12.90 | 51210.59 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |   21.79 |  63.4% |     271 |   21.24 |  318.78 |392 | 84 |  4 | 122932.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  318.78 |  0 |  0 |  0 | 122932.0 |
   |    4 |     198 | \n             |   12.40 |  23.4% |     271 |   12.06 |  478.98 |378 | 87 | 15 | 156682.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  478.98 |  0 |  0 |  0 | 156682.0 |
   |    6 |     198 | \n             |   12.62 |  21.8% |  248046 |   12.50 |  363.30 |409 | 64 |  7 | 128584.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  363.30 |  0 |  0 |  0 | 128584.0 |
   |    8 |  248046 | <|im_end|>     |   13.00 |  28.4% |     198 |   12.13 |  506.17 |437 | 42 |  1 | 107957.0 |
   |   26 |       0 | !              |   13.54 |  54.3% |     198 |   10.71 |  536.46 |318 |103 | 59 | 269957.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  536.46 |  0 |  0 |  0 | 269957.0 |
   |   18 |       0 | !              |   13.85 |  46.9% |     198 |   12.04 |  530.02 |296 |115 | 69 | 276882.0 |
   |   19 |       0 | !              |     nan | 100.0% |       1 |     nan |  530.02 |  0 |  0 |  0 | 276882.0 |
   |   62 |       0 | !              |   15.17 |  81.0% |     198 |   11.37 |  335.24 |420 | 52 |  8 | 175869.5 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  335.24 |  0 |  0 |  0 | 175869.5 |
   |   64 |       0 | !              |   13.02 |  35.5% |     198 |   11.60 |  353.97 |396 | 62 | 22 | 179119.5 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  353.97 |  0 |  0 |  0 | 179119.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 51.211s, TTFT=51210.59ms): Avg=1.78 | Min=1.78 | Max=1.78 tps
   Prefill Chunks (1): C1:91t/1.8tps/79%
   Decode  (64 tok, 23.376s): Avg=2.74 | Min=1.86 | Max=3.81 tps
   Latency (ms) : Min=262.16 | P10=293.92 | P25=324.25 | P50=353.97 | P75=396.20 | P90=478.98 | P95=530.02 | P99=536.46 | Max=536.46
   Mean/SD/Jitt : Mean=365.24ms | StdDev=72.39ms | Jitter=43.40ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (59040): RawRAM=47708 (80.81%) | Lookahead=1809 (+3.06%) | ColdMiss=9523 (16.13%) | EFF HIT=83.87%
   Lookahead    : 4779 prefetched -> 2129 consumed (44.5% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 80.8% | @64= 83.9% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1230 |  888 |  28 | 314 | 74.5%| 576.12 | | L24 | 1230 |  999 |  52 | 179 | 85.4%| 539.53 |
   | L01 | 1230 |  966 |  10 | 254 | 79.3%| 636.25 | | L25 | 1230 |  955 |  71 | 204 | 83.4%| 571.48 |
   | L02 | 1230 |  973 |  14 | 243 | 80.2%| 651.93 | | L26 | 1230 |  942 |  83 | 205 | 83.3%| 637.28 |
   | L03 | 1230 | 1068 |  10 | 152 | 87.6%| 590.28 | | L27 | 1230 |  966 |  80 | 184 | 85.0%| 582.76 |
   | L04 | 1230 | 1010 |  11 | 209 | 83.0%| 742.92 | | L28 | 1230 |  928 |  69 | 233 | 81.1%| 667.36 |
   | L05 | 1230 |  993 |  13 | 224 | 81.8%| 462.45 | | L29 | 1230 |  946 |  92 | 192 | 84.4%| 468.14 |
   | L06 | 1230 |  963 |  10 | 257 | 79.1%| 528.25 | | L30 | 1230 |  924 |  84 | 222 | 82.0%| 517.11 |
   | L07 | 1230 |  979 |  18 | 233 | 81.1%| 426.20 | | L31 | 1230 | 1031 |  36 | 163 | 86.7%| 420.61 |
   | L08 | 1230 | 1055 |  11 | 164 | 86.7%| 226.61 | | L32 | 1230 | 1006 |  45 | 179 | 85.4%| 498.17 |
   | L09 | 1230 | 1037 |  17 | 176 | 85.7%| 247.78 | | L33 | 1230 |  931 |  93 | 206 | 83.3%| 486.87 |
   | L10 | 1230 | 1030 |  16 | 184 | 85.0%| 260.23 | | L34 | 1230 |  979 |  52 | 199 | 83.8%| 515.67 |
   | L11 | 1230 | 1049 |  18 | 163 | 86.7%| 254.00 | | L35 | 1230 |  994 |  63 | 173 | 85.9%| 394.68 |
   | L12 | 1230 |  992 |  23 | 215 | 82.5%| 516.97 | | L36 | 1230 |  999 |  42 | 189 | 84.6%| 435.01 |
   | L13 | 1230 | 1039 |  28 | 163 | 86.7%| 308.25 | | L37 | 1230 | 1032 |  19 | 179 | 85.4%| 449.29 |
   | L14 | 1230 |  973 |  61 | 196 | 84.1%| 505.59 | | L38 | 1230 |  944 |  27 | 259 | 78.9%| 627.88 |
   | L15 | 1230 | 1071 |  26 | 133 | 89.2%| 426.73 | | L39 | 1230 | 1038 |  36 | 156 | 87.3%| 498.17 |
   | L16 | 1230 | 1005 |  59 | 166 | 86.5%| 468.09 | | L40 | 1230 |  999 |  50 | 181 | 85.3%| 473.73 |
   | L17 | 1230 |  969 |  64 | 197 | 84.0%| 586.52 | | L41 | 1230 | 1008 |  31 | 191 | 84.5%| 361.55 |
   | L18 | 1230 |  980 |  28 | 222 | 82.0%| 663.60 | | L42 | 1230 |  987 |  24 | 219 | 82.2%| 417.72 |
   | L19 | 1230 |  990 |  72 | 168 | 86.3%| 432.13 | | L43 | 1230 | 1034 |  31 | 165 | 86.6%| 306.81 |
   | L20 | 1230 |  983 |  48 | 199 | 83.8%| 420.61 | | L44 | 1230 | 1026 |  12 | 192 | 84.4%| 364.43 |
   | L21 | 1230 |  983 |  29 | 218 | 82.3%| 673.00 | | L45 | 1230 | 1036 |   7 | 187 | 84.8%| 299.61 |
   | L22 | 1230 |  945 |  20 | 265 | 78.5%| 727.51 | | L46 | 1230 | 1018 |  19 | 193 | 84.3%| 388.92 |
   | L23 | 1230 | 1026 |  43 | 161 | 86.9%| 377.39 | | L47 | 1230 | 1019 |  14 | 197 | 84.0%| 438.01 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 29286.48 MB (Load=4614.69 | Prefill=14988.07 | Warmup=0.00 | Decode=9683.72 MB)
   SSD Data/Token (Decode)      : Avg=151.308 MB/tok (Min=86.066 | P50=146.662 | P95=263.630 | Max=270.393 MB) | Prefill=164.704 MB/tok
   NVMe Batches / Requests      : 1988 Batches | 45982 Raw -> 43841 Merged (2141 LBA Merges, Avg 684.0 KB/io)
   SSD I/O Size Histogram       : <64K=2178 | 64K-512K=9872 | 512K-2M=31313 | >2M=478
   SSD Read Bandwidth (Active)  : Min=14.35 | Avg=594.51 | Peak=8881.01 MB/s | WallAmort=392.65 MB/s (100.0% of 571.9 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=30284.07 MB | Write=128.00 MB | Syscalls=60893
   Sync Stall vs Async DMA      : SyncStall=29274.29 ms | AsyncOverlapped=40658.90 ms (58.1% Overlapped)
   RAM Traffic & Active BW      : 622.87 GB moved | Active=16.26 GB/s (38.7% STREAM) | WallAmort=8.35 GB/s (Max=42.05 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=51.21s (68.7%, 14988.07 MB SSD) | Decode=23.38s (31.3%, 9683.72 MB SSD)
   CPU Time & Utilization       : User=121.672s + Sys=8.953s (Wall=88.195s) | SysUtil=37.0% | ThrUtil=37.0% | 82.71 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  17755.03 ms (114548.6 us/tok | 23.80%)
   MoE AVX2 Q8 Expert Compute   :  17955.10 ms (115839.3 us/tok | 24.07%)
   Router + Lookahead Dispatch  :    800.38 ms ( 5163.7 us/tok |  1.07%)
   LM Head Output Projection    :   2591.20 ms (16717.4 us/tok |  3.47%)
   Foreground NVMe Sync Stall   :  29274.29 ms (188866.4 us/tok | 39.25%)
   Unaccounted / OMP & Sampling :   6210.21 ms (40065.9 us/tok |  8.33%) | Total Wall=74586.21 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    69.11%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     8.13%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    13.58%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     6.62%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.56%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7632.57 MB (3678 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=2.61 tps | Avg=2.61 tps | Hit=90.7% | NVMe=534.0 MB/s (23425.94 MB, QD=64) | RSS=13596.1 MB
[LIVE-PREFILL] 512/512 tok | Chunk=2.65 tps | Avg=2.63 tps | Hit=90.9% | NVMe=523.7 MB/s (41144.77 MB, QD=64) | RSS=13597.3 MB
[LIVE-DECODE] 4/128 tok | Avg=1.64 tps | Hit=90.9% (LA:+0.1%) | NVMe=525.9 MB/s (42388.03 MB) | RSS=13596.9 MB
[LIVE-DECODE] 8/128 tok | Avg=1.99 tps | Hit=90.9% (LA:+0.3%) | NVMe=532.4 MB/s (43469.80 MB) | RSS=13500.9 MB
[LIVE-DECODE] 16/128 tok | Avg=2.33 tps | Hit=91.0% (LA:+0.5%) | NVMe=547.0 MB/s (45507.89 MB) | RSS=13463.2 MB
[LIVE-DECODE] 24/128 tok | Avg=2.39 tps | Hit=91.0% (LA:+0.7%) | NVMe=555.6 MB/s (47308.14 MB) | RSS=13458.2 MB
[LIVE-DECODE] 32/128 tok | Avg=2.49 tps | Hit=91.1% (LA:+0.9%) | NVMe=565.2 MB/s (48909.64 MB) | RSS=13458.2 MB
[LIVE-DECODE] 40/128 tok | Avg=2.59 tps | Hit=91.1% (LA:+1.0%) | NVMe=575.7 MB/s (50515.94 MB) | RSS=13458.2 MB
[LIVE-DECODE] 48/128 tok | Avg=2.62 tps | Hit=91.1% (LA:+1.2%) | NVMe=585.2 MB/s (52385.33 MB) | RSS=13458.2 MB
[LIVE-DECODE] 56/128 tok | Avg=2.67 tps | Hit=91.2% (LA:+1.3%) | NVMe=592.5 MB/s (53864.49 MB) | RSS=13458.2 MB
[LIVE-DECODE] 64/128 tok | Avg=2.67 tps | Hit=91.2% (LA:+1.4%) | NVMe=599.4 MB/s (55579.97 MB) | RSS=13452.0 MB
[LIVE-DECODE] 72/128 tok | Avg=2.70 tps | Hit=91.2% (LA:+1.5%) | NVMe=605.8 MB/s (56990.57 MB) | RSS=13452.0 MB
[LIVE-DECODE] 80/128 tok | Avg=2.76 tps | Hit=91.3% (LA:+1.6%) | NVMe=613.2 MB/s (58281.21 MB) | RSS=13458.2 MB
[LIVE-DECODE] 88/128 tok | Avg=2.73 tps | Hit=91.3% (LA:+1.7%) | NVMe=616.8 MB/s (59904.48 MB) | RSS=13458.1 MB
[LIVE-DECODE] 96/128 tok | Avg=2.76 tps | Hit=91.4% (LA:+1.7%) | NVMe=623.2 MB/s (61224.82 MB) | RSS=13458.1 MB
[LIVE-DECODE] 104/128 tok | Avg=2.76 tps | Hit=91.4% (LA:+1.8%) | NVMe=628.6 MB/s (62735.81 MB) | RSS=13458.1 MB
[LIVE-DECODE] 112/128 tok | Avg=2.78 tps | Hit=91.5% (LA:+1.9%) | NVMe=634.5 MB/s (64165.56 MB) | RSS=13458.1 MB
[LIVE-DECODE] 120/128 tok | Avg=2.80 tps | Hit=91.5% (LA:+2.0%) | NVMe=639.0 MB/s (65422.71 MB) | RSS=13458.1 MB
[LIVE-DECODE] 128/128 tok | Avg=2.79 tps | Hit=91.5% (LA:+2.1%) | NVMe=643.3 MB/s (67011.64 MB) | RSS=13458.1 MB

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
   LRFU Cache / Staging Ring    : 7632.57 MB (3678/25088 exp = 14.66% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.74 MB | End=13458.15 MB | Peak=14025.31 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : " layer-wise!

!

!

!

!

!

!

!

!

!

!

!

!

!

!

!!!

!

!

!!!

!

!

!

!

!

!

!

!!!

!

!

!

!

!

!

!

!

!

!

!!!

!

!!!

!

!!!

!

!!!

!

!!!

!!!!!

!!!

!!!!!

!

!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=83.4% | AvgMargin=1.017 | MinMargin=0.011
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    6000 |  layer         |   23.21 | 100.0% |   22028 |   13.32 | 194712.04 |  0 |  0 |  0 |     0.0 |
   |    2 |   42962 | -wise          |   20.97 |  99.8% |     271 |   13.36 |  441.03 |352 | 97 | 31 | 227232.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  441.03 |  0 |  0 |  0 | 227232.0 |
   |    4 |     271 | \n\n           |   14.91 |  64.2% |    1249 |   12.28 |  775.39 |126 |255 | 99 | 409321.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  775.39 |  0 |  0 |  0 | 409321.5 |
   |    6 |     271 | \n\n           |   14.60 |  51.0% |      12 |   12.47 |  479.64 |252 |172 | 56 | 307019.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  479.64 |  0 |  0 |  0 | 307019.5 |
   |    8 |     271 | \n\n           |   15.03 |  62.2% |      12 |   12.04 |  310.15 |313 |161 |  6 | 246844.5 |
   |   24 |     271 | \n\n           |   14.22 |  63.2% |     729 |   11.22 |  556.54 |335 |135 | 10 | 221519.5 |
   |   25 |       0 | !              |     nan | 100.0% |       1 |     nan |  556.54 |  0 |  0 |  0 | 221519.5 |
   |   82 |     271 | \n\n           |   14.28 |  58.8% |       0 |   13.23 |  548.21 |325 |120 | 35 | 255469.5 |
   |   83 |       0 | !              |     nan | 100.0% |       1 |     nan |  548.21 |  0 |  0 |  0 | 255469.5 |
   |  126 |     271 | \n\n           |   15.13 |  67.9% |       0 |   13.61 |  354.40 |393 | 61 | 26 | 197857.0 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  354.40 |  0 |  0 |  0 | 197857.0 |
   |  128 |     271 | \n\n           |   15.21 |  63.7% |       0 |   13.85 |  279.79 |441 | 38 |  1 | 129844.5 |
   |  129 |       0 | !              |     nan | 100.0% |       1 |     nan |  279.79 |  0 |  0 |  0 | 129844.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 194.712s, TTFT=194712.04ms): Avg=2.63 | Min=2.61 | Max=2.65 tps
   Prefill Chunks (2): C1:256t/2.6tps/91% | C2:256t/2.7tps/91%
   Decode  (128 tok, 45.886s): Avg=2.79 | Min=1.29 | Max=3.77 tps
   Latency (ms) : Min=265.33 | P10=281.82 | P25=298.65 | P50=334.58 | P75=403.00 | P90=479.64 | P95=507.82 | P99=775.39 | Max=775.39
   Mean/SD/Jitt : Mean=358.48ms | StdDev=88.59ms | Jitter=39.43ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (276480): RawRAM=247376 (89.47%) | Lookahead=5688 (+2.06%) | ColdMiss=23416 (8.47%) | EFF HIT=91.53%
   Lookahead    : 13376 prefetched -> 6328 consumed (47.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 91.0% | @64= 91.2% | @128= 91.5% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 5760 | 5054 |  65 | 641 | 88.9%|1189.31 | | L24 | 5760 | 5152 | 133 | 475 | 91.8%|1661.82 |
   | L01 | 5760 | 5151 |  65 | 544 | 90.6%|1286.21 | | L25 | 5760 | 5164 | 142 | 454 | 92.1%|1283.96 |
   | L02 | 5760 | 5183 |  33 | 544 | 90.6%|1731.74 | | L26 | 5760 | 5039 | 191 | 530 | 90.8%|1641.14 |
   | L03 | 5760 | 5343 |  33 | 384 | 93.3%|1317.80 | | L27 | 5760 | 5126 | 171 | 463 | 92.0%|1385.47 |
   | L04 | 5760 | 5287 |  25 | 448 | 92.2%|1413.21 | | L28 | 5760 | 5068 | 168 | 524 | 90.9%|1518.95 |
   | L05 | 5760 | 5204 |  49 | 507 | 91.2%|1252.00 | | L29 | 5760 | 5004 | 212 | 544 | 90.6%|1296.39 |
   | L06 | 5760 | 5131 |  47 | 582 | 89.9%|1300.88 | | L30 | 5760 | 5033 | 205 | 522 | 90.9%|1250.29 |
   | L07 | 5760 | 5131 |  84 | 545 | 90.5%|1224.68 | | L31 | 5760 | 5186 | 143 | 431 | 92.5%|1198.44 |
   | L08 | 5760 | 5220 |  78 | 462 | 92.0%| 820.53 | | L32 | 5760 | 5188 | 127 | 445 | 92.3%|1327.20 |
   | L09 | 5760 | 5224 |  80 | 456 | 92.1%| 765.75 | | L33 | 5760 | 4995 | 223 | 542 | 90.6%|1261.82 |
   | L10 | 5760 | 5179 |  96 | 485 | 91.6%| 819.29 | | L34 | 5760 | 5046 | 172 | 542 | 90.6%|1351.12 |
   | L11 | 5760 | 5160 | 127 | 473 | 91.8%| 839.21 | | L35 | 5760 | 5161 | 137 | 462 | 92.0%| 993.90 |
   | L12 | 5760 | 5155 | 109 | 496 | 91.4%|1314.04 | | L36 | 5760 | 5149 | 124 | 487 | 91.5%|1042.87 |
   | L13 | 5760 | 5041 | 198 | 521 | 91.0%|1178.27 | | L37 | 5760 | 5176 |  93 | 491 | 91.5%|1374.19 |
   | L14 | 5760 | 5099 | 182 | 479 | 91.7%|1096.17 | | L38 | 5760 | 5084 | 113 | 563 | 90.2%|1513.31 |
   | L15 | 5760 | 5333 | 117 | 310 | 94.6%|1079.05 | | L39 | 5760 | 5237 |  89 | 434 | 92.5%|1263.28 |
   | L16 | 5760 | 5223 | 178 | 359 | 93.8%|1259.52 | | L40 | 5760 | 5254 |  85 | 421 | 92.7%|1075.29 |
   | L17 | 5760 | 5050 | 215 | 495 | 91.4%|1537.74 | | L41 | 5760 | 5161 |  92 | 507 | 91.2%| 993.90 |
   | L18 | 5760 | 5128 | 112 | 520 | 91.0%|1627.98 | | L42 | 5760 | 5154 | 104 | 502 | 91.3%|1165.31 |
   | L19 | 5760 | 5107 | 201 | 452 | 92.2%|1107.69 | | L43 | 5760 | 5256 |  84 | 420 | 92.7%| 898.83 |
   | L20 | 5760 | 5066 | 201 | 493 | 91.4%|1218.60 | | L44 | 5760 | 5190 |  64 | 506 | 91.2%|1114.89 |
   | L21 | 5760 | 5083 | 128 | 549 | 90.5%|1518.95 | | L45 | 5760 | 5219 |  68 | 473 | 91.8%| 980.93 |
   | L22 | 5760 | 5084 | 112 | 564 | 90.2%|1635.50 | | L46 | 5760 | 5271 |  56 | 433 | 92.5%| 978.05 |
   | L23 | 5760 | 5233 | 120 | 407 | 92.9%| 969.41 | | L47 | 5760 | 5194 |  37 | 529 | 90.8%|1097.85 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 67011.64 MB (Load=4614.69 | Prefill=36530.07 | Warmup=0.00 | Decode=25866.87 MB)
   SSD Data/Token (Decode)      : Avg=202.085 MB/tok (Min=124.848 | P50=198.579 | P95=269.733 | Max=399.728 MB) | Prefill=71.348 MB/tok
   NVMe Batches / Requests      : 5153 Batches | 120700 Raw -> 115580 Merged (5120 LBA Merges, Avg 593.7 KB/io)
   SSD I/O Size Histogram       : <64K=9473 | 64K-512K=26750 | 512K-2M=78754 | >2M=603
   SSD Read Bandwidth (Active)  : Min=7.98 | Avg=643.31 | Peak=10614.81 MB/s | WallAmort=278.52 MB/s
   OS Kernel I/O Verification   : Read=67031.77 MB | Write=0.00 MB | Syscalls=125096
   Sync Stall vs Async DMA      : SyncStall=71219.04 ms | AsyncOverlapped=95667.92 ms (57.3% Overlapped)
   RAM Traffic & Active BW      : 2072.99 GB moved | Active=13.66 GB/s | WallAmort=8.62 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=194.71s (80.9%, 36530.07 MB SSD) | Decode=45.89s (19.1%, 25866.87 MB SSD)
   CPU Time & Utilization       : User=521.156s + Sys=19.344s (Wall=253.478s) | SysUtil=53.3% | ThrUtil=53.3% | 49.31 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  69601.34 ms (108752.1 us/tok | 28.93%)
   MoE AVX2 Q8 Expert Compute   :  77063.52 ms (120411.7 us/tok | 32.03%)
   Router + Lookahead Dispatch  :   3480.69 ms ( 5438.6 us/tok |  1.45%)
   LM Head Output Projection    :   5087.50 ms ( 7949.2 us/tok |  2.11%)
   Foreground NVMe Sync Stall   :  71219.04 ms (111279.8 us/tok | 29.60%)
   Unaccounted / OMP & Sampling :  14146.01 ms (22103.1 us/tok |  5.88%) | Total Wall=240598.10 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    78.44%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.77%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     7.17%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     6.22%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.40%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 28099.6ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\n\n<think>\nThe user is asking me to summarize "LBA-coalesced'
[Stage 3] /v1/chat/completions (stream=true SSE) 9278.7ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=5978.64 MB (2881 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2.70 tps | Avg=2.70 tps | Hit=90.7% | NVMe=542.5 MB/s (23425.94 MB, QD=64) | RSS=11948.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.71 tps | Avg=2.71 tps | Hit=90.6% | NVMe=548.8 MB/s (42324.09 MB, QD=64) | RSS=11969.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.70 tps | Avg=2.71 tps | Hit=90.6% | NVMe=554.9 MB/s (61641.39 MB, QD=64) | RSS=11973.0 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.70 tps | Avg=2.70 tps | Hit=90.5% | NVMe=558.8 MB/s (80842.50 MB, QD=64) | RSS=11973.6 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.73 tps | Avg=2.71 tps | Hit=90.6% | NVMe=560.9 MB/s (99081.85 MB, QD=64) | RSS=11973.3 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.76 tps | Avg=2.72 tps | Hit=90.7% | NVMe=563.0 MB/s (116639.63 MB, QD=64) | RSS=11973.1 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.74 tps | Avg=2.72 tps | Hit=90.8% | NVMe=564.5 MB/s (134582.25 MB, QD=64) | RSS=11973.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.72 tps | Avg=2.72 tps | Hit=90.8% | NVMe=565.8 MB/s (152636.55 MB, QD=64) | RSS=11974.2 MB
[LIVE-DECODE] 4/64 tok | Avg=1.38 tps | Hit=90.8% (LA:+0.0%) | NVMe=566.3 MB/s (154194.41 MB) | RSS=11976.8 MB
[LIVE-DECODE] 8/64 tok | Avg=1.77 tps | Hit=90.8% (LA:+0.1%) | NVMe=568.4 MB/s (155393.27 MB) | RSS=11972.6 MB
[LIVE-DECODE] 16/64 tok | Avg=2.23 tps | Hit=90.8% (LA:+0.2%) | NVMe=574.7 MB/s (157754.41 MB) | RSS=11972.4 MB
[LIVE-DECODE] 24/64 tok | Avg=2.47 tps | Hit=90.9% (LA:+0.2%) | NVMe=581.2 MB/s (160104.02 MB) | RSS=11972.1 MB
[LIVE-DECODE] 32/64 tok | Avg=2.58 tps | Hit=90.9% (LA:+0.3%) | NVMe=587.1 MB/s (162401.76 MB) | RSS=11969.9 MB
[LIVE-DECODE] 40/64 tok | Avg=2.67 tps | Hit=90.9% (LA:+0.4%) | NVMe=592.7 MB/s (164527.47 MB) | RSS=11960.4 MB
[LIVE-DECODE] 48/64 tok | Avg=2.75 tps | Hit=90.9% (LA:+0.5%) | NVMe=598.5 MB/s (166627.80 MB) | RSS=11955.8 MB
[LIVE-DECODE] 56/64 tok | Avg=2.83 tps | Hit=90.9% (LA:+0.5%) | NVMe=603.9 MB/s (168477.02 MB) | RSS=11955.8 MB
[LIVE-DECODE] 64/64 tok | Avg=2.89 tps | Hit=90.9% (LA:+0.6%) | NVMe=608.8 MB/s (170230.57 MB) | RSS=11955.8 MB

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
   LRFU Cache / Staging Ring    : 5978.64 MB (2881/25088 exp = 11.48% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.74 MB | End=11955.75 MB | Peak=12372.99 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : " layer-wise!

!

!

!

!

!

!

!!!

!

!

!!!

!

!

!!!

!

!

!

!

!

!

!

!

!

!

!

!

!

!

!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=82.7% | AvgMargin=0.866 | MinMargin=0.129
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    6000 |  layer         |   21.89 |  99.5% |     271 |   16.32 | 753264.10 |  0 |  0 |  0 |     0.0 |
   |    2 |   42962 | -wise          |   22.34 |  99.5% |     271 |   16.47 |  518.81 |341 | 86 | 53 | 277694.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  518.81 |  0 |  0 |  0 | 277694.5 |
   |    4 |     271 | \n\n           |   16.51 |  89.2% |      12 |   11.88 |  928.76 | 27 |322 |131 | 519934.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  928.76 |  0 |  0 |  0 | 519934.0 |
   |    6 |     271 | \n\n           |   15.91 |  81.7% |  248046 |   12.04 |  482.67 |240 |192 | 48 | 329444.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  482.67 |  0 |  0 |  0 | 329444.5 |
   |    8 |     271 | \n\n           |   15.66 |  75.8% |       0 |   13.24 |  331.25 |301 |174 |  5 | 284369.5 |
   |   26 |       0 | !              |   15.65 |  63.7% |     271 |   14.82 |  401.20 |251 |212 | 17 | 324182.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  401.20 |  0 |  0 |  0 | 324182.0 |
   |   34 |       0 | !              |   16.39 |  64.6% |     271 |   15.58 |  377.50 |284 |190 |  6 | 290744.5 |
   |   35 |       0 | !              |     nan | 100.0% |       1 |     nan |  377.50 |  0 |  0 |  0 | 290744.5 |
   |   62 |     271 | \n\n           |   14.68 |  48.3% |       0 |   14.40 |  288.20 |363 |117 |  0 | 228707.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  288.20 |  0 |  0 |  0 | 228707.0 |
   |   64 |     271 | \n\n           |   14.92 |  60.9% |       0 |   13.88 |  290.14 |361 |119 |  0 | 217182.0 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  290.14 |  0 |  0 |  0 | 217182.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 753.264s, TTFT=753264.10ms): Avg=2.72 | Min=2.70 | Max=2.76 tps
   Prefill Chunks (8): C1:256t/2.7tps/91% | C2:256t/2.7tps/91% | C3:256t/2.7tps/91% | C4:256t/2.7tps/91%
                       C5:256t/2.7tps/91% | C6:256t/2.8tps/91% | C7:256t/2.7tps/91% | C8:256t/2.7tps/91%
   Decode  (64 tok, 22.112s): Avg=2.89 | Min=1.08 | Max=3.52 tps
   Latency (ms) : Min=284.30 | P10=288.20 | P25=298.14 | P50=312.81 | P75=334.86 | P90=401.20 | P95=518.81 | P99=928.76 | Max=928.76
   Mean/SD/Jitt : Mean=345.50ms | StdDev=117.18ms | Jitter=27.07ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (998400): RawRAM=902365 (90.38%) | Lookahead=5552 (+0.56%) | ColdMiss=90483 (9.06%) | EFF HIT=90.94%
   Lookahead    : 9730 prefetched -> 5872 consumed (60.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.8% | @64= 90.9% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |20800 |18000 | 221 |2579 | 87.6%|4716.80 | | L24 |20800 |18904 |  96 |1800 | 91.3%|3836.84 |
   | L01 |20800 |18386 | 153 |2261 | 89.1%|3242.29 | | L25 |20800 |18654 |  99 |2047 | 90.2%|4105.66 |
   | L02 |20800 |18270 | 139 |2391 | 88.5%|4642.68 | | L26 |20800 |18790 | 114 |1896 | 90.9%|3908.28 |
   | L03 |20800 |18782 | 139 |1879 | 91.0%|4116.94 | | L27 |20800 |18757 | 135 |1908 | 90.8%|3966.55 |
   | L04 |20800 |19086 |  69 |1645 | 92.1%|3691.77 | | L28 |20800 |18939 | 121 |1740 | 91.6%|3641.33 |
   | L05 |20800 |18626 | 117 |2057 | 90.1%|4254.17 | | L29 |20800 |18831 | 118 |1851 | 91.1%|2926.95 |
   | L06 |20800 |18489 |  70 |2241 | 89.2%|4466.60 | | L30 |20800 |18530 |  99 |2171 | 89.6%|3361.96 |
   | L07 |20800 |18481 | 171 |2148 | 89.7%|4002.54 | | L31 |20800 |18954 | 105 |1741 | 91.6%|2818.92 |
   | L08 |20800 |18879 | 151 |1770 | 91.5%|2482.76 | | L32 |20800 |18885 |  76 |1839 | 91.2%|3701.49 |
   | L09 |20800 |18947 | 141 |1712 | 91.8%|2355.76 | | L33 |20800 |18671 |  93 |2036 | 90.2%|3141.58 |
   | L10 |20800 |19009 | 127 |1664 | 92.0%|2287.28 | | L34 |20800 |18845 |  97 |1858 | 91.1%|2944.24 |
   | L11 |20800 |18986 | 152 |1662 | 92.0%|2315.92 | | L35 |20800 |18905 |  75 |1820 | 91.2%|2787.23 |
   | L12 |20800 |18960 | 196 |1644 | 92.1%|3577.42 | | L36 |20800 |18939 | 122 |1739 | 91.6%|2788.67 |
   | L13 |20800 |19103 | 148 |1549 | 92.6%|2517.87 | | L37 |20800 |18843 | 111 |1846 | 91.1%|3789.84 |
   | L14 |20800 |18857 | 146 |1797 | 91.4%|2908.23 | | L38 |20800 |18699 |  84 |2017 | 90.3%|4032.35 |
   | L15 |20800 |18994 | 147 |1659 | 92.0%|3556.74 | | L39 |20800 |19000 | 100 |1700 | 91.8%|3628.17 |
   | L16 |20800 |18877 | 158 |1765 | 91.5%|3780.44 | | L40 |20800 |18876 |  57 |1867 | 91.0%|3720.29 |
   | L17 |20800 |18855 | 138 |1807 | 91.3%|3780.44 | | L41 |20800 |18550 |  56 |2194 | 89.5%|3325.95 |
   | L18 |20800 |18877 | 138 |1785 | 91.4%|3772.92 | | L42 |20800 |18738 |  55 |2007 | 90.4%|3128.61 |
   | L19 |20800 |18796 | 148 |1856 | 91.1%|3009.06 | | L43 |20800 |18919 |  67 |1814 | 91.3%|2839.09 |
   | L20 |20800 |18625 | 156 |2019 | 90.3%|3271.22 | | L44 |20800 |18846 |  54 |1900 | 90.9%|2952.88 |
   | L21 |20800 |18992 | 154 |1654 | 92.0%|3541.70 | | L45 |20800 |18810 |  62 |1928 | 90.7%|2974.49 |
   | L22 |20800 |18965 | 127 |1708 | 91.8%|3645.09 | | L46 |20800 |19243 |  31 |1526 | 92.7%|2388.23 |
   | L23 |20800 |18753 | 144 |1903 | 90.9%|3112.77 | | L47 |20800 |18642 |  75 |2083 | 90.0%|4130.10 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 170230.57 MB (Load=4614.69 | Prefill=148021.85 | Warmup=0.00 | Decode=17594.02 MB)
   SSD Data/Token (Decode)      : Avg=274.907 MB/tok (Min=212.092 | P50=276.752 | P95=321.723 | Max=507.748 MB) | Prefill=72.276 MB/tok
   NVMe Batches / Requests      : 4555 Batches | 335027 Raw -> 315323 Merged (19704 LBA Merges, Avg 552.8 KB/io)
   SSD I/O Size Histogram       : <64K=33329 | 64K-512K=70618 | 512K-2M=210244 | >2M=1132
   SSD Read Bandwidth (Active)  : Min=10.87 | Avg=608.84 | Peak=11712.67 MB/s | WallAmort=219.55 MB/s
   OS Kernel I/O Verification   : Read=170251.11 MB | Write=0.00 MB | Syscalls=324837
   Sync Stall vs Async DMA      : SyncStall=261664.34 ms | AsyncOverlapped=271199.69 ms (50.9% Overlapped)
   RAM Traffic & Active BW      : 5562.56 GB moved | Active=11.25 GB/s | WallAmort=7.17 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=753.26s (97.1%, 148021.85 MB SSD) | Decode=22.11s (2.9%, 17594.02 MB SSD)
   CPU Time & Utilization       : User=1814.734s + Sys=40.984s (Wall=787.420s) | SysUtil=58.9% | ThrUtil=58.9% | 54.50 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 224192.95 ms (106152.0 us/tok | 28.91%)
   MoE AVX2 Q8 Expert Compute   : 267919.48 ms (126855.8 us/tok | 34.55%)
   Router + Lookahead Dispatch  :  11828.13 ms ( 5600.4 us/tok |  1.53%)
   LM Head Output Projection    :   2484.71 ms ( 1176.5 us/tok |  0.32%)
   Foreground NVMe Sync Stall   : 261664.34 ms (123894.1 us/tok | 33.75%)
   Unaccounted / OMP & Sampling :   7286.27 ms ( 3449.9 us/tok |  0.94%) | Total Wall=775375.87 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    82.58%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.35%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     6.05%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.53%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.49%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=65.0s | Competitor drastic-underperform cutoff=325.0s (5x Apex)
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=325.0s) ===
  [Colibri-Qwen38] [gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
  [Colibri-Qwen38] [gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
  [Colibri-Qwen38] == Qwen3.8-Flash-Next native text engine | cache=72/layer | CPU ==
  [Colibri-Qwen38] [tok] loaded 248320 base pieces + 33 added tokens (max id 248319) from D:/apex_d_drive/models/qwen38/tokenizer.json
  [Colibri-Qwen38] [qwen38] native text weights: prefix=model, 48 layers, PLE=1, cache=72/layer, FP8=native, BF16=native (resident matrices 4.40 GiB)
  [Colibri-Qwen38] [qwen38] MTP head mtp.*: wiring b (a norm per stream, fc_hidden per stream), RoPE base 1e+07, 96.86 MiB resident; routed experts Q8_0 from the snapshot (its own GGUF), cache 72 (Q38_MTP_CAP) x 4.98 MiB = 0.35 GiB full
  [Colibri-Qwen38] [qwen38] MTP norm weights, mean: embedding -0.7642, hidden -0.3284, mixer 3.7881 (q38_rms0 scales by 1+w; a plain norm's weights would sit near 1)
  [Colibri-Qwen38] [qwen38] trunk: 62 matrices int8 on the CPU (0.08 GiB, 0.28 GiB of BF16 released) in 0.3s; Q38_TRUNK_CPU_INT8=0 keeps BF16
  [Colibri-Qwen38] [qwen38 MTP] draft vocabulary: the lm_head has no int8 rows on the host, so the head scores the whole vocabulary (Q38_MTP_VOCAB=0 silences this)
  [Colibri-Qwen38] [qwen38] routed experts: GGUF IQ2_XXS/IQ2_XXS/IQ4_NL (layer 0), 1.68 MiB per expert; cache 72/layer
  [Colibri-Qwen38] [qwen38] trunk: 62 int8 matrices interleaved by 16 for the CPU in 0.02s (Q38_ILV16=0 keeps the rows)
  [Colibri-Qwen38] resident weights loaded in 9.6s | RSS after load: 4.60 GB
  [Colibri-Qwen38] [qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=325.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.0s / cutoff=325.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=325.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=60.1s / cutoff=325.0s
  [Colibri-Qwen38] TTFT: 25.68 s (time to first token)
  [Colibri-Qwen38] [qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
  [Colibri-Qwen38] [qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
  [Colibri-Qwen38] [qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes
  [Colibri-Qwen38] 
  [Colibri-Qwen38] PEAK RSS: 10.73 GB
  [Colibri-Qwen38] Expert cache hit rate: 62.0% (hit=15849 miss=9733)
  [Colibri-Qwen38] Speed: 0.66 tok/s (48.8s for 32 tokens)
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
=== [Colibri-Qwen38] Finished rc=1 elapsed=61.15s cancelled=False ===
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 1.70 | 2.64 | 350.58 | 82.94% | 590.72 | 13550.32 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 2.63 | 2.79 | 334.58 | 91.53% | 643.31 | 14025.31 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.72 | 2.89 | 312.81 | 90.94% | 608.84 | 12372.99 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.66 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 865K Nov 13 15:21 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 865K Nov 13 15:21 build/apex.exe
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
   SEQ1M Direct Uncached NVMe Read    :    592.49 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2503.10 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9762.35 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11205.76 MB/s
   RND4K Q32T16 Read                  :    715.00 MB/s (  183041 IOPS)
   RND4K Q1T1  Read                   :    862.37 MB/s (Latency: 4.53 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     64.10 GB/s
   AVX2 256-bit Sequential Write BW   :     62.84 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.01 GB/s
   Random Pointer-Chase Latency       :     97.87 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.41 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    225.82 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     27.27 GB/s (FP32 Equiv)
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
[Apex-Parity] Serial  Tokens (16) : [49, 193, 68, 63, 223, 193, 128, 49, 49, 66, 67, 19, 49, 18, 49, 18] -> "qtok_49qtok_193qtok_68qtok_63qtok_223qtok_193qtok_128qtok_49qtok_49qtok_66qtok_67qtok_19qtok_49qtok_18qtok_49qtok_18"
[Apex-Parity] Batched Tokens (16) : [49, 193, 68, 63, 223, 193, 128, 49, 49, 66, 67, 19, 49, 18, 49, 18] -> "qtok_49qtok_193qtok_68qtok_63qtok_223qtok_193qtok_128qtok_49qtok_49qtok_66qtok_67qtok_19qtok_49qtok_18qtok_49qtok_18"
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] GLM-5.3-Flash 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_glm53_ud_iq2_xxs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=1.93 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1803.18 tps | Avg=1803.18 tps | Hit=99.5% | NVMe=2801.9 MB/s (6.19 MB, QD=64) | RSS=71.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1652.54 tps | Avg=1724.58 tps | Hit=99.5% | NVMe=2645.3 MB/s (7.01 MB, QD=64) | RSS=71.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1442.08 tps | Avg=1618.87 tps | Hit=99.5% | NVMe=2548.5 MB/s (7.78 MB, QD=64) | RSS=71.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1258.09 tps | Avg=1510.57 tps | Hit=99.5% | NVMe=2314.0 MB/s (8.61 MB, QD=64) | RSS=72.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1145.36 tps | Avg=1420.02 tps | Hit=99.5% | NVMe=2282.9 MB/s (9.33 MB, QD=64) | RSS=72.2 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1022.81 tps | Avg=1333.69 tps | Hit=99.5% | NVMe=2248.6 MB/s (10.06 MB, QD=64) | RSS=72.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=940.06 tps | Avg=1258.42 tps | Hit=99.5% | NVMe=2221.7 MB/s (10.83 MB, QD=64) | RSS=72.7 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=866.10 tps | Avg=1190.98 tps | Hit=99.5% | NVMe=2164.7 MB/s (11.60 MB, QD=64) | RSS=73.0 MB
[LIVE-DECODE] 8/32 tok | Avg=259.13 tps | Hit=99.5% (LA:+0.0%) | NVMe=2121.8 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=263.24 tps | Hit=99.5% (LA:+0.1%) | NVMe=2084.5 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=265.47 tps | Hit=99.5% (LA:+0.1%) | NVMe=2058.4 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=265.82 tps | Hit=99.5% (LA:+0.1%) | NVMe=2047.7 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=73.07 MB | Peak=73.07 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1719.59 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    3.97 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    3.97 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    3.94 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    3.94 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    3.81 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    3.81 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    3.71 | 11 |  1 |  0 |    49.5 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    3.78 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    3.78 |  0 |  0 |  0 |   173.2 |
   |   14 |     220 | tok_220        |  147.52 |  55.4% |      55 |  147.01 |    3.76 |  9 |  3 |  0 |   173.2 |
   |   15 |     197 | tok_197        |   65.84 |  97.8% |     133 |   62.03 |    3.76 |  0 |  0 |  0 |   173.2 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    3.82 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    3.82 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    3.75 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    3.75 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.720s, TTFT=1719.59ms): Avg=1190.98 | Min=866.10 | Max=1803.18 tps
   Prefill Chunks (8): C1:256t/1803.2tps/99% | C2:256t/1652.5tps/99% | C3:256t/1442.1tps/99% | C4:256t/1258.1tps/99%
                       C5:256t/1145.4tps/99% | C6:256t/1022.8tps/99% | C7:256t/940.1tps/99% | C8:256t/866.1tps/99%
   Decode  (32 tok, 0.120s): Avg=265.82 | Min=251.60 | Max=271.96 tps
   Latency (ms) : Min=3.68 | P10=3.70 | P25=3.71 | P50=3.72 | P75=3.81 | P90=3.94 | P95=3.97 | P99=3.97 | Max=3.97
   Mean/SD/Jitt : Mean=3.76ms | StdDev=0.08ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=442.67 | Avg=2047.70 | Peak=7022.47 MB/s | WallAmort=7.23 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=4.57 ms | AsyncOverlapped=5.45 ms (54.4% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.82 GB/s | WallAmort=0.78 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.72s (93.5%, 6.19 MB SSD) | Decode=0.12s (6.5%, 1.69 MB SSD)
   CPU Time & Utilization       : User=2.312s + Sys=0.469s (Wall=1.857s) | SysUtil=37.5% | ThrUtil=37.5% | 34.64 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1549.56 ms (  745.0 us/tok | 84.22%)
   MoE AVX2 Q8 Expert Compute   :    187.03 ms (   89.9 us/tok | 10.16%)
   Router + Lookahead Dispatch  :     47.83 ms (   23.0 us/tok |  2.60%)
   LM Head Output Projection    :      4.43 ms (    2.1 us/tok |  0.24%)
   Foreground NVMe Sync Stall   :      4.57 ms (    2.2 us/tok |  0.25%)
   Unaccounted / OMP & Sampling :     46.55 ms (   22.4 us/tok |  2.53%) | Total Wall=1839.97 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    23.77%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.21%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.46%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    71.22%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.34%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2597.45 tps | Avg=2597.45 tps | Hit=99.2% | NVMe=3306.4 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2541.26 tps | Avg=2569.05 tps | Hit=99.2% | NVMe=4338.9 MB/s (42.92 MB, QD=64) | RSS=89.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2247.75 tps | Avg=2452.20 tps | Hit=99.2% | NVMe=4904.3 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2163.13 tps | Avg=2372.93 tps | Hit=99.2% | NVMe=5269.9 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2055.19 tps | Avg=2301.76 tps | Hit=99.2% | NVMe=5573.4 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1893.63 tps | Avg=2221.94 tps | Hit=99.2% | NVMe=5793.9 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1675.73 tps | Avg=2123.08 tps | Hit=99.2% | NVMe=5942.9 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1658.94 tps | Avg=2051.34 tps | Hit=99.2% | NVMe=6109.4 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=242.37 tps | Hit=99.2% (LA:+0.0%) | NVMe=5991.6 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=245.26 tps | Hit=99.2% (LA:+0.1%) | NVMe=5930.0 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=245.72 tps | Hit=99.2% (LA:+0.1%) | NVMe=5830.0 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=245.91 tps | Hit=99.2% (LA:+0.1%) | NVMe=5750.4 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=91.71 MB | Peak=91.71 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_129qtok_68qtok_209qtok_223qtok_113qtok_229qtok_112qtok_193qtok_63qtok_128qtok_63qtok_128qtok_63qtok_194qtok_49qtok_49qtok_148qtok_254qtok_48qtok_254qtok_49"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=93.4% | AvgMargin=10.261 | MinMargin=0.202
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 |  998.37 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    4.19 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    4.19 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    4.14 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    4.14 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    4.11 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    4.11 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    4.06 | 16 |  0 |  0 |    32.0 |
   |   26 |     194 | qtok_194       |   71.13 | 100.0% |       2 |   54.96 |    4.07 | 12 |  4 |  0 |   147.0 |
   |   27 |      49 | qtok_49        |   67.58 |  99.9% |     209 |   61.01 |    4.07 |  0 |  0 |  0 |   147.0 |
   |   20 |     193 | qtok_193       |   68.69 | 100.0% |      17 |   59.53 |    4.07 | 14 |  2 |  0 |    87.5 |
   |   21 |      63 | qtok_63        |   75.06 |  99.9% |     193 |   67.57 |    4.07 |  0 |  0 |  0 |    87.5 |
   |   30 |     254 | qtok_254       |   58.92 |  92.7% |      49 |   56.39 |    4.06 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    4.06 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.75 |  64.8% |     229 |   52.56 |    4.04 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    4.04 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 0.998s, TTFT=998.37ms): Avg=2051.34 | Min=1658.94 | Max=2597.45 tps
   Prefill Chunks (8): C1:256t/2597.5tps/99% | C2:256t/2541.3tps/99% | C3:256t/2247.7tps/99% | C4:256t/2163.1tps/99%
                       C5:256t/2055.2tps/99% | C6:256t/1893.6tps/99% | C7:256t/1675.7tps/99% | C8:256t/1658.9tps/99%
   Decode  (32 tok, 0.130s): Avg=245.91 | Min=238.62 | Max=249.45 tps
   Latency (ms) : Min=4.01 | P10=4.02 | P25=4.04 | P50=4.06 | P75=4.07 | P90=4.14 | P95=4.19 | P99=4.19 | Max=4.19
   Mean/SD/Jitt : Mean=4.07ms | StdDev=0.04ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=446.08 | Avg=5750.41 | Peak=10546.52 MB/s | WallAmort=137.47 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=6.43 ms | AsyncOverlapped=25.74 ms (80.0% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=2.15 GB/s | WallAmort=1.86 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.00s (88.5%, 144.44 MB SSD) | Decode=0.13s (11.5%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.078s + Sys=0.312s (Wall=1.157s) | SysUtil=51.7% | ThrUtil=51.7% | 47.79 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    688.39 ms (  331.0 us/tok | 61.00%)
   MoE AVX2 Q8 Expert Compute   :    286.33 ms (  137.7 us/tok | 25.37%)
   Router + Lookahead Dispatch  :     63.27 ms (   30.4 us/tok |  5.61%)
   LM Head Output Projection    :      4.20 ms (    2.0 us/tok |  0.37%)
   Foreground NVMe Sync Stall   :      6.43 ms (    3.1 us/tok |  0.57%)
   Unaccounted / OMP & Sampling :     79.88 ms (   38.4 us/tok |  7.08%) | Total Wall=1128.50 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    20.63%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.02%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.24%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    65.48%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.63%  |
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
    "ttft_ms": 172.54,
    "avg_tps": 950.51,
    "min_tps": 785.51,
    "max_tps": 1073.85
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 202.26,
    "min_tps": 181.68,
    "max_tps": 208.94,
    "p50_ms": 4.91,
    "p90_ms": 5.17,
    "p99_ms": 5.5,
    "mean_ms": 4.94,
    "jitter_ms": 0.12
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
    "avg_mbs": 2177.27,
    "peak_mbs": 6578.95,
    "sync_wait_ms": 1.6,
    "async_overlap_ms": 2.83
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
    "dense_attention": 272.65,
    "moe_compute": 75.33,
    "router_lookahead": 5.8,
    "lm_head": 6.02,
    "unaccounted": 3.96
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 81.92,
    "ram_bandwidth_pinning": 2.52,
    "expert_cache_lrfu": 12.07,
    "lookahead_parallel_overlap": 2.25,
    "ssd_nvme_throughput": 1.24,
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
    "ttft_ms": 218.91,
    "avg_tps": 749.17,
    "min_tps": 533.79,
    "max_tps": 852.19
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 178.58,
    "min_tps": 172.02,
    "max_tps": 182.76,
    "p50_ms": 5.59,
    "p90_ms": 5.73,
    "p99_ms": 5.81,
    "mean_ms": 5.6,
    "jitter_ms": 0.06
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
    "avg_mbs": 2926.17,
    "peak_mbs": 7508.48,
    "sync_wait_ms": 4.16,
    "async_overlap_ms": 11.41
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
    "dense_attention": 246.73,
    "moe_compute": 142.31,
    "router_lookahead": 7.08,
    "lm_head": 6.02,
    "unaccounted": 31.01
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 78.4,
    "ram_bandwidth_pinning": 2.91,
    "expert_cache_lrfu": 10.21,
    "lookahead_parallel_overlap": 5.19,
    "ssd_nvme_throughput": 3.29,
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
Host CPU: AMD EPYC 9V74 80-Core Processor | Cores=2 Threads=4 | RAM=15.99 GB
--- winsat disk -seq -read -drive c ---
Windows System Assessment Tool
Error: Unable to run inside of a Virtual Machine.  Please try again running directly on the native hardware.
--- winsat disk -seq -read -drive d ---
Windows System Assessment Tool
Error: Unable to run inside of a Virtual Machine.  Please try again running directly on the native hardware.
--- winsat disk -ran -read -drive d ---
Windows System Assessment Tool
Error: Unable to run inside of a Virtual Machine.  Please try again running directly on the native hardware.
--- winsat mem ---
Windows System Assessment Tool
Error: Unable to run inside of a Virtual Machine.  Please try again running directly on the native hardware.
```

### 📄 `04_qwen38_stage1_parity.log`
```text
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (4) : [17, 21, 25, 17] -> "26:2"
[Apex-Parity] Batched Tokens (4) : [17, 21, 25, 17] -> "26:2"
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
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 14.69 GB Available
   Active Drive Space : 219.98 GB Total / 149.17 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    571.91 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2260.23 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9365.56 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10504.16 MB/s
   RND4K Q32T16 Read                  :    624.41 MB/s (  159850 IOPS)
   RND4K Q1T1  Read                   :    742.91 MB/s (Latency: 5.26 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     66.81 GB/s
   AVX2 256-bit Sequential Write BW   :     59.56 GB/s
   STREAM Triad (A = B + s*C) BW      :     42.05 GB/s
   Random Pointer-Chase Latency       :    102.93 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.40 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    223.39 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.21 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=1.78 tps | Avg=1.78 tps | Hit=79.2% | NVMe=534.1 MB/s (19602.76 MB, QD=64) | RSS=13615.7 MB

 >>> [Apex-Model-Response] <think>
!
!
!<|im_end|>!<|im_end|>!
!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   LRFU Cache / Staging Ring    : 7676.15 MB (3699/25088 exp = 14.74% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.70 MB | End=13502.75 MB | Peak=14018.57 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "<think>
!
!
!<|im_end|>!<|im_end|>!
!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=73.5% | AvgMargin=1.204 | MinMargin=0.120
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |  248068 | <think>        |   32.95 | 100.0% |  248045 |   12.90 | 51210.59 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |   21.79 |  63.4% |     271 |   21.24 |  318.78 |392 | 84 |  4 | 122932.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  318.78 |  0 |  0 |  0 | 122932.0 |
   |    4 |     198 | \n             |   12.40 |  23.4% |     271 |   12.06 |  478.98 |378 | 87 | 15 | 156682.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  478.98 |  0 |  0 |  0 | 156682.0 |
   |    6 |     198 | \n             |   12.62 |  21.8% |  248046 |   12.50 |  363.30 |409 | 64 |  7 | 128584.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  363.30 |  0 |  0 |  0 | 128584.0 |
   |    8 |  248046 | <|im_end|>     |   13.00 |  28.4% |     198 |   12.13 |  506.17 |437 | 42 |  1 | 107957.0 |
   |   26 |       0 | !              |   13.54 |  54.3% |     198 |   10.71 |  536.46 |318 |103 | 59 | 269957.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  536.46 |  0 |  0 |  0 | 269957.0 |
   |   18 |       0 | !              |   13.85 |  46.9% |     198 |   12.04 |  530.02 |296 |115 | 69 | 276882.0 |
   |   19 |       0 | !              |     nan | 100.0% |       1 |     nan |  530.02 |  0 |  0 |  0 | 276882.0 |
   |   62 |       0 | !              |   15.17 |  81.0% |     198 |   11.37 |  335.24 |420 | 52 |  8 | 175869.5 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  335.24 |  0 |  0 |  0 | 175869.5 |
   |   64 |       0 | !              |   13.02 |  35.5% |     198 |   11.60 |  353.97 |396 | 62 | 22 | 179119.5 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  353.97 |  0 |  0 |  0 | 179119.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 51.211s, TTFT=51210.59ms): Avg=1.78 | Min=1.78 | Max=1.78 tps
   Prefill Chunks (1): C1:91t/1.8tps/79%
   Decode  (64 tok, 23.376s): Avg=2.74 | Min=1.86 | Max=3.81 tps
   Latency (ms) : Min=262.16 | P10=293.92 | P25=324.25 | P50=353.97 | P75=396.20 | P90=478.98 | P95=530.02 | P99=536.46 | Max=536.46
   Mean/SD/Jitt : Mean=365.24ms | StdDev=72.39ms | Jitter=43.40ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (59040): RawRAM=47708 (80.81%) | Lookahead=1809 (+3.06%) | ColdMiss=9523 (16.13%) | EFF HIT=83.87%
   Lookahead    : 4779 prefetched -> 2129 consumed (44.5% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 80.8% | @64= 83.9% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1230 |  888 |  28 | 314 | 74.5%| 576.12 | | L24 | 1230 |  999 |  52 | 179 | 85.4%| 539.53 |
   | L01 | 1230 |  966 |  10 | 254 | 79.3%| 636.25 | | L25 | 1230 |  955 |  71 | 204 | 83.4%| 571.48 |
   | L02 | 1230 |  973 |  14 | 243 | 80.2%| 651.93 | | L26 | 1230 |  942 |  83 | 205 | 83.3%| 637.28 |
   | L03 | 1230 | 1068 |  10 | 152 | 87.6%| 590.28 | | L27 | 1230 |  966 |  80 | 184 | 85.0%| 582.76 |
   | L04 | 1230 | 1010 |  11 | 209 | 83.0%| 742.92 | | L28 | 1230 |  928 |  69 | 233 | 81.1%| 667.36 |
   | L05 | 1230 |  993 |  13 | 224 | 81.8%| 462.45 | | L29 | 1230 |  946 |  92 | 192 | 84.4%| 468.14 |
   | L06 | 1230 |  963 |  10 | 257 | 79.1%| 528.25 | | L30 | 1230 |  924 |  84 | 222 | 82.0%| 517.11 |
   | L07 | 1230 |  979 |  18 | 233 | 81.1%| 426.20 | | L31 | 1230 | 1031 |  36 | 163 | 86.7%| 420.61 |
   | L08 | 1230 | 1055 |  11 | 164 | 86.7%| 226.61 | | L32 | 1230 | 1006 |  45 | 179 | 85.4%| 498.17 |
   | L09 | 1230 | 1037 |  17 | 176 | 85.7%| 247.78 | | L33 | 1230 |  931 |  93 | 206 | 83.3%| 486.87 |
   | L10 | 1230 | 1030 |  16 | 184 | 85.0%| 260.23 | | L34 | 1230 |  979 |  52 | 199 | 83.8%| 515.67 |
   | L11 | 1230 | 1049 |  18 | 163 | 86.7%| 254.00 | | L35 | 1230 |  994 |  63 | 173 | 85.9%| 394.68 |
   | L12 | 1230 |  992 |  23 | 215 | 82.5%| 516.97 | | L36 | 1230 |  999 |  42 | 189 | 84.6%| 435.01 |
   | L13 | 1230 | 1039 |  28 | 163 | 86.7%| 308.25 | | L37 | 1230 | 1032 |  19 | 179 | 85.4%| 449.29 |
   | L14 | 1230 |  973 |  61 | 196 | 84.1%| 505.59 | | L38 | 1230 |  944 |  27 | 259 | 78.9%| 627.88 |
   | L15 | 1230 | 1071 |  26 | 133 | 89.2%| 426.73 | | L39 | 1230 | 1038 |  36 | 156 | 87.3%| 498.17 |
   | L16 | 1230 | 1005 |  59 | 166 | 86.5%| 468.09 | | L40 | 1230 |  999 |  50 | 181 | 85.3%| 473.73 |
   | L17 | 1230 |  969 |  64 | 197 | 84.0%| 586.52 | | L41 | 1230 | 1008 |  31 | 191 | 84.5%| 361.55 |
   | L18 | 1230 |  980 |  28 | 222 | 82.0%| 663.60 | | L42 | 1230 |  987 |  24 | 219 | 82.2%| 417.72 |
   | L19 | 1230 |  990 |  72 | 168 | 86.3%| 432.13 | | L43 | 1230 | 1034 |  31 | 165 | 86.6%| 306.81 |
   | L20 | 1230 |  983 |  48 | 199 | 83.8%| 420.61 | | L44 | 1230 | 1026 |  12 | 192 | 84.4%| 364.43 |
   | L21 | 1230 |  983 |  29 | 218 | 82.3%| 673.00 | | L45 | 1230 | 1036 |   7 | 187 | 84.8%| 299.61 |
   | L22 | 1230 |  945 |  20 | 265 | 78.5%| 727.51 | | L46 | 1230 | 1018 |  19 | 193 | 84.3%| 388.92 |
   | L23 | 1230 | 1026 |  43 | 161 | 86.9%| 377.39 | | L47 | 1230 | 1019 |  14 | 197 | 84.0%| 438.01 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 29286.48 MB (Load=4614.69 | Prefill=14988.07 | Warmup=0.00 | Decode=9683.72 MB)
   SSD Data/Token (Decode)      : Avg=151.308 MB/tok (Min=86.066 | P50=146.662 | P95=263.630 | Max=270.393 MB) | Prefill=164.704 MB/tok
   NVMe Batches / Requests      : 1988 Batches | 45982 Raw -> 43841 Merged (2141 LBA Merges, Avg 684.0 KB/io)
   SSD I/O Size Histogram       : <64K=2178 | 64K-512K=9872 | 512K-2M=31313 | >2M=478
   SSD Read Bandwidth (Active)  : Min=14.35 | Avg=594.51 | Peak=8881.01 MB/s | WallAmort=392.65 MB/s (100.0% of 571.9 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=30284.07 MB | Write=128.00 MB | Syscalls=60893
   Sync Stall vs Async DMA      : SyncStall=29274.29 ms | AsyncOverlapped=40658.90 ms (58.1% Overlapped)
   RAM Traffic & Active BW      : 622.87 GB moved | Active=16.26 GB/s (38.7% STREAM) | WallAmort=8.35 GB/s (Max=42.05 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=51.21s (68.7%, 14988.07 MB SSD) | Decode=23.38s (31.3%, 9683.72 MB SSD)
   CPU Time & Utilization       : User=121.672s + Sys=8.953s (Wall=88.195s) | SysUtil=37.0% | ThrUtil=37.0% | 82.71 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  17755.03 ms (114548.6 us/tok | 23.80%)
   MoE AVX2 Q8 Expert Compute   :  17955.10 ms (115839.3 us/tok | 24.07%)
   Router + Lookahead Dispatch  :    800.38 ms ( 5163.7 us/tok |  1.07%)
   LM Head Output Projection    :   2591.20 ms (16717.4 us/tok |  3.47%)
   Foreground NVMe Sync Stall   :  29274.29 ms (188866.4 us/tok | 39.25%)
   Unaccounted / OMP & Sampling :   6210.21 ms (40065.9 us/tok |  8.33%) | Total Wall=74586.21 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    69.11%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     8.13%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    13.58%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     6.62%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.56%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_qwen38_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7196.78 MB (3468 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=1.70 tps | Avg=1.70 tps | Hit=79.7% | NVMe=527.1 MB/s (14858.61 MB, QD=64) | RSS=13120.5 MB
[LIVE-DECODE] 8/32 tok | Avg=1.95 tps | Hit=80.3% (LA:+1.8%) | NVMe=541.0 MB/s (17036.89 MB) | RSS=13127.1 MB
[LIVE-DECODE] 16/32 tok | Avg=2.32 tps | Hit=81.2% (LA:+2.9%) | NVMe=561.6 MB/s (18641.19 MB) | RSS=13091.0 MB
[LIVE-DECODE] 24/32 tok | Avg=2.48 tps | Hit=82.1% (LA:+3.4%) | NVMe=576.1 MB/s (19955.60 MB) | RSS=13085.1 MB
[LIVE-DECODE] 32/32 tok | Avg=2.64 tps | Hit=82.9% (LA:+3.7%) | NVMe=590.7 MB/s (21096.85 MB) | RSS=13073.6 MB

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
   LRFU Cache / Staging Ring    : 7196.78 MB (3468/25088 exp = 13.82% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=13073.65 MB | Peak=13550.32 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " 2!@!$!m! !! !! !! !! !! !! !! !! !!!! !! !!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=56.5% | AvgMargin=0.439 | MinMargin=0.031
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     220 |                |   15.43 |   8.4% |    2446 |   14.41 | 37718.98 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |   18.13 |  24.4% |      16 |   18.10 |  548.40 |241 |186 | 53 | 297232.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  548.40 |  0 |  0 |  0 | 297232.0 |
   |    4 |      31 | @              |   12.60 |   7.7% |      76 |   12.56 |  604.22 |235 |178 | 67 | 325719.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  604.22 |  0 |  0 |  0 | 325719.5 |
   |    6 |       3 | $              |   12.91 |  13.1% |      12 |   12.65 |  532.83 |262 |158 | 60 | 302784.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  532.83 |  0 |  0 |  0 | 302784.0 |
   |    8 |      76 | m              |   11.77 |   3.8% |   35716 |   11.70 |  370.87 |382 | 79 | 19 | 189544.5 |
   |   24 |     729 |  !             |   12.39 |  23.4% |       3 |   10.35 |  421.38 |424 | 56 |  0 | 151844.5 |
   |   25 |       0 | !              |     nan | 100.0% |       1 |     nan |  421.38 |  0 |  0 |  0 | 151844.5 |
   |   10 |     729 |  !             |   11.71 |   9.5% |    1088 |   10.91 |  377.22 |342 |122 | 16 | 220394.5 |
   |   11 |       0 | !              |     nan | 100.0% |       1 |     nan |  377.22 |  0 |  0 |  0 | 220394.5 |
   |   30 |     729 |  !             |   11.42 |   8.7% |     198 |   11.23 |  291.97 |435 | 45 |  0 | 134494.5 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  291.97 |  0 |  0 |  0 | 134494.5 |
   |   32 |     729 |  !             |   12.57 |  23.3% |   13682 |   10.85 |  293.12 |446 | 34 |  0 | 122669.5 |
   |   33 |       0 | !              |     nan | 100.0% |       1 |     nan |  293.12 |  0 |  0 |  0 | 122669.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 37.719s, TTFT=37718.98ms): Avg=1.70 | Min=1.70 | Max=1.70 tps
   Prefill Chunks (1): C1:64t/1.7tps/80%
   Decode  (32 tok, 12.103s): Avg=2.64 | Min=1.66 | Max=3.56 tps
   Latency (ms) : Min=281.01 | P10=291.97 | P25=320.76 | P50=350.58 | P75=421.38 | P90=548.40 | P95=604.22 | P99=604.22 | Max=604.22
   Mean/SD/Jitt : Mean=378.21ms | StdDev=95.82ms | Jitter=26.93ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (38400): RawRAM=30419 (79.22%) | Lookahead=1429 (+3.72%) | ColdMiss=6552 (17.06%) | EFF HIT=82.94%
   Lookahead    : 3172 prefetched -> 1589 consumed (50.1% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 81.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  800 |  537 |  26 | 237 | 70.4%| 443.04 | | L24 |  800 |  639 |  35 | 126 | 84.2%| 364.70 |
   | L01 |  800 |  605 |  23 | 172 | 78.5%| 398.44 | | L25 |  800 |  649 |  33 | 118 | 85.2%| 325.22 |
   | L02 |  800 |  599 |  16 | 185 | 76.9%| 534.01 | | L26 |  800 |  624 |  40 | 136 | 83.0%| 355.30 |
   | L03 |  800 |  698 |   8 |  94 | 88.2%| 332.74 | | L27 |  800 |  650 |  24 | 126 | 84.2%| 300.78 |
   | L04 |  800 |  654 |  11 | 135 | 83.1%| 415.04 | | L28 |  800 |  611 |  30 | 159 | 80.1%| 404.17 |
   | L05 |  800 |  622 |  17 | 161 | 79.9%| 407.93 | | L29 |  800 |  620 |  41 | 139 | 82.6%| 315.45 |
   | L06 |  800 |  611 |  23 | 166 | 79.2%| 415.45 | | L30 |  800 |  636 |  36 | 128 | 84.0%| 279.44 |
   | L07 |  800 |  599 |  25 | 176 | 78.0%| 394.19 | | L31 |  800 |  660 |  28 | 112 | 86.0%| 266.48 |
   | L08 |  800 |  645 |  31 | 124 | 84.5%| 216.65 | | L32 |  800 |  672 |  33 |  95 | 88.1%| 265.06 |
   | L09 |  800 |  658 |  27 | 115 | 85.6%| 192.99 | | L33 |  800 |  609 |  46 | 145 | 81.9%| 306.81 |
   | L10 |  800 |  633 |  30 | 137 | 82.9%| 229.10 | | L34 |  800 |  611 |  39 | 150 | 81.2%| 316.89 |
   | L11 |  800 |  638 |  34 | 128 | 84.0%| 236.57 | | L35 |  800 |  657 |  32 | 111 | 86.1%| 247.75 |
   | L12 |  800 |  608 |  31 | 161 | 79.9%| 389.14 | | L36 |  800 |  619 |  38 | 143 | 82.1%| 306.81 |
   | L13 |  800 |  598 |  56 | 146 | 81.8%| 325.54 | | L37 |  800 |  630 |  26 | 144 | 82.0%| 368.46 |
   | L14 |  800 |  616 |  51 | 133 | 83.4%| 308.25 | | L38 |  800 |  595 |  33 | 172 | 78.5%| 449.29 |
   | L15 |  800 |  667 |  19 | 114 | 85.8%| 345.90 | | L39 |  800 |  694 |  14 |  92 | 88.5%| 297.02 |
   | L16 |  800 |  670 |  32 |  98 | 87.8%| 265.06 | | L40 |  800 |  685 |  19 |  96 | 88.0%| 263.18 |
   | L17 |  800 |  645 |  35 | 120 | 85.0%| 319.58 | | L41 |  800 |  656 |  20 | 124 | 84.5%| 223.27 |
   | L18 |  800 |  603 |  39 | 158 | 80.2%| 428.61 | | L42 |  800 |  624 |  27 | 149 | 81.4%| 301.05 |
   | L19 |  800 |  655 |  41 | 104 | 87.0%| 253.52 | | L43 |  800 |  680 |  23 |  97 | 87.9%| 210.30 |
   | L20 |  800 |  615 |  38 | 147 | 81.6%| 303.93 | | L44 |  800 |  639 |  29 | 132 | 83.5%| 278.00 |
   | L21 |  800 |  608 |  40 | 152 | 81.0%| 432.37 | | L45 |  800 |  646 |  26 | 128 | 84.0%| 273.68 |
   | L22 |  800 |  575 |  39 | 186 | 76.8%| 490.65 | | L46 |  800 |  638 |  22 | 140 | 82.5%| 275.12 |
   | L23 |  800 |  678 |  23 |  99 | 87.6%| 221.83 | | L47 |  800 |  638 |  20 | 142 | 82.2%| 385.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 21096.85 MB (Load=4614.69 | Prefill=10243.92 | Warmup=0.00 | Decode=6238.24 MB)
   SSD Data/Token (Decode)      : Avg=194.945 MB/tok (Min=119.794 | P50=185.102 | P95=318.085 | Max=318.085 MB) | Prefill=160.061 MB/tok
   NVMe Batches / Requests      : 1297 Batches | 31560 Raw -> 30257 Merged (1303 LBA Merges, Avg 714.0 KB/io)
   SSD I/O Size Histogram       : <64K=1595 | 64K-512K=7504 | 512K-2M=20714 | >2M=444
   SSD Read Bandwidth (Active)  : Min=10.89 | Avg=590.72 | Peak=9804.07 MB/s | WallAmort=423.45 MB/s
   OS Kernel I/O Verification   : Read=21116.82 MB | Write=0.00 MB | Syscalls=39759
   Sync Stall vs Async DMA      : SyncStall=20462.86 ms | AsyncOverlapped=26994.42 ms (56.9% Overlapped)
   RAM Traffic & Active BW      : 360.23 GB moved | Active=14.61 GB/s | WallAmort=7.23 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=37.72s (75.7%, 10243.92 MB SSD) | Decode=12.10s (24.3%, 6238.24 MB SSD)
   CPU Time & Utilization       : User=77.953s + Sys=5.859s (Wall=62.473s) | SysUtil=33.5% | ThrUtil=33.5% | 31.02 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  11621.26 ms (121054.7 us/tok | 23.33%)
   MoE AVX2 Q8 Expert Compute   :  11739.16 ms (122282.9 us/tok | 23.56%)
   Router + Lookahead Dispatch  :    509.43 ms ( 5306.5 us/tok |  1.02%)
   LM Head Output Projection    :   1301.15 ms (13553.6 us/tok |  2.61%)
   Foreground NVMe Sync Stall   :  20462.86 ms (213154.8 us/tok | 41.07%)
   Unaccounted / OMP & Sampling :   4187.70 ms (43621.9 us/tok |  8.41%) | Total Wall=49821.55 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    66.84%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     8.33%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    14.64%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     6.43%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.76%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_qwen38_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7632.57 MB (3678 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=2.61 tps | Avg=2.61 tps | Hit=90.7% | NVMe=534.0 MB/s (23425.94 MB, QD=64) | RSS=13596.1 MB
[LIVE-PREFILL] 512/512 tok | Chunk=2.65 tps | Avg=2.63 tps | Hit=90.9% | NVMe=523.7 MB/s (41144.77 MB, QD=64) | RSS=13597.3 MB
[LIVE-DECODE] 4/128 tok | Avg=1.64 tps | Hit=90.9% (LA:+0.1%) | NVMe=525.9 MB/s (42388.03 MB) | RSS=13596.9 MB
[LIVE-DECODE] 8/128 tok | Avg=1.99 tps | Hit=90.9% (LA:+0.3%) | NVMe=532.4 MB/s (43469.80 MB) | RSS=13500.9 MB
[LIVE-DECODE] 16/128 tok | Avg=2.33 tps | Hit=91.0% (LA:+0.5%) | NVMe=547.0 MB/s (45507.89 MB) | RSS=13463.2 MB
[LIVE-DECODE] 24/128 tok | Avg=2.39 tps | Hit=91.0% (LA:+0.7%) | NVMe=555.6 MB/s (47308.14 MB) | RSS=13458.2 MB
[LIVE-DECODE] 32/128 tok | Avg=2.49 tps | Hit=91.1% (LA:+0.9%) | NVMe=565.2 MB/s (48909.64 MB) | RSS=13458.2 MB
[LIVE-DECODE] 40/128 tok | Avg=2.59 tps | Hit=91.1% (LA:+1.0%) | NVMe=575.7 MB/s (50515.94 MB) | RSS=13458.2 MB
[LIVE-DECODE] 48/128 tok | Avg=2.62 tps | Hit=91.1% (LA:+1.2%) | NVMe=585.2 MB/s (52385.33 MB) | RSS=13458.2 MB
[LIVE-DECODE] 56/128 tok | Avg=2.67 tps | Hit=91.2% (LA:+1.3%) | NVMe=592.5 MB/s (53864.49 MB) | RSS=13458.2 MB
[LIVE-DECODE] 64/128 tok | Avg=2.67 tps | Hit=91.2% (LA:+1.4%) | NVMe=599.4 MB/s (55579.97 MB) | RSS=13452.0 MB
[LIVE-DECODE] 72/128 tok | Avg=2.70 tps | Hit=91.2% (LA:+1.5%) | NVMe=605.8 MB/s (56990.57 MB) | RSS=13452.0 MB
[LIVE-DECODE] 80/128 tok | Avg=2.76 tps | Hit=91.3% (LA:+1.6%) | NVMe=613.2 MB/s (58281.21 MB) | RSS=13458.2 MB
[LIVE-DECODE] 88/128 tok | Avg=2.73 tps | Hit=91.3% (LA:+1.7%) | NVMe=616.8 MB/s (59904.48 MB) | RSS=13458.1 MB
[LIVE-DECODE] 96/128 tok | Avg=2.76 tps | Hit=91.4% (LA:+1.7%) | NVMe=623.2 MB/s (61224.82 MB) | RSS=13458.1 MB
[LIVE-DECODE] 104/128 tok | Avg=2.76 tps | Hit=91.4% (LA:+1.8%) | NVMe=628.6 MB/s (62735.81 MB) | RSS=13458.1 MB
[LIVE-DECODE] 112/128 tok | Avg=2.78 tps | Hit=91.5% (LA:+1.9%) | NVMe=634.5 MB/s (64165.56 MB) | RSS=13458.1 MB
[LIVE-DECODE] 120/128 tok | Avg=2.80 tps | Hit=91.5% (LA:+2.0%) | NVMe=639.0 MB/s (65422.71 MB) | RSS=13458.1 MB
[LIVE-DECODE] 128/128 tok | Avg=2.79 tps | Hit=91.5% (LA:+2.1%) | NVMe=643.3 MB/s (67011.64 MB) | RSS=13458.1 MB

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
   LRFU Cache / Staging Ring    : 7632.57 MB (3678/25088 exp = 14.66% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.74 MB | End=13458.15 MB | Peak=14025.31 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : " layer-wise!

!

!

!

!

!

!

!

!

!

!

!

!

!

!

!!!

!

!

!!!

!

!

!

!

!

!

!

!!!

!

!

!

!

!

!

!

!

!

!

!!!

!

!!!

!

!!!

!

!!!

!

!!!

!!!!!

!!!

!!!!!

!

!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=83.4% | AvgMargin=1.017 | MinMargin=0.011
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    6000 |  layer         |   23.21 | 100.0% |   22028 |   13.32 | 194712.04 |  0 |  0 |  0 |     0.0 |
   |    2 |   42962 | -wise          |   20.97 |  99.8% |     271 |   13.36 |  441.03 |352 | 97 | 31 | 227232.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  441.03 |  0 |  0 |  0 | 227232.0 |
   |    4 |     271 | \n\n           |   14.91 |  64.2% |    1249 |   12.28 |  775.39 |126 |255 | 99 | 409321.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  775.39 |  0 |  0 |  0 | 409321.5 |
   |    6 |     271 | \n\n           |   14.60 |  51.0% |      12 |   12.47 |  479.64 |252 |172 | 56 | 307019.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  479.64 |  0 |  0 |  0 | 307019.5 |
   |    8 |     271 | \n\n           |   15.03 |  62.2% |      12 |   12.04 |  310.15 |313 |161 |  6 | 246844.5 |
   |   24 |     271 | \n\n           |   14.22 |  63.2% |     729 |   11.22 |  556.54 |335 |135 | 10 | 221519.5 |
   |   25 |       0 | !              |     nan | 100.0% |       1 |     nan |  556.54 |  0 |  0 |  0 | 221519.5 |
   |   82 |     271 | \n\n           |   14.28 |  58.8% |       0 |   13.23 |  548.21 |325 |120 | 35 | 255469.5 |
   |   83 |       0 | !              |     nan | 100.0% |       1 |     nan |  548.21 |  0 |  0 |  0 | 255469.5 |
   |  126 |     271 | \n\n           |   15.13 |  67.9% |       0 |   13.61 |  354.40 |393 | 61 | 26 | 197857.0 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  354.40 |  0 |  0 |  0 | 197857.0 |
   |  128 |     271 | \n\n           |   15.21 |  63.7% |       0 |   13.85 |  279.79 |441 | 38 |  1 | 129844.5 |
   |  129 |       0 | !              |     nan | 100.0% |       1 |     nan |  279.79 |  0 |  0 |  0 | 129844.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 194.712s, TTFT=194712.04ms): Avg=2.63 | Min=2.61 | Max=2.65 tps
   Prefill Chunks (2): C1:256t/2.6tps/91% | C2:256t/2.7tps/91%
   Decode  (128 tok, 45.886s): Avg=2.79 | Min=1.29 | Max=3.77 tps
   Latency (ms) : Min=265.33 | P10=281.82 | P25=298.65 | P50=334.58 | P75=403.00 | P90=479.64 | P95=507.82 | P99=775.39 | Max=775.39
   Mean/SD/Jitt : Mean=358.48ms | StdDev=88.59ms | Jitter=39.43ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (276480): RawRAM=247376 (89.47%) | Lookahead=5688 (+2.06%) | ColdMiss=23416 (8.47%) | EFF HIT=91.53%
   Lookahead    : 13376 prefetched -> 6328 consumed (47.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 91.0% | @64= 91.2% | @128= 91.5% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 5760 | 5054 |  65 | 641 | 88.9%|1189.31 | | L24 | 5760 | 5152 | 133 | 475 | 91.8%|1661.82 |
   | L01 | 5760 | 5151 |  65 | 544 | 90.6%|1286.21 | | L25 | 5760 | 5164 | 142 | 454 | 92.1%|1283.96 |
   | L02 | 5760 | 5183 |  33 | 544 | 90.6%|1731.74 | | L26 | 5760 | 5039 | 191 | 530 | 90.8%|1641.14 |
   | L03 | 5760 | 5343 |  33 | 384 | 93.3%|1317.80 | | L27 | 5760 | 5126 | 171 | 463 | 92.0%|1385.47 |
   | L04 | 5760 | 5287 |  25 | 448 | 92.2%|1413.21 | | L28 | 5760 | 5068 | 168 | 524 | 90.9%|1518.95 |
   | L05 | 5760 | 5204 |  49 | 507 | 91.2%|1252.00 | | L29 | 5760 | 5004 | 212 | 544 | 90.6%|1296.39 |
   | L06 | 5760 | 5131 |  47 | 582 | 89.9%|1300.88 | | L30 | 5760 | 5033 | 205 | 522 | 90.9%|1250.29 |
   | L07 | 5760 | 5131 |  84 | 545 | 90.5%|1224.68 | | L31 | 5760 | 5186 | 143 | 431 | 92.5%|1198.44 |
   | L08 | 5760 | 5220 |  78 | 462 | 92.0%| 820.53 | | L32 | 5760 | 5188 | 127 | 445 | 92.3%|1327.20 |
   | L09 | 5760 | 5224 |  80 | 456 | 92.1%| 765.75 | | L33 | 5760 | 4995 | 223 | 542 | 90.6%|1261.82 |
   | L10 | 5760 | 5179 |  96 | 485 | 91.6%| 819.29 | | L34 | 5760 | 5046 | 172 | 542 | 90.6%|1351.12 |
   | L11 | 5760 | 5160 | 127 | 473 | 91.8%| 839.21 | | L35 | 5760 | 5161 | 137 | 462 | 92.0%| 993.90 |
   | L12 | 5760 | 5155 | 109 | 496 | 91.4%|1314.04 | | L36 | 5760 | 5149 | 124 | 487 | 91.5%|1042.87 |
   | L13 | 5760 | 5041 | 198 | 521 | 91.0%|1178.27 | | L37 | 5760 | 5176 |  93 | 491 | 91.5%|1374.19 |
   | L14 | 5760 | 5099 | 182 | 479 | 91.7%|1096.17 | | L38 | 5760 | 5084 | 113 | 563 | 90.2%|1513.31 |
   | L15 | 5760 | 5333 | 117 | 310 | 94.6%|1079.05 | | L39 | 5760 | 5237 |  89 | 434 | 92.5%|1263.28 |
   | L16 | 5760 | 5223 | 178 | 359 | 93.8%|1259.52 | | L40 | 5760 | 5254 |  85 | 421 | 92.7%|1075.29 |
   | L17 | 5760 | 5050 | 215 | 495 | 91.4%|1537.74 | | L41 | 5760 | 5161 |  92 | 507 | 91.2%| 993.90 |
   | L18 | 5760 | 5128 | 112 | 520 | 91.0%|1627.98 | | L42 | 5760 | 5154 | 104 | 502 | 91.3%|1165.31 |
   | L19 | 5760 | 5107 | 201 | 452 | 92.2%|1107.69 | | L43 | 5760 | 5256 |  84 | 420 | 92.7%| 898.83 |
   | L20 | 5760 | 5066 | 201 | 493 | 91.4%|1218.60 | | L44 | 5760 | 5190 |  64 | 506 | 91.2%|1114.89 |
   | L21 | 5760 | 5083 | 128 | 549 | 90.5%|1518.95 | | L45 | 5760 | 5219 |  68 | 473 | 91.8%| 980.93 |
   | L22 | 5760 | 5084 | 112 | 564 | 90.2%|1635.50 | | L46 | 5760 | 5271 |  56 | 433 | 92.5%| 978.05 |
   | L23 | 5760 | 5233 | 120 | 407 | 92.9%| 969.41 | | L47 | 5760 | 5194 |  37 | 529 | 90.8%|1097.85 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 67011.64 MB (Load=4614.69 | Prefill=36530.07 | Warmup=0.00 | Decode=25866.87 MB)
   SSD Data/Token (Decode)      : Avg=202.085 MB/tok (Min=124.848 | P50=198.579 | P95=269.733 | Max=399.728 MB) | Prefill=71.348 MB/tok
   NVMe Batches / Requests      : 5153 Batches | 120700 Raw -> 115580 Merged (5120 LBA Merges, Avg 593.7 KB/io)
   SSD I/O Size Histogram       : <64K=9473 | 64K-512K=26750 | 512K-2M=78754 | >2M=603
   SSD Read Bandwidth (Active)  : Min=7.98 | Avg=643.31 | Peak=10614.81 MB/s | WallAmort=278.52 MB/s
   OS Kernel I/O Verification   : Read=67031.77 MB | Write=0.00 MB | Syscalls=125096
   Sync Stall vs Async DMA      : SyncStall=71219.04 ms | AsyncOverlapped=95667.92 ms (57.3% Overlapped)
   RAM Traffic & Active BW      : 2072.99 GB moved | Active=13.66 GB/s | WallAmort=8.62 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=194.71s (80.9%, 36530.07 MB SSD) | Decode=45.89s (19.1%, 25866.87 MB SSD)
   CPU Time & Utilization       : User=521.156s + Sys=19.344s (Wall=253.478s) | SysUtil=53.3% | ThrUtil=53.3% | 49.31 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  69601.34 ms (108752.1 us/tok | 28.93%)
   MoE AVX2 Q8 Expert Compute   :  77063.52 ms (120411.7 us/tok | 32.03%)
   Router + Lookahead Dispatch  :   3480.69 ms ( 5438.6 us/tok |  1.45%)
   LM Head Output Projection    :   5087.50 ms ( 7949.2 us/tok |  2.11%)
   Foreground NVMe Sync Stall   :  71219.04 ms (111279.8 us/tok | 29.60%)
   Unaccounted / OMP & Sampling :  14146.01 ms (22103.1 us/tok |  5.88%) | Total Wall=240598.10 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    78.44%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.77%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     7.17%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     6.22%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.40%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_qwen38_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 28099.6ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\n\n<think>\nThe user is asking me to summarize "LBA-coalesced'
[Stage 3] /v1/chat/completions (stream=true SSE) 9278.7ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_qwen38_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=5978.64 MB (2881 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2.70 tps | Avg=2.70 tps | Hit=90.7% | NVMe=542.5 MB/s (23425.94 MB, QD=64) | RSS=11948.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.71 tps | Avg=2.71 tps | Hit=90.6% | NVMe=548.8 MB/s (42324.09 MB, QD=64) | RSS=11969.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.70 tps | Avg=2.71 tps | Hit=90.6% | NVMe=554.9 MB/s (61641.39 MB, QD=64) | RSS=11973.0 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.70 tps | Avg=2.70 tps | Hit=90.5% | NVMe=558.8 MB/s (80842.50 MB, QD=64) | RSS=11973.6 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.73 tps | Avg=2.71 tps | Hit=90.6% | NVMe=560.9 MB/s (99081.85 MB, QD=64) | RSS=11973.3 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.76 tps | Avg=2.72 tps | Hit=90.7% | NVMe=563.0 MB/s (116639.63 MB, QD=64) | RSS=11973.1 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.74 tps | Avg=2.72 tps | Hit=90.8% | NVMe=564.5 MB/s (134582.25 MB, QD=64) | RSS=11973.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.72 tps | Avg=2.72 tps | Hit=90.8% | NVMe=565.8 MB/s (152636.55 MB, QD=64) | RSS=11974.2 MB
[LIVE-DECODE] 4/64 tok | Avg=1.38 tps | Hit=90.8% (LA:+0.0%) | NVMe=566.3 MB/s (154194.41 MB) | RSS=11976.8 MB
[LIVE-DECODE] 8/64 tok | Avg=1.77 tps | Hit=90.8% (LA:+0.1%) | NVMe=568.4 MB/s (155393.27 MB) | RSS=11972.6 MB
[LIVE-DECODE] 16/64 tok | Avg=2.23 tps | Hit=90.8% (LA:+0.2%) | NVMe=574.7 MB/s (157754.41 MB) | RSS=11972.4 MB
[LIVE-DECODE] 24/64 tok | Avg=2.47 tps | Hit=90.9% (LA:+0.2%) | NVMe=581.2 MB/s (160104.02 MB) | RSS=11972.1 MB
[LIVE-DECODE] 32/64 tok | Avg=2.58 tps | Hit=90.9% (LA:+0.3%) | NVMe=587.1 MB/s (162401.76 MB) | RSS=11969.9 MB
[LIVE-DECODE] 40/64 tok | Avg=2.67 tps | Hit=90.9% (LA:+0.4%) | NVMe=592.7 MB/s (164527.47 MB) | RSS=11960.4 MB
[LIVE-DECODE] 48/64 tok | Avg=2.75 tps | Hit=90.9% (LA:+0.5%) | NVMe=598.5 MB/s (166627.80 MB) | RSS=11955.8 MB
[LIVE-DECODE] 56/64 tok | Avg=2.83 tps | Hit=90.9% (LA:+0.5%) | NVMe=603.9 MB/s (168477.02 MB) | RSS=11955.8 MB
[LIVE-DECODE] 64/64 tok | Avg=2.89 tps | Hit=90.9% (LA:+0.6%) | NVMe=608.8 MB/s (170230.57 MB) | RSS=11955.8 MB

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
   LRFU Cache / Staging Ring    : 5978.64 MB (2881/25088 exp = 11.48% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.74 MB | End=11955.75 MB | Peak=12372.99 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : " layer-wise!

!

!

!

!

!

!

!!!

!

!

!!!

!

!

!!!

!

!

!

!

!

!

!

!

!

!

!

!

!

!

!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=82.7% | AvgMargin=0.866 | MinMargin=0.129
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    6000 |  layer         |   21.89 |  99.5% |     271 |   16.32 | 753264.10 |  0 |  0 |  0 |     0.0 |
   |    2 |   42962 | -wise          |   22.34 |  99.5% |     271 |   16.47 |  518.81 |341 | 86 | 53 | 277694.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  518.81 |  0 |  0 |  0 | 277694.5 |
   |    4 |     271 | \n\n           |   16.51 |  89.2% |      12 |   11.88 |  928.76 | 27 |322 |131 | 519934.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  928.76 |  0 |  0 |  0 | 519934.0 |
   |    6 |     271 | \n\n           |   15.91 |  81.7% |  248046 |   12.04 |  482.67 |240 |192 | 48 | 329444.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  482.67 |  0 |  0 |  0 | 329444.5 |
   |    8 |     271 | \n\n           |   15.66 |  75.8% |       0 |   13.24 |  331.25 |301 |174 |  5 | 284369.5 |
   |   26 |       0 | !              |   15.65 |  63.7% |     271 |   14.82 |  401.20 |251 |212 | 17 | 324182.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  401.20 |  0 |  0 |  0 | 324182.0 |
   |   34 |       0 | !              |   16.39 |  64.6% |     271 |   15.58 |  377.50 |284 |190 |  6 | 290744.5 |
   |   35 |       0 | !              |     nan | 100.0% |       1 |     nan |  377.50 |  0 |  0 |  0 | 290744.5 |
   |   62 |     271 | \n\n           |   14.68 |  48.3% |       0 |   14.40 |  288.20 |363 |117 |  0 | 228707.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  288.20 |  0 |  0 |  0 | 228707.0 |
   |   64 |     271 | \n\n           |   14.92 |  60.9% |       0 |   13.88 |  290.14 |361 |119 |  0 | 217182.0 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  290.14 |  0 |  0 |  0 | 217182.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 753.264s, TTFT=753264.10ms): Avg=2.72 | Min=2.70 | Max=2.76 tps
   Prefill Chunks (8): C1:256t/2.7tps/91% | C2:256t/2.7tps/91% | C3:256t/2.7tps/91% | C4:256t/2.7tps/91%
                       C5:256t/2.7tps/91% | C6:256t/2.8tps/91% | C7:256t/2.7tps/91% | C8:256t/2.7tps/91%
   Decode  (64 tok, 22.112s): Avg=2.89 | Min=1.08 | Max=3.52 tps
   Latency (ms) : Min=284.30 | P10=288.20 | P25=298.14 | P50=312.81 | P75=334.86 | P90=401.20 | P95=518.81 | P99=928.76 | Max=928.76
   Mean/SD/Jitt : Mean=345.50ms | StdDev=117.18ms | Jitter=27.07ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (998400): RawRAM=902365 (90.38%) | Lookahead=5552 (+0.56%) | ColdMiss=90483 (9.06%) | EFF HIT=90.94%
   Lookahead    : 9730 prefetched -> 5872 consumed (60.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.8% | @64= 90.9% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |20800 |18000 | 221 |2579 | 87.6%|4716.80 | | L24 |20800 |18904 |  96 |1800 | 91.3%|3836.84 |
   | L01 |20800 |18386 | 153 |2261 | 89.1%|3242.29 | | L25 |20800 |18654 |  99 |2047 | 90.2%|4105.66 |
   | L02 |20800 |18270 | 139 |2391 | 88.5%|4642.68 | | L26 |20800 |18790 | 114 |1896 | 90.9%|3908.28 |
   | L03 |20800 |18782 | 139 |1879 | 91.0%|4116.94 | | L27 |20800 |18757 | 135 |1908 | 90.8%|3966.55 |
   | L04 |20800 |19086 |  69 |1645 | 92.1%|3691.77 | | L28 |20800 |18939 | 121 |1740 | 91.6%|3641.33 |
   | L05 |20800 |18626 | 117 |2057 | 90.1%|4254.17 | | L29 |20800 |18831 | 118 |1851 | 91.1%|2926.95 |
   | L06 |20800 |18489 |  70 |2241 | 89.2%|4466.60 | | L30 |20800 |18530 |  99 |2171 | 89.6%|3361.96 |
   | L07 |20800 |18481 | 171 |2148 | 89.7%|4002.54 | | L31 |20800 |18954 | 105 |1741 | 91.6%|2818.92 |
   | L08 |20800 |18879 | 151 |1770 | 91.5%|2482.76 | | L32 |20800 |18885 |  76 |1839 | 91.2%|3701.49 |
   | L09 |20800 |18947 | 141 |1712 | 91.8%|2355.76 | | L33 |20800 |18671 |  93 |2036 | 90.2%|3141.58 |
   | L10 |20800 |19009 | 127 |1664 | 92.0%|2287.28 | | L34 |20800 |18845 |  97 |1858 | 91.1%|2944.24 |
   | L11 |20800 |18986 | 152 |1662 | 92.0%|2315.92 | | L35 |20800 |18905 |  75 |1820 | 91.2%|2787.23 |
   | L12 |20800 |18960 | 196 |1644 | 92.1%|3577.42 | | L36 |20800 |18939 | 122 |1739 | 91.6%|2788.67 |
   | L13 |20800 |19103 | 148 |1549 | 92.6%|2517.87 | | L37 |20800 |18843 | 111 |1846 | 91.1%|3789.84 |
   | L14 |20800 |18857 | 146 |1797 | 91.4%|2908.23 | | L38 |20800 |18699 |  84 |2017 | 90.3%|4032.35 |
   | L15 |20800 |18994 | 147 |1659 | 92.0%|3556.74 | | L39 |20800 |19000 | 100 |1700 | 91.8%|3628.17 |
   | L16 |20800 |18877 | 158 |1765 | 91.5%|3780.44 | | L40 |20800 |18876 |  57 |1867 | 91.0%|3720.29 |
   | L17 |20800 |18855 | 138 |1807 | 91.3%|3780.44 | | L41 |20800 |18550 |  56 |2194 | 89.5%|3325.95 |
   | L18 |20800 |18877 | 138 |1785 | 91.4%|3772.92 | | L42 |20800 |18738 |  55 |2007 | 90.4%|3128.61 |
   | L19 |20800 |18796 | 148 |1856 | 91.1%|3009.06 | | L43 |20800 |18919 |  67 |1814 | 91.3%|2839.09 |
   | L20 |20800 |18625 | 156 |2019 | 90.3%|3271.22 | | L44 |20800 |18846 |  54 |1900 | 90.9%|2952.88 |
   | L21 |20800 |18992 | 154 |1654 | 92.0%|3541.70 | | L45 |20800 |18810 |  62 |1928 | 90.7%|2974.49 |
   | L22 |20800 |18965 | 127 |1708 | 91.8%|3645.09 | | L46 |20800 |19243 |  31 |1526 | 92.7%|2388.23 |
   | L23 |20800 |18753 | 144 |1903 | 90.9%|3112.77 | | L47 |20800 |18642 |  75 |2083 | 90.0%|4130.10 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 170230.57 MB (Load=4614.69 | Prefill=148021.85 | Warmup=0.00 | Decode=17594.02 MB)
   SSD Data/Token (Decode)      : Avg=274.907 MB/tok (Min=212.092 | P50=276.752 | P95=321.723 | Max=507.748 MB) | Prefill=72.276 MB/tok
   NVMe Batches / Requests      : 4555 Batches | 335027 Raw -> 315323 Merged (19704 LBA Merges, Avg 552.8 KB/io)
   SSD I/O Size Histogram       : <64K=33329 | 64K-512K=70618 | 512K-2M=210244 | >2M=1132
   SSD Read Bandwidth (Active)  : Min=10.87 | Avg=608.84 | Peak=11712.67 MB/s | WallAmort=219.55 MB/s
   OS Kernel I/O Verification   : Read=170251.11 MB | Write=0.00 MB | Syscalls=324837
   Sync Stall vs Async DMA      : SyncStall=261664.34 ms | AsyncOverlapped=271199.69 ms (50.9% Overlapped)
   RAM Traffic & Active BW      : 5562.56 GB moved | Active=11.25 GB/s | WallAmort=7.17 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=753.26s (97.1%, 148021.85 MB SSD) | Decode=22.11s (2.9%, 17594.02 MB SSD)
   CPU Time & Utilization       : User=1814.734s + Sys=40.984s (Wall=787.420s) | SysUtil=58.9% | ThrUtil=58.9% | 54.50 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 224192.95 ms (106152.0 us/tok | 28.91%)
   MoE AVX2 Q8 Expert Compute   : 267919.48 ms (126855.8 us/tok | 34.55%)
   Router + Lookahead Dispatch  :  11828.13 ms ( 5600.4 us/tok |  1.53%)
   LM Head Output Projection    :   2484.71 ms ( 1176.5 us/tok |  0.32%)
   Foreground NVMe Sync Stall   : 261664.34 ms (123894.1 us/tok | 33.75%)
   Unaccounted / OMP & Sampling :   7286.27 ms ( 3449.9 us/tok |  0.94%) | Total Wall=775375.87 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    82.58%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.35%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     6.05%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.53%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.49%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_qwen38_colibri_bench.log`
```text
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=325.0s) ===
[gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
[gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
== Qwen3.8-Flash-Next native text engine | cache=72/layer | CPU ==
[tok] loaded 248320 base pieces + 33 added tokens (max id 248319) from D:/apex_d_drive/models/qwen38/tokenizer.json
[qwen38] native text weights: prefix=model, 48 layers, PLE=1, cache=72/layer, FP8=native, BF16=native (resident matrices 4.40 GiB)
[qwen38] MTP head mtp.*: wiring b (a norm per stream, fc_hidden per stream), RoPE base 1e+07, 96.86 MiB resident; routed experts Q8_0 from the snapshot (its own GGUF), cache 72 (Q38_MTP_CAP) x 4.98 MiB = 0.35 GiB full
[qwen38] MTP norm weights, mean: embedding -0.7642, hidden -0.3284, mixer 3.7881 (q38_rms0 scales by 1+w; a plain norm's weights would sit near 1)
[qwen38] trunk: 62 matrices int8 on the CPU (0.08 GiB, 0.28 GiB of BF16 released) in 0.3s; Q38_TRUNK_CPU_INT8=0 keeps BF16
[qwen38 MTP] draft vocabulary: the lm_head has no int8 rows on the host, so the head scores the whole vocabulary (Q38_MTP_VOCAB=0 silences this)
[qwen38] routed experts: GGUF IQ2_XXS/IQ2_XXS/IQ4_NL (layer 0), 1.68 MiB per expert; cache 72/layer
[qwen38] trunk: 62 int8 matrices interleaved by 16 for the CPU in 0.02s (Q38_ILV16=0 keeps the rows)
resident weights loaded in 9.6s | RSS after load: 4.60 GB
[qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=325.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.0s / cutoff=325.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=325.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=60.1s / cutoff=325.0s
TTFT: 25.68 s (time to first token)
[qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
[qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
[qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes

PEAK RSS: 10.73 GB
Expert cache hit rate: 62.0% (hit=15849 miss=9733)
Speed: 0.66 tok/s (48.8s for 32 tokens)
[STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage

Reference: 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 
C engine : 220 248046 198 248045 74455 198 248068 198 760 1156 682 3106 1092 7701 310 381 264 7132 36412 2805 269 82987 886 314 5587 13 6558 728 22903 411 25 271 Text      :  <|im_end|>
<|im_start|>assistant
<think>
The user has sent what appears to be a garbled/corrupted string of characters. Let me analyze this:



Matching tokens: 0/32
=== [Colibri-Qwen38] Finished rc=1 elapsed=61.15s cancelled=False ===
```

### 📄 `12_qwen38_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 1.70 | 2.64 | 350.58 | 82.94% | 590.72 | 13550.32 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 2.63 | 2.79 | 334.58 | 91.53% | 643.31 | 14025.31 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.72 | 2.89 | 312.81 | 90.94% | 608.84 | 12372.99 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.66 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
