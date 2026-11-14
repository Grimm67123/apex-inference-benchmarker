<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#36 (Run ID `43603752340`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43603752340)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-14 14:47:48 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T14:13:40.847Z] ================================================================================
[2026-11-14T14:13:40.867Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T14:13:40.869Z] ================================================================================
[2026-11-14T14:13:44.997Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T14:13:45.335Z] --------------------------------------------------------------------------------
[2026-11-14T14:13:45.337Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 31 GB / 149.89 GB
[2026-11-14T14:13:45.339Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.02 GB / 150 GB
[2026-11-14T14:13:45.341Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.02 GB
[2026-11-14T14:13:45.342Z] --------------------------------------------------------------------------------
[2026-11-14T14:13:45.343Z]  [OK] Disk space verification passed: 178.02 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 916K Nov 14 14:14 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 916K Nov 14 14:14 build/apex.exe
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
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.50 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    232.19 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    946.04 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4906.68 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   5529.71 MB/s
   RND4K Q32T16 Read                  :    582.25 MB/s (  149057 IOPS)
   RND4K Q1T1  Read                   :    769.53 MB/s (Latency: 5.08 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     35.34 GB/s
   AVX2 256-bit Sequential Write BW   :     22.99 GB/s
   STREAM Triad (A = B + s*C) BW      :     26.54 GB/s
   Random Pointer-Chase Latency       :    111.77 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     42.29 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    142.33 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     16.64 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1330.23 tps | Avg=1330.23 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=60.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1265.95 tps | Avg=1297.30 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=60.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1094.28 tps | Avg=1221.74 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=61.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=966.24 tps | Avg=1145.98 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=61.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=862.99 tps | Avg=1075.45 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=61.7 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=781.06 tps | Avg=1011.88 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=61.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=719.72 tps | Avg=956.42 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=62.2 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=667.89 tps | Avg=907.42 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=62.4 MB
[LIVE-DECODE] 8/32 tok | Avg=50.07 tps | Hit=100.0% (LA:+0.0%) | NVMe=1796.5 MB/s (6.58 MB) | RSS=70.8 MB
[LIVE-DECODE] 16/32 tok | Avg=65.26 tps | Hit=100.0% (LA:+0.0%) | NVMe=1796.5 MB/s (6.58 MB) | RSS=70.8 MB
[LIVE-DECODE] 24/32 tok | Avg=73.35 tps | Hit=100.0% (LA:+0.0%) | NVMe=1796.5 MB/s (6.58 MB) | RSS=70.8 MB
[LIVE-DECODE] 31/32 tok | Avg=77.12 tps | Hit=100.0% (LA:+0.0%) | NVMe=1796.5 MB/s (6.58 MB) | RSS=70.8 MB

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
   Pinned Dense / KV+State RAM  : Dense=3.48 MB | KV/State=15.37 MB (3840 B/tok)
   LRFU Cache / Staging Ring    : 3.24 MB (67/64 exp = 104.69% pinned) | Staging=1.55 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=70.79 MB | Peak=78.26 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (31 tok) : "tok_55tok_55tok_55tok_55tok_246tok_251tok_199tok_55tok_246tok_71tok_246tok_251tok_55tok_55tok_251tok_251tok_21tok_55tok_246tok_55tok_119tok_251tok_251tok_246tok_119tok_55tok_55tok_55tok_55tok_199tok_55tok_199"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 32 Steps)]
   Logit Summary: AvgTop1Prob=95.4% | AvgMargin=12.467 | MinMargin=0.282
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2256.95 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |   30.80 | 48 |  0 |  0 |     0.0 |
   |    3 |      55 | tok_55         |  162.07 | 100.0% |     251 |  153.28 |   28.96 | 48 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  156.13 | 100.0% |     251 |  144.98 |   25.29 | 36 |  0 |  0 |     0.0 |
   |    5 |     246 | tok_246        |  161.71 | 100.0% |      55 |  147.08 |   24.93 | 36 |  0 |  0 |     0.0 |
   |    6 |     251 | tok_251        |  129.93 | 100.0% |     229 |  114.13 |    8.54 | 12 |  0 |  0 |     0.0 |
   |    7 |     199 | tok_199        |  140.67 |  66.3% |      71 |  139.99 |    8.26 | 12 |  0 |  0 |     0.0 |
   |    8 |      55 | tok_55         |  162.64 | 100.0% |     251 |  151.50 |    8.39 | 12 |  0 |  0 |     0.0 |
   |   17 |      21 | tok_21         |  162.32 |  57.0% |      86 |  162.03 |   26.23 | 36 |  0 |  0 |     0.0 |
   |    9 |     246 | tok_246        |  160.62 | 100.0% |      55 |  147.78 |   24.61 | 36 |  0 |  0 |     0.0 |
   |   25 |     119 | tok_119        |  190.28 | 100.0% |      55 |  146.04 |   23.66 | 36 |  0 |  0 |     0.0 |
   |   16 |     251 | tok_251        |  160.44 |  96.6% |      55 |  157.08 |    8.64 | 12 |  0 |  0 |     0.0 |
   |   29 |      55 | tok_55         |  170.19 | 100.0% |     251 |  153.56 |    8.22 | 12 |  0 |  0 |     0.0 |
   |   30 |     199 | tok_199        |  145.48 |  99.9% |      71 |  138.84 |   24.83 | 60 |  0 |  0 |     0.0 |
   |   31 |      55 | tok_55         |  163.52 | 100.0% |     251 |  152.05 |    8.37 | 12 |  0 |  0 |     0.0 |
   |   32 |     199 | tok_199        |  139.62 |  96.9% |      71 |  136.19 |    8.40 | 12 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.257s, TTFT=2256.95ms): Avg=907.42 | Min=667.89 | Max=1330.23 tps
   Prefill Chunks (8): C1:256t/1330.2tps/100% | C2:256t/1266.0tps/100% | C3:256t/1094.3tps/100% | C4:256t/966.2tps/100%
                       C5:256t/863.0tps/100% | C6:256t/781.1tps/100% | C7:256t/719.7tps/100% | C8:256t/667.9tps/100%
   Decode  (31 tok, 0.402s): Avg=77.12 | Min=32.46 | Max=122.79 tps
   Latency (ms) : Min=8.14 | P10=8.28 | P25=8.31 | P50=8.40 | P75=23.66 | P90=25.29 | P95=28.96 | P99=30.80 | Max=30.80
   Mean/SD/Jitt : Mean=12.97ms | StdDev=7.87ms | Jitter=5.20ms | Hist(<25/50/100/200/>200ms): 27/4/0/0/0
   MTP Head     : 0/12 draft tokens accepted (0.0% verified accept | Net 1.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (25188): RawRAM=25188 (100.00%) | Lookahead=0 (+0.00%) | ColdMiss=0 (0.00%) | EFF HIT=100.00%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 0 prefetched -> 0 consumed (0.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16=100.0% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L01 | 8396 | 8396 |   0 |   0 |100.0%|   0.00 | | L03 | 8396 | 8396 |   0 |   0 |100.0%|   0.00 |
   | L02 | 8396 | 8396 |   0 |   0 |100.0%|   0.00 | |     |      |      |     |     |      |        |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 6.58 MB (Load=6.58 | Prefill=0.00 | Warmup=0.00 | Decode=0.00 MB)
   SSD Data/Token (Decode)      : Avg=0.000 MB/tok (Min=0.000 | P50=0.000 | P95=0.000 | Max=0.000 MB) | Prefill=0.000 MB/tok
   NVMe Batches / Requests      : 1 Batches | 331 Raw -> 143 Merged (188 LBA Merges, Avg 47.1 KB/io)
   SSD I/O Size Histogram       : <64K=107 | 64K-512K=32 | 512K-2M=4 | >2M=0
   SSD Read Bandwidth (Active)  : Min=219.83 | Avg=1796.54 | Peak=4416.96 MB/s | WallAmort=2.47 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=7.88 MB | Syscalls=165
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=2.14 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.56 GB/s | WallAmort=0.54 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.26s (84.9%, 0.00 MB SSD) | Decode=0.40s (15.1%, 0.00 MB SSD)
   CPU Time & Utilization       : User=3.453s + Sys=0.453s (Wall=2.709s) | SysUtil=36.1% | ThrUtil=36.1% | 33.35 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2236.62 ms ( 1075.8 us/tok | 84.12%)
   MoE AVX2 Q8 Expert Compute   :    299.09 ms (  143.9 us/tok | 11.25%)
   Router + Lookahead Dispatch  :     61.06 ms (   29.4 us/tok |  2.30%)
   LM Head Output Projection    :      8.40 ms (    4.0 us/tok |  0.32%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     53.74 ms (   25.8 us/tok |  2.02%) | Total Wall=2658.91 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    20.26%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.89%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.10%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    76.04%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.71%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1796.84 tps | Avg=1796.84 tps | Hit=99.2% | NVMe=2223.2 MB/s (24.91 MB, QD=64) | RSS=85.7 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1939.57 tps | Avg=1865.48 tps | Hit=99.2% | NVMe=2923.1 MB/s (42.92 MB, QD=64) | RSS=85.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1806.69 tps | Avg=1845.46 tps | Hit=99.2% | NVMe=3364.8 MB/s (61.04 MB, QD=64) | RSS=86.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1661.19 tps | Avg=1795.66 tps | Hit=99.2% | NVMe=3670.3 MB/s (79.10 MB, QD=64) | RSS=86.5 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1552.08 tps | Avg=1741.02 tps | Hit=99.2% | NVMe=3883.3 MB/s (97.14 MB, QD=64) | RSS=87.0 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1455.76 tps | Avg=1685.96 tps | Hit=99.2% | NVMe=4038.3 MB/s (115.20 MB, QD=64) | RSS=87.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1371.45 tps | Avg=1632.47 tps | Hit=99.2% | NVMe=4157.4 MB/s (133.27 MB, QD=64) | RSS=87.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1253.67 tps | Avg=1573.06 tps | Hit=99.2% | NVMe=4278.9 MB/s (151.30 MB, QD=64) | RSS=88.2 MB
[LIVE-DECODE] 8/32 tok | Avg=42.96 tps | Hit=99.2% (LA:+0.0%) | NVMe=4096.8 MB/s (155.02 MB) | RSS=100.4 MB
[LIVE-DECODE] 16/32 tok | Avg=56.88 tps | Hit=99.1% (LA:+0.1%) | NVMe=3989.2 MB/s (157.50 MB) | RSS=100.4 MB
[LIVE-DECODE] 25/32 tok | Avg=72.39 tps | Hit=99.1% (LA:+0.2%) | NVMe=3897.1 MB/s (158.94 MB) | RSS=100.4 MB
[LIVE-DECODE] 33/32 tok | Avg=85.36 tps | Hit=99.1% (LA:+0.2%) | NVMe=3863.6 MB/s (160.48 MB) | RSS=100.4 MB

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
   LRFU Cache / Staging Ring    : 2.17 MB (40/80 exp = 50.00% pinned) | Staging=1.73 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=100.41 MB | Peak=111.56 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (33 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63qtok_194qtok_49qtok_229qtok_63qtok_223qtok_68qtok_66qtok_103qtok_65qtok_194qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63qtok_194qtok_49qtok_229qtok_63qtok_223qtok_68qtok_66qtok_103"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 34 Steps)]
   Logit Summary: AvgTop1Prob=96.9% | AvgMargin=7.559 | MinMargin=0.681
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   63.79 |  98.0% |     254 |   59.79 | 1301.92 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |   33.68 | 54 |  0 | 10 |  1279.0 |
   |    3 |      49 | qtok_49        |   64.76 |  99.9% |     177 |   57.43 |   35.51 | 51 |  8 |  5 |   755.5 |
   |    4 |     254 | qtok_254       |   51.96 |  89.9% |     229 |   49.75 |   28.27 | 47 |  0 |  1 |   303.0 |
   |    5 |      49 | qtok_49        |   69.73 |  99.7% |     177 |   63.67 |   30.17 | 44 |  0 |  4 |   469.5 |
   |    6 |     229 | qtok_229       |   50.30 |  93.3% |     254 |   47.41 |    9.57 | 15 |  1 |  0 |   230.5 |
   |    7 |      19 | qtok_19        |   81.50 |  96.5% |      63 |   78.17 |    9.46 | 12 |  4 |  0 |   119.5 |
   |    8 |      63 | qtok_63        |   86.30 |  99.6% |      19 |   80.66 |    9.43 | 15 |  1 |  0 |   119.5 |
   |   17 |      65 | qtok_65        |   59.40 |  95.1% |     209 |   56.43 |   30.45 | 36 |  2 | 10 |   913.5 |
   |    9 |     194 | qtok_194       |   63.76 | 100.0% |     118 |   41.99 |   30.15 | 44 |  0 |  4 |   525.0 |
   |   11 |     229 | qtok_229       |   52.77 |  76.0% |     194 |   51.58 |    9.48 | 16 |  0 |  0 |    64.0 |
   |   10 |      49 | qtok_49        |   73.57 | 100.0% |      81 |   53.37 |    9.40 | 15 |  1 |  0 |    64.0 |
   |   31 |     223 | qtok_223       |   72.59 |  99.9% |     159 |   65.60 |    5.03 | 48 |  7 |  9 |   192.9 |
   |   32 |      68 | qtok_68        |   72.59 |  99.9% |     159 |   65.60 |    5.03 |  0 |  0 |  0 |   192.9 |
   |   33 |      66 | qtok_66        |   72.59 |  99.9% |     159 |   65.60 |    5.03 |  0 |  0 |  0 |   192.9 |
   |   34 |     103 | qtok_103       |   72.59 |  99.9% |     159 |   65.60 |    5.03 |  0 |  0 |  0 |   192.9 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.302s, TTFT=1301.92ms): Avg=1573.06 | Min=1253.67 | Max=1939.57 tps
   Prefill Chunks (8): C1:256t/1796.8tps/99% | C2:256t/1939.6tps/99% | C3:256t/1806.7tps/99% | C4:256t/1661.2tps/99%
                       C5:256t/1552.1tps/99% | C6:256t/1455.8tps/99% | C7:256t/1371.4tps/99% | C8:256t/1253.7tps/99%
   Decode  (33 tok, 0.387s): Avg=85.36 | Min=28.16 | Max=211.38 tps
   Latency (ms) : Min=4.73 | P10=4.73 | P25=5.28 | P50=9.10 | P75=9.46 | P90=30.17 | P95=33.68 | P99=35.51 | Max=35.51
   Mean/SD/Jitt : Mean=11.72ms | StdDev=9.51ms | Jitter=3.82ms | Hist(<25/50/100/200/>200ms): 27/6/0/0/0
   MTP Head     : 9/17 draft tokens accepted (52.9% verified accept | Net 1.38x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33520): RawRAM=33151 (98.90%) | Lookahead=58 (+0.17%) | ColdMiss=311 (0.93%) | EFF HIT=99.07%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 59 prefetched -> 56 consumed (94.9% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.1% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8380 | 8314 |   0 |  66 | 99.2%|   3.58 | | L02 | 8380 | 8258 |  39 |  83 | 99.0%|   6.18 |
   | L01 | 8380 | 8286 |   9 |  85 | 99.0%|   5.09 | | L03 | 8380 | 8293 |  10 |  77 | 99.1%|   4.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 160.48 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=9.18 MB)
   SSD Data/Token (Decode)      : Avg=0.278 MB/tok (Min=0.062 | P50=0.225 | P95=0.892 | Max=1.249 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 128 Batches | 34879 Raw -> 458 Merged (34421 LBA Merges, Avg 358.8 KB/io)
   SSD I/O Size Histogram       : <64K=283 | 64K-512K=175 | 512K-2M=0 | >2M=0
   SSD Read Bandwidth (Active)  : Min=208.26 | Avg=3863.65 | Peak=7734.05 MB/s | WallAmort=95.04 MB/s
   OS Kernel I/O Verification   : Read=27.89 MB | Write=11.62 MB | Syscalls=480
   Sync Stall vs Async DMA      : SyncStall=12.23 ms | AsyncOverlapped=39.93 ms (76.5% Overlapped)
   RAM Traffic & Active BW      : 2.14 GB moved | Active=1.44 GB/s | WallAmort=1.26 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.30s (77.1%, 144.44 MB SSD) | Decode=0.39s (22.9%, 9.18 MB SSD)
   CPU Time & Utilization       : User=2.766s + Sys=0.609s (Wall=1.772s) | SysUtil=47.6% | ThrUtil=47.6% | 44.05 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1013.34 ms (  486.9 us/tok | 60.01%)
   MoE AVX2 Q8 Expert Compute   :    459.70 ms (  220.9 us/tok | 27.23%)
   Router + Lookahead Dispatch  :     80.40 ms (   38.6 us/tok |  4.76%)
   LM Head Output Projection    :      6.80 ms (    3.3 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :     12.23 ms (    5.9 us/tok |  0.72%)
   Unaccounted / OMP & Sampling :    116.04 ms (   55.8 us/tok |  6.87%) | Total Wall=1688.53 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.07%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.56%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.44%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    67.06%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.87%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] OpenAI-Compatible API Server on port 18081 (tests/synth_glm53_ud_iq2_xxs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 71, "completion_tokens": 8, "total_tokens": 79}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"tok_55tok_55tok_55tok_55tok_55tok_55"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"text": "tok_246tok_55tok_55tok_55tok_55tok_55", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "tok_55tok_55tok_55tok_55tok_55tok_55", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 69, "completion_tokens": 6, "total_tokens": 75}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "glm-5.3-flash-ud-iq2_xxs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "tok_55tok_55tok_55tok_55tok_55tok_55"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
[Concurrent Stress Test]: 4/4 parallel client requests completed cleanly.
[llama.cpp Server Parity]: /props, /tokenize, /detokenize, /v1/embeddings passed.
[GET /v1/telemetry]: {
  "model_name": "GLM-5.3-Flash-UD-IQ2_XXS-Synthetic",
  "architecture": "glm5-next (GLM-5.3-Flash)",
  "quantization": "Unsloth UD-IQ2_XXS",
  "mtp_enabled": false,
  "avx512_vnni_active": true,
  "prefix_cache_hits": 0,
  "prefix_tokens_reused": 0,
  "persistent_cache_saves": 9,
  "persistent_cache_loads": 0,
  "dense_pinned_ram_bytes": 3037760,
  "kv_cache_ram_bytes": 10797056,
  "kv_bytes_per_token": 2560,
  "expert_cache_ram_bytes": 2534400,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 514,
    "ttft_ms": 460.64,
    "avg_tps": 1115.84,
    "min_tps": 539.42,
    "max_tps": 1224.34
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 131.89,
    "min_tps": 120.49,
    "max_tps": 149.59,
    "p50_ms": 7.7,
    "p90_ms": 8.02,
    "p99_ms": 8.3,
    "mean_ms": 7.58,
    "jitter_ms": 0.21
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
    "bytes_per_token": 9892.92,
    "avg_mbs": 1696.64,
    "peak_mbs": 4770.99,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 1.72
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 483593728
  },
  "kernel_attribution_ms": {
    "dense_attention": 587.58,
    "moe_compute": 130.36,
    "router_lookahead": 17.13,
    "lm_head": 9.84,
    "unaccounted": 11.44
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 75.96,
    "ram_bandwidth_pinning": 2.02,
    "expert_cache_lrfu": 19.73,
    "lookahead_parallel_overlap": 1.97,
    "ssd_nvme_throughput": 0.32,
    "total": 100.0
  }
}

=== [TEST] OpenAI-Compatible API Server on port 18082 (tests/synth_qwen38_ud_iq2_xs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_49qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229qtok_19"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 71, "completion_tokens": 8, "total_tokens": 79}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"qtok_49qtok_49qtok_254qtok_49qtok_254qtok_49"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"text": "qtok_159qtok_112qtok_193qtok_128qtok_49qtok_254", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_49qtok_49qtok_254qtok_49qtok_254qtok_49", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 69, "completion_tokens": 6, "total_tokens": 75}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "qwen-3.8-flash-next-ud-iq2_xs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
[Concurrent Stress Test]: 4/4 parallel client requests completed cleanly.
[llama.cpp Server Parity]: /props, /tokenize, /detokenize, /v1/embeddings passed.
[GET /v1/telemetry]: {
  "model_name": "Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic",
  "architecture": "qwen4exp (Qwen-3.8-Flash-Next)",
  "quantization": "Unsloth UD-IQ2_XS",
  "mtp_enabled": false,
  "avx512_vnni_active": true,
  "prefix_cache_hits": 0,
  "prefix_tokens_reused": 0,
  "persistent_cache_saves": 9,
  "persistent_cache_loads": 0,
  "dense_pinned_ram_bytes": 3738208,
  "kv_cache_ram_bytes": 19173376,
  "kv_bytes_per_token": 13824,
  "expert_cache_ram_bytes": 1818624,
  "ssd_offloaded_expert_bytes": 3653632,
  "prefill": {
    "tokens": 514,
    "ttft_ms": 463.5,
    "avg_tps": 1108.95,
    "min_tps": 374.38,
    "max_tps": 1338.56
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 121.35,
    "min_tps": 109.83,
    "max_tps": 136.82,
    "p50_ms": 8.32,
    "p90_ms": 8.86,
    "p99_ms": 9.11,
    "mean_ms": 8.24,
    "jitter_ms": 0.23
  },
  "cache": {
    "raw_hit_rate_pct": 94.24,
    "effective_hit_rate_pct": 97.48,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 60007008,
    "prefill_bytes": 47063552,
    "warmup_bytes": 0,
    "decode_bytes": 7386624,
    "bytes_per_token": 108511.77,
    "avg_mbs": 2733.52,
    "peak_mbs": 6533.26,
    "sync_wait_ms": 8.03,
    "async_overlap_ms": 19.64
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 689928192
  },
  "kernel_attribution_ms": {
    "dense_attention": 442.78,
    "moe_compute": 246.0,
    "router_lookahead": 22.3,
    "lm_head": 9.17,
    "unaccounted": 56.61
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 71.8,
    "ram_bandwidth_pinning": 2.84,
    "expert_cache_lrfu": 17.01,
    "lookahead_parallel_overlap": 5.38,
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
 [Step 4.0] Host Hardware Benchmark + 1GB Uncached Disk Throttle Probe (C: & D:)
================================================================================
Host CPU: INTEL(R) XEON(R) PLATINUM 8573C | Cores=2 Threads=4 | RAM=15.99 GB

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.49 GB Available
   Active Drive Space : 150.00 GB Total / 146.92 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    231.91 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    945.69 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4900.97 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7573.70 MB/s
   RND4K Q32T16 Read                  :    572.83 MB/s (  146644 IOPS)
   RND4K Q1T1  Read                   :    808.70 MB/s (Latency: 4.83 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     45.80 GB/s
   AVX2 256-bit Sequential Write BW   :     34.82 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.79 GB/s
   Random Pointer-Chase Latency       :    112.83 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     48.59 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    132.35 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     16.62 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 31.00 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 164.94 MB/s (6.21s)
   Window #01 (116.0 MB in 0.50s):   231.86 MB/s (Uncached Direct Read)
   Window #02 (116.0 MB in 0.51s):   227.92 MB/s (Uncached Direct Read)
   Window #03 (108.0 MB in 0.51s):   212.77 MB/s (Uncached Direct Read)
   Window #04 (124.0 MB in 0.52s):   240.76 MB/s (Uncached Direct Read)
   Window #05 (120.0 MB in 0.51s):   235.70 MB/s (Uncached Direct Read)
   Window #06 (116.0 MB in 0.50s):   230.44 MB/s (Uncached Direct Read)
   Window #07 (116.0 MB in 0.52s):   225.12 MB/s (Uncached Direct Read)
   Window #08 (116.0 MB in 0.50s):   230.34 MB/s (Uncached Direct Read)
   Window #09 ( 92.0 MB in 0.40s):   228.12 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   229.26 MB/s (Min=212.77 | Max=240.76 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.92 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 238.10 MB/s (4.30s)
   Window #01 (124.0 MB in 0.51s):   242.99 MB/s (Uncached Direct Read)
   Window #02 (120.0 MB in 0.51s):   235.37 MB/s (Uncached Direct Read)
   Window #03 (124.0 MB in 0.52s):   238.53 MB/s (Uncached Direct Read)
   Window #04 (120.0 MB in 0.50s):   239.89 MB/s (Uncached Direct Read)
   Window #05 (120.0 MB in 0.50s):   239.96 MB/s (Uncached Direct Read)
   Window #06 (120.0 MB in 0.51s):   235.42 MB/s (Uncached Direct Read)
   Window #07 (120.0 MB in 0.50s):   239.91 MB/s (Uncached Direct Read)
   Window #08 (120.0 MB in 0.50s):   239.98 MB/s (Uncached Direct Read)
   Window #09 ( 56.0 MB in 0.24s):   233.53 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   238.69 MB/s (Min=233.53 | Max=242.99 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: qwen38 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (0.010 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 100.00% (0.01/0.01 GB) @ 25.8 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (43.792 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  11.42% (5.00/43.79 GB) @ 215.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  22.84% (10.00/43.79 GB) @ 133.8 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  34.25% (15.00/43.79 GB) @ 145.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  45.67% (20.00/43.79 GB) @ 140.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  57.09% (25.00/43.79 GB) @ 122.2 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  68.51% (30.00/43.79 GB) @ 132.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  79.92% (35.00/43.79 GB) @ 136.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  91.34% (40.00/43.79 GB) @ 141.2 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf: 100.00% (43.79/43.79 GB) @ 145.1 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (26.822 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  18.64% (5.00/26.82 GB) @ 148.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  37.28% (10.00/26.82 GB) @ 185.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  55.92% (15.00/26.82 GB) @ 190.2 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  74.57% (20.00/26.82 GB) @ 187.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  93.21% (25.00/26.82 GB) @ 188.2 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf: 100.00% (26.82/26.82 GB) @ 189.6 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/MTP/mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (2.595 GB) -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Sequential Non-Truncate)
  [DL] mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 100.00% (2.60/2.60 GB) @ 140.0 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=78,618,661,594 (73.22 GB) | Elapsed=474.14s
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
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=8026.86 MB (3868 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=1.40 tps | Avg=1.40 tps | Hit=88.2% | NVMe=238.4 MB/s (10527.38 MB, QD=64) | RSS=13808.9 MB
[LIVE-DECODE] 1/32 tok | Avg=0.62 tps | Hit=88.4% (LA:+0.2%) | NVMe=239.2 MB/s (10840.78 MB) | RSS=13972.1 MB
[LIVE-DECODE] 8/32 tok | Avg=0.90 tps | Hit=89.4% (LA:+0.8%) | NVMe=250.3 MB/s (12377.57 MB) | RSS=13939.9 MB
[LIVE-DECODE] 16/32 tok | Avg=1.09 tps | Hit=90.5% (LA:+0.9%) | NVMe=269.0 MB/s (13663.76 MB) | RSS=13930.9 MB
[LIVE-DECODE] 24/32 tok | Avg=1.15 tps | Hit=91.3% (LA:+1.1%) | NVMe=285.5 MB/s (15022.82 MB) | RSS=13934.7 MB
[LIVE-DECODE] 32/32 tok | Avg=1.14 tps | Hit=92.3% (LA:+1.2%) | NVMe=295.5 MB/s (16034.43 MB) | RSS=13944.3 MB

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
   LRFU Cache / Staging Ring    : 8026.86 MB (3868/25088 exp = 15.42% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=13944.31 MB | Peak=14056.30 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : "25  

2





u


22
22
21222
2121"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=20.3% | AvgMargin=1.316 | MinMargin=0.005
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      17 | 2              |    9.31 |   2.7% |     350 |    9.23 | 45594.85 |  0 |  0 |  0 |     0.0 |
   |    2 |      20 | 5              |    9.48 |   2.8% |      22 |    9.31 | 1606.08 |411 | 54 | 15 | 320914.0 |
   |    3 |     220 |                |   11.82 |  14.5% |     264 |   11.73 | 1423.99 |403 | 62 | 15 | 316868.0 |
   |    4 |     220 |                |   11.57 |  15.6% |     198 |   10.03 | 1356.26 |424 | 47 |  9 | 279218.0 |
   |    5 |     198 | \n             |   13.28 |  58.0% |     539 |    9.97 |  949.67 |462 | 18 |  0 | 214639.0 |
   |    6 |     198 | \n             |   10.52 |   9.8% |      84 |    8.46 | 1057.63 |440 | 38 |  2 | 221572.0 |
   |    7 |      17 | 2              |    8.72 |   1.2% |      64 |    8.52 |  780.26 |461 | 19 |  0 | 166293.0 |
   |    8 |     198 | \n             |   13.23 |  57.3% |     264 |    9.99 |  826.87 |449 | 31 |  0 | 214918.0 |
   |   15 |     198 | \n             |   10.62 |  14.0% |      17 |    8.27 |  933.36 |450 | 27 |  3 | 230089.0 |
   |   26 |      17 | 2              |   12.47 |  23.4% |      16 |   12.03 |  867.04 |450 | 27 |  3 | 233014.0 |
   |    9 |     198 | \n             |   15.12 |  91.3% |     271 |    9.59 |  853.88 |464 | 16 |  0 | 160164.0 |
   |   28 |      17 | 2              |   12.72 |  19.0% |      24 |   12.34 |  822.08 |457 | 23 |  0 | 194243.0 |
   |   30 |      17 | 2              |   11.66 |  15.1% |      15 |   10.60 |  834.11 |472 |  8 |  0 | 162364.0 |
   |   31 |      16 | 1              |   10.29 |   5.2% |      17 |   10.28 | 1034.41 |3321 |  1 | 38 | 20903.3 |
   |   32 |      17 | 2              |   10.29 |   5.2% |      17 |   10.28 | 1034.41 |  0 |  0 |  0 | 20903.3 |
   |   33 |      16 | 1              |   10.29 |   5.2% |      17 |   10.28 | 1034.41 |  0 |  0 |  0 | 20903.3 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 45.595s, TTFT=45594.85ms): Avg=1.40 | Min=1.40 | Max=1.40 tps
   Prefill Chunks (1): C1:64t/1.4tps/88%
   Decode  (32 tok, 27.998s): Avg=1.14 | Min=0.62 | Max=1.55 tps
   Latency (ms) : Min=643.75 | P10=687.50 | P25=734.32 | P50=820.66 | P75=949.67 | P90=1057.63 | P95=1423.99 | P99=1606.08 | Max=1606.08
   Mean/SD/Jitt : Mean=874.93ms | StdDev=221.26ms | Jitter=88.65ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 2/3 draft tokens accepted (66.7% verified accept | Net 1.07x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (48000): RawRAM=43738 (91.12%) | Lookahead=557 (+1.16%) | ColdMiss=3705 (7.72%) | EFF HIT=92.28%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 2668 prefetched -> 847 consumed (31.7% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1000 |  729 |  52 | 219 | 78.1%| 454.83 | | L24 | 1000 |  946 |   8 |  46 | 95.4%| 139.11 |
   | L01 | 1000 |  869 |  38 |  93 | 90.7%| 381.01 | | L25 | 1000 |  936 |  11 |  53 | 94.7%| 142.87 |
   | L02 | 1000 |  882 |  10 | 108 | 89.2%| 377.34 | | L26 | 1000 |  917 |  12 |  71 | 92.9%| 176.71 |
   | L03 | 1000 |  943 |   0 |  57 | 94.3%| 469.97 | | L27 | 1000 |  925 |  10 |  65 | 93.5%| 236.87 |
   | L04 | 1000 |  938 |   3 |  59 | 94.1%| 273.93 | | L28 | 1000 |  900 |  17 |  83 | 91.7%| 253.78 |
   | L05 | 1000 |  921 |   9 |  70 | 93.0%| 306.42 | | L29 | 1000 |  917 |   8 |  75 | 92.5%| 148.36 |
   | L06 | 1000 |  921 |  13 |  66 | 93.4%| 227.47 | | L30 | 1000 |  887 |  12 | 101 | 89.9%| 190.14 |
   | L07 | 1000 |  921 |  19 |  60 | 94.0%| 143.19 | | L31 | 1000 |  893 |  13 |  94 | 90.6%| 185.82 |
   | L08 | 1000 |  950 |  10 |  40 | 96.0%|  92.14 | | L32 | 1000 |  918 |   5 |  77 | 92.3%| 189.87 |
   | L09 | 1000 |  940 |   7 |  53 | 94.7%| 115.80 | | L33 | 1000 |  912 |   9 |  79 | 92.1%| 136.84 |
   | L10 | 1000 |  933 |  11 |  56 | 94.4%| 104.59 | | L34 | 1000 |  914 |   8 |  78 | 92.2%| 145.48 |
   | L11 | 1000 |  946 |   3 |  51 | 94.9%| 133.23 | | L35 | 1000 |  922 |  10 |  68 | 93.2%| 123.88 |
   | L12 | 1000 |  921 |  12 |  67 | 93.3%| 212.43 | | L36 | 1000 |  913 |  10 |  77 | 92.3%| 168.53 |
   | L13 | 1000 |  913 |  13 |  74 | 92.6%| 151.25 | | L37 | 1000 |  921 |   6 |  73 | 92.7%| 171.07 |
   | L14 | 1000 |  907 |  16 |  77 | 92.3%| 169.97 | | L38 | 1000 |  932 |   4 |  64 | 93.6%| 218.07 |
   | L15 | 1000 |  909 |  15 |  76 | 92.4%| 212.43 | | L39 | 1000 |  923 |   8 |  69 | 93.1%| 221.83 |
   | L16 | 1000 |  922 |   4 |  74 | 92.6%| 167.31 | | L40 | 1000 |  907 |   4 |  89 | 91.1%| 250.02 |
   | L17 | 1000 |  923 |   8 |  69 | 93.1%| 167.31 | | L41 | 1000 |  901 |   9 |  90 | 91.0%| 146.92 |
   | L18 | 1000 |  913 |  15 |  72 | 92.8%| 191.75 | | L42 | 1000 |  877 |  16 | 107 | 89.3%| 246.31 |
   | L19 | 1000 |  923 |  11 |  66 | 93.4%| 145.48 | | L43 | 1000 |  903 |   9 |  88 | 91.2%| 198.78 |
   | L20 | 1000 |  890 |  14 |  96 | 90.4%| 190.14 | | L44 | 1000 |  892 |  16 |  92 | 90.8%| 167.09 |
   | L21 | 1000 |  896 |  12 |  92 | 90.8%| 381.62 | | L45 | 1000 |  885 |  17 |  98 | 90.2%| 226.15 |
   | L22 | 1000 |  933 |  13 |  54 | 94.6%| 187.99 | | L46 | 1000 |  918 |   8 |  74 | 92.6%| 236.23 |
   | L23 | 1000 |  929 |   9 |  62 | 93.8%| 161.33 | | L47 | 1000 |  907 |  10 |  83 | 91.7%| 229.35 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 16034.43 MB (Load=4614.69 | Prefill=5912.69 | Warmup=0.00 | Decode=5507.05 MB)
   SSD Data/Token (Decode)      : Avg=172.095 MB/tok (Min=20.413 | P50=174.578 | P95=309.441 | Max=313.393 MB) | Prefill=92.386 MB/tok
   NVMe Batches / Requests      : 1383 Batches | 21827 Raw -> 21088 Merged (739 LBA Merges, Avg 778.6 KB/io)
   SSD I/O Size Histogram       : <64K=1915 | 64K-512K=5005 | 512K-2M=13735 | >2M=433
   SSD Read Bandwidth (Active)  : Min=4.75 | Avg=295.53 | Peak=5132.09 MB/s | WallAmort=217.88 MB/s
   OS Kernel I/O Verification   : Read=16054.40 MB | Write=166.92 MB | Syscalls=30594
   Sync Stall vs Async DMA      : SyncStall=25594.10 ms | AsyncOverlapped=35331.72 ms (58.0% Overlapped)
   RAM Traffic & Active BW      : 410.37 GB moved | Active=10.50 GB/s | WallAmort=5.58 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=45.59s (62.0%, 5912.69 MB SSD) | Decode=28.00s (38.0%, 5507.05 MB SSD)
   CPU Time & Utilization       : User=130.047s + Sys=10.203s (Wall=101.011s) | SysUtil=34.7% | ThrUtil=34.7% | 32.11 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  19882.50 ms (207109.3 us/tok | 27.02%)
   MoE AVX2 Q8 Expert Compute   :  16875.53 ms (175786.7 us/tok | 22.93%)
   Router + Lookahead Dispatch  :   1087.50 ms (11328.2 us/tok |  1.48%)
   LM Head Output Projection    :   2326.49 ms (24234.2 us/tok |  3.16%)
   Foreground NVMe Sync Stall   :  25594.10 ms (266605.2 us/tok | 34.78%)
   Unaccounted / OMP & Sampling :   7826.54 ms (81526.4 us/tok | 10.63%) | Total Wall=73592.64 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    80.76%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.41%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     8.75%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.28%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.80%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 103s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 14.21 GB Available
   Active Drive Space : 150.00 GB Total / 75.97 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    230.04 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    946.31 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4752.68 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7488.05 MB/s
   RND4K Q32T16 Read                  :    481.51 MB/s (  123266 IOPS)
   RND4K Q1T1  Read                   :    742.25 MB/s (Latency: 5.26 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     43.52 GB/s
   AVX2 256-bit Sequential Write BW   :     30.43 GB/s
   STREAM Triad (A = B + s*C) BW      :     35.37 GB/s
   Random Pointer-Chase Latency       :    112.66 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     45.92 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    156.15 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     14.88 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=4.86 tps | Avg=4.86 tps | Hit=92.8% | NVMe=255.8 MB/s (5242.36 MB, QD=64) | RSS=14403.3 MB

 >>> [Apex-Model-Response] !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   LRFU Cache / Staging Ring    : 8668.09 MB (4177/25088 exp = 16.65% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=14575.54 MB | Peak=14706.40 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (63 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=0.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 18734.76 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  911.75 |474 |  6 |  0 | 72889.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  656.79 |478 |  2 |  0 | 57064.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  667.68 |480 |  0 |  0 | 51064.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  645.02 |479 |  1 |  0 | 54064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  652.36 |480 |  0 |  0 | 52339.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  625.56 |480 |  0 |  0 | 51064.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  626.40 |480 |  0 |  0 | 51064.0 |
   |   17 |       0 | !              |     nan | 100.0% |       1 |     nan |  254.99 |228 |  0 |  0 |    64.0 |
   |   18 |       0 | !              |     nan | 100.0% |       1 |     nan |  254.99 |  0 |  0 |  0 |    64.0 |
   |   19 |       0 | !              |     nan | 100.0% |       1 |     nan |  254.99 |  0 |  0 |  0 |    64.0 |
   |   20 |       0 | !              |     nan | 100.0% |       1 |     nan |  254.99 |  0 |  0 |  0 |    64.0 |
   |   61 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.37 |228 |  0 |  0 |    64.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.37 |  0 |  0 |  0 |    64.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.37 |  0 |  0 |  0 |    64.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.37 |  0 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 18.735s, TTFT=18734.76ms): Avg=4.86 | Min=4.86 | Max=4.86 tps
   Prefill Chunks (1): C1:91t/4.9tps/93%
   Decode  (63 tok, 18.518s): Avg=3.40 | Min=1.10 | Max=4.18 tps
   Latency (ms) : Min=239.37 | P10=240.02 | P25=243.11 | P50=244.06 | P75=250.44 | P90=625.56 | P95=652.36 | P99=911.75 | Max=911.75
   Mean/SD/Jitt : Mean=293.94ms | StdDev=141.38ms | Jitter=12.14ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
   MTP Head     : 42/42 draft tokens accepted (100.0% verified accept | Net 3.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (11964): RawRAM=11564 (96.66%) | Lookahead=9 (+0.08%) | ColdMiss=391 (3.27%) | EFF HIT=96.73%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 29 prefetched -> 16 consumed (55.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 95.9% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1266 |   9 | 265 | 82.8%| 461.57 | | L24 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L01 |  442 |  362 |   0 |  80 | 81.9%| 115.80 | | L25 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L02 |  217 |  216 |   0 |   1 | 99.5%|   1.68 | | L26 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L03 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L27 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L04 |  217 |  216 |   0 |   1 | 99.5%|   2.08 | | L28 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L05 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L29 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L06 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L30 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L07 |  217 |  216 |   0 |   1 | 99.5%|   1.68 | | L31 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L08 |  217 |  216 |   0 |   1 | 99.5%|   1.25 | | L32 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L09 |  217 |  216 |   0 |   1 | 99.5%|   1.25 | | L33 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L10 |  217 |  216 |   0 |   1 | 99.5%|   1.25 | | L34 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L11 |  217 |  216 |   0 |   1 | 99.5%|   1.25 | | L35 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L12 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L36 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L13 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L37 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L14 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L38 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L15 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L39 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L16 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L40 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L17 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L41 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L18 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L42 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L19 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L43 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L20 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L44 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L21 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L45 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L22 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L46 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L23 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L47 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 5626.28 MB (Load=4614.69 | Prefill=627.67 | Warmup=0.00 | Decode=383.92 MB)
   SSD Data/Token (Decode)      : Avg=6.094 MB/tok (Min=0.062 | P50=0.062 | P95=55.727 | Max=71.181 MB) | Prefill=6.897 MB/tok
   NVMe Batches / Requests      : 96 Batches | 5021 Raw -> 4009 Merged (1012 LBA Merges, Avg 1437.1 KB/io)
   SSD I/O Size Histogram       : <64K=2002 | 64K-512K=994 | 512K-2M=608 | >2M=405
   SSD Read Bandwidth (Active)  : Min=4.77 | Avg=271.38 | Peak=11935.93 MB/s | WallAmort=151.03 MB/s (100.0% of 230.0 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=6134.69 MB | Write=300.73 MB | Syscalls=21064
   Sync Stall vs Async DMA      : SyncStall=1580.36 ms | AsyncOverlapped=1781.16 ms (53.0% Overlapped)
   RAM Traffic & Active BW      : 372.18 GB moved | Active=11.28 GB/s (31.9% STREAM) | WallAmort=9.99 GB/s (Max=35.37 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=18.73s (50.3%, 627.67 MB SSD) | Decode=18.52s (49.7%, 383.92 MB SSD)
   CPU Time & Utilization       : User=112.234s + Sys=7.625s (Wall=67.168s) | SysUtil=44.6% | ThrUtil=44.6% | 69.66 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  26308.50 ms (170834.4 us/tok | 70.62%)
   MoE AVX2 Q8 Expert Compute   :   4251.38 ms (27606.4 us/tok | 11.41%)
   Router + Lookahead Dispatch  :   1585.84 ms (10297.7 us/tok |  4.26%)
   LM Head Output Projection    :   2422.85 ms (15732.8 us/tok |  6.50%)
   Foreground NVMe Sync Stall   :   1580.36 ms (10262.1 us/tok |  4.24%)
   Unaccounted / OMP & Sampling :   1103.77 ms ( 7167.3 us/tok |  2.96%) | Total Wall=37252.70 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    75.41%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.21%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     7.92%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    11.72%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.74%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=8614.14 MB (4151 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=5.64 tps | Avg=5.64 tps | Hit=97.5% | NVMe=262.9 MB/s (5225.38 MB, QD=64) | RSS=14376.2 MB
[LIVE-PREFILL] 512/512 tok | Chunk=5.81 tps | Avg=5.72 tps | Hit=98.0% | NVMe=274.0 MB/s (5615.71 MB, QD=64) | RSS=14465.4 MB
[LIVE-DECODE] 11/128 tok | Avg=1.96 tps | Hit=98.2% (LA:+0.2%) | NVMe=290.4 MB/s (5988.84 MB) | RSS=14524.7 MB
[LIVE-DECODE] 19/128 tok | Avg=2.50 tps | Hit=98.2% (LA:+0.2%) | NVMe=290.4 MB/s (5991.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 27/128 tok | Avg=2.82 tps | Hit=98.3% (LA:+0.2%) | NVMe=290.5 MB/s (5991.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 35/128 tok | Avg=3.01 tps | Hit=98.3% (LA:+0.2%) | NVMe=290.5 MB/s (5992.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 43/128 tok | Avg=3.16 tps | Hit=98.3% (LA:+0.2%) | NVMe=290.5 MB/s (5992.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 51/128 tok | Avg=3.27 tps | Hit=98.3% (LA:+0.2%) | NVMe=290.5 MB/s (5993.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 59/128 tok | Avg=3.35 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.5 MB/s (5993.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 67/128 tok | Avg=3.42 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.6 MB/s (5994.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 75/128 tok | Avg=3.47 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.6 MB/s (5994.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 83/128 tok | Avg=3.51 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.6 MB/s (5995.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 91/128 tok | Avg=3.54 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.6 MB/s (5995.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 99/128 tok | Avg=3.58 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.6 MB/s (5996.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 107/128 tok | Avg=3.60 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.7 MB/s (5996.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 115/128 tok | Avg=3.62 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.7 MB/s (5997.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 123/128 tok | Avg=3.64 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.7 MB/s (5997.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 127/128 tok | Avg=3.65 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.7 MB/s (5997.77 MB) | RSS=14524.7 MB

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
   LRFU Cache / Staging Ring    : 8614.14 MB (4151/25088 exp = 16.55% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=14524.68 MB | Peak=14718.59 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (127 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 128 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=0.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 89448.27 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  851.74 |474 |  6 |  0 | 74164.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  621.66 |480 |  0 |  0 | 52339.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  622.37 |480 |  0 |  0 | 51064.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  623.69 |480 |  0 |  0 | 51064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  622.34 |480 |  0 |  0 | 51064.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  634.27 |480 |  0 |  0 | 51064.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  625.28 |480 |  0 |  0 | 51064.0 |
   |   73 |       0 | !              |     nan | 100.0% |       1 |     nan |  264.42 |228 |  0 |  0 |    64.0 |
   |   74 |       0 | !              |     nan | 100.0% |       1 |     nan |  264.42 |  0 |  0 |  0 |    64.0 |
   |   75 |       0 | !              |     nan | 100.0% |       1 |     nan |  264.42 |  0 |  0 |  0 |    64.0 |
   |   76 |       0 | !              |     nan | 100.0% |       1 |     nan |  264.42 |  0 |  0 |  0 |    64.0 |
   |  125 |       0 | !              |     nan | 100.0% |       1 |     nan |  253.03 |228 |  0 |  0 |    64.0 |
   |  126 |       0 | !              |     nan | 100.0% |       1 |     nan |  253.03 |  0 |  0 |  0 |    64.0 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  253.03 |  0 |  0 |  0 |    64.0 |
   |  128 |       0 | !              |     nan | 100.0% |       1 |     nan |  253.03 |  0 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 89.448s, TTFT=89448.27ms): Avg=5.72 | Min=5.64 | Max=5.81 tps
   Prefill Chunks (2): C1:256t/5.6tps/98% | C2:256t/5.8tps/98%
   Decode  (127 tok, 34.759s): Avg=3.65 | Min=1.17 | Max=4.08 tps
   Latency (ms) : Min=245.37 | P10=247.28 | P25=249.32 | P50=251.00 | P75=253.03 | P90=255.56 | P95=621.66 | P99=634.27 | Max=851.74
   Mean/SD/Jitt : Mean=273.69ms | StdDev=94.58ms | Jitter=5.79ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/127
   MTP Head     : 90/90 draft tokens accepted (100.0% verified accept | Net 3.43x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (39402): RawRAM=38755 (98.36%) | Lookahead=65 (+0.16%) | ColdMiss=582 (1.48%) | EFF HIT=98.52%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 24 prefetched -> 29 consumed (120.8% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 98.2% | @64= 98.4% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 6390 | 5809 |  65 | 516 | 91.9%| 879.35 | | L24 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L01 |  720 |  700 |   0 |  20 | 97.2%|  38.60 | | L25 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L02 |  702 |  701 |   0 |   1 | 99.9%|   1.68 | | L26 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L03 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L27 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L04 |  702 |  701 |   0 |   1 | 99.9%|   2.08 | | L28 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L05 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L29 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L06 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L30 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L07 |  702 |  701 |   0 |   1 | 99.9%|   1.68 | | L31 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L08 |  702 |  701 |   0 |   1 | 99.9%|   1.25 | | L32 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L09 |  702 |  701 |   0 |   1 | 99.9%|   1.25 | | L33 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L10 |  702 |  701 |   0 |   1 | 99.9%|   1.25 | | L34 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L11 |  702 |  701 |   0 |   1 | 99.9%|   1.25 | | L35 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L12 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L36 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L13 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L37 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L14 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L38 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L15 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L39 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L16 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L40 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L17 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L41 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L18 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L42 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L19 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L43 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L20 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L44 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L21 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L45 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L22 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L46 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L23 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L47 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 5997.77 MB (Load=4614.69 | Prefill=1001.02 | Warmup=0.00 | Decode=382.06 MB)
   SSD Data/Token (Decode)      : Avg=3.008 MB/tok (Min=0.062 | P50=0.062 | P95=51.112 | Max=72.426 MB) | Prefill=1.955 MB/tok
   NVMe Batches / Requests      : 116 Batches | 13339 Raw -> 11591 Merged (1748 LBA Merges, Avg 529.9 KB/io)
   SSD I/O Size Histogram       : <64K=9041 | 64K-512K=1314 | 512K-2M=835 | >2M=401
   SSD Read Bandwidth (Active)  : Min=4.78 | Avg=290.71 | Peak=11874.28 MB/s | WallAmort=48.29 MB/s
   OS Kernel I/O Verification   : Read=5131.65 MB | Write=263.39 MB | Syscalls=21109
   Sync Stall vs Async DMA      : SyncStall=1312.31 ms | AsyncOverlapped=1710.19 ms (56.6% Overlapped)
   RAM Traffic & Active BW      : 830.03 GB moved | Active=7.26 GB/s | WallAmort=6.68 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=89.45s (72.0%, 1001.02 MB SSD) | Decode=34.76s (28.0%, 382.06 MB SSD)
   CPU Time & Utilization       : User=415.438s + Sys=12.656s (Wall=152.989s) | SysUtil=70.0% | ThrUtil=70.0% | 64.71 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  97441.96 ms (152491.3 us/tok | 78.45%)
   MoE AVX2 Q8 Expert Compute   :  12212.62 ms (19112.1 us/tok |  9.83%)
   Router + Lookahead Dispatch  :   6004.21 ms ( 9396.3 us/tok |  4.83%)
   LM Head Output Projection    :   4663.54 ms ( 7298.2 us/tok |  3.75%)
   Foreground NVMe Sync Stall   :   1312.31 ms ( 2053.7 us/tok |  1.06%)
   Unaccounted / OMP & Sampling :   2572.44 ms ( 4025.7 us/tok |  2.07%) | Total Wall=124207.07 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    78.92%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     0.93%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.61%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    13.59%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.95%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 40165.6ms | usage={'prompt_tokens': 30, 'completion_tokens': 16, 'total_tokens': 46} | text='\n\n2223\n22222\n1\n2'
[Stage 3] /v1/chat/completions (stream=true SSE) 10852.4ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6980.96 MB (3364 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2.25 tps | Avg=2.25 tps | Hit=95.5% | NVMe=244.6 MB/s (13737.52 MB, QD=64) | RSS=12879.8 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.69 tps | Avg=2.45 tps | Hit=96.5% | NVMe=249.6 MB/s (18630.34 MB, QD=64) | RSS=12835.1 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.78 tps | Avg=2.55 tps | Hit=96.9% | NVMe=256.6 MB/s (23098.34 MB, QD=64) | RSS=12820.3 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.77 tps | Avg=2.60 tps | Hit=97.2% | NVMe=262.6 MB/s (27568.53 MB, QD=64) | RSS=12838.6 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.74 tps | Avg=2.63 tps | Hit=97.3% | NVMe=267.6 MB/s (32089.64 MB, QD=64) | RSS=12819.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.74 tps | Avg=2.65 tps | Hit=97.4% | NVMe=271.8 MB/s (36471.59 MB, QD=64) | RSS=12838.4 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.69 tps | Avg=2.65 tps | Hit=97.4% | NVMe=273.9 MB/s (40806.18 MB, QD=64) | RSS=12827.7 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.67 tps | Avg=2.65 tps | Hit=97.5% | NVMe=276.0 MB/s (45220.19 MB, QD=64) | RSS=12823.2 MB
[LIVE-DECODE] 8/64 tok | Avg=0.99 tps | Hit=97.5% (LA:+0.0%) | NVMe=282.4 MB/s (47477.66 MB) | RSS=12907.8 MB
[LIVE-DECODE] 13/64 tok | Avg=0.95 tps | Hit=97.5% (LA:+0.0%) | NVMe=288.9 MB/s (48842.86 MB) | RSS=12908.4 MB
[LIVE-DECODE] 16/64 tok | Avg=1.00 tps | Hit=97.5% (LA:+0.0%) | NVMe=292.2 MB/s (49550.33 MB) | RSS=12908.4 MB
[LIVE-DECODE] 24/64 tok | Avg=1.05 tps | Hit=97.5% (LA:+0.1%) | NVMe=300.4 MB/s (51620.92 MB) | RSS=12901.3 MB
[LIVE-DECODE] 27/64 tok | Avg=0.99 tps | Hit=97.5% (LA:+0.1%) | NVMe=303.3 MB/s (52467.81 MB) | RSS=12897.3 MB
[LIVE-DECODE] 32/64 tok | Avg=1.02 tps | Hit=97.5% (LA:+0.1%) | NVMe=307.9 MB/s (53497.86 MB) | RSS=12897.3 MB
[LIVE-DECODE] 40/64 tok | Avg=1.07 tps | Hit=97.5% (LA:+0.1%) | NVMe=315.7 MB/s (55241.41 MB) | RSS=12897.3 MB
[LIVE-DECODE] 48/64 tok | Avg=1.12 tps | Hit=97.5% (LA:+0.1%) | NVMe=323.8 MB/s (56933.94 MB) | RSS=12897.4 MB
[LIVE-DECODE] 52/64 tok | Avg=1.09 tps | Hit=97.5% (LA:+0.1%) | NVMe=327.8 MB/s (57802.36 MB) | RSS=12897.4 MB
[LIVE-DECODE] 56/64 tok | Avg=1.11 tps | Hit=97.5% (LA:+0.1%) | NVMe=331.9 MB/s (58690.01 MB) | RSS=12897.4 MB
[LIVE-DECODE] 66/64 tok | Avg=1.17 tps | Hit=97.5% (LA:+0.1%) | NVMe=338.4 MB/s (60034.16 MB) | RSS=12897.4 MB

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
   LRFU Cache / Staging Ring    : 6980.96 MB (3364/25088 exp = 13.41% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.76 MB | End=12897.36 MB | Peak=13417.81 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (66 tok) : "mu2202120220222322
```


22023092227252297371327270222127222222222222"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 67 Steps)]
   Logit Summary: AvgTop1Prob=10.3% | AvgMargin=0.507 | MinMargin=0.002
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      76 | m              |    7.55 |   0.9% |      16 |    7.49 | 771977.31 |  0 |  0 |  0 |     0.0 |
   |    2 |      84 | u              |    8.91 |   1.3% |     277 |    8.73 | 1398.95 |453 | 19 |  8 | 257289.0 |
   |    3 |      17 | 2              |   11.63 |   4.5% |      76 |   11.47 | 1039.21 |454 | 19 |  7 | 268993.0 |
   |    4 |      17 | 2              |   12.28 |  15.1% |      24 |   11.21 |  964.62 |449 | 27 |  4 | 289714.0 |
   |    5 |      15 | 0              |    9.77 |   5.1% |      17 |    9.73 |  969.88 |438 | 36 |  6 | 310643.0 |
   |    6 |      17 | 2              |    9.65 |   2.1% |      18 |    9.16 | 1142.83 |429 | 37 | 14 | 340264.0 |
   |    7 |      16 | 1              |   10.00 |   5.8% |      15 |    9.52 |  839.00 |450 | 27 |  3 | 279214.0 |
   |    8 |      17 | 2              |   12.82 |  20.9% |      18 |   12.19 |  975.22 |436 | 37 |  7 | 301714.0 |
   |   28 |      18 | 3              |   12.60 |  17.4% |      17 |   12.49 | 2578.23 |2336 |  6 | 58 | 242307.0 |
   |   14 |      17 | 2              |   10.18 |   4.7% |      16 |   10.01 | 2559.34 |2302 | 10 | 88 | 304249.0 |
   |   53 |      16 | 1              |    9.57 |   3.9% |      17 |    9.57 | 2519.36 |2346 |  3 | 51 | 235607.0 |
   |   21 |     198 | \n             |   11.94 |  47.4% |  248046 |    7.99 | 1059.25 |425 | 52 |  3 | 275964.0 |
   |   64 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  455.19 |1890 |  1 | 29 | 11549.2 |
   |   65 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  455.19 |  0 |  0 |  0 | 11549.2 |
   |   66 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  455.19 |  0 |  0 |  0 | 11549.2 |
   |   67 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  455.19 |  0 |  0 |  0 | 11549.2 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 771.977s, TTFT=771977.31ms): Avg=2.65 | Min=2.25 | Max=2.78 tps
   Prefill Chunks (8): C1:256t/2.3tps/95% | C2:256t/2.7tps/97% | C3:256t/2.8tps/97% | C4:256t/2.8tps/97%
                       C5:256t/2.7tps/97% | C6:256t/2.7tps/97% | C7:256t/2.7tps/97% | C8:256t/2.7tps/97%
   Decode  (66 tok, 56.620s): Avg=1.17 | Min=0.39 | Max=2.20 tps
   Latency (ms) : Min=455.19 | P10=691.83 | P25=712.01 | P50=748.94 | P75=832.32 | P90=1041.36 | P95=1398.95 | P99=2578.23 | Max=2578.23
   Mean/SD/Jitt : Mean=857.87ms | StdDev=399.05ms | Jitter=225.30ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/66
   MTP Head     : 3/12 draft tokens accepted (25.0% verified accept | Net 1.05x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1020480): RawRAM=994030 (97.41%) | Lookahead=1341 (+0.13%) | ColdMiss=25109 (2.46%) | EFF HIT=97.54%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 7481 prefetched -> 1931 consumed (25.8% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.5% | @64= 97.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21260 |19114 | 108 |2038 | 90.4%|3615.09 | | L24 |21260 |21044 |  10 | 206 | 99.0%| 447.41 |
   | L01 |21260 |20608 |  70 | 582 | 97.3%|1375.85 | | L25 |21260 |21067 |   7 | 186 | 99.1%| 385.38 |
   | L02 |21260 |20591 |  10 | 659 | 96.9%|1758.69 | | L26 |21260 |20651 |  38 | 571 | 97.3%|1276.44 |
   | L03 |21260 |21177 |   4 |  79 | 99.6%|1043.33 | | L27 |21260 |20913 |  25 | 322 | 98.5%| 742.55 |
   | L04 |21260 |20968 |   8 | 284 | 98.7%|1052.12 | | L28 |21260 |20552 |  43 | 665 | 96.9%|1498.27 |
   | L05 |21260 |20894 |  12 | 354 | 98.3%|1003.86 | | L29 |21260 |20726 |  28 | 506 | 97.6%| 845.53 |
   | L06 |21260 |20914 |  24 | 322 | 98.5%| 881.67 | | L30 |21260 |20345 |  44 | 871 | 95.9%|1394.34 |
   | L07 |21260 |20902 |  13 | 345 | 98.4%| 648.56 | | L31 |21260 |20476 |  46 | 738 | 96.5%|1306.47 |
   | L08 |21260 |21188 |   1 |  71 | 99.7%| 164.36 | | L32 |21260 |20659 |  19 | 582 | 97.3%|1362.92 |
   | L09 |21260 |21184 |   1 |  75 | 99.6%| 103.34 | | L33 |21260 |20538 |  45 | 677 | 96.8%|1132.18 |
   | L10 |21260 |21037 |   7 | 216 | 99.0%| 298.83 | | L34 |21260 |20265 |  35 | 960 | 95.5%|1515.33 |
   | L11 |21260 |21180 |   5 |  75 | 99.6%| 143.19 | | L35 |21260 |20653 |  35 | 572 | 97.3%| 962.21 |
   | L12 |21260 |21077 |   8 | 175 | 99.2%| 571.48 | | L36 |21260 |20649 |  24 | 587 | 97.2%|1008.30 |
   | L13 |21260 |20982 |  18 | 260 | 98.8%| 499.83 | | L37 |21260 |20611 |  29 | 620 | 97.1%|1293.36 |
   | L14 |21260 |20867 |  45 | 348 | 98.4%| 798.00 | | L38 |21260 |20853 |  18 | 389 | 98.2%|1041.46 |
   | L15 |21260 |20729 |  38 | 493 | 97.7%|1099.73 | | L39 |21260 |20631 |  33 | 596 | 97.2%|1471.95 |
   | L16 |21260 |20644 |  22 | 594 | 97.2%|1246.36 | | L40 |21260 |20784 |  28 | 448 | 97.9%|1210.64 |
   | L17 |21260 |20470 |  31 | 759 | 96.4%|1594.14 | | L41 |21260 |20768 |  14 | 478 | 97.8%| 782.15 |
   | L18 |21260 |20559 |  30 | 671 | 96.8%|1398.63 | | L42 |21260 |20460 |  48 | 752 | 96.5%|1313.67 |
   | L19 |21260 |20768 |  33 | 459 | 97.8%| 776.39 | | L43 |21260 |20374 |  34 | 852 | 96.0%|1482.20 |
   | L20 |21260 |20353 |  39 | 868 | 95.9%|1616.16 | | L44 |21260 |20383 |  48 | 829 | 96.1%|1431.79 |
   | L21 |21260 |20485 |  38 | 737 | 96.5%|1921.24 | | L45 |21260 |20378 |  53 | 829 | 96.1%|1528.30 |
   | L22 |21260 |21010 |  12 | 238 | 98.9%| 614.72 | | L46 |21260 |21014 |   9 | 237 | 98.9%| 659.72 |
   | L23 |21260 |20648 |  24 | 588 | 97.2%|1101.93 | | L47 |21260 |20887 |  27 | 346 | 98.4%| 924.90 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 60034.16 MB (Load=4614.69 | Prefill=40605.50 | Warmup=0.00 | Decode=14813.97 MB)
   SSD Data/Token (Decode)      : Avg=224.454 MB/tok (Min=11.279 | P50=225.384 | P95=303.362 | Max=332.289 MB) | Prefill=19.827 MB/tok
   NVMe Batches / Requests      : 3988 Batches | 132894 Raw -> 127970 Merged (4924 LBA Merges, Avg 480.4 KB/io)
   SSD I/O Size Histogram       : <64K=34001 | 64K-512K=23582 | 512K-2M=69875 | >2M=512
   SSD Read Bandwidth (Active)  : Min=4.80 | Avg=338.43 | Peak=5134.90 MB/s | WallAmort=72.45 MB/s
   OS Kernel I/O Verification   : Read=60054.43 MB | Write=594.14 MB | Syscalls=137491
   Sync Stall vs Async DMA      : SyncStall=144926.57 ms | AsyncOverlapped=158472.45 ms (52.2% Overlapped)
   RAM Traffic & Active BW      : 5687.55 GB moved | Active=8.73 GB/s | WallAmort=6.86 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=771.98s (93.2%, 40605.50 MB SSD) | Decode=56.62s (6.8%, 14813.97 MB SSD)
   CPU Time & Utilization       : User=2402.750s + Sys=42.219s (Wall=858.245s) | SysUtil=71.2% | ThrUtil=71.2% | 65.88 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 334400.42 ms (158183.7 us/tok | 40.36%)
   MoE AVX2 Q8 Expert Compute   : 312011.10 ms (147592.8 us/tok | 37.66%)
   Router + Lookahead Dispatch  :  18947.94 ms ( 8963.1 us/tok |  2.29%)
   LM Head Output Projection    :   4821.44 ms ( 2280.7 us/tok |  0.58%)
   Foreground NVMe Sync Stall   : 144926.57 ms (68555.6 us/tok | 17.49%)
   Unaccounted / OMP & Sampling :  13489.37 ms ( 6381.0 us/tok |  1.63%) | Total Wall=828596.84 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    91.34%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.16%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.01%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.07%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.42%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=103.0s | Competitor drastic-underperform cutoff=515.0s (5x Apex)
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=515.0s) ===
  [Colibri-Qwen38] [gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
  [Colibri-Qwen38] [gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
  [Colibri-Qwen38] == Qwen3.8-Flash-Next native text engine | cache=72/layer | CPU ==
  [Colibri-Qwen38] [tok] loaded 248320 base pieces + 33 added tokens (max id 248319) from D:/apex_d_drive/models/qwen38/tokenizer.json
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=515.0s
  [Colibri-Qwen38] [qwen38] native text weights: prefix=model, 48 layers, PLE=1, cache=72/layer, FP8=native, BF16=native (resident matrices 4.40 GiB)
  [Colibri-Qwen38] [qwen38] MTP head mtp.*: wiring b (a norm per stream, fc_hidden per stream), RoPE base 1e+07, 96.86 MiB resident; routed experts Q8_0 from the snapshot (its own GGUF), cache 72 (Q38_MTP_CAP) x 4.98 MiB = 0.35 GiB full
  [Colibri-Qwen38] [qwen38] MTP norm weights, mean: embedding -0.7642, hidden -0.3284, mixer 3.7881 (q38_rms0 scales by 1+w; a plain norm's weights would sit near 1)
  [Colibri-Qwen38] [qwen38] trunk: 62 matrices int8 on the CPU (0.08 GiB, 0.28 GiB of BF16 released) in 0.2s; Q38_TRUNK_CPU_INT8=0 keeps BF16
  [Colibri-Qwen38] [qwen38 MTP] draft vocabulary: the lm_head has no int8 rows on the host, so the head scores the whole vocabulary (Q38_MTP_VOCAB=0 silences this)
  [Colibri-Qwen38] [qwen38] routed experts: GGUF IQ2_XXS/IQ2_XXS/IQ4_NL (layer 0), 1.68 MiB per expert; cache 72/layer
  [Colibri-Qwen38] [qwen38] trunk: 62 int8 matrices interleaved by 16 for the CPU in 0.03s (Q38_ILV16=0 keeps the rows)
  [Colibri-Qwen38] resident weights loaded in 20.6s | RSS after load: 4.60 GB
  [Colibri-Qwen38] [qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.0s / cutoff=515.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=515.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=60.1s / cutoff=515.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=75.1s / cutoff=515.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=90.1s / cutoff=515.0s
  [Colibri-Qwen38] TTFT: 42.31 s (time to first token)
  [Colibri-Qwen38] [qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
  [Colibri-Qwen38] [qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
  [Colibri-Qwen38] [qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes
  [Colibri-Qwen38] 
  [Colibri-Qwen38] PEAK RSS: 10.76 GB
  [Colibri-Qwen38] Expert cache hit rate: 62.0% (hit=15849 miss=9733)
  [Colibri-Qwen38] Speed: 0.39 tok/s (81.6s for 32 tokens)
  [Colibri-Qwen38] [STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage
  [COMP-LIVE] Colibri-Qwen38: elapsed=105.1s / cutoff=515.0s
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
=== [Colibri-Qwen38] Finished rc=1 elapsed=105.63s cancelled=False ===
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 1.40 | 1.14 | 820.66 | 92.28% | 295.53 | 14056.30 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 5.72 | 3.65 | 251.00 | 98.52% | 290.71 | 14718.59 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.65 | 1.17 | 748.94 | 97.54% | 338.43 | 13417.81 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.39 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 916K Nov 14 14:14 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 916K Nov 14 14:14 build/apex.exe
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
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.50 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    232.19 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    946.04 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4906.68 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   5529.71 MB/s
   RND4K Q32T16 Read                  :    582.25 MB/s (  149057 IOPS)
   RND4K Q1T1  Read                   :    769.53 MB/s (Latency: 5.08 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     35.34 GB/s
   AVX2 256-bit Sequential Write BW   :     22.99 GB/s
   STREAM Triad (A = B + s*C) BW      :     26.54 GB/s
   Random Pointer-Chase Latency       :    111.77 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     42.29 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    142.33 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     16.64 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1330.23 tps | Avg=1330.23 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=60.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1265.95 tps | Avg=1297.30 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=60.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1094.28 tps | Avg=1221.74 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=61.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=966.24 tps | Avg=1145.98 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=61.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=862.99 tps | Avg=1075.45 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=61.7 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=781.06 tps | Avg=1011.88 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=61.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=719.72 tps | Avg=956.42 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=62.2 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=667.89 tps | Avg=907.42 tps | Hit=100.0% | NVMe=1796.5 MB/s (6.58 MB, QD=64) | RSS=62.4 MB
[LIVE-DECODE] 8/32 tok | Avg=50.07 tps | Hit=100.0% (LA:+0.0%) | NVMe=1796.5 MB/s (6.58 MB) | RSS=70.8 MB
[LIVE-DECODE] 16/32 tok | Avg=65.26 tps | Hit=100.0% (LA:+0.0%) | NVMe=1796.5 MB/s (6.58 MB) | RSS=70.8 MB
[LIVE-DECODE] 24/32 tok | Avg=73.35 tps | Hit=100.0% (LA:+0.0%) | NVMe=1796.5 MB/s (6.58 MB) | RSS=70.8 MB
[LIVE-DECODE] 31/32 tok | Avg=77.12 tps | Hit=100.0% (LA:+0.0%) | NVMe=1796.5 MB/s (6.58 MB) | RSS=70.8 MB

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
   Pinned Dense / KV+State RAM  : Dense=3.48 MB | KV/State=15.37 MB (3840 B/tok)
   LRFU Cache / Staging Ring    : 3.24 MB (67/64 exp = 104.69% pinned) | Staging=1.55 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=70.79 MB | Peak=78.26 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (31 tok) : "tok_55tok_55tok_55tok_55tok_246tok_251tok_199tok_55tok_246tok_71tok_246tok_251tok_55tok_55tok_251tok_251tok_21tok_55tok_246tok_55tok_119tok_251tok_251tok_246tok_119tok_55tok_55tok_55tok_55tok_199tok_55tok_199"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 32 Steps)]
   Logit Summary: AvgTop1Prob=95.4% | AvgMargin=12.467 | MinMargin=0.282
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2256.95 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |   30.80 | 48 |  0 |  0 |     0.0 |
   |    3 |      55 | tok_55         |  162.07 | 100.0% |     251 |  153.28 |   28.96 | 48 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  156.13 | 100.0% |     251 |  144.98 |   25.29 | 36 |  0 |  0 |     0.0 |
   |    5 |     246 | tok_246        |  161.71 | 100.0% |      55 |  147.08 |   24.93 | 36 |  0 |  0 |     0.0 |
   |    6 |     251 | tok_251        |  129.93 | 100.0% |     229 |  114.13 |    8.54 | 12 |  0 |  0 |     0.0 |
   |    7 |     199 | tok_199        |  140.67 |  66.3% |      71 |  139.99 |    8.26 | 12 |  0 |  0 |     0.0 |
   |    8 |      55 | tok_55         |  162.64 | 100.0% |     251 |  151.50 |    8.39 | 12 |  0 |  0 |     0.0 |
   |   17 |      21 | tok_21         |  162.32 |  57.0% |      86 |  162.03 |   26.23 | 36 |  0 |  0 |     0.0 |
   |    9 |     246 | tok_246        |  160.62 | 100.0% |      55 |  147.78 |   24.61 | 36 |  0 |  0 |     0.0 |
   |   25 |     119 | tok_119        |  190.28 | 100.0% |      55 |  146.04 |   23.66 | 36 |  0 |  0 |     0.0 |
   |   16 |     251 | tok_251        |  160.44 |  96.6% |      55 |  157.08 |    8.64 | 12 |  0 |  0 |     0.0 |
   |   29 |      55 | tok_55         |  170.19 | 100.0% |     251 |  153.56 |    8.22 | 12 |  0 |  0 |     0.0 |
   |   30 |     199 | tok_199        |  145.48 |  99.9% |      71 |  138.84 |   24.83 | 60 |  0 |  0 |     0.0 |
   |   31 |      55 | tok_55         |  163.52 | 100.0% |     251 |  152.05 |    8.37 | 12 |  0 |  0 |     0.0 |
   |   32 |     199 | tok_199        |  139.62 |  96.9% |      71 |  136.19 |    8.40 | 12 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.257s, TTFT=2256.95ms): Avg=907.42 | Min=667.89 | Max=1330.23 tps
   Prefill Chunks (8): C1:256t/1330.2tps/100% | C2:256t/1266.0tps/100% | C3:256t/1094.3tps/100% | C4:256t/966.2tps/100%
                       C5:256t/863.0tps/100% | C6:256t/781.1tps/100% | C7:256t/719.7tps/100% | C8:256t/667.9tps/100%
   Decode  (31 tok, 0.402s): Avg=77.12 | Min=32.46 | Max=122.79 tps
   Latency (ms) : Min=8.14 | P10=8.28 | P25=8.31 | P50=8.40 | P75=23.66 | P90=25.29 | P95=28.96 | P99=30.80 | Max=30.80
   Mean/SD/Jitt : Mean=12.97ms | StdDev=7.87ms | Jitter=5.20ms | Hist(<25/50/100/200/>200ms): 27/4/0/0/0
   MTP Head     : 0/12 draft tokens accepted (0.0% verified accept | Net 1.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (25188): RawRAM=25188 (100.00%) | Lookahead=0 (+0.00%) | ColdMiss=0 (0.00%) | EFF HIT=100.00%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 0 prefetched -> 0 consumed (0.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16=100.0% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L01 | 8396 | 8396 |   0 |   0 |100.0%|   0.00 | | L03 | 8396 | 8396 |   0 |   0 |100.0%|   0.00 |
   | L02 | 8396 | 8396 |   0 |   0 |100.0%|   0.00 | |     |      |      |     |     |      |        |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 6.58 MB (Load=6.58 | Prefill=0.00 | Warmup=0.00 | Decode=0.00 MB)
   SSD Data/Token (Decode)      : Avg=0.000 MB/tok (Min=0.000 | P50=0.000 | P95=0.000 | Max=0.000 MB) | Prefill=0.000 MB/tok
   NVMe Batches / Requests      : 1 Batches | 331 Raw -> 143 Merged (188 LBA Merges, Avg 47.1 KB/io)
   SSD I/O Size Histogram       : <64K=107 | 64K-512K=32 | 512K-2M=4 | >2M=0
   SSD Read Bandwidth (Active)  : Min=219.83 | Avg=1796.54 | Peak=4416.96 MB/s | WallAmort=2.47 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=7.88 MB | Syscalls=165
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=2.14 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.56 GB/s | WallAmort=0.54 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.26s (84.9%, 0.00 MB SSD) | Decode=0.40s (15.1%, 0.00 MB SSD)
   CPU Time & Utilization       : User=3.453s + Sys=0.453s (Wall=2.709s) | SysUtil=36.1% | ThrUtil=36.1% | 33.35 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2236.62 ms ( 1075.8 us/tok | 84.12%)
   MoE AVX2 Q8 Expert Compute   :    299.09 ms (  143.9 us/tok | 11.25%)
   Router + Lookahead Dispatch  :     61.06 ms (   29.4 us/tok |  2.30%)
   LM Head Output Projection    :      8.40 ms (    4.0 us/tok |  0.32%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     53.74 ms (   25.8 us/tok |  2.02%) | Total Wall=2658.91 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    20.26%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.89%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.10%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    76.04%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.71%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1796.84 tps | Avg=1796.84 tps | Hit=99.2% | NVMe=2223.2 MB/s (24.91 MB, QD=64) | RSS=85.7 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1939.57 tps | Avg=1865.48 tps | Hit=99.2% | NVMe=2923.1 MB/s (42.92 MB, QD=64) | RSS=85.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1806.69 tps | Avg=1845.46 tps | Hit=99.2% | NVMe=3364.8 MB/s (61.04 MB, QD=64) | RSS=86.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1661.19 tps | Avg=1795.66 tps | Hit=99.2% | NVMe=3670.3 MB/s (79.10 MB, QD=64) | RSS=86.5 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1552.08 tps | Avg=1741.02 tps | Hit=99.2% | NVMe=3883.3 MB/s (97.14 MB, QD=64) | RSS=87.0 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1455.76 tps | Avg=1685.96 tps | Hit=99.2% | NVMe=4038.3 MB/s (115.20 MB, QD=64) | RSS=87.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1371.45 tps | Avg=1632.47 tps | Hit=99.2% | NVMe=4157.4 MB/s (133.27 MB, QD=64) | RSS=87.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1253.67 tps | Avg=1573.06 tps | Hit=99.2% | NVMe=4278.9 MB/s (151.30 MB, QD=64) | RSS=88.2 MB
[LIVE-DECODE] 8/32 tok | Avg=42.96 tps | Hit=99.2% (LA:+0.0%) | NVMe=4096.8 MB/s (155.02 MB) | RSS=100.4 MB
[LIVE-DECODE] 16/32 tok | Avg=56.88 tps | Hit=99.1% (LA:+0.1%) | NVMe=3989.2 MB/s (157.50 MB) | RSS=100.4 MB
[LIVE-DECODE] 25/32 tok | Avg=72.39 tps | Hit=99.1% (LA:+0.2%) | NVMe=3897.1 MB/s (158.94 MB) | RSS=100.4 MB
[LIVE-DECODE] 33/32 tok | Avg=85.36 tps | Hit=99.1% (LA:+0.2%) | NVMe=3863.6 MB/s (160.48 MB) | RSS=100.4 MB

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
   LRFU Cache / Staging Ring    : 2.17 MB (40/80 exp = 50.00% pinned) | Staging=1.73 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=100.41 MB | Peak=111.56 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (33 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63qtok_194qtok_49qtok_229qtok_63qtok_223qtok_68qtok_66qtok_103qtok_65qtok_194qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229qtok_19qtok_63qtok_194qtok_49qtok_229qtok_63qtok_223qtok_68qtok_66qtok_103"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 34 Steps)]
   Logit Summary: AvgTop1Prob=96.9% | AvgMargin=7.559 | MinMargin=0.681
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   63.79 |  98.0% |     254 |   59.79 | 1301.92 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |   33.68 | 54 |  0 | 10 |  1279.0 |
   |    3 |      49 | qtok_49        |   64.76 |  99.9% |     177 |   57.43 |   35.51 | 51 |  8 |  5 |   755.5 |
   |    4 |     254 | qtok_254       |   51.96 |  89.9% |     229 |   49.75 |   28.27 | 47 |  0 |  1 |   303.0 |
   |    5 |      49 | qtok_49        |   69.73 |  99.7% |     177 |   63.67 |   30.17 | 44 |  0 |  4 |   469.5 |
   |    6 |     229 | qtok_229       |   50.30 |  93.3% |     254 |   47.41 |    9.57 | 15 |  1 |  0 |   230.5 |
   |    7 |      19 | qtok_19        |   81.50 |  96.5% |      63 |   78.17 |    9.46 | 12 |  4 |  0 |   119.5 |
   |    8 |      63 | qtok_63        |   86.30 |  99.6% |      19 |   80.66 |    9.43 | 15 |  1 |  0 |   119.5 |
   |   17 |      65 | qtok_65        |   59.40 |  95.1% |     209 |   56.43 |   30.45 | 36 |  2 | 10 |   913.5 |
   |    9 |     194 | qtok_194       |   63.76 | 100.0% |     118 |   41.99 |   30.15 | 44 |  0 |  4 |   525.0 |
   |   11 |     229 | qtok_229       |   52.77 |  76.0% |     194 |   51.58 |    9.48 | 16 |  0 |  0 |    64.0 |
   |   10 |      49 | qtok_49        |   73.57 | 100.0% |      81 |   53.37 |    9.40 | 15 |  1 |  0 |    64.0 |
   |   31 |     223 | qtok_223       |   72.59 |  99.9% |     159 |   65.60 |    5.03 | 48 |  7 |  9 |   192.9 |
   |   32 |      68 | qtok_68        |   72.59 |  99.9% |     159 |   65.60 |    5.03 |  0 |  0 |  0 |   192.9 |
   |   33 |      66 | qtok_66        |   72.59 |  99.9% |     159 |   65.60 |    5.03 |  0 |  0 |  0 |   192.9 |
   |   34 |     103 | qtok_103       |   72.59 |  99.9% |     159 |   65.60 |    5.03 |  0 |  0 |  0 |   192.9 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.302s, TTFT=1301.92ms): Avg=1573.06 | Min=1253.67 | Max=1939.57 tps
   Prefill Chunks (8): C1:256t/1796.8tps/99% | C2:256t/1939.6tps/99% | C3:256t/1806.7tps/99% | C4:256t/1661.2tps/99%
                       C5:256t/1552.1tps/99% | C6:256t/1455.8tps/99% | C7:256t/1371.4tps/99% | C8:256t/1253.7tps/99%
   Decode  (33 tok, 0.387s): Avg=85.36 | Min=28.16 | Max=211.38 tps
   Latency (ms) : Min=4.73 | P10=4.73 | P25=5.28 | P50=9.10 | P75=9.46 | P90=30.17 | P95=33.68 | P99=35.51 | Max=35.51
   Mean/SD/Jitt : Mean=11.72ms | StdDev=9.51ms | Jitter=3.82ms | Hist(<25/50/100/200/>200ms): 27/6/0/0/0
   MTP Head     : 9/17 draft tokens accepted (52.9% verified accept | Net 1.38x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33520): RawRAM=33151 (98.90%) | Lookahead=58 (+0.17%) | ColdMiss=311 (0.93%) | EFF HIT=99.07%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 59 prefetched -> 56 consumed (94.9% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.1% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8380 | 8314 |   0 |  66 | 99.2%|   3.58 | | L02 | 8380 | 8258 |  39 |  83 | 99.0%|   6.18 |
   | L01 | 8380 | 8286 |   9 |  85 | 99.0%|   5.09 | | L03 | 8380 | 8293 |  10 |  77 | 99.1%|   4.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 160.48 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=9.18 MB)
   SSD Data/Token (Decode)      : Avg=0.278 MB/tok (Min=0.062 | P50=0.225 | P95=0.892 | Max=1.249 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 128 Batches | 34879 Raw -> 458 Merged (34421 LBA Merges, Avg 358.8 KB/io)
   SSD I/O Size Histogram       : <64K=283 | 64K-512K=175 | 512K-2M=0 | >2M=0
   SSD Read Bandwidth (Active)  : Min=208.26 | Avg=3863.65 | Peak=7734.05 MB/s | WallAmort=95.04 MB/s
   OS Kernel I/O Verification   : Read=27.89 MB | Write=11.62 MB | Syscalls=480
   Sync Stall vs Async DMA      : SyncStall=12.23 ms | AsyncOverlapped=39.93 ms (76.5% Overlapped)
   RAM Traffic & Active BW      : 2.14 GB moved | Active=1.44 GB/s | WallAmort=1.26 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.30s (77.1%, 144.44 MB SSD) | Decode=0.39s (22.9%, 9.18 MB SSD)
   CPU Time & Utilization       : User=2.766s + Sys=0.609s (Wall=1.772s) | SysUtil=47.6% | ThrUtil=47.6% | 44.05 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1013.34 ms (  486.9 us/tok | 60.01%)
   MoE AVX2 Q8 Expert Compute   :    459.70 ms (  220.9 us/tok | 27.23%)
   Router + Lookahead Dispatch  :     80.40 ms (   38.6 us/tok |  4.76%)
   LM Head Output Projection    :      6.80 ms (    3.3 us/tok |  0.40%)
   Foreground NVMe Sync Stall   :     12.23 ms (    5.9 us/tok |  0.72%)
   Unaccounted / OMP & Sampling :    116.04 ms (   55.8 us/tok |  6.87%) | Total Wall=1688.53 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.07%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.56%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.44%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    67.06%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.87%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] OpenAI-Compatible API Server on port 18081 (tests/synth_glm53_ud_iq2_xxs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "tok_55tok_55tok_55tok_55tok_55tok_55tok_55tok_55"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 71, "completion_tokens": 8, "total_tokens": 79}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"tok_55tok_55tok_55tok_55tok_55tok_55"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"text": "tok_246tok_55tok_55tok_55tok_55tok_55", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "glm-5.3-flash-ud-iq2_xxs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "tok_55tok_55tok_55tok_55tok_55tok_55", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 69, "completion_tokens": 6, "total_tokens": 75}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "glm-5.3-flash-ud-iq2_xxs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "tok_55tok_55tok_55tok_55tok_55tok_55"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
[Concurrent Stress Test]: 4/4 parallel client requests completed cleanly.
[llama.cpp Server Parity]: /props, /tokenize, /detokenize, /v1/embeddings passed.
[GET /v1/telemetry]: {
  "model_name": "GLM-5.3-Flash-UD-IQ2_XXS-Synthetic",
  "architecture": "glm5-next (GLM-5.3-Flash)",
  "quantization": "Unsloth UD-IQ2_XXS",
  "mtp_enabled": false,
  "avx512_vnni_active": true,
  "prefix_cache_hits": 0,
  "prefix_tokens_reused": 0,
  "persistent_cache_saves": 9,
  "persistent_cache_loads": 0,
  "dense_pinned_ram_bytes": 3037760,
  "kv_cache_ram_bytes": 10797056,
  "kv_bytes_per_token": 2560,
  "expert_cache_ram_bytes": 2534400,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 514,
    "ttft_ms": 460.64,
    "avg_tps": 1115.84,
    "min_tps": 539.42,
    "max_tps": 1224.34
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 131.89,
    "min_tps": 120.49,
    "max_tps": 149.59,
    "p50_ms": 7.7,
    "p90_ms": 8.02,
    "p99_ms": 8.3,
    "mean_ms": 7.58,
    "jitter_ms": 0.21
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
    "bytes_per_token": 9892.92,
    "avg_mbs": 1696.64,
    "peak_mbs": 4770.99,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 1.72
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 483593728
  },
  "kernel_attribution_ms": {
    "dense_attention": 587.58,
    "moe_compute": 130.36,
    "router_lookahead": 17.13,
    "lm_head": 9.84,
    "unaccounted": 11.44
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 75.96,
    "ram_bandwidth_pinning": 2.02,
    "expert_cache_lrfu": 19.73,
    "lookahead_parallel_overlap": 1.97,
    "ssd_nvme_throughput": 0.32,
    "total": 100.0
  }
}

=== [TEST] OpenAI-Compatible API Server on port 18082 (tests/synth_qwen38_ud_iq2_xs.gguf) ===
[GET /v1/models]: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[POST /v1/chat/completions (stream=false)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_49qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229qtok_19"}, "finish_reason": "stop"}], "usage": {"prompt_tokens": 71, "completion_tokens": 8, "total_tokens": 79}}
[POST /v1/chat/completions (stream=true SSE)]: data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{"role":"assistant","content":"qtok_49qtok_49qtok_254qtok_49qtok_254qtok_49"},"finish_reason":null}]} | data: {"id":"chatcmpl-apex-stream","object":"chat.completion.chunk","choices":[{"index":0,"delta":{},"finish_reason":"stop"}]} | data: [DONE]
[POST /v1/completions]: {"id": "cmpl-apex-001", "object": "text_completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"text": "qtok_159qtok_112qtok_193qtok_128qtok_49qtok_254", "index": 0, "finish_reason": "stop"}], "usage": {"prompt_tokens": 12, "completion_tokens": 6, "total_tokens": 18}}
[POST /v1/chat/completions (Tool Call)]: {"id": "chatcmpl-apex-001", "object": "chat.completion", "created": 1770000000, "model": "qwen-3.8-flash-next-ud-iq2_xs", "choices": [{"index": 0, "message": {"role": "assistant", "content": "qtok_49qtok_49qtok_254qtok_49qtok_254qtok_49", "tool_calls": [{"id": "call_apex_1", "type": "function", "function": {"name": "get_system_status", "arguments": "{\"status\":\"ready\"}"}}]}, "finish_reason": "tool_calls"}], "usage": {"prompt_tokens": 69, "completion_tokens": 6, "total_tokens": 75}}
[POST /v1/responses (Codex API)]: {"id": "resp_apex_001", "object": "response", "model": "qwen-3.8-flash-next-ud-iq2_xs", "status": "completed", "output": [{"type": "message", "role": "assistant", "content": [{"type": "output_text", "text": "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_229"}]}], "usage": {"input_tokens": 15, "output_tokens": 6, "total_tokens": 21}}
[Concurrent Stress Test]: 4/4 parallel client requests completed cleanly.
[llama.cpp Server Parity]: /props, /tokenize, /detokenize, /v1/embeddings passed.
[GET /v1/telemetry]: {
  "model_name": "Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic",
  "architecture": "qwen4exp (Qwen-3.8-Flash-Next)",
  "quantization": "Unsloth UD-IQ2_XS",
  "mtp_enabled": false,
  "avx512_vnni_active": true,
  "prefix_cache_hits": 0,
  "prefix_tokens_reused": 0,
  "persistent_cache_saves": 9,
  "persistent_cache_loads": 0,
  "dense_pinned_ram_bytes": 3738208,
  "kv_cache_ram_bytes": 19173376,
  "kv_bytes_per_token": 13824,
  "expert_cache_ram_bytes": 1818624,
  "ssd_offloaded_expert_bytes": 3653632,
  "prefill": {
    "tokens": 514,
    "ttft_ms": 463.5,
    "avg_tps": 1108.95,
    "min_tps": 374.38,
    "max_tps": 1338.56
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 121.35,
    "min_tps": 109.83,
    "max_tps": 136.82,
    "p50_ms": 8.32,
    "p90_ms": 8.86,
    "p99_ms": 9.11,
    "mean_ms": 8.24,
    "jitter_ms": 0.23
  },
  "cache": {
    "raw_hit_rate_pct": 94.24,
    "effective_hit_rate_pct": 97.48,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 60007008,
    "prefill_bytes": 47063552,
    "warmup_bytes": 0,
    "decode_bytes": 7386624,
    "bytes_per_token": 108511.77,
    "avg_mbs": 2733.52,
    "peak_mbs": 6533.26,
    "sync_wait_ms": 8.03,
    "async_overlap_ms": 19.64
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 689928192
  },
  "kernel_attribution_ms": {
    "dense_attention": 442.78,
    "moe_compute": 246.0,
    "router_lookahead": 22.3,
    "lm_head": 9.17,
    "unaccounted": 56.61
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 71.8,
    "ram_bandwidth_pinning": 2.84,
    "expert_cache_lrfu": 17.01,
    "lookahead_parallel_overlap": 5.38,
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

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.49 GB Available
   Active Drive Space : 150.00 GB Total / 146.92 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    231.91 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    945.69 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4900.97 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7573.70 MB/s
   RND4K Q32T16 Read                  :    572.83 MB/s (  146644 IOPS)
   RND4K Q1T1  Read                   :    808.70 MB/s (Latency: 4.83 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     45.80 GB/s
   AVX2 256-bit Sequential Write BW   :     34.82 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.79 GB/s
   Random Pointer-Chase Latency       :    112.83 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     48.59 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    132.35 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     16.62 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 31.00 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 164.94 MB/s (6.21s)
   Window #01 (116.0 MB in 0.50s):   231.86 MB/s (Uncached Direct Read)
   Window #02 (116.0 MB in 0.51s):   227.92 MB/s (Uncached Direct Read)
   Window #03 (108.0 MB in 0.51s):   212.77 MB/s (Uncached Direct Read)
   Window #04 (124.0 MB in 0.52s):   240.76 MB/s (Uncached Direct Read)
   Window #05 (120.0 MB in 0.51s):   235.70 MB/s (Uncached Direct Read)
   Window #06 (116.0 MB in 0.50s):   230.44 MB/s (Uncached Direct Read)
   Window #07 (116.0 MB in 0.52s):   225.12 MB/s (Uncached Direct Read)
   Window #08 (116.0 MB in 0.50s):   230.34 MB/s (Uncached Direct Read)
   Window #09 ( 92.0 MB in 0.40s):   228.12 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   229.26 MB/s (Min=212.77 | Max=240.76 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.92 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 238.10 MB/s (4.30s)
   Window #01 (124.0 MB in 0.51s):   242.99 MB/s (Uncached Direct Read)
   Window #02 (120.0 MB in 0.51s):   235.37 MB/s (Uncached Direct Read)
   Window #03 (124.0 MB in 0.52s):   238.53 MB/s (Uncached Direct Read)
   Window #04 (120.0 MB in 0.50s):   239.89 MB/s (Uncached Direct Read)
   Window #05 (120.0 MB in 0.50s):   239.96 MB/s (Uncached Direct Read)
   Window #06 (120.0 MB in 0.51s):   235.42 MB/s (Uncached Direct Read)
   Window #07 (120.0 MB in 0.50s):   239.91 MB/s (Uncached Direct Read)
   Window #08 (120.0 MB in 0.50s):   239.98 MB/s (Uncached Direct Read)
   Window #09 ( 56.0 MB in 0.24s):   233.53 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   238.69 MB/s (Min=233.53 | Max=242.99 MB/s)
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
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 14.21 GB Available
   Active Drive Space : 150.00 GB Total / 75.97 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    230.04 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    946.31 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4752.68 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7488.05 MB/s
   RND4K Q32T16 Read                  :    481.51 MB/s (  123266 IOPS)
   RND4K Q1T1  Read                   :    742.25 MB/s (Latency: 5.26 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     43.52 GB/s
   AVX2 256-bit Sequential Write BW   :     30.43 GB/s
   STREAM Triad (A = B + s*C) BW      :     35.37 GB/s
   Random Pointer-Chase Latency       :    112.66 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     45.92 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    156.15 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     14.88 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=4.86 tps | Avg=4.86 tps | Hit=92.8% | NVMe=255.8 MB/s (5242.36 MB, QD=64) | RSS=14403.3 MB

 >>> [Apex-Model-Response] !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   LRFU Cache / Staging Ring    : 8668.09 MB (4177/25088 exp = 16.65% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=14575.54 MB | Peak=14706.40 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (63 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=0.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 18734.76 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  911.75 |474 |  6 |  0 | 72889.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  656.79 |478 |  2 |  0 | 57064.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  667.68 |480 |  0 |  0 | 51064.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  645.02 |479 |  1 |  0 | 54064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  652.36 |480 |  0 |  0 | 52339.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  625.56 |480 |  0 |  0 | 51064.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  626.40 |480 |  0 |  0 | 51064.0 |
   |   17 |       0 | !              |     nan | 100.0% |       1 |     nan |  254.99 |228 |  0 |  0 |    64.0 |
   |   18 |       0 | !              |     nan | 100.0% |       1 |     nan |  254.99 |  0 |  0 |  0 |    64.0 |
   |   19 |       0 | !              |     nan | 100.0% |       1 |     nan |  254.99 |  0 |  0 |  0 |    64.0 |
   |   20 |       0 | !              |     nan | 100.0% |       1 |     nan |  254.99 |  0 |  0 |  0 |    64.0 |
   |   61 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.37 |228 |  0 |  0 |    64.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.37 |  0 |  0 |  0 |    64.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.37 |  0 |  0 |  0 |    64.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  239.37 |  0 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 18.735s, TTFT=18734.76ms): Avg=4.86 | Min=4.86 | Max=4.86 tps
   Prefill Chunks (1): C1:91t/4.9tps/93%
   Decode  (63 tok, 18.518s): Avg=3.40 | Min=1.10 | Max=4.18 tps
   Latency (ms) : Min=239.37 | P10=240.02 | P25=243.11 | P50=244.06 | P75=250.44 | P90=625.56 | P95=652.36 | P99=911.75 | Max=911.75
   Mean/SD/Jitt : Mean=293.94ms | StdDev=141.38ms | Jitter=12.14ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
   MTP Head     : 42/42 draft tokens accepted (100.0% verified accept | Net 3.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (11964): RawRAM=11564 (96.66%) | Lookahead=9 (+0.08%) | ColdMiss=391 (3.27%) | EFF HIT=96.73%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 29 prefetched -> 16 consumed (55.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 95.9% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1266 |   9 | 265 | 82.8%| 461.57 | | L24 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L01 |  442 |  362 |   0 |  80 | 81.9%| 115.80 | | L25 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L02 |  217 |  216 |   0 |   1 | 99.5%|   1.68 | | L26 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L03 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L27 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L04 |  217 |  216 |   0 |   1 | 99.5%|   2.08 | | L28 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L05 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L29 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L06 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L30 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L07 |  217 |  216 |   0 |   1 | 99.5%|   1.68 | | L31 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L08 |  217 |  216 |   0 |   1 | 99.5%|   1.25 | | L32 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L09 |  217 |  216 |   0 |   1 | 99.5%|   1.25 | | L33 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L10 |  217 |  216 |   0 |   1 | 99.5%|   1.25 | | L34 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L11 |  217 |  216 |   0 |   1 | 99.5%|   1.25 | | L35 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L12 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L36 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L13 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L37 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L14 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L38 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L15 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L39 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L16 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L40 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L17 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L41 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L18 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L42 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L19 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L43 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L20 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L44 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L21 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L45 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L22 |  217 |  216 |   0 |   1 | 99.5%|   1.88 | | L46 |  217 |  216 |   0 |   1 | 99.5%|   1.44 |
   | L23 |  217 |  216 |   0 |   1 | 99.5%|   1.44 | | L47 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 5626.28 MB (Load=4614.69 | Prefill=627.67 | Warmup=0.00 | Decode=383.92 MB)
   SSD Data/Token (Decode)      : Avg=6.094 MB/tok (Min=0.062 | P50=0.062 | P95=55.727 | Max=71.181 MB) | Prefill=6.897 MB/tok
   NVMe Batches / Requests      : 96 Batches | 5021 Raw -> 4009 Merged (1012 LBA Merges, Avg 1437.1 KB/io)
   SSD I/O Size Histogram       : <64K=2002 | 64K-512K=994 | 512K-2M=608 | >2M=405
   SSD Read Bandwidth (Active)  : Min=4.77 | Avg=271.38 | Peak=11935.93 MB/s | WallAmort=151.03 MB/s (100.0% of 230.0 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=6134.69 MB | Write=300.73 MB | Syscalls=21064
   Sync Stall vs Async DMA      : SyncStall=1580.36 ms | AsyncOverlapped=1781.16 ms (53.0% Overlapped)
   RAM Traffic & Active BW      : 372.18 GB moved | Active=11.28 GB/s (31.9% STREAM) | WallAmort=9.99 GB/s (Max=35.37 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=18.73s (50.3%, 627.67 MB SSD) | Decode=18.52s (49.7%, 383.92 MB SSD)
   CPU Time & Utilization       : User=112.234s + Sys=7.625s (Wall=67.168s) | SysUtil=44.6% | ThrUtil=44.6% | 69.66 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  26308.50 ms (170834.4 us/tok | 70.62%)
   MoE AVX2 Q8 Expert Compute   :   4251.38 ms (27606.4 us/tok | 11.41%)
   Router + Lookahead Dispatch  :   1585.84 ms (10297.7 us/tok |  4.26%)
   LM Head Output Projection    :   2422.85 ms (15732.8 us/tok |  6.50%)
   Foreground NVMe Sync Stall   :   1580.36 ms (10262.1 us/tok |  4.24%)
   Unaccounted / OMP & Sampling :   1103.77 ms ( 7167.3 us/tok |  2.96%) | Total Wall=37252.70 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    75.41%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.21%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     7.92%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    11.72%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.74%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_qwen38_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=8026.86 MB (3868 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=1.40 tps | Avg=1.40 tps | Hit=88.2% | NVMe=238.4 MB/s (10527.38 MB, QD=64) | RSS=13808.9 MB
[LIVE-DECODE] 1/32 tok | Avg=0.62 tps | Hit=88.4% (LA:+0.2%) | NVMe=239.2 MB/s (10840.78 MB) | RSS=13972.1 MB
[LIVE-DECODE] 8/32 tok | Avg=0.90 tps | Hit=89.4% (LA:+0.8%) | NVMe=250.3 MB/s (12377.57 MB) | RSS=13939.9 MB
[LIVE-DECODE] 16/32 tok | Avg=1.09 tps | Hit=90.5% (LA:+0.9%) | NVMe=269.0 MB/s (13663.76 MB) | RSS=13930.9 MB
[LIVE-DECODE] 24/32 tok | Avg=1.15 tps | Hit=91.3% (LA:+1.1%) | NVMe=285.5 MB/s (15022.82 MB) | RSS=13934.7 MB
[LIVE-DECODE] 32/32 tok | Avg=1.14 tps | Hit=92.3% (LA:+1.2%) | NVMe=295.5 MB/s (16034.43 MB) | RSS=13944.3 MB

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
   LRFU Cache / Staging Ring    : 8026.86 MB (3868/25088 exp = 15.42% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=13944.31 MB | Peak=14056.30 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : "25  

2





u


22
22
21222
2121"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=20.3% | AvgMargin=1.316 | MinMargin=0.005
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      17 | 2              |    9.31 |   2.7% |     350 |    9.23 | 45594.85 |  0 |  0 |  0 |     0.0 |
   |    2 |      20 | 5              |    9.48 |   2.8% |      22 |    9.31 | 1606.08 |411 | 54 | 15 | 320914.0 |
   |    3 |     220 |                |   11.82 |  14.5% |     264 |   11.73 | 1423.99 |403 | 62 | 15 | 316868.0 |
   |    4 |     220 |                |   11.57 |  15.6% |     198 |   10.03 | 1356.26 |424 | 47 |  9 | 279218.0 |
   |    5 |     198 | \n             |   13.28 |  58.0% |     539 |    9.97 |  949.67 |462 | 18 |  0 | 214639.0 |
   |    6 |     198 | \n             |   10.52 |   9.8% |      84 |    8.46 | 1057.63 |440 | 38 |  2 | 221572.0 |
   |    7 |      17 | 2              |    8.72 |   1.2% |      64 |    8.52 |  780.26 |461 | 19 |  0 | 166293.0 |
   |    8 |     198 | \n             |   13.23 |  57.3% |     264 |    9.99 |  826.87 |449 | 31 |  0 | 214918.0 |
   |   15 |     198 | \n             |   10.62 |  14.0% |      17 |    8.27 |  933.36 |450 | 27 |  3 | 230089.0 |
   |   26 |      17 | 2              |   12.47 |  23.4% |      16 |   12.03 |  867.04 |450 | 27 |  3 | 233014.0 |
   |    9 |     198 | \n             |   15.12 |  91.3% |     271 |    9.59 |  853.88 |464 | 16 |  0 | 160164.0 |
   |   28 |      17 | 2              |   12.72 |  19.0% |      24 |   12.34 |  822.08 |457 | 23 |  0 | 194243.0 |
   |   30 |      17 | 2              |   11.66 |  15.1% |      15 |   10.60 |  834.11 |472 |  8 |  0 | 162364.0 |
   |   31 |      16 | 1              |   10.29 |   5.2% |      17 |   10.28 | 1034.41 |3321 |  1 | 38 | 20903.3 |
   |   32 |      17 | 2              |   10.29 |   5.2% |      17 |   10.28 | 1034.41 |  0 |  0 |  0 | 20903.3 |
   |   33 |      16 | 1              |   10.29 |   5.2% |      17 |   10.28 | 1034.41 |  0 |  0 |  0 | 20903.3 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 45.595s, TTFT=45594.85ms): Avg=1.40 | Min=1.40 | Max=1.40 tps
   Prefill Chunks (1): C1:64t/1.4tps/88%
   Decode  (32 tok, 27.998s): Avg=1.14 | Min=0.62 | Max=1.55 tps
   Latency (ms) : Min=643.75 | P10=687.50 | P25=734.32 | P50=820.66 | P75=949.67 | P90=1057.63 | P95=1423.99 | P99=1606.08 | Max=1606.08
   Mean/SD/Jitt : Mean=874.93ms | StdDev=221.26ms | Jitter=88.65ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 2/3 draft tokens accepted (66.7% verified accept | Net 1.07x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (48000): RawRAM=43738 (91.12%) | Lookahead=557 (+1.16%) | ColdMiss=3705 (7.72%) | EFF HIT=92.28%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 2668 prefetched -> 847 consumed (31.7% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1000 |  729 |  52 | 219 | 78.1%| 454.83 | | L24 | 1000 |  946 |   8 |  46 | 95.4%| 139.11 |
   | L01 | 1000 |  869 |  38 |  93 | 90.7%| 381.01 | | L25 | 1000 |  936 |  11 |  53 | 94.7%| 142.87 |
   | L02 | 1000 |  882 |  10 | 108 | 89.2%| 377.34 | | L26 | 1000 |  917 |  12 |  71 | 92.9%| 176.71 |
   | L03 | 1000 |  943 |   0 |  57 | 94.3%| 469.97 | | L27 | 1000 |  925 |  10 |  65 | 93.5%| 236.87 |
   | L04 | 1000 |  938 |   3 |  59 | 94.1%| 273.93 | | L28 | 1000 |  900 |  17 |  83 | 91.7%| 253.78 |
   | L05 | 1000 |  921 |   9 |  70 | 93.0%| 306.42 | | L29 | 1000 |  917 |   8 |  75 | 92.5%| 148.36 |
   | L06 | 1000 |  921 |  13 |  66 | 93.4%| 227.47 | | L30 | 1000 |  887 |  12 | 101 | 89.9%| 190.14 |
   | L07 | 1000 |  921 |  19 |  60 | 94.0%| 143.19 | | L31 | 1000 |  893 |  13 |  94 | 90.6%| 185.82 |
   | L08 | 1000 |  950 |  10 |  40 | 96.0%|  92.14 | | L32 | 1000 |  918 |   5 |  77 | 92.3%| 189.87 |
   | L09 | 1000 |  940 |   7 |  53 | 94.7%| 115.80 | | L33 | 1000 |  912 |   9 |  79 | 92.1%| 136.84 |
   | L10 | 1000 |  933 |  11 |  56 | 94.4%| 104.59 | | L34 | 1000 |  914 |   8 |  78 | 92.2%| 145.48 |
   | L11 | 1000 |  946 |   3 |  51 | 94.9%| 133.23 | | L35 | 1000 |  922 |  10 |  68 | 93.2%| 123.88 |
   | L12 | 1000 |  921 |  12 |  67 | 93.3%| 212.43 | | L36 | 1000 |  913 |  10 |  77 | 92.3%| 168.53 |
   | L13 | 1000 |  913 |  13 |  74 | 92.6%| 151.25 | | L37 | 1000 |  921 |   6 |  73 | 92.7%| 171.07 |
   | L14 | 1000 |  907 |  16 |  77 | 92.3%| 169.97 | | L38 | 1000 |  932 |   4 |  64 | 93.6%| 218.07 |
   | L15 | 1000 |  909 |  15 |  76 | 92.4%| 212.43 | | L39 | 1000 |  923 |   8 |  69 | 93.1%| 221.83 |
   | L16 | 1000 |  922 |   4 |  74 | 92.6%| 167.31 | | L40 | 1000 |  907 |   4 |  89 | 91.1%| 250.02 |
   | L17 | 1000 |  923 |   8 |  69 | 93.1%| 167.31 | | L41 | 1000 |  901 |   9 |  90 | 91.0%| 146.92 |
   | L18 | 1000 |  913 |  15 |  72 | 92.8%| 191.75 | | L42 | 1000 |  877 |  16 | 107 | 89.3%| 246.31 |
   | L19 | 1000 |  923 |  11 |  66 | 93.4%| 145.48 | | L43 | 1000 |  903 |   9 |  88 | 91.2%| 198.78 |
   | L20 | 1000 |  890 |  14 |  96 | 90.4%| 190.14 | | L44 | 1000 |  892 |  16 |  92 | 90.8%| 167.09 |
   | L21 | 1000 |  896 |  12 |  92 | 90.8%| 381.62 | | L45 | 1000 |  885 |  17 |  98 | 90.2%| 226.15 |
   | L22 | 1000 |  933 |  13 |  54 | 94.6%| 187.99 | | L46 | 1000 |  918 |   8 |  74 | 92.6%| 236.23 |
   | L23 | 1000 |  929 |   9 |  62 | 93.8%| 161.33 | | L47 | 1000 |  907 |  10 |  83 | 91.7%| 229.35 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 16034.43 MB (Load=4614.69 | Prefill=5912.69 | Warmup=0.00 | Decode=5507.05 MB)
   SSD Data/Token (Decode)      : Avg=172.095 MB/tok (Min=20.413 | P50=174.578 | P95=309.441 | Max=313.393 MB) | Prefill=92.386 MB/tok
   NVMe Batches / Requests      : 1383 Batches | 21827 Raw -> 21088 Merged (739 LBA Merges, Avg 778.6 KB/io)
   SSD I/O Size Histogram       : <64K=1915 | 64K-512K=5005 | 512K-2M=13735 | >2M=433
   SSD Read Bandwidth (Active)  : Min=4.75 | Avg=295.53 | Peak=5132.09 MB/s | WallAmort=217.88 MB/s
   OS Kernel I/O Verification   : Read=16054.40 MB | Write=166.92 MB | Syscalls=30594
   Sync Stall vs Async DMA      : SyncStall=25594.10 ms | AsyncOverlapped=35331.72 ms (58.0% Overlapped)
   RAM Traffic & Active BW      : 410.37 GB moved | Active=10.50 GB/s | WallAmort=5.58 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=45.59s (62.0%, 5912.69 MB SSD) | Decode=28.00s (38.0%, 5507.05 MB SSD)
   CPU Time & Utilization       : User=130.047s + Sys=10.203s (Wall=101.011s) | SysUtil=34.7% | ThrUtil=34.7% | 32.11 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  19882.50 ms (207109.3 us/tok | 27.02%)
   MoE AVX2 Q8 Expert Compute   :  16875.53 ms (175786.7 us/tok | 22.93%)
   Router + Lookahead Dispatch  :   1087.50 ms (11328.2 us/tok |  1.48%)
   LM Head Output Projection    :   2326.49 ms (24234.2 us/tok |  3.16%)
   Foreground NVMe Sync Stall   :  25594.10 ms (266605.2 us/tok | 34.78%)
   Unaccounted / OMP & Sampling :   7826.54 ms (81526.4 us/tok | 10.63%) | Total Wall=73592.64 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    80.76%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.41%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     8.75%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.28%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.80%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_qwen38_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=8614.14 MB (4151 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=5.64 tps | Avg=5.64 tps | Hit=97.5% | NVMe=262.9 MB/s (5225.38 MB, QD=64) | RSS=14376.2 MB
[LIVE-PREFILL] 512/512 tok | Chunk=5.81 tps | Avg=5.72 tps | Hit=98.0% | NVMe=274.0 MB/s (5615.71 MB, QD=64) | RSS=14465.4 MB
[LIVE-DECODE] 11/128 tok | Avg=1.96 tps | Hit=98.2% (LA:+0.2%) | NVMe=290.4 MB/s (5988.84 MB) | RSS=14524.7 MB
[LIVE-DECODE] 19/128 tok | Avg=2.50 tps | Hit=98.2% (LA:+0.2%) | NVMe=290.4 MB/s (5991.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 27/128 tok | Avg=2.82 tps | Hit=98.3% (LA:+0.2%) | NVMe=290.5 MB/s (5991.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 35/128 tok | Avg=3.01 tps | Hit=98.3% (LA:+0.2%) | NVMe=290.5 MB/s (5992.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 43/128 tok | Avg=3.16 tps | Hit=98.3% (LA:+0.2%) | NVMe=290.5 MB/s (5992.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 51/128 tok | Avg=3.27 tps | Hit=98.3% (LA:+0.2%) | NVMe=290.5 MB/s (5993.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 59/128 tok | Avg=3.35 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.5 MB/s (5993.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 67/128 tok | Avg=3.42 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.6 MB/s (5994.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 75/128 tok | Avg=3.47 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.6 MB/s (5994.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 83/128 tok | Avg=3.51 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.6 MB/s (5995.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 91/128 tok | Avg=3.54 tps | Hit=98.4% (LA:+0.2%) | NVMe=290.6 MB/s (5995.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 99/128 tok | Avg=3.58 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.6 MB/s (5996.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 107/128 tok | Avg=3.60 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.7 MB/s (5996.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 115/128 tok | Avg=3.62 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.7 MB/s (5997.02 MB) | RSS=14524.7 MB
[LIVE-DECODE] 123/128 tok | Avg=3.64 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.7 MB/s (5997.52 MB) | RSS=14524.7 MB
[LIVE-DECODE] 127/128 tok | Avg=3.65 tps | Hit=98.5% (LA:+0.2%) | NVMe=290.7 MB/s (5997.77 MB) | RSS=14524.7 MB

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
   LRFU Cache / Staging Ring    : 8614.14 MB (4151/25088 exp = 16.55% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=14524.68 MB | Peak=14718.59 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (127 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 128 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=0.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 89448.27 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  851.74 |474 |  6 |  0 | 74164.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  621.66 |480 |  0 |  0 | 52339.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  622.37 |480 |  0 |  0 | 51064.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  623.69 |480 |  0 |  0 | 51064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  622.34 |480 |  0 |  0 | 51064.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  634.27 |480 |  0 |  0 | 51064.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  625.28 |480 |  0 |  0 | 51064.0 |
   |   73 |       0 | !              |     nan | 100.0% |       1 |     nan |  264.42 |228 |  0 |  0 |    64.0 |
   |   74 |       0 | !              |     nan | 100.0% |       1 |     nan |  264.42 |  0 |  0 |  0 |    64.0 |
   |   75 |       0 | !              |     nan | 100.0% |       1 |     nan |  264.42 |  0 |  0 |  0 |    64.0 |
   |   76 |       0 | !              |     nan | 100.0% |       1 |     nan |  264.42 |  0 |  0 |  0 |    64.0 |
   |  125 |       0 | !              |     nan | 100.0% |       1 |     nan |  253.03 |228 |  0 |  0 |    64.0 |
   |  126 |       0 | !              |     nan | 100.0% |       1 |     nan |  253.03 |  0 |  0 |  0 |    64.0 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  253.03 |  0 |  0 |  0 |    64.0 |
   |  128 |       0 | !              |     nan | 100.0% |       1 |     nan |  253.03 |  0 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 89.448s, TTFT=89448.27ms): Avg=5.72 | Min=5.64 | Max=5.81 tps
   Prefill Chunks (2): C1:256t/5.6tps/98% | C2:256t/5.8tps/98%
   Decode  (127 tok, 34.759s): Avg=3.65 | Min=1.17 | Max=4.08 tps
   Latency (ms) : Min=245.37 | P10=247.28 | P25=249.32 | P50=251.00 | P75=253.03 | P90=255.56 | P95=621.66 | P99=634.27 | Max=851.74
   Mean/SD/Jitt : Mean=273.69ms | StdDev=94.58ms | Jitter=5.79ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/127
   MTP Head     : 90/90 draft tokens accepted (100.0% verified accept | Net 3.43x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (39402): RawRAM=38755 (98.36%) | Lookahead=65 (+0.16%) | ColdMiss=582 (1.48%) | EFF HIT=98.52%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 24 prefetched -> 29 consumed (120.8% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 98.2% | @64= 98.4% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 6390 | 5809 |  65 | 516 | 91.9%| 879.35 | | L24 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L01 |  720 |  700 |   0 |  20 | 97.2%|  38.60 | | L25 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L02 |  702 |  701 |   0 |   1 | 99.9%|   1.68 | | L26 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L03 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L27 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L04 |  702 |  701 |   0 |   1 | 99.9%|   2.08 | | L28 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L05 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L29 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L06 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L30 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L07 |  702 |  701 |   0 |   1 | 99.9%|   1.68 | | L31 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L08 |  702 |  701 |   0 |   1 | 99.9%|   1.25 | | L32 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L09 |  702 |  701 |   0 |   1 | 99.9%|   1.25 | | L33 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L10 |  702 |  701 |   0 |   1 | 99.9%|   1.25 | | L34 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L11 |  702 |  701 |   0 |   1 | 99.9%|   1.25 | | L35 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L12 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L36 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L13 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L37 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L14 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L38 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L15 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L39 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L16 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L40 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   | L17 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L41 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L18 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L42 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L19 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L43 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L20 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L44 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L21 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L45 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L22 |  702 |  701 |   0 |   1 | 99.9%|   1.88 | | L46 |  702 |  701 |   0 |   1 | 99.9%|   1.44 |
   | L23 |  702 |  701 |   0 |   1 | 99.9%|   1.44 | | L47 |  702 |  701 |   0 |   1 | 99.9%|   1.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 5997.77 MB (Load=4614.69 | Prefill=1001.02 | Warmup=0.00 | Decode=382.06 MB)
   SSD Data/Token (Decode)      : Avg=3.008 MB/tok (Min=0.062 | P50=0.062 | P95=51.112 | Max=72.426 MB) | Prefill=1.955 MB/tok
   NVMe Batches / Requests      : 116 Batches | 13339 Raw -> 11591 Merged (1748 LBA Merges, Avg 529.9 KB/io)
   SSD I/O Size Histogram       : <64K=9041 | 64K-512K=1314 | 512K-2M=835 | >2M=401
   SSD Read Bandwidth (Active)  : Min=4.78 | Avg=290.71 | Peak=11874.28 MB/s | WallAmort=48.29 MB/s
   OS Kernel I/O Verification   : Read=5131.65 MB | Write=263.39 MB | Syscalls=21109
   Sync Stall vs Async DMA      : SyncStall=1312.31 ms | AsyncOverlapped=1710.19 ms (56.6% Overlapped)
   RAM Traffic & Active BW      : 830.03 GB moved | Active=7.26 GB/s | WallAmort=6.68 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=89.45s (72.0%, 1001.02 MB SSD) | Decode=34.76s (28.0%, 382.06 MB SSD)
   CPU Time & Utilization       : User=415.438s + Sys=12.656s (Wall=152.989s) | SysUtil=70.0% | ThrUtil=70.0% | 64.71 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  97441.96 ms (152491.3 us/tok | 78.45%)
   MoE AVX2 Q8 Expert Compute   :  12212.62 ms (19112.1 us/tok |  9.83%)
   Router + Lookahead Dispatch  :   6004.21 ms ( 9396.3 us/tok |  4.83%)
   LM Head Output Projection    :   4663.54 ms ( 7298.2 us/tok |  3.75%)
   Foreground NVMe Sync Stall   :   1312.31 ms ( 2053.7 us/tok |  1.06%)
   Unaccounted / OMP & Sampling :   2572.44 ms ( 4025.7 us/tok |  2.07%) | Total Wall=124207.07 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    78.92%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     0.93%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.61%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    13.59%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.95%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_qwen38_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 40165.6ms | usage={'prompt_tokens': 30, 'completion_tokens': 16, 'total_tokens': 46} | text='\n\n2223\n22222\n1\n2'
[Stage 3] /v1/chat/completions (stream=true SSE) 10852.4ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_qwen38_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6980.96 MB (3364 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2.25 tps | Avg=2.25 tps | Hit=95.5% | NVMe=244.6 MB/s (13737.52 MB, QD=64) | RSS=12879.8 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.69 tps | Avg=2.45 tps | Hit=96.5% | NVMe=249.6 MB/s (18630.34 MB, QD=64) | RSS=12835.1 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.78 tps | Avg=2.55 tps | Hit=96.9% | NVMe=256.6 MB/s (23098.34 MB, QD=64) | RSS=12820.3 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.77 tps | Avg=2.60 tps | Hit=97.2% | NVMe=262.6 MB/s (27568.53 MB, QD=64) | RSS=12838.6 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.74 tps | Avg=2.63 tps | Hit=97.3% | NVMe=267.6 MB/s (32089.64 MB, QD=64) | RSS=12819.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.74 tps | Avg=2.65 tps | Hit=97.4% | NVMe=271.8 MB/s (36471.59 MB, QD=64) | RSS=12838.4 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.69 tps | Avg=2.65 tps | Hit=97.4% | NVMe=273.9 MB/s (40806.18 MB, QD=64) | RSS=12827.7 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.67 tps | Avg=2.65 tps | Hit=97.5% | NVMe=276.0 MB/s (45220.19 MB, QD=64) | RSS=12823.2 MB
[LIVE-DECODE] 8/64 tok | Avg=0.99 tps | Hit=97.5% (LA:+0.0%) | NVMe=282.4 MB/s (47477.66 MB) | RSS=12907.8 MB
[LIVE-DECODE] 13/64 tok | Avg=0.95 tps | Hit=97.5% (LA:+0.0%) | NVMe=288.9 MB/s (48842.86 MB) | RSS=12908.4 MB
[LIVE-DECODE] 16/64 tok | Avg=1.00 tps | Hit=97.5% (LA:+0.0%) | NVMe=292.2 MB/s (49550.33 MB) | RSS=12908.4 MB
[LIVE-DECODE] 24/64 tok | Avg=1.05 tps | Hit=97.5% (LA:+0.1%) | NVMe=300.4 MB/s (51620.92 MB) | RSS=12901.3 MB
[LIVE-DECODE] 27/64 tok | Avg=0.99 tps | Hit=97.5% (LA:+0.1%) | NVMe=303.3 MB/s (52467.81 MB) | RSS=12897.3 MB
[LIVE-DECODE] 32/64 tok | Avg=1.02 tps | Hit=97.5% (LA:+0.1%) | NVMe=307.9 MB/s (53497.86 MB) | RSS=12897.3 MB
[LIVE-DECODE] 40/64 tok | Avg=1.07 tps | Hit=97.5% (LA:+0.1%) | NVMe=315.7 MB/s (55241.41 MB) | RSS=12897.3 MB
[LIVE-DECODE] 48/64 tok | Avg=1.12 tps | Hit=97.5% (LA:+0.1%) | NVMe=323.8 MB/s (56933.94 MB) | RSS=12897.4 MB
[LIVE-DECODE] 52/64 tok | Avg=1.09 tps | Hit=97.5% (LA:+0.1%) | NVMe=327.8 MB/s (57802.36 MB) | RSS=12897.4 MB
[LIVE-DECODE] 56/64 tok | Avg=1.11 tps | Hit=97.5% (LA:+0.1%) | NVMe=331.9 MB/s (58690.01 MB) | RSS=12897.4 MB
[LIVE-DECODE] 66/64 tok | Avg=1.17 tps | Hit=97.5% (LA:+0.1%) | NVMe=338.4 MB/s (60034.16 MB) | RSS=12897.4 MB

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
   LRFU Cache / Staging Ring    : 6980.96 MB (3364/25088 exp = 13.41% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.76 MB | End=12897.36 MB | Peak=13417.81 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (66 tok) : "mu2202120220222322
```


22023092227252297371327270222127222222222222"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 67 Steps)]
   Logit Summary: AvgTop1Prob=10.3% | AvgMargin=0.507 | MinMargin=0.002
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      76 | m              |    7.55 |   0.9% |      16 |    7.49 | 771977.31 |  0 |  0 |  0 |     0.0 |
   |    2 |      84 | u              |    8.91 |   1.3% |     277 |    8.73 | 1398.95 |453 | 19 |  8 | 257289.0 |
   |    3 |      17 | 2              |   11.63 |   4.5% |      76 |   11.47 | 1039.21 |454 | 19 |  7 | 268993.0 |
   |    4 |      17 | 2              |   12.28 |  15.1% |      24 |   11.21 |  964.62 |449 | 27 |  4 | 289714.0 |
   |    5 |      15 | 0              |    9.77 |   5.1% |      17 |    9.73 |  969.88 |438 | 36 |  6 | 310643.0 |
   |    6 |      17 | 2              |    9.65 |   2.1% |      18 |    9.16 | 1142.83 |429 | 37 | 14 | 340264.0 |
   |    7 |      16 | 1              |   10.00 |   5.8% |      15 |    9.52 |  839.00 |450 | 27 |  3 | 279214.0 |
   |    8 |      17 | 2              |   12.82 |  20.9% |      18 |   12.19 |  975.22 |436 | 37 |  7 | 301714.0 |
   |   28 |      18 | 3              |   12.60 |  17.4% |      17 |   12.49 | 2578.23 |2336 |  6 | 58 | 242307.0 |
   |   14 |      17 | 2              |   10.18 |   4.7% |      16 |   10.01 | 2559.34 |2302 | 10 | 88 | 304249.0 |
   |   53 |      16 | 1              |    9.57 |   3.9% |      17 |    9.57 | 2519.36 |2346 |  3 | 51 | 235607.0 |
   |   21 |     198 | \n             |   11.94 |  47.4% |  248046 |    7.99 | 1059.25 |425 | 52 |  3 | 275964.0 |
   |   64 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  455.19 |1890 |  1 | 29 | 11549.2 |
   |   65 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  455.19 |  0 |  0 |  0 | 11549.2 |
   |   66 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  455.19 |  0 |  0 |  0 | 11549.2 |
   |   67 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  455.19 |  0 |  0 |  0 | 11549.2 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 771.977s, TTFT=771977.31ms): Avg=2.65 | Min=2.25 | Max=2.78 tps
   Prefill Chunks (8): C1:256t/2.3tps/95% | C2:256t/2.7tps/97% | C3:256t/2.8tps/97% | C4:256t/2.8tps/97%
                       C5:256t/2.7tps/97% | C6:256t/2.7tps/97% | C7:256t/2.7tps/97% | C8:256t/2.7tps/97%
   Decode  (66 tok, 56.620s): Avg=1.17 | Min=0.39 | Max=2.20 tps
   Latency (ms) : Min=455.19 | P10=691.83 | P25=712.01 | P50=748.94 | P75=832.32 | P90=1041.36 | P95=1398.95 | P99=2578.23 | Max=2578.23
   Mean/SD/Jitt : Mean=857.87ms | StdDev=399.05ms | Jitter=225.30ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/66
   MTP Head     : 3/12 draft tokens accepted (25.0% verified accept | Net 1.05x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1020480): RawRAM=994030 (97.41%) | Lookahead=1341 (+0.13%) | ColdMiss=25109 (2.46%) | EFF HIT=97.54%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 7481 prefetched -> 1931 consumed (25.8% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.5% | @64= 97.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21260 |19114 | 108 |2038 | 90.4%|3615.09 | | L24 |21260 |21044 |  10 | 206 | 99.0%| 447.41 |
   | L01 |21260 |20608 |  70 | 582 | 97.3%|1375.85 | | L25 |21260 |21067 |   7 | 186 | 99.1%| 385.38 |
   | L02 |21260 |20591 |  10 | 659 | 96.9%|1758.69 | | L26 |21260 |20651 |  38 | 571 | 97.3%|1276.44 |
   | L03 |21260 |21177 |   4 |  79 | 99.6%|1043.33 | | L27 |21260 |20913 |  25 | 322 | 98.5%| 742.55 |
   | L04 |21260 |20968 |   8 | 284 | 98.7%|1052.12 | | L28 |21260 |20552 |  43 | 665 | 96.9%|1498.27 |
   | L05 |21260 |20894 |  12 | 354 | 98.3%|1003.86 | | L29 |21260 |20726 |  28 | 506 | 97.6%| 845.53 |
   | L06 |21260 |20914 |  24 | 322 | 98.5%| 881.67 | | L30 |21260 |20345 |  44 | 871 | 95.9%|1394.34 |
   | L07 |21260 |20902 |  13 | 345 | 98.4%| 648.56 | | L31 |21260 |20476 |  46 | 738 | 96.5%|1306.47 |
   | L08 |21260 |21188 |   1 |  71 | 99.7%| 164.36 | | L32 |21260 |20659 |  19 | 582 | 97.3%|1362.92 |
   | L09 |21260 |21184 |   1 |  75 | 99.6%| 103.34 | | L33 |21260 |20538 |  45 | 677 | 96.8%|1132.18 |
   | L10 |21260 |21037 |   7 | 216 | 99.0%| 298.83 | | L34 |21260 |20265 |  35 | 960 | 95.5%|1515.33 |
   | L11 |21260 |21180 |   5 |  75 | 99.6%| 143.19 | | L35 |21260 |20653 |  35 | 572 | 97.3%| 962.21 |
   | L12 |21260 |21077 |   8 | 175 | 99.2%| 571.48 | | L36 |21260 |20649 |  24 | 587 | 97.2%|1008.30 |
   | L13 |21260 |20982 |  18 | 260 | 98.8%| 499.83 | | L37 |21260 |20611 |  29 | 620 | 97.1%|1293.36 |
   | L14 |21260 |20867 |  45 | 348 | 98.4%| 798.00 | | L38 |21260 |20853 |  18 | 389 | 98.2%|1041.46 |
   | L15 |21260 |20729 |  38 | 493 | 97.7%|1099.73 | | L39 |21260 |20631 |  33 | 596 | 97.2%|1471.95 |
   | L16 |21260 |20644 |  22 | 594 | 97.2%|1246.36 | | L40 |21260 |20784 |  28 | 448 | 97.9%|1210.64 |
   | L17 |21260 |20470 |  31 | 759 | 96.4%|1594.14 | | L41 |21260 |20768 |  14 | 478 | 97.8%| 782.15 |
   | L18 |21260 |20559 |  30 | 671 | 96.8%|1398.63 | | L42 |21260 |20460 |  48 | 752 | 96.5%|1313.67 |
   | L19 |21260 |20768 |  33 | 459 | 97.8%| 776.39 | | L43 |21260 |20374 |  34 | 852 | 96.0%|1482.20 |
   | L20 |21260 |20353 |  39 | 868 | 95.9%|1616.16 | | L44 |21260 |20383 |  48 | 829 | 96.1%|1431.79 |
   | L21 |21260 |20485 |  38 | 737 | 96.5%|1921.24 | | L45 |21260 |20378 |  53 | 829 | 96.1%|1528.30 |
   | L22 |21260 |21010 |  12 | 238 | 98.9%| 614.72 | | L46 |21260 |21014 |   9 | 237 | 98.9%| 659.72 |
   | L23 |21260 |20648 |  24 | 588 | 97.2%|1101.93 | | L47 |21260 |20887 |  27 | 346 | 98.4%| 924.90 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 60034.16 MB (Load=4614.69 | Prefill=40605.50 | Warmup=0.00 | Decode=14813.97 MB)
   SSD Data/Token (Decode)      : Avg=224.454 MB/tok (Min=11.279 | P50=225.384 | P95=303.362 | Max=332.289 MB) | Prefill=19.827 MB/tok
   NVMe Batches / Requests      : 3988 Batches | 132894 Raw -> 127970 Merged (4924 LBA Merges, Avg 480.4 KB/io)
   SSD I/O Size Histogram       : <64K=34001 | 64K-512K=23582 | 512K-2M=69875 | >2M=512
   SSD Read Bandwidth (Active)  : Min=4.80 | Avg=338.43 | Peak=5134.90 MB/s | WallAmort=72.45 MB/s
   OS Kernel I/O Verification   : Read=60054.43 MB | Write=594.14 MB | Syscalls=137491
   Sync Stall vs Async DMA      : SyncStall=144926.57 ms | AsyncOverlapped=158472.45 ms (52.2% Overlapped)
   RAM Traffic & Active BW      : 5687.55 GB moved | Active=8.73 GB/s | WallAmort=6.86 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=771.98s (93.2%, 40605.50 MB SSD) | Decode=56.62s (6.8%, 14813.97 MB SSD)
   CPU Time & Utilization       : User=2402.750s + Sys=42.219s (Wall=858.245s) | SysUtil=71.2% | ThrUtil=71.2% | 65.88 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 334400.42 ms (158183.7 us/tok | 40.36%)
   MoE AVX2 Q8 Expert Compute   : 312011.10 ms (147592.8 us/tok | 37.66%)
   Router + Lookahead Dispatch  :  18947.94 ms ( 8963.1 us/tok |  2.29%)
   LM Head Output Projection    :   4821.44 ms ( 2280.7 us/tok |  0.58%)
   Foreground NVMe Sync Stall   : 144926.57 ms (68555.6 us/tok | 17.49%)
   Unaccounted / OMP & Sampling :  13489.37 ms ( 6381.0 us/tok |  1.63%) | Total Wall=828596.84 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    91.34%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.16%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.01%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.07%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.42%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_qwen38_colibri_bench.log`
```text
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=515.0s) ===
[gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
[gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
== Qwen3.8-Flash-Next native text engine | cache=72/layer | CPU ==
[tok] loaded 248320 base pieces + 33 added tokens (max id 248319) from D:/apex_d_drive/models/qwen38/tokenizer.json
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=515.0s
[qwen38] native text weights: prefix=model, 48 layers, PLE=1, cache=72/layer, FP8=native, BF16=native (resident matrices 4.40 GiB)
[qwen38] MTP head mtp.*: wiring b (a norm per stream, fc_hidden per stream), RoPE base 1e+07, 96.86 MiB resident; routed experts Q8_0 from the snapshot (its own GGUF), cache 72 (Q38_MTP_CAP) x 4.98 MiB = 0.35 GiB full
[qwen38] MTP norm weights, mean: embedding -0.7642, hidden -0.3284, mixer 3.7881 (q38_rms0 scales by 1+w; a plain norm's weights would sit near 1)
[qwen38] trunk: 62 matrices int8 on the CPU (0.08 GiB, 0.28 GiB of BF16 released) in 0.2s; Q38_TRUNK_CPU_INT8=0 keeps BF16
[qwen38 MTP] draft vocabulary: the lm_head has no int8 rows on the host, so the head scores the whole vocabulary (Q38_MTP_VOCAB=0 silences this)
[qwen38] routed experts: GGUF IQ2_XXS/IQ2_XXS/IQ4_NL (layer 0), 1.68 MiB per expert; cache 72/layer
[qwen38] trunk: 62 int8 matrices interleaved by 16 for the CPU in 0.03s (Q38_ILV16=0 keeps the rows)
resident weights loaded in 20.6s | RSS after load: 4.60 GB
[qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.0s / cutoff=515.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=515.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=60.1s / cutoff=515.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=75.1s / cutoff=515.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=90.1s / cutoff=515.0s
TTFT: 42.31 s (time to first token)
[qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
[qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
[qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes

PEAK RSS: 10.76 GB
Expert cache hit rate: 62.0% (hit=15849 miss=9733)
Speed: 0.39 tok/s (81.6s for 32 tokens)
[STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage
  [COMP-LIVE] Colibri-Qwen38: elapsed=105.1s / cutoff=515.0s

Reference: 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 
C engine : 220 248046 198 248045 74455 198 248068 198 760 1156 682 3106 1092 7701 310 381 264 7132 36412 2805 269 82987 886 314 5587 13 6558 728 22903 411 25 271 Text      :  <|im_end|>
<|im_start|>assistant
<think>
The user has sent what appears to be a garbled/corrupted string of characters. Let me analyze this:



Matching tokens: 0/32
=== [Colibri-Qwen38] Finished rc=1 elapsed=105.63s cancelled=False ===
```

### 📄 `12_qwen38_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 1.40 | 1.14 | 820.66 | 92.28% | 295.53 | 14056.30 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 5.72 | 3.65 | 251.00 | 98.52% | 290.71 | 14718.59 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.65 | 1.17 | 748.94 | 97.54% | 338.43 | 13417.81 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.39 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
