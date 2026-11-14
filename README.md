<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#30 (Run ID `43579941611`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43579941611)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-14 10:03:36 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T09:18:45.306Z] ================================================================================
[2026-11-14T09:18:45.326Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T09:18:45.327Z] ================================================================================
[2026-11-14T09:18:49.853Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T09:18:50.055Z] --------------------------------------------------------------------------------
[2026-11-14T09:18:50.057Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 31 GB / 149.89 GB
[2026-11-14T09:18:50.059Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-14T09:18:50.060Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.01 GB
[2026-11-14T09:18:50.074Z] --------------------------------------------------------------------------------
[2026-11-14T09:18:50.075Z]  [OK] Disk space verification passed: 178.01 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 09:19 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 09:19 build/apex.exe
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
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 13.40 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    502.84 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1474.69 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7741.53 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10119.86 MB/s
   RND4K Q32T16 Read                  :    474.32 MB/s (  121426 IOPS)
   RND4K Q1T1  Read                   :    695.43 MB/s (Latency: 5.62 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     40.43 GB/s
   AVX2 256-bit Sequential Write BW   :     36.15 GB/s
   STREAM Triad (A = B + s*C) BW      :      2.30 GB/s
   Random Pointer-Chase Latency       :     61.80 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     50.82 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    141.43 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     19.44 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1093.38 tps | Avg=1093.38 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=60.4 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1104.46 tps | Avg=1098.89 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=60.7 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1013.57 tps | Avg=1068.90 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=61.0 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=922.97 tps | Avg=1028.26 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=61.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=747.22 tps | Avg=956.32 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=61.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=685.55 tps | Avg=897.26 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=61.8 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=673.69 tps | Avg=856.64 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=62.0 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=608.56 tps | Avg=815.11 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=62.3 MB
[LIVE-DECODE] 8/32 tok | Avg=188.73 tps | Hit=100.0% (LA:+0.0%) | NVMe=2079.9 MB/s (6.58 MB) | RSS=62.3 MB
[LIVE-DECODE] 16/32 tok | Avg=188.40 tps | Hit=100.0% (LA:+0.0%) | NVMe=2079.9 MB/s (6.58 MB) | RSS=62.3 MB
[LIVE-DECODE] 24/32 tok | Avg=188.34 tps | Hit=100.0% (LA:+0.0%) | NVMe=2079.9 MB/s (6.58 MB) | RSS=62.3 MB
[LIVE-DECODE] 32/32 tok | Avg=188.65 tps | Hit=100.0% (LA:+0.0%) | NVMe=2079.9 MB/s (6.58 MB) | RSS=62.3 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=62.32 MB | Peak=62.32 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2512.55 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.38 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.38 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.27 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.27 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.31 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.31 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.23 | 12 |  0 |  0 |     0.0 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.34 | 12 |  0 |  0 |     0.0 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.34 |  0 |  0 |  0 |     0.0 |
   |   14 |     220 | tok_220        |  147.52 |  55.4% |      55 |  147.01 |    5.33 | 12 |  0 |  0 |     0.0 |
   |   15 |     197 | tok_197        |   65.84 |  97.8% |     133 |   62.03 |    5.33 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.33 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.33 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.28 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.28 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.513s, TTFT=2512.55ms): Avg=815.11 | Min=608.56 | Max=1104.46 tps
   Prefill Chunks (8): C1:256t/1093.4tps/100% | C2:256t/1104.5tps/100% | C3:256t/1013.6tps/100% | C4:256t/923.0tps/100%
                       C5:256t/747.2tps/100% | C6:256t/685.6tps/100% | C7:256t/673.7tps/100% | C8:256t/608.6tps/100%
   Decode  (32 tok, 0.170s): Avg=188.65 | Min=185.78 | Max=191.12 tps
   Latency (ms) : Min=5.23 | P10=5.24 | P25=5.28 | P50=5.31 | P75=5.33 | P90=5.34 | P95=5.38 | P99=5.38 | Max=5.38
   Mean/SD/Jitt : Mean=5.30ms | StdDev=0.04ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=206.85 | Avg=2079.91 | Peak=5754.74 MB/s | WallAmort=2.45 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=1.32 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.41 GB moved | Active=0.55 GB/s | WallAmort=0.53 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.51s (93.7%, 0.00 MB SSD) | Decode=0.17s (6.3%, 0.00 MB SSD)
   CPU Time & Utilization       : User=3.062s + Sys=0.656s (Wall=2.702s) | SysUtil=34.4% | ThrUtil=34.4% | 31.83 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2236.03 ms ( 1075.0 us/tok | 83.37%)
   MoE AVX2 Q8 Expert Compute   :    307.43 ms (  147.8 us/tok | 11.46%)
   Router + Lookahead Dispatch  :     69.35 ms (   33.3 us/tok |  2.59%)
   LM Head Output Projection    :      6.34 ms (    3.0 us/tok |  0.24%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     63.02 ms (   30.3 us/tok |  2.35%) | Total Wall=2682.17 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    17.68%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.17%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.10%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    78.32%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.73%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1482.41 tps | Avg=1482.41 tps | Hit=99.2% | NVMe=2734.9 MB/s (24.91 MB, QD=64) | RSS=85.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1734.57 tps | Avg=1598.61 tps | Hit=99.2% | NVMe=3664.8 MB/s (42.92 MB, QD=64) | RSS=85.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=996.84 tps | Avg=1330.82 tps | Hit=99.2% | NVMe=4092.5 MB/s (61.04 MB, QD=64) | RSS=86.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1129.83 tps | Avg=1274.15 tps | Hit=99.2% | NVMe=4419.1 MB/s (79.10 MB, QD=64) | RSS=86.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1107.28 tps | Avg=1236.87 tps | Hit=99.2% | NVMe=4405.1 MB/s (97.14 MB, QD=64) | RSS=86.9 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1183.91 tps | Avg=1227.72 tps | Hit=99.2% | NVMe=4647.5 MB/s (115.20 MB, QD=64) | RSS=87.4 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1102.64 tps | Avg=1208.14 tps | Hit=99.2% | NVMe=4755.1 MB/s (133.27 MB, QD=64) | RSS=87.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=947.43 tps | Avg=1167.96 tps | Hit=99.2% | NVMe=4939.7 MB/s (151.30 MB, QD=64) | RSS=88.2 MB
[LIVE-DECODE] 8/32 tok | Avg=137.37 tps | Hit=99.2% (LA:+0.0%) | NVMe=4793.2 MB/s (152.70 MB) | RSS=88.2 MB
[LIVE-DECODE] 16/32 tok | Avg=142.69 tps | Hit=99.2% (LA:+0.1%) | NVMe=4733.9 MB/s (153.28 MB) | RSS=88.2 MB
[LIVE-DECODE] 24/32 tok | Avg=142.72 tps | Hit=99.2% (LA:+0.1%) | NVMe=4646.3 MB/s (154.23 MB) | RSS=88.2 MB
[LIVE-DECODE] 32/32 tok | Avg=142.98 tps | Hit=99.2% (LA:+0.1%) | NVMe=4567.9 MB/s (155.30 MB) | RSS=88.2 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=88.19 MB | Peak=88.19 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1753.48 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    7.26 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    7.26 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    6.71 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    6.71 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    7.93 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    7.93 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    7.23 | 16 |  0 |  0 |    32.0 |
   |   28 |      49 | qtok_49        |   65.10 | 100.0% |      18 |   55.78 |    7.28 | 10 |  6 |  0 |   198.5 |
   |   29 |     148 | qtok_148       |   77.89 | 100.0% |     127 |   51.09 |    7.28 |  0 |  0 |  0 |   198.5 |
   |   22 |     128 | qtok_128       |   64.14 |  98.8% |       2 |   59.73 |    7.25 | 12 |  4 |  0 |   115.2 |
   |   23 |      63 | qtok_63        |   98.11 | 100.0% |     113 |   72.66 |    7.25 |  0 |  0 |  0 |   115.2 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    6.93 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    6.93 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    6.69 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    6.69 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.753s, TTFT=1753.48ms): Avg=1167.96 | Min=947.43 | Max=1734.57 tps
   Prefill Chunks (8): C1:256t/1482.4tps/99% | C2:256t/1734.6tps/99% | C3:256t/996.8tps/99% | C4:256t/1129.8tps/99%
                       C5:256t/1107.3tps/99% | C6:256t/1183.9tps/99% | C7:256t/1102.6tps/99% | C8:256t/947.4tps/99%
   Decode  (32 tok, 0.224s): Avg=142.98 | Min=126.17 | Max=151.86 tps
   Latency (ms) : Min=6.58 | P10=6.61 | P25=6.72 | P50=6.93 | P75=7.25 | P90=7.28 | P95=7.93 | P99=7.93 | Max=7.93
   Mean/SD/Jitt : Mean=6.99ms | StdDev=0.34ms | Jitter=0.18ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33024): RawRAM=32726 (99.10%) | Lookahead=42 (+0.13%) | ColdMiss=256 (0.78%) | EFF HIT=99.22%
   Lookahead    : 55 prefetched -> 46 consumed (83.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8256 | 8190 |   2 |  64 | 99.2%|   3.58 | | L02 | 8256 | 8171 |  21 |  64 | 99.2%|   4.99 |
   | L01 | 8256 | 8179 |  13 |  64 | 99.2%|   4.23 | | L03 | 8256 | 8186 |   6 |  64 | 99.2%|   3.85 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 155.30 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=4.00 MB)
   SSD Data/Token (Decode)      : Avg=0.125 MB/tok (Min=0.031 | P50=0.113 | P95=0.523 | Max=0.523 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 93 Batches | 34206 Raw -> 374 Merged (33832 LBA Merges, Avg 425.2 KB/io)
   SSD I/O Size Histogram       : <64K=220 | 64K-512K=154 | 512K-2M=0 | >2M=0
   SSD Read Bandwidth (Active)  : Min=385.21 | Avg=4567.89 | Peak=10862.24 MB/s | WallAmort=78.54 MB/s
   OS Kernel I/O Verification   : Read=24.47 MB | Write=0.00 MB | Syscalls=391
   Sync Stall vs Async DMA      : SyncStall=8.46 ms | AsyncOverlapped=32.51 ms (79.3% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.21 GB/s | WallAmort=1.06 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.75s (88.7%, 144.44 MB SSD) | Decode=0.22s (11.3%, 4.00 MB SSD)
   CPU Time & Utilization       : User=2.609s + Sys=0.469s (Wall=2.007s) | SysUtil=38.3% | ThrUtil=38.3% | 35.47 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1213.25 ms (  583.3 us/tok | 61.36%)
   MoE AVX2 Q8 Expert Compute   :    512.52 ms (  246.4 us/tok | 25.92%)
   Router + Lookahead Dispatch  :     95.04 ms (   45.7 us/tok |  4.81%)
   LM Head Output Projection    :      7.28 ms (    3.5 us/tok |  0.37%)
   Foreground NVMe Sync Stall   :      8.46 ms (    4.1 us/tok |  0.43%)
   Unaccounted / OMP & Sampling :    140.74 ms (   67.7 us/tok |  7.12%) | Total Wall=1977.29 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    16.34%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.42%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.79%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    72.91%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.54%  |
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
  "kv_cache_ram_bytes": 10797056,
  "kv_bytes_per_token": 2560,
  "expert_cache_ram_bytes": 2534400,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 250.2,
    "avg_tps": 655.49,
    "min_tps": 532.87,
    "max_tps": 738.29
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 131.73,
    "min_tps": 112.2,
    "max_tps": 157.69,
    "p50_ms": 7.52,
    "p90_ms": 8.12,
    "p99_ms": 8.91,
    "mean_ms": 7.59,
    "jitter_ms": 0.4
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
    "avg_mbs": 1764.52,
    "peak_mbs": 6127.45,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 1.18
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 269808128
  },
  "kernel_attribution_ms": {
    "dense_attention": 411.55,
    "moe_compute": 110.22,
    "router_lookahead": 7.32,
    "lm_head": 9.96,
    "unaccounted": 7.21
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 85.66,
    "ram_bandwidth_pinning": 1.74,
    "expert_cache_lrfu": 10.75,
    "lookahead_parallel_overlap": 1.37,
    "ssd_nvme_throughput": 0.48,
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
    "ttft_ms": 315.55,
    "avg_tps": 519.73,
    "min_tps": 369.6,
    "max_tps": 592.53
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 118.03,
    "min_tps": 97.54,
    "max_tps": 123.98,
    "p50_ms": 8.24,
    "p90_ms": 9.49,
    "p99_ms": 10.25,
    "mean_ms": 8.47,
    "jitter_ms": 0.27
  },
  "cache": {
    "raw_hit_rate_pct": 85.44,
    "effective_hit_rate_pct": 94.95,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 37982304,
    "prefill_bytes": 20240384,
    "warmup_bytes": 0,
    "decode_bytes": 12185088,
    "bytes_per_token": 187104.95,
    "avg_mbs": 2608.45,
    "peak_mbs": 8496.65,
    "sync_wait_ms": 4.69,
    "async_overlap_ms": 12.65
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
    "dense_attention": 369.41,
    "moe_compute": 208.23,
    "router_lookahead": 9.5,
    "lm_head": 9.29,
    "unaccounted": 44.85
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.8,
    "ram_bandwidth_pinning": 2.07,
    "expert_cache_lrfu": 8.13,
    "lookahead_parallel_overlap": 4.37,
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
Host CPU: AMD EPYC 7763 64-Core Processor | Cores=2 Threads=4 | RAM=15.99 GB

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 13.44 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    548.99 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1462.35 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7724.99 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10172.70 MB/s
   RND4K Q32T16 Read                  :    491.26 MB/s (  125763 IOPS)
   RND4K Q1T1  Read                   :    730.25 MB/s (Latency: 5.35 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     55.89 GB/s
   AVX2 256-bit Sequential Write BW   :     51.63 GB/s
   STREAM Triad (A = B + s*C) BW      :     40.73 GB/s
   Random Pointer-Chase Latency       :     68.40 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.43 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    196.28 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.19 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 30.95 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 165.79 MB/s (6.18s)
   Window #01 (300.0 MB in 0.50s):   595.01 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   389.23 MB/s (Uncached Direct Read)
   Window #03 (208.0 MB in 0.50s):   415.81 MB/s (Uncached Direct Read)
   Window #04 (188.0 MB in 0.50s):   374.63 MB/s (Uncached Direct Read)
   Window #05 (132.0 MB in 0.31s):   429.77 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   441.95 MB/s (Min=374.63 | Max=595.01 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 391.79 MB/s (2.61s)
   Window #01 (220.0 MB in 0.54s):   409.50 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.51s):   386.72 MB/s (Uncached Direct Read)
   Window #03 (216.0 MB in 0.54s):   398.78 MB/s (Uncached Direct Read)
   Window #04 (196.0 MB in 0.51s):   387.24 MB/s (Uncached Direct Read)
   Window #05 (196.0 MB in 0.46s):   424.10 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   400.93 MB/s (Min=386.72 | Max=424.10 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: glm53 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (0.009 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: 100.00% (0.01/0.01 GB) @ 23.2 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (46.470 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  10.76% (5.00/46.47 GB) @ 344.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  21.52% (10.00/46.47 GB) @ 338.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  32.28% (15.00/46.47 GB) @ 355.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  43.04% (20.00/46.47 GB) @ 332.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  53.80% (25.00/46.47 GB) @ 312.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  64.56% (30.00/46.47 GB) @ 270.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  75.32% (35.00/46.47 GB) @ 269.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  86.08% (40.00/46.47 GB) @ 272.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  96.84% (45.00/46.47 GB) @ 257.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf: 100.00% (46.47/46.47 GB) @ 258.2 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (45.866 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  10.90% (5.00/45.87 GB) @ 260.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  21.80% (10.00/45.87 GB) @ 271.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  32.70% (15.00/45.87 GB) @ 273.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  43.61% (20.00/45.87 GB) @ 270.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  54.51% (25.00/45.87 GB) @ 277.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  65.41% (30.00/45.87 GB) @ 286.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  76.31% (35.00/45.87 GB) @ 286.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  87.21% (40.00/45.87 GB) @ 288.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  98.11% (45.00/45.87 GB) @ 291.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf: 100.00% (45.87/45.87 GB) @ 291.5 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (2.506 GB) -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf: 100.00% (2.51/2.51 GB) @ 128.5 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=101,844,951,904 (94.85 GB) | Elapsed=366.96s
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
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=6750.00 MB (720 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=1.41 tps | Avg=1.41 tps | Hit=78.2% | NVMe=641.2 MB/s (18800.09 MB, QD=64) | RSS=14163.0 MB
[LIVE-DECODE] 2/32 tok | Avg=0.65 tps | Hit=78.8% (LA:+8.7%) | NVMe=633.0 MB/s (19645.09 MB) | RSS=14112.0 MB
[LIVE-DECODE] 4/32 tok | Avg=0.70 tps | Hit=79.6% (LA:+8.7%) | NVMe=628.7 MB/s (20344.90 MB) | RSS=14074.5 MB
[LIVE-DECODE] 6/32 tok | Avg=0.77 tps | Hit=80.2% (LA:+8.6%) | NVMe=624.6 MB/s (20973.46 MB) | RSS=14051.9 MB
[LIVE-DECODE] 8/32 tok | Avg=0.83 tps | Hit=80.8% (LA:+8.3%) | NVMe=622.8 MB/s (21514.21 MB) | RSS=14029.2 MB
[LIVE-DECODE] 10/32 tok | Avg=0.87 tps | Hit=81.4% (LA:+8.1%) | NVMe=621.2 MB/s (22062.15 MB) | RSS=14017.9 MB
[LIVE-DECODE] 12/32 tok | Avg=0.91 tps | Hit=82.1% (LA:+7.9%) | NVMe=622.2 MB/s (22536.02 MB) | RSS=14015.7 MB
[LIVE-DECODE] 14/32 tok | Avg=0.94 tps | Hit=82.6% (LA:+7.7%) | NVMe=622.3 MB/s (23066.15 MB) | RSS=14010.0 MB
[LIVE-DECODE] 16/32 tok | Avg=0.95 tps | Hit=83.1% (LA:+7.5%) | NVMe=623.5 MB/s (23680.96 MB) | RSS=13992.6 MB
[LIVE-DECODE] 18/32 tok | Avg=0.97 tps | Hit=83.7% (LA:+7.3%) | NVMe=625.4 MB/s (24185.77 MB) | RSS=13982.1 MB
[LIVE-DECODE] 20/32 tok | Avg=1.00 tps | Hit=84.2% (LA:+7.1%) | NVMe=625.9 MB/s (24635.27 MB) | RSS=13980.5 MB
[LIVE-DECODE] 22/32 tok | Avg=1.01 tps | Hit=84.6% (LA:+6.9%) | NVMe=627.3 MB/s (25135.09 MB) | RSS=13973.2 MB
[LIVE-DECODE] 24/32 tok | Avg=1.03 tps | Hit=85.1% (LA:+6.7%) | NVMe=629.8 MB/s (25651.46 MB) | RSS=13972.2 MB
[LIVE-DECODE] 26/32 tok | Avg=1.05 tps | Hit=85.5% (LA:+6.5%) | NVMe=633.1 MB/s (26170.65 MB) | RSS=13969.4 MB
[LIVE-DECODE] 28/32 tok | Avg=1.07 tps | Hit=85.9% (LA:+6.3%) | NVMe=634.8 MB/s (26651.71 MB) | RSS=13964.7 MB
[LIVE-DECODE] 32/32 tok | Avg=1.10 tps | Hit=86.6% (LA:+6.1%) | NVMe=641.3 MB/s (27628.21 MB) | RSS=13955.6 MB

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
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=345.25 MB (36864 B/tok)
   LRFU Cache / Staging Ring    : 6750.00 MB (720/12384 exp = 5.81% pinned) | Staging=300.00 MB
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=13955.64 MB | Peak=14217.79 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 45471.13 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan | 1527.17 |266 | 44 | 26 | 432640.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan | 1527.17 |  0 |  0 |  0 | 432640.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan | 1310.40 |290 | 29 | 17 | 358304.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan | 1310.40 |  0 |  0 |  0 | 358304.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan | 1052.74 |296 | 18 | 22 | 321824.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan | 1052.74 |  0 |  0 |  0 | 321824.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  942.34 |310 | 10 | 16 | 276864.0 |
   |    9 |       0 | !              |     nan | 100.0% |       1 |     nan |  942.34 |  0 |  0 |  0 | 276864.0 |
   |   16 |       0 | !              |     nan | 100.0% |       1 |     nan |  940.57 |317 |  9 | 10 | 314784.0 |
   |   17 |       0 | !              |     nan | 100.0% |       1 |     nan |  940.57 |  0 |  0 |  0 | 314784.0 |
   |   10 |       0 | !              |     nan | 100.0% |       1 |     nan |  936.31 |315 | 10 | 11 | 280544.0 |
   |   30 |       0 | !              |     nan | 100.0% |       1 |     nan |  682.99 |326 |  5 |  5 | 253664.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  682.99 |  0 |  0 |  0 | 253664.0 |
   |   32 |       0 | !              |     nan | 100.0% |       1 |     nan |  767.09 |332 |  2 |  2 | 246304.0 |
   |   33 |       0 | !              |     nan | 100.0% |       1 |     nan |  767.09 |  0 |  0 |  0 | 246304.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 45.471s, TTFT=45471.13ms): Avg=1.41 | Min=1.41 | Max=1.41 tps
   Prefill Chunks (1): C1:64t/1.4tps/78%
   Decode  (32 tok, 29.191s): Avg=1.10 | Min=0.65 | Max=1.46 tps
   Latency (ms) : Min=682.99 | P10=758.45 | P25=776.19 | P50=827.94 | P75=942.34 | P90=1310.40 | P95=1527.17 | P99=1527.17 | Max=1527.17
   Mean/SD/Jitt : Mean=912.21ms | StdDev=214.78ms | Jitter=39.30ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (12110): RawRAM=9755 (80.55%) | Lookahead=733 (+6.05%) | ColdMiss=1622 (13.39%) | EFF HIT=86.61%
   Lookahead    : 1242 prefetched -> 371 consumed (29.9% util) | Warmup >=75%:1t, >=85%:23t
   Trajectory   : @16= 83.1% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  370 |  73 | 197 | 69.2%|2544.38 | | L24 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L04 |  640 |  367 |  92 | 181 | 71.7%|2680.94 | | L25 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L05 |  640 |  360 |  66 | 214 | 66.6%|2716.88 | | L26 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L06 |  640 |  376 |  74 | 190 | 70.3%|2235.31 | | L27 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L07 |  640 |  417 |  73 | 150 | 76.6%|1732.19 | | L28 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L08 |  640 |  383 |  94 | 163 | 74.5%|1919.06 | | L29 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L09 |  640 |  386 |  88 | 166 | 74.1%|1926.25 | | L30 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L10 |  640 |  374 |  97 | 169 | 73.6%|1897.50 | | L31 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L11 |  640 |  422 |  76 | 142 | 77.8%|2109.38 | | L32 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L12 |  206 |  188 |   0 |  18 | 91.3%|1264.62 | | L33 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L13 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L34 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L14 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L35 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L15 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L36 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L16 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L37 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L17 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L38 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L18 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L39 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L19 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L40 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L20 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L41 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L21 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L42 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L22 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L43 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L23 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L44 |  192 |  191 |   0 |   1 | 99.5%|   8.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 27628.21 MB (Load=6361.84 | Prefill=12438.25 | Warmup=0.00 | Decode=8828.12 MB)
   SSD Data/Token (Decode)      : Avg=275.879 MB/tok (Min=224.750 | P50=259.594 | P95=422.500 | Max=422.500 MB) | Prefill=194.348 MB/tok
   NVMe Batches / Requests      : 377 Batches | 9878 Raw -> 9679 Merged (199 LBA Merges, Avg 2923.0 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=8800
   SSD Read Bandwidth (Active)  : Min=0.48 | Avg=641.26 | Peak=4734.07 MB/s | WallAmort=370.05 MB/s
   OS Kernel I/O Verification   : Read=23348.37 MB | Write=0.00 MB | Syscalls=13714
   Sync Stall vs Async DMA      : SyncStall=13124.51 ms | AsyncOverlapped=28336.86 ms (68.3% Overlapped)
   RAM Traffic & Active BW      : 342.62 GB moved | Active=6.54 GB/s | WallAmort=4.59 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=45.47s (60.9%, 12438.25 MB SSD) | Decode=29.19s (39.1%, 8828.12 MB SSD)
   CPU Time & Utilization       : User=169.250s + Sys=6.469s (Wall=93.134s) | SysUtil=47.2% | ThrUtil=47.2% | 43.63 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  31010.88 ms (323030.0 us/tok | 41.54%)
   MoE AVX2 Q8 Expert Compute   :  20368.67 ms (212173.7 us/tok | 27.28%)
   Router + Lookahead Dispatch  :    690.52 ms ( 7192.9 us/tok |  0.92%)
   LM Head Output Projection    :    986.94 ms (10280.6 us/tok |  1.32%)
   Foreground NVMe Sync Stall   :  13124.51 ms (136713.7 us/tok | 17.58%)
   Unaccounted / OMP & Sampling :   8480.20 ms (88335.4 us/tok | 11.36%) | Total Wall=74661.73 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    47.56%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    11.66%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    18.75%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    17.46%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.57%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 95s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 14.59 GB Available
   Active Drive Space : 150.00 GB Total / 54.59 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    422.13 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1587.50 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7037.34 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9258.22 MB/s
   RND4K Q32T16 Read                  :    361.34 MB/s (   92504 IOPS)
   RND4K Q1T1  Read                   :    642.10 MB/s (Latency: 6.08 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     54.87 GB/s
   AVX2 256-bit Sequential Write BW   :     48.11 GB/s
   STREAM Triad (A = B + s*C) BW      :     38.68 GB/s
   Random Pointer-Chase Latency       :     55.20 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.19 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    141.18 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     20.53 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=1.16 tps | Avg=1.16 tps | Hit=73.4% | NVMe=579.5 MB/s (23748.52 MB, QD=64) | RSS=14121.1 MB

 >>> [Apex-Model-Response] !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=345.25 MB (36864 B/tok)
   LRFU Cache / Staging Ring    : 6937.50 MB (740/12384 exp = 5.98% pinned) | Staging=300.00 MB
   Process RSS (Start/End/Peak) : Start=4.83 MB | End=14092.20 MB | Peak=14409.30 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (70 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 60432.79 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan | 1359.04 |260 | 54 | 22 | 447392.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan | 1359.04 |  0 |  0 |  0 | 447392.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan | 1170.84 |287 | 24 | 25 | 373024.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan | 1170.84 |  0 |  0 |  0 | 373024.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan | 1139.41 |298 | 15 | 23 | 348704.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan | 1139.41 |  0 |  0 |  0 | 348704.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan | 1074.65 |300 | 11 | 25 | 332864.0 |
   |    9 |       0 | !              |     nan | 100.0% |       1 |     nan | 1074.65 |  0 |  0 |  0 | 332864.0 |
   |   10 |       0 | !              |     nan | 100.0% |       1 |     nan |  987.19 |305 | 15 | 16 | 322944.0 |
   |   11 |       0 | !              |     nan | 100.0% |       1 |     nan |  987.19 |  0 |  0 |  0 | 322944.0 |
   |   24 |       0 | !              |     nan | 100.0% |       1 |     nan |  968.14 |331 |  2 |  3 | 311616.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  763.47 |329 |  4 |  3 | 221056.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  763.47 |  0 |  0 |  0 | 221056.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  816.09 |332 |  1 |  3 | 266816.0 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  816.09 |  0 |  0 |  0 | 266816.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 60.433s, TTFT=60432.79ms): Avg=1.16 | Min=1.16 | Max=1.16 tps
   Prefill Chunks (1): C1:70t/1.2tps/73%
   Decode  (64 tok, 55.213s): Avg=1.16 | Min=0.74 | Max=1.46 tps
   Latency (ms) : Min=685.12 | P10=745.93 | P25=763.47 | P50=816.09 | P75=908.55 | P90=1074.65 | P95=1170.84 | P99=1359.04 | Max=1359.04
   Mean/SD/Jitt : Mean=862.70ms | StdDev=144.68ms | Jitter=39.25ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (18795): RawRAM=15620 (83.11%) | Lookahead=821 (+4.37%) | ColdMiss=2354 (12.52%) | EFF HIT=87.48%
   Lookahead    : 2402 prefetched -> 444 consumed (18.5% util) | Warmup >=75%:5t, >=85%:45t
   Trajectory   : @16= 78.9% | @64= 87.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  536 |  83 | 197 | 75.9%|3442.81 | | L24 |  347 |  326 |   0 |  21 | 93.9%| 150.94 |
   | L04 |  816 |  523 |  93 | 200 | 75.5%|4449.06 | | L25 |  347 |  326 |   0 |  21 | 93.9%| 150.94 |
   | L05 |  816 |  509 |  94 | 213 | 73.9%|3766.25 | | L26 |  347 |  331 |   0 |  16 | 95.4%| 115.00 |
   | L06 |  816 |  508 |  92 | 216 | 73.5%|2853.44 | | L27 |  347 |  326 |   1 |  20 | 94.2%| 150.94 |
   | L07 |  816 |  553 |  69 | 194 | 76.2%|3140.94 | | L28 |  347 |  325 |   1 |  21 | 93.9%| 158.12 |
   | L08 |  816 |  510 | 118 | 188 | 77.0%|2688.12 | | L29 |  347 |  331 |   0 |  16 | 95.4%| 115.00 |
   | L09 |  816 |  542 |  83 | 191 | 76.6%|2702.50 | | L30 |  347 |  326 |   1 |  20 | 94.2%| 150.94 |
   | L10 |  816 |  516 | 115 | 185 | 77.3%|2666.56 | | L31 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L11 |  816 |  569 |  60 | 187 | 77.1%|3309.38 | | L32 |  347 |  328 |   1 |  18 | 94.8%| 136.56 |
   | L12 |  347 |  331 |   0 |  16 | 95.4%|2051.88 | | L33 |  347 |  332 |   0 |  15 | 95.7%| 107.81 |
   | L13 |  347 |  330 |   0 |  17 | 95.1%| 122.19 | | L34 |  347 |  328 |   1 |  18 | 94.8%| 136.56 |
   | L14 |  347 |  336 |   0 |  11 | 96.8%|  79.06 | | L35 |  347 |  328 |   1 |  18 | 94.8%| 136.56 |
   | L15 |  347 |  327 |   1 |  19 | 94.5%| 143.75 | | L36 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L16 |  347 |  330 |   0 |  17 | 95.1%| 122.19 | | L37 |  347 |  328 |   1 |  18 | 94.8%| 136.56 |
   | L17 |  347 |  330 |   0 |  17 | 95.1%| 122.19 | | L38 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L18 |  347 |  333 |   0 |  14 | 96.0%| 100.62 | | L39 |  347 |  327 |   1 |  19 | 94.5%| 143.75 |
   | L19 |  347 |  328 |   1 |  18 | 94.8%| 136.56 | | L40 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L20 |  347 |  327 |   1 |  19 | 94.5%| 143.75 | | L41 |  347 |  331 |   0 |  16 | 95.4%| 115.00 |
   | L21 |  347 |  328 |   1 |  18 | 94.8%| 136.56 | | L42 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L22 |  347 |  325 |   1 |  21 | 93.9%| 158.12 | | L43 |  347 |  331 |   0 |  16 | 95.4%| 115.00 |
   | L23 |  347 |  325 |   1 |  21 | 93.9%| 158.12 | | L44 |  347 |  330 |   0 |  17 | 95.1%| 142.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 41637.59 MB (Load=6361.84 | Prefill=17386.69 | Warmup=0.00 | Decode=17889.06 MB)
   SSD Data/Token (Decode)      : Avg=279.517 MB/tok (Min=215.875 | P50=270.875 | P95=364.281 | Max=436.906 MB) | Prefill=248.381 MB/tok
   NVMe Batches / Requests      : 645 Batches | 15554 Raw -> 15239 Merged (315 LBA Merges, Avg 2797.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=14360
   SSD Read Bandwidth (Active)  : Min=0.47 | Avg=620.98 | Peak=5003.63 MB/s | WallAmort=360.04 MB/s (100.0% of 422.1 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=40993.12 MB | Write=128.00 MB | Syscalls=26813
   Sync Stall vs Async DMA      : SyncStall=25565.53 ms | AsyncOverlapped=52282.32 ms (67.2% Overlapped)
   RAM Traffic & Active BW      : 625.13 GB moved | Active=8.45 GB/s (21.8% STREAM) | WallAmort=5.41 GB/s (Max=38.68 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=60.43s (52.3%, 17386.69 MB SSD) | Decode=55.21s (47.7%, 17889.06 MB SSD)
   CPU Time & Utilization       : User=241.766s + Sys=9.156s (Wall=134.885s) | SysUtil=46.5% | ThrUtil=46.5% | 65.66 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  39258.56 ms (292974.3 us/tok | 33.95%)
   MoE AVX2 Q8 Expert Compute   :  32770.35 ms (244554.8 us/tok | 28.34%)
   Router + Lookahead Dispatch  :    889.59 ms ( 6638.8 us/tok |  0.77%)
   LM Head Output Projection    :   1985.50 ms (14817.2 us/tok |  1.72%)
   Foreground NVMe Sync Stall   :  25565.53 ms (190787.6 us/tok | 22.11%)
   Unaccounted / OMP & Sampling :  15176.06 ms (113254.2 us/tok | 13.12%) | Total Wall=115645.60 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    49.06%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.92%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    19.26%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    15.40%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.36%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=7096.88 MB (757 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=2.29 tps | Avg=2.29 tps | Hit=93.2% | NVMe=666.6 MB/s (13694.77 MB, QD=64) | RSS=14354.8 MB
[LIVE-PREFILL] 512/512 tok | Chunk=2.37 tps | Avg=2.33 tps | Hit=95.5% | NVMe=671.2 MB/s (15723.84 MB, QD=64) | RSS=14327.7 MB
[LIVE-DECODE] 8/128 tok | Avg=1.67 tps | Hit=95.7% (LA:+2.2%) | NVMe=682.2 MB/s (16251.59 MB) | RSS=14359.4 MB
[LIVE-DECODE] 16/128 tok | Avg=1.74 tps | Hit=95.9% (LA:+2.1%) | NVMe=687.6 MB/s (16416.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 24/128 tok | Avg=1.77 tps | Hit=96.1% (LA:+2.0%) | NVMe=688.9 MB/s (16460.02 MB) | RSS=14359.4 MB
[LIVE-DECODE] 32/128 tok | Avg=1.78 tps | Hit=96.3% (LA:+1.9%) | NVMe=690.8 MB/s (16517.52 MB) | RSS=14359.4 MB
[LIVE-DECODE] 40/128 tok | Avg=1.79 tps | Hit=96.4% (LA:+1.9%) | NVMe=693.6 MB/s (16603.77 MB) | RSS=14359.4 MB
[LIVE-DECODE] 48/128 tok | Avg=1.79 tps | Hit=96.6% (LA:+1.8%) | NVMe=695.8 MB/s (16675.65 MB) | RSS=14359.4 MB
[LIVE-DECODE] 56/128 tok | Avg=1.80 tps | Hit=96.7% (LA:+1.8%) | NVMe=700.1 MB/s (16797.84 MB) | RSS=14359.4 MB
[LIVE-DECODE] 64/128 tok | Avg=1.80 tps | Hit=96.8% (LA:+1.7%) | NVMe=700.5 MB/s (16812.21 MB) | RSS=14359.4 MB
[LIVE-DECODE] 72/128 tok | Avg=1.80 tps | Hit=96.9% (LA:+1.6%) | NVMe=702.5 MB/s (16869.71 MB) | RSS=14359.4 MB
[LIVE-DECODE] 80/128 tok | Avg=1.80 tps | Hit=97.0% (LA:+1.6%) | NVMe=702.7 MB/s (16876.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 88/128 tok | Avg=1.80 tps | Hit=97.1% (LA:+1.5%) | NVMe=702.7 MB/s (16876.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 96/128 tok | Avg=1.81 tps | Hit=97.2% (LA:+1.5%) | NVMe=702.7 MB/s (16876.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 104/128 tok | Avg=1.81 tps | Hit=97.3% (LA:+1.4%) | NVMe=702.7 MB/s (16876.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 112/128 tok | Avg=1.81 tps | Hit=97.4% (LA:+1.4%) | NVMe=703.7 MB/s (16912.84 MB) | RSS=14360.0 MB
[LIVE-DECODE] 120/128 tok | Avg=1.81 tps | Hit=97.5% (LA:+1.4%) | NVMe=703.7 MB/s (16912.84 MB) | RSS=14352.8 MB
[LIVE-DECODE] 128/128 tok | Avg=1.81 tps | Hit=97.5% (LA:+1.3%) | NVMe=703.7 MB/s (16912.84 MB) | RSS=14346.0 MB

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
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=345.25 MB (36864 B/tok)
   LRFU Cache / Staging Ring    : 7096.88 MB (757/12384 exp = 6.11% pinned) | Staging=300.00 MB
   Process RSS (Start/End/Peak) : Start=4.70 MB | End=14346.04 MB | Peak=14627.11 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 219523.73 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  693.89 |328 |  0 |  8 | 89088.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  693.89 |  0 |  0 |  0 | 89088.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  583.10 |334 |  2 |  0 | 36800.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  583.10 |  0 |  0 |  0 | 36800.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  567.32 |333 |  3 |  0 | 22080.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  567.32 |  0 |  0 |  0 | 22080.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  551.69 |333 |  3 |  0 | 22080.0 |
   |   66 |       0 | !              |     nan | 100.0% |       1 |     nan |  564.46 |335 |  1 |  0 | 14720.0 |
   |   67 |       0 | !              |     nan | 100.0% |       1 |     nan |  564.46 |  0 |  0 |  0 | 14720.0 |
   |   12 |       0 | !              |     nan | 100.0% |       1 |     nan |  561.59 |335 |  1 |  0 | 18400.0 |
   |   13 |       0 | !              |     nan | 100.0% |       1 |     nan |  561.59 |  0 |  0 |  0 | 18400.0 |
   |  126 |       0 | !              |     nan | 100.0% |       1 |     nan |  547.97 |336 |  0 |  0 |     0.0 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  547.97 |  0 |  0 |  0 |     0.0 |
   |  128 |       0 | !              |     nan | 100.0% |       1 |     nan |  547.20 |336 |  0 |  0 |     0.0 |
   |  129 |       0 | !              |     nan | 100.0% |       1 |     nan |  547.20 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 219.524s, TTFT=219523.73ms): Avg=2.33 | Min=2.29 | Max=2.37 tps
   Prefill Chunks (2): C1:256t/2.3tps/93% | C2:256t/2.4tps/96%
   Decode  (128 tok, 70.738s): Avg=1.81 | Min=1.44 | Max=1.83 tps
   Latency (ms) : Min=545.79 | P10=546.91 | P25=547.51 | P50=548.95 | P75=550.62 | P90=555.33 | P95=564.46 | P99=693.89 | Max=693.89
   Mean/SD/Jitt : Mean=552.64ms | StdDev=18.71ms | Jitter=2.41ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (47551): RawRAM=45755 (96.22%) | Lookahead=627 (+1.32%) | ColdMiss=1169 (2.46%) | EFF HIT=97.54%
   Lookahead    : 249 prefetched -> 150 consumed (60.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 95.9% | @64= 96.8% | @128= 97.5% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3558 | 565 | 485 | 89.5%|4485.00 | | L24 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L04 | 1297 | 1111 |  35 | 151 | 88.4%|1753.75 | | L25 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L05 | 1234 | 1082 |  27 | 125 | 89.9%|1070.94 | | L26 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L06 | 1101 | 1038 |   0 |  63 | 94.3%| 488.75 | | L27 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L07 | 1101 | 1043 |   0 |  58 | 94.7%| 438.44 | | L28 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L08 | 1101 | 1044 |   0 |  57 | 94.8%| 431.25 | | L29 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L09 | 1101 | 1041 |   0 |  60 | 94.6%| 438.44 | | L30 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L10 | 1101 | 1041 |   0 |  60 | 94.6%| 452.81 | | L31 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L11 | 1101 | 1040 |   0 |  61 | 94.5%| 609.38 | | L32 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L12 | 1038 | 1021 |   0 |  17 | 98.4%| 142.38 | | L33 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L13 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L34 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L14 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L35 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L15 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L36 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L16 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L37 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L17 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L38 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L18 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L39 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L19 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L40 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L20 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L41 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L21 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L42 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L22 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L43 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L23 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L44 | 1024 | 1023 |   0 |   1 | 99.9%|   8.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 16912.84 MB (Load=6361.84 | Prefill=9362.00 | Warmup=195.62 | Decode=993.38 MB)
   SSD Data/Token (Decode)      : Avg=7.761 MB/tok (Min=0.000 | P50=3.594 | P95=25.156 | Max=87.000 MB) | Prefill=18.285 MB/tok
   NVMe Batches / Requests      : 154 Batches | 5618 Raw -> 5555 Merged (63 LBA Merges, Avg 3117.7 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=4676
   SSD Read Bandwidth (Active)  : Min=0.32 | Avg=703.68 | Peak=5816.19 MB/s | WallAmort=58.27 MB/s
   OS Kernel I/O Verification   : Read=12896.93 MB | Write=0.00 MB | Syscalls=9592
   Sync Stall vs Async DMA      : SyncStall=6811.34 ms | AsyncOverlapped=9320.69 ms (57.8% Overlapped)
   RAM Traffic & Active BW      : 1348.20 GB moved | Active=4.90 GB/s | WallAmort=4.64 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=219.52s (75.6%, 9362.00 MB SSD) | Decode=70.74s (24.4%, 993.38 MB SSD)
   CPU Time & Utilization       : User=971.672s + Sys=14.266s (Wall=308.835s) | SysUtil=79.8% | ThrUtil=79.8% | 73.83 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 206464.25 ms (322600.4 us/tok | 71.13%)
   MoE AVX2 Q8 Expert Compute   :  64816.98 ms (101276.5 us/tok | 22.33%)
   Router + Lookahead Dispatch  :   4329.60 ms ( 6765.0 us/tok |  1.49%)
   LM Head Output Projection    :   3682.32 ms ( 5753.6 us/tok |  1.27%)
   Foreground NVMe Sync Stall   :   6811.34 ms (10642.7 us/tok |  2.35%)
   Unaccounted / OMP & Sampling :   4157.38 ms ( 6495.9 us/tok |  1.43%) | Total Wall=290261.87 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    61.78%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.75%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.13%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    27.87%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.47%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 45373.7ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='!!!!!!!!!!!!!!!!'
[Stage 3] /v1/chat/completions (stream=true SSE) 25674.4ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=7087.50 MB (756 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1.91 tps | Avg=1.91 tps | Hit=92.3% | NVMe=808.9 MB/s (24020.09 MB, QD=64) | RSS=14454.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.21 tps | Avg=2.05 tps | Hit=93.0% | NVMe=837.4 MB/s (31056.34 MB, QD=64) | RSS=14440.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.28 tps | Avg=2.12 tps | Hit=93.8% | NVMe=831.8 MB/s (34925.40 MB, QD=64) | RSS=14366.4 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.31 tps | Avg=2.16 tps | Hit=94.6% | NVMe=822.4 MB/s (36916.34 MB, QD=64) | RSS=14312.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.28 tps | Avg=2.19 tps | Hit=95.2% | NVMe=814.8 MB/s (38821.02 MB, QD=64) | RSS=14400.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.24 tps | Avg=2.19 tps | Hit=95.6% | NVMe=811.2 MB/s (40761.65 MB, QD=64) | RSS=14354.3 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.22 tps | Avg=2.20 tps | Hit=95.9% | NVMe=805.7 MB/s (42766.96 MB, QD=64) | RSS=14383.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.19 tps | Avg=2.20 tps | Hit=96.1% | NVMe=798.4 MB/s (44678.84 MB, QD=64) | RSS=14340.9 MB
[LIVE-DECODE] 8/64 tok | Avg=1.52 tps | Hit=96.2% (LA:+4.3%) | NVMe=802.7 MB/s (45317.21 MB) | RSS=14350.0 MB
[LIVE-DECODE] 16/64 tok | Avg=1.59 tps | Hit=96.2% (LA:+4.3%) | NVMe=805.6 MB/s (45540.02 MB) | RSS=14350.0 MB
[LIVE-DECODE] 24/64 tok | Avg=1.62 tps | Hit=96.3% (LA:+4.2%) | NVMe=806.8 MB/s (45633.46 MB) | RSS=14350.0 MB
[LIVE-DECODE] 32/64 tok | Avg=1.64 tps | Hit=96.3% (LA:+4.2%) | NVMe=807.1 MB/s (45662.21 MB) | RSS=14350.0 MB
[LIVE-DECODE] 40/64 tok | Avg=1.65 tps | Hit=96.3% (LA:+4.1%) | NVMe=807.4 MB/s (45690.96 MB) | RSS=14350.0 MB
[LIVE-DECODE] 48/64 tok | Avg=1.66 tps | Hit=96.4% (LA:+4.1%) | NVMe=807.9 MB/s (45734.09 MB) | RSS=14350.0 MB
[LIVE-DECODE] 56/64 tok | Avg=1.66 tps | Hit=96.4% (LA:+4.1%) | NVMe=808.6 MB/s (45784.40 MB) | RSS=14350.0 MB
[LIVE-DECODE] 64/64 tok | Avg=1.67 tps | Hit=96.5% (LA:+4.0%) | NVMe=809.1 MB/s (45820.34 MB) | RSS=14350.0 MB

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
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=345.25 MB (36864 B/tok)
   LRFU Cache / Staging Ring    : 7087.50 MB (756/12384 exp = 6.10% pinned) | Staging=300.00 MB
   Process RSS (Start/End/Peak) : Start=4.66 MB | End=14350.00 MB | Peak=14620.28 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 932206.79 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  747.96 |329 |  2 |  5 | 81728.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  747.96 |  0 |  0 |  0 | 81728.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  632.23 |331 |  1 |  4 | 58880.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  632.23 |  0 |  0 |  0 | 58880.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  644.76 |332 |  4 |  0 | 29440.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  644.76 |  0 |  0 |  0 | 29440.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  608.87 |332 |  4 |  0 | 62560.0 |
   |   30 |       0 | !              |     nan | 100.0% |       1 |     nan |  609.95 |336 |  0 |  0 |     0.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  609.95 |  0 |  0 |  0 |     0.0 |
   |    9 |       0 | !              |     nan | 100.0% |       1 |     nan |  608.87 |  0 |  0 |  0 | 62560.0 |
   |   10 |       0 | !              |     nan | 100.0% |       1 |     nan |  607.75 |334 |  2 |  0 | 33120.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  593.77 |335 |  1 |  0 |  3680.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  593.77 |  0 |  0 |  0 |  3680.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  592.39 |335 |  1 |  0 | 14720.0 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  592.39 |  0 |  0 |  0 | 14720.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 932.207s, TTFT=932206.79ms): Avg=2.20 | Min=1.91 | Max=2.31 tps
   Prefill Chunks (8): C1:256t/1.9tps/92% | C2:256t/2.2tps/93% | C3:256t/2.3tps/94% | C4:256t/2.3tps/95%
                       C5:256t/2.3tps/95% | C6:256t/2.2tps/96% | C7:256t/2.2tps/96% | C8:256t/2.2tps/96%
   Decode  (64 tok, 38.396s): Avg=1.67 | Min=1.34 | Max=1.71 tps
   Latency (ms) : Min=585.02 | P10=586.19 | P25=587.66 | P50=591.62 | P75=596.80 | P90=609.95 | P95=644.76 | P99=747.96 | Max=747.96
   Mean/SD/Jitt : Mean=599.94ms | StdDev=29.59ms | Jitter=4.85ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (128709): RawRAM=118968 (92.43%) | Lookahead=5175 (+4.02%) | ColdMiss=4566 (3.55%) | EFF HIT=96.45%
   Lookahead    : 804 prefetched -> 733 consumed (91.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.2% | @64= 96.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |16640 |12445 |2316 |1879 | 88.7%|16250.94 | | L24 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L04 | 6812 | 5328 | 798 | 686 | 89.9%|6231.56 | | L25 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L05 | 4173 | 3388 | 483 | 302 | 92.8%|2530.00 | | L26 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L06 | 4173 | 3391 | 492 | 290 | 93.1%|2465.31 | | L27 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L07 | 4173 | 3680 | 228 | 265 | 93.6%|2141.88 | | L28 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L08 | 4173 | 3692 | 208 | 273 | 93.5%|2213.75 | | L29 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L09 | 4173 | 3686 | 207 | 280 | 93.3%|2242.50 | | L30 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L10 | 4173 | 3635 | 262 | 276 | 93.4%|2206.56 | | L31 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L11 | 4173 | 3726 | 181 | 266 | 93.6%|2793.75 | | L32 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L12 | 2318 | 2301 |   0 |  17 | 99.3%| 142.38 | | L33 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L13 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L34 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L14 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L35 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L15 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L36 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L16 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L37 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L17 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L38 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L18 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L39 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L19 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L40 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L20 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L41 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L21 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L42 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L22 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L43 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L23 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L44 | 2304 | 2303 |   0 |   1 |100.0%|   8.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 45820.34 MB (Load=6361.84 | Prefill=38317.00 | Warmup=184.06 | Decode=957.44 MB)
   SSD Data/Token (Decode)      : Avg=14.960 MB/tok (Min=0.000 | P50=7.188 | P95=61.094 | Max=79.812 MB) | Prefill=18.709 MB/tok
   NVMe Batches / Requests      : 259 Batches | 17471 Raw -> 17225 Merged (246 LBA Merges, Avg 2723.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=16346
   SSD Read Bandwidth (Active)  : Min=0.42 | Avg=809.06 | Peak=5819.63 MB/s | WallAmort=47.21 MB/s
   OS Kernel I/O Verification   : Read=31303.87 MB | Write=0.00 MB | Syscalls=21260
   Sync Stall vs Async DMA      : SyncStall=28212.97 ms | AsyncOverlapped=41911.93 ms (59.8% Overlapped)
   RAM Traffic & Active BW      : 1753.13 GB moved | Active=1.91 GB/s | WallAmort=1.81 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=932.21s (96.0%, 38317.00 MB SSD) | Decode=38.40s (4.0%, 957.44 MB SSD)
   CPU Time & Utilization       : User=3262.359s + Sys=29.656s (Wall=989.065s) | SysUtil=83.2% | ThrUtil=83.2% | 76.97 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 761858.49 ms (360728.5 us/tok | 78.49%)
   MoE AVX2 Q8 Expert Compute   : 155278.40 ms (73522.0 us/tok | 16.00%)
   Router + Lookahead Dispatch  :  15394.51 ms ( 7289.1 us/tok |  1.59%)
   LM Head Output Projection    :   1908.75 ms (  903.8 us/tok |  0.20%)
   Foreground NVMe Sync Stall   :  28212.97 ms (13358.4 us/tok |  2.91%)
   Unaccounted / OMP & Sampling :   7950.12 ms ( 3764.3 us/tok |  0.82%) | Total Wall=970603.24 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    54.23%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.51%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.34%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    36.16%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.76%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=95.0s | Competitor drastic-underperform cutoff=475.0s (5x Apex)
=== [Colibri-GLM53] CMD: ./baselines/colibri/c/glm53.exe --model D:/apex_d_drive/models/glm53 --ids 1,8,15,22,29,36,43,50,57,64,71,78,85,92,99,106,113,120,127,134,141,148,155,162,169,176,183,190,197,204,211,218,225,232,239,246,253,260,267,274,281,288,295,302,309,316,323,330,337,344,351,358,365,372,379,386,393,400,407,414,421,428,435,442 --greedy 64 32 (5x cutoff=475.0s) ===
  [Colibri-GLM53] [gguf] D:\apex_d_drive\models\glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: glm5-next, 4 part(s), 38435 tensors under the checkpoint's names (1283 renamed, 129 fused expert tensors split per expert, 0 kept as named), read in place
  [Colibri-GLM53] glm53: GGUF experts interleaved by 16 rows on 3 of 42 layers (G53_ILV16=0: the file's rows)
  [COMP-LIVE] Colibri-GLM53: elapsed=15.0s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=30.0s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=45.1s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=60.1s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=75.2s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=90.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=105.7s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=120.8s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=136.1s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=151.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=166.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=181.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=196.5s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=211.5s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=226.6s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=241.7s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=256.9s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=272.4s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=287.8s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=302.8s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=318.0s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=333.2s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=348.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=363.7s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=378.7s / cutoff=475.0s
  [Colibri-GLM53] [STATS] 43008 selections across 6945 distinct experts -> D:/apex_d_drive/models/glm53/.coli_usage
  [Colibri-GLM53] teacher_forcing 5556 335 11 15 15 22 22 22 22 36 57 22 36 64 9 154850 154850 154850 123 121 127967 127501 243 104 253 237 154842 1986 197 220 220 0 220 154827 154827 154827 154827 220 83 220 274 220 220 274 295 83 279 8 220 1 1 2776 72 83 84 365 13 220 220 220 320 83 220 220
  [Colibri-GLM53] greedy 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330
  [Colibri-GLM53] decode 64 token in 259.0s = 0.247 tok/s (4.0 s/token)
  [Colibri-GLM53] experts hits 15425 miss 11249 bytes 111319384064
=== [Colibri-GLM53] Finished rc=0 elapsed=391.30s cancelled=False ===
================================================================================
 [Stage 5 Summary] GLM53 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 1.41 | 1.10 | 827.94 | 86.61% | 641.26 | 14217.79 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 2.33 | 1.81 | 548.95 | 97.54% | 703.68 | 14627.11 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.20 | 1.67 | 591.62 | 96.45% | 809.06 | 14620.28 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.247 | - | 57.8% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 09:19 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 09:19 build/apex.exe
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
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 13.40 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    502.84 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1474.69 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7741.53 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10119.86 MB/s
   RND4K Q32T16 Read                  :    474.32 MB/s (  121426 IOPS)
   RND4K Q1T1  Read                   :    695.43 MB/s (Latency: 5.62 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     40.43 GB/s
   AVX2 256-bit Sequential Write BW   :     36.15 GB/s
   STREAM Triad (A = B + s*C) BW      :      2.30 GB/s
   Random Pointer-Chase Latency       :     61.80 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     50.82 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    141.43 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     19.44 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1093.38 tps | Avg=1093.38 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=60.4 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1104.46 tps | Avg=1098.89 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=60.7 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1013.57 tps | Avg=1068.90 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=61.0 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=922.97 tps | Avg=1028.26 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=61.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=747.22 tps | Avg=956.32 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=61.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=685.55 tps | Avg=897.26 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=61.8 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=673.69 tps | Avg=856.64 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=62.0 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=608.56 tps | Avg=815.11 tps | Hit=100.0% | NVMe=2079.9 MB/s (6.58 MB, QD=64) | RSS=62.3 MB
[LIVE-DECODE] 8/32 tok | Avg=188.73 tps | Hit=100.0% (LA:+0.0%) | NVMe=2079.9 MB/s (6.58 MB) | RSS=62.3 MB
[LIVE-DECODE] 16/32 tok | Avg=188.40 tps | Hit=100.0% (LA:+0.0%) | NVMe=2079.9 MB/s (6.58 MB) | RSS=62.3 MB
[LIVE-DECODE] 24/32 tok | Avg=188.34 tps | Hit=100.0% (LA:+0.0%) | NVMe=2079.9 MB/s (6.58 MB) | RSS=62.3 MB
[LIVE-DECODE] 32/32 tok | Avg=188.65 tps | Hit=100.0% (LA:+0.0%) | NVMe=2079.9 MB/s (6.58 MB) | RSS=62.3 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=62.32 MB | Peak=62.32 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2512.55 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.38 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.38 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.27 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.27 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.31 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.31 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.23 | 12 |  0 |  0 |     0.0 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.34 | 12 |  0 |  0 |     0.0 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.34 |  0 |  0 |  0 |     0.0 |
   |   14 |     220 | tok_220        |  147.52 |  55.4% |      55 |  147.01 |    5.33 | 12 |  0 |  0 |     0.0 |
   |   15 |     197 | tok_197        |   65.84 |  97.8% |     133 |   62.03 |    5.33 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.33 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.33 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.28 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.28 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.513s, TTFT=2512.55ms): Avg=815.11 | Min=608.56 | Max=1104.46 tps
   Prefill Chunks (8): C1:256t/1093.4tps/100% | C2:256t/1104.5tps/100% | C3:256t/1013.6tps/100% | C4:256t/923.0tps/100%
                       C5:256t/747.2tps/100% | C6:256t/685.6tps/100% | C7:256t/673.7tps/100% | C8:256t/608.6tps/100%
   Decode  (32 tok, 0.170s): Avg=188.65 | Min=185.78 | Max=191.12 tps
   Latency (ms) : Min=5.23 | P10=5.24 | P25=5.28 | P50=5.31 | P75=5.33 | P90=5.34 | P95=5.38 | P99=5.38 | Max=5.38
   Mean/SD/Jitt : Mean=5.30ms | StdDev=0.04ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=206.85 | Avg=2079.91 | Peak=5754.74 MB/s | WallAmort=2.45 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=1.32 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.41 GB moved | Active=0.55 GB/s | WallAmort=0.53 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.51s (93.7%, 0.00 MB SSD) | Decode=0.17s (6.3%, 0.00 MB SSD)
   CPU Time & Utilization       : User=3.062s + Sys=0.656s (Wall=2.702s) | SysUtil=34.4% | ThrUtil=34.4% | 31.83 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2236.03 ms ( 1075.0 us/tok | 83.37%)
   MoE AVX2 Q8 Expert Compute   :    307.43 ms (  147.8 us/tok | 11.46%)
   Router + Lookahead Dispatch  :     69.35 ms (   33.3 us/tok |  2.59%)
   LM Head Output Projection    :      6.34 ms (    3.0 us/tok |  0.24%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     63.02 ms (   30.3 us/tok |  2.35%) | Total Wall=2682.17 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    17.68%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.17%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.10%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    78.32%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.73%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1482.41 tps | Avg=1482.41 tps | Hit=99.2% | NVMe=2734.9 MB/s (24.91 MB, QD=64) | RSS=85.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1734.57 tps | Avg=1598.61 tps | Hit=99.2% | NVMe=3664.8 MB/s (42.92 MB, QD=64) | RSS=85.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=996.84 tps | Avg=1330.82 tps | Hit=99.2% | NVMe=4092.5 MB/s (61.04 MB, QD=64) | RSS=86.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1129.83 tps | Avg=1274.15 tps | Hit=99.2% | NVMe=4419.1 MB/s (79.10 MB, QD=64) | RSS=86.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1107.28 tps | Avg=1236.87 tps | Hit=99.2% | NVMe=4405.1 MB/s (97.14 MB, QD=64) | RSS=86.9 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1183.91 tps | Avg=1227.72 tps | Hit=99.2% | NVMe=4647.5 MB/s (115.20 MB, QD=64) | RSS=87.4 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1102.64 tps | Avg=1208.14 tps | Hit=99.2% | NVMe=4755.1 MB/s (133.27 MB, QD=64) | RSS=87.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=947.43 tps | Avg=1167.96 tps | Hit=99.2% | NVMe=4939.7 MB/s (151.30 MB, QD=64) | RSS=88.2 MB
[LIVE-DECODE] 8/32 tok | Avg=137.37 tps | Hit=99.2% (LA:+0.0%) | NVMe=4793.2 MB/s (152.70 MB) | RSS=88.2 MB
[LIVE-DECODE] 16/32 tok | Avg=142.69 tps | Hit=99.2% (LA:+0.1%) | NVMe=4733.9 MB/s (153.28 MB) | RSS=88.2 MB
[LIVE-DECODE] 24/32 tok | Avg=142.72 tps | Hit=99.2% (LA:+0.1%) | NVMe=4646.3 MB/s (154.23 MB) | RSS=88.2 MB
[LIVE-DECODE] 32/32 tok | Avg=142.98 tps | Hit=99.2% (LA:+0.1%) | NVMe=4567.9 MB/s (155.30 MB) | RSS=88.2 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=88.19 MB | Peak=88.19 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1753.48 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    7.26 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    7.26 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    6.71 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    6.71 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    7.93 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    7.93 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    7.23 | 16 |  0 |  0 |    32.0 |
   |   28 |      49 | qtok_49        |   65.10 | 100.0% |      18 |   55.78 |    7.28 | 10 |  6 |  0 |   198.5 |
   |   29 |     148 | qtok_148       |   77.89 | 100.0% |     127 |   51.09 |    7.28 |  0 |  0 |  0 |   198.5 |
   |   22 |     128 | qtok_128       |   64.14 |  98.8% |       2 |   59.73 |    7.25 | 12 |  4 |  0 |   115.2 |
   |   23 |      63 | qtok_63        |   98.11 | 100.0% |     113 |   72.66 |    7.25 |  0 |  0 |  0 |   115.2 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    6.93 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    6.93 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    6.69 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    6.69 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.753s, TTFT=1753.48ms): Avg=1167.96 | Min=947.43 | Max=1734.57 tps
   Prefill Chunks (8): C1:256t/1482.4tps/99% | C2:256t/1734.6tps/99% | C3:256t/996.8tps/99% | C4:256t/1129.8tps/99%
                       C5:256t/1107.3tps/99% | C6:256t/1183.9tps/99% | C7:256t/1102.6tps/99% | C8:256t/947.4tps/99%
   Decode  (32 tok, 0.224s): Avg=142.98 | Min=126.17 | Max=151.86 tps
   Latency (ms) : Min=6.58 | P10=6.61 | P25=6.72 | P50=6.93 | P75=7.25 | P90=7.28 | P95=7.93 | P99=7.93 | Max=7.93
   Mean/SD/Jitt : Mean=6.99ms | StdDev=0.34ms | Jitter=0.18ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33024): RawRAM=32726 (99.10%) | Lookahead=42 (+0.13%) | ColdMiss=256 (0.78%) | EFF HIT=99.22%
   Lookahead    : 55 prefetched -> 46 consumed (83.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8256 | 8190 |   2 |  64 | 99.2%|   3.58 | | L02 | 8256 | 8171 |  21 |  64 | 99.2%|   4.99 |
   | L01 | 8256 | 8179 |  13 |  64 | 99.2%|   4.23 | | L03 | 8256 | 8186 |   6 |  64 | 99.2%|   3.85 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 155.30 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=4.00 MB)
   SSD Data/Token (Decode)      : Avg=0.125 MB/tok (Min=0.031 | P50=0.113 | P95=0.523 | Max=0.523 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 93 Batches | 34206 Raw -> 374 Merged (33832 LBA Merges, Avg 425.2 KB/io)
   SSD I/O Size Histogram       : <64K=220 | 64K-512K=154 | 512K-2M=0 | >2M=0
   SSD Read Bandwidth (Active)  : Min=385.21 | Avg=4567.89 | Peak=10862.24 MB/s | WallAmort=78.54 MB/s
   OS Kernel I/O Verification   : Read=24.47 MB | Write=0.00 MB | Syscalls=391
   Sync Stall vs Async DMA      : SyncStall=8.46 ms | AsyncOverlapped=32.51 ms (79.3% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.21 GB/s | WallAmort=1.06 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.75s (88.7%, 144.44 MB SSD) | Decode=0.22s (11.3%, 4.00 MB SSD)
   CPU Time & Utilization       : User=2.609s + Sys=0.469s (Wall=2.007s) | SysUtil=38.3% | ThrUtil=38.3% | 35.47 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1213.25 ms (  583.3 us/tok | 61.36%)
   MoE AVX2 Q8 Expert Compute   :    512.52 ms (  246.4 us/tok | 25.92%)
   Router + Lookahead Dispatch  :     95.04 ms (   45.7 us/tok |  4.81%)
   LM Head Output Projection    :      7.28 ms (    3.5 us/tok |  0.37%)
   Foreground NVMe Sync Stall   :      8.46 ms (    4.1 us/tok |  0.43%)
   Unaccounted / OMP & Sampling :    140.74 ms (   67.7 us/tok |  7.12%) | Total Wall=1977.29 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    16.34%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.42%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.79%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    72.91%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.54%  |
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
  "kv_cache_ram_bytes": 10797056,
  "kv_bytes_per_token": 2560,
  "expert_cache_ram_bytes": 2534400,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 250.2,
    "avg_tps": 655.49,
    "min_tps": 532.87,
    "max_tps": 738.29
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 131.73,
    "min_tps": 112.2,
    "max_tps": 157.69,
    "p50_ms": 7.52,
    "p90_ms": 8.12,
    "p99_ms": 8.91,
    "mean_ms": 7.59,
    "jitter_ms": 0.4
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
    "avg_mbs": 1764.52,
    "peak_mbs": 6127.45,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 1.18
  },
  "os_verification": {
    "io_read_bytes": 0,
    "io_write_bytes": 0,
    "io_syscalls": 0,
    "cpu_user_sec": 0.0,
    "cpu_sys_sec": 0.0,
    "ram_bytes_moved": 269808128
  },
  "kernel_attribution_ms": {
    "dense_attention": 411.55,
    "moe_compute": 110.22,
    "router_lookahead": 7.32,
    "lm_head": 9.96,
    "unaccounted": 7.21
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 85.66,
    "ram_bandwidth_pinning": 1.74,
    "expert_cache_lrfu": 10.75,
    "lookahead_parallel_overlap": 1.37,
    "ssd_nvme_throughput": 0.48,
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
    "ttft_ms": 315.55,
    "avg_tps": 519.73,
    "min_tps": 369.6,
    "max_tps": 592.53
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 118.03,
    "min_tps": 97.54,
    "max_tps": 123.98,
    "p50_ms": 8.24,
    "p90_ms": 9.49,
    "p99_ms": 10.25,
    "mean_ms": 8.47,
    "jitter_ms": 0.27
  },
  "cache": {
    "raw_hit_rate_pct": 85.44,
    "effective_hit_rate_pct": 94.95,
    "warmup_tokens_to_75pct": 1
  },
  "ssd": {
    "total_bytes_transferred": 37982304,
    "prefill_bytes": 20240384,
    "warmup_bytes": 0,
    "decode_bytes": 12185088,
    "bytes_per_token": 187104.95,
    "avg_mbs": 2608.45,
    "peak_mbs": 8496.65,
    "sync_wait_ms": 4.69,
    "async_overlap_ms": 12.65
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
    "dense_attention": 369.41,
    "moe_compute": 208.23,
    "router_lookahead": 9.5,
    "lm_head": 9.29,
    "unaccounted": 44.85
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.8,
    "ram_bandwidth_pinning": 2.07,
    "expert_cache_lrfu": 8.13,
    "lookahead_parallel_overlap": 4.37,
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
Host CPU: AMD EPYC 7763 64-Core Processor | Cores=2 Threads=4 | RAM=15.99 GB

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 13.44 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    548.99 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1462.35 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7724.99 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10172.70 MB/s
   RND4K Q32T16 Read                  :    491.26 MB/s (  125763 IOPS)
   RND4K Q1T1  Read                   :    730.25 MB/s (Latency: 5.35 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     55.89 GB/s
   AVX2 256-bit Sequential Write BW   :     51.63 GB/s
   STREAM Triad (A = B + s*C) BW      :     40.73 GB/s
   Random Pointer-Chase Latency       :     68.40 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.43 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    196.28 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.19 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 30.95 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 165.79 MB/s (6.18s)
   Window #01 (300.0 MB in 0.50s):   595.01 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   389.23 MB/s (Uncached Direct Read)
   Window #03 (208.0 MB in 0.50s):   415.81 MB/s (Uncached Direct Read)
   Window #04 (188.0 MB in 0.50s):   374.63 MB/s (Uncached Direct Read)
   Window #05 (132.0 MB in 0.31s):   429.77 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   441.95 MB/s (Min=374.63 | Max=595.01 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 391.79 MB/s (2.61s)
   Window #01 (220.0 MB in 0.54s):   409.50 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.51s):   386.72 MB/s (Uncached Direct Read)
   Window #03 (216.0 MB in 0.54s):   398.78 MB/s (Uncached Direct Read)
   Window #04 (196.0 MB in 0.51s):   387.24 MB/s (Uncached Direct Read)
   Window #05 (196.0 MB in 0.46s):   424.10 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   400.93 MB/s (Min=386.72 | Max=424.10 MB/s)
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
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 14.59 GB Available
   Active Drive Space : 150.00 GB Total / 54.59 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    422.13 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1587.50 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7037.34 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9258.22 MB/s
   RND4K Q32T16 Read                  :    361.34 MB/s (   92504 IOPS)
   RND4K Q1T1  Read                   :    642.10 MB/s (Latency: 6.08 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     54.87 GB/s
   AVX2 256-bit Sequential Write BW   :     48.11 GB/s
   STREAM Triad (A = B + s*C) BW      :     38.68 GB/s
   Random Pointer-Chase Latency       :     55.20 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.19 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    141.18 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     20.53 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=1.16 tps | Avg=1.16 tps | Hit=73.4% | NVMe=579.5 MB/s (23748.52 MB, QD=64) | RSS=14121.1 MB

 >>> [Apex-Model-Response] !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=345.25 MB (36864 B/tok)
   LRFU Cache / Staging Ring    : 6937.50 MB (740/12384 exp = 5.98% pinned) | Staging=300.00 MB
   Process RSS (Start/End/Peak) : Start=4.83 MB | End=14092.20 MB | Peak=14409.30 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (70 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 60432.79 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan | 1359.04 |260 | 54 | 22 | 447392.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan | 1359.04 |  0 |  0 |  0 | 447392.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan | 1170.84 |287 | 24 | 25 | 373024.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan | 1170.84 |  0 |  0 |  0 | 373024.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan | 1139.41 |298 | 15 | 23 | 348704.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan | 1139.41 |  0 |  0 |  0 | 348704.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan | 1074.65 |300 | 11 | 25 | 332864.0 |
   |    9 |       0 | !              |     nan | 100.0% |       1 |     nan | 1074.65 |  0 |  0 |  0 | 332864.0 |
   |   10 |       0 | !              |     nan | 100.0% |       1 |     nan |  987.19 |305 | 15 | 16 | 322944.0 |
   |   11 |       0 | !              |     nan | 100.0% |       1 |     nan |  987.19 |  0 |  0 |  0 | 322944.0 |
   |   24 |       0 | !              |     nan | 100.0% |       1 |     nan |  968.14 |331 |  2 |  3 | 311616.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  763.47 |329 |  4 |  3 | 221056.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  763.47 |  0 |  0 |  0 | 221056.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  816.09 |332 |  1 |  3 | 266816.0 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  816.09 |  0 |  0 |  0 | 266816.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 60.433s, TTFT=60432.79ms): Avg=1.16 | Min=1.16 | Max=1.16 tps
   Prefill Chunks (1): C1:70t/1.2tps/73%
   Decode  (64 tok, 55.213s): Avg=1.16 | Min=0.74 | Max=1.46 tps
   Latency (ms) : Min=685.12 | P10=745.93 | P25=763.47 | P50=816.09 | P75=908.55 | P90=1074.65 | P95=1170.84 | P99=1359.04 | Max=1359.04
   Mean/SD/Jitt : Mean=862.70ms | StdDev=144.68ms | Jitter=39.25ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (18795): RawRAM=15620 (83.11%) | Lookahead=821 (+4.37%) | ColdMiss=2354 (12.52%) | EFF HIT=87.48%
   Lookahead    : 2402 prefetched -> 444 consumed (18.5% util) | Warmup >=75%:5t, >=85%:45t
   Trajectory   : @16= 78.9% | @64= 87.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  536 |  83 | 197 | 75.9%|3442.81 | | L24 |  347 |  326 |   0 |  21 | 93.9%| 150.94 |
   | L04 |  816 |  523 |  93 | 200 | 75.5%|4449.06 | | L25 |  347 |  326 |   0 |  21 | 93.9%| 150.94 |
   | L05 |  816 |  509 |  94 | 213 | 73.9%|3766.25 | | L26 |  347 |  331 |   0 |  16 | 95.4%| 115.00 |
   | L06 |  816 |  508 |  92 | 216 | 73.5%|2853.44 | | L27 |  347 |  326 |   1 |  20 | 94.2%| 150.94 |
   | L07 |  816 |  553 |  69 | 194 | 76.2%|3140.94 | | L28 |  347 |  325 |   1 |  21 | 93.9%| 158.12 |
   | L08 |  816 |  510 | 118 | 188 | 77.0%|2688.12 | | L29 |  347 |  331 |   0 |  16 | 95.4%| 115.00 |
   | L09 |  816 |  542 |  83 | 191 | 76.6%|2702.50 | | L30 |  347 |  326 |   1 |  20 | 94.2%| 150.94 |
   | L10 |  816 |  516 | 115 | 185 | 77.3%|2666.56 | | L31 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L11 |  816 |  569 |  60 | 187 | 77.1%|3309.38 | | L32 |  347 |  328 |   1 |  18 | 94.8%| 136.56 |
   | L12 |  347 |  331 |   0 |  16 | 95.4%|2051.88 | | L33 |  347 |  332 |   0 |  15 | 95.7%| 107.81 |
   | L13 |  347 |  330 |   0 |  17 | 95.1%| 122.19 | | L34 |  347 |  328 |   1 |  18 | 94.8%| 136.56 |
   | L14 |  347 |  336 |   0 |  11 | 96.8%|  79.06 | | L35 |  347 |  328 |   1 |  18 | 94.8%| 136.56 |
   | L15 |  347 |  327 |   1 |  19 | 94.5%| 143.75 | | L36 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L16 |  347 |  330 |   0 |  17 | 95.1%| 122.19 | | L37 |  347 |  328 |   1 |  18 | 94.8%| 136.56 |
   | L17 |  347 |  330 |   0 |  17 | 95.1%| 122.19 | | L38 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L18 |  347 |  333 |   0 |  14 | 96.0%| 100.62 | | L39 |  347 |  327 |   1 |  19 | 94.5%| 143.75 |
   | L19 |  347 |  328 |   1 |  18 | 94.8%| 136.56 | | L40 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L20 |  347 |  327 |   1 |  19 | 94.5%| 143.75 | | L41 |  347 |  331 |   0 |  16 | 95.4%| 115.00 |
   | L21 |  347 |  328 |   1 |  18 | 94.8%| 136.56 | | L42 |  347 |  330 |   0 |  17 | 95.1%| 122.19 |
   | L22 |  347 |  325 |   1 |  21 | 93.9%| 158.12 | | L43 |  347 |  331 |   0 |  16 | 95.4%| 115.00 |
   | L23 |  347 |  325 |   1 |  21 | 93.9%| 158.12 | | L44 |  347 |  330 |   0 |  17 | 95.1%| 142.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 41637.59 MB (Load=6361.84 | Prefill=17386.69 | Warmup=0.00 | Decode=17889.06 MB)
   SSD Data/Token (Decode)      : Avg=279.517 MB/tok (Min=215.875 | P50=270.875 | P95=364.281 | Max=436.906 MB) | Prefill=248.381 MB/tok
   NVMe Batches / Requests      : 645 Batches | 15554 Raw -> 15239 Merged (315 LBA Merges, Avg 2797.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=14360
   SSD Read Bandwidth (Active)  : Min=0.47 | Avg=620.98 | Peak=5003.63 MB/s | WallAmort=360.04 MB/s (100.0% of 422.1 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=40993.12 MB | Write=128.00 MB | Syscalls=26813
   Sync Stall vs Async DMA      : SyncStall=25565.53 ms | AsyncOverlapped=52282.32 ms (67.2% Overlapped)
   RAM Traffic & Active BW      : 625.13 GB moved | Active=8.45 GB/s (21.8% STREAM) | WallAmort=5.41 GB/s (Max=38.68 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=60.43s (52.3%, 17386.69 MB SSD) | Decode=55.21s (47.7%, 17889.06 MB SSD)
   CPU Time & Utilization       : User=241.766s + Sys=9.156s (Wall=134.885s) | SysUtil=46.5% | ThrUtil=46.5% | 65.66 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  39258.56 ms (292974.3 us/tok | 33.95%)
   MoE AVX2 Q8 Expert Compute   :  32770.35 ms (244554.8 us/tok | 28.34%)
   Router + Lookahead Dispatch  :    889.59 ms ( 6638.8 us/tok |  0.77%)
   LM Head Output Projection    :   1985.50 ms (14817.2 us/tok |  1.72%)
   Foreground NVMe Sync Stall   :  25565.53 ms (190787.6 us/tok | 22.11%)
   Unaccounted / OMP & Sampling :  15176.06 ms (113254.2 us/tok | 13.12%) | Total Wall=115645.60 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    49.06%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.92%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    19.26%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    15.40%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     3.36%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_glm53_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=6750.00 MB (720 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=1.41 tps | Avg=1.41 tps | Hit=78.2% | NVMe=641.2 MB/s (18800.09 MB, QD=64) | RSS=14163.0 MB
[LIVE-DECODE] 2/32 tok | Avg=0.65 tps | Hit=78.8% (LA:+8.7%) | NVMe=633.0 MB/s (19645.09 MB) | RSS=14112.0 MB
[LIVE-DECODE] 4/32 tok | Avg=0.70 tps | Hit=79.6% (LA:+8.7%) | NVMe=628.7 MB/s (20344.90 MB) | RSS=14074.5 MB
[LIVE-DECODE] 6/32 tok | Avg=0.77 tps | Hit=80.2% (LA:+8.6%) | NVMe=624.6 MB/s (20973.46 MB) | RSS=14051.9 MB
[LIVE-DECODE] 8/32 tok | Avg=0.83 tps | Hit=80.8% (LA:+8.3%) | NVMe=622.8 MB/s (21514.21 MB) | RSS=14029.2 MB
[LIVE-DECODE] 10/32 tok | Avg=0.87 tps | Hit=81.4% (LA:+8.1%) | NVMe=621.2 MB/s (22062.15 MB) | RSS=14017.9 MB
[LIVE-DECODE] 12/32 tok | Avg=0.91 tps | Hit=82.1% (LA:+7.9%) | NVMe=622.2 MB/s (22536.02 MB) | RSS=14015.7 MB
[LIVE-DECODE] 14/32 tok | Avg=0.94 tps | Hit=82.6% (LA:+7.7%) | NVMe=622.3 MB/s (23066.15 MB) | RSS=14010.0 MB
[LIVE-DECODE] 16/32 tok | Avg=0.95 tps | Hit=83.1% (LA:+7.5%) | NVMe=623.5 MB/s (23680.96 MB) | RSS=13992.6 MB
[LIVE-DECODE] 18/32 tok | Avg=0.97 tps | Hit=83.7% (LA:+7.3%) | NVMe=625.4 MB/s (24185.77 MB) | RSS=13982.1 MB
[LIVE-DECODE] 20/32 tok | Avg=1.00 tps | Hit=84.2% (LA:+7.1%) | NVMe=625.9 MB/s (24635.27 MB) | RSS=13980.5 MB
[LIVE-DECODE] 22/32 tok | Avg=1.01 tps | Hit=84.6% (LA:+6.9%) | NVMe=627.3 MB/s (25135.09 MB) | RSS=13973.2 MB
[LIVE-DECODE] 24/32 tok | Avg=1.03 tps | Hit=85.1% (LA:+6.7%) | NVMe=629.8 MB/s (25651.46 MB) | RSS=13972.2 MB
[LIVE-DECODE] 26/32 tok | Avg=1.05 tps | Hit=85.5% (LA:+6.5%) | NVMe=633.1 MB/s (26170.65 MB) | RSS=13969.4 MB
[LIVE-DECODE] 28/32 tok | Avg=1.07 tps | Hit=85.9% (LA:+6.3%) | NVMe=634.8 MB/s (26651.71 MB) | RSS=13964.7 MB
[LIVE-DECODE] 32/32 tok | Avg=1.10 tps | Hit=86.6% (LA:+6.1%) | NVMe=641.3 MB/s (27628.21 MB) | RSS=13955.6 MB

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
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=345.25 MB (36864 B/tok)
   LRFU Cache / Staging Ring    : 6750.00 MB (720/12384 exp = 5.81% pinned) | Staging=300.00 MB
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=13955.64 MB | Peak=14217.79 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 45471.13 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan | 1527.17 |266 | 44 | 26 | 432640.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan | 1527.17 |  0 |  0 |  0 | 432640.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan | 1310.40 |290 | 29 | 17 | 358304.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan | 1310.40 |  0 |  0 |  0 | 358304.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan | 1052.74 |296 | 18 | 22 | 321824.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan | 1052.74 |  0 |  0 |  0 | 321824.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  942.34 |310 | 10 | 16 | 276864.0 |
   |    9 |       0 | !              |     nan | 100.0% |       1 |     nan |  942.34 |  0 |  0 |  0 | 276864.0 |
   |   16 |       0 | !              |     nan | 100.0% |       1 |     nan |  940.57 |317 |  9 | 10 | 314784.0 |
   |   17 |       0 | !              |     nan | 100.0% |       1 |     nan |  940.57 |  0 |  0 |  0 | 314784.0 |
   |   10 |       0 | !              |     nan | 100.0% |       1 |     nan |  936.31 |315 | 10 | 11 | 280544.0 |
   |   30 |       0 | !              |     nan | 100.0% |       1 |     nan |  682.99 |326 |  5 |  5 | 253664.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  682.99 |  0 |  0 |  0 | 253664.0 |
   |   32 |       0 | !              |     nan | 100.0% |       1 |     nan |  767.09 |332 |  2 |  2 | 246304.0 |
   |   33 |       0 | !              |     nan | 100.0% |       1 |     nan |  767.09 |  0 |  0 |  0 | 246304.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 45.471s, TTFT=45471.13ms): Avg=1.41 | Min=1.41 | Max=1.41 tps
   Prefill Chunks (1): C1:64t/1.4tps/78%
   Decode  (32 tok, 29.191s): Avg=1.10 | Min=0.65 | Max=1.46 tps
   Latency (ms) : Min=682.99 | P10=758.45 | P25=776.19 | P50=827.94 | P75=942.34 | P90=1310.40 | P95=1527.17 | P99=1527.17 | Max=1527.17
   Mean/SD/Jitt : Mean=912.21ms | StdDev=214.78ms | Jitter=39.30ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (12110): RawRAM=9755 (80.55%) | Lookahead=733 (+6.05%) | ColdMiss=1622 (13.39%) | EFF HIT=86.61%
   Lookahead    : 1242 prefetched -> 371 consumed (29.9% util) | Warmup >=75%:1t, >=85%:23t
   Trajectory   : @16= 83.1% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  370 |  73 | 197 | 69.2%|2544.38 | | L24 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L04 |  640 |  367 |  92 | 181 | 71.7%|2680.94 | | L25 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L05 |  640 |  360 |  66 | 214 | 66.6%|2716.88 | | L26 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L06 |  640 |  376 |  74 | 190 | 70.3%|2235.31 | | L27 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L07 |  640 |  417 |  73 | 150 | 76.6%|1732.19 | | L28 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L08 |  640 |  383 |  94 | 163 | 74.5%|1919.06 | | L29 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L09 |  640 |  386 |  88 | 166 | 74.1%|1926.25 | | L30 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L10 |  640 |  374 |  97 | 169 | 73.6%|1897.50 | | L31 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L11 |  640 |  422 |  76 | 142 | 77.8%|2109.38 | | L32 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L12 |  206 |  188 |   0 |  18 | 91.3%|1264.62 | | L33 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L13 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L34 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L14 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L35 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L15 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L36 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L16 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L37 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L17 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L38 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L18 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L39 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L19 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L40 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L20 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L41 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L21 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L42 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L22 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L43 |  192 |  191 |   0 |   1 | 99.5%|   7.19 |
   | L23 |  192 |  191 |   0 |   1 | 99.5%|   7.19 | | L44 |  192 |  191 |   0 |   1 | 99.5%|   8.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 27628.21 MB (Load=6361.84 | Prefill=12438.25 | Warmup=0.00 | Decode=8828.12 MB)
   SSD Data/Token (Decode)      : Avg=275.879 MB/tok (Min=224.750 | P50=259.594 | P95=422.500 | Max=422.500 MB) | Prefill=194.348 MB/tok
   NVMe Batches / Requests      : 377 Batches | 9878 Raw -> 9679 Merged (199 LBA Merges, Avg 2923.0 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=8800
   SSD Read Bandwidth (Active)  : Min=0.48 | Avg=641.26 | Peak=4734.07 MB/s | WallAmort=370.05 MB/s
   OS Kernel I/O Verification   : Read=23348.37 MB | Write=0.00 MB | Syscalls=13714
   Sync Stall vs Async DMA      : SyncStall=13124.51 ms | AsyncOverlapped=28336.86 ms (68.3% Overlapped)
   RAM Traffic & Active BW      : 342.62 GB moved | Active=6.54 GB/s | WallAmort=4.59 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=45.47s (60.9%, 12438.25 MB SSD) | Decode=29.19s (39.1%, 8828.12 MB SSD)
   CPU Time & Utilization       : User=169.250s + Sys=6.469s (Wall=93.134s) | SysUtil=47.2% | ThrUtil=47.2% | 43.63 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  31010.88 ms (323030.0 us/tok | 41.54%)
   MoE AVX2 Q8 Expert Compute   :  20368.67 ms (212173.7 us/tok | 27.28%)
   Router + Lookahead Dispatch  :    690.52 ms ( 7192.9 us/tok |  0.92%)
   LM Head Output Projection    :    986.94 ms (10280.6 us/tok |  1.32%)
   Foreground NVMe Sync Stall   :  13124.51 ms (136713.7 us/tok | 17.58%)
   Unaccounted / OMP & Sampling :   8480.20 ms (88335.4 us/tok | 11.36%) | Total Wall=74661.73 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    47.56%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    11.66%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    18.75%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    17.46%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.57%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_glm53_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=7096.88 MB (757 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=2.29 tps | Avg=2.29 tps | Hit=93.2% | NVMe=666.6 MB/s (13694.77 MB, QD=64) | RSS=14354.8 MB
[LIVE-PREFILL] 512/512 tok | Chunk=2.37 tps | Avg=2.33 tps | Hit=95.5% | NVMe=671.2 MB/s (15723.84 MB, QD=64) | RSS=14327.7 MB
[LIVE-DECODE] 8/128 tok | Avg=1.67 tps | Hit=95.7% (LA:+2.2%) | NVMe=682.2 MB/s (16251.59 MB) | RSS=14359.4 MB
[LIVE-DECODE] 16/128 tok | Avg=1.74 tps | Hit=95.9% (LA:+2.1%) | NVMe=687.6 MB/s (16416.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 24/128 tok | Avg=1.77 tps | Hit=96.1% (LA:+2.0%) | NVMe=688.9 MB/s (16460.02 MB) | RSS=14359.4 MB
[LIVE-DECODE] 32/128 tok | Avg=1.78 tps | Hit=96.3% (LA:+1.9%) | NVMe=690.8 MB/s (16517.52 MB) | RSS=14359.4 MB
[LIVE-DECODE] 40/128 tok | Avg=1.79 tps | Hit=96.4% (LA:+1.9%) | NVMe=693.6 MB/s (16603.77 MB) | RSS=14359.4 MB
[LIVE-DECODE] 48/128 tok | Avg=1.79 tps | Hit=96.6% (LA:+1.8%) | NVMe=695.8 MB/s (16675.65 MB) | RSS=14359.4 MB
[LIVE-DECODE] 56/128 tok | Avg=1.80 tps | Hit=96.7% (LA:+1.8%) | NVMe=700.1 MB/s (16797.84 MB) | RSS=14359.4 MB
[LIVE-DECODE] 64/128 tok | Avg=1.80 tps | Hit=96.8% (LA:+1.7%) | NVMe=700.5 MB/s (16812.21 MB) | RSS=14359.4 MB
[LIVE-DECODE] 72/128 tok | Avg=1.80 tps | Hit=96.9% (LA:+1.6%) | NVMe=702.5 MB/s (16869.71 MB) | RSS=14359.4 MB
[LIVE-DECODE] 80/128 tok | Avg=1.80 tps | Hit=97.0% (LA:+1.6%) | NVMe=702.7 MB/s (16876.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 88/128 tok | Avg=1.80 tps | Hit=97.1% (LA:+1.5%) | NVMe=702.7 MB/s (16876.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 96/128 tok | Avg=1.81 tps | Hit=97.2% (LA:+1.5%) | NVMe=702.7 MB/s (16876.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 104/128 tok | Avg=1.81 tps | Hit=97.3% (LA:+1.4%) | NVMe=702.7 MB/s (16876.90 MB) | RSS=14359.4 MB
[LIVE-DECODE] 112/128 tok | Avg=1.81 tps | Hit=97.4% (LA:+1.4%) | NVMe=703.7 MB/s (16912.84 MB) | RSS=14360.0 MB
[LIVE-DECODE] 120/128 tok | Avg=1.81 tps | Hit=97.5% (LA:+1.4%) | NVMe=703.7 MB/s (16912.84 MB) | RSS=14352.8 MB
[LIVE-DECODE] 128/128 tok | Avg=1.81 tps | Hit=97.5% (LA:+1.3%) | NVMe=703.7 MB/s (16912.84 MB) | RSS=14346.0 MB

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
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=345.25 MB (36864 B/tok)
   LRFU Cache / Staging Ring    : 7096.88 MB (757/12384 exp = 6.11% pinned) | Staging=300.00 MB
   Process RSS (Start/End/Peak) : Start=4.70 MB | End=14346.04 MB | Peak=14627.11 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (128 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 219523.73 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  693.89 |328 |  0 |  8 | 89088.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  693.89 |  0 |  0 |  0 | 89088.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  583.10 |334 |  2 |  0 | 36800.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  583.10 |  0 |  0 |  0 | 36800.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  567.32 |333 |  3 |  0 | 22080.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  567.32 |  0 |  0 |  0 | 22080.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  551.69 |333 |  3 |  0 | 22080.0 |
   |   66 |       0 | !              |     nan | 100.0% |       1 |     nan |  564.46 |335 |  1 |  0 | 14720.0 |
   |   67 |       0 | !              |     nan | 100.0% |       1 |     nan |  564.46 |  0 |  0 |  0 | 14720.0 |
   |   12 |       0 | !              |     nan | 100.0% |       1 |     nan |  561.59 |335 |  1 |  0 | 18400.0 |
   |   13 |       0 | !              |     nan | 100.0% |       1 |     nan |  561.59 |  0 |  0 |  0 | 18400.0 |
   |  126 |       0 | !              |     nan | 100.0% |       1 |     nan |  547.97 |336 |  0 |  0 |     0.0 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  547.97 |  0 |  0 |  0 |     0.0 |
   |  128 |       0 | !              |     nan | 100.0% |       1 |     nan |  547.20 |336 |  0 |  0 |     0.0 |
   |  129 |       0 | !              |     nan | 100.0% |       1 |     nan |  547.20 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 219.524s, TTFT=219523.73ms): Avg=2.33 | Min=2.29 | Max=2.37 tps
   Prefill Chunks (2): C1:256t/2.3tps/93% | C2:256t/2.4tps/96%
   Decode  (128 tok, 70.738s): Avg=1.81 | Min=1.44 | Max=1.83 tps
   Latency (ms) : Min=545.79 | P10=546.91 | P25=547.51 | P50=548.95 | P75=550.62 | P90=555.33 | P95=564.46 | P99=693.89 | Max=693.89
   Mean/SD/Jitt : Mean=552.64ms | StdDev=18.71ms | Jitter=2.41ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (47551): RawRAM=45755 (96.22%) | Lookahead=627 (+1.32%) | ColdMiss=1169 (2.46%) | EFF HIT=97.54%
   Lookahead    : 249 prefetched -> 150 consumed (60.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 95.9% | @64= 96.8% | @128= 97.5% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3558 | 565 | 485 | 89.5%|4485.00 | | L24 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L04 | 1297 | 1111 |  35 | 151 | 88.4%|1753.75 | | L25 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L05 | 1234 | 1082 |  27 | 125 | 89.9%|1070.94 | | L26 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L06 | 1101 | 1038 |   0 |  63 | 94.3%| 488.75 | | L27 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L07 | 1101 | 1043 |   0 |  58 | 94.7%| 438.44 | | L28 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L08 | 1101 | 1044 |   0 |  57 | 94.8%| 431.25 | | L29 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L09 | 1101 | 1041 |   0 |  60 | 94.6%| 438.44 | | L30 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L10 | 1101 | 1041 |   0 |  60 | 94.6%| 452.81 | | L31 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L11 | 1101 | 1040 |   0 |  61 | 94.5%| 609.38 | | L32 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L12 | 1038 | 1021 |   0 |  17 | 98.4%| 142.38 | | L33 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L13 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L34 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L14 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L35 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L15 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L36 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L16 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L37 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L17 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L38 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L18 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L39 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L19 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L40 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L20 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L41 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L21 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L42 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L22 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L43 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 |
   | L23 | 1024 | 1023 |   0 |   1 | 99.9%|   7.19 | | L44 | 1024 | 1023 |   0 |   1 | 99.9%|   8.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 16912.84 MB (Load=6361.84 | Prefill=9362.00 | Warmup=195.62 | Decode=993.38 MB)
   SSD Data/Token (Decode)      : Avg=7.761 MB/tok (Min=0.000 | P50=3.594 | P95=25.156 | Max=87.000 MB) | Prefill=18.285 MB/tok
   NVMe Batches / Requests      : 154 Batches | 5618 Raw -> 5555 Merged (63 LBA Merges, Avg 3117.7 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=4676
   SSD Read Bandwidth (Active)  : Min=0.32 | Avg=703.68 | Peak=5816.19 MB/s | WallAmort=58.27 MB/s
   OS Kernel I/O Verification   : Read=12896.93 MB | Write=0.00 MB | Syscalls=9592
   Sync Stall vs Async DMA      : SyncStall=6811.34 ms | AsyncOverlapped=9320.69 ms (57.8% Overlapped)
   RAM Traffic & Active BW      : 1348.20 GB moved | Active=4.90 GB/s | WallAmort=4.64 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=219.52s (75.6%, 9362.00 MB SSD) | Decode=70.74s (24.4%, 993.38 MB SSD)
   CPU Time & Utilization       : User=971.672s + Sys=14.266s (Wall=308.835s) | SysUtil=79.8% | ThrUtil=79.8% | 73.83 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 206464.25 ms (322600.4 us/tok | 71.13%)
   MoE AVX2 Q8 Expert Compute   :  64816.98 ms (101276.5 us/tok | 22.33%)
   Router + Lookahead Dispatch  :   4329.60 ms ( 6765.0 us/tok |  1.49%)
   LM Head Output Projection    :   3682.32 ms ( 5753.6 us/tok |  1.27%)
   Foreground NVMe Sync Stall   :   6811.34 ms (10642.7 us/tok |  2.35%)
   Unaccounted / OMP & Sampling :   4157.38 ms ( 6495.9 us/tok |  1.43%) | Total Wall=290261.87 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    61.78%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.75%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.13%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    27.87%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.47%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_glm53_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 45373.7ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='!!!!!!!!!!!!!!!!'
[Stage 3] /v1/chat/completions (stream=true SSE) 25674.4ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_glm53_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=7087.50 MB (756 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1.91 tps | Avg=1.91 tps | Hit=92.3% | NVMe=808.9 MB/s (24020.09 MB, QD=64) | RSS=14454.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.21 tps | Avg=2.05 tps | Hit=93.0% | NVMe=837.4 MB/s (31056.34 MB, QD=64) | RSS=14440.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.28 tps | Avg=2.12 tps | Hit=93.8% | NVMe=831.8 MB/s (34925.40 MB, QD=64) | RSS=14366.4 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.31 tps | Avg=2.16 tps | Hit=94.6% | NVMe=822.4 MB/s (36916.34 MB, QD=64) | RSS=14312.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.28 tps | Avg=2.19 tps | Hit=95.2% | NVMe=814.8 MB/s (38821.02 MB, QD=64) | RSS=14400.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.24 tps | Avg=2.19 tps | Hit=95.6% | NVMe=811.2 MB/s (40761.65 MB, QD=64) | RSS=14354.3 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.22 tps | Avg=2.20 tps | Hit=95.9% | NVMe=805.7 MB/s (42766.96 MB, QD=64) | RSS=14383.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.19 tps | Avg=2.20 tps | Hit=96.1% | NVMe=798.4 MB/s (44678.84 MB, QD=64) | RSS=14340.9 MB
[LIVE-DECODE] 8/64 tok | Avg=1.52 tps | Hit=96.2% (LA:+4.3%) | NVMe=802.7 MB/s (45317.21 MB) | RSS=14350.0 MB
[LIVE-DECODE] 16/64 tok | Avg=1.59 tps | Hit=96.2% (LA:+4.3%) | NVMe=805.6 MB/s (45540.02 MB) | RSS=14350.0 MB
[LIVE-DECODE] 24/64 tok | Avg=1.62 tps | Hit=96.3% (LA:+4.2%) | NVMe=806.8 MB/s (45633.46 MB) | RSS=14350.0 MB
[LIVE-DECODE] 32/64 tok | Avg=1.64 tps | Hit=96.3% (LA:+4.2%) | NVMe=807.1 MB/s (45662.21 MB) | RSS=14350.0 MB
[LIVE-DECODE] 40/64 tok | Avg=1.65 tps | Hit=96.3% (LA:+4.1%) | NVMe=807.4 MB/s (45690.96 MB) | RSS=14350.0 MB
[LIVE-DECODE] 48/64 tok | Avg=1.66 tps | Hit=96.4% (LA:+4.1%) | NVMe=807.9 MB/s (45734.09 MB) | RSS=14350.0 MB
[LIVE-DECODE] 56/64 tok | Avg=1.66 tps | Hit=96.4% (LA:+4.1%) | NVMe=808.6 MB/s (45784.40 MB) | RSS=14350.0 MB
[LIVE-DECODE] 64/64 tok | Avg=1.67 tps | Hit=96.5% (LA:+4.0%) | NVMe=809.1 MB/s (45820.34 MB) | RSS=14350.0 MB

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
   Pinned Dense / KV+State RAM  : Dense=6460.98 MB | KV/State=345.25 MB (36864 B/tok)
   LRFU Cache / Staging Ring    : 7087.50 MB (756/12384 exp = 6.10% pinned) | Staging=300.00 MB
   Process RSS (Start/End/Peak) : Start=4.66 MB | End=14350.00 MB | Peak=14620.28 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 932206.79 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  747.96 |329 |  2 |  5 | 81728.0 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  747.96 |  0 |  0 |  0 | 81728.0 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  632.23 |331 |  1 |  4 | 58880.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  632.23 |  0 |  0 |  0 | 58880.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  644.76 |332 |  4 |  0 | 29440.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  644.76 |  0 |  0 |  0 | 29440.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  608.87 |332 |  4 |  0 | 62560.0 |
   |   30 |       0 | !              |     nan | 100.0% |       1 |     nan |  609.95 |336 |  0 |  0 |     0.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  609.95 |  0 |  0 |  0 |     0.0 |
   |    9 |       0 | !              |     nan | 100.0% |       1 |     nan |  608.87 |  0 |  0 |  0 | 62560.0 |
   |   10 |       0 | !              |     nan | 100.0% |       1 |     nan |  607.75 |334 |  2 |  0 | 33120.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  593.77 |335 |  1 |  0 |  3680.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  593.77 |  0 |  0 |  0 |  3680.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  592.39 |335 |  1 |  0 | 14720.0 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  592.39 |  0 |  0 |  0 | 14720.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 932.207s, TTFT=932206.79ms): Avg=2.20 | Min=1.91 | Max=2.31 tps
   Prefill Chunks (8): C1:256t/1.9tps/92% | C2:256t/2.2tps/93% | C3:256t/2.3tps/94% | C4:256t/2.3tps/95%
                       C5:256t/2.3tps/95% | C6:256t/2.2tps/96% | C7:256t/2.2tps/96% | C8:256t/2.2tps/96%
   Decode  (64 tok, 38.396s): Avg=1.67 | Min=1.34 | Max=1.71 tps
   Latency (ms) : Min=585.02 | P10=586.19 | P25=587.66 | P50=591.62 | P75=596.80 | P90=609.95 | P95=644.76 | P99=747.96 | Max=747.96
   Mean/SD/Jitt : Mean=599.94ms | StdDev=29.59ms | Jitter=4.85ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (128709): RawRAM=118968 (92.43%) | Lookahead=5175 (+4.02%) | ColdMiss=4566 (3.55%) | EFF HIT=96.45%
   Lookahead    : 804 prefetched -> 733 consumed (91.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.2% | @64= 96.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |16640 |12445 |2316 |1879 | 88.7%|16250.94 | | L24 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L04 | 6812 | 5328 | 798 | 686 | 89.9%|6231.56 | | L25 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L05 | 4173 | 3388 | 483 | 302 | 92.8%|2530.00 | | L26 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L06 | 4173 | 3391 | 492 | 290 | 93.1%|2465.31 | | L27 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L07 | 4173 | 3680 | 228 | 265 | 93.6%|2141.88 | | L28 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L08 | 4173 | 3692 | 208 | 273 | 93.5%|2213.75 | | L29 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L09 | 4173 | 3686 | 207 | 280 | 93.3%|2242.50 | | L30 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L10 | 4173 | 3635 | 262 | 276 | 93.4%|2206.56 | | L31 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L11 | 4173 | 3726 | 181 | 266 | 93.6%|2793.75 | | L32 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L12 | 2318 | 2301 |   0 |  17 | 99.3%| 142.38 | | L33 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L13 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L34 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L14 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L35 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L15 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L36 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L16 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L37 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L17 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L38 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L18 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L39 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L19 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L40 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L20 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L41 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L21 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L42 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L22 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L43 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 |
   | L23 | 2304 | 2303 |   0 |   1 |100.0%|   7.19 | | L44 | 2304 | 2303 |   0 |   1 |100.0%|   8.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 45820.34 MB (Load=6361.84 | Prefill=38317.00 | Warmup=184.06 | Decode=957.44 MB)
   SSD Data/Token (Decode)      : Avg=14.960 MB/tok (Min=0.000 | P50=7.188 | P95=61.094 | Max=79.812 MB) | Prefill=18.709 MB/tok
   NVMe Batches / Requests      : 259 Batches | 17471 Raw -> 17225 Merged (246 LBA Merges, Avg 2723.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=16346
   SSD Read Bandwidth (Active)  : Min=0.42 | Avg=809.06 | Peak=5819.63 MB/s | WallAmort=47.21 MB/s
   OS Kernel I/O Verification   : Read=31303.87 MB | Write=0.00 MB | Syscalls=21260
   Sync Stall vs Async DMA      : SyncStall=28212.97 ms | AsyncOverlapped=41911.93 ms (59.8% Overlapped)
   RAM Traffic & Active BW      : 1753.13 GB moved | Active=1.91 GB/s | WallAmort=1.81 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=932.21s (96.0%, 38317.00 MB SSD) | Decode=38.40s (4.0%, 957.44 MB SSD)
   CPU Time & Utilization       : User=3262.359s + Sys=29.656s (Wall=989.065s) | SysUtil=83.2% | ThrUtil=83.2% | 76.97 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 761858.49 ms (360728.5 us/tok | 78.49%)
   MoE AVX2 Q8 Expert Compute   : 155278.40 ms (73522.0 us/tok | 16.00%)
   Router + Lookahead Dispatch  :  15394.51 ms ( 7289.1 us/tok |  1.59%)
   LM Head Output Projection    :   1908.75 ms (  903.8 us/tok |  0.20%)
   Foreground NVMe Sync Stall   :  28212.97 ms (13358.4 us/tok |  2.91%)
   Unaccounted / OMP & Sampling :   7950.12 ms ( 3764.3 us/tok |  0.82%) | Total Wall=970603.24 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    54.23%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.51%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.34%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    36.16%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.76%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_glm53_colibri_bench.log`
```text
=== [Colibri-GLM53] CMD: ./baselines/colibri/c/glm53.exe --model D:/apex_d_drive/models/glm53 --ids 1,8,15,22,29,36,43,50,57,64,71,78,85,92,99,106,113,120,127,134,141,148,155,162,169,176,183,190,197,204,211,218,225,232,239,246,253,260,267,274,281,288,295,302,309,316,323,330,337,344,351,358,365,372,379,386,393,400,407,414,421,428,435,442 --greedy 64 32 (5x cutoff=475.0s) ===
[gguf] D:\apex_d_drive\models\glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: glm5-next, 4 part(s), 38435 tensors under the checkpoint's names (1283 renamed, 129 fused expert tensors split per expert, 0 kept as named), read in place
glm53: GGUF experts interleaved by 16 rows on 3 of 42 layers (G53_ILV16=0: the file's rows)
  [COMP-LIVE] Colibri-GLM53: elapsed=15.0s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=30.0s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=45.1s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=60.1s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=75.2s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=90.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=105.7s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=120.8s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=136.1s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=151.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=166.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=181.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=196.5s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=211.5s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=226.6s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=241.7s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=256.9s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=272.4s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=287.8s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=302.8s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=318.0s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=333.2s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=348.3s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=363.7s / cutoff=475.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=378.7s / cutoff=475.0s
[STATS] 43008 selections across 6945 distinct experts -> D:/apex_d_drive/models/glm53/.coli_usage
teacher_forcing 5556 335 11 15 15 22 22 22 22 36 57 22 36 64 9 154850 154850 154850 123 121 127967 127501 243 104 253 237 154842 1986 197 220 220 0 220 154827 154827 154827 154827 220 83 220 274 220 220 274 295 83 279 8 220 1 1 2776 72 83 84 365 13 220 220 220 320 83 220 220
greedy 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330
decode 64 token in 259.0s = 0.247 tok/s (4.0 s/token)
experts hits 15425 miss 11249 bytes 111319384064
=== [Colibri-GLM53] Finished rc=0 elapsed=391.30s cancelled=False ===
```

### 📄 `12_glm53_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] GLM53 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 1.41 | 1.10 | 827.94 | 86.61% | 641.26 | 14217.79 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 2.33 | 1.81 | 548.95 | 97.54% | 703.68 | 14627.11 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.20 | 1.67 | 591.62 | 96.45% | 809.06 | 14620.28 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.247 | - | 57.8% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
