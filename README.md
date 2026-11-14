<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#37 (Run ID `43631529363`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43631529363)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-14 19:46:30 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T19:20:13.475Z] ================================================================================
[2026-11-14T19:20:13.493Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T19:20:13.495Z] ================================================================================
[2026-11-14T19:20:17.655Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T19:20:17.817Z] --------------------------------------------------------------------------------
[2026-11-14T19:20:17.818Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.11 GB / 149.89 GB
[2026-11-14T19:20:17.819Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-14T19:20:17.820Z]  [Disk Telemetry] Total Combined Usable Free Space: 247.98 GB
[2026-11-14T19:20:17.832Z] --------------------------------------------------------------------------------
[2026-11-14T19:20:17.834Z]  [OK] Disk space verification passed: 247.98 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 938K Nov 14 19:20 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 938K Nov 14 19:20 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.33 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    589.45 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2454.34 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9582.34 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9843.73 MB/s
   RND4K Q32T16 Read                  :    765.61 MB/s (  195997 IOPS)
   RND4K Q1T1  Read                   :    503.44 MB/s (Latency: 7.76 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     75.09 GB/s
   AVX2 256-bit Sequential Write BW   :     66.32 GB/s
   STREAM Triad (A = B + s*C) BW      :      4.11 GB/s
   Random Pointer-Chase Latency       :     69.35 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.55 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.28 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.83 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1708.67 tps | Avg=1708.67 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=60.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1549.10 tps | Avg=1624.98 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=60.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1394.15 tps | Avg=1539.99 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=61.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1257.38 tps | Avg=1458.06 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=61.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1140.43 tps | Avg=1381.13 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=61.7 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=999.38 tps | Avg=1298.46 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=61.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=945.90 tps | Avg=1232.82 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=62.2 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=857.69 tps | Avg=1168.91 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=62.5 MB
[LIVE-DECODE] 8/32 tok | Avg=75.47 tps | Hit=100.0% (LA:+0.0%) | NVMe=3265.2 MB/s (6.58 MB) | RSS=70.9 MB
[LIVE-DECODE] 16/32 tok | Avg=98.81 tps | Hit=100.0% (LA:+0.0%) | NVMe=3265.2 MB/s (6.58 MB) | RSS=70.9 MB
[LIVE-DECODE] 24/32 tok | Avg=110.79 tps | Hit=100.0% (LA:+0.0%) | NVMe=3265.2 MB/s (6.58 MB) | RSS=70.9 MB
[LIVE-DECODE] 31/32 tok | Avg=116.24 tps | Hit=100.0% (LA:+0.0%) | NVMe=3265.2 MB/s (6.58 MB) | RSS=70.9 MB

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
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=70.86 MB | Peak=78.33 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1752.06 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |   19.82 | 48 |  0 |  0 |     0.0 |
   |    3 |      55 | tok_55         |  162.07 | 100.0% |     251 |  153.28 |   20.04 | 48 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  156.13 | 100.0% |     251 |  144.98 |   16.50 | 36 |  0 |  0 |     0.0 |
   |    5 |     246 | tok_246        |  161.71 | 100.0% |      55 |  147.08 |   16.61 | 36 |  0 |  0 |     0.0 |
   |    6 |     251 | tok_251        |  129.93 | 100.0% |     229 |  114.13 |    5.51 | 12 |  0 |  0 |     0.0 |
   |    7 |     199 | tok_199        |  140.67 |  66.3% |      71 |  139.99 |    5.47 | 12 |  0 |  0 |     0.0 |
   |    8 |      55 | tok_55         |  162.64 | 100.0% |     251 |  151.50 |    5.54 | 12 |  0 |  0 |     0.0 |
   |   17 |      21 | tok_21         |  162.32 |  57.0% |      86 |  162.03 |   17.33 | 36 |  0 |  0 |     0.0 |
   |    9 |     246 | tok_246        |  160.62 | 100.0% |      55 |  147.78 |   16.51 | 36 |  0 |  0 |     0.0 |
   |   25 |     119 | tok_119        |  190.28 | 100.0% |      55 |  146.04 |   16.03 | 36 |  0 |  0 |     0.0 |
   |   20 |      55 | tok_55         |  167.21 |  94.7% |     251 |  164.33 |    5.83 | 12 |  0 |  0 |     0.0 |
   |   29 |      55 | tok_55         |  170.19 | 100.0% |     251 |  153.56 |    5.61 | 12 |  0 |  0 |     0.0 |
   |   30 |     199 | tok_199        |  145.48 |  99.9% |      71 |  138.84 |   16.67 | 60 |  0 |  0 |     0.0 |
   |   31 |      55 | tok_55         |  163.52 | 100.0% |     251 |  152.05 |    5.53 | 12 |  0 |  0 |     0.0 |
   |   32 |     199 | tok_199        |  139.62 |  96.9% |      71 |  136.19 |    5.53 | 12 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.752s, TTFT=1752.06ms): Avg=1168.91 | Min=857.69 | Max=1708.67 tps
   Prefill Chunks (8): C1:256t/1708.7tps/100% | C2:256t/1549.1tps/100% | C3:256t/1394.2tps/100% | C4:256t/1257.4tps/100%
                       C5:256t/1140.4tps/100% | C6:256t/999.4tps/100% | C7:256t/945.9tps/100% | C8:256t/857.7tps/100%
   Decode  (31 tok, 0.267s): Avg=116.24 | Min=49.89 | Max=183.35 tps
   Latency (ms) : Min=5.45 | P10=5.47 | P25=5.49 | P50=5.54 | P75=16.03 | P90=16.67 | P95=19.82 | P99=20.04 | Max=20.04
   Mean/SD/Jitt : Mean=8.60ms | StdDev=5.27ms | Jitter=3.51ms | Hist(<25/50/100/200/>200ms): 31/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=419.62 | Avg=3265.17 | Peak=7961.78 MB/s | WallAmort=3.26 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=7.88 MB | Syscalls=165
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=0.99 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.74 GB/s | WallAmort=0.71 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.75s (86.8%, 0.00 MB SSD) | Decode=0.27s (13.2%, 0.00 MB SSD)
   CPU Time & Utilization       : User=2.219s + Sys=0.719s (Wall=2.049s) | SysUtil=35.8% | ThrUtil=35.8% | 33.15 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1708.22 ms (  821.7 us/tok | 84.62%)
   MoE AVX2 Q8 Expert Compute   :    218.26 ms (  105.0 us/tok | 10.81%)
   Router + Lookahead Dispatch  :     49.95 ms (   24.0 us/tok |  2.47%)
   LM Head Output Projection    :      5.24 ms (    2.5 us/tok |  0.26%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     37.09 ms (   17.8 us/tok |  1.84%) | Total Wall=2018.75 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    15.44%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.11%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.09%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    80.00%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.36%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2561.49 tps | Avg=2561.49 tps | Hit=99.2% | NVMe=3269.5 MB/s (24.91 MB, QD=64) | RSS=85.8 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2334.02 tps | Avg=2442.47 tps | Hit=99.2% | NVMe=4296.8 MB/s (42.92 MB, QD=64) | RSS=86.0 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2242.45 tps | Avg=2371.95 tps | Hit=99.2% | NVMe=4890.4 MB/s (61.04 MB, QD=64) | RSS=86.3 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2179.09 tps | Avg=2320.60 tps | Hit=99.2% | NVMe=5333.2 MB/s (79.10 MB, QD=64) | RSS=86.6 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2029.98 tps | Avg=2256.00 tps | Hit=99.2% | NVMe=5663.9 MB/s (97.14 MB, QD=64) | RSS=87.1 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1811.18 tps | Avg=2167.29 tps | Hit=99.2% | NVMe=5914.0 MB/s (115.20 MB, QD=64) | RSS=87.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1622.47 tps | Avg=2068.08 tps | Hit=99.2% | NVMe=6108.8 MB/s (133.27 MB, QD=64) | RSS=88.0 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1645.36 tps | Avg=2003.73 tps | Hit=99.2% | NVMe=6297.5 MB/s (151.30 MB, QD=64) | RSS=88.3 MB
[LIVE-DECODE] 8/32 tok | Avg=68.83 tps | Hit=99.2% (LA:+0.0%) | NVMe=6086.9 MB/s (155.02 MB) | RSS=100.5 MB
[LIVE-DECODE] 16/32 tok | Avg=89.64 tps | Hit=99.1% (LA:+0.1%) | NVMe=5964.5 MB/s (157.50 MB) | RSS=100.5 MB
[LIVE-DECODE] 25/32 tok | Avg=113.62 tps | Hit=99.1% (LA:+0.2%) | NVMe=5864.3 MB/s (158.94 MB) | RSS=100.5 MB
[LIVE-DECODE] 33/32 tok | Avg=133.10 tps | Hit=99.1% (LA:+0.2%) | NVMe=5832.4 MB/s (160.48 MB) | RSS=100.5 MB

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
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=100.49 MB | Peak=111.64 MB
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
   |    1 |      49 | qtok_49        |   63.79 |  98.0% |     254 |   59.79 | 1022.09 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |   22.26 | 54 |  0 | 10 |  1279.0 |
   |    3 |      49 | qtok_49        |   64.76 |  99.9% |     177 |   57.43 |   22.23 | 51 |  8 |  5 |   755.5 |
   |    4 |     254 | qtok_254       |   51.96 |  89.9% |     229 |   49.75 |   17.40 | 47 |  0 |  1 |   303.0 |
   |    5 |      49 | qtok_49        |   69.73 |  99.7% |     177 |   63.67 |   18.38 | 44 |  0 |  4 |   469.5 |
   |    6 |     229 | qtok_229       |   50.30 |  93.3% |     254 |   47.41 |    5.79 | 15 |  1 |  0 |   230.5 |
   |    7 |      19 | qtok_19        |   81.50 |  96.5% |      63 |   78.17 |    5.82 | 12 |  4 |  0 |   119.5 |
   |    8 |      63 | qtok_63        |   86.30 |  99.6% |      19 |   80.66 |    5.80 | 15 |  1 |  0 |   119.5 |
   |   17 |      65 | qtok_65        |   59.40 |  95.1% |     209 |   56.43 |   19.72 | 36 |  2 | 10 |   913.5 |
   |    9 |     194 | qtok_194       |   63.76 | 100.0% |     118 |   41.99 |   18.54 | 44 |  0 |  4 |   525.0 |
   |   13 |     223 | qtok_223       |   70.42 |  99.2% |     159 |   65.56 |    7.63 | 16 |  0 |  0 |    64.0 |
   |   20 |     254 | qtok_254       |   60.90 | 100.0% |     229 |   50.50 |    6.00 | 11 |  5 |  0 |   175.0 |
   |   31 |     223 | qtok_223       |   72.59 |  99.9% |     159 |   65.60 |    3.43 | 48 |  7 |  9 |   192.9 |
   |   32 |      68 | qtok_68        |   72.59 |  99.9% |     159 |   65.60 |    3.43 |  0 |  0 |  0 |   192.9 |
   |   33 |      66 | qtok_66        |   72.59 |  99.9% |     159 |   65.60 |    3.43 |  0 |  0 |  0 |   192.9 |
   |   34 |     103 | qtok_103       |   72.59 |  99.9% |     159 |   65.60 |    3.43 |  0 |  0 |  0 |   192.9 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.022s, TTFT=1022.09ms): Avg=2003.73 | Min=1622.47 | Max=2561.49 tps
   Prefill Chunks (8): C1:256t/2561.5tps/99% | C2:256t/2334.0tps/99% | C3:256t/2242.4tps/99% | C4:256t/2179.1tps/99%
                       C5:256t/2030.0tps/99% | C6:256t/1811.2tps/99% | C7:256t/1622.5tps/99% | C8:256t/1645.4tps/99%
   Decode  (33 tok, 0.248s): Avg=133.10 | Min=44.93 | Max=330.79 tps
   Latency (ms) : Min=3.02 | P10=3.02 | P25=3.55 | P50=5.81 | P75=5.96 | P90=18.54 | P95=22.23 | P99=22.26 | Max=22.26
   Mean/SD/Jitt : Mean=7.51ms | StdDev=5.95ms | Jitter=2.48ms | Hist(<25/50/100/200/>200ms): 33/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=540.91 | Avg=5832.42 | Peak=11031.03 MB/s | WallAmort=126.36 MB/s
   OS Kernel I/O Verification   : Read=27.89 MB | Write=11.62 MB | Syscalls=480
   Sync Stall vs Async DMA      : SyncStall=7.29 ms | AsyncOverlapped=25.95 ms (78.1% Overlapped)
   RAM Traffic & Active BW      : 2.14 GB moved | Active=1.92 GB/s | WallAmort=1.68 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.02s (80.5%, 144.44 MB SSD) | Decode=0.25s (19.5%, 9.18 MB SSD)
   CPU Time & Utilization       : User=2.016s + Sys=0.406s (Wall=1.323s) | SysUtil=45.8% | ThrUtil=45.8% | 42.34 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    765.69 ms (  367.9 us/tok | 60.29%)
   MoE AVX2 Q8 Expert Compute   :    341.72 ms (  164.2 us/tok | 26.91%)
   Router + Lookahead Dispatch  :     69.34 ms (   33.3 us/tok |  5.46%)
   LM Head Output Projection    :      4.14 ms (    2.0 us/tok |  0.33%)
   Foreground NVMe Sync Stall   :      7.29 ms (    3.5 us/tok |  0.57%)
   Unaccounted / OMP & Sampling :     81.85 ms (   39.3 us/tok |  6.44%) | Total Wall=1270.03 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    18.82%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.91%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.13%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    67.92%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.22%  |
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
    "ttft_ms": 340.88,
    "avg_tps": 1507.85,
    "min_tps": 505.79,
    "max_tps": 1705.98
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 191.38,
    "min_tps": 87.55,
    "max_tps": 211.22,
    "p50_ms": 4.85,
    "p90_ms": 5.82,
    "p99_ms": 11.42,
    "mean_ms": 5.23,
    "jitter_ms": 0.54
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
    "avg_mbs": 3153.81,
    "peak_mbs": 6613.76,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.76
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
    "dense_attention": 419.77,
    "moe_compute": 96.43,
    "router_lookahead": 14.16,
    "lm_head": 6.35,
    "unaccounted": 7.95
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 79.15,
    "ram_bandwidth_pinning": 2.93,
    "expert_cache_lrfu": 15.41,
    "lookahead_parallel_overlap": 2.26,
    "ssd_nvme_throughput": 0.25,
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
    "ttft_ms": 340.82,
    "avg_tps": 1508.14,
    "min_tps": 534.87,
    "max_tps": 1752.47
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 179.87,
    "min_tps": 160.15,
    "max_tps": 186.48,
    "p50_ms": 5.5,
    "p90_ms": 5.84,
    "p99_ms": 6.24,
    "mean_ms": 5.56,
    "jitter_ms": 0.12
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
    "avg_mbs": 4309.53,
    "peak_mbs": 9083.93,
    "sync_wait_ms": 4.71,
    "async_overlap_ms": 12.3
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
    "dense_attention": 311.7,
    "moe_compute": 178.28,
    "router_lookahead": 18.13,
    "lm_head": 5.98,
    "unaccounted": 38.85
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 72.63,
    "ram_bandwidth_pinning": 4.04,
    "expert_cache_lrfu": 15.36,
    "lookahead_parallel_overlap": 5.34,
    "ssd_nvme_throughput": 2.63,
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
   Active Drive Space : 219.98 GB Total / 219.78 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    589.53 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2234.00 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9705.20 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11393.07 MB/s
   RND4K Q32T16 Read                  :    763.60 MB/s (  195481 IOPS)
   RND4K Q1T1  Read                   :    854.70 MB/s (Latency: 4.57 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     81.10 GB/s
   AVX2 256-bit Sequential Write BW   :     75.65 GB/s
   STREAM Triad (A = B + s*C) BW      :     46.11 GB/s
   Random Pointer-Chase Latency       :     57.90 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.61 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.60 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     27.12 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 28.06 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 163.33 MB/s (6.27s)
   Window #01 (308.0 MB in 0.50s):   610.66 MB/s (Uncached Direct Read)
   Window #02 (208.0 MB in 0.53s):   392.29 MB/s (Uncached Direct Read)
   Window #03 (152.0 MB in 0.55s):   274.04 MB/s (Uncached Direct Read)
   Window #04 (264.0 MB in 0.50s):   524.56 MB/s (Uncached Direct Read)
   Window #05 ( 92.0 MB in 0.21s):   428.28 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   443.79 MB/s (Min=274.04 | Max=610.66 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 219.78 GB / 219.98 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 266.45 MB/s (3.84s)
   Window #01 (280.0 MB in 0.51s):   551.15 MB/s (Uncached Direct Read)
   Window #02 (268.0 MB in 0.50s):   533.95 MB/s (Uncached Direct Read)
   Window #03 (268.0 MB in 0.50s):   533.81 MB/s (Uncached Direct Read)
   Window #04 (208.0 MB in 0.39s):   533.43 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   538.38 MB/s (Min=533.43 | Max=551.15 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: qwen38 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (0.010 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 100.00% (0.01/0.01 GB) @ 106.3 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (43.792 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  11.42% (5.00/43.79 GB) @ 201.8 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  22.84% (10.00/43.79 GB) @ 206.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  34.25% (15.00/43.79 GB) @ 186.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  45.67% (20.00/43.79 GB) @ 198.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  57.09% (25.00/43.79 GB) @ 202.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  68.51% (30.00/43.79 GB) @ 204.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  79.92% (35.00/43.79 GB) @ 195.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  91.34% (40.00/43.79 GB) @ 158.2 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf: 100.00% (43.79/43.79 GB) @ 144.6 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (26.822 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  18.64% (5.00/26.82 GB) @ 227.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  37.28% (10.00/26.82 GB) @ 239.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  55.92% (15.00/26.82 GB) @ 228.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  74.57% (20.00/26.82 GB) @ 223.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  93.21% (25.00/26.82 GB) @ 225.0 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf: 100.00% (26.82/26.82 GB) @ 222.9 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/MTP/mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (2.595 GB) -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Sequential Non-Truncate)
  [DL] mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 100.00% (2.60/2.60 GB) @ 39.5 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=78,618,661,594 (73.22 GB) | Elapsed=501.63s
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
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7134.52 MB (3438 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=2.45 tps | Avg=2.45 tps | Hit=88.2% | NVMe=538.6 MB/s (10527.38 MB, QD=64) | RSS=12933.2 MB
[LIVE-DECODE] 8/32 tok | Avg=1.55 tps | Hit=89.5% (LA:+1.0%) | NVMe=575.4 MB/s (12500.20 MB) | RSS=13094.2 MB
[LIVE-DECODE] 16/32 tok | Avg=1.66 tps | Hit=90.5% (LA:+1.1%) | NVMe=610.0 MB/s (13848.57 MB) | RSS=13093.9 MB
[LIVE-DECODE] 24/32 tok | Avg=1.71 tps | Hit=91.4% (LA:+1.3%) | NVMe=645.4 MB/s (15258.85 MB) | RSS=13069.4 MB
[LIVE-DECODE] 32/32 tok | Avg=1.67 tps | Hit=92.3% (LA:+1.4%) | NVMe=667.5 MB/s (16322.52 MB) | RSS=13060.1 MB

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
   LRFU Cache / Staging Ring    : 7134.52 MB (3438/25088 exp = 13.70% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=13060.07 MB | Peak=13167.70 MB
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
   |    1 |      17 | 2              |    9.31 |   2.7% |     350 |    9.23 | 26101.06 |  0 |  0 |  0 |     0.0 |
   |    2 |      20 | 5              |    9.48 |   2.8% |      22 |    9.31 |  789.48 |402 | 67 | 11 | 342964.0 |
   |    3 |     220 |                |   11.82 |  14.5% |     264 |   11.73 |  723.67 |395 | 81 |  4 | 334943.0 |
   |    4 |     220 |                |   11.57 |  15.6% |     198 |   10.03 |  681.41 |417 | 58 |  5 | 294668.0 |
   |    5 |     198 | \n             |   13.28 |  58.0% |     539 |    9.97 |  644.95 |458 | 22 |  0 | 226764.0 |
   |    6 |     198 | \n             |   10.52 |   9.8% |      84 |    8.46 |  628.76 |430 | 49 |  1 | 249847.0 |
   |    7 |      17 | 2              |    8.72 |   1.2% |      64 |    8.52 |  567.79 |457 | 23 |  0 | 182118.0 |
   |    8 |     198 | \n             |   13.23 |  57.3% |     264 |    9.99 |  590.23 |446 | 34 |  0 | 222993.0 |
   |   15 |     198 | \n             |   10.62 |  14.0% |      17 |    8.27 |  629.28 |448 | 29 |  3 | 242664.0 |
   |   16 |     198 | \n             |    8.86 |   2.1% |      17 |    7.21 |  608.88 |470 | 10 |  0 | 181964.0 |
   |   26 |      17 | 2              |   12.47 |  23.4% |      16 |   12.03 |  583.63 |448 | 32 |  0 | 242114.0 |
   |   27 |      17 | 2              |   10.84 |  13.5% |      16 |    9.80 |  571.84 |453 | 26 |  1 | 196693.0 |
   |   30 |      17 | 2              |   11.66 |  15.1% |      15 |   10.60 |  537.81 |472 |  8 |  0 | 165764.0 |
   |   31 |      16 | 1              |   10.29 |   5.2% |      17 |   10.28 |  768.35 |3316 |  1 | 43 | 23511.7 |
   |   32 |      17 | 2              |   10.29 |   5.2% |      17 |   10.28 |  768.35 |  0 |  0 |  0 | 23511.7 |
   |   33 |      16 | 1              |   10.29 |   5.2% |      17 |   10.28 |  768.35 |  0 |  0 |  0 | 23511.7 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 26.101s, TTFT=26101.06ms): Avg=2.45 | Min=2.45 | Max=2.45 tps
   Prefill Chunks (1): C1:64t/2.5tps/88%
   Decode  (32 tok, 19.130s): Avg=1.67 | Min=1.27 | Max=1.90 tps
   Latency (ms) : Min=526.87 | P10=536.80 | P25=541.83 | P50=558.65 | P75=629.28 | P90=768.35 | P95=768.35 | P99=789.48 | Max=789.48
   Mean/SD/Jitt : Mean=597.81ms | StdDev=80.19ms | Jitter=29.76ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 2/3 draft tokens accepted (66.7% verified accept | Net 1.07x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (48000): RawRAM=43661 (90.96%) | Lookahead=655 (+1.36%) | ColdMiss=3684 (7.67%) | EFF HIT=92.33%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 2869 prefetched -> 945 consumed (32.9% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1000 |  723 |  58 | 219 | 78.1%| 464.94 | | L24 | 1000 |  946 |   8 |  46 | 95.4%| 139.11 |
   | L01 | 1000 |  861 |  46 |  93 | 90.7%| 395.95 | | L25 | 1000 |  936 |  11 |  53 | 94.7%| 142.87 |
   | L02 | 1000 |  882 |  11 | 107 | 89.3%| 377.34 | | L26 | 1000 |  916 |  13 |  71 | 92.9%| 184.23 |
   | L03 | 1000 |  943 |   0 |  57 | 94.3%| 469.97 | | L27 | 1000 |  925 |  10 |  65 | 93.5%| 236.87 |
   | L04 | 1000 |  938 |   3 |  59 | 94.1%| 273.93 | | L28 | 1000 |  900 |  21 |  79 | 92.1%| 253.78 |
   | L05 | 1000 |  920 |  11 |  69 | 93.1%| 308.30 | | L29 | 1000 |  915 |  10 |  75 | 92.5%| 154.13 |
   | L06 | 1000 |  921 |  18 |  61 | 93.9%| 227.47 | | L30 | 1000 |  884 |  16 | 100 | 90.0%| 195.90 |
   | L07 | 1000 |  920 |  20 |  60 | 94.0%| 144.87 | | L31 | 1000 |  890 |  15 |  95 | 90.5%| 193.02 |
   | L08 | 1000 |  950 |  10 |  40 | 96.0%|  92.14 | | L32 | 1000 |  918 |   6 |  76 | 92.4%| 195.51 |
   | L09 | 1000 |  940 |   7 |  53 | 94.7%| 115.80 | | L33 | 1000 |  909 |  14 |  77 | 92.3%| 149.80 |
   | L10 | 1000 |  933 |  12 |  55 | 94.5%| 104.59 | | L34 | 1000 |  911 |  10 |  79 | 92.1%| 155.57 |
   | L11 | 1000 |  946 |   3 |  51 | 94.9%| 133.23 | | L35 | 1000 |  922 |  10 |  68 | 93.2%| 123.88 |
   | L12 | 1000 |  921 |  13 |  66 | 93.4%| 214.31 | | L36 | 1000 |  908 |  15 |  77 | 92.3%| 182.93 |
   | L13 | 1000 |  911 |  17 |  72 | 92.8%| 157.01 | | L37 | 1000 |  921 |   7 |  72 | 92.8%| 171.07 |
   | L14 | 1000 |  901 |  20 |  79 | 92.1%| 182.93 | | L38 | 1000 |  932 |   4 |  64 | 93.6%| 218.07 |
   | L15 | 1000 |  904 |  20 |  76 | 92.4%| 225.59 | | L39 | 1000 |  921 |   9 |  70 | 93.0%| 227.47 |
   | L16 | 1000 |  921 |   5 |  74 | 92.6%| 169.19 | | L40 | 1000 |  904 |  11 |  85 | 91.5%| 278.22 |
   | L17 | 1000 |  923 |   8 |  69 | 93.1%| 167.31 | | L41 | 1000 |  899 |  11 |  90 | 91.0%| 154.13 |
   | L18 | 1000 |  911 |  17 |  72 | 92.8%| 195.51 | | L42 | 1000 |  872 |  21 | 107 | 89.3%| 257.84 |
   | L19 | 1000 |  923 |  11 |  66 | 93.4%| 145.48 | | L43 | 1000 |  901 |  12 |  87 | 91.3%| 205.98 |
   | L20 | 1000 |  889 |  15 |  96 | 90.4%| 191.58 | | L44 | 1000 |  891 |  18 |  91 | 90.9%| 168.53 |
   | L21 | 1000 |  894 |  13 |  93 | 90.7%| 392.90 | | L45 | 1000 |  882 |  21 |  97 | 90.3%| 240.55 |
   | L22 | 1000 |  933 |  14 |  53 | 94.7%| 187.99 | | L46 | 1000 |  916 |   9 |  75 | 92.5%| 253.52 |
   | L23 | 1000 |  929 |   9 |  62 | 93.8%| 161.33 | | L47 | 1000 |  905 |  12 |  83 | 91.7%| 274.46 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 16322.52 MB (Load=4614.69 | Prefill=5912.69 | Warmup=0.00 | Decode=5795.13 MB)
   SSD Data/Token (Decode)      : Avg=181.098 MB/tok (Min=22.961 | P50=182.220 | P95=327.093 | Max=334.926 MB) | Prefill=92.386 MB/tok
   NVMe Batches / Requests      : 1447 Batches | 22367 Raw -> 21628 Merged (739 LBA Merges, Avg 772.8 KB/io)
   SSD I/O Size Histogram       : <64K=1915 | 64K-512K=5149 | 512K-2M=14131 | >2M=433
   SSD Read Bandwidth (Active)  : Min=12.29 | Avg=667.46 | Peak=10822.16 MB/s | WallAmort=360.87 MB/s
   OS Kernel I/O Verification   : Read=16342.49 MB | Write=166.92 MB | Syscalls=31133
   Sync Stall vs Async DMA      : SyncStall=11190.60 ms | AsyncOverlapped=15984.72 ms (58.8% Overlapped)
   RAM Traffic & Active BW      : 410.37 GB moved | Active=13.32 GB/s | WallAmort=9.07 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=26.10s (57.7%, 5912.69 MB SSD) | Decode=19.13s (42.3%, 5795.13 MB SSD)
   CPU Time & Utilization       : User=102.641s + Sys=7.109s (Wall=59.233s) | SysUtil=46.3% | ThrUtil=46.3% | 42.85 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  14638.39 ms (152483.3 us/tok | 32.36%)
   MoE AVX2 Q8 Expert Compute   :  13632.94 ms (142009.8 us/tok | 30.14%)
   Router + Lookahead Dispatch  :    695.31 ms ( 7242.8 us/tok |  1.54%)
   LM Head Output Projection    :   2545.30 ms (26513.6 us/tok |  5.63%)
   Foreground NVMe Sync Stall   :  11190.60 ms (116568.7 us/tok | 24.74%)
   Unaccounted / OMP & Sampling :   2528.60 ms (26339.6 us/tok |  5.59%) | Total Wall=45231.14 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    76.24%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.37%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     8.34%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.21%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.84%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 61s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.64 GB Available
   Active Drive Space : 219.98 GB Total / 148.83 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    569.63 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2409.63 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9295.37 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11034.39 MB/s
   RND4K Q32T16 Read                  :    647.28 MB/s (  165705 IOPS)
   RND4K Q1T1  Read                   :    781.83 MB/s (Latency: 5.00 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     74.42 GB/s
   AVX2 256-bit Sequential Write BW   :     66.46 GB/s
   STREAM Triad (A = B + s*C) BW      :     44.35 GB/s
   Random Pointer-Chase Latency       :     82.87 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.44 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    200.24 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     25.74 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=7.42 tps | Avg=7.42 tps | Hit=91.8% | NVMe=556.7 MB/s (5363.65 MB, QD=64) | RSS=14217.5 MB

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
   LRFU Cache / Staging Ring    : 8481.32 MB (4087/25088 exp = 16.29% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.83 MB | End=14405.12 MB | Peak=14521.55 MB
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
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 12265.63 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  722.27 |474 |  6 |  0 | 72889.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  499.80 |478 |  2 |  0 | 57064.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  511.42 |480 |  0 |  0 | 51064.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  506.23 |479 |  1 |  0 | 54064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  482.61 |480 |  0 |  0 | 52339.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  491.89 |480 |  0 |  0 | 51064.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  492.10 |480 |  0 |  0 | 51064.0 |
   |   41 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.53 |228 |  0 |  0 |    64.0 |
   |   42 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.53 |  0 |  0 |  0 |    64.0 |
   |   43 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.53 |  0 |  0 |  0 |    64.0 |
   |   44 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.53 |  0 |  0 |  0 |    64.0 |
   |   61 |       0 | !              |     nan | 100.0% |       1 |     nan |  181.22 |228 |  0 |  0 |    64.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  181.22 |  0 |  0 |  0 |    64.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  181.22 |  0 |  0 |  0 |    64.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  181.22 |  0 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 12.266s, TTFT=12265.63ms): Avg=7.42 | Min=7.42 | Max=7.42 tps
   Prefill Chunks (1): C1:91t/7.4tps/92%
   Decode  (63 tok, 13.878s): Avg=4.54 | Min=1.38 | Max=5.60 tps
   Latency (ms) : Min=178.63 | P10=179.03 | P25=180.27 | P50=181.22 | P75=183.37 | P90=482.61 | P95=499.80 | P99=722.27 | Max=722.27
   Mean/SD/Jitt : Mean=220.29ms | StdDev=112.48ms | Jitter=9.92ms | Hist(<25/50/100/200/>200ms): 0/0/0/56/7
   MTP Head     : 42/42 draft tokens accepted (100.0% verified accept | Net 3.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (12189): RawRAM=11717 (96.13%) | Lookahead=9 (+0.07%) | ColdMiss=463 (3.80%) | EFF HIT=96.20%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 29 prefetched -> 16 consumed (55.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 95.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1266 |   9 | 265 | 82.8%| 461.57 | | L24 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L01 |  442 |  362 |   0 |  80 | 81.9%| 115.80 | | L25 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L02 |  442 |  369 |   0 |  73 | 83.5%| 122.97 | | L26 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
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
   Engine SSD Transfer Total    : 5747.57 MB (Load=4614.69 | Prefill=748.96 | Warmup=0.00 | Decode=383.92 MB)
   SSD Data/Token (Decode)      : Avg=6.094 MB/tok (Min=0.062 | P50=0.062 | P95=55.727 | Max=71.181 MB) | Prefill=8.230 MB/tok
   NVMe Batches / Requests      : 97 Batches | 5237 Raw -> 4214 Merged (1023 LBA Merges, Avg 1396.7 KB/io)
   SSD I/O Size Histogram       : <64K=2002 | 64K-512K=1134 | 512K-2M=672 | >2M=406
   SSD Read Bandwidth (Active)  : Min=2.37 | Avg=581.68 | Peak=21501.52 MB/s | WallAmort=219.84 MB/s (100.0% of 569.6 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=6342.92 MB | Write=300.73 MB | Syscalls=21269
   Sync Stall vs Async DMA      : SyncStall=1253.43 ms | AsyncOverlapped=1402.38 ms (52.8% Overlapped)
   RAM Traffic & Active BW      : 373.36 GB moved | Active=16.03 GB/s (36.1% STREAM) | WallAmort=14.28 GB/s (Max=44.35 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=12.27s (46.9%, 748.96 MB SSD) | Decode=13.88s (53.1%, 383.92 MB SSD)
   CPU Time & Utilization       : User=82.203s + Sys=5.719s (Wall=40.610s) | SysUtil=54.1% | ThrUtil=54.1% | 108.38 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  18042.96 ms (117162.1 us/tok | 69.01%)
   MoE AVX2 Q8 Expert Compute   :   3097.50 ms (20113.7 us/tok | 11.85%)
   Router + Lookahead Dispatch  :    953.59 ms ( 6192.1 us/tok |  3.65%)
   LM Head Output Projection    :   2156.28 ms (14001.8 us/tok |  8.25%)
   Foreground NVMe Sync Stall   :   1253.43 ms ( 8139.2 us/tok |  4.79%)
   Unaccounted / OMP & Sampling :    640.15 ms ( 4156.8 us/tok |  2.45%) | Total Wall=26143.91 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    68.93%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.64%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     7.64%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    16.01%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.78%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=8605.83 MB (4147 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=7.90 tps | Avg=7.90 tps | Hit=97.5% | NVMe=584.7 MB/s (5225.38 MB, QD=64) | RSS=14367.6 MB
[LIVE-PREFILL] 512/512 tok | Chunk=8.28 tps | Avg=8.08 tps | Hit=98.0% | NVMe=592.9 MB/s (5615.71 MB, QD=64) | RSS=14418.6 MB
[LIVE-DECODE] 11/128 tok | Avg=2.40 tps | Hit=98.2% (LA:+0.2%) | NVMe=617.2 MB/s (5988.84 MB) | RSS=14527.8 MB
[LIVE-DECODE] 19/128 tok | Avg=3.15 tps | Hit=98.2% (LA:+0.2%) | NVMe=617.4 MB/s (5991.02 MB) | RSS=14527.8 MB
[LIVE-DECODE] 27/128 tok | Avg=3.60 tps | Hit=98.3% (LA:+0.2%) | NVMe=617.4 MB/s (5991.52 MB) | RSS=14527.8 MB
[LIVE-DECODE] 35/128 tok | Avg=3.90 tps | Hit=98.3% (LA:+0.2%) | NVMe=617.5 MB/s (5992.02 MB) | RSS=14527.8 MB
[LIVE-DECODE] 43/128 tok | Avg=4.12 tps | Hit=98.3% (LA:+0.2%) | NVMe=617.5 MB/s (5992.52 MB) | RSS=14527.8 MB
[LIVE-DECODE] 51/128 tok | Avg=4.27 tps | Hit=98.3% (LA:+0.2%) | NVMe=617.5 MB/s (5993.02 MB) | RSS=14527.8 MB
[LIVE-DECODE] 59/128 tok | Avg=4.40 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.6 MB/s (5993.52 MB) | RSS=14527.8 MB
[LIVE-DECODE] 67/128 tok | Avg=4.43 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.6 MB/s (5994.02 MB) | RSS=14527.8 MB
[LIVE-DECODE] 75/128 tok | Avg=4.45 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.6 MB/s (5994.52 MB) | RSS=14514.3 MB
[LIVE-DECODE] 83/128 tok | Avg=4.41 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.7 MB/s (5995.02 MB) | RSS=14485.5 MB
[LIVE-DECODE] 91/128 tok | Avg=4.45 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.7 MB/s (5995.52 MB) | RSS=14485.5 MB
[LIVE-DECODE] 99/128 tok | Avg=4.52 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.7 MB/s (5996.02 MB) | RSS=14485.5 MB
[LIVE-DECODE] 107/128 tok | Avg=4.57 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.8 MB/s (5996.52 MB) | RSS=14485.5 MB
[LIVE-DECODE] 115/128 tok | Avg=4.62 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.8 MB/s (5997.02 MB) | RSS=14485.5 MB
[LIVE-DECODE] 123/128 tok | Avg=4.67 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.8 MB/s (5997.52 MB) | RSS=14485.5 MB
[LIVE-DECODE] 127/128 tok | Avg=4.69 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.8 MB/s (5997.77 MB) | RSS=14485.5 MB

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
   LRFU Cache / Staging Ring    : 8605.83 MB (4147/25088 exp = 16.53% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=14485.48 MB | Peak=14683.27 MB
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
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 63337.18 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  806.99 |474 |  6 |  0 | 74164.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  522.49 |480 |  0 |  0 | 52339.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  501.66 |480 |  0 |  0 | 51064.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  501.18 |480 |  0 |  0 | 51064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  503.33 |480 |  0 |  0 | 51064.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  504.78 |480 |  0 |  0 | 51064.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  487.52 |480 |  0 |  0 | 51064.0 |
   |   81 |       0 | !              |     nan | 100.0% |       1 |     nan |  252.00 |228 |  0 |  0 |    64.0 |
   |   82 |       0 | !              |     nan | 100.0% |       1 |     nan |  252.00 |  0 |  0 |  0 |    64.0 |
   |   83 |       0 | !              |     nan | 100.0% |       1 |     nan |  252.00 |  0 |  0 |  0 |    64.0 |
   |   84 |       0 | !              |     nan | 100.0% |       1 |     nan |  252.00 |  0 |  0 |  0 |    64.0 |
   |  125 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.71 |228 |  0 |  0 |    64.0 |
   |  126 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.71 |  0 |  0 |  0 |    64.0 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.71 |  0 |  0 |  0 |    64.0 |
   |  128 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.71 |  0 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 63.337s, TTFT=63337.18ms): Avg=8.08 | Min=7.90 | Max=8.28 tps
   Prefill Chunks (2): C1:256t/7.9tps/98% | C2:256t/8.3tps/98%
   Decode  (127 tok, 27.099s): Avg=4.69 | Min=1.24 | Max=5.50 tps
   Latency (ms) : Min=181.70 | P10=182.45 | P25=183.62 | P50=185.01 | P75=191.73 | P90=241.09 | P95=487.52 | P99=522.49 | Max=806.99
   Mean/SD/Jitt : Mean=213.38ms | StdDev=86.39ms | Jitter=7.00ms | Hist(<25/50/100/200/>200ms): 0/0/0/96/31
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
   SSD Read Bandwidth (Active)  : Min=11.05 | Avg=617.83 | Peak=21337.76 MB/s | WallAmort=66.32 MB/s
   OS Kernel I/O Verification   : Read=5124.99 MB | Write=263.39 MB | Syscalls=21109
   Sync Stall vs Async DMA      : SyncStall=906.92 ms | AsyncOverlapped=1253.30 ms (58.0% Overlapped)
   RAM Traffic & Active BW      : 830.03 GB moved | Active=9.86 GB/s | WallAmort=9.18 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=63.34s (70.0%, 1001.02 MB SSD) | Decode=27.10s (30.0%, 382.06 MB SSD)
   CPU Time & Utilization       : User=299.125s + Sys=10.219s (Wall=104.359s) | SysUtil=74.1% | ThrUtil=74.1% | 68.55 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  70635.07 ms (110540.0 us/tok | 78.10%)
   MoE AVX2 Q8 Expert Compute   :   9526.03 ms (14907.7 us/tok | 10.53%)
   Router + Lookahead Dispatch  :   3693.57 ms ( 5780.2 us/tok |  4.08%)
   LM Head Output Projection    :   4032.23 ms ( 6310.2 us/tok |  4.46%)
   Foreground NVMe Sync Stall   :    906.92 ms ( 1419.3 us/tok |  1.00%)
   Unaccounted / OMP & Sampling :   1642.80 ms ( 2570.9 us/tok |  1.82%) | Total Wall=90436.62 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    70.13%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.13%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.39%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    18.90%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     7.45%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 24401.8ms | usage={'prompt_tokens': 30, 'completion_tokens': 16, 'total_tokens': 46} | text='\n\n2223\n22222\n1\n2'
[Stage 3] /v1/chat/completions (stream=true SSE) 8249.1ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6960.21 MB (3354 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3.37 tps | Avg=3.37 tps | Hit=95.5% | NVMe=510.5 MB/s (13737.52 MB, QD=64) | RSS=12798.8 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=3.85 tps | Avg=3.59 tps | Hit=96.5% | NVMe=521.1 MB/s (18630.34 MB, QD=64) | RSS=12799.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=3.77 tps | Avg=3.65 tps | Hit=96.9% | NVMe=501.5 MB/s (23098.34 MB, QD=64) | RSS=12818.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=3.85 tps | Avg=3.70 tps | Hit=97.2% | NVMe=508.4 MB/s (27568.53 MB, QD=64) | RSS=12819.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=3.91 tps | Avg=3.74 tps | Hit=97.3% | NVMe=525.4 MB/s (32089.64 MB, QD=64) | RSS=12819.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=3.91 tps | Avg=3.77 tps | Hit=97.4% | NVMe=538.7 MB/s (36471.59 MB, QD=64) | RSS=12819.8 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=3.89 tps | Avg=3.78 tps | Hit=97.4% | NVMe=550.2 MB/s (40806.18 MB, QD=64) | RSS=12819.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=3.86 tps | Avg=3.79 tps | Hit=97.5% | NVMe=560.0 MB/s (45220.19 MB, QD=64) | RSS=12819.9 MB
[LIVE-DECODE] 8/64 tok | Avg=1.45 tps | Hit=97.5% (LA:+0.0%) | NVMe=573.9 MB/s (47477.66 MB) | RSS=12950.1 MB
[LIVE-DECODE] 13/64 tok | Avg=1.32 tps | Hit=97.5% (LA:+0.0%) | NVMe=585.5 MB/s (48842.86 MB) | RSS=12943.3 MB
[LIVE-DECODE] 16/64 tok | Avg=1.36 tps | Hit=97.5% (LA:+0.0%) | NVMe=591.0 MB/s (49550.33 MB) | RSS=12939.5 MB
[LIVE-DECODE] 24/64 tok | Avg=1.44 tps | Hit=97.5% (LA:+0.1%) | NVMe=606.8 MB/s (51654.88 MB) | RSS=12877.7 MB
[LIVE-DECODE] 27/64 tok | Avg=1.36 tps | Hit=97.5% (LA:+0.1%) | NVMe=613.0 MB/s (52499.89 MB) | RSS=12877.7 MB
[LIVE-DECODE] 32/64 tok | Avg=1.41 tps | Hit=97.5% (LA:+0.1%) | NVMe=621.7 MB/s (53528.06 MB) | RSS=12877.7 MB
[LIVE-DECODE] 40/64 tok | Avg=1.47 tps | Hit=97.5% (LA:+0.1%) | NVMe=636.9 MB/s (55271.61 MB) | RSS=12877.6 MB
[LIVE-DECODE] 48/64 tok | Avg=1.50 tps | Hit=97.5% (LA:+0.1%) | NVMe=649.6 MB/s (56964.14 MB) | RSS=12877.5 MB
[LIVE-DECODE] 52/64 tok | Avg=1.46 tps | Hit=97.5% (LA:+0.1%) | NVMe=657.3 MB/s (57834.00 MB) | RSS=12877.5 MB
[LIVE-DECODE] 56/64 tok | Avg=1.48 tps | Hit=97.5% (LA:+0.1%) | NVMe=665.4 MB/s (58721.65 MB) | RSS=12877.5 MB
[LIVE-DECODE] 66/64 tok | Avg=1.56 tps | Hit=97.5% (LA:+0.1%) | NVMe=678.0 MB/s (60065.80 MB) | RSS=12877.5 MB

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
   LRFU Cache / Staging Ring    : 6960.21 MB (3354/25088 exp = 13.37% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=12877.54 MB | Peak=13414.38 MB
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
   |    1 |      76 | m              |    7.55 |   0.9% |      16 |    7.49 | 539927.92 |  0 |  0 |  0 |     0.0 |
   |    2 |      84 | u              |    8.91 |   1.3% |     277 |    8.73 | 1002.67 |453 | 27 |  0 | 257289.0 |
   |    3 |      17 | 2              |   11.63 |   4.5% |      76 |   11.47 |  783.73 |454 | 21 |  5 | 268993.0 |
   |    4 |      17 | 2              |   12.28 |  15.1% |      24 |   11.21 |  613.66 |449 | 30 |  1 | 289714.0 |
   |    5 |      15 | 0              |    9.77 |   5.1% |      17 |    9.73 |  658.81 |438 | 40 |  2 | 310643.0 |
   |    6 |      17 | 2              |    9.65 |   2.1% |      18 |    9.16 |  649.22 |429 | 44 |  7 | 340264.0 |
   |    7 |      16 | 1              |   10.00 |   5.8% |      15 |    9.52 |  593.93 |450 | 29 |  1 | 279214.0 |
   |    8 |      17 | 2              |   12.82 |  20.9% |      18 |   12.19 |  611.65 |436 | 43 |  1 | 301714.0 |
   |   14 |      17 | 2              |   10.18 |   4.7% |      16 |   10.01 | 2022.67 |2302 | 10 | 88 | 304249.0 |
   |   28 |      18 | 3              |   12.60 |  17.4% |      17 |   12.49 | 1882.24 |2336 |  8 | 56 | 242307.0 |
   |   53 |      16 | 1              |    9.57 |   3.9% |      17 |    9.57 | 1877.76 |2345 |  3 | 52 | 237082.0 |
   |   44 |      18 | 3              |    9.89 |   5.1% |      17 |    9.68 |  770.84 |455 | 25 |  0 | 245589.0 |
   |   64 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  335.78 |1890 |  1 | 29 | 11549.2 |
   |   65 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  335.78 |  0 |  0 |  0 | 11549.2 |
   |   66 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  335.78 |  0 |  0 |  0 | 11549.2 |
   |   67 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  335.78 |  0 |  0 |  0 | 11549.2 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 539.928s, TTFT=539927.92ms): Avg=3.79 | Min=3.37 | Max=3.91 tps
   Prefill Chunks (8): C1:256t/3.4tps/95% | C2:256t/3.9tps/97% | C3:256t/3.8tps/97% | C4:256t/3.9tps/97%
                       C5:256t/3.9tps/97% | C6:256t/3.9tps/97% | C7:256t/3.9tps/97% | C8:256t/3.9tps/97%
   Decode  (66 tok, 42.394s): Avg=1.56 | Min=0.49 | Max=2.98 tps
   Latency (ms) : Min=335.78 | P10=543.38 | P25=554.68 | P50=568.80 | P75=611.65 | P90=717.14 | P95=1002.67 | P99=2022.67 | Max=2022.67
   Mean/SD/Jitt : Mean=642.34ms | StdDev=296.61ms | Jitter=167.61ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/66
   MTP Head     : 3/12 draft tokens accepted (25.0% verified accept | Net 1.05x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1020480): RawRAM=994009 (97.41%) | Lookahead=1430 (+0.14%) | ColdMiss=25041 (2.45%) | EFF HIT=97.55%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 7567 prefetched -> 2020 consumed (26.7% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.5% | @64= 97.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21260 |19114 | 108 |2038 | 90.4%|3615.09 | | L24 |21260 |21044 |  10 | 206 | 99.0%| 447.41 |
   | L01 |21260 |20608 |  70 | 582 | 97.3%|1375.85 | | L25 |21260 |21067 |   7 | 186 | 99.1%| 385.38 |
   | L02 |21260 |20591 |  10 | 659 | 96.9%|1758.69 | | L26 |21260 |20651 |  42 | 567 | 97.3%|1276.44 |
   | L03 |21260 |21177 |   4 |  79 | 99.6%|1043.33 | | L27 |21260 |20913 |  25 | 322 | 98.5%| 742.55 |
   | L04 |21260 |20968 |   8 | 284 | 98.7%|1052.12 | | L28 |21260 |20552 |  45 | 663 | 96.9%|1498.27 |
   | L05 |21260 |20883 |  28 | 349 | 98.4%|1024.54 | | L29 |21260 |20726 |  28 | 506 | 97.6%| 845.53 |
   | L06 |21260 |20914 |  24 | 322 | 98.5%| 881.67 | | L30 |21260 |20345 |  44 | 871 | 95.9%|1394.34 |
   | L07 |21260 |20892 |  28 | 340 | 98.4%| 663.72 | | L31 |21260 |20476 |  48 | 736 | 96.5%|1306.47 |
   | L08 |21260 |21188 |   1 |  71 | 99.7%| 164.36 | | L32 |21260 |20659 |  21 | 580 | 97.3%|1362.92 |
   | L09 |21260 |21184 |   1 |  75 | 99.6%| 103.34 | | L33 |21260 |20538 |  47 | 675 | 96.8%|1132.18 |
   | L10 |21260 |21037 |   7 | 216 | 99.0%| 298.83 | | L34 |21260 |20264 |  42 | 954 | 95.5%|1516.77 |
   | L11 |21260 |21180 |   5 |  75 | 99.6%| 143.19 | | L35 |21260 |20653 |  36 | 571 | 97.3%| 962.21 |
   | L12 |21260 |21077 |   9 | 174 | 99.2%| 571.48 | | L36 |21260 |20649 |  25 | 586 | 97.2%|1008.30 |
   | L13 |21260 |20982 |  18 | 260 | 98.8%| 499.83 | | L37 |21260 |20611 |  29 | 620 | 97.1%|1293.36 |
   | L14 |21260 |20867 |  45 | 348 | 98.4%| 798.00 | | L38 |21260 |20853 |  19 | 388 | 98.2%|1041.46 |
   | L15 |21260 |20729 |  43 | 488 | 97.7%|1099.73 | | L39 |21260 |20631 |  34 | 595 | 97.2%|1471.95 |
   | L16 |21260 |20644 |  22 | 594 | 97.2%|1246.36 | | L40 |21260 |20785 |  32 | 443 | 97.9%|1205.00 |
   | L17 |21260 |20470 |  32 | 758 | 96.4%|1594.14 | | L41 |21260 |20768 |  14 | 478 | 97.8%| 782.15 |
   | L18 |21260 |20559 |  32 | 669 | 96.9%|1398.63 | | L42 |21260 |20460 |  48 | 752 | 96.5%|1313.67 |
   | L19 |21260 |20768 |  34 | 458 | 97.8%| 776.39 | | L43 |21260 |20374 |  37 | 849 | 96.0%|1482.20 |
   | L20 |21260 |20353 |  39 | 868 | 95.9%|1616.16 | | L44 |21260 |20383 |  52 | 825 | 96.1%|1431.79 |
   | L21 |21260 |20485 |  41 | 734 | 96.5%|1921.24 | | L45 |21260 |20378 |  61 | 821 | 96.1%|1528.30 |
   | L22 |21260 |21010 |  12 | 238 | 98.9%| 614.72 | | L46 |21260 |21014 |  10 | 236 | 98.9%| 659.72 |
   | L23 |21260 |20648 |  25 | 587 | 97.2%|1101.93 | | L47 |21260 |20887 |  28 | 345 | 98.4%| 924.90 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 60065.80 MB (Load=4614.69 | Prefill=40605.50 | Warmup=0.00 | Decode=14845.61 MB)
   SSD Data/Token (Decode)      : Avg=224.934 MB/tok (Min=11.279 | P50=225.384 | P95=303.362 | Max=332.289 MB) | Prefill=19.827 MB/tok
   NVMe Batches / Requests      : 3988 Batches | 132948 Raw -> 128024 Merged (4924 LBA Merges, Avg 480.4 KB/io)
   SSD I/O Size Histogram       : <64K=34001 | 64K-512K=23601 | 512K-2M=69910 | >2M=512
   SSD Read Bandwidth (Active)  : Min=2.14 | Avg=678.05 | Peak=10308.97 MB/s | WallAmort=103.15 MB/s
   OS Kernel I/O Verification   : Read=60086.07 MB | Write=594.14 MB | Syscalls=137545
   Sync Stall vs Async DMA      : SyncStall=70050.49 ms | AsyncOverlapped=80194.89 ms (53.4% Overlapped)
   RAM Traffic & Active BW      : 5687.55 GB moved | Active=11.58 GB/s | WallAmort=9.77 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=539.93s (92.7%, 40605.50 MB SSD) | Decode=42.39s (7.3%, 14845.61 MB SSD)
   CPU Time & Utilization       : User=1824.312s + Sys=31.031s (Wall=597.855s) | SysUtil=77.6% | ThrUtil=77.6% | 71.76 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 230968.87 ms (109256.8 us/tok | 39.66%)
   MoE AVX2 Q8 Expert Compute   : 254958.57 ms (120604.8 us/tok | 43.78%)
   Router + Lookahead Dispatch  :  12100.72 ms ( 5724.1 us/tok |  2.08%)
   LM Head Output Projection    :   5082.53 ms ( 2404.2 us/tok |  0.87%)
   Foreground NVMe Sync Stall   :  70050.49 ms (33136.5 us/tok | 12.03%)
   Unaccounted / OMP & Sampling :   9160.97 ms ( 4333.5 us/tok |  1.57%) | Total Wall=582322.16 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    88.24%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.16%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.92%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.93%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.75%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=61.0s | Competitor drastic-underperform cutoff=305.0s (5x Apex)
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=305.0s) ===
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
  [Colibri-Qwen38] resident weights loaded in 9.5s | RSS after load: 4.60 GB
  [Colibri-Qwen38] [qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=305.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.1s / cutoff=305.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=305.0s
  [Colibri-Qwen38] TTFT: 23.10 s (time to first token)
  [Colibri-Qwen38] [qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
  [Colibri-Qwen38] [qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
  [Colibri-Qwen38] [qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes
  [Colibri-Qwen38] 
  [Colibri-Qwen38] PEAK RSS: 10.72 GB
  [Colibri-Qwen38] Expert cache hit rate: 62.0% (hit=15849 miss=9733)
  [Colibri-Qwen38] Speed: 0.72 tok/s (44.3s for 32 tokens)
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
=== [Colibri-Qwen38] Finished rc=1 elapsed=56.15s cancelled=False ===
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 2.45 | 1.67 | 558.65 | 92.33% | 667.46 | 13167.70 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 8.08 | 4.69 | 185.01 | 98.52% | 617.83 | 14683.27 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 3.79 | 1.56 | 568.80 | 97.55% | 678.05 | 13414.38 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.72 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 938K Nov 14 19:20 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 938K Nov 14 19:20 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.33 GB Available
   Active Drive Space : 219.98 GB Total / 219.86 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    589.45 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2454.34 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9582.34 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9843.73 MB/s
   RND4K Q32T16 Read                  :    765.61 MB/s (  195997 IOPS)
   RND4K Q1T1  Read                   :    503.44 MB/s (Latency: 7.76 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     75.09 GB/s
   AVX2 256-bit Sequential Write BW   :     66.32 GB/s
   STREAM Triad (A = B + s*C) BW      :      4.11 GB/s
   Random Pointer-Chase Latency       :     69.35 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.55 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.28 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     26.83 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1708.67 tps | Avg=1708.67 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=60.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1549.10 tps | Avg=1624.98 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=60.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1394.15 tps | Avg=1539.99 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=61.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1257.38 tps | Avg=1458.06 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=61.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1140.43 tps | Avg=1381.13 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=61.7 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=999.38 tps | Avg=1298.46 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=61.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=945.90 tps | Avg=1232.82 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=62.2 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=857.69 tps | Avg=1168.91 tps | Hit=100.0% | NVMe=3265.2 MB/s (6.58 MB, QD=64) | RSS=62.5 MB
[LIVE-DECODE] 8/32 tok | Avg=75.47 tps | Hit=100.0% (LA:+0.0%) | NVMe=3265.2 MB/s (6.58 MB) | RSS=70.9 MB
[LIVE-DECODE] 16/32 tok | Avg=98.81 tps | Hit=100.0% (LA:+0.0%) | NVMe=3265.2 MB/s (6.58 MB) | RSS=70.9 MB
[LIVE-DECODE] 24/32 tok | Avg=110.79 tps | Hit=100.0% (LA:+0.0%) | NVMe=3265.2 MB/s (6.58 MB) | RSS=70.9 MB
[LIVE-DECODE] 31/32 tok | Avg=116.24 tps | Hit=100.0% (LA:+0.0%) | NVMe=3265.2 MB/s (6.58 MB) | RSS=70.9 MB

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
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=70.86 MB | Peak=78.33 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 1752.06 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |   19.82 | 48 |  0 |  0 |     0.0 |
   |    3 |      55 | tok_55         |  162.07 | 100.0% |     251 |  153.28 |   20.04 | 48 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  156.13 | 100.0% |     251 |  144.98 |   16.50 | 36 |  0 |  0 |     0.0 |
   |    5 |     246 | tok_246        |  161.71 | 100.0% |      55 |  147.08 |   16.61 | 36 |  0 |  0 |     0.0 |
   |    6 |     251 | tok_251        |  129.93 | 100.0% |     229 |  114.13 |    5.51 | 12 |  0 |  0 |     0.0 |
   |    7 |     199 | tok_199        |  140.67 |  66.3% |      71 |  139.99 |    5.47 | 12 |  0 |  0 |     0.0 |
   |    8 |      55 | tok_55         |  162.64 | 100.0% |     251 |  151.50 |    5.54 | 12 |  0 |  0 |     0.0 |
   |   17 |      21 | tok_21         |  162.32 |  57.0% |      86 |  162.03 |   17.33 | 36 |  0 |  0 |     0.0 |
   |    9 |     246 | tok_246        |  160.62 | 100.0% |      55 |  147.78 |   16.51 | 36 |  0 |  0 |     0.0 |
   |   25 |     119 | tok_119        |  190.28 | 100.0% |      55 |  146.04 |   16.03 | 36 |  0 |  0 |     0.0 |
   |   20 |      55 | tok_55         |  167.21 |  94.7% |     251 |  164.33 |    5.83 | 12 |  0 |  0 |     0.0 |
   |   29 |      55 | tok_55         |  170.19 | 100.0% |     251 |  153.56 |    5.61 | 12 |  0 |  0 |     0.0 |
   |   30 |     199 | tok_199        |  145.48 |  99.9% |      71 |  138.84 |   16.67 | 60 |  0 |  0 |     0.0 |
   |   31 |      55 | tok_55         |  163.52 | 100.0% |     251 |  152.05 |    5.53 | 12 |  0 |  0 |     0.0 |
   |   32 |     199 | tok_199        |  139.62 |  96.9% |      71 |  136.19 |    5.53 | 12 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.752s, TTFT=1752.06ms): Avg=1168.91 | Min=857.69 | Max=1708.67 tps
   Prefill Chunks (8): C1:256t/1708.7tps/100% | C2:256t/1549.1tps/100% | C3:256t/1394.2tps/100% | C4:256t/1257.4tps/100%
                       C5:256t/1140.4tps/100% | C6:256t/999.4tps/100% | C7:256t/945.9tps/100% | C8:256t/857.7tps/100%
   Decode  (31 tok, 0.267s): Avg=116.24 | Min=49.89 | Max=183.35 tps
   Latency (ms) : Min=5.45 | P10=5.47 | P25=5.49 | P50=5.54 | P75=16.03 | P90=16.67 | P95=19.82 | P99=20.04 | Max=20.04
   Mean/SD/Jitt : Mean=8.60ms | StdDev=5.27ms | Jitter=3.51ms | Hist(<25/50/100/200/>200ms): 31/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=419.62 | Avg=3265.17 | Peak=7961.78 MB/s | WallAmort=3.26 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=7.88 MB | Syscalls=165
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=0.99 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.74 GB/s | WallAmort=0.71 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.75s (86.8%, 0.00 MB SSD) | Decode=0.27s (13.2%, 0.00 MB SSD)
   CPU Time & Utilization       : User=2.219s + Sys=0.719s (Wall=2.049s) | SysUtil=35.8% | ThrUtil=35.8% | 33.15 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1708.22 ms (  821.7 us/tok | 84.62%)
   MoE AVX2 Q8 Expert Compute   :    218.26 ms (  105.0 us/tok | 10.81%)
   Router + Lookahead Dispatch  :     49.95 ms (   24.0 us/tok |  2.47%)
   LM Head Output Projection    :      5.24 ms (    2.5 us/tok |  0.26%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     37.09 ms (   17.8 us/tok |  1.84%) | Total Wall=2018.75 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    15.44%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.11%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.09%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    80.00%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.36%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2561.49 tps | Avg=2561.49 tps | Hit=99.2% | NVMe=3269.5 MB/s (24.91 MB, QD=64) | RSS=85.8 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2334.02 tps | Avg=2442.47 tps | Hit=99.2% | NVMe=4296.8 MB/s (42.92 MB, QD=64) | RSS=86.0 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2242.45 tps | Avg=2371.95 tps | Hit=99.2% | NVMe=4890.4 MB/s (61.04 MB, QD=64) | RSS=86.3 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2179.09 tps | Avg=2320.60 tps | Hit=99.2% | NVMe=5333.2 MB/s (79.10 MB, QD=64) | RSS=86.6 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2029.98 tps | Avg=2256.00 tps | Hit=99.2% | NVMe=5663.9 MB/s (97.14 MB, QD=64) | RSS=87.1 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1811.18 tps | Avg=2167.29 tps | Hit=99.2% | NVMe=5914.0 MB/s (115.20 MB, QD=64) | RSS=87.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1622.47 tps | Avg=2068.08 tps | Hit=99.2% | NVMe=6108.8 MB/s (133.27 MB, QD=64) | RSS=88.0 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1645.36 tps | Avg=2003.73 tps | Hit=99.2% | NVMe=6297.5 MB/s (151.30 MB, QD=64) | RSS=88.3 MB
[LIVE-DECODE] 8/32 tok | Avg=68.83 tps | Hit=99.2% (LA:+0.0%) | NVMe=6086.9 MB/s (155.02 MB) | RSS=100.5 MB
[LIVE-DECODE] 16/32 tok | Avg=89.64 tps | Hit=99.1% (LA:+0.1%) | NVMe=5964.5 MB/s (157.50 MB) | RSS=100.5 MB
[LIVE-DECODE] 25/32 tok | Avg=113.62 tps | Hit=99.1% (LA:+0.2%) | NVMe=5864.3 MB/s (158.94 MB) | RSS=100.5 MB
[LIVE-DECODE] 33/32 tok | Avg=133.10 tps | Hit=99.1% (LA:+0.2%) | NVMe=5832.4 MB/s (160.48 MB) | RSS=100.5 MB

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
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=100.49 MB | Peak=111.64 MB
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
   |    1 |      49 | qtok_49        |   63.79 |  98.0% |     254 |   59.79 | 1022.09 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |   22.26 | 54 |  0 | 10 |  1279.0 |
   |    3 |      49 | qtok_49        |   64.76 |  99.9% |     177 |   57.43 |   22.23 | 51 |  8 |  5 |   755.5 |
   |    4 |     254 | qtok_254       |   51.96 |  89.9% |     229 |   49.75 |   17.40 | 47 |  0 |  1 |   303.0 |
   |    5 |      49 | qtok_49        |   69.73 |  99.7% |     177 |   63.67 |   18.38 | 44 |  0 |  4 |   469.5 |
   |    6 |     229 | qtok_229       |   50.30 |  93.3% |     254 |   47.41 |    5.79 | 15 |  1 |  0 |   230.5 |
   |    7 |      19 | qtok_19        |   81.50 |  96.5% |      63 |   78.17 |    5.82 | 12 |  4 |  0 |   119.5 |
   |    8 |      63 | qtok_63        |   86.30 |  99.6% |      19 |   80.66 |    5.80 | 15 |  1 |  0 |   119.5 |
   |   17 |      65 | qtok_65        |   59.40 |  95.1% |     209 |   56.43 |   19.72 | 36 |  2 | 10 |   913.5 |
   |    9 |     194 | qtok_194       |   63.76 | 100.0% |     118 |   41.99 |   18.54 | 44 |  0 |  4 |   525.0 |
   |   13 |     223 | qtok_223       |   70.42 |  99.2% |     159 |   65.56 |    7.63 | 16 |  0 |  0 |    64.0 |
   |   20 |     254 | qtok_254       |   60.90 | 100.0% |     229 |   50.50 |    6.00 | 11 |  5 |  0 |   175.0 |
   |   31 |     223 | qtok_223       |   72.59 |  99.9% |     159 |   65.60 |    3.43 | 48 |  7 |  9 |   192.9 |
   |   32 |      68 | qtok_68        |   72.59 |  99.9% |     159 |   65.60 |    3.43 |  0 |  0 |  0 |   192.9 |
   |   33 |      66 | qtok_66        |   72.59 |  99.9% |     159 |   65.60 |    3.43 |  0 |  0 |  0 |   192.9 |
   |   34 |     103 | qtok_103       |   72.59 |  99.9% |     159 |   65.60 |    3.43 |  0 |  0 |  0 |   192.9 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.022s, TTFT=1022.09ms): Avg=2003.73 | Min=1622.47 | Max=2561.49 tps
   Prefill Chunks (8): C1:256t/2561.5tps/99% | C2:256t/2334.0tps/99% | C3:256t/2242.4tps/99% | C4:256t/2179.1tps/99%
                       C5:256t/2030.0tps/99% | C6:256t/1811.2tps/99% | C7:256t/1622.5tps/99% | C8:256t/1645.4tps/99%
   Decode  (33 tok, 0.248s): Avg=133.10 | Min=44.93 | Max=330.79 tps
   Latency (ms) : Min=3.02 | P10=3.02 | P25=3.55 | P50=5.81 | P75=5.96 | P90=18.54 | P95=22.23 | P99=22.26 | Max=22.26
   Mean/SD/Jitt : Mean=7.51ms | StdDev=5.95ms | Jitter=2.48ms | Hist(<25/50/100/200/>200ms): 33/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=540.91 | Avg=5832.42 | Peak=11031.03 MB/s | WallAmort=126.36 MB/s
   OS Kernel I/O Verification   : Read=27.89 MB | Write=11.62 MB | Syscalls=480
   Sync Stall vs Async DMA      : SyncStall=7.29 ms | AsyncOverlapped=25.95 ms (78.1% Overlapped)
   RAM Traffic & Active BW      : 2.14 GB moved | Active=1.92 GB/s | WallAmort=1.68 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.02s (80.5%, 144.44 MB SSD) | Decode=0.25s (19.5%, 9.18 MB SSD)
   CPU Time & Utilization       : User=2.016s + Sys=0.406s (Wall=1.323s) | SysUtil=45.8% | ThrUtil=45.8% | 42.34 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    765.69 ms (  367.9 us/tok | 60.29%)
   MoE AVX2 Q8 Expert Compute   :    341.72 ms (  164.2 us/tok | 26.91%)
   Router + Lookahead Dispatch  :     69.34 ms (   33.3 us/tok |  5.46%)
   LM Head Output Projection    :      4.14 ms (    2.0 us/tok |  0.33%)
   Foreground NVMe Sync Stall   :      7.29 ms (    3.5 us/tok |  0.57%)
   Unaccounted / OMP & Sampling :     81.85 ms (   39.3 us/tok |  6.44%) | Total Wall=1270.03 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    18.82%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.91%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.13%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    67.92%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.22%  |
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
    "ttft_ms": 340.88,
    "avg_tps": 1507.85,
    "min_tps": 505.79,
    "max_tps": 1705.98
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 191.38,
    "min_tps": 87.55,
    "max_tps": 211.22,
    "p50_ms": 4.85,
    "p90_ms": 5.82,
    "p99_ms": 11.42,
    "mean_ms": 5.23,
    "jitter_ms": 0.54
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
    "avg_mbs": 3153.81,
    "peak_mbs": 6613.76,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.76
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
    "dense_attention": 419.77,
    "moe_compute": 96.43,
    "router_lookahead": 14.16,
    "lm_head": 6.35,
    "unaccounted": 7.95
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 79.15,
    "ram_bandwidth_pinning": 2.93,
    "expert_cache_lrfu": 15.41,
    "lookahead_parallel_overlap": 2.26,
    "ssd_nvme_throughput": 0.25,
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
    "ttft_ms": 340.82,
    "avg_tps": 1508.14,
    "min_tps": 534.87,
    "max_tps": 1752.47
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 179.87,
    "min_tps": 160.15,
    "max_tps": 186.48,
    "p50_ms": 5.5,
    "p90_ms": 5.84,
    "p99_ms": 6.24,
    "mean_ms": 5.56,
    "jitter_ms": 0.12
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
    "avg_mbs": 4309.53,
    "peak_mbs": 9083.93,
    "sync_wait_ms": 4.71,
    "async_overlap_ms": 12.3
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
    "dense_attention": 311.7,
    "moe_compute": 178.28,
    "router_lookahead": 18.13,
    "lm_head": 5.98,
    "unaccounted": 38.85
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 72.63,
    "ram_bandwidth_pinning": 4.04,
    "expert_cache_lrfu": 15.36,
    "lookahead_parallel_overlap": 5.34,
    "ssd_nvme_throughput": 2.63,
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
   Active Drive Space : 219.98 GB Total / 219.78 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    589.53 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2234.00 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9705.20 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11393.07 MB/s
   RND4K Q32T16 Read                  :    763.60 MB/s (  195481 IOPS)
   RND4K Q1T1  Read                   :    854.70 MB/s (Latency: 4.57 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     81.10 GB/s
   AVX2 256-bit Sequential Write BW   :     75.65 GB/s
   STREAM Triad (A = B + s*C) BW      :     46.11 GB/s
   Random Pointer-Chase Latency       :     57.90 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.61 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    226.60 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     27.12 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 28.06 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 163.33 MB/s (6.27s)
   Window #01 (308.0 MB in 0.50s):   610.66 MB/s (Uncached Direct Read)
   Window #02 (208.0 MB in 0.53s):   392.29 MB/s (Uncached Direct Read)
   Window #03 (152.0 MB in 0.55s):   274.04 MB/s (Uncached Direct Read)
   Window #04 (264.0 MB in 0.50s):   524.56 MB/s (Uncached Direct Read)
   Window #05 ( 92.0 MB in 0.21s):   428.28 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   443.79 MB/s (Min=274.04 | Max=610.66 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 219.78 GB / 219.98 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 266.45 MB/s (3.84s)
   Window #01 (280.0 MB in 0.51s):   551.15 MB/s (Uncached Direct Read)
   Window #02 (268.0 MB in 0.50s):   533.95 MB/s (Uncached Direct Read)
   Window #03 (268.0 MB in 0.50s):   533.81 MB/s (Uncached Direct Read)
   Window #04 (208.0 MB in 0.39s):   533.43 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   538.38 MB/s (Min=533.43 | Max=551.15 MB/s)
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
   CPU Model          : AMD EPYC 9V74 80-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 13.64 GB Available
   Active Drive Space : 219.98 GB Total / 148.83 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    569.63 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   2409.63 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   9295.37 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  11034.39 MB/s
   RND4K Q32T16 Read                  :    647.28 MB/s (  165705 IOPS)
   RND4K Q1T1  Read                   :    781.83 MB/s (Latency: 5.00 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     74.42 GB/s
   AVX2 256-bit Sequential Write BW   :     66.46 GB/s
   STREAM Triad (A = B + s*C) BW      :     44.35 GB/s
   Random Pointer-Chase Latency       :     82.87 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     58.44 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    200.24 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     25.74 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=7.42 tps | Avg=7.42 tps | Hit=91.8% | NVMe=556.7 MB/s (5363.65 MB, QD=64) | RSS=14217.5 MB

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
   LRFU Cache / Staging Ring    : 8481.32 MB (4087/25088 exp = 16.29% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.83 MB | End=14405.12 MB | Peak=14521.55 MB
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
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 12265.63 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  722.27 |474 |  6 |  0 | 72889.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  499.80 |478 |  2 |  0 | 57064.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  511.42 |480 |  0 |  0 | 51064.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  506.23 |479 |  1 |  0 | 54064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  482.61 |480 |  0 |  0 | 52339.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  491.89 |480 |  0 |  0 | 51064.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  492.10 |480 |  0 |  0 | 51064.0 |
   |   41 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.53 |228 |  0 |  0 |    64.0 |
   |   42 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.53 |  0 |  0 |  0 |    64.0 |
   |   43 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.53 |  0 |  0 |  0 |    64.0 |
   |   44 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.53 |  0 |  0 |  0 |    64.0 |
   |   61 |       0 | !              |     nan | 100.0% |       1 |     nan |  181.22 |228 |  0 |  0 |    64.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  181.22 |  0 |  0 |  0 |    64.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  181.22 |  0 |  0 |  0 |    64.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  181.22 |  0 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 12.266s, TTFT=12265.63ms): Avg=7.42 | Min=7.42 | Max=7.42 tps
   Prefill Chunks (1): C1:91t/7.4tps/92%
   Decode  (63 tok, 13.878s): Avg=4.54 | Min=1.38 | Max=5.60 tps
   Latency (ms) : Min=178.63 | P10=179.03 | P25=180.27 | P50=181.22 | P75=183.37 | P90=482.61 | P95=499.80 | P99=722.27 | Max=722.27
   Mean/SD/Jitt : Mean=220.29ms | StdDev=112.48ms | Jitter=9.92ms | Hist(<25/50/100/200/>200ms): 0/0/0/56/7
   MTP Head     : 42/42 draft tokens accepted (100.0% verified accept | Net 3.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (12189): RawRAM=11717 (96.13%) | Lookahead=9 (+0.07%) | ColdMiss=463 (3.80%) | EFF HIT=96.20%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 29 prefetched -> 16 consumed (55.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 95.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1266 |   9 | 265 | 82.8%| 461.57 | | L24 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L01 |  442 |  362 |   0 |  80 | 81.9%| 115.80 | | L25 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
   | L02 |  442 |  369 |   0 |  73 | 83.5%| 122.97 | | L26 |  217 |  216 |   0 |   1 | 99.5%|   1.88 |
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
   Engine SSD Transfer Total    : 5747.57 MB (Load=4614.69 | Prefill=748.96 | Warmup=0.00 | Decode=383.92 MB)
   SSD Data/Token (Decode)      : Avg=6.094 MB/tok (Min=0.062 | P50=0.062 | P95=55.727 | Max=71.181 MB) | Prefill=8.230 MB/tok
   NVMe Batches / Requests      : 97 Batches | 5237 Raw -> 4214 Merged (1023 LBA Merges, Avg 1396.7 KB/io)
   SSD I/O Size Histogram       : <64K=2002 | 64K-512K=1134 | 512K-2M=672 | >2M=406
   SSD Read Bandwidth (Active)  : Min=2.37 | Avg=581.68 | Peak=21501.52 MB/s | WallAmort=219.84 MB/s (100.0% of 569.6 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=6342.92 MB | Write=300.73 MB | Syscalls=21269
   Sync Stall vs Async DMA      : SyncStall=1253.43 ms | AsyncOverlapped=1402.38 ms (52.8% Overlapped)
   RAM Traffic & Active BW      : 373.36 GB moved | Active=16.03 GB/s (36.1% STREAM) | WallAmort=14.28 GB/s (Max=44.35 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=12.27s (46.9%, 748.96 MB SSD) | Decode=13.88s (53.1%, 383.92 MB SSD)
   CPU Time & Utilization       : User=82.203s + Sys=5.719s (Wall=40.610s) | SysUtil=54.1% | ThrUtil=54.1% | 108.38 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  18042.96 ms (117162.1 us/tok | 69.01%)
   MoE AVX2 Q8 Expert Compute   :   3097.50 ms (20113.7 us/tok | 11.85%)
   Router + Lookahead Dispatch  :    953.59 ms ( 6192.1 us/tok |  3.65%)
   LM Head Output Projection    :   2156.28 ms (14001.8 us/tok |  8.25%)
   Foreground NVMe Sync Stall   :   1253.43 ms ( 8139.2 us/tok |  4.79%)
   Unaccounted / OMP & Sampling :    640.15 ms ( 4156.8 us/tok |  2.45%) | Total Wall=26143.91 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    68.93%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.64%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     7.64%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    16.01%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.78%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_qwen38_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7134.52 MB (3438 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=2.45 tps | Avg=2.45 tps | Hit=88.2% | NVMe=538.6 MB/s (10527.38 MB, QD=64) | RSS=12933.2 MB
[LIVE-DECODE] 8/32 tok | Avg=1.55 tps | Hit=89.5% (LA:+1.0%) | NVMe=575.4 MB/s (12500.20 MB) | RSS=13094.2 MB
[LIVE-DECODE] 16/32 tok | Avg=1.66 tps | Hit=90.5% (LA:+1.1%) | NVMe=610.0 MB/s (13848.57 MB) | RSS=13093.9 MB
[LIVE-DECODE] 24/32 tok | Avg=1.71 tps | Hit=91.4% (LA:+1.3%) | NVMe=645.4 MB/s (15258.85 MB) | RSS=13069.4 MB
[LIVE-DECODE] 32/32 tok | Avg=1.67 tps | Hit=92.3% (LA:+1.4%) | NVMe=667.5 MB/s (16322.52 MB) | RSS=13060.1 MB

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
   LRFU Cache / Staging Ring    : 7134.52 MB (3438/25088 exp = 13.70% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=13060.07 MB | Peak=13167.70 MB
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
   |    1 |      17 | 2              |    9.31 |   2.7% |     350 |    9.23 | 26101.06 |  0 |  0 |  0 |     0.0 |
   |    2 |      20 | 5              |    9.48 |   2.8% |      22 |    9.31 |  789.48 |402 | 67 | 11 | 342964.0 |
   |    3 |     220 |                |   11.82 |  14.5% |     264 |   11.73 |  723.67 |395 | 81 |  4 | 334943.0 |
   |    4 |     220 |                |   11.57 |  15.6% |     198 |   10.03 |  681.41 |417 | 58 |  5 | 294668.0 |
   |    5 |     198 | \n             |   13.28 |  58.0% |     539 |    9.97 |  644.95 |458 | 22 |  0 | 226764.0 |
   |    6 |     198 | \n             |   10.52 |   9.8% |      84 |    8.46 |  628.76 |430 | 49 |  1 | 249847.0 |
   |    7 |      17 | 2              |    8.72 |   1.2% |      64 |    8.52 |  567.79 |457 | 23 |  0 | 182118.0 |
   |    8 |     198 | \n             |   13.23 |  57.3% |     264 |    9.99 |  590.23 |446 | 34 |  0 | 222993.0 |
   |   15 |     198 | \n             |   10.62 |  14.0% |      17 |    8.27 |  629.28 |448 | 29 |  3 | 242664.0 |
   |   16 |     198 | \n             |    8.86 |   2.1% |      17 |    7.21 |  608.88 |470 | 10 |  0 | 181964.0 |
   |   26 |      17 | 2              |   12.47 |  23.4% |      16 |   12.03 |  583.63 |448 | 32 |  0 | 242114.0 |
   |   27 |      17 | 2              |   10.84 |  13.5% |      16 |    9.80 |  571.84 |453 | 26 |  1 | 196693.0 |
   |   30 |      17 | 2              |   11.66 |  15.1% |      15 |   10.60 |  537.81 |472 |  8 |  0 | 165764.0 |
   |   31 |      16 | 1              |   10.29 |   5.2% |      17 |   10.28 |  768.35 |3316 |  1 | 43 | 23511.7 |
   |   32 |      17 | 2              |   10.29 |   5.2% |      17 |   10.28 |  768.35 |  0 |  0 |  0 | 23511.7 |
   |   33 |      16 | 1              |   10.29 |   5.2% |      17 |   10.28 |  768.35 |  0 |  0 |  0 | 23511.7 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 26.101s, TTFT=26101.06ms): Avg=2.45 | Min=2.45 | Max=2.45 tps
   Prefill Chunks (1): C1:64t/2.5tps/88%
   Decode  (32 tok, 19.130s): Avg=1.67 | Min=1.27 | Max=1.90 tps
   Latency (ms) : Min=526.87 | P10=536.80 | P25=541.83 | P50=558.65 | P75=629.28 | P90=768.35 | P95=768.35 | P99=789.48 | Max=789.48
   Mean/SD/Jitt : Mean=597.81ms | StdDev=80.19ms | Jitter=29.76ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 2/3 draft tokens accepted (66.7% verified accept | Net 1.07x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (48000): RawRAM=43661 (90.96%) | Lookahead=655 (+1.36%) | ColdMiss=3684 (7.67%) | EFF HIT=92.33%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 2869 prefetched -> 945 consumed (32.9% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1000 |  723 |  58 | 219 | 78.1%| 464.94 | | L24 | 1000 |  946 |   8 |  46 | 95.4%| 139.11 |
   | L01 | 1000 |  861 |  46 |  93 | 90.7%| 395.95 | | L25 | 1000 |  936 |  11 |  53 | 94.7%| 142.87 |
   | L02 | 1000 |  882 |  11 | 107 | 89.3%| 377.34 | | L26 | 1000 |  916 |  13 |  71 | 92.9%| 184.23 |
   | L03 | 1000 |  943 |   0 |  57 | 94.3%| 469.97 | | L27 | 1000 |  925 |  10 |  65 | 93.5%| 236.87 |
   | L04 | 1000 |  938 |   3 |  59 | 94.1%| 273.93 | | L28 | 1000 |  900 |  21 |  79 | 92.1%| 253.78 |
   | L05 | 1000 |  920 |  11 |  69 | 93.1%| 308.30 | | L29 | 1000 |  915 |  10 |  75 | 92.5%| 154.13 |
   | L06 | 1000 |  921 |  18 |  61 | 93.9%| 227.47 | | L30 | 1000 |  884 |  16 | 100 | 90.0%| 195.90 |
   | L07 | 1000 |  920 |  20 |  60 | 94.0%| 144.87 | | L31 | 1000 |  890 |  15 |  95 | 90.5%| 193.02 |
   | L08 | 1000 |  950 |  10 |  40 | 96.0%|  92.14 | | L32 | 1000 |  918 |   6 |  76 | 92.4%| 195.51 |
   | L09 | 1000 |  940 |   7 |  53 | 94.7%| 115.80 | | L33 | 1000 |  909 |  14 |  77 | 92.3%| 149.80 |
   | L10 | 1000 |  933 |  12 |  55 | 94.5%| 104.59 | | L34 | 1000 |  911 |  10 |  79 | 92.1%| 155.57 |
   | L11 | 1000 |  946 |   3 |  51 | 94.9%| 133.23 | | L35 | 1000 |  922 |  10 |  68 | 93.2%| 123.88 |
   | L12 | 1000 |  921 |  13 |  66 | 93.4%| 214.31 | | L36 | 1000 |  908 |  15 |  77 | 92.3%| 182.93 |
   | L13 | 1000 |  911 |  17 |  72 | 92.8%| 157.01 | | L37 | 1000 |  921 |   7 |  72 | 92.8%| 171.07 |
   | L14 | 1000 |  901 |  20 |  79 | 92.1%| 182.93 | | L38 | 1000 |  932 |   4 |  64 | 93.6%| 218.07 |
   | L15 | 1000 |  904 |  20 |  76 | 92.4%| 225.59 | | L39 | 1000 |  921 |   9 |  70 | 93.0%| 227.47 |
   | L16 | 1000 |  921 |   5 |  74 | 92.6%| 169.19 | | L40 | 1000 |  904 |  11 |  85 | 91.5%| 278.22 |
   | L17 | 1000 |  923 |   8 |  69 | 93.1%| 167.31 | | L41 | 1000 |  899 |  11 |  90 | 91.0%| 154.13 |
   | L18 | 1000 |  911 |  17 |  72 | 92.8%| 195.51 | | L42 | 1000 |  872 |  21 | 107 | 89.3%| 257.84 |
   | L19 | 1000 |  923 |  11 |  66 | 93.4%| 145.48 | | L43 | 1000 |  901 |  12 |  87 | 91.3%| 205.98 |
   | L20 | 1000 |  889 |  15 |  96 | 90.4%| 191.58 | | L44 | 1000 |  891 |  18 |  91 | 90.9%| 168.53 |
   | L21 | 1000 |  894 |  13 |  93 | 90.7%| 392.90 | | L45 | 1000 |  882 |  21 |  97 | 90.3%| 240.55 |
   | L22 | 1000 |  933 |  14 |  53 | 94.7%| 187.99 | | L46 | 1000 |  916 |   9 |  75 | 92.5%| 253.52 |
   | L23 | 1000 |  929 |   9 |  62 | 93.8%| 161.33 | | L47 | 1000 |  905 |  12 |  83 | 91.7%| 274.46 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 16322.52 MB (Load=4614.69 | Prefill=5912.69 | Warmup=0.00 | Decode=5795.13 MB)
   SSD Data/Token (Decode)      : Avg=181.098 MB/tok (Min=22.961 | P50=182.220 | P95=327.093 | Max=334.926 MB) | Prefill=92.386 MB/tok
   NVMe Batches / Requests      : 1447 Batches | 22367 Raw -> 21628 Merged (739 LBA Merges, Avg 772.8 KB/io)
   SSD I/O Size Histogram       : <64K=1915 | 64K-512K=5149 | 512K-2M=14131 | >2M=433
   SSD Read Bandwidth (Active)  : Min=12.29 | Avg=667.46 | Peak=10822.16 MB/s | WallAmort=360.87 MB/s
   OS Kernel I/O Verification   : Read=16342.49 MB | Write=166.92 MB | Syscalls=31133
   Sync Stall vs Async DMA      : SyncStall=11190.60 ms | AsyncOverlapped=15984.72 ms (58.8% Overlapped)
   RAM Traffic & Active BW      : 410.37 GB moved | Active=13.32 GB/s | WallAmort=9.07 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=26.10s (57.7%, 5912.69 MB SSD) | Decode=19.13s (42.3%, 5795.13 MB SSD)
   CPU Time & Utilization       : User=102.641s + Sys=7.109s (Wall=59.233s) | SysUtil=46.3% | ThrUtil=46.3% | 42.85 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  14638.39 ms (152483.3 us/tok | 32.36%)
   MoE AVX2 Q8 Expert Compute   :  13632.94 ms (142009.8 us/tok | 30.14%)
   Router + Lookahead Dispatch  :    695.31 ms ( 7242.8 us/tok |  1.54%)
   LM Head Output Projection    :   2545.30 ms (26513.6 us/tok |  5.63%)
   Foreground NVMe Sync Stall   :  11190.60 ms (116568.7 us/tok | 24.74%)
   Unaccounted / OMP & Sampling :   2528.60 ms (26339.6 us/tok |  5.59%) | Total Wall=45231.14 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    76.24%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.37%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     8.34%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     7.21%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.84%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_qwen38_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=8605.83 MB (4147 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=7.90 tps | Avg=7.90 tps | Hit=97.5% | NVMe=584.7 MB/s (5225.38 MB, QD=64) | RSS=14367.6 MB
[LIVE-PREFILL] 512/512 tok | Chunk=8.28 tps | Avg=8.08 tps | Hit=98.0% | NVMe=592.9 MB/s (5615.71 MB, QD=64) | RSS=14418.6 MB
[LIVE-DECODE] 11/128 tok | Avg=2.40 tps | Hit=98.2% (LA:+0.2%) | NVMe=617.2 MB/s (5988.84 MB) | RSS=14527.8 MB
[LIVE-DECODE] 19/128 tok | Avg=3.15 tps | Hit=98.2% (LA:+0.2%) | NVMe=617.4 MB/s (5991.02 MB) | RSS=14527.8 MB
[LIVE-DECODE] 27/128 tok | Avg=3.60 tps | Hit=98.3% (LA:+0.2%) | NVMe=617.4 MB/s (5991.52 MB) | RSS=14527.8 MB
[LIVE-DECODE] 35/128 tok | Avg=3.90 tps | Hit=98.3% (LA:+0.2%) | NVMe=617.5 MB/s (5992.02 MB) | RSS=14527.8 MB
[LIVE-DECODE] 43/128 tok | Avg=4.12 tps | Hit=98.3% (LA:+0.2%) | NVMe=617.5 MB/s (5992.52 MB) | RSS=14527.8 MB
[LIVE-DECODE] 51/128 tok | Avg=4.27 tps | Hit=98.3% (LA:+0.2%) | NVMe=617.5 MB/s (5993.02 MB) | RSS=14527.8 MB
[LIVE-DECODE] 59/128 tok | Avg=4.40 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.6 MB/s (5993.52 MB) | RSS=14527.8 MB
[LIVE-DECODE] 67/128 tok | Avg=4.43 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.6 MB/s (5994.02 MB) | RSS=14527.8 MB
[LIVE-DECODE] 75/128 tok | Avg=4.45 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.6 MB/s (5994.52 MB) | RSS=14514.3 MB
[LIVE-DECODE] 83/128 tok | Avg=4.41 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.7 MB/s (5995.02 MB) | RSS=14485.5 MB
[LIVE-DECODE] 91/128 tok | Avg=4.45 tps | Hit=98.4% (LA:+0.2%) | NVMe=617.7 MB/s (5995.52 MB) | RSS=14485.5 MB
[LIVE-DECODE] 99/128 tok | Avg=4.52 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.7 MB/s (5996.02 MB) | RSS=14485.5 MB
[LIVE-DECODE] 107/128 tok | Avg=4.57 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.8 MB/s (5996.52 MB) | RSS=14485.5 MB
[LIVE-DECODE] 115/128 tok | Avg=4.62 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.8 MB/s (5997.02 MB) | RSS=14485.5 MB
[LIVE-DECODE] 123/128 tok | Avg=4.67 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.8 MB/s (5997.52 MB) | RSS=14485.5 MB
[LIVE-DECODE] 127/128 tok | Avg=4.69 tps | Hit=98.5% (LA:+0.2%) | NVMe=617.8 MB/s (5997.77 MB) | RSS=14485.5 MB

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
   LRFU Cache / Staging Ring    : 8605.83 MB (4147/25088 exp = 16.53% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=14485.48 MB | Peak=14683.27 MB
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
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 63337.18 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  806.99 |474 |  6 |  0 | 74164.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  522.49 |480 |  0 |  0 | 52339.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  501.66 |480 |  0 |  0 | 51064.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  501.18 |480 |  0 |  0 | 51064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  503.33 |480 |  0 |  0 | 51064.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  504.78 |480 |  0 |  0 | 51064.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  487.52 |480 |  0 |  0 | 51064.0 |
   |   81 |       0 | !              |     nan | 100.0% |       1 |     nan |  252.00 |228 |  0 |  0 |    64.0 |
   |   82 |       0 | !              |     nan | 100.0% |       1 |     nan |  252.00 |  0 |  0 |  0 |    64.0 |
   |   83 |       0 | !              |     nan | 100.0% |       1 |     nan |  252.00 |  0 |  0 |  0 |    64.0 |
   |   84 |       0 | !              |     nan | 100.0% |       1 |     nan |  252.00 |  0 |  0 |  0 |    64.0 |
   |  125 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.71 |228 |  0 |  0 |    64.0 |
   |  126 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.71 |  0 |  0 |  0 |    64.0 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.71 |  0 |  0 |  0 |    64.0 |
   |  128 |       0 | !              |     nan | 100.0% |       1 |     nan |  186.71 |  0 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 63.337s, TTFT=63337.18ms): Avg=8.08 | Min=7.90 | Max=8.28 tps
   Prefill Chunks (2): C1:256t/7.9tps/98% | C2:256t/8.3tps/98%
   Decode  (127 tok, 27.099s): Avg=4.69 | Min=1.24 | Max=5.50 tps
   Latency (ms) : Min=181.70 | P10=182.45 | P25=183.62 | P50=185.01 | P75=191.73 | P90=241.09 | P95=487.52 | P99=522.49 | Max=806.99
   Mean/SD/Jitt : Mean=213.38ms | StdDev=86.39ms | Jitter=7.00ms | Hist(<25/50/100/200/>200ms): 0/0/0/96/31
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
   SSD Read Bandwidth (Active)  : Min=11.05 | Avg=617.83 | Peak=21337.76 MB/s | WallAmort=66.32 MB/s
   OS Kernel I/O Verification   : Read=5124.99 MB | Write=263.39 MB | Syscalls=21109
   Sync Stall vs Async DMA      : SyncStall=906.92 ms | AsyncOverlapped=1253.30 ms (58.0% Overlapped)
   RAM Traffic & Active BW      : 830.03 GB moved | Active=9.86 GB/s | WallAmort=9.18 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=63.34s (70.0%, 1001.02 MB SSD) | Decode=27.10s (30.0%, 382.06 MB SSD)
   CPU Time & Utilization       : User=299.125s + Sys=10.219s (Wall=104.359s) | SysUtil=74.1% | ThrUtil=74.1% | 68.55 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  70635.07 ms (110540.0 us/tok | 78.10%)
   MoE AVX2 Q8 Expert Compute   :   9526.03 ms (14907.7 us/tok | 10.53%)
   Router + Lookahead Dispatch  :   3693.57 ms ( 5780.2 us/tok |  4.08%)
   LM Head Output Projection    :   4032.23 ms ( 6310.2 us/tok |  4.46%)
   Foreground NVMe Sync Stall   :    906.92 ms ( 1419.3 us/tok |  1.00%)
   Unaccounted / OMP & Sampling :   1642.80 ms ( 2570.9 us/tok |  1.82%) | Total Wall=90436.62 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    70.13%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.13%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.39%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    18.90%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     7.45%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_qwen38_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 24401.8ms | usage={'prompt_tokens': 30, 'completion_tokens': 16, 'total_tokens': 46} | text='\n\n2223\n22222\n1\n2'
[Stage 3] /v1/chat/completions (stream=true SSE) 8249.1ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_qwen38_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6960.21 MB (3354 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3.37 tps | Avg=3.37 tps | Hit=95.5% | NVMe=510.5 MB/s (13737.52 MB, QD=64) | RSS=12798.8 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=3.85 tps | Avg=3.59 tps | Hit=96.5% | NVMe=521.1 MB/s (18630.34 MB, QD=64) | RSS=12799.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=3.77 tps | Avg=3.65 tps | Hit=96.9% | NVMe=501.5 MB/s (23098.34 MB, QD=64) | RSS=12818.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=3.85 tps | Avg=3.70 tps | Hit=97.2% | NVMe=508.4 MB/s (27568.53 MB, QD=64) | RSS=12819.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=3.91 tps | Avg=3.74 tps | Hit=97.3% | NVMe=525.4 MB/s (32089.64 MB, QD=64) | RSS=12819.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=3.91 tps | Avg=3.77 tps | Hit=97.4% | NVMe=538.7 MB/s (36471.59 MB, QD=64) | RSS=12819.8 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=3.89 tps | Avg=3.78 tps | Hit=97.4% | NVMe=550.2 MB/s (40806.18 MB, QD=64) | RSS=12819.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=3.86 tps | Avg=3.79 tps | Hit=97.5% | NVMe=560.0 MB/s (45220.19 MB, QD=64) | RSS=12819.9 MB
[LIVE-DECODE] 8/64 tok | Avg=1.45 tps | Hit=97.5% (LA:+0.0%) | NVMe=573.9 MB/s (47477.66 MB) | RSS=12950.1 MB
[LIVE-DECODE] 13/64 tok | Avg=1.32 tps | Hit=97.5% (LA:+0.0%) | NVMe=585.5 MB/s (48842.86 MB) | RSS=12943.3 MB
[LIVE-DECODE] 16/64 tok | Avg=1.36 tps | Hit=97.5% (LA:+0.0%) | NVMe=591.0 MB/s (49550.33 MB) | RSS=12939.5 MB
[LIVE-DECODE] 24/64 tok | Avg=1.44 tps | Hit=97.5% (LA:+0.1%) | NVMe=606.8 MB/s (51654.88 MB) | RSS=12877.7 MB
[LIVE-DECODE] 27/64 tok | Avg=1.36 tps | Hit=97.5% (LA:+0.1%) | NVMe=613.0 MB/s (52499.89 MB) | RSS=12877.7 MB
[LIVE-DECODE] 32/64 tok | Avg=1.41 tps | Hit=97.5% (LA:+0.1%) | NVMe=621.7 MB/s (53528.06 MB) | RSS=12877.7 MB
[LIVE-DECODE] 40/64 tok | Avg=1.47 tps | Hit=97.5% (LA:+0.1%) | NVMe=636.9 MB/s (55271.61 MB) | RSS=12877.6 MB
[LIVE-DECODE] 48/64 tok | Avg=1.50 tps | Hit=97.5% (LA:+0.1%) | NVMe=649.6 MB/s (56964.14 MB) | RSS=12877.5 MB
[LIVE-DECODE] 52/64 tok | Avg=1.46 tps | Hit=97.5% (LA:+0.1%) | NVMe=657.3 MB/s (57834.00 MB) | RSS=12877.5 MB
[LIVE-DECODE] 56/64 tok | Avg=1.48 tps | Hit=97.5% (LA:+0.1%) | NVMe=665.4 MB/s (58721.65 MB) | RSS=12877.5 MB
[LIVE-DECODE] 66/64 tok | Avg=1.56 tps | Hit=97.5% (LA:+0.1%) | NVMe=678.0 MB/s (60065.80 MB) | RSS=12877.5 MB

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
   LRFU Cache / Staging Ring    : 6960.21 MB (3354/25088 exp = 13.37% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=12877.54 MB | Peak=13414.38 MB
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
   |    1 |      76 | m              |    7.55 |   0.9% |      16 |    7.49 | 539927.92 |  0 |  0 |  0 |     0.0 |
   |    2 |      84 | u              |    8.91 |   1.3% |     277 |    8.73 | 1002.67 |453 | 27 |  0 | 257289.0 |
   |    3 |      17 | 2              |   11.63 |   4.5% |      76 |   11.47 |  783.73 |454 | 21 |  5 | 268993.0 |
   |    4 |      17 | 2              |   12.28 |  15.1% |      24 |   11.21 |  613.66 |449 | 30 |  1 | 289714.0 |
   |    5 |      15 | 0              |    9.77 |   5.1% |      17 |    9.73 |  658.81 |438 | 40 |  2 | 310643.0 |
   |    6 |      17 | 2              |    9.65 |   2.1% |      18 |    9.16 |  649.22 |429 | 44 |  7 | 340264.0 |
   |    7 |      16 | 1              |   10.00 |   5.8% |      15 |    9.52 |  593.93 |450 | 29 |  1 | 279214.0 |
   |    8 |      17 | 2              |   12.82 |  20.9% |      18 |   12.19 |  611.65 |436 | 43 |  1 | 301714.0 |
   |   14 |      17 | 2              |   10.18 |   4.7% |      16 |   10.01 | 2022.67 |2302 | 10 | 88 | 304249.0 |
   |   28 |      18 | 3              |   12.60 |  17.4% |      17 |   12.49 | 1882.24 |2336 |  8 | 56 | 242307.0 |
   |   53 |      16 | 1              |    9.57 |   3.9% |      17 |    9.57 | 1877.76 |2345 |  3 | 52 | 237082.0 |
   |   44 |      18 | 3              |    9.89 |   5.1% |      17 |    9.68 |  770.84 |455 | 25 |  0 | 245589.0 |
   |   64 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  335.78 |1890 |  1 | 29 | 11549.2 |
   |   65 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  335.78 |  0 |  0 |  0 | 11549.2 |
   |   66 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  335.78 |  0 |  0 |  0 | 11549.2 |
   |   67 |      17 | 2              |   11.07 |  12.8% |      18 |   10.48 |  335.78 |  0 |  0 |  0 | 11549.2 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 539.928s, TTFT=539927.92ms): Avg=3.79 | Min=3.37 | Max=3.91 tps
   Prefill Chunks (8): C1:256t/3.4tps/95% | C2:256t/3.9tps/97% | C3:256t/3.8tps/97% | C4:256t/3.9tps/97%
                       C5:256t/3.9tps/97% | C6:256t/3.9tps/97% | C7:256t/3.9tps/97% | C8:256t/3.9tps/97%
   Decode  (66 tok, 42.394s): Avg=1.56 | Min=0.49 | Max=2.98 tps
   Latency (ms) : Min=335.78 | P10=543.38 | P25=554.68 | P50=568.80 | P75=611.65 | P90=717.14 | P95=1002.67 | P99=2022.67 | Max=2022.67
   Mean/SD/Jitt : Mean=642.34ms | StdDev=296.61ms | Jitter=167.61ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/66
   MTP Head     : 3/12 draft tokens accepted (25.0% verified accept | Net 1.05x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1020480): RawRAM=994009 (97.41%) | Lookahead=1430 (+0.14%) | ColdMiss=25041 (2.45%) | EFF HIT=97.55%
   Prefix Cache : Hits=0 | Reused=0 tok | DiskSaves=1 | DiskLoads=0
   Lookahead    : 7567 prefetched -> 2020 consumed (26.7% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.5% | @64= 97.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21260 |19114 | 108 |2038 | 90.4%|3615.09 | | L24 |21260 |21044 |  10 | 206 | 99.0%| 447.41 |
   | L01 |21260 |20608 |  70 | 582 | 97.3%|1375.85 | | L25 |21260 |21067 |   7 | 186 | 99.1%| 385.38 |
   | L02 |21260 |20591 |  10 | 659 | 96.9%|1758.69 | | L26 |21260 |20651 |  42 | 567 | 97.3%|1276.44 |
   | L03 |21260 |21177 |   4 |  79 | 99.6%|1043.33 | | L27 |21260 |20913 |  25 | 322 | 98.5%| 742.55 |
   | L04 |21260 |20968 |   8 | 284 | 98.7%|1052.12 | | L28 |21260 |20552 |  45 | 663 | 96.9%|1498.27 |
   | L05 |21260 |20883 |  28 | 349 | 98.4%|1024.54 | | L29 |21260 |20726 |  28 | 506 | 97.6%| 845.53 |
   | L06 |21260 |20914 |  24 | 322 | 98.5%| 881.67 | | L30 |21260 |20345 |  44 | 871 | 95.9%|1394.34 |
   | L07 |21260 |20892 |  28 | 340 | 98.4%| 663.72 | | L31 |21260 |20476 |  48 | 736 | 96.5%|1306.47 |
   | L08 |21260 |21188 |   1 |  71 | 99.7%| 164.36 | | L32 |21260 |20659 |  21 | 580 | 97.3%|1362.92 |
   | L09 |21260 |21184 |   1 |  75 | 99.6%| 103.34 | | L33 |21260 |20538 |  47 | 675 | 96.8%|1132.18 |
   | L10 |21260 |21037 |   7 | 216 | 99.0%| 298.83 | | L34 |21260 |20264 |  42 | 954 | 95.5%|1516.77 |
   | L11 |21260 |21180 |   5 |  75 | 99.6%| 143.19 | | L35 |21260 |20653 |  36 | 571 | 97.3%| 962.21 |
   | L12 |21260 |21077 |   9 | 174 | 99.2%| 571.48 | | L36 |21260 |20649 |  25 | 586 | 97.2%|1008.30 |
   | L13 |21260 |20982 |  18 | 260 | 98.8%| 499.83 | | L37 |21260 |20611 |  29 | 620 | 97.1%|1293.36 |
   | L14 |21260 |20867 |  45 | 348 | 98.4%| 798.00 | | L38 |21260 |20853 |  19 | 388 | 98.2%|1041.46 |
   | L15 |21260 |20729 |  43 | 488 | 97.7%|1099.73 | | L39 |21260 |20631 |  34 | 595 | 97.2%|1471.95 |
   | L16 |21260 |20644 |  22 | 594 | 97.2%|1246.36 | | L40 |21260 |20785 |  32 | 443 | 97.9%|1205.00 |
   | L17 |21260 |20470 |  32 | 758 | 96.4%|1594.14 | | L41 |21260 |20768 |  14 | 478 | 97.8%| 782.15 |
   | L18 |21260 |20559 |  32 | 669 | 96.9%|1398.63 | | L42 |21260 |20460 |  48 | 752 | 96.5%|1313.67 |
   | L19 |21260 |20768 |  34 | 458 | 97.8%| 776.39 | | L43 |21260 |20374 |  37 | 849 | 96.0%|1482.20 |
   | L20 |21260 |20353 |  39 | 868 | 95.9%|1616.16 | | L44 |21260 |20383 |  52 | 825 | 96.1%|1431.79 |
   | L21 |21260 |20485 |  41 | 734 | 96.5%|1921.24 | | L45 |21260 |20378 |  61 | 821 | 96.1%|1528.30 |
   | L22 |21260 |21010 |  12 | 238 | 98.9%| 614.72 | | L46 |21260 |21014 |  10 | 236 | 98.9%| 659.72 |
   | L23 |21260 |20648 |  25 | 587 | 97.2%|1101.93 | | L47 |21260 |20887 |  28 | 345 | 98.4%| 924.90 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 60065.80 MB (Load=4614.69 | Prefill=40605.50 | Warmup=0.00 | Decode=14845.61 MB)
   SSD Data/Token (Decode)      : Avg=224.934 MB/tok (Min=11.279 | P50=225.384 | P95=303.362 | Max=332.289 MB) | Prefill=19.827 MB/tok
   NVMe Batches / Requests      : 3988 Batches | 132948 Raw -> 128024 Merged (4924 LBA Merges, Avg 480.4 KB/io)
   SSD I/O Size Histogram       : <64K=34001 | 64K-512K=23601 | 512K-2M=69910 | >2M=512
   SSD Read Bandwidth (Active)  : Min=2.14 | Avg=678.05 | Peak=10308.97 MB/s | WallAmort=103.15 MB/s
   OS Kernel I/O Verification   : Read=60086.07 MB | Write=594.14 MB | Syscalls=137545
   Sync Stall vs Async DMA      : SyncStall=70050.49 ms | AsyncOverlapped=80194.89 ms (53.4% Overlapped)
   RAM Traffic & Active BW      : 5687.55 GB moved | Active=11.58 GB/s | WallAmort=9.77 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=539.93s (92.7%, 40605.50 MB SSD) | Decode=42.39s (7.3%, 14845.61 MB SSD)
   CPU Time & Utilization       : User=1824.312s + Sys=31.031s (Wall=597.855s) | SysUtil=77.6% | ThrUtil=77.6% | 71.76 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 230968.87 ms (109256.8 us/tok | 39.66%)
   MoE AVX2 Q8 Expert Compute   : 254958.57 ms (120604.8 us/tok | 43.78%)
   Router + Lookahead Dispatch  :  12100.72 ms ( 5724.1 us/tok |  2.08%)
   LM Head Output Projection    :   5082.53 ms ( 2404.2 us/tok |  0.87%)
   Foreground NVMe Sync Stall   :  70050.49 ms (33136.5 us/tok | 12.03%)
   Unaccounted / OMP & Sampling :   9160.97 ms ( 4333.5 us/tok |  1.57%) | Total Wall=582322.16 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    88.24%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.16%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.92%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.93%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.75%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_qwen38_colibri_bench.log`
```text
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=305.0s) ===
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
resident weights loaded in 9.5s | RSS after load: 4.60 GB
[qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=305.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.1s / cutoff=305.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=305.0s
TTFT: 23.10 s (time to first token)
[qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
[qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
[qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes

PEAK RSS: 10.72 GB
Expert cache hit rate: 62.0% (hit=15849 miss=9733)
Speed: 0.72 tok/s (44.3s for 32 tokens)
[STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage

Reference: 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 
C engine : 220 248046 198 248045 74455 198 248068 198 760 1156 682 3106 1092 7701 310 381 264 7132 36412 2805 269 82987 886 314 5587 13 6558 728 22903 411 25 271 Text      :  <|im_end|>
<|im_start|>assistant
<think>
The user has sent what appears to be a garbled/corrupted string of characters. Let me analyze this:



Matching tokens: 0/32
=== [Colibri-Qwen38] Finished rc=1 elapsed=56.15s cancelled=False ===
```

### 📄 `12_qwen38_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 2.45 | 1.67 | 558.65 | 92.33% | 667.46 | 13167.70 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 8.08 | 4.69 | 185.01 | 98.52% | 617.83 | 14683.27 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 3.79 | 1.56 | 568.80 | 97.55% | 678.05 | 13414.38 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.72 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
