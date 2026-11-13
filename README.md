<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#24 (Run ID `43464219439`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43464219439)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-13 19:21:02 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-13T17:46:43.774Z] ================================================================================
[2026-11-13T17:46:43.792Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-13T17:46:43.794Z] ================================================================================
[2026-11-13T17:46:49.182Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-13T17:46:49.376Z] --------------------------------------------------------------------------------
[2026-11-13T17:46:49.378Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.31 GB / 149.89 GB
[2026-11-13T17:46:49.379Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-13T17:46:49.380Z]  [Disk Telemetry] Total Combined Usable Free Space: 248.18 GB
[2026-11-13T17:46:49.396Z] --------------------------------------------------------------------------------
[2026-11-13T17:46:49.397Z]  [OK] Disk space verification passed: 248.18 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 868K Nov 13 17:47 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 868K Nov 13 17:47 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.48 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    581.16 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2342.44 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9357.34 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10824.25 MB/s
   RND4K Q32T16 Read                  :    756.32 MB/s (  193618 IOPS)
   RND4K Q1T1  Read                   :    836.75 MB/s (Latency: 4.67 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     50.99 GB/s
   AVX2 256-bit Sequential Write BW   :     41.27 GB/s
   STREAM Triad (A = B + s*C) BW      :     30.99 GB/s
   Random Pointer-Chase Latency       :    138.01 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.49 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    225.19 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.70 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1856.75 tps | Avg=1856.75 tps | Hit=99.5% | NVMe=2439.3 MB/s (6.19 MB, QD=64) | RSS=71.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1654.24 tps | Avg=1749.65 tps | Hit=99.5% | NVMe=2321.9 MB/s (7.01 MB, QD=64) | RSS=71.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1415.58 tps | Avg=1622.06 tps | Hit=99.5% | NVMe=2235.3 MB/s (7.78 MB, QD=64) | RSS=71.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1253.45 tps | Avg=1510.97 tps | Hit=99.5% | NVMe=2164.5 MB/s (8.61 MB, QD=64) | RSS=72.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1144.46 tps | Avg=1420.02 tps | Hit=99.5% | NVMe=2092.3 MB/s (9.33 MB, QD=64) | RSS=72.2 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1009.19 tps | Avg=1329.80 tps | Hit=99.5% | NVMe=2025.8 MB/s (10.06 MB, QD=64) | RSS=72.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=948.40 tps | Avg=1257.55 tps | Hit=99.5% | NVMe=1957.8 MB/s (10.83 MB, QD=64) | RSS=72.8 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=861.24 tps | Avg=1189.15 tps | Hit=99.5% | NVMe=1935.0 MB/s (11.60 MB, QD=64) | RSS=73.0 MB
[LIVE-DECODE] 8/32 tok | Avg=264.84 tps | Hit=99.5% (LA:+0.0%) | NVMe=1858.4 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=257.17 tps | Hit=99.5% (LA:+0.1%) | NVMe=1817.5 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=248.11 tps | Hit=99.5% (LA:+0.1%) | NVMe=1779.1 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=251.07 tps | Hit=99.5% (LA:+0.1%) | NVMe=1766.4 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=73.06 MB | Peak=73.06 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1722.24 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    3.83 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    3.83 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    3.83 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    3.83 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    3.74 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    3.74 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    3.70 | 11 |  1 |  0 |    49.5 |
   |   16 |     246 | tok_246        |  170.49 |  98.4% |      55 |  166.39 |    4.62 | 12 |  0 |  0 |     0.0 |
   |   17 |     228 | tok_228        |   91.50 | 100.0% |     246 |   70.88 |    4.62 |  0 |  0 |  0 |     0.0 |
   |   20 |      86 | tok_86         |  167.81 |  99.1% |     246 |  163.11 |    4.39 | 12 |  0 |  0 |    24.8 |
   |   21 |      68 | tok_68         |  177.01 | 100.0% |     246 |  152.23 |    4.39 |  0 |  0 |  0 |    24.8 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    3.65 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    3.65 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    3.67 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    3.67 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.722s, TTFT=1722.24ms): Avg=1189.15 | Min=861.24 | Max=1856.75 tps
   Prefill Chunks (8): C1:256t/1856.8tps/99% | C2:256t/1654.2tps/99% | C3:256t/1415.6tps/99% | C4:256t/1253.5tps/99%
                       C5:256t/1144.5tps/99% | C6:256t/1009.2tps/99% | C7:256t/948.4tps/99% | C8:256t/861.2tps/99%
   Decode  (32 tok, 0.127s): Avg=251.07 | Min=216.62 | Max=274.33 tps
   Latency (ms) : Min=3.65 | P10=3.67 | P25=3.77 | P50=3.83 | P75=4.30 | P90=4.39 | P95=4.62 | P99=4.62 | Max=4.62
   Mean/SD/Jitt : Mean=3.98ms | StdDev=0.30ms | Jitter=0.07ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=281.70 | Avg=1766.39 | Peak=6218.91 MB/s | WallAmort=7.19 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=5.11 ms | AsyncOverlapped=6.32 ms (55.3% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.82 GB/s | WallAmort=0.77 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.72s (93.1%, 6.19 MB SSD) | Decode=0.13s (6.9%, 1.69 MB SSD)
   CPU Time & Utilization       : User=2.203s + Sys=0.578s (Wall=1.869s) | SysUtil=37.2% | ThrUtil=37.2% | 34.41 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1552.69 ms (  746.5 us/tok | 83.94%)
   MoE AVX2 Q8 Expert Compute   :    189.40 ms (   91.1 us/tok | 10.24%)
   Router + Lookahead Dispatch  :     48.89 ms (   23.5 us/tok |  2.64%)
   LM Head Output Projection    :      4.55 ms (    2.2 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      5.11 ms (    2.5 us/tok |  0.28%)
   Unaccounted / OMP & Sampling :     49.06 ms (   23.6 us/tok |  2.65%) | Total Wall=1849.70 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    26.46%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.20%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.49%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    68.60%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.25%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2571.00 tps | Avg=2571.00 tps | Hit=99.2% | NVMe=3106.7 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2510.07 tps | Avg=2540.17 tps | Hit=99.2% | NVMe=4047.2 MB/s (42.92 MB, QD=64) | RSS=89.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2056.47 tps | Avg=2355.49 tps | Hit=99.2% | NVMe=4537.2 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2195.26 tps | Avg=2313.28 tps | Hit=99.2% | NVMe=4932.2 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2035.07 tps | Avg=2251.71 tps | Hit=99.2% | NVMe=5209.9 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1894.21 tps | Avg=2183.04 tps | Hit=99.2% | NVMe=5419.4 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1681.78 tps | Avg=2093.89 tps | Hit=99.2% | NVMe=5588.0 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1654.62 tps | Avg=2026.63 tps | Hit=99.2% | NVMe=5744.3 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=245.58 tps | Hit=99.2% (LA:+0.0%) | NVMe=5642.6 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=247.92 tps | Hit=99.2% (LA:+0.1%) | NVMe=5583.1 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=248.40 tps | Hit=99.2% (LA:+0.1%) | NVMe=5484.9 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=247.96 tps | Hit=99.2% (LA:+0.1%) | NVMe=5405.5 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=91.73 MB | Peak=91.73 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1010.54 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    4.14 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    4.14 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    4.07 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    4.07 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    4.06 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    4.06 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    4.02 | 16 |  0 |  0 |    32.0 |
   |   26 |     194 | qtok_194       |   70.46 | 100.0% |     128 |   54.98 |    4.06 | 12 |  4 |  0 |   147.0 |
   |   27 |      49 | qtok_49        |   67.58 |  99.9% |     209 |   61.01 |    4.06 |  0 |  0 |  0 |   147.0 |
   |   28 |      49 | qtok_49        |   65.10 | 100.0% |      18 |   55.78 |    4.04 | 10 |  6 |  0 |   115.2 |
   |   29 |     148 | qtok_148       |   77.89 | 100.0% |     127 |   51.09 |    4.04 |  0 |  0 |  0 |   115.2 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    4.06 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    4.06 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    4.06 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    4.06 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.011s, TTFT=1010.54ms): Avg=2026.63 | Min=1654.62 | Max=2571.00 tps
   Prefill Chunks (8): C1:256t/2571.0tps/99% | C2:256t/2510.1tps/99% | C3:256t/2056.5tps/99% | C4:256t/2195.3tps/99%
                       C5:256t/2035.1tps/99% | C6:256t/1894.2tps/99% | C7:256t/1681.8tps/99% | C8:256t/1654.6tps/99%
   Decode  (32 tok, 0.129s): Avg=247.96 | Min=241.58 | Max=252.43 tps
   Latency (ms) : Min=3.96 | P10=3.99 | P25=4.01 | P50=4.03 | P75=4.06 | P90=4.07 | P95=4.14 | P99=4.14 | Max=4.14
   Mean/SD/Jitt : Mean=4.03ms | StdDev=0.04ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=396.19 | Avg=5405.50 | Peak=10580.69 MB/s | WallAmort=136.13 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=7.21 ms | AsyncOverlapped=27.35 ms (79.1% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=2.13 GB/s | WallAmort=1.85 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.01s (88.7%, 144.44 MB SSD) | Decode=0.13s (11.3%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.125s + Sys=0.391s (Wall=1.170s) | SysUtil=53.7% | ThrUtil=53.7% | 49.72 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    699.90 ms (  336.5 us/tok | 61.42%)
   MoE AVX2 Q8 Expert Compute   :    284.18 ms (  136.6 us/tok | 24.94%)
   Router + Lookahead Dispatch  :     64.71 ms (   31.1 us/tok |  5.68%)
   LM Head Output Projection    :      4.07 ms (    2.0 us/tok |  0.36%)
   Foreground NVMe Sync Stall   :      7.21 ms (    3.5 us/tok |  0.63%)
   Unaccounted / OMP & Sampling :     79.53 ms (   38.2 us/tok |  6.98%) | Total Wall=1139.60 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.45%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.10%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.35%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    64.60%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.50%  |
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
    "ttft_ms": 171.96,
    "avg_tps": 953.72,
    "min_tps": 783.44,
    "max_tps": 1091.55
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 204.83,
    "min_tps": 197.74,
    "max_tps": 210.7,
    "p50_ms": 4.87,
    "p90_ms": 5.02,
    "p99_ms": 5.06,
    "mean_ms": 4.88,
    "jitter_ms": 0.06
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
    "avg_mbs": 1864.49,
    "peak_mbs": 5868.54,
    "sync_wait_ms": 1.81,
    "async_overlap_ms": 3.39
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
    "dense_attention": 270.45,
    "moe_compute": 74.3,
    "router_lookahead": 5.89,
    "lm_head": 6.02,
    "unaccounted": 3.89
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 79.85,
    "ram_bandwidth_pinning": 2.48,
    "expert_cache_lrfu": 13.87,
    "lookahead_parallel_overlap": 2.4,
    "ssd_nvme_throughput": 1.4,
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
    "ttft_ms": 220.89,
    "avg_tps": 742.46,
    "min_tps": 519.84,
    "max_tps": 855.77
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 175.74,
    "min_tps": 158.64,
    "max_tps": 183.92,
    "p50_ms": 5.68,
    "p90_ms": 5.96,
    "p99_ms": 6.3,
    "mean_ms": 5.69,
    "jitter_ms": 0.14
  },
  "cache": {
    "raw_hit_rate_pct": 85.44,
    "effective_hit_rate_pct": 94.95,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 37925472,
    "prefill_bytes": 20240384,
    "warmup_bytes": 0,
    "decode_bytes": 12128256,
    "bytes_per_token": 186824.99,
    "avg_mbs": 2444.3,
    "peak_mbs": 7183.91,
    "sync_wait_ms": 4.93,
    "async_overlap_ms": 13.77
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
    "dense_attention": 249.59,
    "moe_compute": 143.38,
    "router_lookahead": 7.11,
    "lm_head": 6.15,
    "unaccounted": 31.64
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 75.99,
    "ram_bandwidth_pinning": 2.79,
    "expert_cache_lrfu": 11.72,
    "lookahead_parallel_overlap": 5.74,
    "ssd_nvme_throughput": 3.76,
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
Host CPU: AMD EPYC 9V74 80-Core Processor | Cores=2 Threads=4 | RAM=15.99 GB

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.34 GB Available
   Active Drive Space : 219.98 GB Total / 219.81 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    590.35 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2346.62 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9227.09 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9412.21 MB/s
   RND4K Q32T16 Read                  :    840.18 MB/s (  215085 IOPS)
   RND4K Q1T1  Read                   :    817.96 MB/s (Latency: 4.78 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     47.95 GB/s
   AVX2 256-bit Sequential Write BW   :     42.47 GB/s
   STREAM Triad (A = B + s*C) BW      :     35.24 GB/s
   Random Pointer-Chase Latency       :    138.18 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.67 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    116.31 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.74 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 28.33 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 51.75 MB/s (19.79s)
   Window #01 (296.0 MB in 0.51s):   582.58 MB/s (Uncached Direct Read)
   Window #02 (208.0 MB in 0.52s):   398.09 MB/s (Uncached Direct Read)
   Window #03 (196.0 MB in 0.51s):   385.08 MB/s (Uncached Direct Read)
   Window #04 (196.0 MB in 0.50s):   390.88 MB/s (Uncached Direct Read)
   Window #05 (128.0 MB in 0.42s):   305.72 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   416.30 MB/s (Min=305.72 | Max=582.58 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 219.81 GB / 219.98 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 266.46 MB/s (3.84s)
   Window #01 (304.0 MB in 0.51s):   601.01 MB/s (Uncached Direct Read)
   Window #02 (268.0 MB in 0.50s):   533.87 MB/s (Uncached Direct Read)
   Window #03 (268.0 MB in 0.50s):   533.91 MB/s (Uncached Direct Read)
   Window #04 (184.0 MB in 0.35s):   531.63 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   551.74 MB/s (Min=531.63 | Max=601.01 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: glm53 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (0.009 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: 100.00% (0.01/0.01 GB) @ 12.0 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (46.470 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  10.76% (5.00/46.47 GB) @ 241.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  21.52% (10.00/46.47 GB) @ 217.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  32.28% (15.00/46.47 GB) @ 222.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  43.04% (20.00/46.47 GB) @ 231.2 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  53.80% (25.00/46.47 GB) @ 230.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  64.56% (30.00/46.47 GB) @ 237.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  75.32% (35.00/46.47 GB) @ 241.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  86.08% (40.00/46.47 GB) @ 239.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  96.84% (45.00/46.47 GB) @ 227.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf: 100.00% (46.47/46.47 GB) @ 228.2 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (45.866 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  10.90% (5.00/45.87 GB) @ 153.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  21.80% (10.00/45.87 GB) @ 171.2 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  32.70% (15.00/45.87 GB) @ 162.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  43.61% (20.00/45.87 GB) @ 134.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  54.51% (25.00/45.87 GB) @ 126.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  65.41% (30.00/45.87 GB) @ 128.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  76.31% (35.00/45.87 GB) @ 125.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  87.21% (40.00/45.87 GB) @ 127.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  98.11% (45.00/45.87 GB) @ 129.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf: 100.00% (45.87/45.87 GB) @ 128.6 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (2.506 GB) -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf: 100.00% (2.51/2.51 GB) @ 99.9 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=101,844,951,904 (94.85 GB) | Elapsed=602.97s
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
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5334.38 MB (569 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.53 tps | Avg=0.53 tps | Hit=73.8% | NVMe=528.3 MB/s (47437.59 MB, QD=64) | RSS=13722.8 MB
[LIVE-DECODE] 2/32 tok | Avg=0.35 tps | Hit=73.9% (LA:+1.1%) | NVMe=529.7 MB/s (50443.27 MB) | RSS=13725.4 MB
[LIVE-DECODE] 4/32 tok | Avg=0.40 tps | Hit=73.9% (LA:+1.8%) | NVMe=530.9 MB/s (52750.96 MB) | RSS=13532.2 MB
[LIVE-DECODE] 6/32 tok | Avg=0.41 tps | Hit=74.1% (LA:+2.4%) | NVMe=527.2 MB/s (54638.34 MB) | RSS=13500.7 MB
[LIVE-DECODE] 8/32 tok | Avg=0.45 tps | Hit=74.2% (LA:+2.8%) | NVMe=528.1 MB/s (56255.40 MB) | RSS=13392.5 MB
[LIVE-DECODE] 10/32 tok | Avg=0.47 tps | Hit=74.4% (LA:+3.2%) | NVMe=529.6 MB/s (57948.21 MB) | RSS=13346.2 MB
[LIVE-DECODE] 12/32 tok | Avg=0.48 tps | Hit=74.5% (LA:+3.6%) | NVMe=530.9 MB/s (59713.77 MB) | RSS=13294.0 MB
[LIVE-DECODE] 14/32 tok | Avg=0.50 tps | Hit=74.6% (LA:+4.0%) | NVMe=532.5 MB/s (61475.46 MB) | RSS=13286.2 MB
[LIVE-DECODE] 16/32 tok | Avg=0.51 tps | Hit=74.7% (LA:+4.4%) | NVMe=534.3 MB/s (63460.34 MB) | RSS=13274.7 MB
[LIVE-DECODE] 18/32 tok | Avg=0.52 tps | Hit=74.8% (LA:+4.7%) | NVMe=535.5 MB/s (65144.90 MB) | RSS=13264.3 MB
[LIVE-DECODE] 20/32 tok | Avg=0.53 tps | Hit=74.9% (LA:+5.0%) | NVMe=537.0 MB/s (67002.27 MB) | RSS=13246.8 MB
[LIVE-DECODE] 22/32 tok | Avg=0.54 tps | Hit=75.0% (LA:+5.3%) | NVMe=538.2 MB/s (68772.71 MB) | RSS=13227.7 MB
[LIVE-DECODE] 24/32 tok | Avg=0.54 tps | Hit=75.1% (LA:+5.6%) | NVMe=539.6 MB/s (70584.77 MB) | RSS=13225.0 MB
[LIVE-DECODE] 26/32 tok | Avg=0.55 tps | Hit=75.2% (LA:+5.9%) | NVMe=540.9 MB/s (72406.40 MB) | RSS=13225.0 MB
[LIVE-DECODE] 28/32 tok | Avg=0.55 tps | Hit=75.2% (LA:+6.2%) | NVMe=542.3 MB/s (74247.34 MB) | RSS=13225.0 MB
[LIVE-DECODE] 30/32 tok | Avg=0.56 tps | Hit=75.3% (LA:+6.3%) | NVMe=543.7 MB/s (76070.84 MB) | RSS=13225.0 MB
[LIVE-DECODE] 32/32 tok | Avg=0.56 tps | Hit=75.4% (LA:+6.6%) | NVMe=544.7 MB/s (77858.52 MB) | RSS=13225.0 MB

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
   LRFU Cache / Staging Ring    : 5334.38 MB (569/12384 exp = 4.59% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.67 MB | End=13224.97 MB | Peak=13810.34 MB
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
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 121489.08 |  0 |  0 |  0 |     0.0 |
   |    2 |   24923 |  persistent    |   14.20 |   9.2% |     220 |   14.17 | 2856.05 | 20 |231 | 85 | 1538912.0 |
   |    3 |   54443 |  CUDA          |   14.65 |  11.4% |    9996 |   14.41 | 2856.05 |  0 |  0 |  0 | 1538912.0 |
   |    4 |    4269 |  stream        |   14.37 |  14.3% |   11292 |   13.81 | 2178.95 |100 |166 | 70 | 1181536.0 |
   |    5 |   47414 |  pinned        |   14.48 |  22.4% |   12675 |   13.14 | 2178.95 |  0 |  0 |  0 | 1181536.0 |
   |    6 |   63637 | -memory        |   18.96 |  91.2% |    3468 |   15.18 | 2235.38 |142 |144 | 50 | 966336.0 |
   |    7 |   47414 |  pinned        |   16.01 |  30.3% |    7314 |   15.09 | 2235.38 |  0 |  0 |  0 | 966336.0 |
   |    8 |   63637 | -memory        |   16.32 |  36.5% |   47414 |   15.67 | 1525.34 |189 | 92 | 55 | 827936.0 |
   |   10 |   47414 |  pinned        |   17.39 |  70.7% |    4938 |   14.82 | 1931.17 |185 |101 | 50 | 866720.0 |
   |   11 |   63637 | -memory        |   19.83 |  93.1% |    4938 |   16.09 | 1931.17 |  0 |  0 |  0 | 866720.0 |
   |   16 |   47414 |  pinned        |   16.87 |  71.1% |   25372 |   13.63 | 1743.02 |161 |106 | 69 | 1016256.0 |
   |   17 |   63637 | -memory        |   19.08 |  72.7% |   47414 |   17.80 | 1743.02 |  0 |  0 |  0 | 1016256.0 |
   |   30 |   47414 |  pinned        |   17.05 |  51.0% |   63637 |   16.85 | 1589.23 |192 | 73 | 71 | 933632.0 |
   |   31 |   63637 | -memory        |   21.56 |  94.1% |   47414 |   18.55 | 1589.23 |  0 |  0 |  0 | 933632.0 |
   |   32 |   63637 | -memory        |   17.13 |  66.4% |   47414 |   16.08 | 1586.44 |179 | 95 | 62 | 915296.0 |
   |   33 |   47414 |  pinned        |   21.73 |  98.5% |   63637 |   16.47 | 1586.44 |  0 |  0 |  0 | 915296.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 121.489s, TTFT=121489.08ms): Avg=0.53 | Min=0.53 | Max=0.53 tps
   Prefill Chunks (1): C1:64t/0.5tps/74%
   Decode  (32 tok, 56.994s): Avg=0.56 | Min=0.35 | Max=0.66 tps
   Latency (ms) : Min=1525.34 | P10=1530.66 | P25=1589.23 | P50=1618.16 | P75=1931.17 | P90=2235.38 | P95=2856.05 | P99=2856.05 | Max=2856.05
   Mean/SD/Jitt : Mean=1781.06ms | StdDev=348.15ms | Jitter=90.43ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=18475 (68.73%) | Lookahead=1780 (+6.62%) | ColdMiss=6625 (24.65%) | EFF HIT=75.35%
   Lookahead    : 3123 prefetched -> 1780 consumed (57.0% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.7% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  354 |  75 | 211 | 67.0%|2055.62 | | L24 |  640 |  467 |  39 | 134 | 79.1%|1473.44 |
   | L04 |  640 |  335 |  43 | 262 | 59.1%|2637.81 | | L25 |  640 |  464 |  32 | 144 | 77.5%|1523.75 |
   | L05 |  640 |  352 |  52 | 236 | 63.1%|2350.31 | | L26 |  640 |  468 |  47 | 125 | 80.5%|1415.94 |
   | L06 |  640 |  376 |  61 | 203 | 68.3%|2105.94 | | L27 |  640 |  430 |  52 | 158 | 75.3%|1840.00 |
   | L07 |  640 |  404 |  62 | 174 | 72.8%|1832.81 | | L28 |  640 |  453 |  42 | 145 | 77.3%|1588.44 |
   | L08 |  640 |  416 |  37 | 187 | 70.8%|1969.38 | | L29 |  640 |  441 |  45 | 154 | 75.9%|1674.69 |
   | L09 |  640 |  378 |  42 | 220 | 65.6%|2177.81 | | L30 |  640 |  447 |  39 | 154 | 75.9%|1624.38 |
   | L10 |  640 |  385 |  43 | 212 | 66.9%|2062.81 | | L31 |  640 |  433 |  39 | 168 | 73.8%|1681.88 |
   | L11 |  640 |  420 |  45 | 175 | 72.7%|2371.88 | | L32 |  640 |  420 |  56 | 164 | 74.4%|1804.06 |
   | L12 |  640 |  433 |  46 | 161 | 74.8%|1959.75 | | L33 |  640 |  448 |  43 | 149 | 76.7%|1732.19 |
   | L13 |  640 |  446 |  41 | 153 | 76.1%|1595.62 | | L34 |  640 |  450 |  53 | 137 | 78.6%|1588.44 |
   | L14 |  640 |  459 |  29 | 152 | 76.2%|1602.81 | | L35 |  640 |  452 |  47 | 141 | 78.0%|1530.94 |
   | L15 |  640 |  455 |  30 | 155 | 75.8%|1538.12 | | L36 |  640 |  450 |  40 | 150 | 76.6%|1581.25 |
   | L16 |  640 |  459 |  46 | 135 | 78.9%|1487.81 | | L37 |  640 |  450 |  40 | 150 | 76.6%|1530.94 |
   | L17 |  640 |  454 |  36 | 150 | 76.6%|1559.69 | | L38 |  640 |  451 |  45 | 144 | 77.5%|1566.88 |
   | L18 |  640 |  475 |  30 | 135 | 78.9%|1444.69 | | L39 |  640 |  454 |  50 | 136 | 78.8%|1408.75 |
   | L19 |  640 |  464 |  34 | 142 | 77.8%|1502.19 | | L40 |  640 |  459 |  39 | 142 | 77.8%|1466.25 |
   | L20 |  640 |  464 |  40 | 136 | 78.8%|1552.50 | | L41 |  640 |  472 |  27 | 141 | 78.0%|1365.62 |
   | L21 |  640 |  466 |  50 | 124 | 80.6%|1444.69 | | L42 |  640 |  493 |  21 | 126 | 80.3%|1221.88 |
   | L22 |  640 |  468 |  42 | 130 | 79.7%|1473.44 | | L43 |  640 |  493 |  33 | 114 | 82.2%|1221.88 |
   | L23 |  640 |  437 |  39 | 164 | 74.4%|1789.69 | | L44 |  640 |  480 |  28 | 132 | 79.4%|1792.25 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 77858.52 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=30420.94 MB)
   SSD Data/Token (Decode)      : Avg=950.654 MB/tok (Min=808.531 | P50=910.812 | P95=1502.844 | Max=1502.844 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1319 Batches | 30647 Raw -> 30329 Merged (318 LBA Merges, Avg 2628.7 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=29450
   SSD Read Bandwidth (Active)  : Min=10.97 | Avg=544.65 | Peak=3901.51 MB/s | WallAmort=436.22 MB/s
   OS Kernel I/O Verification   : Read=77867.56 MB | Write=0.00 MB | Syscalls=34365
   Sync Stall vs Async DMA      : SyncStall=90457.87 ms | AsyncOverlapped=130692.78 ms (59.1% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=8.05 GB/s | WallAmort=2.73 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=121.49s (68.1%, 41075.75 MB SSD) | Decode=56.99s (31.9%, 30420.94 MB SSD)
   CPU Time & Utilization       : User=196.484s + Sys=6.266s (Wall=193.924s) | SysUtil=26.1% | ThrUtil=26.1% | 24.18 GFLOPS
----------------------------------------------------------------------------

... [TRUNCATED] ...

009.2 us/tok |  0.27%)
   LM Head Output Projection    :    711.98 ms ( 7416.4 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :  90457.87 ms (942269.5 us/tok | 50.68%)
   Unaccounted / OMP & Sampling :  26951.60 ms (280745.8 us/tok | 15.10%) | Total Wall=178483.15 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    40.41%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    19.76%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.65%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.70%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.48%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 195s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.59 GB Available
   Active Drive Space : 219.98 GB Total / 127.45 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    580.42 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2255.19 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9134.24 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7867.34 MB/s
   RND4K Q32T16 Read                  :    624.57 MB/s (  159890 IOPS)
   RND4K Q1T1  Read                   :    742.83 MB/s (Latency: 5.26 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     75.76 GB/s
   AVX2 256-bit Sequential Write BW   :     62.65 GB/s
   STREAM Triad (A = B + s*C) BW      :     46.60 GB/s
   Random Pointer-Chase Latency       :     72.37 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.76 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    179.67 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.83 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.53 tps | Avg=0.53 tps | Hit=73.6% | NVMe=524.9 MB/s (51661.71 MB, QD=64) | RSS=14033.4 MB

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
   LRFU Cache / Staging Ring    : 5634.38 MB (601/12384 exp = 4.85% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.67 MB | End=13507.13 MB | Peak=14113.89 MB
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
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 132902.65 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   20.50 |  79.8% |   15724 |   19.10 | 3240.63 | 20 |235 | 81 | 1512544.0 |
   |    3 |    1339 | >\n\n          |   14.01 |  20.8% |     397 |   12.96 | 3240.63 |  0 |  0 |  0 | 1512544.0 |
   |    4 |   10056 | Let            |   15.28 |  31.5% |     334 |   14.78 | 1824.75 |142 |135 | 59 | 996096.0 |
   |    5 |     752 |  me            |   16.52 |  72.1% |     594 |   14.85 | 1824.75 |  0 |  0 |  0 | 996096.0 |
   |    6 |    1744 |  think         |   15.53 |  38.0% |   23578 |   13.60 | 2030.78 |120 |164 | 52 | 1075232.0 |
   |    7 |    1526 |  through       |   17.47 |  63.7% |   15504 |   14.79 | 2030.78 |  0 |  0 |  0 | 1075232.0 |
   |    8 |     419 |  this          |   17.34 |  55.6% |     279 |   16.09 | 2296.55 |107 |172 | 57 | 1147072.0 |
   |    9 |   15504 |  carefully     |   14.89 |   6.9% |    3019 |   14.71 | 2296.55 |  0 |  0 |  0 | 1147072.0 |
   |   42 |     594 | 's             |   17.29 |  64.6% |    1526 |   16.09 | 1939.22 |148 |108 | 80 | 1069984.0 |
   |   43 |    1526 |  through       |   21.63 |  92.8% |     279 |   18.16 | 1939.22 |  0 |  0 |  0 | 1069984.0 |
   |   12 |   32559 |  reasoning     |   14.05 |   8.5% |    1681 |   14.01 | 1931.22 |124 |156 | 56 | 1064640.0 |
   |   62 |    1526 |  through       |   17.43 |  49.9% |     594 |   17.31 | 1797.24 |180 | 68 | 88 | 1031744.0 |
   |   63 |     594 | 's             |   21.37 |  93.3% |    1526 |   17.99 | 1797.24 |  0 |  0 |  0 | 1031744.0 |
   |   64 |     594 | 's             |   17.28 |  49.5% |    1526 |   17.16 | 1990.63 |158 |101 | 77 | 1100800.0 |
   |   65 |    1526 |  through       |   21.46 |  88.7% |     594 |   18.70 | 1990.63 |  0 |  0 |  0 | 1100800.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 132.903s, TTFT=132902.65ms): Avg=0.53 | Min=0.53 | Max=0.53 tps
   Prefill Chunks (1): C1:70t/0.5tps/74%
   Decode  (64 tok, 113.499s): Avg=0.56 | Min=0.31 | Max=0.81 tps
   Latency (ms) : Min=1234.06 | P10=1423.23 | P25=1651.57 | P50=1765.84 | P75=1896.04 | P90=1990.63 | P95=2296.55 | P99=3240.63 | Max=3240.63
   Mean/SD/Jitt : Mean=1773.42ms | StdDev=341.04ms | Jitter=117.62ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=22528 (65.73%) | Lookahead=3652 (+10.66%) | ColdMiss=8092 (23.61%) | EFF HIT=76.39%
   Lookahead    : 6418 prefetched -> 3652 consumed (56.9% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64= 76.4% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  475 | 131 | 210 | 74.3%|2450.94 | | L24 |  816 |  579 |  83 | 154 | 81.1%|2170.62 |
   | L04 |  816 |  442 |  75 | 299 | 63.4%|3450.00 | | L25 |  816 |  569 |  62 | 185 | 77.3%|2371.88 |
   | L05 |  816 |  441 | 103 | 272 | 66.7%|3291.88 | | L26 |  816 |  554 |  87 | 175 | 78.6%|2307.19 |
   | L06 |  816 |  478 |  99 | 239 | 70.7%|2846.25 | | L27 |  816 |  538 | 103 | 175 | 78.6%|2515.62 |
   | L07 |  816 |  498 | 120 | 198 | 75.7%|2645.00 | | L28 |  816 |  522 |  95 | 199 | 75.6%|2551.56 |
   | L08 |  816 |  516 |  59 | 241 | 70.5%|3040.31 | | L29 |  816 |  531 |  98 | 187 | 77.1%|2522.81 |
   | L09 |  816 |  456 |  94 | 266 | 67.4%|3220.00 | | L30 |  816 |  533 |  77 | 206 | 74.8%|2501.25 |
   | L10 |  816 |  473 | 106 | 237 | 71.0%|2954.06 | | L31 |  816 |  514 | 107 | 195 | 76.1%|2637.81 |
   | L11 |  816 |  469 | 104 | 243 | 70.2%|4087.50 | | L32 |  816 |  513 | 119 | 184 | 77.5%|2666.56 |
   | L12 |  816 |  526 |  73 | 217 | 73.4%|3115.50 | | L33 |  816 |  573 |  85 | 158 | 80.6%|2206.56 |
   | L13 |  816 |  554 |  63 | 199 | 75.6%|2357.50 | | L34 |  816 |  513 | 120 | 183 | 77.6%|2522.81 |
   | L14 |  816 |  541 |  67 | 208 | 74.5%|2731.25 | | L35 |  816 |  527 | 116 | 173 | 78.8%|2400.62 |
   | L15 |  816 |  540 |  99 | 177 | 78.3%|2379.06 | | L36 |  816 |  534 | 101 | 181 | 77.8%|2379.06 |
   | L16 |  816 |  554 |  73 | 189 | 76.8%|2278.44 | | L37 |  816 |  554 |  90 | 172 | 78.9%|2199.38 |
   | L17 |  816 |  556 |  51 | 209 | 74.4%|2379.06 | | L38 |  816 |  567 |  85 | 164 | 79.9%|2213.75 |
   | L18 |  816 |  597 |  59 | 160 | 80.4%|2120.31 | | L39 |  816 |  546 | 100 | 170 | 79.2%|2185.00 |
   | L19 |  816 |  578 |  69 | 169 | 79.3%|2098.75 | | L40 |  816 |  496 | 109 | 211 | 74.1%|2910.94 |
   | L20 |  816 |  617 |  50 | 149 | 81.7%|1796.88 | | L41 |  816 |  544 |  97 | 175 | 78.6%|2328.75 |
   | L21 |  816 |  592 |  71 | 153 | 81.2%|2055.62 | | L42 |  816 |  592 |  57 | 167 | 79.5%|2084.38 |
   | L22 |  816 |  582 |  69 | 165 | 79.8%|2314.38 | | L43 |  816 |  596 |  69 | 151 | 81.5%|2105.94 |
   | L23 |  816 |  583 |  72 | 161 | 80.3%|1983.75 | | L44 |  816 |  565 |  85 | 166 | 79.7%|2688.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 113002.52 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=61340.81 MB)
   SSD Data/Token (Decode)      : Avg=958.450 MB/tok (Min=679.188 | P50=972.750 | P95=1120.188 | Max=1477.094 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2505 Batches | 45011 Raw -> 44502 Merged (509 LBA Merges, Avg 2600.2 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=43623
   SSD Read Bandwidth (Active)  : Min=5.58 | Avg=552.00 | Peak=3749.76 MB/s | WallAmort=458.61 MB/s (100.0% of 580.4 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=113989.56 MB | Write=128.00 MB | Syscalls=56076
   Sync Stall vs Async DMA      : SyncStall=110293.95 ms | AsyncOverlapped=192584.57 ms (63.6% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=9.39 GB/s (20.1% STREAM) | WallAmort=3.15 GB/s (Max=46.60 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=132.90s (53.9%, 45299.88 MB SSD) | Decode=113.50s (46.1%, 61340.81 MB SSD)
   CPU Time & Utilization       : User=258.984s + Sys=8.703s (Wall=262.687s) | SysUtil=25.5% | ThrUtil=25.5% | 45.77 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  33760.93 ms (251947.2 us/tok | 13.70%)
   MoE AVX2 Q8 Expert Compute   :  47700.64 ms (355974.9 us/tok | 19.36%)
   Router + Lookahead Dispatch  :    658.90 ms ( 4917.2 us/tok |  0.27%)
   LM Head Output Projection    :   1313.58 ms ( 9802.8 us/tok |  0.53%)
   Foreground NVMe Sync Stall   : 110293.95 ms (823089.2 us/tok | 44.76%)
   Unaccounted / OMP & Sampling :  52673.81 ms (393088.1 us/tok | 21.38%) | Total Wall=246401.81 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    36.79%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    23.37%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    30.28%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.96%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.60%  |
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
[LIVE-PREFILL] 256/512 tok | Chunk=0.89 tps | Avg=0.89 tps | Hit=89.2% | NVMe=525.5 MB/s (74277.59 MB, QD=64) | RSS=14129.8 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.87 tps | Avg=0.88 tps | Hit=88.9% | NVMe=525.8 MB/s (145202.09 MB, QD=64) | RSS=14127.1 MB
[LIVE-DECODE] 2/128 tok | Avg=0.30 tps | Hit=88.9% (LA:+0.1%) | NVMe=526.3 MB/s (148375.09 MB) | RSS=13985.6 MB
[LIVE-DECODE] 4/128 tok | Avg=0.35 tps | Hit=88.9% (LA:+0.2%) | NVMe=526.4 MB/s (150769.90 MB) | RSS=13792.0 MB
[LIVE-DECODE] 6/128 tok | Avg=0.39 tps | Hit=88.8% (LA:+0.3%) | NVMe=526.9 MB/s (152946.34 MB) | RSS=13689.2 MB
[LIVE-DECODE] 8/128 tok | Avg=0.41 tps | Hit=88.8% (LA:+0.3%) | NVMe=527.6 MB/s (155009.77 MB) | RSS=13633.0 MB
[LIVE-DECODE] 10/128 tok | Avg=0.42 tps | Hit=88.8% (LA:+0.4%) | NVMe=528.1 MB/s (157272.84 MB) | RSS=13592.3 MB
[LIVE-DECODE] 12/128 tok | Avg=0.43 tps | Hit=88.8% (LA:+0.5%) | NVMe=528.5 MB/s (159327.84 MB) | RSS=13553.5 MB
[LIVE-DECODE] 14/128 tok | Avg=0.44 tps | Hit=88.8% (LA:+0.6%) | NVMe=528.9 MB/s (161558.34 MB) | RSS=13553.6 MB
[LIVE-DECODE] 16/128 tok | Avg=0.45 tps | Hit=88.8% (LA:+0.7%) | NVMe=529.4 MB/s (163580.65 MB) | RSS=13553.6 MB
[LIVE-DECODE] 18/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+0.7%) | NVMe=529.6 MB/s (165912.40 MB) | RSS=13553.2 MB
[LIVE-DECODE] 20/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+0.8%) | NVMe=530.2 MB/s (168241.21 MB) | RSS=13553.2 MB
[LIVE-DECODE] 22/128 tok | Avg=0.46 tps | Hit=88.7% (LA:+0.9%) | NVMe=530.8 MB/s (170209.96 MB) | RSS=13552.4 MB
[LIVE-DECODE] 24/128 tok | Avg=0.47 tps | Hit=88.7% (LA:+1.0%) | NVMe=531.3 MB/s (172030.40 MB) | RSS=13552.4 MB
[LIVE-DECODE] 26/128 tok | Avg=0.47 tps | Hit=88.7% (LA:+1.0%) | NVMe=531.8 MB/s (174149.71 MB) | RSS=13552.4 MB
[LIVE-DECODE] 28/128 tok | Avg=0.47 tps | Hit=88.7% (LA:+1.1%) | NVMe=531.9 MB/s (176255.84 MB) | RSS=13543.8 MB
[LIVE-DECODE] 30/128 tok | Avg=0.47 tps | Hit=88.6% (LA:+1.2%) | NVMe=531.7 MB/s (178249.15 MB) | RSS=13553.1 MB
[LIVE-DECODE] 32/128 tok | Avg=0.47 tps | Hit=88.6% (LA:+1.2%) | NVMe=531.3 MB/s (179976.65 MB) | RSS=13553.1 MB
[LIVE-DECODE] 34/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.3%) | NVMe=531.4 MB/s (181668.27 MB) | RSS=13553.2 MB
[LIVE-DECODE] 36/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.3%) | NVMe=531.7 MB/s (183953.84 MB) | RSS=13553.4 MB
[LIVE-DECODE] 38/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.4%) | NVMe=532.0 MB/s (186012.90 MB) | RSS=13553.4 MB
[LIVE-DECODE] 40/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.5%) | NVMe=532.5 MB/s (187923.27 MB) | RSS=13544.0 MB
[LIVE-DECODE] 42/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.5%) | NVMe=532.4 MB/s (189745.65 MB) | RSS=13544.0 MB
[LIVE-DECODE] 44/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.6%) | NVMe=532.8 MB/s (191878.59 MB) | RSS=13553.4 MB
[LIVE-DECODE] 46/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.6%) | NVMe=533.2 MB/s (193949.96 MB) | RSS=13553.4 MB
[LIVE-DECODE] 48/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.7%) | NVMe=533.6 MB/s (196051.90 MB) | RSS=13553.1 MB
[LIVE-DECODE] 50/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.8%) | NVMe=534.0 MB/s (197895.71 MB) | RSS=13553.1 MB
[LIVE-DECODE] 52/128 tok | Avg=0.50 tps | Hit=88.5% (LA:+1.8%) | NVMe=534.5 MB/s (199771.59 MB) | RSS=13545.5 MB
[LIVE-DECODE] 54/128 tok | Avg=0.50 tps | Hit=88.5% (LA:+1.9%) | NVMe=534.9 MB/s (201688.90 MB) | RSS=13545.5 MB
[LIVE-DECODE] 56/128 tok | Avg=0.50 tps | Hit=88.5% (LA:+1.9%) | NVMe=535.3 MB/s (203763.84 MB) | RSS=13545.5 MB
[LIVE-DECODE] 58/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.0%) | NVMe=535.7 MB/s (205656.59 MB) | RSS=13545.5 MB
[LIVE-DECODE] 60/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.0%) | NVMe=536.0 MB/s (207856.96 MB) | RSS=13543.8 MB
[LIVE-DECODE] 62/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.1%) | NVMe=536.3 MB/s (209608.34 MB) | RSS=13543.8 MB
[LIVE-DECODE] 64/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.1%) | NVMe=536.7 MB/s (211413.34 MB) | RSS=13553.1 MB
[LIVE-DECODE] 66/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.2%) | NVMe=537.0 MB/s (213429.40 MB) | RSS=13553.1 MB
[LIVE-DECODE] 68/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.3%) | NVMe=537.3 MB/s (215234.27 MB) | RSS=13553.1 MB
[LIVE-DECODE] 70/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.3%) | NVMe=537.7 MB/s (217024.90 MB) | RSS=13562.5 MB
[LIVE-DECODE] 72/128 tok | Avg=0.52 tps | Hit=88.4% (LA:+2.3%) | NVMe=538.1 MB/s (218720.09 MB) | RSS=13562.5 MB
[LIVE-DECODE] 74/128 tok | Avg=0.52 tps | Hit=88.4% (LA:+2.4%) | NVMe=538.5 MB/s (220365.65 MB) | RSS=13562.5 MB
[LIVE-DECODE] 76/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.4%) | NVMe=538.9 MB/s (222120.27 MB) | RSS=13562.5 MB
[LIVE-DECODE] 78/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.5%) | NVMe=539.3 MB/s (223909.59 MB) | RSS=13562.5 MB
[LIVE-DECODE] 80/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.5%) | NVMe=539.7 MB/s (225827.90 MB) | RSS=13562.5 MB
[LIVE-DECODE] 82/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.5%) | NVMe=540.2 MB/s (227723.84 MB) | RSS=13562.5 MB
[LIVE-DECODE] 84/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.6%) | NVMe=540.4 MB/s (229445.71 MB) | RSS=13551.1 MB
[LIVE-DECODE] 86/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.6%) | NVMe=540.8 MB/s (231247.84 MB) | RSS=13543.7 MB
[LIVE-DECODE] 88/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.7%) | NVMe=539.8 MB/s (232969.65 MB) | RSS=13543.7 MB
[LIVE-DECODE] 90/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.7%) | NVMe=539.1 MB/s (234978.27 MB) | RSS=13543.7 MB
[LIVE-DECODE] 92/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.7%) | NVMe=539.1 MB/s (236656.09 MB) | RSS=13543.7 MB
[LIVE-DECODE] 94/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.8%) | NVMe=538.4 MB/s (238379.21 MB) | RSS=13543.7 MB
[LIVE-DECODE] 96/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.8%) | NVMe=538.7 MB/s (239959.21 MB) | RSS=13543.7 MB
[LIVE-DECODE] 98/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.8%) | NVMe=539.0 MB/s (241611.52 MB) | RSS=13543.7 MB
[LIVE-DECODE] 100/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+2.9%) | NVMe=539.3 MB/s (243253.02 MB) | RSS=13532.7 MB
[LIVE-DECODE] 102/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+2.9%) | NVMe=539.6 MB/s (244843.90 MB) | RSS=13518.6 MB
[LIVE-DECODE] 104/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+2.9%) | NVMe=539.9 MB/s (246290.15 MB) | RSS=13515.6 MB
[LIVE-DECODE] 106/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+2.9%) | NVMe=540.2 MB/s (248618.09 MB) | RSS=13525.0 MB
[LIVE-DECODE] 108/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.0%) | NVMe=540.5 MB/s (250355.15 MB) | RSS=13525.0 MB
[LIVE-DECODE] 110/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.0%) | NVMe=540.4 MB/s (252438.40 MB) | RSS=13543.7 MB
[LIVE-DECODE] 112/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.1%) | NVMe=540.6 MB/s (254737.71 MB) | RSS=13562.5 MB
[LIVE-DECODE] 114/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.1%) | NVMe=540.8 MB/s (256580.09 MB) | RSS=13562.5 MB
[LIVE-DECODE] 116/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.2%) | NVMe=541.2 MB/s (258279.77 MB) | RSS=13562.5 MB
[LIVE-DECODE] 118/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.2%) | NVMe=541.2 MB/s (260107.59 MB) | RSS=13553.1 MB
[LIVE-DECODE] 120/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.3%) | NVMe=541.4 MB/s (261927.46 MB) | RSS=13553.1 MB
[LIVE-DECODE] 122/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.3%) | NVMe=541.7 MB/s (263574.84 MB) | RSS=13553.1 MB
[LIVE-DECODE] 124/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.4%) | NVMe=542.0 MB/s (265262.77 MB) | RSS=13553.1 MB
[LIVE-DECODE] 126/128 tok | Avg=0.55 tps | Hit=88.1% (LA:+3.4%) | NVMe=542.2 MB/s (266908.27 MB) | RSS=13553.1 MB
[LIVE-DECODE] 128/128 tok | Avg=0.55 tps | Hit=88.1% (LA:+3.5%) | NVMe=542.5 MB/s (268419.40 MB) | RSS=13553.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.70 MB | End=13553.13 MB | Peak=14194.16 MB
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
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 579400.80 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   21.27 |  96.3% |    1062 |   17.44 | 3283.43 | 46 |159 |131 | 1624576.0 |
   |    3 |   22412 | -co            |   14.00 |  19.9% |   11492 |   13.04 | 3283.43 |  0 |  0 |  0 | 1624576.0 |
   |    4 |    3831 | ales           |   20.23 |  56.4% |     278 |   19.95 | 2403.41 | 96 |166 | 74 | 1226144.0 |
   |    5 |    1998 | ced            |   23.84 |  95.9% |    6125 |   20.05 | 2403.41 |  0 |  0 |  0 | 1226144.0 |
   |    6 |     291 | ed             |   13.00 |  12.2% |      11 |   12.82 | 2015.87 |124 |144 | 68 | 1114336.0 |
   |    7 |     291 | ed             |   17.54 |  71.5% |   11492 |   15.78 | 2015.87 |  0 |  0 |  0 | 1114336.0 |
   |    8 |   39929 |  LB            |   16.46 |  74.9% |      11 |   14.17 | 2115.60 |153 |119 | 64 | 1056480.0 |
   |   30 |    9421 | -block         |   14.49 |  25.5% |    7299 |   13.80 | 2465.99 |151 |113 | 72 | 1020576.0 |
   |   31 |     291 | ed             |   20.39 |  98.8% |   29819 |   13.17 | 2465.99 |  0 |  0 |  0 | 1020576.0 |
   |  112 |      12 | -              |   17.05 |  71.2% |     220 |   14.83 | 2363.14 |113 |150 | 73 | 1177248.0 |
   |  113 |      17 | 2              |   22.18 |  99.2% |      16 |   15.80 | 2363.14 |  0 |  0 |  0 | 1177248.0 |
   |  126 |   10772 | GE             |   14.45 |  16.7% |    2646 |   14.40 | 1510.76 |198 | 83 | 55 | 842496.0 |
   |  127 |   50127 | KK             |   13.12 |  16.3% |      42 |   12.88 | 1510.76 |  0 |  0 |  0 | 842496.0 |
   |  128 |   50127 | KK             |   14.93 |  24.1% |      42 |   14.93 | 1342.10 |212 | 80 | 44 | 773696.0 |
   |  129 |   10772 | GE             |   18.90 |  83.6% |   22197 |   15.87 | 1342.10 |  0 |  0 |  0 | 773696.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 579.401s, TTFT=579400.80ms): Avg=0.88 | Min=0.87 | Max=0.89 tps
   Prefill Chunks (2): C1:256t/0.9tps/89% | C2:256t/0.9tps/89%
   Decode  (128 tok, 233.450s): Avg=0.55 | Min=0.30 | Max=0.76 tps
   Latency (ms) : Min=1308.00 | P10=1482.50 | P25=1617.80 | P50=1749.61 | P75=2025.33 | P90=2151.35 | P95=2363.14 | P99=3283.43 | Max=3283.43
   Mean/SD/Jitt : Mean=1823.83ms | StdDev=322.17ms | Jitter=113.83ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=163754 (84.61%) | Lookahead=6678 (+3.45%) | ColdMiss=23104 (11.94%) | EFF HIT=88.06%
   Lookahead    : 12556 prefetched -> 6678 consumed (53.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 88.8% | @64= 88.4% | @128= 88.1% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3720 | 331 | 557 | 87.9%|6382.50 | | L24 | 4608 | 4013 | 115 | 480 | 89.6%|5016.88 |
   | L04 | 4608 | 3817 | 132 | 659 | 85.7%|7475.00 | | L25 | 4608 | 3931 | 134 | 543 | 88.2%|6360.94 |
   | L05 | 4608 | 3769 | 172 | 667 | 85.5%|7360.00 | | L26 | 4608 | 3964 | 137 | 507 | 89.0%|5534.38 |
   | L06 | 4608 | 3760 | 218 | 630 | 86.3%|6935.94 | | L27 | 4608 | 3874 | 162 | 572 | 87.6%|6756.25 |
   | L07 | 4608 | 3883 | 199 | 526 | 88.6%|5893.75 | | L28 | 4608 | 3853 | 189 | 566 | 87.7%|6382.50 |
   | L08 | 4608 | 3886 | 136 | 586 | 87.3%|6662.81 | | L29 | 4608 | 3889 | 195 | 524 | 88.6%|5929.69 |
   | L09 | 4608 | 3866 | 155 | 587 | 87.3%|6332.19 | | L30 | 4608 | 3819 | 189 | 600 | 87.0%|6727.50 |
   | L10 | 4608 | 3850 | 142 | 616 | 86.6%|6274.69 | | L31 | 4608 | 3847 | 134 | 627 | 86.4%|6935.94 |
   | L11 | 4608 | 3873 | 177 | 558 | 87.9%|8381.25 | | L32 | 4608 | 3817 | 153 | 638 | 86.2%|6914.38 |
   | L12 | 4608 | 3910 | 157 | 541 | 88.3%|6808.88 | | L33 | 4608 | 3829 | 190 | 589 | 87.2%|6971.88 |
   | L13 | 4608 | 3960 | 132 | 516 | 88.8%|5606.25 | | L34 | 4608 | 3855 | 229 | 524 | 88.6%|6202.81 |
   | L14 | 4608 | 3977 | 106 | 525 | 88.6%|5620.62 | | L35 | 4608 | 3815 | 226 | 567 | 87.7%|6619.69 |
   | L15 | 4608 | 3933 | 130 | 545 | 88.2%|5850.62 | | L36 | 4608 | 3813 | 255 | 540 | 88.3%|6382.50 |
   | L16 | 4608 | 3939 | 148 | 521 | 88.7%|5606.25 | | L37 | 4608 | 3906 | 171 | 531 | 88.5%|5591.88 |
   | L17 | 4608 | 3921 | 117 | 570 | 87.6%|6238.75 | | L38 | 4608 | 3884 | 182 | 542 | 88.2%|6152.50 |
   | L18 | 4608 | 3997 | 103 | 508 | 89.0%|5656.56 | | L39 | 4608 | 3862 | 203 | 543 | 88.2%|6037.50 |
   | L19 | 4608 | 3986 | 121 | 501 | 89.1%|5548.75 | | L40 | 4608 | 3876 | 176 | 556 | 87.9%|6195.62 |
   | L20 | 4608 | 3987 | 117 | 504 | 89.1%|5347.50 | | L41 | 4608 | 3960 | 133 | 515 | 88.8%|5476.88 |
   | L21 | 4608 | 3983 | 139 | 486 | 89.5%|5189.38 | | L42 | 4608 | 4017 |  99 | 492 | 89.3%|5397.81 |
   | L22 | 4608 | 4000 | 120 | 488 | 89.4%|5383.44 | | L43 | 4608 | 4033 | 107 | 468 | 89.8%|4966.56 |
   | L23 | 4608 | 3937 | 129 | 542 | 88.2%|5872.19 | | L44 | 4608 | 3943 | 118 | 547 | 88.1%|7277.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 268419.40 MB (Load=6361.84 | Prefill=138840.25 | Warmup=0.00 | Decode=123217.31 MB)
   SSD Data/Token (Decode)      : Avg=962.635 MB/tok (Min=723.125 | P50=937.938 | P95=1164.406 | Max=1586.500 MB) | Prefill=271.172 MB/tok
   NVMe Batches / Requests      : 5127 Batches | 108884 Raw -> 107523 Merged (1361 LBA Merges, Avg 2556.3 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=106644
   SSD Read Bandwidth (Active)  : Min=19.10 | Avg=542.53 | Peak=4097.30 MB/s | WallAmort=330.22 MB/s
   OS Kernel I/O Verification   : Read=268428.43 MB | Write=0.01 MB | Syscalls=111608
   Sync Stall vs Async DMA      : SyncStall=318652.81 ms | AsyncOverlapped=482331.09 ms (60.2% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=7.24 GB/s | WallAmort=3.42 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=579.40s (71.3%, 138840.25 MB SSD) | Decode=233.45s (28.7%, 123217.31 MB SSD)
   CPU Time & Utilization       : User=1314.328s + Sys=18.625s (Wall=829.233s) | SysUtil=40.2% | ThrUtil=40.2% | 37.17 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 174413.87 ms (272521.7 us/tok | 21.46%)
   MoE AVX2 Q8 Expert Compute   : 207183.71 ms (323724.5 us/tok | 25.49%)
   Router + Lookahead Dispatch  :   3268.42 ms ( 5106.9 us/tok |  0.40%)
   LM Head Output Projection    :   2613.72 ms ( 4083.9 us/tok |  0.32%)
   Foreground NVMe Sync Stall   : 318652.81 ms (497895.0 us/tok | 39.20%)
   Unaccounted / OMP & Sampling : 106717.91 ms (166746.7 us/tok | 13.13%) | Total Wall=812850.45 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    60.00%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.25%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    17.24%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.15%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.36%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 111804.4ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='\nSummarize LBACoalesce in one sentence.\nSummarize LB'
[Stage 3] /v1/chat/completions (stream=true SSE) 45724.8ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5671.88 MB (605 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=0.89 tps | Avg=0.89 tps | Hit=89.2% | NVMe=529.8 MB/s (74277.59 MB, QD=64) | RSS=14149.4 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=0.85 tps | Avg=0.87 tps | Hit=88.9% | NVMe=526.9 MB/s (145202.09 MB, QD=64) | RSS=14117.7 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=0.83 tps | Avg=0.86 tps | Hit=88.9% | NVMe=522.1 MB/s (214523.84 MB, QD=64) | RSS=14148.9 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=0.83 tps | Avg=0.85 tps | Hit=89.0% | NVMe=511.3 MB/s (283521.59 MB, QD=64) | RSS=14148.9 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=0.84 tps | Avg=0.85 tps | Hit=89.0% | NVMe=506.1 MB/s (352158.46 MB, QD=64) | RSS=14148.9 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=0.84 tps | Avg=0.85 tps | Hit=89.0% | NVMe=504.3 MB/s (420199.90 MB, QD=64) | RSS=14149.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=0.87 tps | Avg=0.85 tps | Hit=89.0% | NVMe=506.8 MB/s (487453.77 MB, QD=64) | RSS=14148.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=0.84 tps | Avg=0.85 tps | Hit=89.1% | NVMe=503.8 MB/s (553094.27 MB, QD=64) | RSS=14146.4 MB
[LIVE-DECODE] 2/64 tok | Avg=0.31 tps | Hit=89.1% (LA:+0.0%) | NVMe=504.0 MB/s (555435.59 MB) | RSS=14068.1 MB
[LIVE-DECODE] 4/64 tok | Avg=0.33 tps | Hit=89.1% (LA:+0.0%) | NVMe=504.2 MB/s (558342.09 MB) | RSS=13752.8 MB
[LIVE-DECODE] 6/64 tok | Avg=0.37 tps | Hit=89.1% (LA:+0.1%) | NVMe=504.4 MB/s (560724.90 MB) | RSS=13627.0 MB
[LIVE-DECODE] 8/64 tok | Avg=0.38 tps | Hit=89.1% (LA:+0.1%) | NVMe=504.7 MB/s (563057.71 MB) | RSS=13603.2 MB
[LIVE-DECODE] 10/64 tok | Avg=0.40 tps | Hit=89.1% (LA:+0.1%) | NVMe=504.9 MB/s (565194.34 MB) | RSS=13581.6 MB
[LIVE-DECODE] 12/64 tok | Avg=0.41 tps | Hit=89.1% (LA:+0.1%) | NVMe=505.0 MB/s (567325.40 MB) | RSS=13563.6 MB
[LIVE-DECODE] 14/64 tok | Avg=0.43 tps | Hit=89.1% (LA:+0.1%) | NVMe=505.2 MB/s (569408.21 MB) | RSS=13573.0 MB
[LIVE-DECODE] 16/64 tok | Avg=0.44 tps | Hit=89.1% (LA:+0.2%) | NVMe=505.4 MB/s (571521.90 MB) | RSS=13572.9 MB
[LIVE-DECODE] 18/64 tok | Avg=0.44 tps | Hit=89.1% (LA:+0.2%) | NVMe=505.7 MB/s (573760.02 MB) | RSS=13572.9 MB
[LIVE-DECODE] 20/64 tok | Avg=0.44 tps | Hit=89.1% (LA:+0.2%) | NVMe=505.9 MB/s (576033.15 MB) | RSS=13572.9 MB
[LIVE-DECODE] 22/64 tok | Avg=0.45 tps | Hit=89.1% (LA:+0.2%) | NVMe=506.1 MB/s (578168.15 MB) | RSS=13573.0 MB
[LIVE-DECODE] 24/64 tok | Avg=0.45 tps | Hit=89.0% (LA:+0.2%) | NVMe=506.1 MB/s (580418.59 MB) | RSS=13573.0 MB
[LIVE-DECODE] 26/64 tok | Avg=0.45 tps | Hit=89.0% (LA:+0.3%) | NVMe=506.3 MB/s (582587.71 MB) | RSS=13573.0 MB
[LIVE-DECODE] 28/64 tok | Avg=0.46 tps | Hit=89.0% (LA:+0.3%) | NVMe=506.6 MB/s (584531.46 MB) | RSS=13563.6 MB
[LIVE-DECODE] 30/64 tok | Avg=0.46 tps | Hit=89.0% (LA:+0.3%) | NVMe=506.8 MB/s (586689.90 MB) | RSS=13573.0 MB
[LIVE-DECODE] 32/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=507.0 MB/s (588683.46 MB) | RSS=13573.0 MB
[LIVE-DECODE] 34/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=507.2 MB/s (590735.27 MB) | RSS=13572.9 MB
[LIVE-DECODE] 36/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=507.4 MB/s (592692.84 MB) | RSS=13582.3 MB
[LIVE-DECODE] 38/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.4%) | NVMe=507.6 MB/s (594684.15 MB) | RSS=13582.3 MB
[LIVE-DECODE] 40/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.4%) | NVMe=507.7 MB/s (596786.09 MB) | RSS=13582.3 MB
[LIVE-DECODE] 42/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=507.8 MB/s (598794.84 MB) | RSS=13573.0 MB
[LIVE-DECODE] 44/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=508.0 MB/s (600881.96 MB) | RSS=13573.0 MB
[LIVE-DECODE] 46/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=508.2 MB/s (603182.59 MB) | RSS=13582.3 MB
[LIVE-DECODE] 48/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.5%) | NVMe=508.4 MB/s (605175.59 MB) | RSS=13582.3 MB
[LIVE-DECODE] 50/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.5%) | NVMe=508.6 MB/s (607114.84 MB) | RSS=13582.4 MB
[LIVE-DECODE] 52/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.5%) | NVMe=508.8 MB/s (609000.84 MB) | RSS=13582.4 MB
[LIVE-DECODE] 54/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=509.0 MB/s (610908.59 MB) | RSS=13582.3 MB
[LIVE-DECODE] 56/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=509.2 MB/s (612898.21 MB) | RSS=13573.0 MB
[LIVE-DECODE] 58/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=509.3 MB/s (614758.96 MB) | RSS=13582.3 MB
[LIVE-DECODE] 60/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=509.5 MB/s (616618.34 MB) | RSS=13582.4 MB
[LIVE-DECODE] 62/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.6%) | NVMe=509.7 MB/s (618538.02 MB) | RSS=13582.4 MB
[LIVE-DECODE] 64/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.6%) | NVMe=509.8 MB/s (620405.90 MB) | RSS=13582.4 MB

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
   LRFU Cache / Staging Ring    : 5671.88 MB (605/12384 exp = 4.89% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.66 MB | End=13582.35 MB | Peak=14220.20 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : " high-throughput Mixtures of Mixtures-of-Expert (MoE) language inference with NVMe offloading achieving low token requires overlapping PCIe Gen3/ DMA compute attention recurrent state trunks. Window combining Window cache dual horiz lookahead co over prefetching activations RAM directly RAM pipeline. contexts inverted tables tokens expert coal LB Qsort"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=43.9% | AvgMargin=1.435 | MinMargin=0.013
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    1550 |  high          |   25.48 | 100.0% |     279 |   13.45 | 2408423.57 |  0 |  0 |  0 |     0.0 |
   |    2 |   42503 | -through       |   26.97 | 100.0% |   19705 |   16.32 | 3252.92 |137 |106 | 93 | 1198752.0 |
   |    3 |     628 | put            |   23.70 |  99.6% |   19183 |   17.62 | 3252.92 |  0 |  0 |  0 | 1198752.0 |
   |    4 |   19183 |  Mix           |   17.29 |  81.5% |   19705 |   14.69 | 2753.92 | 39 |211 | 86 | 1488128.0 |
   |    5 |   18482 | tures          |   16.23 |  44.3% |      68 |   15.40 | 2753.92 |  0 |  0 |  0 | 1488128.0 |
   |    6 |     315 |  of            |   13.96 |  18.4% |    8667 |   13.90 | 2211.47 |107 |155 | 74 | 1220000.0 |
   |    7 |   19183 |  Mix           |   18.62 |  90.8% |   57687 |   15.49 | 2211.47 |  0 |  0 |  0 | 1220000.0 |
   |    8 |   18482 | tures          |   16.60 |  61.9% |    4974 |   15.05 | 2181.73 |121 |141 | 74 | 1194400.0 |
   |   24 |    3347 |  low           |   16.80 |  51.9% |    9467 |   15.23 | 2325.00 |134 |137 | 65 | 1152224.0 |
   |   25 |    3950 |  token         |   15.83 |  23.5% |   97580 |   15.43 | 2325.00 |  0 |  0 |  0 | 1152224.0 |
   |   46 |   86025 |  lookahead     |   14.57 |  23.9% |    1062 |   14.34 | 2291.04 |126 |133 | 77 | 1177920.0 |
   |   47 |    1062 |  co            |   16.68 |  40.2% |    4389 |   16.21 | 2291.04 |  0 |  0 |  0 | 1177920.0 |
   |   62 |   11492 |  coal          |   16.12 |  32.1% |    1062 |   15.49 | 1763.04 |176 | 94 | 66 | 982880.0 |
   |   63 |   39929 |  LB            |   15.17 |  15.6% |    6203 |   14.88 | 1763.04 |  0 |  0 |  0 | 982880.0 |
   |   64 |    1207 |  Q             |   15.36 |  35.6% |   12149 |   13.79 | 1730.53 |181 |100 | 55 | 956352.0 |
   |   65 |    6860 | sort           |   14.90 |  19.9% |   46254 |   13.96 | 1730.53 |  0 |  0 |  0 | 956352.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2408.424s, TTFT=2408423.57ms): Avg=0.85 | Min=0.83 | Max=0.89 tps
   Prefill Chunks (8): C1:256t/0.9tps/89% | C2:256t/0.9tps/89% | C3:256t/0.8tps/89% | C4:256t/0.8tps/89%
                       C5:256t/0.8tps/89% | C6:256t/0.8tps/89% | C7:256t/0.9tps/89% | C8:256t/0.8tps/89%
   Decode  (64 tok, 128.646s): Avg=0.50 | Min=0.31 | Max=0.59 tps
   Latency (ms) : Min=1705.82 | P10=1763.04 | P25=1823.54 | P50=1950.95 | P75=2101.78 | P90=2291.04 | P95=2753.92 | P99=3252.92 | Max=3252.92
   Mean/SD/Jitt : Mean=2010.09ms | StdDev=309.48ms | Jitter=81.43ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (698880): RawRAM=617784 (88.40%) | Lookahead=4009 (+0.57%) | ColdMiss=77087 (11.03%) | EFF HIT=88.97%
   Lookahead    : 6866 prefetched -> 4009 consumed (58.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 89.1% | @64= 89.0% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |16640 |14185 | 232 |2223 | 86.6%|17645.31 | | L24 |16640 |14852 |  52 |1736 | 89.6%|13325.62 |
   | L04 |16640 |14258 | 106 |2276 | 86.3%|18004.69 | | L25 |16640 |14831 |  79 |1730 | 89.6%|13591.56 |
   | L05 |16640 |14220 | 161 |2259 | 86.4%|17918.44 | | L26 |16640 |14826 |  62 |1752 | 89.5%|13512.50 |
   | L06 |16640 |14249 | 177 |2214 | 86.7%|17630.94 | | L27 |16640 |14719 |  83 |1838 | 89.0%|14569.06 |
   | L07 |16640 |14528 | 138 |1974 | 88.1%|15618.44 | | L28 |16640 |14703 |  98 |1839 | 88.9%|14375.00 |
   | L08 |16640 |14511 |  92 |2037 | 87.8%|16071.25 | | L29 |16640 |14829 |  84 |1727 | 89.6%|13469.38 |
   | L09 |16640 |14510 | 109 |2021 | 87.9%|16013.75 | | L30 |16640 |14731 |  87 |1822 | 89.1%|13994.06 |
   | L10 |16640 |14364 | 133 |2143 | 87.1%|16926.56 | | L31 |16640 |14735 |  53 |1852 | 88.9%|14720.00 |
   | L11 |16640 |14703 | 128 |1809 | 89.1%|18862.50 | | L32 |16640 |14684 |  99 |1857 | 88.8%|14684.06 |
   | L12 |16640 |14748 | 108 |1784 | 89.3%|16440.12 | | L33 |16640 |14854 |  92 |1694 | 89.8%|13562.81 |
   | L13 |16640 |14925 |  76 |1639 | 90.2%|12729.06 | | L34 |16640 |14788 |  92 |1760 | 89.4%|13605.94 |
   | L14 |16640 |15018 |  78 |1544 | 90.7%|12305.00 | | L35 |16640 |14720 | 108 |1812 | 89.1%|14137.81 |
   | L15 |16640 |15114 |  81 |1445 | 91.3%|11413.75 | | L36 |16640 |14673 | 121 |1846 | 88.9%|14396.56 |
   | L16 |16640 |14943 |  85 |1612 | 90.3%|12664.38 | | L37 |16640 |14696 |  97 |1847 | 88.9%|14295.94 |
   | L17 |16640 |14804 |  56 |1780 | 89.3%|13692.19 | | L38 |16640 |14686 |  98 |1856 | 88.8%|14403.75 |
   | L18 |16640 |14931 |  47 |1662 | 90.0%|12980.62 | | L39 |16640 |14595 | 112 |1933 | 88.4%|15014.69 |
   | L19 |16640 |14889 |  61 |1690 | 89.8%|12908.75 | | L40 |16640 |14679 |  83 |1878 | 88.7%|14461.25 |
   | L20 |16640 |14856 |  55 |1729 | 89.6%|13340.00 | | L41 |16640 |14655 | 101 |1884 | 88.7%|14827.81 |
   | L21 |16640 |14928 |  61 |1651 | 90.1%|12671.56 | | L42 |16640 |14744 |  97 |1799 | 89.2%|13915.00 |
   | L22 |16640 |14900 |  61 |1679 | 89.9%|12930.31 | | L43 |16640 |14758 | 106 |1776 | 89.3%|13907.81 |
   | L23 |16640 |14819 |  63 |1758 | 89.4%|13469.38 | | L44 |16640 |14623 |  97 |1920 | 88.5%|17637.75 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 620405.90 MB (Load=6361.84 | Prefill=546732.44 | Warmup=0.00 | Decode=67311.62 MB)
   SSD Data/Token (Decode)      : Avg=1051.744 MB/tok (Min=929.688 | P50=1043.562 | P95=1191.406 | Max=1453.250 MB) | Prefill=266.959 MB/tok
   NVMe Batches / Requests      : 3855 Batches | 253625 Raw -> 250450 Merged (3175 LBA Merges, Avg 2536.6 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=249571
   SSD Read Bandwidth (Active)  : Min=7.07 | Avg=509.84 | Peak=3972.52 MB/s | WallAmort=244.54 MB/s
   OS Kernel I/O Verification   : Read=620414.93 MB | Write=0.01 MB | Syscalls=254509
   Sync Stall vs Async DMA      : SyncStall=1114270.31 ms | AsyncOverlapped=1204378.95 ms (51.9% Overlapped)
   RAM Traffic & Active BW      : 7358.13 GB moved | Active=5.47 GB/s | WallAmort=2.90 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2408.42s (94.9%, 546732.44 MB SSD) | Decode=128.65s (5.1%, 67311.62 MB SSD)
   CPU Time & Utilization       : User=4703.969s + Sys=46.500s (Wall=2555.421s) | SysUtil=46.5% | ThrUtil=46.5% | 42.99 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 661999.32 ms (313446.6 us/tok | 26.09%)
   MoE AVX2 Q8 Expert Compute   : 680868.83 ms (322381.1 us/tok | 26.84%)
   Router + Lookahead Dispatch  :  10714.60 ms ( 5073.2 us/tok |  0.42%)
   LM Head Output Projection    :   1312.17 ms (  621.3 us/tok |  0.05%)
   Foreground NVMe Sync Stall   : 1114270.31 ms (527590.1 us/tok | 43.92%)
   Unaccounted / OMP & Sampling :  67904.15 ms (32151.6 us/tok |  2.68%) | Total Wall=2537069.38 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    68.42%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     7.67%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    14.04%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.10%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.77%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=195.0s | Competitor drastic-underperform cutoff=975.0s (5x Apex)
=== [Colibri-GLM53] CMD: ./baselines/colibri/c/glm53.exe --model D:/apex_d_drive/models/glm53 --ids 1,8,15,22,29,36,43,50,57,64,71,78,85,92,99,106,113,120,127,134,141,148,155,162,169,176,183,190,197,204,211,218,225,232,239,246,253,260,267,274,281,288,295,302,309,316,323,330,337,344,351,358,365,372,379,386,393,400,407,414,421,428,435,442 --greedy 64 32 (5x cutoff=975.0s) ===
  [Colibri-GLM53] [gguf] D:\apex_d_drive\models\glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: glm5-next, 4 part(s), 38435 tensors under the checkpoint's names (1283 renamed, 129 fused expert tensors split per expert, 0 kept as named), read in place
  [Colibri-GLM53] glm53: GGUF experts interleaved by 16 rows on 3 of 42 layers (G53_ILV16=0: the file's rows)
  [COMP-LIVE] Colibri-GLM53: elapsed=15.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=30.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=45.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=60.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=75.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=92.9s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=108.4s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=123.9s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=139.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=154.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=169.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=184.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=199.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=214.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=229.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=244.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=259.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=274.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=289.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=304.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=319.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=334.3s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=349.3s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=364.8s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=379.8s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=395.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=410.4s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=425.5s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=440.6s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=455.8s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=471.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=486.3s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=501.5s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=516.5s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=531.6s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=546.6s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=561.7s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=577.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=592.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=607.2s / cutoff=975.0s
  [Colibri-GLM53] [STATS] 43008 selections across 6945 distinct experts -> D:/apex_d_drive/models/glm53/.coli_usage
  [Colibri-GLM53] teacher_forcing 5556 335 11 15 15 22 22 22 22 36 57 22 36 64 9 154850 154850 154850 123 121 127967 127501 243 104 253 237 154842 1986 197 220 220 0 220 154827 154827 154827 154827 220 83 220 274 220 220 274 295 83 279 8 220 1 1 2776 72 83 84 365 13 220 220 220 320 83 220 220
  [Colibri-GLM53] greedy 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330
  [Colibri-GLM53] decode 64 token in 498.8s = 0.128 tok/s (7.8 s/token)
  [Colibri-GLM53] experts hits 15425 miss 11249 bytes 111319384064
  [COMP-LIVE] Colibri-GLM53: elapsed=622.5s / cutoff=975.0s
=== [Colibri-GLM53] Finished rc=0 elapsed=622.99s cancelled=False ===
================================================================================
 [Stage 5 Summary] GLM53 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 0.53 | 0.56 | 1618.16 | 75.35% | 544.65 | 13810.34 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 0.88 | 0.55 | 1749.61 | 88.06% | 542.53 | 14194.16 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 0.85 | 0.50 | 1950.95 | 88.97% | 509.84 | 14220.20 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.128 | - | 57.8% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 868K Nov 13 17:47 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 868K Nov 13 17:47 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.48 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    581.16 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2342.44 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9357.34 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10824.25 MB/s
   RND4K Q32T16 Read                  :    756.32 MB/s (  193618 IOPS)
   RND4K Q1T1  Read                   :    836.75 MB/s (Latency: 4.67 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     50.99 GB/s
   AVX2 256-bit Sequential Write BW   :     41.27 GB/s
   STREAM Triad (A = B + s*C) BW      :     30.99 GB/s
   Random Pointer-Chase Latency       :    138.01 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.49 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    225.19 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.70 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1856.75 tps | Avg=1856.75 tps | Hit=99.5% | NVMe=2439.3 MB/s (6.19 MB, QD=64) | RSS=71.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1654.24 tps | Avg=1749.65 tps | Hit=99.5% | NVMe=2321.9 MB/s (7.01 MB, QD=64) | RSS=71.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1415.58 tps | Avg=1622.06 tps | Hit=99.5% | NVMe=2235.3 MB/s (7.78 MB, QD=64) | RSS=71.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1253.45 tps | Avg=1510.97 tps | Hit=99.5% | NVMe=2164.5 MB/s (8.61 MB, QD=64) | RSS=72.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1144.46 tps | Avg=1420.02 tps | Hit=99.5% | NVMe=2092.3 MB/s (9.33 MB, QD=64) | RSS=72.2 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1009.19 tps | Avg=1329.80 tps | Hit=99.5% | NVMe=2025.8 MB/s (10.06 MB, QD=64) | RSS=72.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=948.40 tps | Avg=1257.55 tps | Hit=99.5% | NVMe=1957.8 MB/s (10.83 MB, QD=64) | RSS=72.8 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=861.24 tps | Avg=1189.15 tps | Hit=99.5% | NVMe=1935.0 MB/s (11.60 MB, QD=64) | RSS=73.0 MB
[LIVE-DECODE] 8/32 tok | Avg=264.84 tps | Hit=99.5% (LA:+0.0%) | NVMe=1858.4 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=257.17 tps | Hit=99.5% (LA:+0.1%) | NVMe=1817.5 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=248.11 tps | Hit=99.5% (LA:+0.1%) | NVMe=1779.1 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=251.07 tps | Hit=99.5% (LA:+0.1%) | NVMe=1766.4 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=73.06 MB | Peak=73.06 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1722.24 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    3.83 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    3.83 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    3.83 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    3.83 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    3.74 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    3.74 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    3.70 | 11 |  1 |  0 |    49.5 |
   |   16 |     246 | tok_246        |  170.49 |  98.4% |      55 |  166.39 |    4.62 | 12 |  0 |  0 |     0.0 |
   |   17 |     228 | tok_228        |   91.50 | 100.0% |     246 |   70.88 |    4.62 |  0 |  0 |  0 |     0.0 |
   |   20 |      86 | tok_86         |  167.81 |  99.1% |     246 |  163.11 |    4.39 | 12 |  0 |  0 |    24.8 |
   |   21 |      68 | tok_68         |  177.01 | 100.0% |     246 |  152.23 |    4.39 |  0 |  0 |  0 |    24.8 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    3.65 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    3.65 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    3.67 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    3.67 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.722s, TTFT=1722.24ms): Avg=1189.15 | Min=861.24 | Max=1856.75 tps
   Prefill Chunks (8): C1:256t/1856.8tps/99% | C2:256t/1654.2tps/99% | C3:256t/1415.6tps/99% | C4:256t/1253.5tps/99%
                       C5:256t/1144.5tps/99% | C6:256t/1009.2tps/99% | C7:256t/948.4tps/99% | C8:256t/861.2tps/99%
   Decode  (32 tok, 0.127s): Avg=251.07 | Min=216.62 | Max=274.33 tps
   Latency (ms) : Min=3.65 | P10=3.67 | P25=3.77 | P50=3.83 | P75=4.30 | P90=4.39 | P95=4.62 | P99=4.62 | Max=4.62
   Mean/SD/Jitt : Mean=3.98ms | StdDev=0.30ms | Jitter=0.07ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=281.70 | Avg=1766.39 | Peak=6218.91 MB/s | WallAmort=7.19 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=5.11 ms | AsyncOverlapped=6.32 ms (55.3% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.82 GB/s | WallAmort=0.77 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.72s (93.1%, 6.19 MB SSD) | Decode=0.13s (6.9%, 1.69 MB SSD)
   CPU Time & Utilization       : User=2.203s + Sys=0.578s (Wall=1.869s) | SysUtil=37.2% | ThrUtil=37.2% | 34.41 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1552.69 ms (  746.5 us/tok | 83.94%)
   MoE AVX2 Q8 Expert Compute   :    189.40 ms (   91.1 us/tok | 10.24%)
   Router + Lookahead Dispatch  :     48.89 ms (   23.5 us/tok |  2.64%)
   LM Head Output Projection    :      4.55 ms (    2.2 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      5.11 ms (    2.5 us/tok |  0.28%)
   Unaccounted / OMP & Sampling :     49.06 ms (   23.6 us/tok |  2.65%) | Total Wall=1849.70 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    26.46%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.20%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.49%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    68.60%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.25%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2571.00 tps | Avg=2571.00 tps | Hit=99.2% | NVMe=3106.7 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2510.07 tps | Avg=2540.17 tps | Hit=99.2% | NVMe=4047.2 MB/s (42.92 MB, QD=64) | RSS=89.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2056.47 tps | Avg=2355.49 tps | Hit=99.2% | NVMe=4537.2 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2195.26 tps | Avg=2313.28 tps | Hit=99.2% | NVMe=4932.2 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2035.07 tps | Avg=2251.71 tps | Hit=99.2% | NVMe=5209.9 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1894.21 tps | Avg=2183.04 tps | Hit=99.2% | NVMe=5419.4 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1681.78 tps | Avg=2093.89 tps | Hit=99.2% | NVMe=5588.0 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1654.62 tps | Avg=2026.63 tps | Hit=99.2% | NVMe=5744.3 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=245.58 tps | Hit=99.2% (LA:+0.0%) | NVMe=5642.6 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=247.92 tps | Hit=99.2% (LA:+0.1%) | NVMe=5583.1 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=248.40 tps | Hit=99.2% (LA:+0.1%) | NVMe=5484.9 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=247.96 tps | Hit=99.2% (LA:+0.1%) | NVMe=5405.5 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=91.73 MB | Peak=91.73 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1010.54 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    4.14 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    4.14 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    4.07 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    4.07 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    4.06 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    4.06 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    4.02 | 16 |  0 |  0 |    32.0 |
   |   26 |     194 | qtok_194       |   70.46 | 100.0% |     128 |   54.98 |    4.06 | 12 |  4 |  0 |   147.0 |
   |   27 |      49 | qtok_49        |   67.58 |  99.9% |     209 |   61.01 |    4.06 |  0 |  0 |  0 |   147.0 |
   |   28 |      49 | qtok_49        |   65.10 | 100.0% |      18 |   55.78 |    4.04 | 10 |  6 |  0 |   115.2 |
   |   29 |     148 | qtok_148       |   77.89 | 100.0% |     127 |   51.09 |    4.04 |  0 |  0 |  0 |   115.2 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    4.06 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    4.06 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    4.06 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    4.06 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.011s, TTFT=1010.54ms): Avg=2026.63 | Min=1654.62 | Max=2571.00 tps
   Prefill Chunks (8): C1:256t/2571.0tps/99% | C2:256t/2510.1tps/99% | C3:256t/2056.5tps/99% | C4:256t/2195.3tps/99%
                       C5:256t/2035.1tps/99% | C6:256t/1894.2tps/99% | C7:256t/1681.8tps/99% | C8:256t/1654.6tps/99%
   Decode  (32 tok, 0.129s): Avg=247.96 | Min=241.58 | Max=252.43 tps
   Latency (ms) : Min=3.96 | P10=3.99 | P25=4.01 | P50=4.03 | P75=4.06 | P90=4.07 | P95=4.14 | P99=4.14 | Max=4.14
   Mean/SD/Jitt : Mean=4.03ms | StdDev=0.04ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=396.19 | Avg=5405.50 | Peak=10580.69 MB/s | WallAmort=136.13 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=7.21 ms | AsyncOverlapped=27.35 ms (79.1% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=2.13 GB/s | WallAmort=1.85 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.01s (88.7%, 144.44 MB SSD) | Decode=0.13s (11.3%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.125s + Sys=0.391s (Wall=1.170s) | SysUtil=53.7% | ThrUtil=53.7% | 49.72 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    699.90 ms (  336.5 us/tok | 61.42%)
   MoE AVX2 Q8 Expert Compute   :    284.18 ms (  136.6 us/tok | 24.94%)
   Router + Lookahead Dispatch  :     64.71 ms (   31.1 us/tok |  5.68%)
   LM Head Output Projection    :      4.07 ms (    2.0 us/tok |  0.36%)
   Foreground NVMe Sync Stall   :      7.21 ms (    3.5 us/tok |  0.63%)
   Unaccounted / OMP & Sampling :     79.53 ms (   38.2 us/tok |  6.98%) | Total Wall=1139.60 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.45%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.10%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.35%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    64.60%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.50%  |
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
    "ttft_ms": 171.96,
    "avg_tps": 953.72,
    "min_tps": 783.44,
    "max_tps": 1091.55
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 204.83,
    "min_tps": 197.74,
    "max_tps": 210.7,
    "p50_ms": 4.87,
    "p90_ms": 5.02,
    "p99_ms": 5.06,
    "mean_ms": 4.88,
    "jitter_ms": 0.06
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
    "avg_mbs": 1864.49,
    "peak_mbs": 5868.54,
    "sync_wait_ms": 1.81,
    "async_overlap_ms": 3.39
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
    "dense_attention": 270.45,
    "moe_compute": 74.3,
    "router_lookahead": 5.89,
    "lm_head": 6.02,
    "unaccounted": 3.89
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 79.85,
    "ram_bandwidth_pinning": 2.48,
    "expert_cache_lrfu": 13.87,
    "lookahead_parallel_overlap": 2.4,
    "ssd_nvme_throughput": 1.4,
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
    "ttft_ms": 220.89,
    "avg_tps": 742.46,
    "min_tps": 519.84,
    "max_tps": 855.77
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 175.74,
    "min_tps": 158.64,
    "max_tps": 183.92,
    "p50_ms": 5.68,
    "p90_ms": 5.96,
    "p99_ms": 6.3,
    "mean_ms": 5.69,
    "jitter_ms": 0.14
  },
  "cache": {
    "raw_hit_rate_pct": 85.44,
    "effective_hit_rate_pct": 94.95,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 37925472,
    "prefill_bytes": 20240384,
    "warmup_bytes": 0,
    "decode_bytes": 12128256,
    "bytes_per_token": 186824.99,
    "avg_mbs": 2444.3,
    "peak_mbs": 7183.91,
    "sync_wait_ms": 4.93,
    "async_overlap_ms": 13.77
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
    "dense_attention": 249.59,
    "moe_compute": 143.38,
    "router_lookahead": 7.11,
    "lm_head": 6.15,
    "unaccounted": 31.64
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 75.99,
    "ram_bandwidth_pinning": 2.79,
    "expert_cache_lrfu": 11.72,
    "lookahead_parallel_overlap": 5.74,
    "ssd_nvme_throughput": 3.76,
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

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.34 GB Available
   Active Drive Space : 219.98 GB Total / 219.81 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    590.35 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2346.62 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9227.09 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9412.21 MB/s
   RND4K Q32T16 Read                  :    840.18 MB/s (  215085 IOPS)
   RND4K Q1T1  Read                   :    817.96 MB/s (Latency: 4.78 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     47.95 GB/s
   AVX2 256-bit Sequential Write BW   :     42.47 GB/s
   STREAM Triad (A = B + s*C) BW      :     35.24 GB/s
   Random Pointer-Chase Latency       :    138.18 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.67 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    116.31 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.74 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 28.33 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 51.75 MB/s (19.79s)
   Window #01 (296.0 MB in 0.51s):   582.58 MB/s (Uncached Direct Read)
   Window #02 (208.0 MB in 0.52s):   398.09 MB/s (Uncached Direct Read)
   Window #03 (196.0 MB in 0.51s):   385.08 MB/s (Uncached Direct Read)
   Window #04 (196.0 MB in 0.50s):   390.88 MB/s (Uncached Direct Read)
   Window #05 (128.0 MB in 0.42s):   305.72 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   416.30 MB/s (Min=305.72 | Max=582.58 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 219.81 GB / 219.98 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 266.46 MB/s (3.84s)
   Window #01 (304.0 MB in 0.51s):   601.01 MB/s (Uncached Direct Read)
   Window #02 (268.0 MB in 0.50s):   533.87 MB/s (Uncached Direct Read)
   Window #03 (268.0 MB in 0.50s):   533.91 MB/s (Uncached Direct Read)
   Window #04 (184.0 MB in 0.35s):   531.63 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   551.74 MB/s (Min=531.63 | Max=601.01 MB/s)
================================================================================
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
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.59 GB Available
   Active Drive Space : 219.98 GB Total / 127.45 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    580.42 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2255.19 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9134.24 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7867.34 MB/s
   RND4K Q32T16 Read                  :    624.57 MB/s (  159890 IOPS)
   RND4K Q1T1  Read                   :    742.83 MB/s (Latency: 5.26 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     75.76 GB/s
   AVX2 256-bit Sequential Write BW   :     62.65 GB/s
   STREAM Triad (A = B + s*C) BW      :     46.60 GB/s
   Random Pointer-Chase Latency       :     72.37 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     57.76 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    179.67 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.83 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.53 tps | Avg=0.53 tps | Hit=73.6% | NVMe=524.9 MB/s (51661.71 MB, QD=64) | RSS=14033.4 MB

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
   LRFU Cache / Staging Ring    : 5634.38 MB (601/12384 exp = 4.85% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.67 MB | End=13507.13 MB | Peak=14113.89 MB
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
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 132902.65 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   20.50 |  79.8% |   15724 |   19.10 | 3240.63 | 20 |235 | 81 | 1512544.0 |
   |    3 |    1339 | >\n\n          |   14.01 |  20.8% |     397 |   12.96 | 3240.63 |  0 |  0 |  0 | 1512544.0 |
   |    4 |   10056 | Let            |   15.28 |  31.5% |     334 |   14.78 | 1824.75 |142 |135 | 59 | 996096.0 |
   |    5 |     752 |  me            |   16.52 |  72.1% |     594 |   14.85 | 1824.75 |  0 |  0 |  0 | 996096.0 |
   |    6 |    1744 |  think         |   15.53 |  38.0% |   23578 |   13.60 | 2030.78 |120 |164 | 52 | 1075232.0 |
   |    7 |    1526 |  through       |   17.47 |  63.7% |   15504 |   14.79 | 2030.78 |  0 |  0 |  0 | 1075232.0 |
   |    8 |     419 |  this          |   17.34 |  55.6% |     279 |   16.09 | 2296.55 |107 |172 | 57 | 1147072.0 |
   |    9 |   15504 |  carefully     |   14.89 |   6.9% |    3019 |   14.71 | 2296.55 |  0 |  0 |  0 | 1147072.0 |
   |   42 |     594 | 's             |   17.29 |  64.6% |    1526 |   16.09 | 1939.22 |148 |108 | 80 | 1069984.0 |
   |   43 |    1526 |  through       |   21.63 |  92.8% |     279 |   18.16 | 1939.22 |  0 |  0 |  0 | 1069984.0 |
   |   12 |   32559 |  reasoning     |   14.05 |   8.5% |    1681 |   14.01 | 1931.22 |124 |156 | 56 | 1064640.0 |
   |   62 |    1526 |  through       |   17.43 |  49.9% |     594 |   17.31 | 1797.24 |180 | 68 | 88 | 1031744.0 |
   |   63 |     594 | 's             |   21.37 |  93.3% |    1526 |   17.99 | 1797.24 |  0 |  0 |  0 | 1031744.0 |
   |   64 |     594 | 's             |   17.28 |  49.5% |    1526 |   17.16 | 1990.63 |158 |101 | 77 | 1100800.0 |
   |   65 |    1526 |  through       |   21.46 |  88.7% |     594 |   18.70 | 1990.63 |  0 |  0 |  0 | 1100800.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 132.903s, TTFT=132902.65ms): Avg=0.53 | Min=0.53 | Max=0.53 tps
   Prefill Chunks (1): C1:70t/0.5tps/74%
   Decode  (64 tok, 113.499s): Avg=0.56 | Min=0.31 | Max=0.81 tps
   Latency (ms) : Min=1234.06 | P10=1423.23 | P25=1651.57 | P50=1765.84 | P75=1896.04 | P90=1990.63 | P95=2296.55 | P99=3240.63 | Max=3240.63
   Mean/SD/Jitt : Mean=1773.42ms | StdDev=341.04ms | Jitter=117.62ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=22528 (65.73%) | Lookahead=3652 (+10.66%) | ColdMiss=8092 (23.61%) | EFF HIT=76.39%
   Lookahead    : 6418 prefetched -> 3652 consumed (56.9% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64= 76.4% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  475 | 131 | 210 | 74.3%|2450.94 | | L24 |  816 |  579 |  83 | 154 | 81.1%|2170.62 |
   | L04 |  816 |  442 |  75 | 299 | 63.4%|3450.00 | | L25 |  816 |  569 |  62 | 185 | 77.3%|2371.88 |
   | L05 |  816 |  441 | 103 | 272 | 66.7%|3291.88 | | L26 |  816 |  554 |  87 | 175 | 78.6%|2307.19 |
   | L06 |  816 |  478 |  99 | 239 | 70.7%|2846.25 | | L27 |  816 |  538 | 103 | 175 | 78.6%|2515.62 |
   | L07 |  816 |  498 | 120 | 198 | 75.7%|2645.00 | | L28 |  816 |  522 |  95 | 199 | 75.6%|2551.56 |
   | L08 |  816 |  516 |  59 | 241 | 70.5%|3040.31 | | L29 |  816 |  531 |  98 | 187 | 77.1%|2522.81 |
   | L09 |  816 |  456 |  94 | 266 | 67.4%|3220.00 | | L30 |  816 |  533 |  77 | 206 | 74.8%|2501.25 |
   | L10 |  816 |  473 | 106 | 237 | 71.0%|2954.06 | | L31 |  816 |  514 | 107 | 195 | 76.1%|2637.81 |
   | L11 |  816 |  469 | 104 | 243 | 70.2%|4087.50 | | L32 |  816 |  513 | 119 | 184 | 77.5%|2666.56 |
   | L12 |  816 |  526 |  73 | 217 | 73.4%|3115.50 | | L33 |  816 |  573 |  85 | 158 | 80.6%|2206.56 |
   | L13 |  816 |  554 |  63 | 199 | 75.6%|2357.50 | | L34 |  816 |  513 | 120 | 183 | 77.6%|2522.81 |
   | L14 |  816 |  541 |  67 | 208 | 74.5%|2731.25 | | L35 |  816 |  527 | 116 | 173 | 78.8%|2400.62 |
   | L15 |  816 |  540 |  99 | 177 | 78.3%|2379.06 | | L36 |  816 |  534 | 101 | 181 | 77.8%|2379.06 |
   | L16 |  816 |  554 |  73 | 189 | 76.8%|2278.44 | | L37 |  816 |  554 |  90 | 172 | 78.9%|2199.38 |
   | L17 |  816 |  556 |  51 | 209 | 74.4%|2379.06 | | L38 |  816 |  567 |  85 | 164 | 79.9%|2213.75 |
   | L18 |  816 |  597 |  59 | 160 | 80.4%|2120.31 | | L39 |  816 |  546 | 100 | 170 | 79.2%|2185.00 |
   | L19 |  816 |  578 |  69 | 169 | 79.3%|2098.75 | | L40 |  816 |  496 | 109 | 211 | 74.1%|2910.94 |
   | L20 |  816 |  617 |  50 | 149 | 81.7%|1796.88 | | L41 |  816 |  544 |  97 | 175 | 78.6%|2328.75 |
   | L21 |  816 |  592 |  71 | 153 | 81.2%|2055.62 | | L42 |  816 |  592 |  57 | 167 | 79.5%|2084.38 |
   | L22 |  816 |  582 |  69 | 165 | 79.8%|2314.38 | | L43 |  816 |  596 |  69 | 151 | 81.5%|2105.94 |
   | L23 |  816 |  583 |  72 | 161 | 80.3%|1983.75 | | L44 |  816 |  565 |  85 | 166 | 79.7%|2688.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 113002.52 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=61340.81 MB)
   SSD Data/Token (Decode)      : Avg=958.450 MB/tok (Min=679.188 | P50=972.750 | P95=1120.188 | Max=1477.094 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2505 Batches | 45011 Raw -> 44502 Merged (509 LBA Merges, Avg 2600.2 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=43623
   SSD Read Bandwidth (Active)  : Min=5.58 | Avg=552.00 | Peak=3749.76 MB/s | WallAmort=458.61 MB/s (100.0% of 580.4 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=113989.56 MB | Write=128.00 MB | Syscalls=56076
   Sync Stall vs Async DMA      : SyncStall=110293.95 ms | AsyncOverlapped=192584.57 ms (63.6% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=9.39 GB/s (20.1% STREAM) | WallAmort=3.15 GB/s (Max=46.60 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=132.90s (53.9%, 45299.88 MB SSD) | Decode=113.50s (46.1%, 61340.81 MB SSD)
   CPU Time & Utilization       : User=258.984s + Sys=8.703s (Wall=262.687s) | SysUtil=25.5% | ThrUtil=25.5% | 45.77 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  33760.93 ms (251947.2 us/tok | 13.70%)
   MoE AVX2 Q8 Expert Compute   :  47700.64 ms (355974.9 us/tok | 19.36%)
   Router + Lookahead Dispatch  :    658.90 ms ( 4917.2 us/tok |  0.27%)
   LM Head Output Projection    :   1313.58 ms ( 9802.8 us/tok |  0.53%)
   Foreground NVMe Sync Stall   : 110293.95 ms (823089.2 us/tok | 44.76%)
   Unaccounted / OMP & Sampling :  52673.81 ms (393088.1 us/tok | 21.38%) | Total Wall=246401.81 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    36.79%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    23.37%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    30.28%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.96%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.60%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_glm53_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5334.38 MB (569 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.53 tps | Avg=0.53 tps | Hit=73.8% | NVMe=528.3 MB/s (47437.59 MB, QD=64) | RSS=13722.8 MB
[LIVE-DECODE] 2/32 tok | Avg=0.35 tps | Hit=73.9% (LA:+1.1%) | NVMe=529.7 MB/s (50443.27 MB) | RSS=13725.4 MB
[LIVE-DECODE] 4/32 tok | Avg=0.40 tps | Hit=73.9% (LA:+1.8%) | NVMe=530.9 MB/s (52750.96 MB) | RSS=13532.2 MB
[LIVE-DECODE] 6/32 tok | Avg=0.41 tps | Hit=74.1% (LA:+2.4%) | NVMe=527.2 MB/s (54638.34 MB) | RSS=13500.7 MB
[LIVE-DECODE] 8/32 tok | Avg=0.45 tps | Hit=74.2% (LA:+2.8%) | NVMe=528.1 MB/s (56255.40 MB) | RSS=13392.5 MB
[LIVE-DECODE] 10/32 tok | Avg=0.47 tps | Hit=74.4% (LA:+3.2%) | NVMe=529.6 MB/s (57948.21 MB) | RSS=13346.2 MB
[LIVE-DECODE] 12/32 tok | Avg=0.48 tps | Hit=74.5% (LA:+3.6%) | NVMe=530.9 MB/s (59713.77 MB) | RSS=13294.0 MB
[LIVE-DECODE] 14/32 tok | Avg=0.50 tps | Hit=74.6% (LA:+4.0%) | NVMe=532.5 MB/s (61475.46 MB) | RSS=13286.2 MB
[LIVE-DECODE] 16/32 tok | Avg=0.51 tps | Hit=74.7% (LA:+4.4%) | NVMe=534.3 MB/s (63460.34 MB) | RSS=13274.7 MB
[LIVE-DECODE] 18/32 tok | Avg=0.52 tps | Hit=74.8% (LA:+4.7%) | NVMe=535.5 MB/s (65144.90 MB) | RSS=13264.3 MB
[LIVE-DECODE] 20/32 tok | Avg=0.53 tps | Hit=74.9% (LA:+5.0%) | NVMe=537.0 MB/s (67002.27 MB) | RSS=13246.8 MB
[LIVE-DECODE] 22/32 tok | Avg=0.54 tps | Hit=75.0% (LA:+5.3%) | NVMe=538.2 MB/s (68772.71 MB) | RSS=13227.7 MB
[LIVE-DECODE] 24/32 tok | Avg=0.54 tps | Hit=75.1% (LA:+5.6%) | NVMe=539.6 MB/s (70584.77 MB) | RSS=13225.0 MB
[LIVE-DECODE] 26/32 tok | Avg=0.55 tps | Hit=75.2% (LA:+5.9%) | NVMe=540.9 MB/s (72406.40 MB) | RSS=13225.0 MB
[LIVE-DECODE] 28/32 tok | Avg=0.55 tps | Hit=75.2% (LA:+6.2%) | NVMe=542.3 MB/s (74247.34 MB) | RSS=13225.0 MB
[LIVE-DECODE] 30/32 tok | Avg=0.56 tps | Hit=75.3% (LA:+6.3%) | NVMe=543.7 MB/s (76070.84 MB) | RSS=13225.0 MB
[LIVE-DECODE] 32/32 tok | Avg=0.56 tps | Hit=75.4% (LA:+6.6%) | NVMe=544.7 MB/s (77858.52 MB) | RSS=13225.0 MB

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
   LRFU Cache / Staging Ring    : 5334.38 MB (569/12384 exp = 4.59% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.67 MB | End=13224.97 MB | Peak=13810.34 MB
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
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 121489.08 |  0 |  0 |  0 |     0.0 |
   |    2 |   24923 |  persistent    |   14.20 |   9.2% |     220 |   14.17 | 2856.05 | 20 |231 | 85 | 1538912.0 |
   |    3 |   54443 |  CUDA          |   14.65 |  11.4% |    9996 |   14.41 | 2856.05 |  0 |  0 |  0 | 1538912.0 |
   |    4 |    4269 |  stream        |   14.37 |  14.3% |   11292 |   13.81 | 2178.95 |100 |166 | 70 | 1181536.0 |
   |    5 |   47414 |  pinned        |   14.48 |  22.4% |   12675 |   13.14 | 2178.95 |  0 |  0 |  0 | 1181536.0 |
   |    6 |   63637 | -memory        |   18.96 |  91.2% |    3468 |   15.18 | 2235.38 |142 |144 | 50 | 966336.0 |
   |    7 |   47414 |  pinned        |   16.01 |  30.3% |    7314 |   15.09 | 2235.38 |  0 |  0 |  0 | 966336.0 |
   |    8 |   63637 | -memory        |   16.32 |  36.5% |   47414 |   15.67 | 1525.34 |189 | 92 | 55 | 827936.0 |
   |   10 |   47414 |  pinned        |   17.39 |  70.7% |    4938 |   14.82 | 1931.17 |185 |101 | 50 | 866720.0 |
   |   11 |   63637 | -memory        |   19.83 |  93.1% |    4938 |   16.09 | 1931.17 |  0 |  0 |  0 | 866720.0 |
   |   16 |   47414 |  pinned        |   16.87 |  71.1% |   25372 |   13.63 | 1743.02 |161 |106 | 69 | 1016256.0 |
   |   17 |   63637 | -memory        |   19.08 |  72.7% |   47414 |   17.80 | 1743.02 |  0 |  0 |  0 | 1016256.0 |
   |   30 |   47414 |  pinned        |   17.05 |  51.0% |   63637 |   16.85 | 1589.23 |192 | 73 | 71 | 933632.0 |
   |   31 |   63637 | -memory        |   21.56 |  94.1% |   47414 |   18.55 | 1589.23 |  0 |  0 |  0 | 933632.0 |
   |   32 |   63637 | -memory        |   17.13 |  66.4% |   47414 |   16.08 | 1586.44 |179 | 95 | 62 | 915296.0 |
   |   33 |   47414 |  pinned        |   21.73 |  98.5% |   63637 |   16.47 | 1586.44 |  0 |  0 |  0 | 915296.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 121.489s, TTFT=121489.08ms): Avg=0.53 | Min=0.53 | Max=0.53 tps
   Prefill Chunks (1): C1:64t/0.5tps/74%
   Decode  (32 tok, 56.994s): Avg=0.56 | Min=0.35 | Max=0.66 tps
   Latency (ms) : Min=1525.34 | P10=1530.66 | P25=1589.23 | P50=1618.16 | P75=1931.17 | P90=2235.38 | P95=2856.05 | P99=2856.05 | Max=2856.05
   Mean/SD/Jitt : Mean=1781.06ms | StdDev=348.15ms | Jitter=90.43ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=18475 (68.73%) | Lookahead=1780 (+6.62%) | ColdMiss=6625 (24.65%) | EFF HIT=75.35%
   Lookahead    : 3123 prefetched -> 1780 consumed (57.0% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.7% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  354 |  75 | 211 | 67.0%|2055.62 | | L24 |  640 |  467 |  39 | 134 | 79.1%|1473.44 |
   | L04 |  640 |  335 |  43 | 262 | 59.1%|2637.81 | | L25 |  640 |  464 |  32 | 144 | 77.5%|1523.75 |
   | L05 |  640 |  352 |  52 | 236 | 63.1%|2350.31 | | L26 |  640 |  468 |  47 | 125 | 80.5%|1415.94 |
   | L06 |  640 |  376 |  61 | 203 | 68.3%|2105.94 | | L27 |  640 |  430 |  52 | 158 | 75.3%|1840.00 |
   | L07 |  640 |  404 |  62 | 174 | 72.8%|1832.81 | | L28 |  640 |  453 |  42 | 145 | 77.3%|1588.44 |
   | L08 |  640 |  416 |  37 | 187 | 70.8%|1969.38 | | L29 |  640 |  441 |  45 | 154 | 75.9%|1674.69 |
   | L09 |  640 |  378 |  42 | 220 | 65.6%|2177.81 | | L30 |  640 |  447 |  39 | 154 | 75.9%|1624.38 |
   | L10 |  640 |  385 |  43 | 212 | 66.9%|2062.81 | | L31 |  640 |  433 |  39 | 168 | 73.8%|1681.88 |
   | L11 |  640 |  420 |  45 | 175 | 72.7%|2371.88 | | L32 |  640 |  420 |  56 | 164 | 74.4%|1804.06 |
   | L12 |  640 |  433 |  46 | 161 | 74.8%|1959.75 | | L33 |  640 |  448 |  43 | 149 | 76.7%|1732.19 |
   | L13 |  640 |  446 |  41 | 153 | 76.1%|1595.62 | | L34 |  640 |  450 |  53 | 137 | 78.6%|1588.44 |
   | L14 |  640 |  459 |  29 | 152 | 76.2%|1602.81 | | L35 |  640 |  452 |  47 | 141 | 78.0%|1530.94 |
   | L15 |  640 |  455 |  30 | 155 | 75.8%|1538.12 | | L36 |  640 |  450 |  40 | 150 | 76.6%|1581.25 |
   | L16 |  640 |  459 |  46 | 135 | 78.9%|1487.81 | | L37 |  640 |  450 |  40 | 150 | 76.6%|1530.94 |
   | L17 |  640 |  454 |  36 | 150 | 76.6%|1559.69 | | L38 |  640 |  451 |  45 | 144 | 77.5%|1566.88 |
   | L18 |  640 |  475 |  30 | 135 | 78.9%|1444.69 | | L39 |  640 |  454 |  50 | 136 | 78.8%|1408.75 |
   | L19 |  640 |  464 |  34 | 142 | 77.8%|1502.19 | | L40 |  640 |  459 |  39 | 142 | 77.8%|1466.25 |
   | L20 |  640 |  464 |  40 | 136 | 78.8%|1552.50 | | L41 |  640 |  472 |  27 | 141 | 78.0%|1365.62 |
   | L21 |  640 |  466 |  50 | 124 | 80.6%|1444.69 | | L42 |  640 |  493 |  21 | 126 | 80.3%|1221.88 |
   | L22 |  640 |  468 |  42 | 130 | 79.7%|1473.44 | | L43 |  640 |  493 |  33 | 114 | 82.2%|1221.88 |
   | L23 |  640 |  437 |  39 | 164 | 74.4%|1789.69 | | L44 |  640 |  480 |  28 | 132 | 79.4%|1792.25 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 77858.52 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=30420.94 MB)
   SSD Data/Token (Decode)      : Avg=950.654 MB/tok (Min=808.531 | P50=910.812 | P95=1502.844 | Max=1502.844 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1319 Batches | 30647 Raw -> 30329 Merged (318 LBA Merges, Avg 2628.7 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=29450
   SSD Read Bandwidth (Active)  : Min=10.97 | Avg=544.65 | Peak=3901.51 MB/s | WallAmort=436.22 MB/s
   OS Kernel I/O Verification   : Read=77867.56 MB | Write=0.00 MB | Syscalls=34365
   Sync Stall vs Async DMA      : SyncStall=90457.87 ms | AsyncOverlapped=130692.78 ms (59.1% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=8.05 GB/s | WallAmort=2.73 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=121.49s (68.1%, 41075.75 MB SSD) | Decode=56.99s (31.9%, 30420.94 MB SSD)
   CPU Time & Utilization       : User=196.484s + Sys=6.266s (Wall=193.924s) | SysUtil=26.1% | ThrUtil=26.1% | 24.18 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  26003.74 ms (270872.2 us/tok | 14.57%)
   MoE AVX2 Q8 Expert Compute   :  33877.07 ms (352886.2 us/tok | 18.98%)
   Router + Lookahead Dispatch  :    480.88 ms ( 5009.2 us/tok |  0.27%)
   LM Head Output Projection    :    711.98 ms ( 7416.4 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :  90457.87 ms (942269.5 us/tok | 50.68%)
   Unaccounted / OMP & Sampling :  26951.60 ms (280745.8 us/tok | 15.10%) | Total Wall=178483.15 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    40.41%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    19.76%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.65%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.70%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.48%  |
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
[LIVE-PREFILL] 256/512 tok | Chunk=0.89 tps | Avg=0.89 tps | Hit=89.2% | NVMe=525.5 MB/s (74277.59 MB, QD=64) | RSS=14129.8 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.87 tps | Avg=0.88 tps | Hit=88.9% | NVMe=525.8 MB/s (145202.09 MB, QD=64) | RSS=14127.1 MB
[LIVE-DECODE] 2/128 tok | Avg=0.30 tps | Hit=88.9% (LA:+0.1%) | NVMe=526.3 MB/s (148375.09 MB) | RSS=13985.6 MB
[LIVE-DECODE] 4/128 tok | Avg=0.35 tps | Hit=88.9% (LA:+0.2%) | NVMe=526.4 MB/s (150769.90 MB) | RSS=13792.0 MB
[LIVE-DECODE] 6/128 tok | Avg=0.39 tps | Hit=88.8% (LA:+0.3%) | NVMe=526.9 MB/s (152946.34 MB) | RSS=13689.2 MB
[LIVE-DECODE] 8/128 tok | Avg=0.41 tps | Hit=88.8% (LA:+0.3%) | NVMe=527.6 MB/s (155009.77 MB) | RSS=13633.0 MB
[LIVE-DECODE] 10/128 tok | Avg=0.42 tps | Hit=88.8% (LA:+0.4%) | NVMe=528.1 MB/s (157272.84 MB) | RSS=13592.3 MB
[LIVE-DECODE] 12/128 tok | Avg=0.43 tps | Hit=88.8% (LA:+0.5%) | NVMe=528.5 MB/s (159327.84 MB) | RSS=13553.5 MB
[LIVE-DECODE] 14/128 tok | Avg=0.44 tps | Hit=88.8% (LA:+0.6%) | NVMe=528.9 MB/s (161558.34 MB) | RSS=13553.6 MB
[LIVE-DECODE] 16/128 tok | Avg=0.45 tps | Hit=88.8% (LA:+0.7%) | NVMe=529.4 MB/s (163580.65 MB) | RSS=13553.6 MB
[LIVE-DECODE] 18/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+0.7%) | NVMe=529.6 MB/s (165912.40 MB) | RSS=13553.2 MB
[LIVE-DECODE] 20/128 tok | Avg=0.45 tps | Hit=88.7% (LA:+0.8%) | NVMe=530.2 MB/s (168241.21 MB) | RSS=13553.2 MB
[LIVE-DECODE] 22/128 tok | Avg=0.46 tps | Hit=88.7% (LA:+0.9%) | NVMe=530.8 MB/s (170209.96 MB) | RSS=13552.4 MB
[LIVE-DECODE] 24/128 tok | Avg=0.47 tps | Hit=88.7% (LA:+1.0%) | NVMe=531.3 MB/s (172030.40 MB) | RSS=13552.4 MB
[LIVE-DECODE] 26/128 tok | Avg=0.47 tps | Hit=88.7% (LA:+1.0%) | NVMe=531.8 MB/s (174149.71 MB) | RSS=13552.4 MB
[LIVE-DECODE] 28/128 tok | Avg=0.47 tps | Hit=88.7% (LA:+1.1%) | NVMe=531.9 MB/s (176255.84 MB) | RSS=13543.8 MB
[LIVE-DECODE] 30/128 tok | Avg=0.47 tps | Hit=88.6% (LA:+1.2%) | NVMe=531.7 MB/s (178249.15 MB) | RSS=13553.1 MB
[LIVE-DECODE] 32/128 tok | Avg=0.47 tps | Hit=88.6% (LA:+1.2%) | NVMe=531.3 MB/s (179976.65 MB) | RSS=13553.1 MB
[LIVE-DECODE] 34/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.3%) | NVMe=531.4 MB/s (181668.27 MB) | RSS=13553.2 MB
[LIVE-DECODE] 36/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.3%) | NVMe=531.7 MB/s (183953.84 MB) | RSS=13553.4 MB
[LIVE-DECODE] 38/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.4%) | NVMe=532.0 MB/s (186012.90 MB) | RSS=13553.4 MB
[LIVE-DECODE] 40/128 tok | Avg=0.48 tps | Hit=88.6% (LA:+1.5%) | NVMe=532.5 MB/s (187923.27 MB) | RSS=13544.0 MB
[LIVE-DECODE] 42/128 tok | Avg=0.49 tps | Hit=88.6% (LA:+1.5%) | NVMe=532.4 MB/s (189745.65 MB) | RSS=13544.0 MB
[LIVE-DECODE] 44/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.6%) | NVMe=532.8 MB/s (191878.59 MB) | RSS=13553.4 MB
[LIVE-DECODE] 46/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.6%) | NVMe=533.2 MB/s (193949.96 MB) | RSS=13553.4 MB
[LIVE-DECODE] 48/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.7%) | NVMe=533.6 MB/s (196051.90 MB) | RSS=13553.1 MB
[LIVE-DECODE] 50/128 tok | Avg=0.49 tps | Hit=88.5% (LA:+1.8%) | NVMe=534.0 MB/s (197895.71 MB) | RSS=13553.1 MB
[LIVE-DECODE] 52/128 tok | Avg=0.50 tps | Hit=88.5% (LA:+1.8%) | NVMe=534.5 MB/s (199771.59 MB) | RSS=13545.5 MB
[LIVE-DECODE] 54/128 tok | Avg=0.50 tps | Hit=88.5% (LA:+1.9%) | NVMe=534.9 MB/s (201688.90 MB) | RSS=13545.5 MB
[LIVE-DECODE] 56/128 tok | Avg=0.50 tps | Hit=88.5% (LA:+1.9%) | NVMe=535.3 MB/s (203763.84 MB) | RSS=13545.5 MB
[LIVE-DECODE] 58/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.0%) | NVMe=535.7 MB/s (205656.59 MB) | RSS=13545.5 MB
[LIVE-DECODE] 60/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.0%) | NVMe=536.0 MB/s (207856.96 MB) | RSS=13543.8 MB
[LIVE-DECODE] 62/128 tok | Avg=0.50 tps | Hit=88.4% (LA:+2.1%) | NVMe=536.3 MB/s (209608.34 MB) | RSS=13543.8 MB
[LIVE-DECODE] 64/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.1%) | NVMe=536.7 MB/s (211413.34 MB) | RSS=13553.1 MB
[LIVE-DECODE] 66/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.2%) | NVMe=537.0 MB/s (213429.40 MB) | RSS=13553.1 MB
[LIVE-DECODE] 68/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.3%) | NVMe=537.3 MB/s (215234.27 MB) | RSS=13553.1 MB
[LIVE-DECODE] 70/128 tok | Avg=0.51 tps | Hit=88.4% (LA:+2.3%) | NVMe=537.7 MB/s (217024.90 MB) | RSS=13562.5 MB
[LIVE-DECODE] 72/128 tok | Avg=0.52 tps | Hit=88.4% (LA:+2.3%) | NVMe=538.1 MB/s (218720.09 MB) | RSS=13562.5 MB
[LIVE-DECODE] 74/128 tok | Avg=0.52 tps | Hit=88.4% (LA:+2.4%) | NVMe=538.5 MB/s (220365.65 MB) | RSS=13562.5 MB
[LIVE-DECODE] 76/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.4%) | NVMe=538.9 MB/s (222120.27 MB) | RSS=13562.5 MB
[LIVE-DECODE] 78/128 tok | Avg=0.52 tps | Hit=88.3% (LA:+2.5%) | NVMe=539.3 MB/s (223909.59 MB) | RSS=13562.5 MB
[LIVE-DECODE] 80/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.5%) | NVMe=539.7 MB/s (225827.90 MB) | RSS=13562.5 MB
[LIVE-DECODE] 82/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.5%) | NVMe=540.2 MB/s (227723.84 MB) | RSS=13562.5 MB
[LIVE-DECODE] 84/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.6%) | NVMe=540.4 MB/s (229445.71 MB) | RSS=13551.1 MB
[LIVE-DECODE] 86/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.6%) | NVMe=540.8 MB/s (231247.84 MB) | RSS=13543.7 MB
[LIVE-DECODE] 88/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.7%) | NVMe=539.8 MB/s (232969.65 MB) | RSS=13543.7 MB
[LIVE-DECODE] 90/128 tok | Avg=0.53 tps | Hit=88.3% (LA:+2.7%) | NVMe=539.1 MB/s (234978.27 MB) | RSS=13543.7 MB
[LIVE-DECODE] 92/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.7%) | NVMe=539.1 MB/s (236656.09 MB) | RSS=13543.7 MB
[LIVE-DECODE] 94/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.8%) | NVMe=538.4 MB/s (238379.21 MB) | RSS=13543.7 MB
[LIVE-DECODE] 96/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.8%) | NVMe=538.7 MB/s (239959.21 MB) | RSS=13543.7 MB
[LIVE-DECODE] 98/128 tok | Avg=0.53 tps | Hit=88.2% (LA:+2.8%) | NVMe=539.0 MB/s (241611.52 MB) | RSS=13543.7 MB
[LIVE-DECODE] 100/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+2.9%) | NVMe=539.3 MB/s (243253.02 MB) | RSS=13532.7 MB
[LIVE-DECODE] 102/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+2.9%) | NVMe=539.6 MB/s (244843.90 MB) | RSS=13518.6 MB
[LIVE-DECODE] 104/128 tok | Avg=0.54 tps | Hit=88.2% (LA:+2.9%) | NVMe=539.9 MB/s (246290.15 MB) | RSS=13515.6 MB
[LIVE-DECODE] 106/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+2.9%) | NVMe=540.2 MB/s (248618.09 MB) | RSS=13525.0 MB
[LIVE-DECODE] 108/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.0%) | NVMe=540.5 MB/s (250355.15 MB) | RSS=13525.0 MB
[LIVE-DECODE] 110/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.0%) | NVMe=540.4 MB/s (252438.40 MB) | RSS=13543.7 MB
[LIVE-DECODE] 112/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.1%) | NVMe=540.6 MB/s (254737.71 MB) | RSS=13562.5 MB
[LIVE-DECODE] 114/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.1%) | NVMe=540.8 MB/s (256580.09 MB) | RSS=13562.5 MB
[LIVE-DECODE] 116/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.2%) | NVMe=541.2 MB/s (258279.77 MB) | RSS=13562.5 MB
[LIVE-DECODE] 118/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.2%) | NVMe=541.2 MB/s (260107.59 MB) | RSS=13553.1 MB
[LIVE-DECODE] 120/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.3%) | NVMe=541.4 MB/s (261927.46 MB) | RSS=13553.1 MB
[LIVE-DECODE] 122/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.3%) | NVMe=541.7 MB/s (263574.84 MB) | RSS=13553.1 MB
[LIVE-DECODE] 124/128 tok | Avg=0.54 tps | Hit=88.1% (LA:+3.4%) | NVMe=542.0 MB/s (265262.77 MB) | RSS=13553.1 MB
[LIVE-DECODE] 126/128 tok | Avg=0.55 tps | Hit=88.1% (LA:+3.4%) | NVMe=542.2 MB/s (266908.27 MB) | RSS=13553.1 MB
[LIVE-DECODE] 128/128 tok | Avg=0.55 tps | Hit=88.1% (LA:+3.5%) | NVMe=542.5 MB/s (268419.40 MB) | RSS=13553.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.70 MB | End=13553.13 MB | Peak=14194.16 MB
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
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 579400.80 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   21.27 |  96.3% |    1062 |   17.44 | 3283.43 | 46 |159 |131 | 1624576.0 |
   |    3 |   22412 | -co            |   14.00 |  19.9% |   11492 |   13.04 | 3283.43 |  0 |  0 |  0 | 1624576.0 |
   |    4 |    3831 | ales           |   20.23 |  56.4% |     278 |   19.95 | 2403.41 | 96 |166 | 74 | 1226144.0 |
   |    5 |    1998 | ced            |   23.84 |  95.9% |    6125 |   20.05 | 2403.41 |  0 |  0 |  0 | 1226144.0 |
   |    6 |     291 | ed             |   13.00 |  12.2% |      11 |   12.82 | 2015.87 |124 |144 | 68 | 1114336.0 |
   |    7 |     291 | ed             |   17.54 |  71.5% |   11492 |   15.78 | 2015.87 |  0 |  0 |  0 | 1114336.0 |
   |    8 |   39929 |  LB            |   16.46 |  74.9% |      11 |   14.17 | 2115.60 |153 |119 | 64 | 1056480.0 |
   |   30 |    9421 | -block         |   14.49 |  25.5% |    7299 |   13.80 | 2465.99 |151 |113 | 72 | 1020576.0 |
   |   31 |     291 | ed             |   20.39 |  98.8% |   29819 |   13.17 | 2465.99 |  0 |  0 |  0 | 1020576.0 |
   |  112 |      12 | -              |   17.05 |  71.2% |     220 |   14.83 | 2363.14 |113 |150 | 73 | 1177248.0 |
   |  113 |      17 | 2              |   22.18 |  99.2% |      16 |   15.80 | 2363.14 |  0 |  0 |  0 | 1177248.0 |
   |  126 |   10772 | GE             |   14.45 |  16.7% |    2646 |   14.40 | 1510.76 |198 | 83 | 55 | 842496.0 |
   |  127 |   50127 | KK             |   13.12 |  16.3% |      42 |   12.88 | 1510.76 |  0 |  0 |  0 | 842496.0 |
   |  128 |   50127 | KK             |   14.93 |  24.1% |      42 |   14.93 | 1342.10 |212 | 80 | 44 | 773696.0 |
   |  129 |   10772 | GE             |   18.90 |  83.6% |   22197 |   15.87 | 1342.10 |  0 |  0 |  0 | 773696.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 579.401s, TTFT=579400.80ms): Avg=0.88 | Min=0.87 | Max=0.89 tps
   Prefill Chunks (2): C1:256t/0.9tps/89% | C2:256t/0.9tps/89%
   Decode  (128 tok, 233.450s): Avg=0.55 | Min=0.30 | Max=0.76 tps
   Latency (ms) : Min=1308.00 | P10=1482.50 | P25=1617.80 | P50=1749.61 | P75=2025.33 | P90=2151.35 | P95=2363.14 | P99=3283.43 | Max=3283.43
   Mean/SD/Jitt : Mean=1823.83ms | StdDev=322.17ms | Jitter=113.83ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=163754 (84.61%) | Lookahead=6678 (+3.45%) | ColdMiss=23104 (11.94%) | EFF HIT=88.06%
   Lookahead    : 12556 prefetched -> 6678 consumed (53.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 88.8% | @64= 88.4% | @128= 88.1% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3720 | 331 | 557 | 87.9%|6382.50 | | L24 | 4608 | 4013 | 115 | 480 | 89.6%|5016.88 |
   | L04 | 4608 | 3817 | 132 | 659 | 85.7%|7475.00 | | L25 | 4608 | 3931 | 134 | 543 | 88.2%|6360.94 |
   | L05 | 4608 | 3769 | 172 | 667 | 85.5%|7360.00 | | L26 | 4608 | 3964 | 137 | 507 | 89.0%|5534.38 |
   | L06 | 4608 | 3760 | 218 | 630 | 86.3%|6935.94 | | L27 | 4608 | 3874 | 162 | 572 | 87.6%|6756.25 |
   | L07 | 4608 | 3883 | 199 | 526 | 88.6%|5893.75 | | L28 | 4608 | 3853 | 189 | 566 | 87.7%|6382.50 |
   | L08 | 4608 | 3886 | 136 | 586 | 87.3%|6662.81 | | L29 | 4608 | 3889 | 195 | 524 | 88.6%|5929.69 |
   | L09 | 4608 | 3866 | 155 | 587 | 87.3%|6332.19 | | L30 | 4608 | 3819 | 189 | 600 | 87.0%|6727.50 |
   | L10 | 4608 | 3850 | 142 | 616 | 86.6%|6274.69 | | L31 | 4608 | 3847 | 134 | 627 | 86.4%|6935.94 |
   | L11 | 4608 | 3873 | 177 | 558 | 87.9%|8381.25 | | L32 | 4608 | 3817 | 153 | 638 | 86.2%|6914.38 |
   | L12 | 4608 | 3910 | 157 | 541 | 88.3%|6808.88 | | L33 | 4608 | 3829 | 190 | 589 | 87.2%|6971.88 |
   | L13 | 4608 | 3960 | 132 | 516 | 88.8%|5606.25 | | L34 | 4608 | 3855 | 229 | 524 | 88.6%|6202.81 |
   | L14 | 4608 | 3977 | 106 | 525 | 88.6%|5620.62 | | L35 | 4608 | 3815 | 226 | 567 | 87.7%|6619.69 |
   | L15 | 4608 | 3933 | 130 | 545 | 88.2%|5850.62 | | L36 | 4608 | 3813 | 255 | 540 | 88.3%|6382.50 |
   | L16 | 4608 | 3939 | 148 | 521 | 88.7%|5606.25 | | L37 | 4608 | 3906 | 171 | 531 | 88.5%|5591.88 |
   | L17 | 4608 | 3921 | 117 | 570 | 87.6%|6238.75 | | L38 | 4608 | 3884 | 182 | 542 | 88.2%|6152.50 |
   | L18 | 4608 | 3997 | 103 | 508 | 89.0%|5656.56 | | L39 | 4608 | 3862 | 203 | 543 | 88.2%|6037.50 |
   | L19 | 4608 | 3986 | 121 | 501 | 89.1%|5548.75 | | L40 | 4608 | 3876 | 176 | 556 | 87.9%|6195.62 |
   | L20 | 4608 | 3987 | 117 | 504 | 89.1%|5347.50 | | L41 | 4608 | 3960 | 133 | 515 | 88.8%|5476.88 |
   | L21 | 4608 | 3983 | 139 | 486 | 89.5%|5189.38 | | L42 | 4608 | 4017 |  99 | 492 | 89.3%|5397.81 |
   | L22 | 4608 | 4000 | 120 | 488 | 89.4%|5383.44 | | L43 | 4608 | 4033 | 107 | 468 | 89.8%|4966.56 |
   | L23 | 4608 | 3937 | 129 | 542 | 88.2%|5872.19 | | L44 | 4608 | 3943 | 118 | 547 | 88.1%|7277.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 268419.40 MB (Load=6361.84 | Prefill=138840.25 | Warmup=0.00 | Decode=123217.31 MB)
   SSD Data/Token (Decode)      : Avg=962.635 MB/tok (Min=723.125 | P50=937.938 | P95=1164.406 | Max=1586.500 MB) | Prefill=271.172 MB/tok
   NVMe Batches / Requests      : 5127 Batches | 108884 Raw -> 107523 Merged (1361 LBA Merges, Avg 2556.3 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=106644
   SSD Read Bandwidth (Active)  : Min=19.10 | Avg=542.53 | Peak=4097.30 MB/s | WallAmort=330.22 MB/s
   OS Kernel I/O Verification   : Read=268428.43 MB | Write=0.01 MB | Syscalls=111608
   Sync Stall vs Async DMA      : SyncStall=318652.81 ms | AsyncOverlapped=482331.09 ms (60.2% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=7.24 GB/s | WallAmort=3.42 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=579.40s (71.3%, 138840.25 MB SSD) | Decode=233.45s (28.7%, 123217.31 MB SSD)
   CPU Time & Utilization       : User=1314.328s + Sys=18.625s (Wall=829.233s) | SysUtil=40.2% | ThrUtil=40.2% | 37.17 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 174413.87 ms (272521.7 us/tok | 21.46%)
   MoE AVX2 Q8 Expert Compute   : 207183.71 ms (323724.5 us/tok | 25.49%)
   Router + Lookahead Dispatch  :   3268.42 ms ( 5106.9 us/tok |  0.40%)
   LM Head Output Projection    :   2613.72 ms ( 4083.9 us/tok |  0.32%)
   Foreground NVMe Sync Stall   : 318652.81 ms (497895.0 us/tok | 39.20%)
   Unaccounted / OMP & Sampling : 106717.91 ms (166746.7 us/tok | 13.13%) | Total Wall=812850.45 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    60.00%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.25%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    17.24%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.15%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.36%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_glm53_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 111804.4ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='\nSummarize LBACoalesce in one sentence.\nSummarize LB'
[Stage 3] /v1/chat/completions (stream=true SSE) 45724.8ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_glm53_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5671.88 MB (605 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=0.89 tps | Avg=0.89 tps | Hit=89.2% | NVMe=529.8 MB/s (74277.59 MB, QD=64) | RSS=14149.4 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=0.85 tps | Avg=0.87 tps | Hit=88.9% | NVMe=526.9 MB/s (145202.09 MB, QD=64) | RSS=14117.7 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=0.83 tps | Avg=0.86 tps | Hit=88.9% | NVMe=522.1 MB/s (214523.84 MB, QD=64) | RSS=14148.9 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=0.83 tps | Avg=0.85 tps | Hit=89.0% | NVMe=511.3 MB/s (283521.59 MB, QD=64) | RSS=14148.9 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=0.84 tps | Avg=0.85 tps | Hit=89.0% | NVMe=506.1 MB/s (352158.46 MB, QD=64) | RSS=14148.9 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=0.84 tps | Avg=0.85 tps | Hit=89.0% | NVMe=504.3 MB/s (420199.90 MB, QD=64) | RSS=14149.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=0.87 tps | Avg=0.85 tps | Hit=89.0% | NVMe=506.8 MB/s (487453.77 MB, QD=64) | RSS=14148.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=0.84 tps | Avg=0.85 tps | Hit=89.1% | NVMe=503.8 MB/s (553094.27 MB, QD=64) | RSS=14146.4 MB
[LIVE-DECODE] 2/64 tok | Avg=0.31 tps | Hit=89.1% (LA:+0.0%) | NVMe=504.0 MB/s (555435.59 MB) | RSS=14068.1 MB
[LIVE-DECODE] 4/64 tok | Avg=0.33 tps | Hit=89.1% (LA:+0.0%) | NVMe=504.2 MB/s (558342.09 MB) | RSS=13752.8 MB
[LIVE-DECODE] 6/64 tok | Avg=0.37 tps | Hit=89.1% (LA:+0.1%) | NVMe=504.4 MB/s (560724.90 MB) | RSS=13627.0 MB
[LIVE-DECODE] 8/64 tok | Avg=0.38 tps | Hit=89.1% (LA:+0.1%) | NVMe=504.7 MB/s (563057.71 MB) | RSS=13603.2 MB
[LIVE-DECODE] 10/64 tok | Avg=0.40 tps | Hit=89.1% (LA:+0.1%) | NVMe=504.9 MB/s (565194.34 MB) | RSS=13581.6 MB
[LIVE-DECODE] 12/64 tok | Avg=0.41 tps | Hit=89.1% (LA:+0.1%) | NVMe=505.0 MB/s (567325.40 MB) | RSS=13563.6 MB
[LIVE-DECODE] 14/64 tok | Avg=0.43 tps | Hit=89.1% (LA:+0.1%) | NVMe=505.2 MB/s (569408.21 MB) | RSS=13573.0 MB
[LIVE-DECODE] 16/64 tok | Avg=0.44 tps | Hit=89.1% (LA:+0.2%) | NVMe=505.4 MB/s (571521.90 MB) | RSS=13572.9 MB
[LIVE-DECODE] 18/64 tok | Avg=0.44 tps | Hit=89.1% (LA:+0.2%) | NVMe=505.7 MB/s (573760.02 MB) | RSS=13572.9 MB
[LIVE-DECODE] 20/64 tok | Avg=0.44 tps | Hit=89.1% (LA:+0.2%) | NVMe=505.9 MB/s (576033.15 MB) | RSS=13572.9 MB
[LIVE-DECODE] 22/64 tok | Avg=0.45 tps | Hit=89.1% (LA:+0.2%) | NVMe=506.1 MB/s (578168.15 MB) | RSS=13573.0 MB
[LIVE-DECODE] 24/64 tok | Avg=0.45 tps | Hit=89.0% (LA:+0.2%) | NVMe=506.1 MB/s (580418.59 MB) | RSS=13573.0 MB
[LIVE-DECODE] 26/64 tok | Avg=0.45 tps | Hit=89.0% (LA:+0.3%) | NVMe=506.3 MB/s (582587.71 MB) | RSS=13573.0 MB
[LIVE-DECODE] 28/64 tok | Avg=0.46 tps | Hit=89.0% (LA:+0.3%) | NVMe=506.6 MB/s (584531.46 MB) | RSS=13563.6 MB
[LIVE-DECODE] 30/64 tok | Avg=0.46 tps | Hit=89.0% (LA:+0.3%) | NVMe=506.8 MB/s (586689.90 MB) | RSS=13573.0 MB
[LIVE-DECODE] 32/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=507.0 MB/s (588683.46 MB) | RSS=13573.0 MB
[LIVE-DECODE] 34/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=507.2 MB/s (590735.27 MB) | RSS=13572.9 MB
[LIVE-DECODE] 36/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.3%) | NVMe=507.4 MB/s (592692.84 MB) | RSS=13582.3 MB
[LIVE-DECODE] 38/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.4%) | NVMe=507.6 MB/s (594684.15 MB) | RSS=13582.3 MB
[LIVE-DECODE] 40/64 tok | Avg=0.47 tps | Hit=89.0% (LA:+0.4%) | NVMe=507.7 MB/s (596786.09 MB) | RSS=13582.3 MB
[LIVE-DECODE] 42/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=507.8 MB/s (598794.84 MB) | RSS=13573.0 MB
[LIVE-DECODE] 44/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=508.0 MB/s (600881.96 MB) | RSS=13573.0 MB
[LIVE-DECODE] 46/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.4%) | NVMe=508.2 MB/s (603182.59 MB) | RSS=13582.3 MB
[LIVE-DECODE] 48/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.5%) | NVMe=508.4 MB/s (605175.59 MB) | RSS=13582.3 MB
[LIVE-DECODE] 50/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.5%) | NVMe=508.6 MB/s (607114.84 MB) | RSS=13582.4 MB
[LIVE-DECODE] 52/64 tok | Avg=0.48 tps | Hit=89.0% (LA:+0.5%) | NVMe=508.8 MB/s (609000.84 MB) | RSS=13582.4 MB
[LIVE-DECODE] 54/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=509.0 MB/s (610908.59 MB) | RSS=13582.3 MB
[LIVE-DECODE] 56/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=509.2 MB/s (612898.21 MB) | RSS=13573.0 MB
[LIVE-DECODE] 58/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=509.3 MB/s (614758.96 MB) | RSS=13582.3 MB
[LIVE-DECODE] 60/64 tok | Avg=0.49 tps | Hit=89.0% (LA:+0.5%) | NVMe=509.5 MB/s (616618.34 MB) | RSS=13582.4 MB
[LIVE-DECODE] 62/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.6%) | NVMe=509.7 MB/s (618538.02 MB) | RSS=13582.4 MB
[LIVE-DECODE] 64/64 tok | Avg=0.50 tps | Hit=89.0% (LA:+0.6%) | NVMe=509.8 MB/s (620405.90 MB) | RSS=13582.4 MB

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
   LRFU Cache / Staging Ring    : 5671.88 MB (605/12384 exp = 4.89% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.66 MB | End=13582.35 MB | Peak=14220.20 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : " high-throughput Mixtures of Mixtures-of-Expert (MoE) language inference with NVMe offloading achieving low token requires overlapping PCIe Gen3/ DMA compute attention recurrent state trunks. Window combining Window cache dual horiz lookahead co over prefetching activations RAM directly RAM pipeline. contexts inverted tables tokens expert coal LB Qsort"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=43.9% | AvgMargin=1.435 | MinMargin=0.013
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    1550 |  high          |   25.48 | 100.0% |     279 |   13.45 | 2408423.57 |  0 |  0 |  0 |     0.0 |
   |    2 |   42503 | -through       |   26.97 | 100.0% |   19705 |   16.32 | 3252.92 |137 |106 | 93 | 1198752.0 |
   |    3 |     628 | put            |   23.70 |  99.6% |   19183 |   17.62 | 3252.92 |  0 |  0 |  0 | 1198752.0 |
   |    4 |   19183 |  Mix           |   17.29 |  81.5% |   19705 |   14.69 | 2753.92 | 39 |211 | 86 | 1488128.0 |
   |    5 |   18482 | tures          |   16.23 |  44.3% |      68 |   15.40 | 2753.92 |  0 |  0 |  0 | 1488128.0 |
   |    6 |     315 |  of            |   13.96 |  18.4% |    8667 |   13.90 | 2211.47 |107 |155 | 74 | 1220000.0 |
   |    7 |   19183 |  Mix           |   18.62 |  90.8% |   57687 |   15.49 | 2211.47 |  0 |  0 |  0 | 1220000.0 |
   |    8 |   18482 | tures          |   16.60 |  61.9% |    4974 |   15.05 | 2181.73 |121 |141 | 74 | 1194400.0 |
   |   24 |    3347 |  low           |   16.80 |  51.9% |    9467 |   15.23 | 2325.00 |134 |137 | 65 | 1152224.0 |
   |   25 |    3950 |  token         |   15.83 |  23.5% |   97580 |   15.43 | 2325.00 |  0 |  0 |  0 | 1152224.0 |
   |   46 |   86025 |  lookahead     |   14.57 |  23.9% |    1062 |   14.34 | 2291.04 |126 |133 | 77 | 1177920.0 |
   |   47 |    1062 |  co            |   16.68 |  40.2% |    4389 |   16.21 | 2291.04 |  0 |  0 |  0 | 1177920.0 |
   |   62 |   11492 |  coal          |   16.12 |  32.1% |    1062 |   15.49 | 1763.04 |176 | 94 | 66 | 982880.0 |
   |   63 |   39929 |  LB            |   15.17 |  15.6% |    6203 |   14.88 | 1763.04 |  0 |  0 |  0 | 982880.0 |
   |   64 |    1207 |  Q             |   15.36 |  35.6% |   12149 |   13.79 | 1730.53 |181 |100 | 55 | 956352.0 |
   |   65 |    6860 | sort           |   14.90 |  19.9% |   46254 |   13.96 | 1730.53 |  0 |  0 |  0 | 956352.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2408.424s, TTFT=2408423.57ms): Avg=0.85 | Min=0.83 | Max=0.89 tps
   Prefill Chunks (8): C1:256t/0.9tps/89% | C2:256t/0.9tps/89% | C3:256t/0.8tps/89% | C4:256t/0.8tps/89%
                       C5:256t/0.8tps/89% | C6:256t/0.8tps/89% | C7:256t/0.9tps/89% | C8:256t/0.8tps/89%
   Decode  (64 tok, 128.646s): Avg=0.50 | Min=0.31 | Max=0.59 tps
   Latency (ms) : Min=1705.82 | P10=1763.04 | P25=1823.54 | P50=1950.95 | P75=2101.78 | P90=2291.04 | P95=2753.92 | P99=3252.92 | Max=3252.92
   Mean/SD/Jitt : Mean=2010.09ms | StdDev=309.48ms | Jitter=81.43ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (698880): RawRAM=617784 (88.40%) | Lookahead=4009 (+0.57%) | ColdMiss=77087 (11.03%) | EFF HIT=88.97%
   Lookahead    : 6866 prefetched -> 4009 consumed (58.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 89.1% | @64= 89.0% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |16640 |14185 | 232 |2223 | 86.6%|17645.31 | | L24 |16640 |14852 |  52 |1736 | 89.6%|13325.62 |
   | L04 |16640 |14258 | 106 |2276 | 86.3%|18004.69 | | L25 |16640 |14831 |  79 |1730 | 89.6%|13591.56 |
   | L05 |16640 |14220 | 161 |2259 | 86.4%|17918.44 | | L26 |16640 |14826 |  62 |1752 | 89.5%|13512.50 |
   | L06 |16640 |14249 | 177 |2214 | 86.7%|17630.94 | | L27 |16640 |14719 |  83 |1838 | 89.0%|14569.06 |
   | L07 |16640 |14528 | 138 |1974 | 88.1%|15618.44 | | L28 |16640 |14703 |  98 |1839 | 88.9%|14375.00 |
   | L08 |16640 |14511 |  92 |2037 | 87.8%|16071.25 | | L29 |16640 |14829 |  84 |1727 | 89.6%|13469.38 |
   | L09 |16640 |14510 | 109 |2021 | 87.9%|16013.75 | | L30 |16640 |14731 |  87 |1822 | 89.1%|13994.06 |
   | L10 |16640 |14364 | 133 |2143 | 87.1%|16926.56 | | L31 |16640 |14735 |  53 |1852 | 88.9%|14720.00 |
   | L11 |16640 |14703 | 128 |1809 | 89.1%|18862.50 | | L32 |16640 |14684 |  99 |1857 | 88.8%|14684.06 |
   | L12 |16640 |14748 | 108 |1784 | 89.3%|16440.12 | | L33 |16640 |14854 |  92 |1694 | 89.8%|13562.81 |
   | L13 |16640 |14925 |  76 |1639 | 90.2%|12729.06 | | L34 |16640 |14788 |  92 |1760 | 89.4%|13605.94 |
   | L14 |16640 |15018 |  78 |1544 | 90.7%|12305.00 | | L35 |16640 |14720 | 108 |1812 | 89.1%|14137.81 |
   | L15 |16640 |15114 |  81 |1445 | 91.3%|11413.75 | | L36 |16640 |14673 | 121 |1846 | 88.9%|14396.56 |
   | L16 |16640 |14943 |  85 |1612 | 90.3%|12664.38 | | L37 |16640 |14696 |  97 |1847 | 88.9%|14295.94 |
   | L17 |16640 |14804 |  56 |1780 | 89.3%|13692.19 | | L38 |16640 |14686 |  98 |1856 | 88.8%|14403.75 |
   | L18 |16640 |14931 |  47 |1662 | 90.0%|12980.62 | | L39 |16640 |14595 | 112 |1933 | 88.4%|15014.69 |
   | L19 |16640 |14889 |  61 |1690 | 89.8%|12908.75 | | L40 |16640 |14679 |  83 |1878 | 88.7%|14461.25 |
   | L20 |16640 |14856 |  55 |1729 | 89.6%|13340.00 | | L41 |16640 |14655 | 101 |1884 | 88.7%|14827.81 |
   | L21 |16640 |14928 |  61 |1651 | 90.1%|12671.56 | | L42 |16640 |14744 |  97 |1799 | 89.2%|13915.00 |
   | L22 |16640 |14900 |  61 |1679 | 89.9%|12930.31 | | L43 |16640 |14758 | 106 |1776 | 89.3%|13907.81 |
   | L23 |16640 |14819 |  63 |1758 | 89.4%|13469.38 | | L44 |16640 |14623 |  97 |1920 | 88.5%|17637.75 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 620405.90 MB (Load=6361.84 | Prefill=546732.44 | Warmup=0.00 | Decode=67311.62 MB)
   SSD Data/Token (Decode)      : Avg=1051.744 MB/tok (Min=929.688 | P50=1043.562 | P95=1191.406 | Max=1453.250 MB) | Prefill=266.959 MB/tok
   NVMe Batches / Requests      : 3855 Batches | 253625 Raw -> 250450 Merged (3175 LBA Merges, Avg 2536.6 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=249571
   SSD Read Bandwidth (Active)  : Min=7.07 | Avg=509.84 | Peak=3972.52 MB/s | WallAmort=244.54 MB/s
   OS Kernel I/O Verification   : Read=620414.93 MB | Write=0.01 MB | Syscalls=254509
   Sync Stall vs Async DMA      : SyncStall=1114270.31 ms | AsyncOverlapped=1204378.95 ms (51.9% Overlapped)
   RAM Traffic & Active BW      : 7358.13 GB moved | Active=5.47 GB/s | WallAmort=2.90 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2408.42s (94.9%, 546732.44 MB SSD) | Decode=128.65s (5.1%, 67311.62 MB SSD)
   CPU Time & Utilization       : User=4703.969s + Sys=46.500s (Wall=2555.421s) | SysUtil=46.5% | ThrUtil=46.5% | 42.99 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 661999.32 ms (313446.6 us/tok | 26.09%)
   MoE AVX2 Q8 Expert Compute   : 680868.83 ms (322381.1 us/tok | 26.84%)
   Router + Lookahead Dispatch  :  10714.60 ms ( 5073.2 us/tok |  0.42%)
   LM Head Output Projection    :   1312.17 ms (  621.3 us/tok |  0.05%)
   Foreground NVMe Sync Stall   : 1114270.31 ms (527590.1 us/tok | 43.92%)
   Unaccounted / OMP & Sampling :  67904.15 ms (32151.6 us/tok |  2.68%) | Total Wall=2537069.38 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    68.42%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     7.67%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    14.04%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.10%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.77%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_glm53_colibri_bench.log`
```text
=== [Colibri-GLM53] CMD: ./baselines/colibri/c/glm53.exe --model D:/apex_d_drive/models/glm53 --ids 1,8,15,22,29,36,43,50,57,64,71,78,85,92,99,106,113,120,127,134,141,148,155,162,169,176,183,190,197,204,211,218,225,232,239,246,253,260,267,274,281,288,295,302,309,316,323,330,337,344,351,358,365,372,379,386,393,400,407,414,421,428,435,442 --greedy 64 32 (5x cutoff=975.0s) ===
[gguf] D:\apex_d_drive\models\glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: glm5-next, 4 part(s), 38435 tensors under the checkpoint's names (1283 renamed, 129 fused expert tensors split per expert, 0 kept as named), read in place
glm53: GGUF experts interleaved by 16 rows on 3 of 42 layers (G53_ILV16=0: the file's rows)
  [COMP-LIVE] Colibri-GLM53: elapsed=15.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=30.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=45.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=60.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=75.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=92.9s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=108.4s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=123.9s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=139.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=154.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=169.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=184.1s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=199.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=214.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=229.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=244.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=259.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=274.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=289.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=304.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=319.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=334.3s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=349.3s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=364.8s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=379.8s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=395.2s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=410.4s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=425.5s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=440.6s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=455.8s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=471.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=486.3s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=501.5s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=516.5s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=531.6s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=546.6s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=561.7s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=577.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=592.0s / cutoff=975.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=607.2s / cutoff=975.0s
[STATS] 43008 selections across 6945 distinct experts -> D:/apex_d_drive/models/glm53/.coli_usage
teacher_forcing 5556 335 11 15 15 22 22 22 22 36 57 22 36 64 9 154850 154850 154850 123 121 127967 127501 243 104 253 237 154842 1986 197 220 220 0 220 154827 154827 154827 154827 220 83 220 274 220 220 274 295 83 279 8 220 1 1 2776 72 83 84 365 13 220 220 220 320 83 220 220
greedy 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330
decode 64 token in 498.8s = 0.128 tok/s (7.8 s/token)
experts hits 15425 miss 11249 bytes 111319384064
  [COMP-LIVE] Colibri-GLM53: elapsed=622.5s / cutoff=975.0s
=== [Colibri-GLM53] Finished rc=0 elapsed=622.99s cancelled=False ===
```

### 📄 `12_glm53_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] GLM53 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 0.53 | 0.56 | 1618.16 | 75.35% | 544.65 | 13810.34 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 0.88 | 0.55 | 1749.61 | 88.06% | 542.53 | 14194.16 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 0.85 | 0.50 | 1950.95 | 88.97% | 509.84 | 14220.20 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.128 | - | 57.8% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
