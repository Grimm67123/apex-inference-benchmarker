<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#27 (Run ID `43567912496`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43567912496)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-14 07:10:23 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T06:45:51.420Z] ================================================================================
[2026-11-14T06:45:51.432Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T06:45:51.433Z] ================================================================================
[2026-11-14T06:45:55.263Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T06:45:55.425Z] --------------------------------------------------------------------------------
[2026-11-14T06:45:55.426Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.1 GB / 149.89 GB
[2026-11-14T06:45:55.427Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-14T06:45:55.427Z]  [Disk Telemetry] Total Combined Usable Free Space: 247.97 GB
[2026-11-14T06:45:55.438Z] --------------------------------------------------------------------------------
[2026-11-14T06:45:55.439Z]  [OK] Disk space verification passed: 247.97 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 892K Nov 14 06:46 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 892K Nov 14 06:46 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.44 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    553.79 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2117.89 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9731.40 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  12451.12 MB/s
   RND4K Q32T16 Read                  :   1043.45 MB/s (  267122 IOPS)
   RND4K Q1T1  Read                   :   1134.49 MB/s (Latency: 3.44 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     97.32 GB/s
   AVX2 256-bit Sequential Write BW   :     97.37 GB/s
   STREAM Triad (A = B + s*C) BW      :     42.37 GB/s
   Random Pointer-Chase Latency       :     34.70 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     71.85 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    278.06 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     39.84 GB/s (FP32 Equiv)
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
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=3.24 MB (67 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2602.81 tps | Avg=2602.81 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=73.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2291.01 tps | Avg=2436.98 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=73.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1999.40 tps | Avg=2271.28 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=74.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1757.21 tps | Avg=2116.49 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=74.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1580.35 tps | Avg=1982.01 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=74.7 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1396.28 tps | Avg=1852.49 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=75.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1272.13 tps | Avg=1739.14 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=75.2 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1197.58 tps | Avg=1646.09 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=75.5 MB
[LIVE-DECODE] 8/32 tok | Avg=347.21 tps | Hit=100.0% (LA:+0.0%) | NVMe=3486.8 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 16/32 tok | Avg=347.53 tps | Hit=100.0% (LA:+0.0%) | NVMe=3486.8 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 24/32 tok | Avg=346.78 tps | Hit=100.0% (LA:+0.0%) | NVMe=3486.8 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 32/32 tok | Avg=344.87 tps | Hit=100.0% (LA:+0.0%) | NVMe=3486.8 MB/s (6.58 MB) | RSS=75.5 MB

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
   LRFU Cache / Staging Ring    : 3.24 MB (67/64 exp = 104.69% pinned) | Staging=3.09 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=75.51 MB | Peak=75.51 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1244.16 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    2.89 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    2.89 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    2.83 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    2.83 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    2.89 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    2.89 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    2.91 | 12 |  0 |  0 |     0.0 |
   |   26 |     246 | tok_246        |  195.41 | 100.0% |      54 |  174.46 |    2.98 | 12 |  0 |  0 |     0.0 |
   |   27 |     229 | tok_229        |  171.70 | 100.0% |      70 |  154.45 |    2.98 |  0 |  0 |  0 |     0.0 |
   |   28 |     246 | tok_246        |  194.87 | 100.0% |      54 |  173.43 |    2.93 | 12 |  0 |  0 |     0.0 |
   |   29 |     229 | tok_229        |  172.54 | 100.0% |      70 |  154.16 |    2.93 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    2.92 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    2.92 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    2.95 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    2.95 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.244s, TTFT=1244.16ms): Avg=1646.09 | Min=1197.58 | Max=2602.81 tps
   Prefill Chunks (8): C1:256t/2602.8tps/100% | C2:256t/2291.0tps/100% | C3:256t/1999.4tps/100% | C4:256t/1757.2tps/100%
                       C5:256t/1580.3tps/100% | C6:256t/1396.3tps/100% | C7:256t/1272.1tps/100% | C8:256t/1197.6tps/100%
   Decode  (32 tok, 0.093s): Avg=344.87 | Min=335.26 | Max=353.27 tps
   Latency (ms) : Min=2.83 | P10=2.85 | P25=2.88 | P50=2.90 | P75=2.93 | P90=2.95 | P95=2.98 | P99=2.98 | Max=2.98
   Mean/SD/Jitt : Mean=2.90ms | StdDev=0.04ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (24768): RawRAM=24768 (100.00%) | Lookahead=0 (+0.00%) | ColdMiss=0 (0.00%) | EFF HIT=100.00%
   Lookahead    : 0 prefetched -> 0 consumed (0.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16=100.0% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L01 | 8256 | 8256 |   0 |   0 |100.0%|   0.00 | | L03 | 8256 | 8256 |   0 |   0 |100.0%|   0.00 |
   | L02 | 8256 | 8256 |   0 |   0 |100.0%|   0.00 | |     |      |      |     |     |      |        |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 6.58 MB (Load=6.58 | Prefill=0.00 | Warmup=0.00 | Decode=0.00 MB)
   SSD Data/Token (Decode)      : Avg=0.000 MB/tok (Min=0.000 | P50=0.000 | P95=0.000 | Max=0.000 MB) | Prefill=0.000 MB/tok
   NVMe Batches / Requests      : 1 Batches | 331 Raw -> 143 Merged (188 LBA Merges, Avg 47.1 KB/io)
   SSD I/O Size Histogram       : <64K=107 | 64K-512K=32 | 512K-2M=4 | >2M=0
   SSD Read Bandwidth (Active)  : Min=405.88 | Avg=3486.77 | Peak=7267.44 MB/s | WallAmort=4.92 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=0.97 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=1.13 GB/s | WallAmort=1.07 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.24s (93.1%, 0.00 MB SSD) | Decode=0.09s (6.9%, 0.00 MB SSD)
   CPU Time & Utilization       : User=1.406s + Sys=0.562s (Wall=1.350s) | SysUtil=36.5% | ThrUtil=36.5% | 33.73 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1137.25 ms (  546.8 us/tok | 85.06%)
   MoE AVX2 Q8 Expert Compute   :    130.03 ms (   62.5 us/tok |  9.73%)
   Router + Lookahead Dispatch  :     33.07 ms (   15.9 us/tok |  2.47%)
   LM Head Output Projection    :      3.54 ms (    1.7 us/tok |  0.26%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     33.05 ms (   15.9 us/tok |  2.47%) | Total Wall=1336.94 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    20.11%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.99%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.12%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    74.43%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.35%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3725.79 tps | Avg=3725.79 tps | Hit=99.2% | NVMe=4061.0 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=3500.09 tps | Avg=3609.41 tps | Hit=99.2% | NVMe=5713.5 MB/s (42.92 MB, QD=64) | RSS=89.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=3116.61 tps | Avg=3428.70 tps | Hit=99.2% | NVMe=6794.6 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=3101.59 tps | Avg=3340.62 tps | Hit=99.2% | NVMe=7384.0 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2870.93 tps | Avg=3234.78 tps | Hit=99.2% | NVMe=8021.8 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2661.30 tps | Avg=3122.63 tps | Hit=99.2% | NVMe=8574.6 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2455.31 tps | Avg=3005.92 tps | Hit=99.2% | NVMe=9023.0 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2194.22 tps | Avg=2873.07 tps | Hit=99.2% | NVMe=9411.3 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=317.17 tps | Hit=99.2% (LA:+0.0%) | NVMe=9270.2 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=318.77 tps | Hit=99.2% (LA:+0.1%) | NVMe=9195.6 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=320.65 tps | Hit=99.2% (LA:+0.1%) | NVMe=9074.8 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=323.62 tps | Hit=99.2% (LA:+0.1%) | NVMe=8973.0 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=91.71 MB | Peak=91.71 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 |  712.83 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    3.17 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    3.17 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    3.15 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    3.15 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    3.15 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    3.15 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    3.15 | 16 |  0 |  0 |    32.0 |
   |    9 |      49 | qtok_49        |   84.72 | 100.0% |     129 |   76.64 |    3.15 |  0 |  0 |  0 |    32.0 |
   |   12 |     254 | qtok_254       |   71.34 |  95.3% |      66 |   68.21 |    3.13 | 16 |  0 |  0 |    32.0 |
   |   13 |     129 | qtok_129       |   76.30 |  99.3% |      49 |   71.12 |    3.13 |  0 |  0 |  0 |    32.0 |
   |   10 |     254 | qtok_254       |   70.81 |  99.7% |      66 |   64.77 |    3.13 | 15 |  1 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    2.98 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    2.98 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    2.98 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    2.98 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 0.713s, TTFT=712.83ms): Avg=2873.07 | Min=2194.22 | Max=3725.79 tps
   Prefill Chunks (8): C1:256t/3725.8tps/99% | C2:256t/3500.1tps/99% | C3:256t/3116.6tps/99% | C4:256t/3101.6tps/99%
                       C5:256t/2870.9tps/99% | C6:256t/2661.3tps/99% | C7:256t/2455.3tps/99% | C8:256t/2194.2tps/99%
   Decode  (32 tok, 0.099s): Avg=323.62 | Min=315.78 | Max=335.07 tps
   Latency (ms) : Min=2.98 | P10=2.98 | P25=3.04 | P50=3.11 | P75=3.15 | P90=3.15 | P95=3.17 | P99=3.17 | Max=3.17
   Mean/SD/Jitt : Mean=3.09ms | StdDev=0.06ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=494.97 | Avg=8972.99 | Peak=19438.24 MB/s | WallAmort=191.13 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=3.43 ms | AsyncOverlapped=16.29 ms (82.6% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=2.98 GB/s | WallAmort=2.59 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=0.71s (87.8%, 144.44 MB SSD) | Decode=0.10s (12.2%, 3.83 MB SSD)
   CPU Time & Utilization       : User=1.297s + Sys=0.328s (Wall=0.832s) | SysUtil=48.8% | ThrUtil=48.8% | 45.16 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    504.67 ms (  242.6 us/tok | 62.17%)
   MoE AVX2 Q8 Expert Compute   :    197.79 ms (   95.1 us/tok | 24.37%)
   Router + Lookahead Dispatch  :     43.77 ms (   21.0 us/tok |  5.39%)
   LM Head Output Projection    :      3.22 ms (    1.5 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :      3.43 ms (    1.6 us/tok |  0.42%)
   Unaccounted / OMP & Sampling :     58.83 ms (   28.3 us/tok |  7.25%) | Total Wall=811.71 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    18.49%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.67%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.94%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    66.03%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     7.87%  |
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
  "expert_cache_ram_bytes": 2534400,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 126.6,
    "avg_tps": 1295.43,
    "min_tps": 1041.61,
    "max_tps": 1475.37
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 263.33,
    "min_tps": 243.6,
    "max_tps": 288.92,
    "p50_ms": 3.8,
    "p90_ms": 4.04,
    "p99_ms": 4.11,
    "mean_ms": 3.8,
    "jitter_ms": 0.08
  },
  "cache": {
    "raw_hit_rate_pct": 100.0,
    "effective_hit_rate_pct": 100.0,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 5470784,
    "prefill_bytes": 0,
    "warmup_bytes": 0,
    "decode_bytes": 0,
    "bytes_per_token": 26949.67,
    "avg_mbs": 2942.5,
    "peak_mbs": 6281.41,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.78
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
    "dense_attention": 206.09,
    "moe_compute": 56.72,
    "router_lookahead": 3.81,
    "lm_head": 4.96,
    "unaccounted": 3.12
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.38,
    "ram_bandwidth_pinning": 3.35,
    "expert_cache_lrfu": 12.31,
    "lookahead_parallel_overlap": 1.41,
    "ssd_nvme_throughput": 0.55,
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
    "ttft_ms": 168.38,
    "avg_tps": 974.01,
    "min_tps": 684.7,
    "max_tps": 1125.23
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 229.71,
    "min_tps": 214.62,
    "max_tps": 242.7,
    "p50_ms": 4.29,
    "p90_ms": 4.61,
    "p99_ms": 4.66,
    "mean_ms": 4.35,
    "jitter_ms": 0.07
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
    "avg_mbs": 4634.85,
    "peak_mbs": 16119.46,
    "sync_wait_ms": 2.69,
    "async_overlap_ms": 7.01
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
    "dense_attention": 190.26,
    "moe_compute": 112.22,
    "router_lookahead": 4.8,
    "lm_head": 4.99,
    "unaccounted": 23.19
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 80.5,
    "ram_bandwidth_pinning": 3.84,
    "expert_cache_lrfu": 8.5,
    "lookahead_parallel_overlap": 4.42,
    "ssd_nvme_throughput": 2.74,
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
   System Memory (RAM): 15.99 GB Total / 13.44 GB Available
   Active Drive Space : 219.98 GB Total / 219.81 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    555.54 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2122.39 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9542.77 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  12409.89 MB/s
   RND4K Q32T16 Read                  :   1147.15 MB/s (  293671 IOPS)
   RND4K Q1T1  Read                   :   1158.41 MB/s (Latency: 3.37 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     94.07 GB/s
   AVX2 256-bit Sequential Write BW   :     96.03 GB/s
   STREAM Triad (A = B + s*C) BW      :     55.41 GB/s
   Random Pointer-Chase Latency       :     33.51 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     70.18 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    273.45 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     39.66 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 28.11 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 108.84 MB/s (9.41s)
   Window #01 ( 60.0 MB in 0.50s):   119.85 MB/s (Uncached Direct Read)
   Window #02 ( 60.0 MB in 0.51s):   117.33 MB/s (Uncached Direct Read)
   Window #03 ( 64.0 MB in 0.53s):   120.08 MB/s (Uncached Direct Read)
   Window #04 ( 60.0 MB in 0.50s):   119.78 MB/s (Uncached Direct Read)
   Window #05 ( 64.0 MB in 0.53s):   121.22 MB/s (Uncached Direct Read)
   Window #06 ( 60.0 MB in 0.50s):   119.87 MB/s (Uncached Direct Read)
   Window #07 ( 64.0 MB in 0.53s):   120.94 MB/s (Uncached Direct Read)
   Window #08 ( 64.0 MB in 0.53s):   120.51 MB/s (Uncached Direct Read)
   Window #09 ( 60.0 MB in 0.50s):   119.20 MB/s (Uncached Direct Read)
   Window #10 ( 60.0 MB in 0.50s):   119.67 MB/s (Uncached Direct Read)
   Window #11 ( 64.0 MB in 0.53s):   121.26 MB/s (Uncached Direct Read)
   Window #12 ( 64.0 MB in 0.55s):   116.36 MB/s (Uncached Direct Read)
   Window #13 ( 64.0 MB in 0.53s):   121.26 MB/s (Uncached Direct Read)
   Window #14 ( 60.0 MB in 0.50s):   119.81 MB/s (Uncached Direct Read)
   Window #15 ( 60.0 MB in 0.50s):   119.80 MB/s (Uncached Direct Read)
   Window #16 ( 60.0 MB in 0.50s):   119.78 MB/s (Uncached Direct Read)
   Window #17 ( 36.0 MB in 0.32s):   111.70 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   119.49 MB/s (Min=111.70 | Max=121.26 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 219.81 GB / 219.98 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 268.98 MB/s (3.81s)
   Window #01 (272.0 MB in 0.51s):   537.26 MB/s (Uncached Direct Read)
   Window #02 (272.0 MB in 0.51s):   536.40 MB/s (Uncached Direct Read)
   Window #03 (272.0 MB in 0.51s):   536.38 MB/s (Uncached Direct Read)
   Window #04 (208.0 MB in 0.39s):   536.38 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   536.61 MB/s (Min=536.38 | Max=537.26 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: qwen38 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (0.010 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 100.00% (0.01/0.01 GB) @ 17.3 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (43.792 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  11.42% (5.00/43.79 GB) @ 159.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  22.84% (10.00/43.79 GB) @ 151.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  34.25% (15.00/43.79 GB) @ 160.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  45.67% (20.00/43.79 GB) @ 159.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  57.09% (25.00/43.79 GB) @ 159.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  68.51% (30.00/43.79 GB) @ 141.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  79.92% (35.00/43.79 GB) @ 132.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  91.34% (40.00/43.79 GB) @ 135.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf: 100.00% (43.79/43.79 GB) @ 138.9 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (26.822 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  18.64% (5.00/26.82 GB) @ 141.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  37.28% (10.00/26.82 GB) @ 125.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  55.92% (15.00/26.82 GB) @ 123.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  74.57% (20.00/26.82 GB) @ 128.0 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  93.21% (25.00/26.82 GB) @ 125.2 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf: 100.00% (26.82/26.82 GB) @ 119.8 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/MTP/mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (2.595 GB) -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Sequential Non-Truncate)
  [DL] mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 100.00% (2.60/2.60 GB) @ 86.7 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=78,618,661,594 (73.22 GB) | Elapsed=584.47s
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
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6433.11 MB (3100 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=3.09 tps | Avg=3.09 tps | Hit=88.1% | NVMe=544.2 MB/s (10578.12 MB, QD=64) | RSS=12322.8 MB
[LIVE-DECODE] 8/32 tok | Avg=2.12 tps | Hit=89.2% (LA:+1.0%) | NVMe=571.1 MB/s (12431.96 MB) | RSS=12325.5 MB
[LIVE-DECODE] 16/32 tok | Avg=2.41 tps | Hit=90.2% (LA:+1.7%) | NVMe=609.7 MB/s (14020.65 MB) | RSS=12325.5 MB
[LIVE-DECODE] 24/32 tok | Avg=2.63 tps | Hit=91.1% (LA:+1.9%) | NVMe=644.9 MB/s (15251.66 MB) | RSS=12325.5 MB
[LIVE-DECODE] 31/32 tok | Avg=2.74 tps | Hit=91.8% (LA:+1.9%) | NVMe=673.0 MB/s (16271.47 MB) | RSS=12325.5 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=OFF
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 6433.11 MB (3100/25088 exp = 12.36% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=12325.49 MB | Peak=12786.50 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (31 tok) : " a2,
ar,
ing,
e212
2

22
220
222
01
"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 32 Steps)]
   Logit Summary: AvgTop1Prob=10.0% | AvgMargin=0.730 | MinMargin=0.032
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.79 |  18.1% |     303 |   13.43 | 20733.09 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    9.55 |   2.3% |     467 |    8.54 |  682.98 |849 | 84 | 27 | 273239.0 |
   |    3 |      11 | ,              |   13.78 |  50.0% |     198 |   12.15 |  682.98 |  0 |  0 |  0 | 273239.0 |
   |    4 |     198 | \n             |   11.28 |  20.5% |     364 |    8.50 |  426.13 |419 | 51 | 10 | 241639.0 |
   |    5 |     277 | ar             |    9.86 |   2.9% |     261 |    9.53 |  460.22 |396 | 76 |  8 | 258139.0 |
   |    6 |      11 | ,              |    9.33 |   3.0% |      16 |    9.11 |  440.89 |423 | 44 | 13 | 259464.0 |
   |    7 |     198 | \n             |    9.90 |   8.3% |     286 |    7.83 |  407.90 |434 | 40 |  6 | 251814.0 |
   |    8 |     286 | ing            |    9.16 |   2.7% |     278 |    8.60 |  343.04 |447 | 30 |  3 | 162689.0 |
   |   14 |      17 | 2              |    9.40 |   4.0% |      15 |    8.88 |  455.93 |406 | 58 | 16 | 269139.0 |
   |   12 |      17 | 2              |    7.65 |   0.5% |     365 |    6.83 |  403.52 |432 | 43 |  5 | 231639.0 |
   |   25 |     198 | \n             |   10.81 |  12.2% |      15 |   10.44 |  382.48 |421 | 52 |  7 | 247689.0 |
   |   15 |     198 | \n             |   11.71 |  23.3% |      17 |   11.53 |  369.44 |428 | 46 |  6 | 214293.0 |
   |   29 |     198 | \n             |   11.56 |  29.2% |     271 |    9.34 |  298.57 |471 |  9 |  0 | 131518.0 |
   |   30 |      15 | 0              |    9.43 |   3.3% |      17 |    9.40 |  303.39 |471 |  9 |  0 | 141639.0 |
   |   31 |      16 | 1              |    9.74 |   4.3% |      17 |    9.38 |  321.82 |457 | 22 |  1 | 169964.0 |
   |   32 |     198 | \n             |   11.79 |  32.8% |      17 |    9.29 |  318.71 |456 | 24 |  0 | 179714.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 20.733s, TTFT=20733.09ms): Avg=3.09 | Min=3.09 | Max=3.09 tps
   Prefill Chunks (1): C1:64t/3.1tps/88%
   Decode  (31 tok, 11.304s): Avg=2.74 | Min=1.46 | Max=3.41 tps
   Latency (ms) : Min=292.83 | P10=302.33 | P25=304.36 | P50=323.62 | P75=403.52 | P90=455.93 | P95=682.98 | P99=682.98 | Max=682.98
   Mean/SD/Jitt : Mean=364.65ms | StdDev=97.14ms | Jitter=35.13ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/31
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (45600): RawRAM=40956 (89.82%) | Lookahead=885 (+1.94%) | ColdMiss=3759 (8.24%) | EFF HIT=91.76%
   Lookahead    : 3342 prefetched -> 895 consumed (26.8% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  950 |  653 |  83 | 214 | 77.5%| 500.32 | | L24 |  950 |  892 |   9 |  49 | 94.8%| 142.87 |
   | L01 |  950 |  806 |  50 |  94 | 90.1%| 424.58 | | L25 |  950 |  890 |   8 |  52 | 94.5%| 114.67 |
   | L02 |  950 |  829 |  15 | 106 | 88.8%| 459.89 | | L26 |  950 |  864 |  19 |  67 | 92.9%| 204.91 |
   | L03 |  950 |  892 |   1 |  57 | 94.0%| 554.57 | | L27 |  950 |  865 |  20 |  65 | 93.2%| 231.23 |
   | L04 |  950 |  886 |   4 |  60 | 93.7%| 215.82 | | L28 |  950 |  827 |  39 |  84 | 91.2%| 353.42 |
   | L05 |  950 |  864 |   7 |  79 | 91.7%| 291.38 | | L29 |  950 |  855 |  15 |  80 | 91.6%| 174.29 |
   | L06 |  950 |  866 |  17 |  67 | 92.9%| 238.75 | | L30 |  950 |  815 |  33 | 102 | 89.3%| 241.99 |
   | L07 |  950 |  869 |  19 |  62 | 93.5%| 154.98 | | L31 |  950 |  822 |  26 | 102 | 89.3%| 239.11 |
   | L08 |  950 |  902 |   8 |  40 | 95.8%| 103.34 | | L32 |  950 |  845 |  19 |  86 | 90.9%| 293.26 |
   | L09 |  950 |  892 |   5 |  53 | 94.4%| 100.85 | | L33 |  950 |  838 |  28 |  84 | 91.2%| 200.22 |
   | L10 |  950 |  882 |  12 |  56 | 94.1%| 123.27 | | L34 |  950 |  846 |  18 |  86 | 90.9%| 195.90 |
   | L11 |  950 |  895 |   5 |  50 | 94.7%| 128.25 | | L35 |  950 |  865 |  15 |  70 | 92.6%| 139.72 |
   | L12 |  950 |  868 |  15 |  67 | 92.9%| 248.14 | | L36 |  950 |  846 |  18 |  86 | 90.9%| 326.98 |
   | L13 |  950 |  858 |  19 |  73 | 92.3%| 157.01 | | L37 |  950 |  870 |  13 |  67 | 92.9%| 180.47 |
   | L14 |  950 |  837 |  31 |  82 | 91.4%| 275.12 | | L38 |  950 |  873 |   8 |  69 | 92.7%| 246.26 |
   | L15 |  950 |  847 |  19 |  84 | 91.2%| 289.50 | | L39 |  950 |  863 |  13 |  74 | 92.2%| 319.58 |
   | L16 |  950 |  866 |  11 |  73 | 92.3%| 193.63 | | L40 |  950 |  844 |  16 |  90 | 90.5%| 289.50 |
   | L17 |  950 |  866 |  15 |  69 | 92.7%| 218.07 | | L41 |  950 |  848 |  13 |  89 | 90.6%| 161.33 |
   | L18 |  950 |  858 |  22 |  70 | 92.6%| 223.71 | | L42 |  950 |  823 |  17 | 110 | 88.4%| 290.97 |
   | L19 |  950 |  874 |   8 |  68 | 92.8%| 154.13 | | L43 |  950 |  857 |  15 |  78 | 91.8%| 205.98 |
   | L20 |  950 |  832 |  27 |  91 | 90.4%| 221.83 | | L44 |  950 |  845 |  16 |  89 | 90.6%| 181.49 |
   | L21 |  950 |  823 |  31 |  96 | 89.9%| 421.09 | | L45 |  950 |  821 |  33 |  96 | 89.9%| 278.00 |
   | L22 |  950 |  883 |  12 |  55 | 94.2%| 214.31 | | L46 |  950 |  877 |   7 |  66 | 93.1%| 250.63 |
   | L23 |  950 |  870 |  15 |  65 | 93.2%| 145.48 | | L47 |  950 |  847 |  16 |  87 | 90.8%| 280.10 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 16271.47 MB (Load=4614.69 | Prefill=5963.42 | Warmup=0.00 | Decode=5693.35 MB)
   SSD Data/Token (Decode)      : Avg=183.657 MB/tok (Min=122.743 | P50=172.328 | P95=262.831 | Max=266.835 MB) | Prefill=93.178 MB/tok
   NVMe Batches / Requests      : 1617 Batches | 23931 Raw -> 23147 Merged (784 LBA Merges, Avg 719.8 KB/io)
   SSD I/O Size Histogram       : <64K=1835 | 64K-512K=5771 | 512K-2M=15107 | >2M=434
   SSD Read Bandwidth (Active)  : Min=10.44 | Avg=673.02 | Peak=11196.44 MB/s | WallAmort=507.89 MB/s
   OS Kernel I/O Verification   : Read=16291.44 MB | Write=0.00 MB | Syscalls=32649
   Sync Stall vs Async DMA      : SyncStall=10852.38 ms | AsyncOverlapped=15385.32 ms (58.6% Overlapped)
   RAM Traffic & Active BW      : 392.99 GB moved | Active=21.03 GB/s | WallAmort=12.27 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=20.73s (64.7%, 5963.42 MB SSD) | Decode=11.30s (35.3%, 5693.35 MB SSD)
   CPU Time & Utilization       : User=58.656s + Sys=5.203s (Wall=44.501s) | SysUtil=35.9% | ThrUtil=35.9% | 33.18 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   9195.70 ms (96796.8 us/tok | 28.70%)
   MoE AVX2 Q8 Expert Compute   :   8881.95 ms (93494.3 us/tok | 27.72%)
   Router + Lookahead Dispatch  :    504.08 ms ( 5306.1 us/tok |  1.57%)
   LM Head Output Projection    :    609.99 ms ( 6420.9 us/tok |  1.90%)
   Foreground NVMe Sync Stall   :  10852.38 ms (114235.6 us/tok | 33.87%)
   Unaccounted / OMP & Sampling :   1992.99 ms (20978.9 us/tok |  6.22%) | Total Wall=32037.09 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    77.52%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.72%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     8.96%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.78%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.02%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 46s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V45 96-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=YES | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 14.65 GB Available
   Active Drive Space : 219.98 GB Total / 149.17 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    548.11 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2123.16 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8998.94 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11401.04 MB/s
   RND4K Q32T16 Read                  :    832.67 MB/s (  213165 IOPS)
   RND4K Q1T1  Read                   :   1028.12 MB/s (Latency: 3.80 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     93.59 GB/s
   AVX2 256-bit Sequential Write BW   :     94.87 GB/s
   STREAM Triad (A = B + s*C) BW      :     55.98 GB/s
   Random Pointer-Chase Latency       :     28.02 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     72.12 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    278.00 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     38.11 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=3.39 tps | Avg=3.39 tps | Hit=90.0% | NVMe=548.8 MB/s (11789.75 MB, QD=64) | RSS=13595.6 MB

 >>> [Apex-Model-Response] b
0
222719
12
22
21
11122922227321222292271227227123122220212122
================================================================================

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=OFF
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7694.82 MB (3708/25088 exp = 14.78% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.82 MB | End=13536.30 MB | Peak=14053.68 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (63 tok) : "b
0
222719
12
22
21
11122922227321222292271227227123122220212122"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=14.3% | AvgMargin=0.497 | MinMargin=0.027
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      65 | b              |    9.34 |   1.9% |      79 |    9.00 | 26870.69 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |   10.69 |  14.6% |     271 |    7.46 |  566.01 |904 | 51 |  5 | 158753.5 |
   |    3 |      15 | 0              |    9.12 |   1.0% |      79 |    8.96 |  566.01 |  0 |  0 |  0 | 158753.5 |
   |    4 |     198 | \n             |   11.23 |  26.1% |      65 |    7.68 |  378.35 |445 | 33 |  2 | 167539.0 |
   |    5 |      17 | 2              |    7.61 |   0.8% |      15 |    7.44 |  294.56 |472 |  8 |  0 | 91018.0 |
   |    6 |      17 | 2              |    9.33 |   3.4% |      16 |    8.85 |  340.19 |451 | 27 |  2 | 151914.0 |
   |    7 |      17 | 2              |   10.09 |   7.7% |      24 |   10.02 |  354.11 |442 | 38 |  0 | 177918.0 |
   |    8 |      22 | 7              |   11.04 |   9.6% |      17 |   10.99 |  309.54 |451 | 26 |  3 | 135743.0 |
   |   10 |      24 | 9              |   10.61 |   9.0% |      17 |   10.51 |  338.87 |451 | 27 |  2 | 158839.0 |
   |   59 |      17 | 2              |   12.29 |  13.6% |      15 |   12.07 |  332.64 |453 | 23 |  4 | 155989.0 |
   |   11 |     198 | \n             |   11.25 |  22.6% |      16 |   10.26 |  328.26 |449 | 31 |  0 | 172739.0 |
   |   14 |     198 | \n             |   12.07 |  31.1% |      17 |   10.31 |  314.11 |470 | 10 |  0 | 113389.0 |
   |   61 |      17 | 2              |   11.98 |  21.6% |      18 |   11.12 |  288.27 |478 |  2 |  0 | 117789.0 |
   |   62 |      16 | 1              |   12.20 |  17.7% |      17 |   12.06 |  298.69 |476 |  4 |  0 | 119168.0 |
   |   63 |      17 | 2              |   13.90 |  25.0% |      18 |   13.58 |  285.91 |479 |  1 |  0 | 95168.0 |
   |   64 |      17 | 2              |   12.55 |  17.2% |      16 |   12.28 |  294.00 |475 |  5 |  0 | 79443.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 26.871s, TTFT=26870.69ms): Avg=3.39 | Min=3.39 | Max=3.39 tps
   Prefill Chunks (1): C1:91t/3.4tps/90%
   Decode  (63 tok, 19.525s): Avg=3.23 | Min=1.77 | Max=3.54 tps
   Latency (ms) : Min=282.67 | P10=289.09 | P25=292.33 | P50=295.38 | P75=306.78 | P90=332.64 | P95=354.11 | P99=566.01 | Max=566.01
   Mean/SD/Jitt : Mean=309.92ms | StdDev=49.30ms | Jitter=14.95ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (73920): RawRAM=68907 (93.22%) | Lookahead=622 (+0.84%) | ColdMiss=4391 (5.94%) | EFF HIT=94.06%
   Lookahead    : 3943 prefetched -> 632 consumed (16.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 91.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1233 |  42 | 265 | 82.8%| 517.16 | | L24 | 1540 | 1480 |   4 |  56 | 96.4%| 144.75 |
   | L01 | 1540 | 1406 |  22 | 112 | 92.7%| 585.21 | | L25 | 1540 | 1464 |  10 |  66 | 95.7%| 150.39 |
   | L02 | 1540 | 1392 |  13 | 135 | 91.2%| 788.38 | | L26 | 1540 | 1434 |  13 |  93 | 94.0%| 244.38 |
   | L03 | 1540 | 1475 |   0 |  65 | 95.8%| 872.27 | | L27 | 1540 | 1457 |   8 |  75 | 95.1%| 184.23 |
   | L04 | 1540 | 1465 |   1 |  74 | 95.2%| 228.27 | | L28 | 1540 | 1385 |  38 | 117 | 92.4%| 415.45 |
   | L05 | 1540 | 1452 |   3 |  85 | 94.5%| 344.02 | | L29 | 1540 | 1426 |  23 |  91 | 94.1%| 260.72 |
   | L06 | 1540 | 1440 |  11 |  89 | 94.2%| 242.50 | | L30 | 1540 | 1394 |  26 | 120 | 92.2%| 288.09 |
   | L07 | 1540 | 1443 |  10 |  87 | 94.4%| 225.73 | | L31 | 1540 | 1402 |  24 | 114 | 92.6%| 273.68 |
   | L08 | 1540 | 1485 |   2 |  53 | 96.6%| 114.55 | | L32 | 1540 | 1439 |   9 |  92 | 94.0%| 308.30 |
   | L09 | 1540 | 1476 |   4 |  60 | 96.1%| 138.21 | | L33 | 1540 | 1412 |  30 |  98 | 93.6%| 207.42 |
   | L10 | 1540 | 1459 |   3 |  78 | 94.9%| 120.78 | | L34 | 1540 | 1421 |  22 |  97 | 93.7%| 216.06 |
   | L11 | 1540 | 1475 |   2 |  63 | 95.9%| 140.70 | | L35 | 1540 | 1452 |  14 |  74 | 95.2%| 148.36 |
   | L12 | 1540 | 1441 |  12 |  87 | 94.4%| 312.06 | | L36 | 1540 | 1424 |  14 | 102 | 93.4%| 252.08 |
   | L13 | 1540 | 1438 |  13 |  89 | 94.2%| 154.13 | | L37 | 1540 | 1448 |  11 |  81 | 94.7%| 191.75 |
   | L14 | 1540 | 1426 |  19 |  95 | 93.8%| 339.94 | | L38 | 1540 | 1457 |   9 |  74 | 95.2%| 274.46 |
   | L15 | 1540 | 1432 |   9 |  99 | 93.6%| 304.54 | | L39 | 1540 | 1440 |   9 |  91 | 94.1%| 347.78 |
   | L16 | 1540 | 1439 |   8 |  93 | 94.0%| 223.71 | | L40 | 1540 | 1425 |  14 | 101 | 93.4%| 355.30 |
   | L17 | 1540 | 1441 |   6 |  93 | 94.0%| 250.02 | | L41 | 1540 | 1437 |  10 |  93 | 94.0%| 172.85 |
   | L18 | 1540 | 1439 |  12 |  89 | 94.2%| 199.27 | | L42 | 1540 | 1413 |  24 | 103 | 93.3%| 309.69 |
   | L19 | 1540 | 1458 |  10 |  72 | 95.3%| 162.77 | | L43 | 1540 | 1454 |  10 |  76 | 95.1%| 253.52 |
   | L20 | 1540 | 1423 |  14 | 103 | 93.3%| 273.68 | | L44 | 1540 | 1434 |  18 |  88 | 94.3%| 280.88 |
   | L21 | 1540 | 1424 |  18 |  98 | 93.6%| 332.74 | | L45 | 1540 | 1432 |  19 |  89 | 94.2%| 306.81 |
   | L22 | 1540 | 1467 |   3 |  70 | 95.5%| 328.98 | | L46 | 1540 | 1467 |   5 |  68 | 95.6%| 334.18 |
   | L23 | 1540 | 1431 |  15 |  94 | 93.9%| 233.35 | | L47 | 1540 | 1450 |   6 |  84 | 94.5%| 214.31 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 18242.75 MB (Load=4614.69 | Prefill=7175.05 | Warmup=0.00 | Decode=6453.00 MB)
   SSD Data/Token (Decode)      : Avg=102.429 MB/tok (Min=43.060 | P50=98.939 | P95=155.116 | Max=173.748 MB) | Prefill=78.847 MB/tok
   NVMe Batches / Requests      : 2152 Batches | 28574 Raw -> 27546 Merged (1028 LBA Merges, Avg 678.2 KB/io)
   SSD I/O Size Histogram       : <64K=2674 | 64K-512K=7128 | 512K-2M=17310 | >2M=434
   SSD Read Bandwidth (Active)  : Min=10.40 | Avg=711.27 | Peak=10910.52 MB/s | WallAmort=393.20 MB/s (100.0% of 548.1 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=19240.34 MB | Write=128.00 MB | Syscalls=44598
   Sync Stall vs Async DMA      : SyncStall=12739.69 ms | AsyncOverlapped=16883.87 ms (57.0% Overlapped)
   RAM Traffic & Active BW      : 695.74 GB moved | Active=22.34 GB/s (39.9% STREAM) | WallAmort=15.00 GB/s (Max=55.98 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=26.87s (57.9%, 7175.05 MB SSD) | Decode=19.52s (42.1%, 6453.00 MB SSD)
   CPU Time & Utilization       : User=99.094s + Sys=7.750s (Wall=59.229s) | SysUtil=45.1% | ThrUtil=45.1% | 125.37 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  16121.82 ms (104687.2 us/tok | 34.75%)
   MoE AVX2 Q8 Expert Compute   :  13827.92 ms (89791.7 us/tok | 29.80%)
   Router + Lookahead Dispatch  :    855.57 ms ( 5555.6 us/tok |  1.84%)
   LM Head Output Projection    :   1190.45 ms ( 7730.2 us/tok |  2.57%)
   Foreground NVMe Sync Stall   :  12739.69 ms (82725.2 us/tok | 27.46%)
   Unaccounted / OMP & Sampling :   1660.18 ms (10780.4 us/tok |  3.58%) | Total Wall=46395.63 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    82.62%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.35%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     6.57%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.33%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.13%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7742.55 MB (3731 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=4.71 tps | Avg=4.71 tps | Hit=95.4% | NVMe=548.4 MB/s (13785.34 MB, QD=64) | RSS=13682.7 MB
[LIVE-PREFILL] 512/512 tok | Chunk=5.41 tps | Avg=5.03 tps | Hit=96.7% | NVMe=533.2 MB/s (17920.18 MB, QD=64) | RSS=13685.3 MB
[LIVE-DECODE] 8/128 tok | Avg=2.56 tps | Hit=96.7% (LA:+0.1%) | NVMe=555.3 MB/s (19340.95 MB) | RSS=13686.6 MB
[LIVE-DECODE] 16/128 tok | Avg=2.63 tps | Hit=96.8% (LA:+0.2%) | NVMe=580.0 MB/s (20887.47 MB) | RSS=13583.4 MB
[LIVE-DECODE] 24/128 tok | Avg=2.79 tps | Hit=96.8% (LA:+0.2%) | NVMe=608.1 MB/s (22214.54 MB) | RSS=13571.6 MB
[LIVE-DECODE] 32/128 tok | Avg=2.89 tps | Hit=96.9% (LA:+0.3%) | NVMe=631.7 MB/s (23333.58 MB) | RSS=13555.1 MB
[LIVE-DECODE] 40/128 tok | Avg=2.95 tps | Hit=96.9% (LA:+0.3%) | NVMe=656.7 MB/s (24558.62 MB) | RSS=13554.9 MB
[LIVE-DECODE] 48/128 tok | Avg=3.00 tps | Hit=97.0% (LA:+0.3%) | NVMe=680.2 MB/s (25714.20 MB) | RSS=13554.0 MB
[LIVE-DECODE] 56/128 tok | Avg=3.05 tps | Hit=97.0% (LA:+0.3%) | NVMe=703.9 MB/s (26849.16 MB) | RSS=13551.9 MB
[LIVE-DECODE] 64/128 tok | Avg=3.07 tps | Hit=97.0% (LA:+0.4%) | NVMe=723.8 MB/s (27892.78 MB) | RSS=13551.9 MB
[LIVE-DECODE] 72/128 tok | Avg=3.10 tps | Hit=97.1% (LA:+0.4%) | NVMe=745.6 MB/s (29007.18 MB) | RSS=13551.9 MB
[LIVE-DECODE] 80/128 tok | Avg=3.13 tps | Hit=97.1% (LA:+0.4%) | NVMe=768.2 MB/s (30183.58 MB) | RSS=13551.9 MB
[LIVE-DECODE] 88/128 tok | Avg=3.14 tps | Hit=97.2% (LA:+0.4%) | NVMe=789.0 MB/s (31307.03 MB) | RSS=13551.9 MB
[LIVE-DECODE] 96/128 tok | Avg=3.15 tps | Hit=97.2% (LA:+0.5%) | NVMe=810.0 MB/s (32428.42 MB) | RSS=13551.9 MB
[LIVE-DECODE] 104/128 tok | Avg=3.16 tps | Hit=97.2% (LA:+0.5%) | NVMe=830.5 MB/s (33567.13 MB) | RSS=13551.9 MB
[LIVE-DECODE] 112/128 tok | Avg=3.18 tps | Hit=97.3% (LA:+0.5%) | NVMe=851.4 MB/s (34759.05 MB) | RSS=13549.8 MB
[LIVE-DECODE] 120/128 tok | Avg=3.19 tps | Hit=97.3% (LA:+0.5%) | NVMe=871.6 MB/s (35921.99 MB) | RSS=13549.8 MB
[LIVE-DECODE] 127/128 tok | Avg=3.19 tps | Hit=97.3% (LA:+0.5%) | NVMe=887.8 MB/s (36910.92 MB) | RSS=13549.8 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=OFF
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7742.55 MB (3731/25088 exp = 14.87% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13549.85 MB | Peak=14136.88 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (127 tok) : "22222222010
ing{
2
22
3031223132
2732223302232022222331223330
224
2231222122222023022333333333932022222223323272032722223332232222"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 128 Steps)]
   Logit Summary: AvgTop1Prob=14.8% | AvgMargin=0.551 | MinMargin=0.005
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      17 | 2              |   11.64 |   9.2% |      18 |   11.26 | 101691.25 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |   10.56 |   7.0% |      16 |    9.87 |  624.38 |899 | 52 |  9 | 211703.5 |
   |    3 |      17 | 2              |   11.11 |  10.8% |      18 |   10.99 |  624.38 |  0 |  0 |  0 | 211703.5 |
   |    4 |      17 | 2              |   11.51 |  15.9% |      22 |   10.88 |  321.41 |449 | 28 |  3 | 200943.0 |
   |    5 |      17 | 2              |    9.67 |   3.5% |      16 |    9.10 |  305.14 |469 | 11 |  0 | 154418.0 |
   |    6 |      17 | 2              |   11.31 |  11.8% |      18 |   11.07 |  294.51 |473 |  7 |  0 | 160593.0 |
   |    7 |      17 | 2              |   10.93 |   8.5% |      18 |   10.14 |  312.94 |466 | 14 |  0 | 158743.0 |
   |    8 |      17 | 2              |   11.36 |  11.1% |      18 |   11.13 |  317.17 |468 | 12 |  0 | 172443.0 |
   |   13 |     286 | ing            |    8.50 |   1.4% |      68 |    7.85 |  462.75 |436 | 43 |  1 | 201443.0 |
   |   15 |     198 | \n             |    8.95 |   2.8% |      16 |    7.61 |  433.90 |435 | 38 |  7 | 230589.0 |
   |   16 |      17 | 2              |    8.90 |   1.7% |     286 |    8.88 |  370.42 |432 | 43 |  5 | 206414.0 |
   |   14 |      90 | {              |    7.71 |   0.7% |      64 |    7.56 |  359.45 |448 | 27 |  5 | 202589.0 |
   |  125 |      17 | 2              |   11.67 |  19.1% |      18 |   10.97 |  303.84 |472 |  8 |  0 | 146464.0 |
   |  126 |      17 | 2              |   12.31 |  21.8% |     198 |   11.75 |  298.58 |469 | 11 |  0 | 156939.0 |
   |  127 |      17 | 2              |   10.79 |  11.3% |      16 |   10.64 |  301.98 |478 |  2 |  0 | 127793.0 |
   |  128 |      17 | 2              |   12.08 |  19.1% |      18 |   11.55 |  306.45 |475 |  5 |  0 | 146193.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 101.691s, TTFT=101691.25ms): Avg=5.03 | Min=4.71 | Max=5.41 tps
   Prefill Chunks (2): C1:256t/4.7tps/95% | C2:256t/5.4tps/97%
   Decode  (127 tok, 39.754s): Avg=3.19 | Min=1.60 | Max=3.48 tps
   Latency (ms) : Min=287.01 | P10=291.92 | P25=296.69 | P50=303.35 | P75=314.23 | P90=324.69 | P95=345.73 | P99=624.38 | Max=624.38
   Mean/SD/Jitt : Mean=313.02ms | StdDev=45.41ms | Jitter=15.36ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/127
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (306720): RawRAM=297008 (96.83%) | Lookahead=1546 (+0.50%) | ColdMiss=8166 (2.66%) | EFF HIT=97.34%
   Lookahead    : 11519 prefetched -> 1556 consumed (13.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.8% | @64= 97.0% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 6390 | 5713 | 136 | 541 | 91.5%|1140.45 | | L24 | 6390 | 6289 |   5 |  96 | 98.5%| 218.07 |
   | L01 | 6390 | 6128 |  72 | 190 | 97.0%|1497.88 | | L25 | 6390 | 6293 |   7 |  90 | 98.6%| 231.23 |
   | L02 | 6390 | 6138 |  22 | 230 | 96.4%|1561.60 | | L26 | 6390 | 6162 |  49 | 179 | 97.2%| 524.49 |
   | L03 | 6390 | 6316 |   1 |  73 | 98.9%|2259.62 | | L27 | 6390 | 6254 |  20 | 116 | 98.2%| 485.01 |
   | L04 | 6390 | 6276 |   4 | 110 | 98.3%| 672.36 | | L28 | 6390 | 6134 |  49 | 207 | 96.8%| 699.32 |
   | L05 | 6390 | 6232 |  17 | 141 | 97.8%|1167.41 | | L29 | 6390 | 6186 |  36 | 168 | 97.4%| 512.79 |
   | L06 | 6390 | 6250 |  18 | 122 | 98.1%| 656.08 | | L30 | 6390 | 6097 |  57 | 236 | 96.3%| 554.57 |
   | L07 | 6390 | 6242 |  14 | 134 | 97.9%| 527.27 | | L31 | 6390 | 6117 |  60 | 213 | 96.7%| 594.90 |
   | L08 | 6390 | 6319 |   3 |  68 | 98.9%| 250.27 | | L32 | 6390 | 6185 |  37 | 168 | 97.4%| 742.55 |
   | L09 | 6390 | 6318 |   4 |  68 | 98.9%| 107.08 | | L33 | 6390 | 6137 |  54 | 199 | 96.9%| 475.34 |
   | L10 | 6390 | 6284 |   5 | 101 | 98.4%| 174.32 | | L34 | 6390 | 6044 |  86 | 260 | 95.9%| 639.55 |
   | L11 | 6390 | 6321 |   2 |  67 | 99.0%| 180.54 | | L35 | 6390 | 6198 |  32 | 160 | 97.5%| 452.29 |
   | L12 | 6390 | 6277 |   7 | 106 | 98.3%| 629.76 | | L36 | 6390 | 6197 |  31 | 162 | 97.5%| 471.02 |
   | L13 | 6390 | 6237 |  25 | 128 | 98.0%| 252.08 | | L37 | 6390 | 6166 |  35 | 189 | 97.0%| 513.21 |
   | L14 | 6390 | 6223 |  40 | 127 | 98.0%| 622.27 | | L38 | 6390 | 6240 |  16 | 134 | 97.9%| 697.44 |
   | L15 | 6390 | 6186 |  37 | 167 | 97.4%| 565.84 | | L39 | 6390 | 6196 |  27 | 167 | 97.4%| 932.42 |
   | L16 | 6390 | 6190 |  18 | 182 | 97.2%| 483.13 | | L40 | 6390 | 6184 |  38 | 168 | 97.4%| 876.03 |
   | L17 | 6390 | 6174 |  20 | 196 | 96.9%| 603.44 | | L41 | 6390 | 6210 |  12 | 168 | 97.4%| 387.48 |
   | L18 | 6390 | 6173 |  31 | 186 | 97.1%| 565.84 | | L42 | 6390 | 6059 |  83 | 248 | 96.1%| 733.18 |
   | L19 | 6390 | 6220 |  13 | 157 | 97.5%| 329.86 | | L43 | 6390 | 6107 |  43 | 240 | 96.2%| 821.04 |
   | L20 | 6390 | 6124 |  27 | 239 | 96.3%| 882.98 | | L44 | 6390 | 6069 |  60 | 261 | 95.9%| 792.24 |
   | L21 | 6390 | 6144 |  31 | 215 | 96.6%|1315.92 | | L45 | 6390 | 6048 |  90 | 252 | 96.1%| 957.89 |
   | L22 | 6390 | 6284 |   4 | 102 | 98.4%| 419.21 | | L46 | 6390 | 6264 |  16 | 110 | 98.3%| 864.26 |
   | L23 | 6390 | 6199 |  32 | 159 | 97.5%| 615.06 | | L47 | 6390 | 6204 |  20 | 166 | 97.4%| 548.93 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 36910.92 MB (Load=4614.69 | Prefill=13305.49 | Warmup=0.00 | Decode=18990.74 MB)
   SSD Data/Token (Decode)      : Avg=149.533 MB/tok (Min=79.311 | P50=146.620 | P95=190.053 | Max=225.185 MB) | Prefill=25.987 MB/tok
   NVMe Batches / Requests      : 5305 Batches | 70387 Raw -> 68529 Merged (1858 LBA Merges, Avg 551.5 KB/io)
   SSD I/O Size Histogram       : <64K=10481 | 64K-512K=15828 | 512K-2M=41772 | >2M=448
   SSD Read Bandwidth (Active)  : Min=5.41 | Avg=887.81 | Peak=11304.23 MB/s | WallAmort=260.96 MB/s
   OS Kernel I/O Verification   : Read=36931.05 MB | Write=0.00 MB | Syscalls=78044
   Sync Stall vs Async DMA      : SyncStall=23471.05 ms | AsyncOverlapped=32813.23 ms (58.3% Overlapped)
   RAM Traffic & Active BW      : 2226.07 GB moved | Active=20.18 GB/s | WallAmort=15.74 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=101.69s (71.9%, 13305.49 MB SSD) | Decode=39.75s (28.1%, 18990.74 MB SSD)
   CPU Time & Utilization       : User=375.984s + Sys=16.891s (Wall=153.439s) | SysUtil=64.0% | ThrUtil=64.0% | 59.21 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  54667.47 ms (85551.6 us/tok | 38.65%)
   MoE AVX2 Q8 Expert Compute   :  53217.92 ms (83283.1 us/tok | 37.62%)
   Router + Lookahead Dispatch  :   3136.15 ms ( 4907.9 us/tok |  2.22%)
   LM Head Output Projection    :   2420.83 ms ( 3788.5 us/tok |  1.71%)
   Foreground NVMe Sync Stall   :  23471.05 ms (36730.9 us/tok | 16.59%)
   Unaccounted / OMP & Sampling :   4531.52 ms ( 7091.6 us/tok |  3.20%) | Total Wall=141444.94 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    84.54%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.05%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.29%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.60%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.52%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 15266.3ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\nu\n\n\nb2\n\n2\n\nu\n22'
[Stage 3] /v1/chat/completions (stream=true SSE) 3272.8ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7815.19 MB (3766 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=4.76 tps | Avg=4.76 tps | Hit=95.4% | NVMe=548.9 MB/s (13785.34 MB, QD=64) | RSS=13755.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=5.64 tps | Avg=5.16 tps | Hit=96.7% | NVMe=545.3 MB/s (17920.18 MB, QD=64) | RSS=13755.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=5.84 tps | Avg=5.37 tps | Hit=97.2% | NVMe=554.0 MB/s (21711.33 MB, QD=64) | RSS=13754.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=5.69 tps | Avg=5.45 tps | Hit=97.4% | NVMe=548.7 MB/s (25450.53 MB, QD=64) | RSS=13756.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=5.81 tps | Avg=5.51 tps | Hit=97.6% | NVMe=555.8 MB/s (29051.61 MB, QD=64) | RSS=13756.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=5.79 tps | Avg=5.56 tps | Hit=97.7% | NVMe=559.3 MB/s (32660.55 MB, QD=64) | RSS=13756.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=5.64 tps | Avg=5.57 tps | Hit=97.7% | NVMe=561.8 MB/s (36300.10 MB, QD=64) | RSS=13756.8 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=5.60 tps | Avg=5.57 tps | Hit=97.8% | NVMe=557.7 MB/s (39779.71 MB, QD=64) | RSS=13758.1 MB
[LIVE-DECODE] 8/64 tok | Avg=2.18 tps | Hit=97.8% (LA:+0.0%) | NVMe=568.0 MB/s (41435.63 MB) | RSS=13730.3 MB
[LIVE-DECODE] 16/64 tok | Avg=2.50 tps | Hit=97.8% (LA:+0.1%) | NVMe=582.3 MB/s (42903.13 MB) | RSS=13713.5 MB
[LIVE-DECODE] 24/64 tok | Avg=2.66 tps | Hit=97.8% (LA:+0.1%) | NVMe=596.5 MB/s (44276.59 MB) | RSS=13684.2 MB
[LIVE-DECODE] 32/64 tok | Avg=2.75 tps | Hit=97.8% (LA:+0.1%) | NVMe=610.1 MB/s (45550.35 MB) | RSS=13668.1 MB
[LIVE-DECODE] 40/64 tok | Avg=2.82 tps | Hit=97.8% (LA:+0.1%) | NVMe=622.6 MB/s (46748.02 MB) | RSS=13664.0 MB
[LIVE-DECODE] 48/64 tok | Avg=2.84 tps | Hit=97.9% (LA:+0.1%) | NVMe=635.8 MB/s (48184.62 MB) | RSS=13656.3 MB
[LIVE-DECODE] 56/64 tok | Avg=2.84 tps | Hit=97.9% (LA:+0.1%) | NVMe=649.1 MB/s (49744.38 MB) | RSS=13632.0 MB
[LIVE-DECODE] 63/64 tok | Avg=2.86 tps | Hit=97.9% (LA:+0.2%) | NVMe=660.5 MB/s (50986.09 MB) | RSS=13628.1 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=OFF
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7815.19 MB (3766/25088 exp = 15.01% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.68 MB | End=13628.11 MB | Peak=14214.25 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (63 tok) : "


u21
 22111012122502121113212727211221221
20
1
2[2212
12132112"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=9.1% | AvgMargin=0.533 | MinMargin=0.012
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     198 | \n             |    7.38 |   0.7% |      17 |    7.24 | 367396.90 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |    8.16 |   1.8% |      17 |    8.01 |  709.31 |848 | 99 | 13 | 246905.5 |
   |    3 |     198 | \n             |   11.22 |  32.9% |      16 |    8.68 |  709.31 |  0 |  0 |  0 | 246905.5 |
   |    4 |      84 | u              |    8.57 |   2.2% |     198 |    8.18 |  332.08 |434 | 46 |  0 | 188043.0 |
   |    5 |      17 | 2              |    8.16 |   0.8% |      18 |    8.11 |  382.22 |447 | 28 |  5 | 212589.0 |
   |    6 |      16 | 1              |    9.33 |   2.9% |      64 |    9.01 |  401.26 |450 | 29 |  1 | 189139.0 |
   |    7 |     198 | \n             |   10.64 |  10.7% |      16 |   10.09 |  394.14 |427 | 46 |  7 | 216547.0 |
   |    8 |     220 |                |   13.43 |  30.8% |     198 |   12.44 |  352.38 |437 | 41 |  2 | 182689.0 |
   |    9 |      17 | 2              |   10.57 |   7.3% |      16 |   10.29 |  385.72 |436 | 43 |  1 | 212839.0 |
   |   52 |      17 | 2              |   11.57 |  14.9% |      16 |   11.54 |  378.88 |429 | 45 |  6 | 227443.0 |
   |   45 |      17 | 2              |    9.48 |   4.7% |      16 |    9.41 |  373.28 |441 | 38 |  1 | 186314.0 |
   |   15 |      16 | 1              |   10.60 |  11.2% |      17 |   10.06 |  369.38 |440 | 36 |  4 | 213864.0 |
   |   61 |      17 | 2              |   10.66 |  13.6% |      16 |   10.09 |  328.73 |466 | 14 |  0 | 177689.0 |
   |   62 |      16 | 1              |    9.62 |   7.7% |      17 |    9.40 |  317.79 |472 |  8 |  0 | 145964.0 |
   |   63 |      16 | 1              |   11.23 |   5.0% |      17 |   11.07 |  333.97 |471 |  9 |  0 | 173814.0 |
   |   64 |      17 | 2              |   11.22 |   9.4% |      18 |    9.84 |  334.19 |463 | 17 |  0 | 194168.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 367.397s, TTFT=367396.90ms): Avg=5.57 | Min=4.76 | Max=5.84 tps
   Prefill Chunks (8): C1:256t/4.8tps/95% | C2:256t/5.6tps/97% | C3:256t/5.8tps/97% | C4:256t/5.7tps/97%
                       C5:256t/5.8tps/98% | C6:256t/5.8tps/98% | C7:256t/5.6tps/98% | C8:256t/5.6tps/98%
   Decode  (63 tok, 22.032s): Avg=2.86 | Min=1.41 | Max=3.20 tps
   Latency (ms) : Min=312.41 | P10=321.63 | P25=323.65 | P50=332.08 | P75=347.61 | P90=378.88 | P95=394.14 | P99=709.31 | Max=709.31
   Mean/SD/Jitt : Mean=349.71ms | StdDev=67.93ms | Jitter=18.86ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1013280): RawRAM=990167 (97.72%) | Lookahead=1553 (+0.15%) | ColdMiss=21560 (2.13%) | EFF HIT=97.87%
   Lookahead    : 6728 prefetched -> 1563 consumed (23.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.8% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21110 |18966 | 187 |1957 | 90.7%|3611.72 | | L24 |21110 |20937 |  10 | 163 | 99.2%| 385.38 |
   | L01 |21110 |20513 | 105 | 492 | 97.7%|1258.81 | | L25 |21110 |20940 |   6 | 164 | 99.2%| 323.34 |
   | L02 |21110 |20512 |  34 | 564 | 97.3%|1613.82 | | L26 |21110 |20591 |  32 | 487 | 97.7%|1107.25 |
   | L03 |21110 |21030 |   2 |  78 | 99.6%| 934.30 | | L27 |21110 |20840 |  23 | 247 | 98.8%| 629.76 |
   | L04 |21110 |20914 |  10 | 186 | 99.1%| 678.59 | | L28 |21110 |20477 |  45 | 588 | 97.2%|1381.71 |
   | L05 |21110 |20822 |  22 | 266 | 98.7%| 958.74 | | L29 |21110 |20661 |  34 | 415 | 98.0%| 720.21 |
   | L06 |21110 |20830 |  44 | 236 | 98.9%| 757.59 | | L30 |21110 |20286 |  32 | 792 | 96.2%|1264.70 |
   | L07 |21110 |20836 |  33 | 241 | 98.9%| 523.90 | | L31 |21110 |20383 |  38 | 689 | 96.7%|1129.30 |
   | L08 |21110 |21036 |   3 |  71 | 99.7%| 155.64 | | L32 |21110 |20594 |  22 | 494 | 97.7%|1139.21 |
   | L09 |21110 |21033 |   2 |  75 | 99.6%| 105.83 | | L33 |21110 |20494 |  19 | 597 | 97.2%| 956.45 |
   | L10 |21110 |20960 |   5 | 145 | 99.3%| 212.92 | | L34 |21110 |20230 |  45 | 835 | 96.0%|1365.53 |
   | L11 |21110 |21035 |   2 |  73 | 99.7%| 153.15 | | L35 |21110 |20653 |  22 | 435 | 97.9%| 713.01 |
   | L12 |21110 |20983 |   5 | 122 | 99.4%| 445.53 | | L36 |21110 |20591 |  37 | 482 | 97.7%| 881.54 |
   | L13 |21110 |20889 |  20 | 201 | 99.0%| 373.07 | | L37 |21110 |20542 |  22 | 546 | 97.4%|1112.89 |
   | L14 |21110 |20801 |  47 | 262 | 98.8%| 645.31 | | L38 |21110 |20772 |  18 | 320 | 98.5%| 936.18 |
   | L15 |21110 |20641 |  62 | 407 | 98.1%| 990.70 | | L39 |21110 |20593 |  32 | 485 | 97.7%|1173.05 |
   | L16 |21110 |20585 |  27 | 498 | 97.6%|1069.65 | | L40 |21110 |20688 |  36 | 386 | 98.2%|1079.05 |
   | L17 |21110 |20421 |  37 | 652 | 96.9%|1406.15 | | L41 |21110 |20687 |  12 | 411 | 98.1%| 685.64 |
   | L18 |21110 |20495 |  29 | 586 | 97.2%|1255.76 | | L42 |21110 |20363 |  62 | 685 | 96.8%|1284.86 |
   | L19 |21110 |20689 |  34 | 387 | 98.2%| 661.16 | | L43 |21110 |20283 |  37 | 790 | 96.3%|1387.13 |
   | L20 |21110 |20333 |  35 | 742 | 96.5%|1317.99 | | L44 |21110 |20282 |  48 | 780 | 96.3%|1323.75 |
   | L21 |21110 |20446 |  44 | 620 | 97.1%|1733.25 | | L45 |21110 |20333 |  66 | 711 | 96.6%|1390.01 |
   | L22 |21110 |20921 |  12 | 177 | 99.2%| 496.29 | | L46 |21110 |20894 |   9 | 207 | 99.0%| 643.87 |
   | L23 |21110 |20573 |  31 | 506 | 97.6%| 983.81 | | L47 |21110 |20789 |  14 | 307 | 98.5%| 829.03 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 50986.09 MB (Load=4614.69 | Prefill=35165.02 | Warmup=0.00 | Decode=11206.38 MB)
   SSD Data/Token (Decode)      : Avg=177.879 MB/tok (Min=134.706 | P50=178.407 | P95=211.472 | Max=241.119 MB) | Prefill=17.170 MB/tok
   NVMe Batches / Requests      : 3870 Batches | 119748 Raw -> 115601 Merged (4147 LBA Merges, Avg 451.6 KB/io)
   SSD I/O Size Histogram       : <64K=33825 | 64K-512K=21545 | 512K-2M=59746 | >2M=485
   SSD Read Bandwidth (Active)  : Min=10.52 | Avg=660.55 | Peak=10878.95 MB/s | WallAmort=130.93 MB/s
   OS Kernel I/O Verification   : Read=51006.63 MB | Write=0.00 MB | Syscalls=125114
   Sync Stall vs Async DMA      : SyncStall=58740.66 ms | AsyncOverlapped=68476.11 ms (53.8% Overlapped)
   RAM Traffic & Active BW      : 5635.43 GB moved | Active=17.89 GB/s | WallAmort=14.47 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=367.40s (94.3%, 35165.02 MB SSD) | Decode=22.03s (5.7%, 11206.38 MB SSD)
   CPU Time & Utilization       : User=1156.344s + Sys=21.062s (Wall=401.084s) | SysUtil=73.4% | ThrUtil=73.4% | 67.88 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 148633.50 ms (70409.0 us/tok | 38.17%)
   MoE AVX2 Q8 Expert Compute   : 165086.75 ms (78203.1 us/tok | 42.39%)
   Router + Lookahead Dispatch  :   9056.98 ms ( 4290.4 us/tok |  2.33%)
   LM Head Output Projection    :   1240.09 ms (  587.4 us/tok |  0.32%)
   Foreground NVMe Sync Stall   :  58740.66 ms (27826.0 us/tok | 15.08%)
   Unaccounted / OMP & Sampling :   6670.89 ms ( 3160.1 us/tok |  1.71%) | Total Wall=389428.86 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    90.78%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     0.99%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.66%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     3.83%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.74%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=46.0s | Competitor drastic-underperform cutoff=230.0s (5x Apex)
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=230.0s) ===
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
  [Colibri-Qwen38] resident weights loaded in 8.8s | RSS after load: 4.60 GB
  [Colibri-Qwen38] [qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=230.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.1s / cutoff=230.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=230.0s
  [Colibri-Qwen38] TTFT: 25.02 s (time to first token)
  [Colibri-Qwen38] [qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
  [Colibri-Qwen38] [qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
  [Colibri-Qwen38] [qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes
  [Colibri-Qwen38] 
  [Colibri-Qwen38] PEAK RSS: 10.73 GB
  [Colibri-Qwen38] Expert cache hit rate: 62.0% (hit=15849 miss=9733)
  [Colibri-Qwen38] Speed: 0.66 tok/s (48.8s for 32 tokens)
  [Colibri-Qwen38] [STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage
  [COMP-LIVE] Colibri-Qwen38: elapsed=60.1s / cutoff=230.0s
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
=== [Colibri-Qwen38] Finished rc=1 elapsed=60.63s cancelled=False ===
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 3.09 | 2.74 | 323.62 | 91.76% | 673.02 | 12786.50 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 5.03 | 3.19 | 303.35 | 97.34% | 887.81 | 14136.88 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 5.57 | 2.86 | 332.08 | 97.87% | 660.55 | 14214.25 MB | Native GGUF + MTP ON |
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
-rwxr-xr-x 1 runneradmin 197121 892K Nov 14 06:46 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 892K Nov 14 06:46 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.44 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    553.79 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2117.89 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9731.40 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  12451.12 MB/s
   RND4K Q32T16 Read                  :   1043.45 MB/s (  267122 IOPS)
   RND4K Q1T1  Read                   :   1134.49 MB/s (Latency: 3.44 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     97.32 GB/s
   AVX2 256-bit Sequential Write BW   :     97.37 GB/s
   STREAM Triad (A = B + s*C) BW      :     42.37 GB/s
   Random Pointer-Chase Latency       :     34.70 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     71.85 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    278.06 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     39.84 GB/s (FP32 Equiv)
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
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=3.24 MB (67 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2602.81 tps | Avg=2602.81 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=73.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2291.01 tps | Avg=2436.98 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=73.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1999.40 tps | Avg=2271.28 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=74.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1757.21 tps | Avg=2116.49 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=74.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1580.35 tps | Avg=1982.01 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=74.7 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1396.28 tps | Avg=1852.49 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=75.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1272.13 tps | Avg=1739.14 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=75.2 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1197.58 tps | Avg=1646.09 tps | Hit=100.0% | NVMe=3486.8 MB/s (6.58 MB, QD=64) | RSS=75.5 MB
[LIVE-DECODE] 8/32 tok | Avg=347.21 tps | Hit=100.0% (LA:+0.0%) | NVMe=3486.8 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 16/32 tok | Avg=347.53 tps | Hit=100.0% (LA:+0.0%) | NVMe=3486.8 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 24/32 tok | Avg=346.78 tps | Hit=100.0% (LA:+0.0%) | NVMe=3486.8 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 32/32 tok | Avg=344.87 tps | Hit=100.0% (LA:+0.0%) | NVMe=3486.8 MB/s (6.58 MB) | RSS=75.5 MB

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
   LRFU Cache / Staging Ring    : 3.24 MB (67/64 exp = 104.69% pinned) | Staging=3.09 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=75.51 MB | Peak=75.51 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1244.16 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    2.89 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    2.89 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    2.83 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    2.83 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    2.89 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    2.89 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    2.91 | 12 |  0 |  0 |     0.0 |
   |   26 |     246 | tok_246        |  195.41 | 100.0% |      54 |  174.46 |    2.98 | 12 |  0 |  0 |     0.0 |
   |   27 |     229 | tok_229        |  171.70 | 100.0% |      70 |  154.45 |    2.98 |  0 |  0 |  0 |     0.0 |
   |   28 |     246 | tok_246        |  194.87 | 100.0% |      54 |  173.43 |    2.93 | 12 |  0 |  0 |     0.0 |
   |   29 |     229 | tok_229        |  172.54 | 100.0% |      70 |  154.16 |    2.93 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    2.92 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    2.92 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    2.95 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    2.95 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.244s, TTFT=1244.16ms): Avg=1646.09 | Min=1197.58 | Max=2602.81 tps
   Prefill Chunks (8): C1:256t/2602.8tps/100% | C2:256t/2291.0tps/100% | C3:256t/1999.4tps/100% | C4:256t/1757.2tps/100%
                       C5:256t/1580.3tps/100% | C6:256t/1396.3tps/100% | C7:256t/1272.1tps/100% | C8:256t/1197.6tps/100%
   Decode  (32 tok, 0.093s): Avg=344.87 | Min=335.26 | Max=353.27 tps
   Latency (ms) : Min=2.83 | P10=2.85 | P25=2.88 | P50=2.90 | P75=2.93 | P90=2.95 | P95=2.98 | P99=2.98 | Max=2.98
   Mean/SD/Jitt : Mean=2.90ms | StdDev=0.04ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (24768): RawRAM=24768 (100.00%) | Lookahead=0 (+0.00%) | ColdMiss=0 (0.00%) | EFF HIT=100.00%
   Lookahead    : 0 prefetched -> 0 consumed (0.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16=100.0% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L01 | 8256 | 8256 |   0 |   0 |100.0%|   0.00 | | L03 | 8256 | 8256 |   0 |   0 |100.0%|   0.00 |
   | L02 | 8256 | 8256 |   0 |   0 |100.0%|   0.00 | |     |      |      |     |     |      |        |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 6.58 MB (Load=6.58 | Prefill=0.00 | Warmup=0.00 | Decode=0.00 MB)
   SSD Data/Token (Decode)      : Avg=0.000 MB/tok (Min=0.000 | P50=0.000 | P95=0.000 | Max=0.000 MB) | Prefill=0.000 MB/tok
   NVMe Batches / Requests      : 1 Batches | 331 Raw -> 143 Merged (188 LBA Merges, Avg 47.1 KB/io)
   SSD I/O Size Histogram       : <64K=107 | 64K-512K=32 | 512K-2M=4 | >2M=0
   SSD Read Bandwidth (Active)  : Min=405.88 | Avg=3486.77 | Peak=7267.44 MB/s | WallAmort=4.92 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=0.97 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=1.13 GB/s | WallAmort=1.07 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.24s (93.1%, 0.00 MB SSD) | Decode=0.09s (6.9%, 0.00 MB SSD)
   CPU Time & Utilization       : User=1.406s + Sys=0.562s (Wall=1.350s) | SysUtil=36.5% | ThrUtil=36.5% | 33.73 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1137.25 ms (  546.8 us/tok | 85.06%)
   MoE AVX2 Q8 Expert Compute   :    130.03 ms (   62.5 us/tok |  9.73%)
   Router + Lookahead Dispatch  :     33.07 ms (   15.9 us/tok |  2.47%)
   LM Head Output Projection    :      3.54 ms (    1.7 us/tok |  0.26%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     33.05 ms (   15.9 us/tok |  2.47%) | Total Wall=1336.94 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    20.11%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.99%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.12%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    74.43%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.35%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3725.79 tps | Avg=3725.79 tps | Hit=99.2% | NVMe=4061.0 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=3500.09 tps | Avg=3609.41 tps | Hit=99.2% | NVMe=5713.5 MB/s (42.92 MB, QD=64) | RSS=89.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=3116.61 tps | Avg=3428.70 tps | Hit=99.2% | NVMe=6794.6 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=3101.59 tps | Avg=3340.62 tps | Hit=99.2% | NVMe=7384.0 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2870.93 tps | Avg=3234.78 tps | Hit=99.2% | NVMe=8021.8 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2661.30 tps | Avg=3122.63 tps | Hit=99.2% | NVMe=8574.6 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2455.31 tps | Avg=3005.92 tps | Hit=99.2% | NVMe=9023.0 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2194.22 tps | Avg=2873.07 tps | Hit=99.2% | NVMe=9411.3 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=317.17 tps | Hit=99.2% (LA:+0.0%) | NVMe=9270.2 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=318.77 tps | Hit=99.2% (LA:+0.1%) | NVMe=9195.6 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=320.65 tps | Hit=99.2% (LA:+0.1%) | NVMe=9074.8 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=323.62 tps | Hit=99.2% (LA:+0.1%) | NVMe=8973.0 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=91.71 MB | Peak=91.71 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 |  712.83 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    3.17 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    3.17 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    3.15 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    3.15 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    3.15 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    3.15 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    3.15 | 16 |  0 |  0 |    32.0 |
   |    9 |      49 | qtok_49        |   84.72 | 100.0% |     129 |   76.64 |    3.15 |  0 |  0 |  0 |    32.0 |
   |   12 |     254 | qtok_254       |   71.34 |  95.3% |      66 |   68.21 |    3.13 | 16 |  0 |  0 |    32.0 |
   |   13 |     129 | qtok_129       |   76.30 |  99.3% |      49 |   71.12 |    3.13 |  0 |  0 |  0 |    32.0 |
   |   10 |     254 | qtok_254       |   70.81 |  99.7% |      66 |   64.77 |    3.13 | 15 |  1 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    2.98 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    2.98 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    2.98 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    2.98 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 0.713s, TTFT=712.83ms): Avg=2873.07 | Min=2194.22 | Max=3725.79 tps
   Prefill Chunks (8): C1:256t/3725.8tps/99% | C2:256t/3500.1tps/99% | C3:256t/3116.6tps/99% | C4:256t/3101.6tps/99%
                       C5:256t/2870.9tps/99% | C6:256t/2661.3tps/99% | C7:256t/2455.3tps/99% | C8:256t/2194.2tps/99%
   Decode  (32 tok, 0.099s): Avg=323.62 | Min=315.78 | Max=335.07 tps
   Latency (ms) : Min=2.98 | P10=2.98 | P25=3.04 | P50=3.11 | P75=3.15 | P90=3.15 | P95=3.17 | P99=3.17 | Max=3.17
   Mean/SD/Jitt : Mean=3.09ms | StdDev=0.06ms | Jitter=0.01ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=494.97 | Avg=8972.99 | Peak=19438.24 MB/s | WallAmort=191.13 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=3.43 ms | AsyncOverlapped=16.29 ms (82.6% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=2.98 GB/s | WallAmort=2.59 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=0.71s (87.8%, 144.44 MB SSD) | Decode=0.10s (12.2%, 3.83 MB SSD)
   CPU Time & Utilization       : User=1.297s + Sys=0.328s (Wall=0.832s) | SysUtil=48.8% | ThrUtil=48.8% | 45.16 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    504.67 ms (  242.6 us/tok | 62.17%)
   MoE AVX2 Q8 Expert Compute   :    197.79 ms (   95.1 us/tok | 24.37%)
   Router + Lookahead Dispatch  :     43.77 ms (   21.0 us/tok |  5.39%)
   LM Head Output Projection    :      3.22 ms (    1.5 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :      3.43 ms (    1.6 us/tok |  0.42%)
   Unaccounted / OMP & Sampling :     58.83 ms (   28.3 us/tok |  7.25%) | Total Wall=811.71 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    18.49%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.67%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.94%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    66.03%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     7.87%  |
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
  "expert_cache_ram_bytes": 2534400,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 126.6,
    "avg_tps": 1295.43,
    "min_tps": 1041.61,
    "max_tps": 1475.37
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 263.33,
    "min_tps": 243.6,
    "max_tps": 288.92,
    "p50_ms": 3.8,
    "p90_ms": 4.04,
    "p99_ms": 4.11,
    "mean_ms": 3.8,
    "jitter_ms": 0.08
  },
  "cache": {
    "raw_hit_rate_pct": 100.0,
    "effective_hit_rate_pct": 100.0,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 5470784,
    "prefill_bytes": 0,
    "warmup_bytes": 0,
    "decode_bytes": 0,
    "bytes_per_token": 26949.67,
    "avg_mbs": 2942.5,
    "peak_mbs": 6281.41,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.78
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
    "dense_attention": 206.09,
    "moe_compute": 56.72,
    "router_lookahead": 3.81,
    "lm_head": 4.96,
    "unaccounted": 3.12
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.38,
    "ram_bandwidth_pinning": 3.35,
    "expert_cache_lrfu": 12.31,
    "lookahead_parallel_overlap": 1.41,
    "ssd_nvme_throughput": 0.55,
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
    "ttft_ms": 168.38,
    "avg_tps": 974.01,
    "min_tps": 684.7,
    "max_tps": 1125.23
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 229.71,
    "min_tps": 214.62,
    "max_tps": 242.7,
    "p50_ms": 4.29,
    "p90_ms": 4.61,
    "p99_ms": 4.66,
    "mean_ms": 4.35,
    "jitter_ms": 0.07
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
    "avg_mbs": 4634.85,
    "peak_mbs": 16119.46,
    "sync_wait_ms": 2.69,
    "async_overlap_ms": 7.01
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
    "dense_attention": 190.26,
    "moe_compute": 112.22,
    "router_lookahead": 4.8,
    "lm_head": 4.99,
    "unaccounted": 23.19
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 80.5,
    "ram_bandwidth_pinning": 3.84,
    "expert_cache_lrfu": 8.5,
    "lookahead_parallel_overlap": 4.42,
    "ssd_nvme_throughput": 2.74,
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
   System Memory (RAM): 15.99 GB Total / 13.44 GB Available
   Active Drive Space : 219.98 GB Total / 219.81 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    555.54 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2122.39 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9542.77 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  12409.89 MB/s
   RND4K Q32T16 Read                  :   1147.15 MB/s (  293671 IOPS)
   RND4K Q1T1  Read                   :   1158.41 MB/s (Latency: 3.37 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     94.07 GB/s
   AVX2 256-bit Sequential Write BW   :     96.03 GB/s
   STREAM Triad (A = B + s*C) BW      :     55.41 GB/s
   Random Pointer-Chase Latency       :     33.51 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     70.18 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    273.45 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     39.66 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 28.11 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 108.84 MB/s (9.41s)
   Window #01 ( 60.0 MB in 0.50s):   119.85 MB/s (Uncached Direct Read)
   Window #02 ( 60.0 MB in 0.51s):   117.33 MB/s (Uncached Direct Read)
   Window #03 ( 64.0 MB in 0.53s):   120.08 MB/s (Uncached Direct Read)
   Window #04 ( 60.0 MB in 0.50s):   119.78 MB/s (Uncached Direct Read)
   Window #05 ( 64.0 MB in 0.53s):   121.22 MB/s (Uncached Direct Read)
   Window #06 ( 60.0 MB in 0.50s):   119.87 MB/s (Uncached Direct Read)
   Window #07 ( 64.0 MB in 0.53s):   120.94 MB/s (Uncached Direct Read)
   Window #08 ( 64.0 MB in 0.53s):   120.51 MB/s (Uncached Direct Read)
   Window #09 ( 60.0 MB in 0.50s):   119.20 MB/s (Uncached Direct Read)
   Window #10 ( 60.0 MB in 0.50s):   119.67 MB/s (Uncached Direct Read)
   Window #11 ( 64.0 MB in 0.53s):   121.26 MB/s (Uncached Direct Read)
   Window #12 ( 64.0 MB in 0.55s):   116.36 MB/s (Uncached Direct Read)
   Window #13 ( 64.0 MB in 0.53s):   121.26 MB/s (Uncached Direct Read)
   Window #14 ( 60.0 MB in 0.50s):   119.81 MB/s (Uncached Direct Read)
   Window #15 ( 60.0 MB in 0.50s):   119.80 MB/s (Uncached Direct Read)
   Window #16 ( 60.0 MB in 0.50s):   119.78 MB/s (Uncached Direct Read)
   Window #17 ( 36.0 MB in 0.32s):   111.70 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   119.49 MB/s (Min=111.70 | Max=121.26 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 219.81 GB / 219.98 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 268.98 MB/s (3.81s)
   Window #01 (272.0 MB in 0.51s):   537.26 MB/s (Uncached Direct Read)
   Window #02 (272.0 MB in 0.51s):   536.40 MB/s (Uncached Direct Read)
   Window #03 (272.0 MB in 0.51s):   536.38 MB/s (Uncached Direct Read)
   Window #04 (208.0 MB in 0.39s):   536.38 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   536.61 MB/s (Min=536.38 | Max=537.26 MB/s)
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
   System Memory (RAM): 15.99 GB Total / 14.65 GB Available
   Active Drive Space : 219.98 GB Total / 149.17 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    548.11 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2123.16 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8998.94 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11401.04 MB/s
   RND4K Q32T16 Read                  :    832.67 MB/s (  213165 IOPS)
   RND4K Q1T1  Read                   :   1028.12 MB/s (Latency: 3.80 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     93.59 GB/s
   AVX2 256-bit Sequential Write BW   :     94.87 GB/s
   STREAM Triad (A = B + s*C) BW      :     55.98 GB/s
   Random Pointer-Chase Latency       :     28.02 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     72.12 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    278.00 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     38.11 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=3.39 tps | Avg=3.39 tps | Hit=90.0% | NVMe=548.8 MB/s (11789.75 MB, QD=64) | RSS=13595.6 MB

 >>> [Apex-Model-Response] b
0
222719
12
22
21
11122922227321222292271227227123122220212122
================================================================================

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=OFF
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7694.82 MB (3708/25088 exp = 14.78% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.82 MB | End=13536.30 MB | Peak=14053.68 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (63 tok) : "b
0
222719
12
22
21
11122922227321222292271227227123122220212122"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=14.3% | AvgMargin=0.497 | MinMargin=0.027
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      65 | b              |    9.34 |   1.9% |      79 |    9.00 | 26870.69 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |   10.69 |  14.6% |     271 |    7.46 |  566.01 |904 | 51 |  5 | 158753.5 |
   |    3 |      15 | 0              |    9.12 |   1.0% |      79 |    8.96 |  566.01 |  0 |  0 |  0 | 158753.5 |
   |    4 |     198 | \n             |   11.23 |  26.1% |      65 |    7.68 |  378.35 |445 | 33 |  2 | 167539.0 |
   |    5 |      17 | 2              |    7.61 |   0.8% |      15 |    7.44 |  294.56 |472 |  8 |  0 | 91018.0 |
   |    6 |      17 | 2              |    9.33 |   3.4% |      16 |    8.85 |  340.19 |451 | 27 |  2 | 151914.0 |
   |    7 |      17 | 2              |   10.09 |   7.7% |      24 |   10.02 |  354.11 |442 | 38 |  0 | 177918.0 |
   |    8 |      22 | 7              |   11.04 |   9.6% |      17 |   10.99 |  309.54 |451 | 26 |  3 | 135743.0 |
   |   10 |      24 | 9              |   10.61 |   9.0% |      17 |   10.51 |  338.87 |451 | 27 |  2 | 158839.0 |
   |   59 |      17 | 2              |   12.29 |  13.6% |      15 |   12.07 |  332.64 |453 | 23 |  4 | 155989.0 |
   |   11 |     198 | \n             |   11.25 |  22.6% |      16 |   10.26 |  328.26 |449 | 31 |  0 | 172739.0 |
   |   14 |     198 | \n             |   12.07 |  31.1% |      17 |   10.31 |  314.11 |470 | 10 |  0 | 113389.0 |
   |   61 |      17 | 2              |   11.98 |  21.6% |      18 |   11.12 |  288.27 |478 |  2 |  0 | 117789.0 |
   |   62 |      16 | 1              |   12.20 |  17.7% |      17 |   12.06 |  298.69 |476 |  4 |  0 | 119168.0 |
   |   63 |      17 | 2              |   13.90 |  25.0% |      18 |   13.58 |  285.91 |479 |  1 |  0 | 95168.0 |
   |   64 |      17 | 2              |   12.55 |  17.2% |      16 |   12.28 |  294.00 |475 |  5 |  0 | 79443.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 26.871s, TTFT=26870.69ms): Avg=3.39 | Min=3.39 | Max=3.39 tps
   Prefill Chunks (1): C1:91t/3.4tps/90%
   Decode  (63 tok, 19.525s): Avg=3.23 | Min=1.77 | Max=3.54 tps
   Latency (ms) : Min=282.67 | P10=289.09 | P25=292.33 | P50=295.38 | P75=306.78 | P90=332.64 | P95=354.11 | P99=566.01 | Max=566.01
   Mean/SD/Jitt : Mean=309.92ms | StdDev=49.30ms | Jitter=14.95ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (73920): RawRAM=68907 (93.22%) | Lookahead=622 (+0.84%) | ColdMiss=4391 (5.94%) | EFF HIT=94.06%
   Lookahead    : 3943 prefetched -> 632 consumed (16.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 91.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1233 |  42 | 265 | 82.8%| 517.16 | | L24 | 1540 | 1480 |   4 |  56 | 96.4%| 144.75 |
   | L01 | 1540 | 1406 |  22 | 112 | 92.7%| 585.21 | | L25 | 1540 | 1464 |  10 |  66 | 95.7%| 150.39 |
   | L02 | 1540 | 1392 |  13 | 135 | 91.2%| 788.38 | | L26 | 1540 | 1434 |  13 |  93 | 94.0%| 244.38 |
   | L03 | 1540 | 1475 |   0 |  65 | 95.8%| 872.27 | | L27 | 1540 | 1457 |   8 |  75 | 95.1%| 184.23 |
   | L04 | 1540 | 1465 |   1 |  74 | 95.2%| 228.27 | | L28 | 1540 | 1385 |  38 | 117 | 92.4%| 415.45 |
   | L05 | 1540 | 1452 |   3 |  85 | 94.5%| 344.02 | | L29 | 1540 | 1426 |  23 |  91 | 94.1%| 260.72 |
   | L06 | 1540 | 1440 |  11 |  89 | 94.2%| 242.50 | | L30 | 1540 | 1394 |  26 | 120 | 92.2%| 288.09 |
   | L07 | 1540 | 1443 |  10 |  87 | 94.4%| 225.73 | | L31 | 1540 | 1402 |  24 | 114 | 92.6%| 273.68 |
   | L08 | 1540 | 1485 |   2 |  53 | 96.6%| 114.55 | | L32 | 1540 | 1439 |   9 |  92 | 94.0%| 308.30 |
   | L09 | 1540 | 1476 |   4 |  60 | 96.1%| 138.21 | | L33 | 1540 | 1412 |  30 |  98 | 93.6%| 207.42 |
   | L10 | 1540 | 1459 |   3 |  78 | 94.9%| 120.78 | | L34 | 1540 | 1421 |  22 |  97 | 93.7%| 216.06 |
   | L11 | 1540 | 1475 |   2 |  63 | 95.9%| 140.70 | | L35 | 1540 | 1452 |  14 |  74 | 95.2%| 148.36 |
   | L12 | 1540 | 1441 |  12 |  87 | 94.4%| 312.06 | | L36 | 1540 | 1424 |  14 | 102 | 93.4%| 252.08 |
   | L13 | 1540 | 1438 |  13 |  89 | 94.2%| 154.13 | | L37 | 1540 | 1448 |  11 |  81 | 94.7%| 191.75 |
   | L14 | 1540 | 1426 |  19 |  95 | 93.8%| 339.94 | | L38 | 1540 | 1457 |   9 |  74 | 95.2%| 274.46 |
   | L15 | 1540 | 1432 |   9 |  99 | 93.6%| 304.54 | | L39 | 1540 | 1440 |   9 |  91 | 94.1%| 347.78 |
   | L16 | 1540 | 1439 |   8 |  93 | 94.0%| 223.71 | | L40 | 1540 | 1425 |  14 | 101 | 93.4%| 355.30 |
   | L17 | 1540 | 1441 |   6 |  93 | 94.0%| 250.02 | | L41 | 1540 | 1437 |  10 |  93 | 94.0%| 172.85 |
   | L18 | 1540 | 1439 |  12 |  89 | 94.2%| 199.27 | | L42 | 1540 | 1413 |  24 | 103 | 93.3%| 309.69 |
   | L19 | 1540 | 1458 |  10 |  72 | 95.3%| 162.77 | | L43 | 1540 | 1454 |  10 |  76 | 95.1%| 253.52 |
   | L20 | 1540 | 1423 |  14 | 103 | 93.3%| 273.68 | | L44 | 1540 | 1434 |  18 |  88 | 94.3%| 280.88 |
   | L21 | 1540 | 1424 |  18 |  98 | 93.6%| 332.74 | | L45 | 1540 | 1432 |  19 |  89 | 94.2%| 306.81 |
   | L22 | 1540 | 1467 |   3 |  70 | 95.5%| 328.98 | | L46 | 1540 | 1467 |   5 |  68 | 95.6%| 334.18 |
   | L23 | 1540 | 1431 |  15 |  94 | 93.9%| 233.35 | | L47 | 1540 | 1450 |   6 |  84 | 94.5%| 214.31 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 18242.75 MB (Load=4614.69 | Prefill=7175.05 | Warmup=0.00 | Decode=6453.00 MB)
   SSD Data/Token (Decode)      : Avg=102.429 MB/tok (Min=43.060 | P50=98.939 | P95=155.116 | Max=173.748 MB) | Prefill=78.847 MB/tok
   NVMe Batches / Requests      : 2152 Batches | 28574 Raw -> 27546 Merged (1028 LBA Merges, Avg 678.2 KB/io)
   SSD I/O Size Histogram       : <64K=2674 | 64K-512K=7128 | 512K-2M=17310 | >2M=434
   SSD Read Bandwidth (Active)  : Min=10.40 | Avg=711.27 | Peak=10910.52 MB/s | WallAmort=393.20 MB/s (100.0% of 548.1 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=19240.34 MB | Write=128.00 MB | Syscalls=44598
   Sync Stall vs Async DMA      : SyncStall=12739.69 ms | AsyncOverlapped=16883.87 ms (57.0% Overlapped)
   RAM Traffic & Active BW      : 695.74 GB moved | Active=22.34 GB/s (39.9% STREAM) | WallAmort=15.00 GB/s (Max=55.98 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=26.87s (57.9%, 7175.05 MB SSD) | Decode=19.52s (42.1%, 6453.00 MB SSD)
   CPU Time & Utilization       : User=99.094s + Sys=7.750s (Wall=59.229s) | SysUtil=45.1% | ThrUtil=45.1% | 125.37 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  16121.82 ms (104687.2 us/tok | 34.75%)
   MoE AVX2 Q8 Expert Compute   :  13827.92 ms (89791.7 us/tok | 29.80%)
   Router + Lookahead Dispatch  :    855.57 ms ( 5555.6 us/tok |  1.84%)
   LM Head Output Projection    :   1190.45 ms ( 7730.2 us/tok |  2.57%)
   Foreground NVMe Sync Stall   :  12739.69 ms (82725.2 us/tok | 27.46%)
   Unaccounted / OMP & Sampling :   1660.18 ms (10780.4 us/tok |  3.58%) | Total Wall=46395.63 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    82.62%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.35%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     6.57%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.33%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.13%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_qwen38_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6433.11 MB (3100 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=3.09 tps | Avg=3.09 tps | Hit=88.1% | NVMe=544.2 MB/s (10578.12 MB, QD=64) | RSS=12322.8 MB
[LIVE-DECODE] 8/32 tok | Avg=2.12 tps | Hit=89.2% (LA:+1.0%) | NVMe=571.1 MB/s (12431.96 MB) | RSS=12325.5 MB
[LIVE-DECODE] 16/32 tok | Avg=2.41 tps | Hit=90.2% (LA:+1.7%) | NVMe=609.7 MB/s (14020.65 MB) | RSS=12325.5 MB
[LIVE-DECODE] 24/32 tok | Avg=2.63 tps | Hit=91.1% (LA:+1.9%) | NVMe=644.9 MB/s (15251.66 MB) | RSS=12325.5 MB
[LIVE-DECODE] 31/32 tok | Avg=2.74 tps | Hit=91.8% (LA:+1.9%) | NVMe=673.0 MB/s (16271.47 MB) | RSS=12325.5 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=OFF
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 6433.11 MB (3100/25088 exp = 12.36% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=12325.49 MB | Peak=12786.50 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (31 tok) : " a2,
ar,
ing,
e212
2

22
220
222
01
"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 32 Steps)]
   Logit Summary: AvgTop1Prob=10.0% | AvgMargin=0.730 | MinMargin=0.032
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.79 |  18.1% |     303 |   13.43 | 20733.09 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    9.55 |   2.3% |     467 |    8.54 |  682.98 |849 | 84 | 27 | 273239.0 |
   |    3 |      11 | ,              |   13.78 |  50.0% |     198 |   12.15 |  682.98 |  0 |  0 |  0 | 273239.0 |
   |    4 |     198 | \n             |   11.28 |  20.5% |     364 |    8.50 |  426.13 |419 | 51 | 10 | 241639.0 |
   |    5 |     277 | ar             |    9.86 |   2.9% |     261 |    9.53 |  460.22 |396 | 76 |  8 | 258139.0 |
   |    6 |      11 | ,              |    9.33 |   3.0% |      16 |    9.11 |  440.89 |423 | 44 | 13 | 259464.0 |
   |    7 |     198 | \n             |    9.90 |   8.3% |     286 |    7.83 |  407.90 |434 | 40 |  6 | 251814.0 |
   |    8 |     286 | ing            |    9.16 |   2.7% |     278 |    8.60 |  343.04 |447 | 30 |  3 | 162689.0 |
   |   14 |      17 | 2              |    9.40 |   4.0% |      15 |    8.88 |  455.93 |406 | 58 | 16 | 269139.0 |
   |   12 |      17 | 2              |    7.65 |   0.5% |     365 |    6.83 |  403.52 |432 | 43 |  5 | 231639.0 |
   |   25 |     198 | \n             |   10.81 |  12.2% |      15 |   10.44 |  382.48 |421 | 52 |  7 | 247689.0 |
   |   15 |     198 | \n             |   11.71 |  23.3% |      17 |   11.53 |  369.44 |428 | 46 |  6 | 214293.0 |
   |   29 |     198 | \n             |   11.56 |  29.2% |     271 |    9.34 |  298.57 |471 |  9 |  0 | 131518.0 |
   |   30 |      15 | 0              |    9.43 |   3.3% |      17 |    9.40 |  303.39 |471 |  9 |  0 | 141639.0 |
   |   31 |      16 | 1              |    9.74 |   4.3% |      17 |    9.38 |  321.82 |457 | 22 |  1 | 169964.0 |
   |   32 |     198 | \n             |   11.79 |  32.8% |      17 |    9.29 |  318.71 |456 | 24 |  0 | 179714.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 20.733s, TTFT=20733.09ms): Avg=3.09 | Min=3.09 | Max=3.09 tps
   Prefill Chunks (1): C1:64t/3.1tps/88%
   Decode  (31 tok, 11.304s): Avg=2.74 | Min=1.46 | Max=3.41 tps
   Latency (ms) : Min=292.83 | P10=302.33 | P25=304.36 | P50=323.62 | P75=403.52 | P90=455.93 | P95=682.98 | P99=682.98 | Max=682.98
   Mean/SD/Jitt : Mean=364.65ms | StdDev=97.14ms | Jitter=35.13ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/31
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (45600): RawRAM=40956 (89.82%) | Lookahead=885 (+1.94%) | ColdMiss=3759 (8.24%) | EFF HIT=91.76%
   Lookahead    : 3342 prefetched -> 895 consumed (26.8% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  950 |  653 |  83 | 214 | 77.5%| 500.32 | | L24 |  950 |  892 |   9 |  49 | 94.8%| 142.87 |
   | L01 |  950 |  806 |  50 |  94 | 90.1%| 424.58 | | L25 |  950 |  890 |   8 |  52 | 94.5%| 114.67 |
   | L02 |  950 |  829 |  15 | 106 | 88.8%| 459.89 | | L26 |  950 |  864 |  19 |  67 | 92.9%| 204.91 |
   | L03 |  950 |  892 |   1 |  57 | 94.0%| 554.57 | | L27 |  950 |  865 |  20 |  65 | 93.2%| 231.23 |
   | L04 |  950 |  886 |   4 |  60 | 93.7%| 215.82 | | L28 |  950 |  827 |  39 |  84 | 91.2%| 353.42 |
   | L05 |  950 |  864 |   7 |  79 | 91.7%| 291.38 | | L29 |  950 |  855 |  15 |  80 | 91.6%| 174.29 |
   | L06 |  950 |  866 |  17 |  67 | 92.9%| 238.75 | | L30 |  950 |  815 |  33 | 102 | 89.3%| 241.99 |
   | L07 |  950 |  869 |  19 |  62 | 93.5%| 154.98 | | L31 |  950 |  822 |  26 | 102 | 89.3%| 239.11 |
   | L08 |  950 |  902 |   8 |  40 | 95.8%| 103.34 | | L32 |  950 |  845 |  19 |  86 | 90.9%| 293.26 |
   | L09 |  950 |  892 |   5 |  53 | 94.4%| 100.85 | | L33 |  950 |  838 |  28 |  84 | 91.2%| 200.22 |
   | L10 |  950 |  882 |  12 |  56 | 94.1%| 123.27 | | L34 |  950 |  846 |  18 |  86 | 90.9%| 195.90 |
   | L11 |  950 |  895 |   5 |  50 | 94.7%| 128.25 | | L35 |  950 |  865 |  15 |  70 | 92.6%| 139.72 |
   | L12 |  950 |  868 |  15 |  67 | 92.9%| 248.14 | | L36 |  950 |  846 |  18 |  86 | 90.9%| 326.98 |
   | L13 |  950 |  858 |  19 |  73 | 92.3%| 157.01 | | L37 |  950 |  870 |  13 |  67 | 92.9%| 180.47 |
   | L14 |  950 |  837 |  31 |  82 | 91.4%| 275.12 | | L38 |  950 |  873 |   8 |  69 | 92.7%| 246.26 |
   | L15 |  950 |  847 |  19 |  84 | 91.2%| 289.50 | | L39 |  950 |  863 |  13 |  74 | 92.2%| 319.58 |
   | L16 |  950 |  866 |  11 |  73 | 92.3%| 193.63 | | L40 |  950 |  844 |  16 |  90 | 90.5%| 289.50 |
   | L17 |  950 |  866 |  15 |  69 | 92.7%| 218.07 | | L41 |  950 |  848 |  13 |  89 | 90.6%| 161.33 |
   | L18 |  950 |  858 |  22 |  70 | 92.6%| 223.71 | | L42 |  950 |  823 |  17 | 110 | 88.4%| 290.97 |
   | L19 |  950 |  874 |   8 |  68 | 92.8%| 154.13 | | L43 |  950 |  857 |  15 |  78 | 91.8%| 205.98 |
   | L20 |  950 |  832 |  27 |  91 | 90.4%| 221.83 | | L44 |  950 |  845 |  16 |  89 | 90.6%| 181.49 |
   | L21 |  950 |  823 |  31 |  96 | 89.9%| 421.09 | | L45 |  950 |  821 |  33 |  96 | 89.9%| 278.00 |
   | L22 |  950 |  883 |  12 |  55 | 94.2%| 214.31 | | L46 |  950 |  877 |   7 |  66 | 93.1%| 250.63 |
   | L23 |  950 |  870 |  15 |  65 | 93.2%| 145.48 | | L47 |  950 |  847 |  16 |  87 | 90.8%| 280.10 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 16271.47 MB (Load=4614.69 | Prefill=5963.42 | Warmup=0.00 | Decode=5693.35 MB)
   SSD Data/Token (Decode)      : Avg=183.657 MB/tok (Min=122.743 | P50=172.328 | P95=262.831 | Max=266.835 MB) | Prefill=93.178 MB/tok
   NVMe Batches / Requests      : 1617 Batches | 23931 Raw -> 23147 Merged (784 LBA Merges, Avg 719.8 KB/io)
   SSD I/O Size Histogram       : <64K=1835 | 64K-512K=5771 | 512K-2M=15107 | >2M=434
   SSD Read Bandwidth (Active)  : Min=10.44 | Avg=673.02 | Peak=11196.44 MB/s | WallAmort=507.89 MB/s
   OS Kernel I/O Verification   : Read=16291.44 MB | Write=0.00 MB | Syscalls=32649
   Sync Stall vs Async DMA      : SyncStall=10852.38 ms | AsyncOverlapped=15385.32 ms (58.6% Overlapped)
   RAM Traffic & Active BW      : 392.99 GB moved | Active=21.03 GB/s | WallAmort=12.27 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=20.73s (64.7%, 5963.42 MB SSD) | Decode=11.30s (35.3%, 5693.35 MB SSD)
   CPU Time & Utilization       : User=58.656s + Sys=5.203s (Wall=44.501s) | SysUtil=35.9% | ThrUtil=35.9% | 33.18 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   9195.70 ms (96796.8 us/tok | 28.70%)
   MoE AVX2 Q8 Expert Compute   :   8881.95 ms (93494.3 us/tok | 27.72%)
   Router + Lookahead Dispatch  :    504.08 ms ( 5306.1 us/tok |  1.57%)
   LM Head Output Projection    :    609.99 ms ( 6420.9 us/tok |  1.90%)
   Foreground NVMe Sync Stall   :  10852.38 ms (114235.6 us/tok | 33.87%)
   Unaccounted / OMP & Sampling :   1992.99 ms (20978.9 us/tok |  6.22%) | Total Wall=32037.09 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    77.52%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.72%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     8.96%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.78%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.02%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_qwen38_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7742.55 MB (3731 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=4.71 tps | Avg=4.71 tps | Hit=95.4% | NVMe=548.4 MB/s (13785.34 MB, QD=64) | RSS=13682.7 MB
[LIVE-PREFILL] 512/512 tok | Chunk=5.41 tps | Avg=5.03 tps | Hit=96.7% | NVMe=533.2 MB/s (17920.18 MB, QD=64) | RSS=13685.3 MB
[LIVE-DECODE] 8/128 tok | Avg=2.56 tps | Hit=96.7% (LA:+0.1%) | NVMe=555.3 MB/s (19340.95 MB) | RSS=13686.6 MB
[LIVE-DECODE] 16/128 tok | Avg=2.63 tps | Hit=96.8% (LA:+0.2%) | NVMe=580.0 MB/s (20887.47 MB) | RSS=13583.4 MB
[LIVE-DECODE] 24/128 tok | Avg=2.79 tps | Hit=96.8% (LA:+0.2%) | NVMe=608.1 MB/s (22214.54 MB) | RSS=13571.6 MB
[LIVE-DECODE] 32/128 tok | Avg=2.89 tps | Hit=96.9% (LA:+0.3%) | NVMe=631.7 MB/s (23333.58 MB) | RSS=13555.1 MB
[LIVE-DECODE] 40/128 tok | Avg=2.95 tps | Hit=96.9% (LA:+0.3%) | NVMe=656.7 MB/s (24558.62 MB) | RSS=13554.9 MB
[LIVE-DECODE] 48/128 tok | Avg=3.00 tps | Hit=97.0% (LA:+0.3%) | NVMe=680.2 MB/s (25714.20 MB) | RSS=13554.0 MB
[LIVE-DECODE] 56/128 tok | Avg=3.05 tps | Hit=97.0% (LA:+0.3%) | NVMe=703.9 MB/s (26849.16 MB) | RSS=13551.9 MB
[LIVE-DECODE] 64/128 tok | Avg=3.07 tps | Hit=97.0% (LA:+0.4%) | NVMe=723.8 MB/s (27892.78 MB) | RSS=13551.9 MB
[LIVE-DECODE] 72/128 tok | Avg=3.10 tps | Hit=97.1% (LA:+0.4%) | NVMe=745.6 MB/s (29007.18 MB) | RSS=13551.9 MB
[LIVE-DECODE] 80/128 tok | Avg=3.13 tps | Hit=97.1% (LA:+0.4%) | NVMe=768.2 MB/s (30183.58 MB) | RSS=13551.9 MB
[LIVE-DECODE] 88/128 tok | Avg=3.14 tps | Hit=97.2% (LA:+0.4%) | NVMe=789.0 MB/s (31307.03 MB) | RSS=13551.9 MB
[LIVE-DECODE] 96/128 tok | Avg=3.15 tps | Hit=97.2% (LA:+0.5%) | NVMe=810.0 MB/s (32428.42 MB) | RSS=13551.9 MB
[LIVE-DECODE] 104/128 tok | Avg=3.16 tps | Hit=97.2% (LA:+0.5%) | NVMe=830.5 MB/s (33567.13 MB) | RSS=13551.9 MB
[LIVE-DECODE] 112/128 tok | Avg=3.18 tps | Hit=97.3% (LA:+0.5%) | NVMe=851.4 MB/s (34759.05 MB) | RSS=13549.8 MB
[LIVE-DECODE] 120/128 tok | Avg=3.19 tps | Hit=97.3% (LA:+0.5%) | NVMe=871.6 MB/s (35921.99 MB) | RSS=13549.8 MB
[LIVE-DECODE] 127/128 tok | Avg=3.19 tps | Hit=97.3% (LA:+0.5%) | NVMe=887.8 MB/s (36910.92 MB) | RSS=13549.8 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=OFF
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7742.55 MB (3731/25088 exp = 14.87% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13549.85 MB | Peak=14136.88 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (127 tok) : "22222222010
ing{
2
22
3031223132
2732223302232022222331223330
224
2231222122222023022333333333932022222223323272032722223332232222"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 128 Steps)]
   Logit Summary: AvgTop1Prob=14.8% | AvgMargin=0.551 | MinMargin=0.005
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      17 | 2              |   11.64 |   9.2% |      18 |   11.26 | 101691.25 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |   10.56 |   7.0% |      16 |    9.87 |  624.38 |899 | 52 |  9 | 211703.5 |
   |    3 |      17 | 2              |   11.11 |  10.8% |      18 |   10.99 |  624.38 |  0 |  0 |  0 | 211703.5 |
   |    4 |      17 | 2              |   11.51 |  15.9% |      22 |   10.88 |  321.41 |449 | 28 |  3 | 200943.0 |
   |    5 |      17 | 2              |    9.67 |   3.5% |      16 |    9.10 |  305.14 |469 | 11 |  0 | 154418.0 |
   |    6 |      17 | 2              |   11.31 |  11.8% |      18 |   11.07 |  294.51 |473 |  7 |  0 | 160593.0 |
   |    7 |      17 | 2              |   10.93 |   8.5% |      18 |   10.14 |  312.94 |466 | 14 |  0 | 158743.0 |
   |    8 |      17 | 2              |   11.36 |  11.1% |      18 |   11.13 |  317.17 |468 | 12 |  0 | 172443.0 |
   |   13 |     286 | ing            |    8.50 |   1.4% |      68 |    7.85 |  462.75 |436 | 43 |  1 | 201443.0 |
   |   15 |     198 | \n             |    8.95 |   2.8% |      16 |    7.61 |  433.90 |435 | 38 |  7 | 230589.0 |
   |   16 |      17 | 2              |    8.90 |   1.7% |     286 |    8.88 |  370.42 |432 | 43 |  5 | 206414.0 |
   |   14 |      90 | {              |    7.71 |   0.7% |      64 |    7.56 |  359.45 |448 | 27 |  5 | 202589.0 |
   |  125 |      17 | 2              |   11.67 |  19.1% |      18 |   10.97 |  303.84 |472 |  8 |  0 | 146464.0 |
   |  126 |      17 | 2              |   12.31 |  21.8% |     198 |   11.75 |  298.58 |469 | 11 |  0 | 156939.0 |
   |  127 |      17 | 2              |   10.79 |  11.3% |      16 |   10.64 |  301.98 |478 |  2 |  0 | 127793.0 |
   |  128 |      17 | 2              |   12.08 |  19.1% |      18 |   11.55 |  306.45 |475 |  5 |  0 | 146193.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 101.691s, TTFT=101691.25ms): Avg=5.03 | Min=4.71 | Max=5.41 tps
   Prefill Chunks (2): C1:256t/4.7tps/95% | C2:256t/5.4tps/97%
   Decode  (127 tok, 39.754s): Avg=3.19 | Min=1.60 | Max=3.48 tps
   Latency (ms) : Min=287.01 | P10=291.92 | P25=296.69 | P50=303.35 | P75=314.23 | P90=324.69 | P95=345.73 | P99=624.38 | Max=624.38
   Mean/SD/Jitt : Mean=313.02ms | StdDev=45.41ms | Jitter=15.36ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/127
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (306720): RawRAM=297008 (96.83%) | Lookahead=1546 (+0.50%) | ColdMiss=8166 (2.66%) | EFF HIT=97.34%
   Lookahead    : 11519 prefetched -> 1556 consumed (13.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.8% | @64= 97.0% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 6390 | 5713 | 136 | 541 | 91.5%|1140.45 | | L24 | 6390 | 6289 |   5 |  96 | 98.5%| 218.07 |
   | L01 | 6390 | 6128 |  72 | 190 | 97.0%|1497.88 | | L25 | 6390 | 6293 |   7 |  90 | 98.6%| 231.23 |
   | L02 | 6390 | 6138 |  22 | 230 | 96.4%|1561.60 | | L26 | 6390 | 6162 |  49 | 179 | 97.2%| 524.49 |
   | L03 | 6390 | 6316 |   1 |  73 | 98.9%|2259.62 | | L27 | 6390 | 6254 |  20 | 116 | 98.2%| 485.01 |
   | L04 | 6390 | 6276 |   4 | 110 | 98.3%| 672.36 | | L28 | 6390 | 6134 |  49 | 207 | 96.8%| 699.32 |
   | L05 | 6390 | 6232 |  17 | 141 | 97.8%|1167.41 | | L29 | 6390 | 6186 |  36 | 168 | 97.4%| 512.79 |
   | L06 | 6390 | 6250 |  18 | 122 | 98.1%| 656.08 | | L30 | 6390 | 6097 |  57 | 236 | 96.3%| 554.57 |
   | L07 | 6390 | 6242 |  14 | 134 | 97.9%| 527.27 | | L31 | 6390 | 6117 |  60 | 213 | 96.7%| 594.90 |
   | L08 | 6390 | 6319 |   3 |  68 | 98.9%| 250.27 | | L32 | 6390 | 6185 |  37 | 168 | 97.4%| 742.55 |
   | L09 | 6390 | 6318 |   4 |  68 | 98.9%| 107.08 | | L33 | 6390 | 6137 |  54 | 199 | 96.9%| 475.34 |
   | L10 | 6390 | 6284 |   5 | 101 | 98.4%| 174.32 | | L34 | 6390 | 6044 |  86 | 260 | 95.9%| 639.55 |
   | L11 | 6390 | 6321 |   2 |  67 | 99.0%| 180.54 | | L35 | 6390 | 6198 |  32 | 160 | 97.5%| 452.29 |
   | L12 | 6390 | 6277 |   7 | 106 | 98.3%| 629.76 | | L36 | 6390 | 6197 |  31 | 162 | 97.5%| 471.02 |
   | L13 | 6390 | 6237 |  25 | 128 | 98.0%| 252.08 | | L37 | 6390 | 6166 |  35 | 189 | 97.0%| 513.21 |
   | L14 | 6390 | 6223 |  40 | 127 | 98.0%| 622.27 | | L38 | 6390 | 6240 |  16 | 134 | 97.9%| 697.44 |
   | L15 | 6390 | 6186 |  37 | 167 | 97.4%| 565.84 | | L39 | 6390 | 6196 |  27 | 167 | 97.4%| 932.42 |
   | L16 | 6390 | 6190 |  18 | 182 | 97.2%| 483.13 | | L40 | 6390 | 6184 |  38 | 168 | 97.4%| 876.03 |
   | L17 | 6390 | 6174 |  20 | 196 | 96.9%| 603.44 | | L41 | 6390 | 6210 |  12 | 168 | 97.4%| 387.48 |
   | L18 | 6390 | 6173 |  31 | 186 | 97.1%| 565.84 | | L42 | 6390 | 6059 |  83 | 248 | 96.1%| 733.18 |
   | L19 | 6390 | 6220 |  13 | 157 | 97.5%| 329.86 | | L43 | 6390 | 6107 |  43 | 240 | 96.2%| 821.04 |
   | L20 | 6390 | 6124 |  27 | 239 | 96.3%| 882.98 | | L44 | 6390 | 6069 |  60 | 261 | 95.9%| 792.24 |
   | L21 | 6390 | 6144 |  31 | 215 | 96.6%|1315.92 | | L45 | 6390 | 6048 |  90 | 252 | 96.1%| 957.89 |
   | L22 | 6390 | 6284 |   4 | 102 | 98.4%| 419.21 | | L46 | 6390 | 6264 |  16 | 110 | 98.3%| 864.26 |
   | L23 | 6390 | 6199 |  32 | 159 | 97.5%| 615.06 | | L47 | 6390 | 6204 |  20 | 166 | 97.4%| 548.93 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 36910.92 MB (Load=4614.69 | Prefill=13305.49 | Warmup=0.00 | Decode=18990.74 MB)
   SSD Data/Token (Decode)      : Avg=149.533 MB/tok (Min=79.311 | P50=146.620 | P95=190.053 | Max=225.185 MB) | Prefill=25.987 MB/tok
   NVMe Batches / Requests      : 5305 Batches | 70387 Raw -> 68529 Merged (1858 LBA Merges, Avg 551.5 KB/io)
   SSD I/O Size Histogram       : <64K=10481 | 64K-512K=15828 | 512K-2M=41772 | >2M=448
   SSD Read Bandwidth (Active)  : Min=5.41 | Avg=887.81 | Peak=11304.23 MB/s | WallAmort=260.96 MB/s
   OS Kernel I/O Verification   : Read=36931.05 MB | Write=0.00 MB | Syscalls=78044
   Sync Stall vs Async DMA      : SyncStall=23471.05 ms | AsyncOverlapped=32813.23 ms (58.3% Overlapped)
   RAM Traffic & Active BW      : 2226.07 GB moved | Active=20.18 GB/s | WallAmort=15.74 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=101.69s (71.9%, 13305.49 MB SSD) | Decode=39.75s (28.1%, 18990.74 MB SSD)
   CPU Time & Utilization       : User=375.984s + Sys=16.891s (Wall=153.439s) | SysUtil=64.0% | ThrUtil=64.0% | 59.21 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  54667.47 ms (85551.6 us/tok | 38.65%)
   MoE AVX2 Q8 Expert Compute   :  53217.92 ms (83283.1 us/tok | 37.62%)
   Router + Lookahead Dispatch  :   3136.15 ms ( 4907.9 us/tok |  2.22%)
   LM Head Output Projection    :   2420.83 ms ( 3788.5 us/tok |  1.71%)
   Foreground NVMe Sync Stall   :  23471.05 ms (36730.9 us/tok | 16.59%)
   Unaccounted / OMP & Sampling :   4531.52 ms ( 7091.6 us/tok |  3.20%) | Total Wall=141444.94 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    84.54%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.05%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.29%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.60%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.52%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_qwen38_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 15266.3ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\nu\n\n\nb2\n\n2\n\nu\n22'
[Stage 3] /v1/chat/completions (stream=true SSE) 3272.8ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_qwen38_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7815.19 MB (3766 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=4.76 tps | Avg=4.76 tps | Hit=95.4% | NVMe=548.9 MB/s (13785.34 MB, QD=64) | RSS=13755.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=5.64 tps | Avg=5.16 tps | Hit=96.7% | NVMe=545.3 MB/s (17920.18 MB, QD=64) | RSS=13755.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=5.84 tps | Avg=5.37 tps | Hit=97.2% | NVMe=554.0 MB/s (21711.33 MB, QD=64) | RSS=13754.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=5.69 tps | Avg=5.45 tps | Hit=97.4% | NVMe=548.7 MB/s (25450.53 MB, QD=64) | RSS=13756.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=5.81 tps | Avg=5.51 tps | Hit=97.6% | NVMe=555.8 MB/s (29051.61 MB, QD=64) | RSS=13756.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=5.79 tps | Avg=5.56 tps | Hit=97.7% | NVMe=559.3 MB/s (32660.55 MB, QD=64) | RSS=13756.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=5.64 tps | Avg=5.57 tps | Hit=97.7% | NVMe=561.8 MB/s (36300.10 MB, QD=64) | RSS=13756.8 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=5.60 tps | Avg=5.57 tps | Hit=97.8% | NVMe=557.7 MB/s (39779.71 MB, QD=64) | RSS=13758.1 MB
[LIVE-DECODE] 8/64 tok | Avg=2.18 tps | Hit=97.8% (LA:+0.0%) | NVMe=568.0 MB/s (41435.63 MB) | RSS=13730.3 MB
[LIVE-DECODE] 16/64 tok | Avg=2.50 tps | Hit=97.8% (LA:+0.1%) | NVMe=582.3 MB/s (42903.13 MB) | RSS=13713.5 MB
[LIVE-DECODE] 24/64 tok | Avg=2.66 tps | Hit=97.8% (LA:+0.1%) | NVMe=596.5 MB/s (44276.59 MB) | RSS=13684.2 MB
[LIVE-DECODE] 32/64 tok | Avg=2.75 tps | Hit=97.8% (LA:+0.1%) | NVMe=610.1 MB/s (45550.35 MB) | RSS=13668.1 MB
[LIVE-DECODE] 40/64 tok | Avg=2.82 tps | Hit=97.8% (LA:+0.1%) | NVMe=622.6 MB/s (46748.02 MB) | RSS=13664.0 MB
[LIVE-DECODE] 48/64 tok | Avg=2.84 tps | Hit=97.9% (LA:+0.1%) | NVMe=635.8 MB/s (48184.62 MB) | RSS=13656.3 MB
[LIVE-DECODE] 56/64 tok | Avg=2.84 tps | Hit=97.9% (LA:+0.1%) | NVMe=649.1 MB/s (49744.38 MB) | RSS=13632.0 MB
[LIVE-DECODE] 63/64 tok | Avg=2.86 tps | Hit=97.9% (LA:+0.2%) | NVMe=660.5 MB/s (50986.09 MB) | RSS=13628.1 MB

================================================================================
   APEX INFERENCE v1 — COMPACT HIGH-DENSITY 10-SECTION TELEMETRY REPORT
================================================================================
 [1. Model, Shards, Quantization & Execution Topology]
   Model / Arch / Quant         : Qwen3.8 Flash Next | qwen4exp (Qwen-3.8-Flash-Next) | Unsloth UD-IQ2_XS
   Dimensions / Kernel Path     : 48L, H=2560, V=248320 | AVX2+FMA+F16C Q8_K=ACTIVE
   MoE & Engine Topology        : 512 Exp/Lyr (Top-10, 25088 Total) | 4 Threads | QD=64 | Shards=4 | MTP=OFF
--------------------------------------------------------------------------------
 [2. Memory Pinning, Window-LRFU Cache, Staging Ring & KV/Recurrent State]
   GGUF Total / SSD Pool        : 73.22 GB GGUF | 68.69 GB Routed Experts on NVMe
   Pinned Dense / KV+State RAM  : Dense=4614.77 MB | KV/State=1035.09 MB (55296 B/tok)
   LRFU Cache / Staging Ring    : 7815.19 MB (3766/25088 exp = 15.01% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.68 MB | End=13628.11 MB | Peak=14214.25 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (63 tok) : "


u21
 22111012122502121113212727211221221
20
1
2[2212
12132112"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=9.1% | AvgMargin=0.533 | MinMargin=0.012
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     198 | \n             |    7.38 |   0.7% |      17 |    7.24 | 367396.90 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |    8.16 |   1.8% |      17 |    8.01 |  709.31 |848 | 99 | 13 | 246905.5 |
   |    3 |     198 | \n             |   11.22 |  32.9% |      16 |    8.68 |  709.31 |  0 |  0 |  0 | 246905.5 |
   |    4 |      84 | u              |    8.57 |   2.2% |     198 |    8.18 |  332.08 |434 | 46 |  0 | 188043.0 |
   |    5 |      17 | 2              |    8.16 |   0.8% |      18 |    8.11 |  382.22 |447 | 28 |  5 | 212589.0 |
   |    6 |      16 | 1              |    9.33 |   2.9% |      64 |    9.01 |  401.26 |450 | 29 |  1 | 189139.0 |
   |    7 |     198 | \n             |   10.64 |  10.7% |      16 |   10.09 |  394.14 |427 | 46 |  7 | 216547.0 |
   |    8 |     220 |                |   13.43 |  30.8% |     198 |   12.44 |  352.38 |437 | 41 |  2 | 182689.0 |
   |    9 |      17 | 2              |   10.57 |   7.3% |      16 |   10.29 |  385.72 |436 | 43 |  1 | 212839.0 |
   |   52 |      17 | 2              |   11.57 |  14.9% |      16 |   11.54 |  378.88 |429 | 45 |  6 | 227443.0 |
   |   45 |      17 | 2              |    9.48 |   4.7% |      16 |    9.41 |  373.28 |441 | 38 |  1 | 186314.0 |
   |   15 |      16 | 1              |   10.60 |  11.2% |      17 |   10.06 |  369.38 |440 | 36 |  4 | 213864.0 |
   |   61 |      17 | 2              |   10.66 |  13.6% |      16 |   10.09 |  328.73 |466 | 14 |  0 | 177689.0 |
   |   62 |      16 | 1              |    9.62 |   7.7% |      17 |    9.40 |  317.79 |472 |  8 |  0 | 145964.0 |
   |   63 |      16 | 1              |   11.23 |   5.0% |      17 |   11.07 |  333.97 |471 |  9 |  0 | 173814.0 |
   |   64 |      17 | 2              |   11.22 |   9.4% |      18 |    9.84 |  334.19 |463 | 17 |  0 | 194168.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 367.397s, TTFT=367396.90ms): Avg=5.57 | Min=4.76 | Max=5.84 tps
   Prefill Chunks (8): C1:256t/4.8tps/95% | C2:256t/5.6tps/97% | C3:256t/5.8tps/97% | C4:256t/5.7tps/97%
                       C5:256t/5.8tps/98% | C6:256t/5.8tps/98% | C7:256t/5.6tps/98% | C8:256t/5.6tps/98%
   Decode  (63 tok, 22.032s): Avg=2.86 | Min=1.41 | Max=3.20 tps
   Latency (ms) : Min=312.41 | P10=321.63 | P25=323.65 | P50=332.08 | P75=347.61 | P90=378.88 | P95=394.14 | P99=709.31 | Max=709.31
   Mean/SD/Jitt : Mean=349.71ms | StdDev=67.93ms | Jitter=18.86ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1013280): RawRAM=990167 (97.72%) | Lookahead=1553 (+0.15%) | ColdMiss=21560 (2.13%) | EFF HIT=97.87%
   Lookahead    : 6728 prefetched -> 1563 consumed (23.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.8% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21110 |18966 | 187 |1957 | 90.7%|3611.72 | | L24 |21110 |20937 |  10 | 163 | 99.2%| 385.38 |
   | L01 |21110 |20513 | 105 | 492 | 97.7%|1258.81 | | L25 |21110 |20940 |   6 | 164 | 99.2%| 323.34 |
   | L02 |21110 |20512 |  34 | 564 | 97.3%|1613.82 | | L26 |21110 |20591 |  32 | 487 | 97.7%|1107.25 |
   | L03 |21110 |21030 |   2 |  78 | 99.6%| 934.30 | | L27 |21110 |20840 |  23 | 247 | 98.8%| 629.76 |
   | L04 |21110 |20914 |  10 | 186 | 99.1%| 678.59 | | L28 |21110 |20477 |  45 | 588 | 97.2%|1381.71 |
   | L05 |21110 |20822 |  22 | 266 | 98.7%| 958.74 | | L29 |21110 |20661 |  34 | 415 | 98.0%| 720.21 |
   | L06 |21110 |20830 |  44 | 236 | 98.9%| 757.59 | | L30 |21110 |20286 |  32 | 792 | 96.2%|1264.70 |
   | L07 |21110 |20836 |  33 | 241 | 98.9%| 523.90 | | L31 |21110 |20383 |  38 | 689 | 96.7%|1129.30 |
   | L08 |21110 |21036 |   3 |  71 | 99.7%| 155.64 | | L32 |21110 |20594 |  22 | 494 | 97.7%|1139.21 |
   | L09 |21110 |21033 |   2 |  75 | 99.6%| 105.83 | | L33 |21110 |20494 |  19 | 597 | 97.2%| 956.45 |
   | L10 |21110 |20960 |   5 | 145 | 99.3%| 212.92 | | L34 |21110 |20230 |  45 | 835 | 96.0%|1365.53 |
   | L11 |21110 |21035 |   2 |  73 | 99.7%| 153.15 | | L35 |21110 |20653 |  22 | 435 | 97.9%| 713.01 |
   | L12 |21110 |20983 |   5 | 122 | 99.4%| 445.53 | | L36 |21110 |20591 |  37 | 482 | 97.7%| 881.54 |
   | L13 |21110 |20889 |  20 | 201 | 99.0%| 373.07 | | L37 |21110 |20542 |  22 | 546 | 97.4%|1112.89 |
   | L14 |21110 |20801 |  47 | 262 | 98.8%| 645.31 | | L38 |21110 |20772 |  18 | 320 | 98.5%| 936.18 |
   | L15 |21110 |20641 |  62 | 407 | 98.1%| 990.70 | | L39 |21110 |20593 |  32 | 485 | 97.7%|1173.05 |
   | L16 |21110 |20585 |  27 | 498 | 97.6%|1069.65 | | L40 |21110 |20688 |  36 | 386 | 98.2%|1079.05 |
   | L17 |21110 |20421 |  37 | 652 | 96.9%|1406.15 | | L41 |21110 |20687 |  12 | 411 | 98.1%| 685.64 |
   | L18 |21110 |20495 |  29 | 586 | 97.2%|1255.76 | | L42 |21110 |20363 |  62 | 685 | 96.8%|1284.86 |
   | L19 |21110 |20689 |  34 | 387 | 98.2%| 661.16 | | L43 |21110 |20283 |  37 | 790 | 96.3%|1387.13 |
   | L20 |21110 |20333 |  35 | 742 | 96.5%|1317.99 | | L44 |21110 |20282 |  48 | 780 | 96.3%|1323.75 |
   | L21 |21110 |20446 |  44 | 620 | 97.1%|1733.25 | | L45 |21110 |20333 |  66 | 711 | 96.6%|1390.01 |
   | L22 |21110 |20921 |  12 | 177 | 99.2%| 496.29 | | L46 |21110 |20894 |   9 | 207 | 99.0%| 643.87 |
   | L23 |21110 |20573 |  31 | 506 | 97.6%| 983.81 | | L47 |21110 |20789 |  14 | 307 | 98.5%| 829.03 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 50986.09 MB (Load=4614.69 | Prefill=35165.02 | Warmup=0.00 | Decode=11206.38 MB)
   SSD Data/Token (Decode)      : Avg=177.879 MB/tok (Min=134.706 | P50=178.407 | P95=211.472 | Max=241.119 MB) | Prefill=17.170 MB/tok
   NVMe Batches / Requests      : 3870 Batches | 119748 Raw -> 115601 Merged (4147 LBA Merges, Avg 451.6 KB/io)
   SSD I/O Size Histogram       : <64K=33825 | 64K-512K=21545 | 512K-2M=59746 | >2M=485
   SSD Read Bandwidth (Active)  : Min=10.52 | Avg=660.55 | Peak=10878.95 MB/s | WallAmort=130.93 MB/s
   OS Kernel I/O Verification   : Read=51006.63 MB | Write=0.00 MB | Syscalls=125114
   Sync Stall vs Async DMA      : SyncStall=58740.66 ms | AsyncOverlapped=68476.11 ms (53.8% Overlapped)
   RAM Traffic & Active BW      : 5635.43 GB moved | Active=17.89 GB/s | WallAmort=14.47 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=367.40s (94.3%, 35165.02 MB SSD) | Decode=22.03s (5.7%, 11206.38 MB SSD)
   CPU Time & Utilization       : User=1156.344s + Sys=21.062s (Wall=401.084s) | SysUtil=73.4% | ThrUtil=73.4% | 67.88 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 148633.50 ms (70409.0 us/tok | 38.17%)
   MoE AVX2 Q8 Expert Compute   : 165086.75 ms (78203.1 us/tok | 42.39%)
   Router + Lookahead Dispatch  :   9056.98 ms ( 4290.4 us/tok |  2.33%)
   LM Head Output Projection    :   1240.09 ms (  587.4 us/tok |  0.32%)
   Foreground NVMe Sync Stall   :  58740.66 ms (27826.0 us/tok | 15.08%)
   Unaccounted / OMP & Sampling :   6670.89 ms ( 3160.1 us/tok |  1.71%) | Total Wall=389428.86 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    90.78%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     0.99%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.66%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     3.83%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.74%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_qwen38_colibri_bench.log`
```text
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=230.0s) ===
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
resident weights loaded in 8.8s | RSS after load: 4.60 GB
[qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=230.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.1s / cutoff=230.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=230.0s
TTFT: 25.02 s (time to first token)
[qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
[qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
[qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes

PEAK RSS: 10.73 GB
Expert cache hit rate: 62.0% (hit=15849 miss=9733)
Speed: 0.66 tok/s (48.8s for 32 tokens)
[STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage
  [COMP-LIVE] Colibri-Qwen38: elapsed=60.1s / cutoff=230.0s

Reference: 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 
C engine : 220 248046 198 248045 74455 198 248068 198 760 1156 682 3106 1092 7701 310 381 264 7132 36412 2805 269 82987 886 314 5587 13 6558 728 22903 411 25 271 Text      :  <|im_end|>
<|im_start|>assistant
<think>
The user has sent what appears to be a garbled/corrupted string of characters. Let me analyze this:



Matching tokens: 0/32
=== [Colibri-Qwen38] Finished rc=1 elapsed=60.63s cancelled=False ===
```

### 📄 `12_qwen38_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 3.09 | 2.74 | 323.62 | 91.76% | 673.02 | 12786.50 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 5.03 | 3.19 | 303.35 | 97.34% | 887.81 | 14136.88 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 5.57 | 2.86 | 332.08 | 97.87% | 660.55 | 14214.25 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.66 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
