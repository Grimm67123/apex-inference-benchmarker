<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#22 (Run ID `43451812982`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43451812982)
- **Status**: **CANCELLED**
- **Timestamp**: `2026-11-13 16:22:15 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-13T15:21:40.237Z] ================================================================================
[2026-11-13T15:21:40.256Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-13T15:21:40.258Z] ================================================================================
[2026-11-13T15:21:44.717Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-13T15:21:44.950Z] --------------------------------------------------------------------------------
[2026-11-13T15:21:44.952Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.14 GB / 149.89 GB
[2026-11-13T15:21:44.954Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-13T15:21:44.955Z]  [Disk Telemetry] Total Combined Usable Free Space: 248.01 GB
[2026-11-13T15:21:44.957Z] --------------------------------------------------------------------------------
[2026-11-13T15:21:44.958Z]  [OK] Disk space verification passed: 248.01 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 843K Nov 13 15:22 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 843K Nov 13 15:22 build/apex.exe
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
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.42 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :     56.97 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2119.41 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4991.50 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7704.04 MB/s
   RND4K Q32T16 Read                  :    518.58 MB/s (  132757 IOPS)
   RND4K Q1T1  Read                   :    787.15 MB/s (Latency: 4.96 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     46.59 GB/s
   AVX2 256-bit Sequential Write BW   :     40.49 GB/s
   STREAM Triad (A = B + s*C) BW      :     30.12 GB/s
   Random Pointer-Chase Latency       :     50.48 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     38.43 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    189.55 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     17.14 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1349.92 tps | Avg=1349.92 tps | Hit=99.5% | NVMe=1784.0 MB/s (6.19 MB, QD=64) | RSS=71.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1251.52 tps | Avg=1298.86 tps | Hit=99.5% | NVMe=1741.0 MB/s (7.01 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1089.75 tps | Avg=1220.78 tps | Hit=99.5% | NVMe=1690.8 MB/s (7.78 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=960.65 tps | Avg=1143.37 tps | Hit=99.5% | NVMe=1666.8 MB/s (8.61 MB, QD=64) | RSS=71.9 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=853.18 tps | Avg=1070.55 tps | Hit=99.5% | NVMe=1653.1 MB/s (9.33 MB, QD=64) | RSS=72.2 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=792.87 tps | Avg=1011.51 tps | Hit=99.5% | NVMe=1638.8 MB/s (10.06 MB, QD=64) | RSS=72.4 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=716.71 tps | Avg=955.37 tps | Hit=99.5% | NVMe=1612.7 MB/s (10.83 MB, QD=64) | RSS=72.7 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=648.22 tps | Avg=901.95 tps | Hit=99.5% | NVMe=1578.4 MB/s (11.60 MB, QD=64) | RSS=72.9 MB
[LIVE-DECODE] 8/32 tok | Avg=167.30 tps | Hit=99.5% (LA:+0.0%) | NVMe=1532.9 MB/s (12.43 MB) | RSS=73.0 MB
[LIVE-DECODE] 16/32 tok | Avg=172.65 tps | Hit=99.5% (LA:+0.1%) | NVMe=1514.2 MB/s (13.10 MB) | RSS=73.0 MB
[LIVE-DECODE] 24/32 tok | Avg=174.35 tps | Hit=99.5% (LA:+0.1%) | NVMe=1506.9 MB/s (13.25 MB) | RSS=73.0 MB
[LIVE-DECODE] 32/32 tok | Avg=174.73 tps | Hit=99.5% (LA:+0.1%) | NVMe=1499.0 MB/s (13.30 MB) | RSS=73.0 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=72.96 MB | Peak=72.96 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2270.64 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    6.40 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    6.40 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.99 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.99 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.62 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.62 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.90 | 11 |  1 |  0 |    49.5 |
   |    9 |      68 | tok_68         |  176.71 | 100.0% |     228 |  144.43 |    5.90 |  0 |  0 |  0 |    49.5 |
   |   24 |     246 | tok_246        |  204.37 |  99.2% |      55 |  199.55 |    5.82 | 11 |  1 |  0 |     0.0 |
   |   25 |     229 | tok_229        |  171.20 | 100.0% |      70 |  154.08 |    5.82 |  0 |  0 |  0 |     0.0 |
   |   28 |     246 | tok_246        |  194.87 | 100.0% |      54 |  173.43 |    5.78 | 12 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.62 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.62 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.57 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.57 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.271s, TTFT=2270.64ms): Avg=901.95 | Min=648.22 | Max=1349.92 tps
   Prefill Chunks (8): C1:256t/1349.9tps/99% | C2:256t/1251.5tps/99% | C3:256t/1089.7tps/99% | C4:256t/960.6tps/99%
                       C5:256t/853.2tps/99% | C6:256t/792.9tps/99% | C7:256t/716.7tps/99% | C8:256t/648.2tps/99%
   Decode  (32 tok, 0.183s): Avg=174.73 | Min=156.16 | Max=188.75 tps
   Latency (ms) : Min=5.30 | P10=5.44 | P25=5.62 | P50=5.69 | P75=5.82 | P90=5.99 | P95=6.40 | P99=6.40 | Max=6.40
   Mean/SD/Jitt : Mean=5.72ms | StdDev=0.24ms | Jitter=0.10ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=218.34 | Avg=1499.01 | Peak=4562.04 MB/s | WallAmort=5.42 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=5.85 ms | AsyncOverlapped=7.37 ms (55.8% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.62 GB/s | WallAmort=0.58 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.27s (92.5%, 6.19 MB SSD) | Decode=0.18s (7.5%, 1.69 MB SSD)
   CPU Time & Utilization       : User=3.062s + Sys=0.594s (Wall=2.483s) | SysUtil=36.8% | ThrUtil=36.8% | 34.05 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2055.81 ms (  988.4 us/tok | 83.78%)
   MoE AVX2 Q8 Expert Compute   :    257.01 ms (  123.6 us/tok | 10.47%)
   Router + Lookahead Dispatch  :     61.28 ms (   29.5 us/tok |  2.50%)
   LM Head Output Projection    :      7.16 ms (    3.4 us/tok |  0.29%)
   Foreground NVMe Sync Stall   :      5.85 ms (    2.8 us/tok |  0.24%)
   Unaccounted / OMP & Sampling :     66.67 ms (   32.1 us/tok |  2.72%) | Total Wall=2453.78 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    24.39%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.14%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.45%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    71.26%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.76%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1851.83 tps | Avg=1851.83 tps | Hit=99.2% | NVMe=2232.3 MB/s (24.91 MB, QD=64) | RSS=89.0 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1752.34 tps | Avg=1800.71 tps | Hit=99.2% | NVMe=2949.1 MB/s (42.92 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1763.29 tps | Avg=1788.06 tps | Hit=99.2% | NVMe=3402.9 MB/s (61.04 MB, QD=64) | RSS=89.6 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1644.17 tps | Avg=1749.78 tps | Hit=99.2% | NVMe=3639.7 MB/s (79.10 MB, QD=64) | RSS=89.9 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1576.85 tps | Avg=1712.22 tps | Hit=99.2% | NVMe=3859.5 MB/s (97.14 MB, QD=64) | RSS=90.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1460.00 tps | Avg=1664.30 tps | Hit=99.2% | NVMe=4064.3 MB/s (115.20 MB, QD=64) | RSS=90.8 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1391.23 tps | Avg=1618.91 tps | Hit=99.2% | NVMe=4213.5 MB/s (133.27 MB, QD=64) | RSS=91.3 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1278.46 tps | Avg=1566.76 tps | Hit=99.2% | NVMe=4347.8 MB/s (151.30 MB, QD=64) | RSS=91.6 MB
[LIVE-DECODE] 8/32 tok | Avg=157.71 tps | Hit=99.2% (LA:+0.0%) | NVMe=4257.1 MB/s (152.70 MB) | RSS=91.6 MB
[LIVE-DECODE] 16/32 tok | Avg=157.94 tps | Hit=99.2% (LA:+0.1%) | NVMe=4223.6 MB/s (153.28 MB) | RSS=91.6 MB
[LIVE-DECODE] 24/32 tok | Avg=159.84 tps | Hit=99.2% (LA:+0.1%) | NVMe=4156.7 MB/s (154.23 MB) | RSS=91.6 MB
[LIVE-DECODE] 32/32 tok | Avg=159.33 tps | Hit=99.2% (LA:+0.1%) | NVMe=4108.1 MB/s (155.14 MB) | RSS=91.6 MB

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
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=91.63 MB | Peak=91.63 MB
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
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 | 1307.16 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    6.25 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    6.25 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    6.50 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    6.50 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    6.29 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    6.29 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    6.33 | 16 |  0 |  0 |    32.0 |
   |   12 |     254 | qtok_254       |   71.67 |  96.6% |      66 |   68.21 |    6.48 | 16 |  0 |  0 |    32.0 |
   |   13 |     129 | qtok_129       |   76.30 |  99.3% |      49 |   71.12 |    6.48 |  0 |  0 |  0 |    32.0 |
   |   14 |      68 | qtok_68        |   60.97 |  98.8% |      36 |   56.50 |    6.33 | 12 |  4 |  0 |   143.0 |
   |   15 |     209 | qtok_209       |   94.05 |  99.5% |      49 |   88.77 |    6.33 |  0 |  0 |  0 |   143.0 |
   |   30 |     254 | qtok_254       |   58.92 |  92.7% |      49 |   56.39 |    6.36 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    6.36 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.75 |  64.8% |     229 |   52.56 |    6.38 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    6.38 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.307s, TTFT=1307.16ms): Avg=1566.76 | Min=1278.46 | Max=1851.83 tps
   Prefill Chunks (8): C1:256t/1851.8tps/99% | C2:256t/1752.3tps/99% | C3:256t/1763.3tps/99% | C4:256t/1644.2tps/99%
                       C5:256t/1576.9tps/99% | C6:256t/1460.0tps/99% | C7:256t/1391.2tps/99% | C8:256t/1278.5tps/99%
   Decode  (32 tok, 0.201s): Avg=159.33 | Min=153.96 | Max=166.34 tps
   Latency (ms) : Min=6.01 | P10=6.06 | P25=6.22 | P50=6.29 | P75=6.36 | P90=6.48 | P95=6.50 | P99=6.50 | Max=6.50
   Mean/SD/Jitt : Mean=6.28ms | StdDev=0.13ms | Jitter=0.06ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=395.33 | Avg=4108.13 | Peak=7628.76 MB/s | WallAmort=102.88 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=8.23 ms | AsyncOverlapped=36.12 ms (81.4% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.63 GB/s | WallAmort=1.39 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.31s (86.7%, 144.44 MB SSD) | Decode=0.20s (13.3%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.641s + Sys=0.500s (Wall=1.556s) | SysUtil=50.5% | ThrUtil=50.5% | 46.69 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    916.25 ms (  440.5 us/tok | 60.76%)
   MoE AVX2 Q8 Expert Compute   :    370.10 ms (  177.9 us/tok | 24.54%)
   Router + Lookahead Dispatch  :     88.88 ms (   42.7 us/tok |  5.89%)
   LM Head Output Projection    :      6.95 ms (    3.3 us/tok |  0.46%)
   Foreground NVMe Sync Stall   :      8.23 ms (    4.0 us/tok |  0.55%)
   Unaccounted / OMP & Sampling :    117.59 ms (   56.5 us/tok |  7.80%) | Total Wall=1508.01 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.79%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.38%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.32%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    65.27%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.24%  |
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
    "ttft_ms": 247.16,
    "avg_tps": 663.53,
    "min_tps": 497.87,
    "max_tps": 793.21
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 132.27,
    "min_tps": 88.36,
    "max_tps": 161.02,
    "p50_ms": 7.64,
    "p90_ms": 8.32,
    "p99_ms": 11.32,
    "mean_ms": 7.56,
    "jitter_ms": 0.41
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
    "avg_mbs": 1567.96,
    "peak_mbs": 4445.04,
    "sync_wait_ms": 2.08,
    "async_overlap_ms": 3.93
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
    "dense_attention": 406.44,
    "moe_compute": 110.93,
    "router_lookahead": 7.71,
    "lm_head": 9.7,
    "unaccounted": 5.14
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 83.56,
    "ram_bandwidth_pinning": 1.73,
    "expert_cache_lrfu": 11.49,
    "lookahead_parallel_overlap": 2.07,
    "ssd_nvme_throughput": 1.15,
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
    "ttft_ms": 339.75,
    "avg_tps": 482.7,
    "min_tps": 337.83,
    "max_tps": 566.68
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 112.42,
    "min_tps": 103.65,
    "max_tps": 128.14,
    "p50_ms": 8.88,
    "p90_ms": 9.35,
    "p99_ms": 9.65,
    "mean_ms": 8.9,
    "jitter_ms": 0.24
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
    "avg_mbs": 2132.0,
    "peak_mbs": 6438.01,
    "sync_wait_ms": 5.84,
    "async_overlap_ms": 15.76
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
    "dense_attention": 388.82,
    "moe_compute": 224.88,
    "router_lookahead": 9.43,
    "lm_head": 10.41,
    "unaccounted": 47.3
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 81.24,
    "ram_bandwidth_pinning": 1.91,
    "expert_cache_lrfu": 9.2,
    "lookahead_parallel_overlap": 4.68,
    "ssd_nvme_throughput": 2.97,
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
Host CPU: INTEL(R) XEON(R) PLATINUM 8573C | Cores=2 Threads=4 | RAM=15.99 GB
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
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: glm53 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (0.009 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: 100.00% (0.01/0.01 GB) @ 15.5 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (46.470 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  10.76% (5.00/46.47 GB) @ 297.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  21.52% (10.00/46.47 GB) @ 242.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  32.28% (15.00/46.47 GB) @ 256.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  43.04% (20.00/46.47 GB) @ 251.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  53.80% (25.00/46.47 GB) @ 250.2 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  64.56% (30.00/46.47 GB) @ 246.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  75.32% (35.00/46.47 GB) @ 242.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  86.08% (40.00/46.47 GB) @ 245.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  96.84% (45.00/46.47 GB) @ 241.2 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf: 100.00% (46.47/46.47 GB) @ 241.0 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (45.866 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  10.90% (5.00/45.87 GB) @ 241.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  21.80% (10.00/45.87 GB) @ 235.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  32.70% (15.00/45.87 GB) @ 233.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  43.61% (20.00/45.87 GB) @ 248.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  54.51% (25.00/45.87 GB) @ 225.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  65.41% (30.00/45.87 GB) @ 228.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  76.31% (35.00/45.87 GB) @ 230.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  87.21% (40.00/45.87 GB) @ 231.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  98.11% (45.00/45.87 GB) @ 231.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf: 100.00% (45.87/45.87 GB) @ 229.8 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (2.506 GB) -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf: 100.00% (2.51/2.51 GB) @ 77.8 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=101,844,951,904 (94.85 GB) | Elapsed=438.29s
[Colibri-Import] Running baselines/colibri/c/tools/gguf_import.py on D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf -> D:/apex_d_drive/models/glm53 (--mode link)...
colibri model directory ready: D:\apex_d_drive\models\glm53  (glm5-next, 45 layers, mode link)
Verified Primary Shard 1 Path: D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (Alt Shard Dir: C:/apex_c_drive/models/glm53)
--------------------------------------------------------------------------------
 [Stage 1] Small Prompt (64 tokens) + 100.00% Greedy Parity & Prompt/Response Trace
--------------------------------------------------------------------------------
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (4) : [19, 13, 17, 5] -> "4.2&"
[Apex-Parity] Batched Tokens (4) : [19, 13, 17, 5] -> "4.2&"
[Apex-Parity] Model Architecture : glm5-next (GLM-5.3-Flash)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 4 / 4 (100.00% Parity)
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5184.38 MB (553 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=73.8% | NVMe=512.6 MB/s (47437.59 MB, QD=64) | RSS=13573.1 MB
[LIVE-DECODE] 2/32 tok | Avg=0.32 tps | Hit=73.8% (LA:+1.1%) | NVMe=512.8 MB/s (50457.65 MB) | RSS=13575.7 MB
[LIVE-DECODE] 4/32 tok | Avg=0.36 tps | Hit=73.9% (LA:+1.8%) | NVMe=512.9 MB/s (52765.34 MB) | RSS=13429.0 MB
[LIVE-DECODE] 6/32 tok | Avg=0.40 tps | Hit=74.1% (LA:+2.4%) | NVMe=513.1 MB/s (54681.46 MB) | RSS=13365.8 MB
[LIVE-DECODE] 8/32 tok | Avg=0.43 tps | Hit=74.2% (LA:+2.8%) | NVMe=513.8 MB/s (56327.27 MB) | RSS=13316.9 MB
[LIVE-DECODE] 10/32 tok | Avg=0.45 tps | Hit=74.4% (LA:+3.2%) | NVMe=514.6 MB/s (58041.65 MB) | RSS=13269.8 MB
[LIVE-DECODE] 12/32 tok | Avg=0.44 tps | Hit=74.5% (LA:+3.7%) | NVMe=515.1 MB/s (59835.96 MB) | RSS=13187.2 MB
[LIVE-DECODE] 14/32 tok | Avg=0.46 tps | Hit=74.6% (LA:+4.0%) | NVMe=516.7 MB/s (61677.90 MB) | RSS=13169.7 MB
[LIVE-DECODE] 16/32 tok | Avg=0.47 tps | Hit=74.6% (LA:+4.5%) | NVMe=518.3 MB/s (63736.84 MB) | RSS=13166.9 MB
[LIVE-DECODE] 18/32 tok | Avg=0.48 tps | Hit=74.8% (LA:+4.8%) | NVMe=519.7 MB/s (65502.65 MB) | RSS=13154.0 MB
[LIVE-DECODE] 20/32 tok | Avg=0.49 tps | Hit=74.8% (LA:+5.2%) | NVMe=521.1 MB/s (67410.34 MB) | RSS=13142.5 MB
[LIVE-DECODE] 22/32 tok | Avg=0.49 tps | Hit=74.9% (LA:+5.5%) | NVMe=522.2 MB/s (69269.21 MB) | RSS=13120.0 MB
[LIVE-DECODE] 24/32 tok | Avg=0.50 tps | Hit=75.0% (LA:+5.8%) | NVMe=523.6 MB/s (71126.59 MB) | RSS=13112.7 MB
[LIVE-DECODE] 26/32 tok | Avg=0.50 tps | Hit=75.1% (LA:+6.1%) | NVMe=524.9 MB/s (73014.09 MB) | RSS=13107.4 MB
[LIVE-DECODE] 28/32 tok | Avg=0.51 tps | Hit=75.2% (LA:+6.4%) | NVMe=526.0 MB/s (74890.96 MB) | RSS=13099.6 MB
[LIVE-DECODE] 30/32 tok | Avg=0.51 tps | Hit=75.2% (LA:+6.6%) | NVMe=527.4 MB/s (76793.52 MB) | RSS=13084.0 MB
[LIVE-DECODE] 32/32 tok | Avg=0.51 tps | Hit=75.3% (LA:+6.9%) | NVMe=528.5 MB/s (78681.84 MB) | RSS=13083.4 MB

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
   LRFU Cache / Staging Ring    : 5184.38 MB (553/12384 exp = 4.47% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=13083.39 MB | Peak=13661.22 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " a persistent CUDA stream pinned-memory pinned-memory pinned pinned-memory ring pinned pinned-memory pinned-memory pinned-memory-memory pinned-memory pinned pinned-memory pinned-memory-memory pinned pinned-memory-memory pinned"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=59.1% | AvgMargin=2.077 | MinMargin=0.033
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 129465.81 |  0 |  0 |  0 |     0.0 |
   |    2 |   24923 |  persistent    |   14.20 |   9.2% |     220 |   14.17 | 3147.57 | 18 |230 | 88 | 1546272.0 |
   |    3 |   54443 |  CUDA          |   14.65 |  11.4% |    9996 |   14.41 | 3147.57 |  0 |  0 |  0 | 1546272.0 |
   |    4 |    4269 |  stream        |   14.37 |  14.3% |   11292 |   13.81 | 2393.77 |100 |166 | 70 | 1181536.0 |
   |    5 |   47414 |  pinned        |   14.48 |  22.4% |   12675 |   13.14 | 2393.77 |  0 |  0 |  0 | 1181536.0 |
   |    6 |   63637 | -memory        |   18.96 |  91.2% |    3468 |   15.18 | 2019.67 |140 |145 | 51 | 981056.0 |
   |    7 |   47414 |  pinned        |   16.01 |  30.3% |    7314 |   15.09 | 2019.67 |  0 |  0 |  0 | 981056.0 |
   |    8 |   63637 | -memory        |   16.32 |  36.5% |   47414 |   15.67 | 1653.58 |185 | 95 | 56 | 842656.0 |
   |   12 |   10053 |  ring          |   15.22 |  15.0% |   47466 |   14.95 | 2442.15 |165 |118 | 53 | 918688.0 |
   |   13 |   47414 |  pinned        |   17.74 |  41.4% |    4147 |   16.65 | 2442.15 |  0 |  0 |  0 | 918688.0 |
   |   16 |   47414 |  pinned        |   16.87 |  71.1% |   25372 |   13.63 | 1905.99 |152 |111 | 73 | 1054176.0 |
   |   17 |   63637 | -memory        |   19.08 |  72.7% |   47414 |   17.80 | 1905.99 |  0 |  0 |  0 | 1054176.0 |
   |   30 |   47414 |  pinned        |   17.05 |  51.0% |   63637 |   16.85 | 1743.39 |184 | 83 | 69 | 974112.0 |
   |   31 |   63637 | -memory        |   21.56 |  94.1% |   47414 |   18.55 | 1743.39 |  0 |  0 |  0 | 974112.0 |
   |   32 |   63637 | -memory        |   17.13 |  66.4% |   47414 |   16.08 | 1733.37 |169 |102 | 65 | 966816.0 |
   |   33 |   47414 |  pinned        |   21.73 |  98.5% |   63637 |   16.47 | 1733.37 |  0 |  0 |  0 | 966816.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 129.466s, TTFT=129465.81ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:64t/0.5tps/74%
   Decode  (32 tok, 62.248s): Avg=0.51 | Min=0.32 | Max=0.60 tps
   Latency (ms) : Min=1653.58 | P10=1671.92 | P25=1736.62 | P50=1775.20 | P75=2019.67 | P90=2442.15 | P95=3147.57 | P99=3147.57 | Max=3147.57
   Mean/SD/Jitt : Mean=1945.26ms | StdDev=384.26ms | Jitter=117.83ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=18383 (68.39%) | Lookahead=1858 (+6.91%) | ColdMiss=6639 (24.70%) | EFF HIT=75.30%
   Lookahead    : 3222 prefetched -> 1858 consumed (57.7% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  352 |  77 | 211 | 67.0%|2070.00 | | L24 |  640 |  464 |  41 | 135 | 78.9%|1502.19 |
   | L04 |  640 |  332 |  40 | 268 | 58.1%|2659.38 | | L25 |  640 |  463 |  33 | 144 | 77.5%|1530.94 |
   | L05 |  640 |  349 |  53 | 238 | 62.8%|2371.88 | | L26 |  640 |  465 |  53 | 122 | 80.9%|1444.69 |
   | L06 |  640 |  374 |  62 | 204 | 68.1%|2120.31 | | L27 |  640 |  428 |  53 | 159 | 75.2%|1854.38 |
   | L07 |  640 |  402 |  64 | 174 | 72.8%|1854.38 | | L28 |  640 |  452 |  42 | 146 | 77.2%|1595.62 |
   | L08 |  640 |  416 |  37 | 187 | 70.8%|1969.38 | | L29 |  640 |  438 |  47 | 155 | 75.8%|1696.25 |
   | L09 |  640 |  375 |  45 | 220 | 65.6%|2213.75 | | L30 |  640 |  445 |  42 | 153 | 76.1%|1653.12 |
   | L10 |  640 |  383 |  44 | 213 | 66.7%|2084.38 | | L31 |  640 |  430 |  43 | 167 | 73.9%|1703.44 |
   | L11 |  640 |  416 |  48 | 176 | 72.5%|2409.38 | | L32 |  640 |  417 |  59 | 164 | 74.4%|1825.62 |
   | L12 |  640 |  433 |  46 | 161 | 74.8%|1959.75 | | L33 |  640 |  448 |  43 | 149 | 76.7%|1732.19 |
   | L13 |  640 |  440 |  45 | 155 | 75.8%|1645.94 | | L34 |  640 |  450 |  53 | 137 | 78.6%|1588.44 |
   | L14 |  640 |  454 |  32 | 154 | 75.9%|1653.12 | | L35 |  640 |  449 |  49 | 142 | 77.8%|1552.50 |
   | L15 |  640 |  452 |  32 | 156 | 75.6%|1566.88 | | L36 |  640 |  445 |  45 | 150 | 76.6%|1617.19 |
   | L16 |  640 |  457 |  47 | 136 | 78.8%|1502.19 | | L37 |  640 |  447 |  44 | 149 | 76.7%|1559.69 |
   | L17 |  640 |  452 |  37 | 151 | 76.4%|1574.06 | | L38 |  640 |  449 |  46 | 145 | 77.3%|1581.25 |
   | L18 |  640 |  473 |  35 | 132 | 79.4%|1459.06 | | L39 |  640 |  453 |  50 | 137 | 78.6%|1415.94 |
   | L19 |  640 |  463 |  35 | 142 | 77.8%|1509.38 | | L40 |  640 |  456 |  41 | 143 | 77.7%|1502.19 |
   | L20 |  640 |  462 |  40 | 138 | 78.4%|1581.25 | | L41 |  640 |  471 |  30 | 139 | 78.3%|1372.81 |
   | L21 |  640 |  464 |  51 | 125 | 80.5%|1466.25 | | L42 |  640 |  491 |  26 | 123 | 80.8%|1243.44 |
   | L22 |  640 |  466 |  46 | 128 | 80.0%|1487.81 | | L43 |  640 |  491 |  35 | 114 | 82.2%|1236.25 |
   | L23 |  640 |  437 |  39 | 164 | 74.4%|1796.88 | | L44 |  640 |  479 |  28 | 133 | 79.2%|1809.00 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 78681.84 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=31244.25 MB)
   SSD Data/Token (Decode)      : Avg=976.383 MB/tok (Min=822.906 | P50=943.750 | P95=1510.031 | Max=1510.031 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1329 Batches | 30986 Raw -> 30665 Merged (321 LBA Merges, Avg 2627.4 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=29786
   SSD Read Bandwidth (Active)  : Min=7.26 | Avg=528.50 | Peak=1411.40 MB/s | WallAmort=410.41 MB/s
   OS Kernel I/O Verification   : Read=78690.87 MB | Write=0.00 MB | Syscalls=34701
   Sync Stall vs Async DMA      : SyncStall=92931.18 ms | AsyncOverlapped=134375.24 ms (59.1% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=6.58 GB/s | WallAmort=2.54 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=129.47s (67.5%, 41075.75 MB SSD) | Decode=62.25s (32.5%, 31244.25 MB SSD)
   CPU Time & Utilization       : User=239.656s + Sys=8.141s (Wall=212.401s) | SysUtil=29.2% | ThrUtil=29.2% | 26.98 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  30620.95 ms (318968.3 us/tok | 15.97%)
   MoE AVX2 Q8 Expert Compute   :  42708.73 ms (444882.6 us/tok | 22.28%)
   Router + Lookahead Dispatch  :    671.39 ms ( 6993.6 us/tok |  0.35%)
   LM Head Output Projection    :    765.25 ms ( 7971.4 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :  92931.18 ms (968033.1 us/tok | 48.47%)
   Unaccounted / OMP & Sampling :  24016.71 ms (250174.0 us/tok | 12.53%) | Total Wall=191714.21 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    39.64%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    19.58%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.40%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     9.01%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.37%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 215s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.61 GB Available
   Active Drive Space : 219.98 GB Total / 127.45 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :     60.70 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2102.66 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4990.23 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7773.62 MB/s
   RND4K Q32T16 Read                  :    454.24 MB/s (  116285 IOPS)
   RND4K Q1T1  Read                   :    741.92 MB/s (Latency: 5.27 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     49.58 GB/s
   AVX2 256-bit Sequential Write BW   :     45.39 GB/s
   STREAM Triad (A = B + s*C) BW      :     44.47 GB/s
   Random Pointer-Chase Latency       :     44.03 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     44.67 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    185.46 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     15.69 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=73.6% | NVMe=515.1 MB/s (51661.71 MB, QD=64) | RSS=13957.0 MB

 >>> [Apex-Model-Response] <think>

Let me think through this carefully what's reasoning through the reasoning through the user's through the's through's through's through through's through's through's's through through's through's's through's through's through's through's through through's through's's through's through's through's through through's's
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
   Process RSS (Start/End/Peak) : Start=4.73 MB | End=13430.74 MB | Peak=14036.64 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (70 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "<think>

Let me think through this carefully what's reasoning through the reasoning through the user's through the's through's through's through through's through's through's's through through's through's's through's through's through's through's through through's through's's through's through's through's through through's's through"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=50.5% | AvgMargin=1.342 | MinMargin=0.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 143418.96 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   20.50 |  79.8% |   15724 |   19.10 | 3071.79 | 20 |233 | 83 | 1512544.0 |
   |    3 |    1339 | >\n\n          |   14.01 |  20.8% |     397 |   12.96 | 3071.79 |  0 |  0 |  0 | 1512544.0 |
   |    4 |   10056 | Let            |   15.28 |  31.5% |     334 |   14.78 | 2041.79 |142 |135 | 59 | 996096.0 |
   |    5 |     752 |  me            |   16.52 |  72.1% |     594 |   14.85 | 2041.79 |  0 |  0 |  0 | 996096.0 |
   |    6 |    1744 |  think         |   15.53 |  38.0% |   23578 |   13.60 | 2239.56 |120 |165 | 51 | 1075232.0 |
   |    7 |    1526 |  through       |   17.47 |  63.7% |   15504 |   14.79 | 2239.56 |  0 |  0 |  0 | 1075232.0 |
   |    8 |     419 |  this          |   17.34 |  55.6% |     279 |   16.09 | 2310.82 |107 |172 | 57 | 1147072.0 |
   |    9 |   15504 |  carefully     |   14.89 |   6.9% |    3019 |   14.71 | 2310.82 |  0 |  0 |  0 | 1147072.0 |
   |   12 |   32559 |  reasoning     |   14.05 |   8.5% |    1681 |   14.01 | 2106.20 |124 |156 | 56 | 1064640.0 |
   |   13 |    1526 |  through       |   16.95 |  33.1% |    1128 |   15.76 | 2106.20 |  0 |  0 |  0 | 1064640.0 |
   |   10 |    1128 |  what          |   16.98 |  28.3% |      13 |   16.45 | 2104.65 |117 |177 | 42 | 1061216.0 |
   |   62 |    1526 |  through       |   17.43 |  49.9% |     594 |   17.31 | 1854.82 |180 | 70 | 86 | 1031744.0 |
   |   63 |     594 | 's             |   21.37 |  93.3% |    1526 |   17.99 | 1854.82 |  0 |  0 |  0 | 1031744.0 |
   |   64 |     594 | 's             |   17.28 |  49.5% |    1526 |   17.16 | 2049.20 |159 |103 | 74 | 1097120.0 |
   |   65 |    1526 |  through       |   21.46 |  88.7% |     594 |   18.70 | 2049.20 |  0 |  0 |  0 | 1097120.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 143.419s, TTFT=143418.96ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:70t/0.5tps/74%
   Decode  (64 tok, 119.283s): Avg=0.54 | Min=0.33 | Max=0.75 tps
   Latency (ms) : Min=1328.56 | P10=1521.08 | P25=1693.19 | P50=1854.82 | P75=2034.89 | P90=2106.20 | P95=2310.82 | P99=3071.79 | Max=3071.79
   Mean/SD/Jitt : Mean=1863.80ms | StdDev=319.52ms | Jitter=102.37ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=22529 (65.74%) | Lookahead=3701 (+10.80%) | ColdMiss=8042 (23.47%) | EFF HIT=76.53%
   Lookahead    : 6474 prefetched -> 3701 consumed (57.2% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64= 76.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  475 | 131 | 210 | 74.3%|2450.94 | | L24 |  816 |  579 |  83 | 154 | 81.1%|2170.62 |
   | L04 |  816 |  442 |  75 | 299 | 63.4%|3450.00 | | L25 |  816 |  569 |  62 | 185 | 77.3%|2371.88 |
   | L05 |  816 |  441 | 104 | 271 | 66.8%|3291.88 | | L26 |  816 |  554 |  90 | 172 | 78.9%|2307.19 |
   | L06 |  816 |  479 |  99 | 238 | 70.8%|2846.25 | | L27 |  816 |  538 | 103 | 175 | 78.6%|2515.62 |
   | L07 |  816 |  498 | 120 | 198 | 75.7%|2645.00 | | L28 |  816 |  518 | 103 | 195 | 76.1%|2587.50 |
   | L08 |  816 |  516 |  59 | 241 | 70.5%|3040.31 | | L29 |  816 |  531 |  98 | 187 | 77.1%|2522.81 |
   | L09 |  816 |  457 |  95 | 264 | 67.6%|3212.81 | | L30 |  816 |  532 |  78 | 206 | 74.8%|2508.44 |
   | L10 |  816 |  473 | 107 | 236 | 71.1%|2954.06 | | L31 |  816 |  514 | 107 | 195 | 76.1%|2637.81 |
   | L11 |  816 |  469 | 104 | 243 | 70.2%|4087.50 | | L32 |  816 |  513 | 119 | 184 | 77.5%|2666.56 |
   | L12 |  816 |  526 |  73 | 217 | 73.4%|3115.50 | | L33 |  816 |  573 |  86 | 157 | 80.8%|2206.56 |
   | L13 |  816 |  552 |  71 | 193 | 76.3%|2371.88 | | L34 |  816 |  513 | 120 | 183 | 77.6%|2522.81 |
   | L14 |  816 |  541 |  67 | 208 | 74.5%|2731.25 | | L35 |  816 |  527 | 116 | 173 | 78.8%|2400.62 |
   | L15 |  816 |  540 | 100 | 176 | 78.4%|2386.25 | | L36 |  816 |  533 | 103 | 180 | 77.9%|2379.06 |
   | L16 |  816 |  554 |  75 | 187 | 77.1%|2278.44 | | L37 |  816 |  553 |  93 | 170 | 79.2%|2206.56 |
   | L17 |  816 |  558 |  53 | 205 | 74.9%|2364.69 | | L38 |  816 |  567 |  85 | 164 | 79.9%|2213.75 |
   | L18 |  816 |  597 |  60 | 159 | 80.5%|2127.50 | | L39 |  816 |  546 | 101 | 169 | 79.3%|2185.00 |
   | L19 |  816 |  582 |  70 | 164 | 79.9%|2070.00 | | L40 |  816 |  496 | 109 | 211 | 74.1%|2910.94 |
   | L20 |  816 |  617 |  54 | 145 | 82.2%|1796.88 | | L41 |  816 |  546 |  94 | 176 | 78.4%|2314.38 |
   | L21 |  816 |  592 |  72 | 152 | 81.4%|2055.62 | | L42 |  816 |  593 |  59 | 164 | 79.9%|2077.19 |
   | L22 |  816 |  582 |  69 | 165 | 79.8%|2314.38 | | L43 |  816 |  596 |  69 | 151 | 81.5%|2105.94 |
   | L23 |  816 |  582 |  80 | 154 | 81.1%|1983.75 | | L44 |  816 |  565 |  85 | 166 | 79.7%|2730.25 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 113051.59 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=61389.88 MB)
   SSD Data/Token (Decode)      : Avg=959.217 MB/tok (Min=682.781 | P50=972.750 | P95=1120.188 | Max=1477.094 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2507 Batches | 45029 Raw -> 44520 Merged (509 LBA Merges, Avg 2600.3 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=43641
   SSD Read Bandwidth (Active)  : Min=42.24 | Avg=536.70 | Peak=1348.69 MB/s | WallAmort=430.34 MB/s (100.0% of 60.7 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=114038.62 MB | Write=128.00 MB | Syscalls=56094
   Sync Stall vs Async DMA      : SyncStall=112649.63 ms | AsyncOverlapped=196191.27 ms (63.5% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=7.62 GB/s (17.1% STREAM) | WallAmort=2.96 GB/s (Max=44.47 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=143.42s (54.6%, 45299.88 MB SSD) | Decode=119.28s (45.4%, 61389.88 MB SSD)
   CPU Time & Utilization       : User=317.453s + Sys=11.000s (Wall=286.056s) | SysUtil=28.7% | ThrUtil=28.7% | 53.24 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  42137.08 ms (314455.8 us/tok | 16.04%)
   MoE AVX2 Q8 Expert Compute   :  58352.63 ms (435467.4 us/tok | 22.21%)
   Router + Lookahead Dispatch  :    917.50 ms ( 6847.0 us/tok |  0.35%)
   LM Head Output Projection    :   1475.78 ms (11013.3 us/tok |  0.56%)
   Foreground NVMe Sync Stall   : 112649.63 ms (840668.9 us/tok | 42.88%)
   Unaccounted / OMP & Sampling :  47169.59 ms (352011.9 us/tok | 17.96%) | Total Wall=262702.21 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    36.26%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    22.94%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.79%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     9.40%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.61%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5662.50 MB (604 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.80 tps | Avg=0.80 tps | Hit=89.2% | NVMe=519.0 MB/s (74277.59 MB, QD=64) | RSS=14138.2 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.78 tps | Avg=0.79 tps | Hit=88.9% | NVMe=524.1 MB/s (145202.09 MB, QD=64) | RSS=14138.9 MB
[LIVE-DECODE] 2/128 tok | Avg=0.29 tps | Hit=88.9% (LA:+0.1%) | NVMe=523.9 MB/s (148375.09 MB) | RSS=14073.1 MB
[LIVE-DECODE] 4/128 tok | Avg=0.33 tps | Hit=88.9% (LA:+0.2%) | NVMe=523.7 MB/s (150769.90 MB) | RSS=13864.8 MB
[LIVE-DECODE] 6/128 tok | Avg=0.36 tps | Hit=88.9% (LA:+0.3%) | NVMe=523.7 MB/s (152946.34 MB) | RSS=13736.7 MB
[LIVE-DECODE] 8/128 tok | Avg=0.38 tps | Hit=88.8% (LA:+0.3%) | NVMe=523.7 MB/s (155002.59 MB) | RSS=13683.0 MB
[LIVE-DECODE] 10/128 tok | Avg=0.38 tps | Hit=88.8% (LA:+0.4%) | NVMe=522.9 MB/s (157265.65 MB) | RSS=13625.3 MB
[LIVE-DECODE] 12/128 tok | Avg=0.40 tps | Hit=88.8% (LA:+0.5%) | NVMe=522.8 MB/s (159313.46 MB) | RSS=13562.2 MB
[LIVE-DECODE] 14/128 tok | Avg=0.40 tps | Hit=88.8% (LA:+0.6%) | NVMe=522.8 MB/s (161543.96 MB) | RSS=13562.2 MB
[LIVE-DECODE] 16/128 tok | Avg=0.41 tps | Hit=88.8% (LA:+0.7%) | NVMe=522.7 MB/s (163557.59 MB) | RSS=13562.2 MB
[LIVE-DECODE] 18/128 tok | Avg=0.41 tps | Hit=88.8% (LA:+0.7%) | NVMe=523.0 MB/s (165889.34 MB) | RSS=13562.2 MB
[LIVE-DECODE] 20/128 tok | Avg=0.41 tps | Hit=88.7% (LA:+0.8%) | NVMe=523.1 MB/s (168218.15 MB) | RSS=13562.2 MB
[LIVE-DECODE] 22/128 tok | Avg=0.42 tps | Hit=88.7% (LA:+0.9%) | NVMe=523.4 MB/s (170186.90 MB) | RSS=13556.7 MB
[LIVE-DECODE] 24/128 tok | Avg=0.43 tps | Hit=88.7% (LA:+1.0%) | NVMe=523.6 MB/s (172007.34 MB) | RSS=13556.7 MB
[LIVE-DECODE] 26/128 tok | Avg=0.43 tps | Hit=88.7% (LA:+1.0%) | NVMe=523.4 MB/s (174119.46 MB) | RSS=13556.7 MB
[LIVE-DECODE] 28/128 tok | Avg=0.44 tps | Hit=88.7% (LA:+1.1%) | NVMe=523.7 MB/s (176232.77 MB) | RSS=13552.8 MB
[LIVE-DECODE] 30/128 tok | Avg=0.44 tps | Hit=88.7% (LA:+1.2%) | NVMe=524.1 MB/s (178233.27 MB) | RSS=13562.1 MB
[LIVE-DECODE] 32/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+1.2%) | NVMe=524.6 MB/s (179953.59 MB) | RSS=13562.1 MB
[LIVE-DECODE] 34/128 tok | Avg=0.45 tps | Hit=88.6% (LA:+1.3%) | NVMe=524.9 MB/s (181666.77 MB) | RSS=13562.2 MB
[LIVE-DECODE] 36/128 tok | Avg=0.45 tps | Hit=88.6% (LA:+1.3%) | NVMe=524.3 MB/s (183952.34 MB) | RSS=13562.2 MB
[LIVE-DECODE] 38/128 tok | Avg=0.45 tps | Hit=88.6% (LA:+1.4%) | NVMe=524.5 MB/s (186025.77 MB) | RSS=13562.2 MB
[LIVE-DECODE] 40/128 tok | Avg=0.46 tps | Hit=88.6% (LA:+1.5%) | NVMe=524.8 MB/s (187957.71 MB) | RSS=13562.2 MB
[LIVE-DECODE] 42/128 tok | Avg=0.46 tps | Hit=88.6% (LA:+1.5%) | NVMe=525.0 MB/s (189816.02 MB) | RSS=13552.8 MB
[LIVE-DECODE] 44/128 tok | Avg=0.46 tps | Hit=88.6% (LA:+1.6%) | NVMe=525.3 MB/s (191970.52 MB) | RSS=13562.2 MB
[LIVE-DECODE] 46/128 tok | Avg=0.46 tps | Hit=88.5% (LA:+1.6%) | NVMe=525.7 MB/s (194041.90 MB) | RSS=13562.2 MB
[LIVE-DECODE] 48/128 tok | Avg=0.46 tps | Hit=88.5% (LA:+1.7%) | NVMe=525.7 MB/s (196143.84 MB) | RSS=13562.2 MB
[LIVE-DECODE] 50/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+1.8%) | NVMe=526.0 MB/s (197980.46 MB) | RSS=13562.2 MB
[LIVE-DECODE] 52/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+1.8%) | NVMe=526.2 MB/s (199856.34 MB) | RSS=13562.2 MB
[LIVE-DECODE] 54/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+1.9%) | NVMe=526.4 MB/s (201766.46 MB) | RSS=13552.8 MB
[LIVE-DECODE] 56/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+1.9%) | NVMe=526.6 MB/s (203841.40 MB) | RSS=13552.8 MB
[LIVE-DECODE] 58/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+2.0%) | NVMe=526.9 MB/s (205741.34 MB) | RSS=13552.8 MB
[LIVE-DECODE] 60/128 tok | Avg=0.47 tps | Hit=88.4% (LA:+2.0%) | NVMe=526.9 MB/s (207934.52 MB) | RSS=13552.8 MB
[LIVE-DECODE] 62/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.1%) | NVMe=527.1 MB/s (209670.02 MB) | RSS=13552.8 MB
[LIVE-DECODE] 64/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.2%) | NVMe=527.2 MB/s (211475.02 MB) | RSS=13562.2 MB
[LIVE-DECODE] 66/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.2%) | NVMe=527.4 MB/s (213491.09 MB) | RSS=13562.2 MB
[LIVE-DECODE] 68/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.3%) | NVMe=527.7 MB/s (215310.34 MB) | RSS=13562.1 MB
[LIVE-DECODE] 70/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.3%) | NVMe=528.0 MB/s (217115.34 MB) | RSS=13571.5 MB
[LIVE-DECODE] 72/128 tok | Avg=0.49 tps | Hit=88.4% (LA:+2.4%) | NVMe=528.3 MB/s (218810.52 MB) | RSS=13571.5 MB
[LIVE-DECODE] 74/128 tok | Avg=0.49 tps | Hit=88.4% (LA:+2.4%) | NVMe=528.7 MB/s (220456.09 MB) | RSS=13571.5 MB
[LIVE-DECODE] 76/128 tok | Avg=0.49 tps | Hit=88.4% (LA:+2.4%) | NVMe=529.0 MB/s (222227.46 MB) | RSS=13571.5 MB
[LIVE-DECODE] 78/128 tok | Avg=0.49 tps | Hit=88.4% (LA:+2.5%) | NVMe=529.4 MB/s (223995.21 MB) | RSS=13571.5 MB
[LIVE-DECODE] 80/128 tok | Avg=0.49 tps | Hit=88.3% (LA:+2.5%) | NVMe=529.8 MB/s (225960.40 MB) | RSS=13571.5 MB
[LIVE-DECODE] 82/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.6%) | NVMe=530.2 MB/s (227846.96 MB) | RSS=13571.5 MB
[LIVE-DECODE] 84/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.6%) | NVMe=530.5 MB/s (229637.27 MB) | RSS=13545.2 MB
[LIVE-DECODE] 86/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.7%) | NVMe=530.8 MB/s (231484.09 MB) | RSS=13545.2 MB
[LIVE-DECODE] 88/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.7%) | NVMe=531.1 MB/s (233218.09 MB) | RSS=13552.8 MB
[LIVE-DECODE] 90/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.7%) | NVMe=531.4 MB/s (235255.46 MB) | RSS=13552.8 MB
[LIVE-DECODE] 92/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.8%) | NVMe=531.8 MB/s (236989.52 MB) | RSS=13552.8 MB
[LIVE-DECODE] 94/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.8%) | NVMe=532.1 MB/s (238764.52 MB) | RSS=13552.8 MB
[LIVE-DECODE] 96/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.8%) | NVMe=532.3 MB/s (240356.71 MB) | RSS=13552.8 MB
[LIVE-DECODE] 98/128 tok | Avg=0.51 tps | Hit=88.2% (LA:+2.9%) | NVMe=532.6 MB/s (242024.40 MB) | RSS=13552.8 MB
[LIVE-DECODE] 100/128 tok | Avg=0.51 tps | Hit=88.2% (LA:+2.9%) | NVMe=532.8 MB/s (243694.65 MB) | RSS=13552.8 MB
[LIVE-DECODE] 102/128 tok | Avg=0.51 tps | Hit=88.2% (LA:+2.9%) | NVMe=533.1 MB/s (245291.15 MB) | RSS=13552.8 MB
[LIVE-DECODE] 104/128 tok | Avg=0.52 tps | Hit=88.2% (LA:+3.0%) | NVMe=533.4 MB/s (246708.65 MB) | RSS=13552.8 MB
[LIVE-DECODE] 106/128 tok | Avg=0.52 tps | Hit=88.2% (LA:+3.0%) | NVMe=533.6 MB/s (249058.15 MB) | RSS=13534.0 MB
[LIVE-DECODE] 108/128 tok | Avg=0.52 tps | Hit=88.2% (LA:+3.0%) | NVMe=533.9 MB/s (250802.40 MB) | RSS=13534.0 MB
[LIVE-DECODE] 110/128 tok | Avg=0.52 tps | Hit=88.2% (LA:+3.1%) | NVMe=533.9 MB/s (252921.59 MB) | RSS=13552.8 MB
[LIVE-DECODE] 112/128 tok | Avg=0.51 tps | Hit=88.2% (LA:+3.1%) | NVMe=533.9 MB/s (255220.90 MB) | RSS=13571.5 MB
[LIVE-DECODE] 114/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.2%) | NVMe=534.0 MB/s (257063.27 MB) | RSS=13571.5 MB
[LIVE-DECODE] 116/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.2%) | NVMe=534.1 MB/s (258761.46 MB) | RSS=13571.5 MB
[LIVE-DECODE] 118/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.3%) | NVMe=534.1 MB/s (260589.27 MB) | RSS=13571.5 MB
[LIVE-DECODE] 120/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.3%) | NVMe=534.2 MB/s (262409.15 MB) | RSS=13562.2 MB
[LIVE-DECODE] 122/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.4%) | NVMe=534.4 MB/s (264056.52 MB) | RSS=13562.2 MB
[LIVE-DECODE] 124/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.4%) | NVMe=534.5 MB/s (265737.27 MB) | RSS=13562.2 MB
[LIVE-DECODE] 126/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.5%) | NVMe=534.5 MB/s (267382.77 MB) | RSS=13562.2 MB
[LIVE-DECODE] 128/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.5%) | NVMe=534.6 MB/s (268885.21 MB) | RSS=13562.2 MB

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
   LRFU Cache / Staging Ring    : 5662.50 MB (604/12384 exp = 4.88% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.70 MB | End=13562.19 MB | Peak=14240.24 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : " single coal-coalescededed LB- LBQD32 NV-read-and-GE-and-register-and register-and-and register-blocked-blocked-blocked-blocked multi-registered-blocked-block-blocked multi- multi-blocked multi-row multi-row-block multi-row-row-row-row-row AVAVXAVAVX2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2--2-2-2 QD2Q8Q8K_KKGEKKKKGE"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=58.3% | AvgMargin=2.122 | MinMargin=0.001
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 648255.06 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   21.27 |  96.3% |    1062 |   17.44 | 3492.96 | 46 |159 |131 | 1624576.0 |
   |    3 |   22412 | -co            |   14.00 |  19.9% |   11492 |   13.04 | 3492.96 |  0 |  0 |  0 | 1624576.0 |
   |    4 |    3831 | ales           |   20.23 |  56.4% |     278 |   19.95 | 2612.73 | 96 |166 | 74 | 1226144.0 |
   |    5 |    1998 | ced            |   23.84 |  95.9% |    6125 |   20.05 | 2612.73 |  0 |  0 |  0 | 1226144.0 |
   |    6 |     291 | ed             |   13.00 |  12.2% |      11 |   12.82 | 2250.94 |124 |147 | 65 | 1114336.0 |
   |    7 |     291 | ed             |   17.54 |  71.5% |   11492 |   15.78 | 2250.94 |  0 |  0 |  0 | 1114336.0 |
   |    8 |   39929 |  LB            |   16.46 |  74.9% |      11 |   14.17 | 2118.97 |154 |121 | 61 | 1052800.0 |
   |   10 |   39929 |  LB            |   12.87 |  15.0% |  154842 |   12.02 | 2535.00 |123 |138 | 75 | 1158688.0 |
   |   11 |      48 | Q              |   13.97 |  36.6% |   11492 |   12.83 | 2535.00 |  0 |  0 |  0 | 1158688.0 |
   |   36 |   34735 | registered     |   13.64 |  25.3% |   29819 |   12.17 | 2511.34 |127 |135 | 74 | 1170208.0 |
   |   37 |    9421 | -block         |   19.78 |  98.2% |    2504 |   13.99 | 2511.34 |  0 |  0 |  0 | 1170208.0 |
   |  126 |   10772 | GE             |   14.45 |  16.7% |    2646 |   14.40 | 1667.87 |199 | 88 | 49 | 842496.0 |
   |  127 |   50127 | KK             |   13.12 |  16.3% |      42 |   12.88 | 1667.87 |  0 |  0 |  0 | 842496.0 |
   |  128 |   50127 | KK             |   14.93 |  24.1% |      42 |   14.93 | 1535.08 |212 | 84 | 40 | 769248.0 |
   |  129 |   10772 | GE             |   18.90 |  83.6% |   22197 |   15.87 | 1535.08 |  0 |  0 |  0 | 769248.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 648.255s, TTFT=648255.06ms): Avg=0.79 | Min=0.78 | Max=0.80 tps
   Prefill Chunks (2): C1:256t/0.8tps/89% | C2:256t/0.8tps/89%
   Decode  (128 tok, 244.797s): Avg=0.52 | Min=0.29 | Max=0.74 tps
   Latency (ms) : Min=1344.59 | P10=1563.59 | P25=1667.87 | P50=1832.18 | P75=2116.50 | P90=2303.30 | P95=2511.34 | P99=3492.96 | Max=3492.96
   Mean/SD/Jitt : Mean=1912.47ms | StdDev=341.43ms | Jitter=108.93ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=163757 (84.61%) | Lookahead=6790 (+3.51%) | ColdMiss=22989 (11.88%) | EFF HIT=88.12%
   Lookahead    : 12736 prefetched -> 6790 consumed (53.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 88.8% | @64= 88.4% | @128= 88.1% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3720 | 331 | 557 | 87.9%|6382.50 | | L24 | 4608 | 4015 | 123 | 470 | 89.8%|4995.31 |
   | L04 | 4608 | 3817 | 131 | 660 | 85.7%|7475.00 | | L25 | 4608 | 3934 | 135 | 539 | 88.3%|6346.56 |
   | L05 | 4608 | 3768 | 173 | 667 | 85.5%|7367.19 | | L26 | 4608 | 3964 | 147 | 497 | 89.2%|5534.38 |
   | L06 | 4608 | 3760 | 218 | 630 | 86.3%|7151.56 | | L27 | 4608 | 3874 | 162 | 572 | 87.6%|6756.25 |
   | L07 | 4608 | 3883 | 200 | 525 | 88.6%|5807.50 | | L28 | 4608 | 3851 | 189 | 568 | 87.7%|6396.88 |
   | L08 | 4608 | 3886 | 135 | 587 | 87.3%|6842.50 | | L29 | 4608 | 3889 | 195 | 524 | 88.6%|5929.69 |
   | L09 | 4608 | 3865 | 157 | 586 | 87.3%|6253.12 | | L30 | 4608 | 3819 | 190 | 599 | 87.0%|6727.50 |
   | L10 | 4608 | 3849 | 146 | 613 | 86.7%|6332.19 | | L31 | 4608 | 3847 | 134 | 627 | 86.4%|6935.94 |
   | L11 | 4608 | 3879 | 169 | 560 | 87.8%|8493.75 | | L32 | 4608 | 3817 | 157 | 634 | 86.2%|6907.19 |
   | L12 | 4608 | 3910 | 158 | 540 | 88.3%|6842.38 | | L33 | 4608 | 3829 | 190 | 589 | 87.2%|6971.88 |
   | L13 | 4608 | 3961 | 133 | 514 | 88.8%|5599.06 | | L34 | 4608 | 3855 | 229 | 524 | 88.6%|6202.81 |
   | L14 | 4608 | 3977 | 109 | 522 | 88.7%|5649.38 | | L35 | 4608 | 3814 | 226 | 568 | 87.7%|6626.88 |
   | L15 | 4608 | 3935 | 135 | 538 | 88.3%|5807.50 | | L36 | 4608 | 3813 | 255 | 540 | 88.3%|6382.50 |
   | L16 | 4608 | 3940 | 157 | 511 | 88.9%|5599.06 | | L37 | 4608 | 3907 | 175 | 526 | 88.6%|5584.69 |
   | L17 | 4608 | 3920 | 120 | 568 | 87.7%|6245.94 | | L38 | 4608 | 3884 | 185 | 539 | 88.3%|6152.50 |
   | L18 | 4608 | 3997 | 107 | 504 | 89.1%|5656.56 | | L39 | 4608 | 3862 | 202 | 544 | 88.2%|6044.69 |
   | L19 | 4608 | 3987 | 132 | 489 | 89.4%|5541.56 | | L40 | 4608 | 3876 | 176 | 556 | 87.9%|6210.00 |
   | L20 | 4608 | 3983 | 129 | 496 | 89.2%|5376.25 | | L41 | 4608 | 3960 | 138 | 510 | 88.9%|5476.88 |
   | L21 | 4608 | 3987 | 149 | 472 | 89.8%|5175.00 | | L42 | 4608 | 4017 | 102 | 489 | 89.4%|5397.81 |
   | L22 | 4608 | 3997 | 126 | 485 | 89.5%|5412.19 | | L43 | 4608 | 4030 | 112 | 466 | 89.9%|4980.94 |
   | L23 | 4608 | 3936 | 135 | 537 | 88.3%|5893.75 | | L44 | 4608 | 3943 | 118 | 547 | 88.1%|7294.62 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 268885.21 MB (Load=6361.84 | Prefill=138840.25 | Warmup=0.00 | Decode=123683.12 MB)
   SSD Data/Token (Decode)      : Avg=966.274 MB/tok (Min=708.750 | P50=937.938 | P95=1165.875 | Max=1586.500 MB) | Prefill=271.172 MB/tok
   NVMe Batches / Requests      : 5144 Batches | 109067 Raw -> 107702 Merged (1365 LBA Merges, Avg 2556.5 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=106823
   SSD Read Bandwidth (Active)  : Min=38.34 | Avg=534.60 | Peak=1471.81 MB/s | WallAmort=301.09 MB/s
   OS Kernel I/O Verification   : Read=268894.24 MB | Write=0.01 MB | Syscalls=111787
   Sync Stall vs Async DMA      : SyncStall=322985.86 ms | AsyncOverlapped=488364.19 ms (60.2% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=5.89 GB/s | WallAmort=3.12 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=648.26s (72.6%, 138840.25 MB SSD) | Decode=244.80s (27.4%, 123683.12 MB SSD)
   CPU Time & Utilization       : User=1609.688s + Sys=24.109s (Wall=914.706s) | SysUtil=44.7% | ThrUtil=44.7% | 41.30 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 211373.49 ms (330271.1 us/tok | 23.67%)
   MoE AVX2 Q8 Expert Compute   : 258319.32 ms (403623.9 us/tok | 28.93%)
   Router + Lookahead Dispatch  :   4587.56 ms ( 7168.1 us/tok |  0.51%)
   LM Head Output Projection    :   3009.78 ms ( 4702.8 us/tok |  0.34%)
   Foreground NVMe Sync Stall   : 322985.86 ms (504665.4 us/tok | 36.17%)
   Unaccounted / OMP & Sampling :  92775.58 ms (144961.9 us/tok | 10.39%) | Total Wall=893051.60 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    58.97%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.08%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    16.95%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     9.71%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.29%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 115683.6ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='\nSummarize LBACoalesce in one sentence.\nSummarize LB'
[Stage 3] /v1/chat/completions (stream=true SSE) 46124.5ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5568.75 MB (594 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=0.80 tps | Avg=0.80 tps | Hit=89.2% | NVMe=518.7 MB/s (74277.59 MB, QD=64) | RSS=14045.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=0.79 tps | Avg=0.79 tps | Hit=88.9% | NVMe=524.6 MB/s (145295.52 MB, QD=64) | RSS=14045.2 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=0.79 tps | Avg=0.79 tps | Hit=88.9% | NVMe=526.3 MB/s (214799.34 MB, QD=64) | RSS=14045.2 MB
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 843K Nov 13 15:22 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 843K Nov 13 15:22 build/apex.exe
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
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.42 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :     56.97 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2119.41 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4991.50 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7704.04 MB/s
   RND4K Q32T16 Read                  :    518.58 MB/s (  132757 IOPS)
   RND4K Q1T1  Read                   :    787.15 MB/s (Latency: 4.96 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     46.59 GB/s
   AVX2 256-bit Sequential Write BW   :     40.49 GB/s
   STREAM Triad (A = B + s*C) BW      :     30.12 GB/s
   Random Pointer-Chase Latency       :     50.48 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     38.43 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    189.55 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     17.14 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1349.92 tps | Avg=1349.92 tps | Hit=99.5% | NVMe=1784.0 MB/s (6.19 MB, QD=64) | RSS=71.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1251.52 tps | Avg=1298.86 tps | Hit=99.5% | NVMe=1741.0 MB/s (7.01 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1089.75 tps | Avg=1220.78 tps | Hit=99.5% | NVMe=1690.8 MB/s (7.78 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=960.65 tps | Avg=1143.37 tps | Hit=99.5% | NVMe=1666.8 MB/s (8.61 MB, QD=64) | RSS=71.9 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=853.18 tps | Avg=1070.55 tps | Hit=99.5% | NVMe=1653.1 MB/s (9.33 MB, QD=64) | RSS=72.2 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=792.87 tps | Avg=1011.51 tps | Hit=99.5% | NVMe=1638.8 MB/s (10.06 MB, QD=64) | RSS=72.4 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=716.71 tps | Avg=955.37 tps | Hit=99.5% | NVMe=1612.7 MB/s (10.83 MB, QD=64) | RSS=72.7 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=648.22 tps | Avg=901.95 tps | Hit=99.5% | NVMe=1578.4 MB/s (11.60 MB, QD=64) | RSS=72.9 MB
[LIVE-DECODE] 8/32 tok | Avg=167.30 tps | Hit=99.5% (LA:+0.0%) | NVMe=1532.9 MB/s (12.43 MB) | RSS=73.0 MB
[LIVE-DECODE] 16/32 tok | Avg=172.65 tps | Hit=99.5% (LA:+0.1%) | NVMe=1514.2 MB/s (13.10 MB) | RSS=73.0 MB
[LIVE-DECODE] 24/32 tok | Avg=174.35 tps | Hit=99.5% (LA:+0.1%) | NVMe=1506.9 MB/s (13.25 MB) | RSS=73.0 MB
[LIVE-DECODE] 32/32 tok | Avg=174.73 tps | Hit=99.5% (LA:+0.1%) | NVMe=1499.0 MB/s (13.30 MB) | RSS=73.0 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=72.96 MB | Peak=72.96 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2270.64 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    6.40 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    6.40 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.99 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.99 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.62 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.62 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.90 | 11 |  1 |  0 |    49.5 |
   |    9 |      68 | tok_68         |  176.71 | 100.0% |     228 |  144.43 |    5.90 |  0 |  0 |  0 |    49.5 |
   |   24 |     246 | tok_246        |  204.37 |  99.2% |      55 |  199.55 |    5.82 | 11 |  1 |  0 |     0.0 |
   |   25 |     229 | tok_229        |  171.20 | 100.0% |      70 |  154.08 |    5.82 |  0 |  0 |  0 |     0.0 |
   |   28 |     246 | tok_246        |  194.87 | 100.0% |      54 |  173.43 |    5.78 | 12 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.62 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.62 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.57 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.57 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.271s, TTFT=2270.64ms): Avg=901.95 | Min=648.22 | Max=1349.92 tps
   Prefill Chunks (8): C1:256t/1349.9tps/99% | C2:256t/1251.5tps/99% | C3:256t/1089.7tps/99% | C4:256t/960.6tps/99%
                       C5:256t/853.2tps/99% | C6:256t/792.9tps/99% | C7:256t/716.7tps/99% | C8:256t/648.2tps/99%
   Decode  (32 tok, 0.183s): Avg=174.73 | Min=156.16 | Max=188.75 tps
   Latency (ms) : Min=5.30 | P10=5.44 | P25=5.62 | P50=5.69 | P75=5.82 | P90=5.99 | P95=6.40 | P99=6.40 | Max=6.40
   Mean/SD/Jitt : Mean=5.72ms | StdDev=0.24ms | Jitter=0.10ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=218.34 | Avg=1499.01 | Peak=4562.04 MB/s | WallAmort=5.42 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=5.85 ms | AsyncOverlapped=7.37 ms (55.8% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.62 GB/s | WallAmort=0.58 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.27s (92.5%, 6.19 MB SSD) | Decode=0.18s (7.5%, 1.69 MB SSD)
   CPU Time & Utilization       : User=3.062s + Sys=0.594s (Wall=2.483s) | SysUtil=36.8% | ThrUtil=36.8% | 34.05 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2055.81 ms (  988.4 us/tok | 83.78%)
   MoE AVX2 Q8 Expert Compute   :    257.01 ms (  123.6 us/tok | 10.47%)
   Router + Lookahead Dispatch  :     61.28 ms (   29.5 us/tok |  2.50%)
   LM Head Output Projection    :      7.16 ms (    3.4 us/tok |  0.29%)
   Foreground NVMe Sync Stall   :      5.85 ms (    2.8 us/tok |  0.24%)
   Unaccounted / OMP & Sampling :     66.67 ms (   32.1 us/tok |  2.72%) | Total Wall=2453.78 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    24.39%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.14%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.45%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    71.26%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.76%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1851.83 tps | Avg=1851.83 tps | Hit=99.2% | NVMe=2232.3 MB/s (24.91 MB, QD=64) | RSS=89.0 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1752.34 tps | Avg=1800.71 tps | Hit=99.2% | NVMe=2949.1 MB/s (42.92 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1763.29 tps | Avg=1788.06 tps | Hit=99.2% | NVMe=3402.9 MB/s (61.04 MB, QD=64) | RSS=89.6 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1644.17 tps | Avg=1749.78 tps | Hit=99.2% | NVMe=3639.7 MB/s (79.10 MB, QD=64) | RSS=89.9 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1576.85 tps | Avg=1712.22 tps | Hit=99.2% | NVMe=3859.5 MB/s (97.14 MB, QD=64) | RSS=90.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1460.00 tps | Avg=1664.30 tps | Hit=99.2% | NVMe=4064.3 MB/s (115.20 MB, QD=64) | RSS=90.8 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1391.23 tps | Avg=1618.91 tps | Hit=99.2% | NVMe=4213.5 MB/s (133.27 MB, QD=64) | RSS=91.3 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1278.46 tps | Avg=1566.76 tps | Hit=99.2% | NVMe=4347.8 MB/s (151.30 MB, QD=64) | RSS=91.6 MB
[LIVE-DECODE] 8/32 tok | Avg=157.71 tps | Hit=99.2% (LA:+0.0%) | NVMe=4257.1 MB/s (152.70 MB) | RSS=91.6 MB
[LIVE-DECODE] 16/32 tok | Avg=157.94 tps | Hit=99.2% (LA:+0.1%) | NVMe=4223.6 MB/s (153.28 MB) | RSS=91.6 MB
[LIVE-DECODE] 24/32 tok | Avg=159.84 tps | Hit=99.2% (LA:+0.1%) | NVMe=4156.7 MB/s (154.23 MB) | RSS=91.6 MB
[LIVE-DECODE] 32/32 tok | Avg=159.33 tps | Hit=99.2% (LA:+0.1%) | NVMe=4108.1 MB/s (155.14 MB) | RSS=91.6 MB

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
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=91.63 MB | Peak=91.63 MB
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
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 | 1307.16 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    6.25 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    6.25 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    6.50 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    6.50 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    6.29 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    6.29 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    6.33 | 16 |  0 |  0 |    32.0 |
   |   12 |     254 | qtok_254       |   71.67 |  96.6% |      66 |   68.21 |    6.48 | 16 |  0 |  0 |    32.0 |
   |   13 |     129 | qtok_129       |   76.30 |  99.3% |      49 |   71.12 |    6.48 |  0 |  0 |  0 |    32.0 |
   |   14 |      68 | qtok_68        |   60.97 |  98.8% |      36 |   56.50 |    6.33 | 12 |  4 |  0 |   143.0 |
   |   15 |     209 | qtok_209       |   94.05 |  99.5% |      49 |   88.77 |    6.33 |  0 |  0 |  0 |   143.0 |
   |   30 |     254 | qtok_254       |   58.92 |  92.7% |      49 |   56.39 |    6.36 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    6.36 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.75 |  64.8% |     229 |   52.56 |    6.38 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    6.38 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.307s, TTFT=1307.16ms): Avg=1566.76 | Min=1278.46 | Max=1851.83 tps
   Prefill Chunks (8): C1:256t/1851.8tps/99% | C2:256t/1752.3tps/99% | C3:256t/1763.3tps/99% | C4:256t/1644.2tps/99%
                       C5:256t/1576.9tps/99% | C6:256t/1460.0tps/99% | C7:256t/1391.2tps/99% | C8:256t/1278.5tps/99%
   Decode  (32 tok, 0.201s): Avg=159.33 | Min=153.96 | Max=166.34 tps
   Latency (ms) : Min=6.01 | P10=6.06 | P25=6.22 | P50=6.29 | P75=6.36 | P90=6.48 | P95=6.50 | P99=6.50 | Max=6.50
   Mean/SD/Jitt : Mean=6.28ms | StdDev=0.13ms | Jitter=0.06ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=395.33 | Avg=4108.13 | Peak=7628.76 MB/s | WallAmort=102.88 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=8.23 ms | AsyncOverlapped=36.12 ms (81.4% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.63 GB/s | WallAmort=1.39 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.31s (86.7%, 144.44 MB SSD) | Decode=0.20s (13.3%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.641s + Sys=0.500s (Wall=1.556s) | SysUtil=50.5% | ThrUtil=50.5% | 46.69 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    916.25 ms (  440.5 us/tok | 60.76%)
   MoE AVX2 Q8 Expert Compute   :    370.10 ms (  177.9 us/tok | 24.54%)
   Router + Lookahead Dispatch  :     88.88 ms (   42.7 us/tok |  5.89%)
   LM Head Output Projection    :      6.95 ms (    3.3 us/tok |  0.46%)
   Foreground NVMe Sync Stall   :      8.23 ms (    4.0 us/tok |  0.55%)
   Unaccounted / OMP & Sampling :    117.59 ms (   56.5 us/tok |  7.80%) | Total Wall=1508.01 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.79%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.38%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.32%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    65.27%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.24%  |
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
    "ttft_ms": 247.16,
    "avg_tps": 663.53,
    "min_tps": 497.87,
    "max_tps": 793.21
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 132.27,
    "min_tps": 88.36,
    "max_tps": 161.02,
    "p50_ms": 7.64,
    "p90_ms": 8.32,
    "p99_ms": 11.32,
    "mean_ms": 7.56,
    "jitter_ms": 0.41
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
    "avg_mbs": 1567.96,
    "peak_mbs": 4445.04,
    "sync_wait_ms": 2.08,
    "async_overlap_ms": 3.93
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
    "dense_attention": 406.44,
    "moe_compute": 110.93,
    "router_lookahead": 7.71,
    "lm_head": 9.7,
    "unaccounted": 5.14
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 83.56,
    "ram_bandwidth_pinning": 1.73,
    "expert_cache_lrfu": 11.49,
    "lookahead_parallel_overlap": 2.07,
    "ssd_nvme_throughput": 1.15,
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
    "ttft_ms": 339.75,
    "avg_tps": 482.7,
    "min_tps": 337.83,
    "max_tps": 566.68
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 112.42,
    "min_tps": 103.65,
    "max_tps": 128.14,
    "p50_ms": 8.88,
    "p90_ms": 9.35,
    "p99_ms": 9.65,
    "mean_ms": 8.9,
    "jitter_ms": 0.24
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
    "avg_mbs": 2132.0,
    "peak_mbs": 6438.01,
    "sync_wait_ms": 5.84,
    "async_overlap_ms": 15.76
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
    "dense_attention": 388.82,
    "moe_compute": 224.88,
    "router_lookahead": 9.43,
    "lm_head": 10.41,
    "unaccounted": 47.3
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 81.24,
    "ram_bandwidth_pinning": 1.91,
    "expert_cache_lrfu": 9.2,
    "lookahead_parallel_overlap": 4.68,
    "ssd_nvme_throughput": 2.97,
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
Host CPU: INTEL(R) XEON(R) PLATINUM 8573C | Cores=2 Threads=4 | RAM=15.99 GB
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

### 📄 `04_glm53_stage1_parity.log`
```text
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Serial  Tokens (4) : [19, 13, 17, 5] -> "4.2&"
[Apex-Parity] Batched Tokens (4) : [19, 13, 17, 5] -> "4.2&"
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
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.61 GB Available
   Active Drive Space : 219.98 GB Total / 127.45 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :     60.70 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2102.66 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4990.23 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7773.62 MB/s
   RND4K Q32T16 Read                  :    454.24 MB/s (  116285 IOPS)
   RND4K Q1T1  Read                   :    741.92 MB/s (Latency: 5.27 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     49.58 GB/s
   AVX2 256-bit Sequential Write BW   :     45.39 GB/s
   STREAM Triad (A = B + s*C) BW      :     44.47 GB/s
   Random Pointer-Chase Latency       :     44.03 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     44.67 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    185.46 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     15.69 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=73.6% | NVMe=515.1 MB/s (51661.71 MB, QD=64) | RSS=13957.0 MB

 >>> [Apex-Model-Response] <think>

Let me think through this carefully what's reasoning through the reasoning through the user's through the's through's through's through through's through's through's's through through's through's's through's through's through's through's through through's through's's through's through's through's through through's's
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
   Process RSS (Start/End/Peak) : Start=4.73 MB | End=13430.74 MB | Peak=14036.64 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (70 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "<think>

Let me think through this carefully what's reasoning through the reasoning through the user's through the's through's through's through through's through's through's's through through's through's's through's through's through's through's through through's through's's through's through's through's through through's's through"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=50.5% | AvgMargin=1.342 | MinMargin=0.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 143418.96 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   20.50 |  79.8% |   15724 |   19.10 | 3071.79 | 20 |233 | 83 | 1512544.0 |
   |    3 |    1339 | >\n\n          |   14.01 |  20.8% |     397 |   12.96 | 3071.79 |  0 |  0 |  0 | 1512544.0 |
   |    4 |   10056 | Let            |   15.28 |  31.5% |     334 |   14.78 | 2041.79 |142 |135 | 59 | 996096.0 |
   |    5 |     752 |  me            |   16.52 |  72.1% |     594 |   14.85 | 2041.79 |  0 |  0 |  0 | 996096.0 |
   |    6 |    1744 |  think         |   15.53 |  38.0% |   23578 |   13.60 | 2239.56 |120 |165 | 51 | 1075232.0 |
   |    7 |    1526 |  through       |   17.47 |  63.7% |   15504 |   14.79 | 2239.56 |  0 |  0 |  0 | 1075232.0 |
   |    8 |     419 |  this          |   17.34 |  55.6% |     279 |   16.09 | 2310.82 |107 |172 | 57 | 1147072.0 |
   |    9 |   15504 |  carefully     |   14.89 |   6.9% |    3019 |   14.71 | 2310.82 |  0 |  0 |  0 | 1147072.0 |
   |   12 |   32559 |  reasoning     |   14.05 |   8.5% |    1681 |   14.01 | 2106.20 |124 |156 | 56 | 1064640.0 |
   |   13 |    1526 |  through       |   16.95 |  33.1% |    1128 |   15.76 | 2106.20 |  0 |  0 |  0 | 1064640.0 |
   |   10 |    1128 |  what          |   16.98 |  28.3% |      13 |   16.45 | 2104.65 |117 |177 | 42 | 1061216.0 |
   |   62 |    1526 |  through       |   17.43 |  49.9% |     594 |   17.31 | 1854.82 |180 | 70 | 86 | 1031744.0 |
   |   63 |     594 | 's             |   21.37 |  93.3% |    1526 |   17.99 | 1854.82 |  0 |  0 |  0 | 1031744.0 |
   |   64 |     594 | 's             |   17.28 |  49.5% |    1526 |   17.16 | 2049.20 |159 |103 | 74 | 1097120.0 |
   |   65 |    1526 |  through       |   21.46 |  88.7% |     594 |   18.70 | 2049.20 |  0 |  0 |  0 | 1097120.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 143.419s, TTFT=143418.96ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:70t/0.5tps/74%
   Decode  (64 tok, 119.283s): Avg=0.54 | Min=0.33 | Max=0.75 tps
   Latency (ms) : Min=1328.56 | P10=1521.08 | P25=1693.19 | P50=1854.82 | P75=2034.89 | P90=2106.20 | P95=2310.82 | P99=3071.79 | Max=3071.79
   Mean/SD/Jitt : Mean=1863.80ms | StdDev=319.52ms | Jitter=102.37ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=22529 (65.74%) | Lookahead=3701 (+10.80%) | ColdMiss=8042 (23.47%) | EFF HIT=76.53%
   Lookahead    : 6474 prefetched -> 3701 consumed (57.2% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64= 76.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  475 | 131 | 210 | 74.3%|2450.94 | | L24 |  816 |  579 |  83 | 154 | 81.1%|2170.62 |
   | L04 |  816 |  442 |  75 | 299 | 63.4%|3450.00 | | L25 |  816 |  569 |  62 | 185 | 77.3%|2371.88 |
   | L05 |  816 |  441 | 104 | 271 | 66.8%|3291.88 | | L26 |  816 |  554 |  90 | 172 | 78.9%|2307.19 |
   | L06 |  816 |  479 |  99 | 238 | 70.8%|2846.25 | | L27 |  816 |  538 | 103 | 175 | 78.6%|2515.62 |
   | L07 |  816 |  498 | 120 | 198 | 75.7%|2645.00 | | L28 |  816 |  518 | 103 | 195 | 76.1%|2587.50 |
   | L08 |  816 |  516 |  59 | 241 | 70.5%|3040.31 | | L29 |  816 |  531 |  98 | 187 | 77.1%|2522.81 |
   | L09 |  816 |  457 |  95 | 264 | 67.6%|3212.81 | | L30 |  816 |  532 |  78 | 206 | 74.8%|2508.44 |
   | L10 |  816 |  473 | 107 | 236 | 71.1%|2954.06 | | L31 |  816 |  514 | 107 | 195 | 76.1%|2637.81 |
   | L11 |  816 |  469 | 104 | 243 | 70.2%|4087.50 | | L32 |  816 |  513 | 119 | 184 | 77.5%|2666.56 |
   | L12 |  816 |  526 |  73 | 217 | 73.4%|3115.50 | | L33 |  816 |  573 |  86 | 157 | 80.8%|2206.56 |
   | L13 |  816 |  552 |  71 | 193 | 76.3%|2371.88 | | L34 |  816 |  513 | 120 | 183 | 77.6%|2522.81 |
   | L14 |  816 |  541 |  67 | 208 | 74.5%|2731.25 | | L35 |  816 |  527 | 116 | 173 | 78.8%|2400.62 |
   | L15 |  816 |  540 | 100 | 176 | 78.4%|2386.25 | | L36 |  816 |  533 | 103 | 180 | 77.9%|2379.06 |
   | L16 |  816 |  554 |  75 | 187 | 77.1%|2278.44 | | L37 |  816 |  553 |  93 | 170 | 79.2%|2206.56 |
   | L17 |  816 |  558 |  53 | 205 | 74.9%|2364.69 | | L38 |  816 |  567 |  85 | 164 | 79.9%|2213.75 |
   | L18 |  816 |  597 |  60 | 159 | 80.5%|2127.50 | | L39 |  816 |  546 | 101 | 169 | 79.3%|2185.00 |
   | L19 |  816 |  582 |  70 | 164 | 79.9%|2070.00 | | L40 |  816 |  496 | 109 | 211 | 74.1%|2910.94 |
   | L20 |  816 |  617 |  54 | 145 | 82.2%|1796.88 | | L41 |  816 |  546 |  94 | 176 | 78.4%|2314.38 |
   | L21 |  816 |  592 |  72 | 152 | 81.4%|2055.62 | | L42 |  816 |  593 |  59 | 164 | 79.9%|2077.19 |
   | L22 |  816 |  582 |  69 | 165 | 79.8%|2314.38 | | L43 |  816 |  596 |  69 | 151 | 81.5%|2105.94 |
   | L23 |  816 |  582 |  80 | 154 | 81.1%|1983.75 | | L44 |  816 |  565 |  85 | 166 | 79.7%|2730.25 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 113051.59 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=61389.88 MB)
   SSD Data/Token (Decode)      : Avg=959.217 MB/tok (Min=682.781 | P50=972.750 | P95=1120.188 | Max=1477.094 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2507 Batches | 45029 Raw -> 44520 Merged (509 LBA Merges, Avg 2600.3 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=43641
   SSD Read Bandwidth (Active)  : Min=42.24 | Avg=536.70 | Peak=1348.69 MB/s | WallAmort=430.34 MB/s (100.0% of 60.7 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=114038.62 MB | Write=128.00 MB | Syscalls=56094
   Sync Stall vs Async DMA      : SyncStall=112649.63 ms | AsyncOverlapped=196191.27 ms (63.5% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=7.62 GB/s (17.1% STREAM) | WallAmort=2.96 GB/s (Max=44.47 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=143.42s (54.6%, 45299.88 MB SSD) | Decode=119.28s (45.4%, 61389.88 MB SSD)
   CPU Time & Utilization       : User=317.453s + Sys=11.000s (Wall=286.056s) | SysUtil=28.7% | ThrUtil=28.7% | 53.24 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  42137.08 ms (314455.8 us/tok | 16.04%)
   MoE AVX2 Q8 Expert Compute   :  58352.63 ms (435467.4 us/tok | 22.21%)
   Router + Lookahead Dispatch  :    917.50 ms ( 6847.0 us/tok |  0.35%)
   LM Head Output Projection    :   1475.78 ms (11013.3 us/tok |  0.56%)
   Foreground NVMe Sync Stall   : 112649.63 ms (840668.9 us/tok | 42.88%)
   Unaccounted / OMP & Sampling :  47169.59 ms (352011.9 us/tok | 17.96%) | Total Wall=262702.21 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    36.26%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    22.94%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.79%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     9.40%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.61%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_glm53_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5184.38 MB (553 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=73.8% | NVMe=512.6 MB/s (47437.59 MB, QD=64) | RSS=13573.1 MB
[LIVE-DECODE] 2/32 tok | Avg=0.32 tps | Hit=73.8% (LA:+1.1%) | NVMe=512.8 MB/s (50457.65 MB) | RSS=13575.7 MB
[LIVE-DECODE] 4/32 tok | Avg=0.36 tps | Hit=73.9% (LA:+1.8%) | NVMe=512.9 MB/s (52765.34 MB) | RSS=13429.0 MB
[LIVE-DECODE] 6/32 tok | Avg=0.40 tps | Hit=74.1% (LA:+2.4%) | NVMe=513.1 MB/s (54681.46 MB) | RSS=13365.8 MB
[LIVE-DECODE] 8/32 tok | Avg=0.43 tps | Hit=74.2% (LA:+2.8%) | NVMe=513.8 MB/s (56327.27 MB) | RSS=13316.9 MB
[LIVE-DECODE] 10/32 tok | Avg=0.45 tps | Hit=74.4% (LA:+3.2%) | NVMe=514.6 MB/s (58041.65 MB) | RSS=13269.8 MB
[LIVE-DECODE] 12/32 tok | Avg=0.44 tps | Hit=74.5% (LA:+3.7%) | NVMe=515.1 MB/s (59835.96 MB) | RSS=13187.2 MB
[LIVE-DECODE] 14/32 tok | Avg=0.46 tps | Hit=74.6% (LA:+4.0%) | NVMe=516.7 MB/s (61677.90 MB) | RSS=13169.7 MB
[LIVE-DECODE] 16/32 tok | Avg=0.47 tps | Hit=74.6% (LA:+4.5%) | NVMe=518.3 MB/s (63736.84 MB) | RSS=13166.9 MB
[LIVE-DECODE] 18/32 tok | Avg=0.48 tps | Hit=74.8% (LA:+4.8%) | NVMe=519.7 MB/s (65502.65 MB) | RSS=13154.0 MB
[LIVE-DECODE] 20/32 tok | Avg=0.49 tps | Hit=74.8% (LA:+5.2%) | NVMe=521.1 MB/s (67410.34 MB) | RSS=13142.5 MB
[LIVE-DECODE] 22/32 tok | Avg=0.49 tps | Hit=74.9% (LA:+5.5%) | NVMe=522.2 MB/s (69269.21 MB) | RSS=13120.0 MB
[LIVE-DECODE] 24/32 tok | Avg=0.50 tps | Hit=75.0% (LA:+5.8%) | NVMe=523.6 MB/s (71126.59 MB) | RSS=13112.7 MB
[LIVE-DECODE] 26/32 tok | Avg=0.50 tps | Hit=75.1% (LA:+6.1%) | NVMe=524.9 MB/s (73014.09 MB) | RSS=13107.4 MB
[LIVE-DECODE] 28/32 tok | Avg=0.51 tps | Hit=75.2% (LA:+6.4%) | NVMe=526.0 MB/s (74890.96 MB) | RSS=13099.6 MB
[LIVE-DECODE] 30/32 tok | Avg=0.51 tps | Hit=75.2% (LA:+6.6%) | NVMe=527.4 MB/s (76793.52 MB) | RSS=13084.0 MB
[LIVE-DECODE] 32/32 tok | Avg=0.51 tps | Hit=75.3% (LA:+6.9%) | NVMe=528.5 MB/s (78681.84 MB) | RSS=13083.4 MB

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
   LRFU Cache / Staging Ring    : 5184.38 MB (553/12384 exp = 4.47% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=13083.39 MB | Peak=13661.22 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " a persistent CUDA stream pinned-memory pinned-memory pinned pinned-memory ring pinned pinned-memory pinned-memory pinned-memory-memory pinned-memory pinned pinned-memory pinned-memory-memory pinned pinned-memory-memory pinned"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=59.1% | AvgMargin=2.077 | MinMargin=0.033
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 129465.81 |  0 |  0 |  0 |     0.0 |
   |    2 |   24923 |  persistent    |   14.20 |   9.2% |     220 |   14.17 | 3147.57 | 18 |230 | 88 | 1546272.0 |
   |    3 |   54443 |  CUDA          |   14.65 |  11.4% |    9996 |   14.41 | 3147.57 |  0 |  0 |  0 | 1546272.0 |
   |    4 |    4269 |  stream        |   14.37 |  14.3% |   11292 |   13.81 | 2393.77 |100 |166 | 70 | 1181536.0 |
   |    5 |   47414 |  pinned        |   14.48 |  22.4% |   12675 |   13.14 | 2393.77 |  0 |  0 |  0 | 1181536.0 |
   |    6 |   63637 | -memory        |   18.96 |  91.2% |    3468 |   15.18 | 2019.67 |140 |145 | 51 | 981056.0 |
   |    7 |   47414 |  pinned        |   16.01 |  30.3% |    7314 |   15.09 | 2019.67 |  0 |  0 |  0 | 981056.0 |
   |    8 |   63637 | -memory        |   16.32 |  36.5% |   47414 |   15.67 | 1653.58 |185 | 95 | 56 | 842656.0 |
   |   12 |   10053 |  ring          |   15.22 |  15.0% |   47466 |   14.95 | 2442.15 |165 |118 | 53 | 918688.0 |
   |   13 |   47414 |  pinned        |   17.74 |  41.4% |    4147 |   16.65 | 2442.15 |  0 |  0 |  0 | 918688.0 |
   |   16 |   47414 |  pinned        |   16.87 |  71.1% |   25372 |   13.63 | 1905.99 |152 |111 | 73 | 1054176.0 |
   |   17 |   63637 | -memory        |   19.08 |  72.7% |   47414 |   17.80 | 1905.99 |  0 |  0 |  0 | 1054176.0 |
   |   30 |   47414 |  pinned        |   17.05 |  51.0% |   63637 |   16.85 | 1743.39 |184 | 83 | 69 | 974112.0 |
   |   31 |   63637 | -memory        |   21.56 |  94.1% |   47414 |   18.55 | 1743.39 |  0 |  0 |  0 | 974112.0 |
   |   32 |   63637 | -memory        |   17.13 |  66.4% |   47414 |   16.08 | 1733.37 |169 |102 | 65 | 966816.0 |
   |   33 |   47414 |  pinned        |   21.73 |  98.5% |   63637 |   16.47 | 1733.37 |  0 |  0 |  0 | 966816.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 129.466s, TTFT=129465.81ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:64t/0.5tps/74%
   Decode  (32 tok, 62.248s): Avg=0.51 | Min=0.32 | Max=0.60 tps
   Latency (ms) : Min=1653.58 | P10=1671.92 | P25=1736.62 | P50=1775.20 | P75=2019.67 | P90=2442.15 | P95=3147.57 | P99=3147.57 | Max=3147.57
   Mean/SD/Jitt : Mean=1945.26ms | StdDev=384.26ms | Jitter=117.83ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=18383 (68.39%) | Lookahead=1858 (+6.91%) | ColdMiss=6639 (24.70%) | EFF HIT=75.30%
   Lookahead    : 3222 prefetched -> 1858 consumed (57.7% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  352 |  77 | 211 | 67.0%|2070.00 | | L24 |  640 |  464 |  41 | 135 | 78.9%|1502.19 |
   | L04 |  640 |  332 |  40 | 268 | 58.1%|2659.38 | | L25 |  640 |  463 |  33 | 144 | 77.5%|1530.94 |
   | L05 |  640 |  349 |  53 | 238 | 62.8%|2371.88 | | L26 |  640 |  465 |  53 | 122 | 80.9%|1444.69 |
   | L06 |  640 |  374 |  62 | 204 | 68.1%|2120.31 | | L27 |  640 |  428 |  53 | 159 | 75.2%|1854.38 |
   | L07 |  640 |  402 |  64 | 174 | 72.8%|1854.38 | | L28 |  640 |  452 |  42 | 146 | 77.2%|1595.62 |
   | L08 |  640 |  416 |  37 | 187 | 70.8%|1969.38 | | L29 |  640 |  438 |  47 | 155 | 75.8%|1696.25 |
   | L09 |  640 |  375 |  45 | 220 | 65.6%|2213.75 | | L30 |  640 |  445 |  42 | 153 | 76.1%|1653.12 |
   | L10 |  640 |  383 |  44 | 213 | 66.7%|2084.38 | | L31 |  640 |  430 |  43 | 167 | 73.9%|1703.44 |
   | L11 |  640 |  416 |  48 | 176 | 72.5%|2409.38 | | L32 |  640 |  417 |  59 | 164 | 74.4%|1825.62 |
   | L12 |  640 |  433 |  46 | 161 | 74.8%|1959.75 | | L33 |  640 |  448 |  43 | 149 | 76.7%|1732.19 |
   | L13 |  640 |  440 |  45 | 155 | 75.8%|1645.94 | | L34 |  640 |  450 |  53 | 137 | 78.6%|1588.44 |
   | L14 |  640 |  454 |  32 | 154 | 75.9%|1653.12 | | L35 |  640 |  449 |  49 | 142 | 77.8%|1552.50 |
   | L15 |  640 |  452 |  32 | 156 | 75.6%|1566.88 | | L36 |  640 |  445 |  45 | 150 | 76.6%|1617.19 |
   | L16 |  640 |  457 |  47 | 136 | 78.8%|1502.19 | | L37 |  640 |  447 |  44 | 149 | 76.7%|1559.69 |
   | L17 |  640 |  452 |  37 | 151 | 76.4%|1574.06 | | L38 |  640 |  449 |  46 | 145 | 77.3%|1581.25 |
   | L18 |  640 |  473 |  35 | 132 | 79.4%|1459.06 | | L39 |  640 |  453 |  50 | 137 | 78.6%|1415.94 |
   | L19 |  640 |  463 |  35 | 142 | 77.8%|1509.38 | | L40 |  640 |  456 |  41 | 143 | 77.7%|1502.19 |
   | L20 |  640 |  462 |  40 | 138 | 78.4%|1581.25 | | L41 |  640 |  471 |  30 | 139 | 78.3%|1372.81 |
   | L21 |  640 |  464 |  51 | 125 | 80.5%|1466.25 | | L42 |  640 |  491 |  26 | 123 | 80.8%|1243.44 |
   | L22 |  640 |  466 |  46 | 128 | 80.0%|1487.81 | | L43 |  640 |  491 |  35 | 114 | 82.2%|1236.25 |
   | L23 |  640 |  437 |  39 | 164 | 74.4%|1796.88 | | L44 |  640 |  479 |  28 | 133 | 79.2%|1809.00 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 78681.84 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=31244.25 MB)
   SSD Data/Token (Decode)      : Avg=976.383 MB/tok (Min=822.906 | P50=943.750 | P95=1510.031 | Max=1510.031 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1329 Batches | 30986 Raw -> 30665 Merged (321 LBA Merges, Avg 2627.4 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=29786
   SSD Read Bandwidth (Active)  : Min=7.26 | Avg=528.50 | Peak=1411.40 MB/s | WallAmort=410.41 MB/s
   OS Kernel I/O Verification   : Read=78690.87 MB | Write=0.00 MB | Syscalls=34701
   Sync Stall vs Async DMA      : SyncStall=92931.18 ms | AsyncOverlapped=134375.24 ms (59.1% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=6.58 GB/s | WallAmort=2.54 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=129.47s (67.5%, 41075.75 MB SSD) | Decode=62.25s (32.5%, 31244.25 MB SSD)
   CPU Time & Utilization       : User=239.656s + Sys=8.141s (Wall=212.401s) | SysUtil=29.2% | ThrUtil=29.2% | 26.98 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  30620.95 ms (318968.3 us/tok | 15.97%)
   MoE AVX2 Q8 Expert Compute   :  42708.73 ms (444882.6 us/tok | 22.28%)
   Router + Lookahead Dispatch  :    671.39 ms ( 6993.6 us/tok |  0.35%)
   LM Head Output Projection    :    765.25 ms ( 7971.4 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :  92931.18 ms (968033.1 us/tok | 48.47%)
   Unaccounted / OMP & Sampling :  24016.71 ms (250174.0 us/tok | 12.53%) | Total Wall=191714.21 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    39.64%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    19.58%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.40%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     9.01%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.37%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_glm53_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5662.50 MB (604 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.80 tps | Avg=0.80 tps | Hit=89.2% | NVMe=519.0 MB/s (74277.59 MB, QD=64) | RSS=14138.2 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.78 tps | Avg=0.79 tps | Hit=88.9% | NVMe=524.1 MB/s (145202.09 MB, QD=64) | RSS=14138.9 MB
[LIVE-DECODE] 2/128 tok | Avg=0.29 tps | Hit=88.9% (LA:+0.1%) | NVMe=523.9 MB/s (148375.09 MB) | RSS=14073.1 MB
[LIVE-DECODE] 4/128 tok | Avg=0.33 tps | Hit=88.9% (LA:+0.2%) | NVMe=523.7 MB/s (150769.90 MB) | RSS=13864.8 MB
[LIVE-DECODE] 6/128 tok | Avg=0.36 tps | Hit=88.9% (LA:+0.3%) | NVMe=523.7 MB/s (152946.34 MB) | RSS=13736.7 MB
[LIVE-DECODE] 8/128 tok | Avg=0.38 tps | Hit=88.8% (LA:+0.3%) | NVMe=523.7 MB/s (155002.59 MB) | RSS=13683.0 MB
[LIVE-DECODE] 10/128 tok | Avg=0.38 tps | Hit=88.8% (LA:+0.4%) | NVMe=522.9 MB/s (157265.65 MB) | RSS=13625.3 MB
[LIVE-DECODE] 12/128 tok | Avg=0.40 tps | Hit=88.8% (LA:+0.5%) | NVMe=522.8 MB/s (159313.46 MB) | RSS=13562.2 MB
[LIVE-DECODE] 14/128 tok | Avg=0.40 tps | Hit=88.8% (LA:+0.6%) | NVMe=522.8 MB/s (161543.96 MB) | RSS=13562.2 MB
[LIVE-DECODE] 16/128 tok | Avg=0.41 tps | Hit=88.8% (LA:+0.7%) | NVMe=522.7 MB/s (163557.59 MB) | RSS=13562.2 MB
[LIVE-DECODE] 18/128 tok | Avg=0.41 tps | Hit=88.8% (LA:+0.7%) | NVMe=523.0 MB/s (165889.34 MB) | RSS=13562.2 MB
[LIVE-DECODE] 20/128 tok | Avg=0.41 tps | Hit=88.7% (LA:+0.8%) | NVMe=523.1 MB/s (168218.15 MB) | RSS=13562.2 MB
[LIVE-DECODE] 22/128 tok | Avg=0.42 tps | Hit=88.7% (LA:+0.9%) | NVMe=523.4 MB/s (170186.90 MB) | RSS=13556.7 MB
[LIVE-DECODE] 24/128 tok | Avg=0.43 tps | Hit=88.7% (LA:+1.0%) | NVMe=523.6 MB/s (172007.34 MB) | RSS=13556.7 MB
[LIVE-DECODE] 26/128 tok | Avg=0.43 tps | Hit=88.7% (LA:+1.0%) | NVMe=523.4 MB/s (174119.46 MB) | RSS=13556.7 MB
[LIVE-DECODE] 28/128 tok | Avg=0.44 tps | Hit=88.7% (LA:+1.1%) | NVMe=523.7 MB/s (176232.77 MB) | RSS=13552.8 MB
[LIVE-DECODE] 30/128 tok | Avg=0.44 tps | Hit=88.7% (LA:+1.2%) | NVMe=524.1 MB/s (178233.27 MB) | RSS=13562.1 MB
[LIVE-DECODE] 32/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+1.2%) | NVMe=524.6 MB/s (179953.59 MB) | RSS=13562.1 MB
[LIVE-DECODE] 34/128 tok | Avg=0.45 tps | Hit=88.6% (LA:+1.3%) | NVMe=524.9 MB/s (181666.77 MB) | RSS=13562.2 MB
[LIVE-DECODE] 36/128 tok | Avg=0.45 tps | Hit=88.6% (LA:+1.3%) | NVMe=524.3 MB/s (183952.34 MB) | RSS=13562.2 MB
[LIVE-DECODE] 38/128 tok | Avg=0.45 tps | Hit=88.6% (LA:+1.4%) | NVMe=524.5 MB/s (186025.77 MB) | RSS=13562.2 MB
[LIVE-DECODE] 40/128 tok | Avg=0.46 tps | Hit=88.6% (LA:+1.5%) | NVMe=524.8 MB/s (187957.71 MB) | RSS=13562.2 MB
[LIVE-DECODE] 42/128 tok | Avg=0.46 tps | Hit=88.6% (LA:+1.5%) | NVMe=525.0 MB/s (189816.02 MB) | RSS=13552.8 MB
[LIVE-DECODE] 44/128 tok | Avg=0.46 tps | Hit=88.6% (LA:+1.6%) | NVMe=525.3 MB/s (191970.52 MB) | RSS=13562.2 MB
[LIVE-DECODE] 46/128 tok | Avg=0.46 tps | Hit=88.5% (LA:+1.6%) | NVMe=525.7 MB/s (194041.90 MB) | RSS=13562.2 MB
[LIVE-DECODE] 48/128 tok | Avg=0.46 tps | Hit=88.5% (LA:+1.7%) | NVMe=525.7 MB/s (196143.84 MB) | RSS=13562.2 MB
[LIVE-DECODE] 50/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+1.8%) | NVMe=526.0 MB/s (197980.46 MB) | RSS=13562.2 MB
[LIVE-DECODE] 52/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+1.8%) | NVMe=526.2 MB/s (199856.34 MB) | RSS=13562.2 MB
[LIVE-DECODE] 54/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+1.9%) | NVMe=526.4 MB/s (201766.46 MB) | RSS=13552.8 MB
[LIVE-DECODE] 56/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+1.9%) | NVMe=526.6 MB/s (203841.40 MB) | RSS=13552.8 MB
[LIVE-DECODE] 58/128 tok | Avg=0.47 tps | Hit=88.5% (LA:+2.0%) | NVMe=526.9 MB/s (205741.34 MB) | RSS=13552.8 MB
[LIVE-DECODE] 60/128 tok | Avg=0.47 tps | Hit=88.4% (LA:+2.0%) | NVMe=526.9 MB/s (207934.52 MB) | RSS=13552.8 MB
[LIVE-DECODE] 62/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.1%) | NVMe=527.1 MB/s (209670.02 MB) | RSS=13552.8 MB
[LIVE-DECODE] 64/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.2%) | NVMe=527.2 MB/s (211475.02 MB) | RSS=13562.2 MB
[LIVE-DECODE] 66/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.2%) | NVMe=527.4 MB/s (213491.09 MB) | RSS=13562.2 MB
[LIVE-DECODE] 68/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.3%) | NVMe=527.7 MB/s (215310.34 MB) | RSS=13562.1 MB
[LIVE-DECODE] 70/128 tok | Avg=0.48 tps | Hit=88.4% (LA:+2.3%) | NVMe=528.0 MB/s (217115.34 MB) | RSS=13571.5 MB
[LIVE-DECODE] 72/128 tok | Avg=0.49 tps | Hit=88.4% (LA:+2.4%) | NVMe=528.3 MB/s (218810.52 MB) | RSS=13571.5 MB
[LIVE-DECODE] 74/128 tok | Avg=0.49 tps | Hit=88.4% (LA:+2.4%) | NVMe=528.7 MB/s (220456.09 MB) | RSS=13571.5 MB
[LIVE-DECODE] 76/128 tok | Avg=0.49 tps | Hit=88.4% (LA:+2.4%) | NVMe=529.0 MB/s (222227.46 MB) | RSS=13571.5 MB
[LIVE-DECODE] 78/128 tok | Avg=0.49 tps | Hit=88.4% (LA:+2.5%) | NVMe=529.4 MB/s (223995.21 MB) | RSS=13571.5 MB
[LIVE-DECODE] 80/128 tok | Avg=0.49 tps | Hit=88.3% (LA:+2.5%) | NVMe=529.8 MB/s (225960.40 MB) | RSS=13571.5 MB
[LIVE-DECODE] 82/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.6%) | NVMe=530.2 MB/s (227846.96 MB) | RSS=13571.5 MB
[LIVE-DECODE] 84/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.6%) | NVMe=530.5 MB/s (229637.27 MB) | RSS=13545.2 MB
[LIVE-DECODE] 86/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.7%) | NVMe=530.8 MB/s (231484.09 MB) | RSS=13545.2 MB
[LIVE-DECODE] 88/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.7%) | NVMe=531.1 MB/s (233218.09 MB) | RSS=13552.8 MB
[LIVE-DECODE] 90/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.7%) | NVMe=531.4 MB/s (235255.46 MB) | RSS=13552.8 MB
[LIVE-DECODE] 92/128 tok | Avg=0.50 tps | Hit=88.3% (LA:+2.8%) | NVMe=531.8 MB/s (236989.52 MB) | RSS=13552.8 MB
[LIVE-DECODE] 94/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.8%) | NVMe=532.1 MB/s (238764.52 MB) | RSS=13552.8 MB
[LIVE-DECODE] 96/128 tok | Avg=0.51 tps | Hit=88.3% (LA:+2.8%) | NVMe=532.3 MB/s (240356.71 MB) | RSS=13552.8 MB
[LIVE-DECODE] 98/128 tok | Avg=0.51 tps | Hit=88.2% (LA:+2.9%) | NVMe=532.6 MB/s (242024.40 MB) | RSS=13552.8 MB
[LIVE-DECODE] 100/128 tok | Avg=0.51 tps | Hit=88.2% (LA:+2.9%) | NVMe=532.8 MB/s (243694.65 MB) | RSS=13552.8 MB
[LIVE-DECODE] 102/128 tok | Avg=0.51 tps | Hit=88.2% (LA:+2.9%) | NVMe=533.1 MB/s (245291.15 MB) | RSS=13552.8 MB
[LIVE-DECODE] 104/128 tok | Avg=0.52 tps | Hit=88.2% (LA:+3.0%) | NVMe=533.4 MB/s (246708.65 MB) | RSS=13552.8 MB
[LIVE-DECODE] 106/128 tok | Avg=0.52 tps | Hit=88.2% (LA:+3.0%) | NVMe=533.6 MB/s (249058.15 MB) | RSS=13534.0 MB
[LIVE-DECODE] 108/128 tok | Avg=0.52 tps | Hit=88.2% (LA:+3.0%) | NVMe=533.9 MB/s (250802.40 MB) | RSS=13534.0 MB
[LIVE-DECODE] 110/128 tok | Avg=0.52 tps | Hit=88.2% (LA:+3.1%) | NVMe=533.9 MB/s (252921.59 MB) | RSS=13552.8 MB
[LIVE-DECODE] 112/128 tok | Avg=0.51 tps | Hit=88.2% (LA:+3.1%) | NVMe=533.9 MB/s (255220.90 MB) | RSS=13571.5 MB
[LIVE-DECODE] 114/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.2%) | NVMe=534.0 MB/s (257063.27 MB) | RSS=13571.5 MB
[LIVE-DECODE] 116/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.2%) | NVMe=534.1 MB/s (258761.46 MB) | RSS=13571.5 MB
[LIVE-DECODE] 118/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.3%) | NVMe=534.1 MB/s (260589.27 MB) | RSS=13571.5 MB
[LIVE-DECODE] 120/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.3%) | NVMe=534.2 MB/s (262409.15 MB) | RSS=13562.2 MB
[LIVE-DECODE] 122/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.4%) | NVMe=534.4 MB/s (264056.52 MB) | RSS=13562.2 MB
[LIVE-DECODE] 124/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.4%) | NVMe=534.5 MB/s (265737.27 MB) | RSS=13562.2 MB
[LIVE-DECODE] 126/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.5%) | NVMe=534.5 MB/s (267382.77 MB) | RSS=13562.2 MB
[LIVE-DECODE] 128/128 tok | Avg=0.52 tps | Hit=88.1% (LA:+3.5%) | NVMe=534.6 MB/s (268885.21 MB) | RSS=13562.2 MB

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
   LRFU Cache / Staging Ring    : 5662.50 MB (604/12384 exp = 4.88% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.70 MB | End=13562.19 MB | Peak=14240.24 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : " single coal-coalescededed LB- LBQD32 NV-read-and-GE-and-register-and register-and-and register-blocked-blocked-blocked-blocked multi-registered-blocked-block-blocked multi- multi-blocked multi-row multi-row-block multi-row-row-row-row-row AVAVXAVAVX2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2-2--2-2-2 QD2Q8Q8K_KKGEKKKKGE"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=58.3% | AvgMargin=2.122 | MinMargin=0.001
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 648255.06 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   21.27 |  96.3% |    1062 |   17.44 | 3492.96 | 46 |159 |131 | 1624576.0 |
   |    3 |   22412 | -co            |   14.00 |  19.9% |   11492 |   13.04 | 3492.96 |  0 |  0 |  0 | 1624576.0 |
   |    4 |    3831 | ales           |   20.23 |  56.4% |     278 |   19.95 | 2612.73 | 96 |166 | 74 | 1226144.0 |
   |    5 |    1998 | ced            |   23.84 |  95.9% |    6125 |   20.05 | 2612.73 |  0 |  0 |  0 | 1226144.0 |
   |    6 |     291 | ed             |   13.00 |  12.2% |      11 |   12.82 | 2250.94 |124 |147 | 65 | 1114336.0 |
   |    7 |     291 | ed             |   17.54 |  71.5% |   11492 |   15.78 | 2250.94 |  0 |  0 |  0 | 1114336.0 |
   |    8 |   39929 |  LB            |   16.46 |  74.9% |      11 |   14.17 | 2118.97 |154 |121 | 61 | 1052800.0 |
   |   10 |   39929 |  LB            |   12.87 |  15.0% |  154842 |   12.02 | 2535.00 |123 |138 | 75 | 1158688.0 |
   |   11 |      48 | Q              |   13.97 |  36.6% |   11492 |   12.83 | 2535.00 |  0 |  0 |  0 | 1158688.0 |
   |   36 |   34735 | registered     |   13.64 |  25.3% |   29819 |   12.17 | 2511.34 |127 |135 | 74 | 1170208.0 |
   |   37 |    9421 | -block         |   19.78 |  98.2% |    2504 |   13.99 | 2511.34 |  0 |  0 |  0 | 1170208.0 |
   |  126 |   10772 | GE             |   14.45 |  16.7% |    2646 |   14.40 | 1667.87 |199 | 88 | 49 | 842496.0 |
   |  127 |   50127 | KK             |   13.12 |  16.3% |      42 |   12.88 | 1667.87 |  0 |  0 |  0 | 842496.0 |
   |  128 |   50127 | KK             |   14.93 |  24.1% |      42 |   14.93 | 1535.08 |212 | 84 | 40 | 769248.0 |
   |  129 |   10772 | GE             |   18.90 |  83.6% |   22197 |   15.87 | 1535.08 |  0 |  0 |  0 | 769248.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 648.255s, TTFT=648255.06ms): Avg=0.79 | Min=0.78 | Max=0.80 tps
   Prefill Chunks (2): C1:256t/0.8tps/89% | C2:256t/0.8tps/89%
   Decode  (128 tok, 244.797s): Avg=0.52 | Min=0.29 | Max=0.74 tps
   Latency (ms) : Min=1344.59 | P10=1563.59 | P25=1667.87 | P50=1832.18 | P75=2116.50 | P90=2303.30 | P95=2511.34 | P99=3492.96 | Max=3492.96
   Mean/SD/Jitt : Mean=1912.47ms | StdDev=341.43ms | Jitter=108.93ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=163757 (84.61%) | Lookahead=6790 (+3.51%) | ColdMiss=22989 (11.88%) | EFF HIT=88.12%
   Lookahead    : 12736 prefetched -> 6790 consumed (53.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 88.8% | @64= 88.4% | @128= 88.1% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3720 | 331 | 557 | 87.9%|6382.50 | | L24 | 4608 | 4015 | 123 | 470 | 89.8%|4995.31 |
   | L04 | 4608 | 3817 | 131 | 660 | 85.7%|7475.00 | | L25 | 4608 | 3934 | 135 | 539 | 88.3%|6346.56 |
   | L05 | 4608 | 3768 | 173 | 667 | 85.5%|7367.19 | | L26 | 4608 | 3964 | 147 | 497 | 89.2%|5534.38 |
   | L06 | 4608 | 3760 | 218 | 630 | 86.3%|7151.56 | | L27 | 4608 | 3874 | 162 | 572 | 87.6%|6756.25 |
   | L07 | 4608 | 3883 | 200 | 525 | 88.6%|5807.50 | | L28 | 4608 | 3851 | 189 | 568 | 87.7%|6396.88 |
   | L08 | 4608 | 3886 | 135 | 587 | 87.3%|6842.50 | | L29 | 4608 | 3889 | 195 | 524 | 88.6%|5929.69 |
   | L09 | 4608 | 3865 | 157 | 586 | 87.3%|6253.12 | | L30 | 4608 | 3819 | 190 | 599 | 87.0%|6727.50 |
   | L10 | 4608 | 3849 | 146 | 613 | 86.7%|6332.19 | | L31 | 4608 | 3847 | 134 | 627 | 86.4%|6935.94 |
   | L11 | 4608 | 3879 | 169 | 560 | 87.8%|8493.75 | | L32 | 4608 | 3817 | 157 | 634 | 86.2%|6907.19 |
   | L12 | 4608 | 3910 | 158 | 540 | 88.3%|6842.38 | | L33 | 4608 | 3829 | 190 | 589 | 87.2%|6971.88 |
   | L13 | 4608 | 3961 | 133 | 514 | 88.8%|5599.06 | | L34 | 4608 | 3855 | 229 | 524 | 88.6%|6202.81 |
   | L14 | 4608 | 3977 | 109 | 522 | 88.7%|5649.38 | | L35 | 4608 | 3814 | 226 | 568 | 87.7%|6626.88 |
   | L15 | 4608 | 3935 | 135 | 538 | 88.3%|5807.50 | | L36 | 4608 | 3813 | 255 | 540 | 88.3%|6382.50 |
   | L16 | 4608 | 3940 | 157 | 511 | 88.9%|5599.06 | | L37 | 4608 | 3907 | 175 | 526 | 88.6%|5584.69 |
   | L17 | 4608 | 3920 | 120 | 568 | 87.7%|6245.94 | | L38 | 4608 | 3884 | 185 | 539 | 88.3%|6152.50 |
   | L18 | 4608 | 3997 | 107 | 504 | 89.1%|5656.56 | | L39 | 4608 | 3862 | 202 | 544 | 88.2%|6044.69 |
   | L19 | 4608 | 3987 | 132 | 489 | 89.4%|5541.56 | | L40 | 4608 | 3876 | 176 | 556 | 87.9%|6210.00 |
   | L20 | 4608 | 3983 | 129 | 496 | 89.2%|5376.25 | | L41 | 4608 | 3960 | 138 | 510 | 88.9%|5476.88 |
   | L21 | 4608 | 3987 | 149 | 472 | 89.8%|5175.00 | | L42 | 4608 | 4017 | 102 | 489 | 89.4%|5397.81 |
   | L22 | 4608 | 3997 | 126 | 485 | 89.5%|5412.19 | | L43 | 4608 | 4030 | 112 | 466 | 89.9%|4980.94 |
   | L23 | 4608 | 3936 | 135 | 537 | 88.3%|5893.75 | | L44 | 4608 | 3943 | 118 | 547 | 88.1%|7294.62 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 268885.21 MB (Load=6361.84 | Prefill=138840.25 | Warmup=0.00 | Decode=123683.12 MB)
   SSD Data/Token (Decode)      : Avg=966.274 MB/tok (Min=708.750 | P50=937.938 | P95=1165.875 | Max=1586.500 MB) | Prefill=271.172 MB/tok
   NVMe Batches / Requests      : 5144 Batches | 109067 Raw -> 107702 Merged (1365 LBA Merges, Avg 2556.5 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=106823
   SSD Read Bandwidth (Active)  : Min=38.34 | Avg=534.60 | Peak=1471.81 MB/s | WallAmort=301.09 MB/s
   OS Kernel I/O Verification   : Read=268894.24 MB | Write=0.01 MB | Syscalls=111787
   Sync Stall vs Async DMA      : SyncStall=322985.86 ms | AsyncOverlapped=488364.19 ms (60.2% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=5.89 GB/s | WallAmort=3.12 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=648.26s (72.6%, 138840.25 MB SSD) | Decode=244.80s (27.4%, 123683.12 MB SSD)
   CPU Time & Utilization       : User=1609.688s + Sys=24.109s (Wall=914.706s) | SysUtil=44.7% | ThrUtil=44.7% | 41.30 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 211373.49 ms (330271.1 us/tok | 23.67%)
   MoE AVX2 Q8 Expert Compute   : 258319.32 ms (403623.9 us/tok | 28.93%)
   Router + Lookahead Dispatch  :   4587.56 ms ( 7168.1 us/tok |  0.51%)
   LM Head Output Projection    :   3009.78 ms ( 4702.8 us/tok |  0.34%)
   Foreground NVMe Sync Stall   : 322985.86 ms (504665.4 us/tok | 36.17%)
   Unaccounted / OMP & Sampling :  92775.58 ms (144961.9 us/tok | 10.39%) | Total Wall=893051.60 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    58.97%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.08%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    16.95%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     9.71%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.29%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_glm53_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 115683.6ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='\nSummarize LBACoalesce in one sentence.\nSummarize LB'
[Stage 3] /v1/chat/completions (stream=true SSE) 46124.5ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_glm53_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5568.75 MB (594 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=0.80 tps | Avg=0.80 tps | Hit=89.2% | NVMe=518.7 MB/s (74277.59 MB, QD=64) | RSS=14045.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=0.79 tps | Avg=0.79 tps | Hit=88.9% | NVMe=524.6 MB/s (145295.52 MB, QD=64) | RSS=14045.2 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=0.79 tps | Avg=0.79 tps | Hit=88.9% | NVMe=526.3 MB/s (214799.34 MB, QD=64) | RSS=14045.2 MB
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
