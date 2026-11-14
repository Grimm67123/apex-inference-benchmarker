<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#28 (Run ID `43567917411`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43567917411)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-14 08:18:50 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T06:45:55.189Z] ================================================================================
[2026-11-14T06:45:55.210Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T06:45:55.213Z] ================================================================================
[2026-11-14T06:45:59.865Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T06:46:00.077Z] --------------------------------------------------------------------------------
[2026-11-14T06:46:00.079Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 30.98 GB / 149.89 GB
[2026-11-14T06:46:00.081Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-14T06:46:00.082Z]  [Disk Telemetry] Total Combined Usable Free Space: 177.99 GB
[2026-11-14T06:46:00.083Z] --------------------------------------------------------------------------------
[2026-11-14T06:46:00.098Z]  [OK] Disk space verification passed: 177.99 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 06:46 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 06:46 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.48 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    479.15 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1476.37 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8003.60 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10871.09 MB/s
   RND4K Q32T16 Read                  :    493.57 MB/s (  126353 IOPS)
   RND4K Q1T1  Read                   :    708.52 MB/s (Latency: 5.51 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     57.45 GB/s
   AVX2 256-bit Sequential Write BW   :     46.77 GB/s
   STREAM Triad (A = B + s*C) BW      :     31.51 GB/s
   Random Pointer-Chase Latency       :     93.22 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.38 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    197.06 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     22.16 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1380.69 tps | Avg=1380.69 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=73.7 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1215.56 tps | Avg=1292.87 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=73.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1096.67 tps | Avg=1220.11 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=74.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=972.88 tps | Avg=1147.23 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=74.5 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=886.85 tps | Avg=1083.60 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=74.8 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=804.62 tps | Avg=1024.40 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=75.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=749.70 tps | Avg=973.45 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=75.3 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=697.13 tps | Avg=927.49 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=75.5 MB
[LIVE-DECODE] 8/32 tok | Avg=198.03 tps | Hit=100.0% (LA:+0.0%) | NVMe=2633.5 MB/s (6.58 MB) | RSS=75.6 MB
[LIVE-DECODE] 16/32 tok | Avg=196.89 tps | Hit=100.0% (LA:+0.0%) | NVMe=2633.5 MB/s (6.58 MB) | RSS=75.6 MB
[LIVE-DECODE] 24/32 tok | Avg=194.74 tps | Hit=100.0% (LA:+0.0%) | NVMe=2633.5 MB/s (6.58 MB) | RSS=75.6 MB
[LIVE-DECODE] 32/32 tok | Avg=195.57 tps | Hit=100.0% (LA:+0.0%) | NVMe=2633.5 MB/s (6.58 MB) | RSS=75.6 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=75.55 MB | Peak=75.55 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2208.10 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.06 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.06 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.01 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.01 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.06 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.06 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.06 | 12 |  0 |  0 |     0.0 |
   |   18 |     246 | tok_246        |  185.81 | 100.0% |      55 |  160.85 |    5.35 | 12 |  0 |  0 |     0.0 |
   |   19 |     228 | tok_228        |   93.10 |  98.4% |      40 |   88.99 |    5.35 |  0 |  0 |  0 |     0.0 |
   |   20 |      86 | tok_86         |  167.81 |  99.1% |     246 |  163.11 |    5.28 | 12 |  0 |  0 |     0.0 |
   |   21 |      68 | tok_68         |  177.01 | 100.0% |     246 |  152.23 |    5.28 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.06 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.06 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.00 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.00 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.208s, TTFT=2208.10ms): Avg=927.49 | Min=697.13 | Max=1380.69 tps
   Prefill Chunks (8): C1:256t/1380.7tps/100% | C2:256t/1215.6tps/100% | C3:256t/1096.7tps/100% | C4:256t/972.9tps/100%
                       C5:256t/886.9tps/100% | C6:256t/804.6tps/100% | C7:256t/749.7tps/100% | C8:256t/697.1tps/100%
   Decode  (32 tok, 0.164s): Avg=195.57 | Min=187.02 | Max=199.99 tps
   Latency (ms) : Min=5.00 | P10=5.00 | P25=5.04 | P50=5.06 | P75=5.22 | P90=5.28 | P95=5.35 | P99=5.35 | Max=5.35
   Mean/SD/Jitt : Mean=5.11ms | StdDev=0.11ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=300.62 | Avg=2633.47 | Peak=6578.95 MB/s | WallAmort=2.77 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=1.11 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.64 GB/s | WallAmort=0.60 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.21s (93.1%, 0.00 MB SSD) | Decode=0.16s (6.9%, 0.00 MB SSD)
   CPU Time & Utilization       : User=2.906s + Sys=0.750s (Wall=2.390s) | SysUtil=38.2% | ThrUtil=38.2% | 35.37 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1995.53 ms (  959.4 us/tok | 84.14%)
   MoE AVX2 Q8 Expert Compute   :    251.09 ms (  120.7 us/tok | 10.59%)
   Router + Lookahead Dispatch  :     59.07 ms (   28.4 us/tok |  2.49%)
   LM Head Output Projection    :      5.98 ms (    2.9 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     60.06 ms (   28.9 us/tok |  2.53%) | Total Wall=2371.73 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    16.08%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.13%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.09%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    79.68%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.02%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1969.71 tps | Avg=1969.71 tps | Hit=99.2% | NVMe=2663.2 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1845.16 tps | Avg=1905.40 tps | Hit=99.2% | NVMe=3599.5 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1726.69 tps | Avg=1841.86 tps | Hit=99.2% | NVMe=4158.8 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1582.15 tps | Avg=1769.25 tps | Hit=99.2% | NVMe=4623.7 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1553.52 tps | Avg=1721.44 tps | Hit=99.2% | NVMe=4957.5 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1425.97 tps | Avg=1663.98 tps | Hit=99.2% | NVMe=5192.9 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1292.10 tps | Avg=1598.26 tps | Hit=99.2% | NVMe=5384.6 MB/s (133.27 MB, QD=64) | RSS=91.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1281.33 tps | Avg=1550.33 tps | Hit=99.2% | NVMe=5559.7 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=178.69 tps | Hit=99.2% (LA:+0.0%) | NVMe=5460.8 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=179.25 tps | Hit=99.2% (LA:+0.1%) | NVMe=5406.6 MB/s (153.28 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=179.06 tps | Hit=99.2% (LA:+0.1%) | NVMe=5308.4 MB/s (154.23 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=179.23 tps | Hit=99.2% (LA:+0.1%) | NVMe=5228.4 MB/s (155.14 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=91.78 MB | Peak=91.78 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1321.01 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    5.64 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    5.64 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    5.61 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    5.61 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    5.62 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    5.62 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    5.51 | 16 |  0 |  0 |    32.0 |
   |   10 |     254 | qtok_254       |   70.81 |  99.7% |      66 |   64.77 |    5.64 | 15 |  1 |  0 |    59.8 |
   |   11 |      49 | qtok_49        |   84.60 |  79.6% |     129 |   83.23 |    5.64 |  0 |  0 |  0 |    59.8 |
   |   20 |     193 | qtok_193       |   68.95 | 100.0% |      17 |   58.95 |    5.63 | 14 |  2 |  0 |    87.5 |
   |   21 |      63 | qtok_63        |   75.06 |  99.9% |     193 |   67.57 |    5.63 |  0 |  0 |  0 |    87.5 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.49 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.49 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.59 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.59 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.321s, TTFT=1321.01ms): Avg=1550.33 | Min=1281.33 | Max=1969.71 tps
   Prefill Chunks (8): C1:256t/1969.7tps/99% | C2:256t/1845.2tps/99% | C3:256t/1726.7tps/99% | C4:256t/1582.2tps/99%
                       C5:256t/1553.5tps/99% | C6:256t/1426.0tps/99% | C7:256t/1292.1tps/99% | C8:256t/1281.3tps/99%
   Decode  (32 tok, 0.179s): Avg=179.23 | Min=177.21 | Max=182.26 tps
   Latency (ms) : Min=5.49 | P10=5.51 | P25=5.55 | P50=5.59 | P75=5.62 | P90=5.64 | P95=5.64 | P99=5.64 | Max=5.64
   Mean/SD/Jitt : Mean=5.58ms | StdDev=0.05ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=438.51 | Avg=5228.36 | Peak=10603.91 MB/s | WallAmort=103.46 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=6.34 ms | AsyncOverlapped=27.79 ms (81.4% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.61 GB/s | WallAmort=1.40 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.32s (88.1%, 144.44 MB SSD) | Decode=0.18s (11.9%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.719s + Sys=0.469s (Wall=1.530s) | SysUtil=52.1% | ThrUtil=52.1% | 48.19 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    927.15 ms (  445.7 us/tok | 61.83%)
   MoE AVX2 Q8 Expert Compute   :    375.58 ms (  180.6 us/tok | 25.05%)
   Router + Lookahead Dispatch  :     81.43 ms (   39.1 us/tok |  5.43%)
   LM Head Output Projection    :      5.82 ms (    2.8 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :      6.34 ms (    3.0 us/tok |  0.42%)
   Unaccounted / OMP & Sampling :    103.23 ms (   49.6 us/tok |  6.88%) | Total Wall=1499.55 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    18.06%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.87%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.92%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    69.67%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.48%  |
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
    "ttft_ms": 238.43,
    "avg_tps": 687.82,
    "min_tps": 567.72,
    "max_tps": 796.7
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 141.26,
    "min_tps": 116.99,
    "max_tps": 150.78,
    "p50_ms": 6.84,
    "p90_ms": 8.29,
    "p99_ms": 8.55,
    "mean_ms": 7.08,
    "jitter_ms": 0.23
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
    "avg_mbs": 2370.23,
    "peak_mbs": 6127.45,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.83
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
    "dense_attention": 386.75,
    "moe_compute": 105.1,
    "router_lookahead": 7.23,
    "lm_head": 8.86,
    "unaccounted": 6.58
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 87.61,
    "ram_bandwidth_pinning": 1.9,
    "expert_cache_lrfu": 8.69,
    "lookahead_parallel_overlap": 1.41,
    "ssd_nvme_throughput": 0.39,
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
    "ttft_ms": 302.44,
    "avg_tps": 542.25,
    "min_tps": 383.62,
    "max_tps": 613.24
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 126.91,
    "min_tps": 115.19,
    "max_tps": 130.66,
    "p50_ms": 7.83,
    "p90_ms": 8.14,
    "p99_ms": 8.68,
    "mean_ms": 7.88,
    "jitter_ms": 0.2
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
    "avg_mbs": 2444.13,
    "peak_mbs": 8680.56,
    "sync_wait_ms": 4.73,
    "async_overlap_ms": 13.49
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
    "dense_attention": 344.83,
    "moe_compute": 200.36,
    "router_lookahead": 9.13,
    "lm_head": 8.4,
    "unaccounted": 42.29
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 81.31,
    "ram_bandwidth_pinning": 2.16,
    "expert_cache_lrfu": 9.04,
    "lookahead_parallel_overlap": 4.63,
    "ssd_nvme_throughput": 2.86,
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
   System Memory (RAM): 15.99 GB Total / 13.47 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    510.04 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1467.63 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8015.68 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10515.33 MB/s
   RND4K Q32T16 Read                  :    499.72 MB/s (  127928 IOPS)
   RND4K Q1T1  Read                   :    736.21 MB/s (Latency: 5.31 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     59.02 GB/s
   AVX2 256-bit Sequential Write BW   :     38.52 GB/s
   STREAM Triad (A = B + s*C) BW      :     41.90 GB/s
   Random Pointer-Chase Latency       :     56.58 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.29 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    190.98 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     22.97 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 30.98 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 165.50 MB/s (6.19s)
   Window #01 (300.0 MB in 0.51s):   593.82 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   391.64 MB/s (Uncached Direct Read)
   Window #03 (196.0 MB in 0.50s):   388.70 MB/s (Uncached Direct Read)
   Window #04 (216.0 MB in 0.54s):   403.41 MB/s (Uncached Direct Read)
   Window #05 (116.0 MB in 0.27s):   432.17 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   442.56 MB/s (Min=388.70 | Max=593.82 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 391.46 MB/s (2.62s)
   Window #01 (200.0 MB in 0.51s):   395.56 MB/s (Uncached Direct Read)
   Window #02 (216.0 MB in 0.55s):   391.69 MB/s (Uncached Direct Read)
   Window #03 (216.0 MB in 0.54s):   403.14 MB/s (Uncached Direct Read)
   Window #04 (196.0 MB in 0.50s):   389.10 MB/s (Uncached Direct Read)
   Window #05 (196.0 MB in 0.46s):   424.31 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   400.22 MB/s (Min=389.10 | Max=424.31 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: glm53 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (0.009 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: 100.00% (0.01/0.01 GB) @ 119.7 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (46.470 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  10.76% (5.00/46.47 GB) @ 506.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  21.52% (10.00/46.47 GB) @ 371.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  32.28% (15.00/46.47 GB) @ 364.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  43.04% (20.00/46.47 GB) @ 341.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  53.80% (25.00/46.47 GB) @ 350.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  64.56% (30.00/46.47 GB) @ 355.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  75.32% (35.00/46.47 GB) @ 352.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  86.08% (40.00/46.47 GB) @ 353.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  96.84% (45.00/46.47 GB) @ 359.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf: 100.00% (46.47/46.47 GB) @ 356.7 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (45.866 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  10.90% (5.00/45.87 GB) @ 310.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  21.80% (10.00/45.87 GB) @ 324.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  32.70% (15.00/45.87 GB) @ 316.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  43.61% (20.00/45.87 GB) @ 332.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  54.51% (25.00/45.87 GB) @ 338.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  65.41% (30.00/45.87 GB) @ 338.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  76.31% (35.00/45.87 GB) @ 344.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  87.21% (40.00/45.87 GB) @ 340.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  98.11% (45.00/45.87 GB) @ 339.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf: 100.00% (45.87/45.87 GB) @ 342.8 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (2.506 GB) -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf: 100.00% (2.51/2.51 GB) @ 122.4 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=101,844,951,904 (94.85 GB) | Elapsed=293.16s
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
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5371.88 MB (573 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=76.5% | NVMe=487.3 MB/s (47437.59 MB, QD=64) | RSS=13770.9 MB
[LIVE-DECODE] 2/32 tok | Avg=0.25 tps | Hit=76.5% (LA:+10.1%) | NVMe=482.6 MB/s (50529.52 MB) | RSS=13728.8 MB
[LIVE-DECODE] 4/32 tok | Avg=0.28 tps | Hit=76.5% (LA:+10.8%) | NVMe=478.2 MB/s (52885.40 MB) | RSS=13651.4 MB
[LIVE-DECODE] 6/32 tok | Avg=0.29 tps | Hit=76.6% (LA:+11.5%) | NVMe=473.8 MB/s (55352.59 MB) | RSS=13522.0 MB
[LIVE-DECODE] 8/32 tok | Avg=0.31 tps | Hit=76.7% (LA:+12.0%) | NVMe=471.8 MB/s (57341.15 MB) | RSS=13502.4 MB
[LIVE-DECODE] 10/32 tok | Avg=0.33 tps | Hit=76.9% (LA:+12.6%) | NVMe=469.8 MB/s (59420.34 MB) | RSS=13468.9 MB
[LIVE-DECODE] 12/32 tok | Avg=0.33 tps | Hit=77.0% (LA:+13.2%) | NVMe=467.4 MB/s (61661.65 MB) | RSS=13409.7 MB
[LIVE-DECODE] 14/32 tok | Avg=0.34 tps | Hit=77.1% (LA:+13.7%) | NVMe=466.5 MB/s (63635.77 MB) | RSS=13406.9 MB
[LIVE-DECODE] 16/32 tok | Avg=0.36 tps | Hit=77.3% (LA:+13.9%) | NVMe=465.8 MB/s (65208.09 MB) | RSS=13406.8 MB
[LIVE-DECODE] 18/32 tok | Avg=0.35 tps | Hit=77.3% (LA:+14.5%) | NVMe=463.9 MB/s (67659.02 MB) | RSS=13406.8 MB
[LIVE-DECODE] 20/32 tok | Avg=0.35 tps | Hit=77.4% (LA:+14.9%) | NVMe=462.2 MB/s (69754.71 MB) | RSS=13337.1 MB
[LIVE-DECODE] 22/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+15.4%) | NVMe=460.9 MB/s (71761.77 MB) | RSS=13283.2 MB
[LIVE-DECODE] 24/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+15.8%) | NVMe=459.7 MB/s (74033.34 MB) | RSS=13272.6 MB
[LIVE-DECODE] 26/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+16.1%) | NVMe=458.7 MB/s (76170.52 MB) | RSS=13272.5 MB
[LIVE-DECODE] 28/32 tok | Avg=0.36 tps | Hit=77.6% (LA:+16.4%) | NVMe=457.8 MB/s (78374.77 MB) | RSS=13272.5 MB
[LIVE-DECODE] 30/32 tok | Avg=0.36 tps | Hit=77.6% (LA:+16.7%) | NVMe=456.9 MB/s (80399.84 MB) | RSS=13272.5 MB
[LIVE-DECODE] 32/32 tok | Avg=0.37 tps | Hit=77.6% (LA:+16.8%) | NVMe=456.6 MB/s (82344.15 MB) | RSS=13272.5 MB

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
   LRFU Cache / Staging Ring    : 5371.88 MB (573/12384 exp = 4.63% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13272.52 MB | Peak=13844.00 MB
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
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 129827.96 |  0 |  0 |  0 |     0.0 |
   |    2 |     220 |                |   14.20 |   9.2% |   24923 |   14.18 | 3989.04 | 21 |227 | 88 | 1583072.0 |
   |    3 |      16 | 1              |   18.33 |  26.6% |      19 |   17.27 | 3989.04 |  0 |  0 |  0 | 1583072.0 |
   |    4 |   15245 | -bit           |   13.67 |  13.4% |      13 |   13.56 | 3067.80 | 84 |190 | 62 | 1206208.0 |
   |    5 |    1112 | ...            |   13.59 |   8.9% |    1565 |   13.29 | 3067.80 |  0 |  0 |  0 | 1206208.0 |
   |    6 |    4398 |  More          |   11.74 |   8.2% |     508 |   10.90 | 3227.65 | 77 |196 | 63 | 1263200.0 |
   |    7 |     198 | \n             |   11.62 |   6.7% |     271 |   11.49 | 3227.65 |  0 |  0 |  0 | 1263200.0 |
   |    8 |      58 | [              |   13.68 |   7.4% |     785 |   13.10 | 2472.06 |125 |162 | 49 | 1018144.0 |
   |   18 |      16 | 1              |   14.79 |  37.1% |       8 |   12.48 | 3053.33 | 88 |179 | 69 | 1254880.0 |
   |   19 |   15245 | -bit           |   24.00 |  99.8% |    1455 |   16.07 | 3053.33 |  0 |  0 |  0 | 1254880.0 |
   |   12 |   21265 |  highlights    |   11.86 |  14.3% |    7998 |   11.70 | 2853.89 | 96 |194 | 46 | 1147552.0 |
   |   13 |   88737 | ???\n          |   14.28 |  12.8% |    9335 |   14.26 | 2853.89 |  0 |  0 |  0 | 1147552.0 |
   |   30 |    1506 | ized           |   16.47 |  78.5% |   10267 |   12.96 | 2495.31 |141 |124 | 71 | 1036832.0 |
   |   31 |     220 |                |   19.68 |  90.4% |      16 |   16.01 | 2495.31 |  0 |  0 |  0 | 1036832.0 |
   |   32 |      16 | 1              |   15.37 |  33.8% |      19 |   14.89 | 2328.55 |161 |107 | 68 | 995488.0 |
   |   33 |   15245 | -bit           |   25.55 | 100.0% |    1455 |   16.54 | 2328.55 |  0 |  0 |  0 | 995488.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 129.828s, TTFT=129827.96ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:64t/0.5tps/77%
   Decode  (32 tok, 87.658s): Avg=0.37 | Min=0.25 | Max=0.53 tps
   Latency (ms) : Min=1889.11 | P10=2328.55 | P25=2495.31 | P50=2697.57 | P75=3053.33 | P90=3227.65 | P95=3989.04 | P99=3989.04 | Max=3989.04
   Mean/SD/Jitt : Mean=2739.31ms | StdDev=451.13ms | Jitter=184.95ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=16332 (60.76%) | Lookahead=4528 (+16.85%) | ColdMiss=6020 (22.40%) | EFF HIT=77.60%
   Lookahead    : 4270 prefetched -> 3129 consumed (73.3% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 77.3% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  291 |  98 | 251 | 60.8%|2903.75 | | L24 |  640 |  443 |  75 | 122 | 80.9%|1466.25 |
   | L04 |  640 |  290 | 127 | 223 | 65.2%|2716.88 | | L25 |  640 |  409 |  97 | 134 | 79.1%|1681.88 |
   | L05 |  640 |  267 | 158 | 215 | 66.4%|2623.44 | | L26 |  640 |  435 |  98 | 107 | 83.3%|1423.12 |
   | L06 |  640 |  315 | 141 | 184 | 71.2%|2285.62 | | L27 |  640 |  414 |  97 | 129 | 79.8%|1581.25 |
   | L07 |  640 |  354 | 136 | 150 | 76.6%|1976.56 | | L28 |  640 |  406 | 103 | 131 | 79.5%|1617.19 |
   | L08 |  640 |  333 | 143 | 164 | 74.4%|2034.06 | | L29 |  640 |  385 | 114 | 141 | 78.0%|1753.75 |
   | L09 |  640 |  289 | 164 | 187 | 70.8%|2213.75 | | L30 |  640 |  396 | 103 | 141 | 78.0%|1653.12 |
   | L10 |  640 |  306 | 147 | 187 | 70.8%|2235.31 | | L31 |  640 |  383 | 116 | 141 | 78.0%|1725.00 |
   | L11 |  640 |  394 |  93 | 153 | 76.1%|2437.50 | | L32 |  640 |  361 | 143 | 136 | 78.8%|1775.31 |
   | L12 |  640 |  354 | 138 | 148 | 76.9%|2177.50 | | L33 |  640 |  376 | 133 | 131 | 79.5%|1581.25 |
   | L13 |  640 |  402 |  90 | 148 | 76.9%|1753.75 | | L34 |  640 |  433 |  91 | 116 | 81.9%|1466.25 |
   | L14 |  640 |  427 |  66 | 147 | 77.0%|1667.50 | | L35 |  640 |  374 | 139 | 127 | 80.2%|1595.62 |
   | L15 |  640 |  428 |  71 | 141 | 78.0%|1638.75 | | L36 |  640 |  356 | 152 | 132 | 79.4%|1631.56 |
   | L16 |  640 |  422 |  90 | 128 | 80.0%|1667.50 | | L37 |  640 |  385 | 115 | 140 | 78.1%|1840.00 |
   | L17 |  640 |  430 |  77 | 133 | 79.2%|1624.38 | | L38 |  640 |  405 | 104 | 131 | 79.5%|1610.00 |
   | L18 |  640 |  446 |  72 | 122 | 80.9%|1509.38 | | L39 |  640 |  404 | 108 | 128 | 80.0%|1588.44 |
   | L19 |  640 |  447 |  76 | 117 | 81.7%|1480.62 | | L40 |  640 |  421 |  89 | 130 | 79.7%|1538.12 |
   | L20 |  640 |  429 |  78 | 133 | 79.2%|1588.44 | | L41 |  640 |  408 |  92 | 140 | 78.1%|1674.69 |
   | L21 |  640 |  451 |  73 | 116 | 81.9%|1437.50 | | L42 |  640 |  362 | 157 | 121 | 81.1%|1444.69 |
   | L22 |  640 |  453 |  70 | 117 | 81.7%|1430.31 | | L43 |  640 |  424 | 105 | 111 | 82.7%|1509.38 |
   | L23 |  640 |  422 |  82 | 136 | 78.8%|1602.81 | | L44 |  640 |  402 | 107 | 131 | 79.5%|1951.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 82344.15 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=34906.56 MB)
   SSD Data/Token (Decode)      : Avg=1090.830 MB/tok (Min=786.156 | P50=1068.594 | P95=1545.969 | Max=1545.969 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1386 Batches | 32453 Raw -> 31982 Merged (471 LBA Merges, Avg 2636.5 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=31103
   SSD Read Bandwidth (Active)  : Min=0.32 | Avg=456.57 | Peak=4122.14 MB/s | WallAmort=378.62 MB/s
   OS Kernel I/O Verification   : Read=82353.18 MB | Write=0.00 MB | Syscalls=36018
   Sync Stall vs Async DMA      : SyncStall=90310.30 ms | AsyncOverlapped=165203.24 ms (64.7% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=5.95 GB/s | WallAmort=2.24 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=129.83s (59.7%, 41075.75 MB SSD) | Decode=87.66s (40.3%, 34906.56 MB SSD)
   CPU Time & Utilization       : User=238.641s + Sys=9.750s (Wall=236.996s) | SysUtil=26.2% | ThrUtil=26.2% | 24.24 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  34067.03 ms (354864.9 us/tok | 15.66%)
   MoE AVX2 Q8 Expert Compute   :  46864.71 ms (488174.1 us/tok | 21.55%)
   Router + Lookahead Dispatch  :    686.70 ms ( 7153.1 us/tok |  0.32%)
   LM Head Output Projection    :   1030.11 ms (10730.3 us/tok |  0.47%)
   Foreground NVMe Sync Stall   :  90310.30 ms (940732.3 us/tok | 41.52%)
   Unaccounted / OMP & Sampling :  44527.19 ms (463824.9 us/tok | 20.47%) | Total Wall=217486.03 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    35.63%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    24.84%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    28.75%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.71%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.07%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 239s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 13.55 GB Available
   Active Drive Space : 150.00 GB Total / 54.59 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    454.49 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1469.24 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7917.90 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10565.37 MB/s
   RND4K Q32T16 Read                  :    495.71 MB/s (  126901 IOPS)
   RND4K Q1T1  Read                   :    697.67 MB/s (Latency: 5.60 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     56.13 GB/s
   AVX2 256-bit Sequential Write BW   :     41.82 GB/s
   STREAM Triad (A = B + s*C) BW      :     38.93 GB/s
   Random Pointer-Chase Latency       :     85.77 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.42 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    196.58 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.60 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.50 tps | Avg=0.50 tps | Hit=76.8% | NVMe=480.0 MB/s (51661.71 MB, QD=64) | RSS=13929.9 MB

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
   LRFU Cache / Staging Ring    : 5521.88 MB (589/12384 exp = 4.76% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.83 MB | End=13393.82 MB | Peak=13999.27 MB
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
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 139720.40 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   18.90 |  53.4% |   15724 |   18.74 | 4010.77 | 20 |233 | 83 | 1565280.0 |
   |    3 |     397 | >\n            |   12.80 |   6.2% |     318 |   12.73 | 4010.77 |  0 |  0 |  0 | 1565280.0 |
   |    4 |   13699 | <th            |   14.70 |  18.4% |     334 |   14.61 | 2690.52 |148 |120 | 68 | 1037568.0 |
   |    5 |     766 | ink            |   22.04 |  99.6% |     307 |   14.17 | 2690.52 |  0 |  0 |  0 | 1037568.0 |
   |    6 |     397 | >\n            |   12.54 |  13.7% |      29 |   12.50 | 2779.75 |137 |140 | 59 | 1056160.0 |
   |    7 |   13699 | <th            |   16.29 |  41.2% |     522 |   16.02 | 2779.75 |  0 |  0 |  0 | 1056160.0 |
   |    8 |     397 | >\n            |   17.08 |  39.3% |    1339 |   16.33 | 1970.26 |195 | 96 | 45 | 752064.0 |
   |   36 |   29136 |  Gate          |   15.35 |  36.3% |     479 |   14.86 | 3196.04 | 84 |162 | 90 | 1315072.0 |
   |   37 |    3170 |  why           |   16.44 |  65.8% |   34464 |   13.18 | 3196.04 |  0 |  0 |  0 | 1315072.0 |
   |   20 |    3405 |  question      |   16.21 |  30.6% |     374 |   15.58 | 2854.31 |110 |165 | 61 | 1164032.0 |
   |   21 |     374 |  is            |   15.85 |  19.4% |   15504 |   14.87 | 2854.31 |  0 |  0 |  0 | 1164032.0 |
   |   62 |   24384 |  NV            |   15.58 |  36.6% |   50665 |   15.35 | 2336.31 |147 |130 | 59 | 996928.0 |
   |   63 |   50665 |  sequential    |   14.36 |  20.5% |   25372 |   14.09 | 2336.31 |  0 |  0 |  0 | 996928.0 |
   |   64 |   24384 |  NV            |   17.08 |  41.8% |   25372 |   17.00 | 2254.36 |165 |111 | 60 | 939264.0 |
   |   65 |   25372 |  DMA           |   17.65 |  62.3% |   81911 |   16.44 | 2254.36 |  0 |  0 |  0 | 939264.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 139.720s, TTFT=139720.40ms): Avg=0.50 | Min=0.50 | Max=0.50 tps
   Prefill Chunks (1): C1:70t/0.5tps/77%
   Decode  (64 tok, 166.574s): Avg=0.38 | Min=0.25 | Max=0.53 tps
   Latency (ms) : Min=1890.51 | P10=2027.10 | P25=2515.37 | P50=2641.09 | P75=2694.12 | P90=2819.34 | P95=3196.04 | P99=4010.77 | Max=4010.77
   Mean/SD/Jitt : Mean=2602.72ms | StdDev=375.05ms | Jitter=119.14ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=20241 (59.06%) | Lookahead=6547 (+19.10%) | ColdMiss=7484 (21.84%) | EFF HIT=78.16%
   Lookahead    : 7717 prefetched -> 5083 consumed (65.9% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 77.4% | @64= 78.2% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  347 | 149 | 320 | 60.8%|4348.44 | | L24 |  816 |  477 | 196 | 143 | 82.5%|2084.38 |
   | L04 |  816 |  335 | 187 | 294 | 64.0%|4010.62 | | L25 |  816 |  544 | 121 | 151 | 81.5%|2264.06 |
   | L05 |  816 |  341 | 215 | 260 | 68.1%|3687.19 | | L26 |  816 |  508 | 157 | 151 | 81.5%|2048.44 |
   | L06 |  816 |  370 | 220 | 226 | 72.3%|3435.62 | | L27 |  816 |  527 | 113 | 176 | 78.4%|2522.81 |
   | L07 |  816 |  419 | 205 | 192 | 76.5%|2918.12 | | L28 |  816 |  464 | 168 | 184 | 77.5%|2680.94 |
   | L08 |  816 |  398 | 196 | 222 | 72.8%|3320.62 | | L29 |  816 |  499 | 156 | 161 | 80.3%|2314.38 |
   | L09 |  816 |  399 | 185 | 232 | 71.6%|3234.38 | | L30 |  816 |  471 | 168 | 177 | 78.3%|2494.06 |
   | L10 |  816 |  365 | 231 | 220 | 73.0%|3234.38 | | L31 |  816 |  499 | 137 | 180 | 77.9%|2609.06 |
   | L11 |  816 |  458 | 164 | 194 | 76.2%|3618.75 | | L32 |  816 |  497 | 140 | 179 | 78.1%|2688.12 |
   | L12 |  816 |  477 | 162 | 177 | 78.3%|3199.25 | | L33 |  816 |  514 | 143 | 159 | 80.5%|2443.75 |
   | L13 |  816 |  522 | 113 | 181 | 77.8%|2508.44 | | L34 |  816 |  518 | 144 | 154 | 81.1%|2400.62 |
   | L14 |  816 |  473 | 153 | 190 | 76.7%|2839.06 | | L35 |  816 |  508 | 159 | 149 | 81.7%|2343.12 |
   | L15 |  816 |  516 | 123 | 177 | 78.3%|2515.62 | | L36 |  816 |  500 | 167 | 149 | 81.7%|2379.06 |
   | L16 |  816 |  458 | 173 | 185 | 77.3%|2637.81 | | L37 |  816 |  481 | 179 | 156 | 80.9%|2364.69 |
   | L17 |  816 |  463 | 175 | 178 | 78.2%|2666.56 | | L38 |  816 |  548 | 125 | 143 | 82.5%|2141.88 |
   | L18 |  816 |  567 |  96 | 153 | 81.2%|1983.75 | | L39 |  816 |  513 | 156 | 147 | 82.0%|2264.06 |
   | L19 |  816 |  547 | 112 | 157 | 80.8%|2098.75 | | L40 |  816 |  485 | 167 | 164 | 79.9%|2515.62 |
   | L20 |  816 |  590 |  91 | 135 | 83.5%|1897.50 | | L41 |  816 |  466 | 188 | 162 | 80.1%|2515.62 |
   | L21 |  816 |  565 | 100 | 151 | 81.5%|2134.69 | | L42 |  816 |  517 | 149 | 150 | 81.6%|2256.88 |
   | L22 |  816 |  549 | 129 | 138 | 83.1%|1976.56 | | L43 |  816 |  522 | 149 | 145 | 82.2%|2105.94 |
   | L23 |  816 |  550 | 116 | 150 | 81.6%|2070.00 | | L44 |  816 |  474 | 170 | 172 | 78.9%|3241.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 118497.27 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=66835.56 MB)
   SSD Data/Token (Decode)      : Avg=1044.306 MB/tok (Min=734.438 | P50=1072.312 | P95=1284.250 | Max=1528.594 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2669 Batches | 47273 Raw -> 46653 Merged (620 LBA Merges, Avg 2600.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=45774
   SSD Read Bandwidth (Active)  : Min=0.30 | Avg=447.64 | Peak=3876.13 MB/s | WallAmort=386.87 MB/s (100.0% of 454.5 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=119484.31 MB | Write=128.00 MB | Syscalls=58227
   Sync Stall vs Async DMA      : SyncStall=116383.99 ms | AsyncOverlapped=249811.52 ms (68.2% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=7.35 GB/s (18.9% STREAM) | WallAmort=2.54 GB/s (Max=38.93 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=139.72s (45.6%, 45299.88 MB SSD) | Decode=166.57s (54.4%, 66835.56 MB SSD)
   CPU Time & Utilization       : User=314.516s + Sys=12.109s (Wall=326.048s) | SysUtil=25.0% | ThrUtil=25.0% | 49.23 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  41063.26 ms (306442.2 us/tok | 13.41%)
   MoE AVX2 Q8 Expert Compute   :  62929.67 ms (469624.4 us/tok | 20.55%)
   Router + Lookahead Dispatch  :    842.00 ms ( 6283.6 us/tok |  0.27%)
   LM Head Output Projection    :   1690.05 ms (12612.3 us/tok |  0.55%)
   Foreground NVMe Sync Stall   : 116383.99 ms (868537.2 us/tok | 38.00%)
   Unaccounted / OMP & Sampling :  83385.75 ms (622281.7 us/tok | 27.22%) | Total Wall=306294.71 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    33.04%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    27.47%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.69%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.24%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.56%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5606.25 MB (598 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.83 tps | Avg=0.83 tps | Hit=90.6% | NVMe=504.3 MB/s (74277.59 MB, QD=64) | RSS=14093.6 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.82 tps | Avg=0.83 tps | Hit=90.4% | NVMe=510.2 MB/s (145295.52 MB, QD=64) | RSS=14093.8 MB
[LIVE-DECODE] 2/128 tok | Avg=0.22 tps | Hit=90.4% (LA:+10.6%) | NVMe=507.6 MB/s (148736.77 MB) | RSS=14007.1 MB
[LIVE-DECODE] 4/128 tok | Avg=0.24 tps | Hit=90.3% (LA:+10.7%) | NVMe=504.7 MB/s (151480.96 MB) | RSS=13835.1 MB
[LIVE-DECODE] 6/128 tok | Avg=0.26 tps | Hit=90.3% (LA:+10.7%) | NVMe=502.4 MB/s (153889.77 MB) | RSS=13680.2 MB
[LIVE-DECODE] 8/128 tok | Avg=0.28 tps | Hit=90.3% (LA:+10.8%) | NVMe=501.0 MB/s (156170.65 MB) | RSS=13614.0 MB
[LIVE-DECODE] 10/128 tok | Avg=0.29 tps | Hit=90.3% (LA:+10.8%) | NVMe=499.9 MB/s (158190.65 MB) | RSS=13562.2 MB
[LIVE-DECODE] 12/128 tok | Avg=0.30 tps | Hit=90.2% (LA:+10.9%) | NVMe=498.7 MB/s (160325.34 MB) | RSS=13530.8 MB
[LIVE-DECODE] 14/128 tok | Avg=0.31 tps | Hit=90.2% (LA:+10.9%) | NVMe=497.5 MB/s (162419.46 MB) | RSS=13504.6 MB
[LIVE-DECODE] 16/128 tok | Avg=0.32 tps | Hit=90.2% (LA:+11.0%) | NVMe=496.5 MB/s (164537.59 MB) | RSS=13497.8 MB
[LIVE-DECODE] 18/128 tok | Avg=0.33 tps | Hit=90.2% (LA:+11.0%) | NVMe=495.4 MB/s (166678.84 MB) | RSS=13497.8 MB
[LIVE-DECODE] 20/128 tok | Avg=0.33 tps | Hit=90.1% (LA:+11.1%) | NVMe=494.5 MB/s (168777.27 MB) | RSS=13497.7 MB
[LIVE-DECODE] 22/128 tok | Avg=0.33 tps | Hit=90.1% (LA:+11.1%) | NVMe=493.4 MB/s (171002.34 MB) | RSS=13497.6 MB
[LIVE-DECODE] 24/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.2%) | NVMe=492.2 MB/s (173275.09 MB) | RSS=13497.6 MB
[LIVE-DECODE] 26/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.2%) | NVMe=491.2 MB/s (175474.52 MB) | RSS=13497.6 MB
[LIVE-DECODE] 28/128 tok | Avg=0.34 tps | Hit=90.0% (LA:+11.3%) | NVMe=490.3 MB/s (177539.65 MB) | RSS=13497.5 MB
[LIVE-DECODE] 30/128 tok | Avg=0.35 tps | Hit=90.0% (LA:+11.3%) | NVMe=489.7 MB/s (179410.09 MB) | RSS=13497.5 MB
[LIVE-DECODE] 32/128 tok | Avg=0.35 tps | Hit=90.0% (LA:+11.3%) | NVMe=489.3 MB/s (181160.52 MB) | RSS=13497.5 MB
[LIVE-DECODE] 34/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.4%) | NVMe=488.5 MB/s (183219.27 MB) | RSS=13497.5 MB
[LIVE-DECODE] 36/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.4%) | NVMe=487.6 MB/s (185402.96 MB) | RSS=13497.5 MB
[LIVE-DECODE] 38/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.5%) | NVMe=486.7 MB/s (187619.52 MB) | RSS=13497.6 MB
[LIVE-DECODE] 40/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.5%) | NVMe=486.0 MB/s (189600.34 MB) | RSS=13488.2 MB
[LIVE-DECODE] 42/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.5%) | NVMe=485.2 MB/s (191721.40 MB) | RSS=13488.2 MB
[LIVE-DECODE] 44/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.6%) | NVMe=484.2 MB/s (194119.34 MB) | RSS=13488.2 MB
[LIVE-DECODE] 46/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.7%) | NVMe=483.3 MB/s (196408.15 MB) | RSS=13488.2 MB
[LIVE-DECODE] 48/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.7%) | NVMe=482.6 MB/s (198518.71 MB) | RSS=13497.6 MB
[LIVE-DECODE] 50/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=481.8 MB/s (200712.84 MB) | RSS=13497.6 MB
[LIVE-DECODE] 52/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=481.2 MB/s (202668.52 MB) | RSS=13497.6 MB
[LIVE-DECODE] 54/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=480.8 MB/s (204536.71 MB) | RSS=13497.6 MB
[LIVE-DECODE] 56/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.9%) | NVMe=479.9 MB/s (206972.52 MB) | RSS=13497.6 MB
[LIVE-DECODE] 58/128 tok | Avg=0.36 tps | Hit=89.7% (LA:+12.0%) | NVMe=479.2 MB/s (209217.15 MB) | RSS=13497.6 MB
[LIVE-DECODE] 60/128 tok | Avg=0.36 tps | Hit=89.7% (LA:+12.0%) | NVMe=478.7 MB/s (211126.15 MB) | RSS=13497.6 MB
[LIVE-DECODE] 62/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.0%) | NVMe=478.1 MB/s (213078.96 MB) | RSS=13497.6 MB
[LIVE-DECODE] 64/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.1%) | NVMe=477.7 MB/s (214950.02 MB) | RSS=13497.6 MB
[LIVE-DECODE] 66/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.2%) | NVMe=477.1 MB/s (217120.71 MB) | RSS=13497.6 MB
[LIVE-DECODE] 68/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.2%) | NVMe=476.8 MB/s (219203.59 MB) | RSS=13507.0 MB
[LIVE-DECODE] 70/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.2%) | NVMe=476.3 MB/s (221131.84 MB) | RSS=13507.0 MB
[LIVE-DECODE] 72/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=475.8 MB/s (223088.84 MB) | RSS=13506.9 MB
[LIVE-DECODE] 74/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=475.3 MB/s (225066.52 MB) | RSS=13507.0 MB
[LIVE-DECODE] 76/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=474.8 MB/s (227095.21 MB) | RSS=13507.0 MB
[LIVE-DECODE] 78/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.4%) | NVMe=474.2 MB/s (229112.59 MB) | RSS=13488.2 MB
[LIVE-DECODE] 80/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.4%) | NVMe=473.9 MB/s (230932.09 MB) | RSS=13488.2 MB
[LIVE-DECODE] 82/128 tok | Avg=0.38 tps | Hit=89.6% (LA:+12.4%) | NVMe=473.6 MB/s (232589.15 MB) | RSS=13488.2 MB
[LIVE-DECODE] 84/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.4%) | NVMe=473.3 MB/s (234322.84 MB) | RSS=13488.2 MB
[LIVE-DECODE] 86/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=473.0 MB/s (236051.15 MB) | RSS=13488.2 MB
[LIVE-DECODE] 88/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.6 MB/s (237968.84 MB) | RSS=13488.2 MB
[LIVE-DECODE] 90/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.2 MB/s (239879.02 MB) | RSS=13488.2 MB
[LIVE-DECODE] 92/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.0 MB/s (241875.09 MB) | RSS=13497.6 MB
[LIVE-DECODE] 94/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.6%) | NVMe=471.6 MB/s (243864.34 MB) | RSS=13497.6 MB
[LIVE-DECODE] 96/128 tok | Avg=0.38 tps | Hit=89.4% (LA:+12.6%) | NVMe=471.3 MB/s (245669.15 MB) | RSS=13497.6 MB
[LIVE-DECODE] 98/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=470.9 MB/s (247630.59 MB) | RSS=13497.6 MB
[LIVE-DECODE] 100/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=470.7 MB/s (249443.46 MB) | RSS=13491.6 MB
[LIVE-DECODE] 102/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=470.3 MB/s (251289.21 MB) | RSS=13478.8 MB
[LIVE-DECODE] 104/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=469.9 MB/s (253249.52 MB) | RSS=13478.8 MB
[LIVE-DECODE] 106/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=469.7 MB/s (255233.15 MB) | RSS=13488.2 MB
[LIVE-DECODE] 108/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=469.3 MB/s (257254.21 MB) | RSS=13488.2 MB
[LIVE-DECODE] 110/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.9 MB/s (259203.65 MB) | RSS=13488.2 MB
[LIVE-DECODE] 112/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.6 MB/s (261099.90 MB) | RSS=13488.2 MB
[LIVE-DECODE] 114/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=468.3 MB/s (263146.46 MB) | RSS=13488.2 MB
[LIVE-DECODE] 116/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=468.0 MB/s (264962.59 MB) | RSS=13488.2 MB
[LIVE-DECODE] 118/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=467.7 MB/s (266796.96 MB) | RSS=13488.2 MB
[LIVE-DECODE] 120/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+12.9%) | NVMe=467.4 MB/s (268768.84 MB) | RSS=13488.2 MB
[LIVE-DECODE] 122/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=467.1 MB/s (270828.84 MB) | RSS=13488.2 MB
[LIVE-DECODE] 124/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.8 MB/s (272657.90 MB) | RSS=13488.2 MB
[LIVE-DECODE] 126/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.5 MB/s (274385.59 MB) | RSS=13488.2 MB
[LIVE-DECODE] 128/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.4 MB/s (276203.84 MB) | RSS=13488.2 MB

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
   LRFU Cache / Staging Ring    : 5606.25 MB (598/12384 exp = 4.83% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.79 MB | End=13488.16 MB | Peak=14184.51 MB
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
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 619707.82 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   24.96 | 100.0% |    1062 |   16.43 | 4516.12 | 35 |173 |128 | 1761920.0 |
   |    3 |   39929 |  LB            |   17.75 |  78.0% |   33903 |   16.24 | 4516.12 |  0 |  0 |  0 | 1761920.0 |
   |    4 |      32 | A              |   14.08 |  30.6% |    1911 |   13.59 | 3691.18 | 71 |173 | 92 | 1405024.0 |
   |    5 |   46254 | -sort          |   18.02 |  42.5% |    1331 |   17.61 | 3691.18 |  0 |  0 |  0 | 1405024.0 |
   |    6 |     287 | ing            |   14.36 |  38.6% |   11492 |   11.93 | 3182.19 |111 |152 | 73 | 1233312.0 |
   |    7 |   11492 |  coal          |   16.09 |  54.1% |    1207 |   14.51 | 3182.19 |  0 |  0 |  0 | 1233312.0 |
   |    8 |    3300 | esc            |   18.05 |  93.7% |     642 |   13.98 | 3006.86 |123 |138 | 75 | 1167808.0 |
   |   56 |  154842 | </think>       |   14.32 |  56.1% |     641 |   13.02 | 3066.43 | 90 |167 | 79 | 1247136.0 |
   |   57 |     641 | In             |   15.30 |  41.7% |     565 |   13.90 | 3066.43 |  0 |  0 |  0 | 1247136.0 |
   |    9 |     291 | ed             |   20.63 |  75.1% |     287 |   19.27 | 3006.86 |  0 |  0 |  0 | 1167808.0 |
   |   44 |    3170 |  why           |   17.45 |  85.5% |     419 |   13.32 | 2990.48 |114 |136 | 86 | 1227744.0 |
   |  126 |     291 | ed             |   14.96 |  32.3% |    1207 |   14.08 | 2137.12 |190 | 85 | 61 | 884576.0 |
   |  127 |    9421 | -block         |   17.23 |  54.2% |    7299 |   15.51 | 2137.12 |  0 |  0 |  0 | 884576.0 |
   |  128 |    9421 | -block         |   14.61 |  29.9% |    1207 |   13.52 | 2146.75 |189 | 94 | 53 | 930944.0 |
   |  129 |     291 | ed             |   20.50 |  98.5% |   29819 |   14.11 | 2146.75 |  0 |  0 |  0 | 930944.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 619.708s, TTFT=619707.82ms): Avg=0.83 | Min=0.82 | Max=0.83 tps
   Prefill Chunks (2): C1:256t/0.8tps/91% | C2:256t/0.8tps/90%
   Decode  (128 tok, 324.324s): Avg=0.39 | Min=0.22 | Max=0.49 tps
   Latency (ms) : Min=2042.43 | P10=2156.46 | P25=2314.79 | P50=2471.21 | P75=2683.51 | P90=2840.40 | P95=3066.43 | P99=4516.12 | Max=4516.12
   Mean/SD/Jitt : Mean=2533.78ms | StdDev=380.77ms | Jitter=91.10ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=147361 (76.14%) | Lookahead=25256 (+13.05%) | ColdMiss=20919 (10.81%) | EFF HIT=89.19%
   Lookahead    : 15757 prefetched -> 9727 consumed (61.7% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.2% | @64= 89.7% | @128= 89.2% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3154 | 741 | 713 | 84.5%|9228.75 | | L24 | 4608 | 3590 | 559 | 459 | 90.0%|5426.56 |
   | L04 | 4608 | 3238 | 676 | 694 | 84.9%|8826.25 | | L25 | 4608 | 3654 | 484 | 470 | 89.8%|6087.81 |
   | L05 | 4608 | 3184 | 797 | 627 | 86.4%|8244.06 | | L26 | 4608 | 3657 | 509 | 442 | 90.4%|5455.31 |
   | L06 | 4608 | 3253 | 787 | 568 | 87.7%|7755.31 | | L27 | 4608 | 3534 | 530 | 544 | 88.2%|7086.88 |
   | L07 | 4608 | 3369 | 755 | 484 | 89.5%|6504.69 | | L28 | 4608 | 3516 | 589 | 503 | 89.1%|6130.94 |
   | L08 | 4608 | 3455 | 629 | 524 | 88.6%|6907.19 | | L29 | 4608 | 3425 | 704 | 479 | 89.6%|6066.25 |
   | L09 | 4608 | 3308 | 724 | 576 | 87.5%|7065.31 | | L30 | 4608 | 3519 | 610 | 479 | 89.6%|5750.00 |
   | L10 | 4608 | 3264 | 757 | 587 | 87.3%|7424.69 | | L31 | 4608 | 3371 | 644 | 593 | 87.1%|7288.12 |
   | L11 | 4608 | 3486 | 596 | 526 | 88.6%|8568.75 | | L32 | 4608 | 3289 | 759 | 560 | 87.8%|6792.19 |
   | L12 | 4608 | 3449 | 665 | 494 | 89.3%|7152.25 | | L33 | 4608 | 3375 | 736 | 497 | 89.2%|6619.69 |
   | L13 | 4608 | 3596 | 543 | 469 | 89.8%|5764.38 | | L34 | 4608 | 3661 | 507 | 440 | 90.5%|5742.81 |
   | L14 | 4608 | 3625 | 487 | 496 | 89.2%|6210.00 | | L35 | 4608 | 3465 | 668 | 475 | 89.7%|6066.25 |
   | L15 | 4608 | 3618 | 500 | 490 | 89.4%|6008.75 | | L36 | 4608 | 3313 | 830 | 465 | 89.9%|6145.31 |
   | L16 | 4608 | 3638 | 498 | 472 | 89.8%|5994.38 | | L37 | 4608 | 3609 | 534 | 465 | 89.9%|5750.00 |
   | L17 | 4608 | 3739 | 394 | 475 | 89.7%|5771.56 | | L38 | 4608 | 3601 | 539 | 468 | 89.8%|5972.81 |
   | L18 | 4608 | 3814 | 345 | 449 | 90.3%|5498.44 | | L39 | 4608 | 3586 | 538 | 484 | 89.5%|5764.38 |
   | L19 | 4608 | 3742 | 455 | 411 | 91.1%|5124.69 | | L40 | 4608 | 3623 | 525 | 460 | 90.0%|5656.56 |
   | L20 | 4608 | 3636 | 535 | 437 | 90.5%|5354.69 | | L41 | 4608 | 3518 | 623 | 467 | 89.9%|6087.81 |
   | L21 | 4608 | 3727 | 438 | 443 | 90.4%|5383.44 | | L42 | 4608 | 3387 | 766 | 455 | 90.1%|5469.69 |
   | L22 | 4608 | 3689 | 496 | 423 | 90.8%|5232.50 | | L43 | 4608 | 3575 | 614 | 419 | 90.9%|5354.69 |
   | L23 | 4608 | 3589 | 585 | 434 | 90.6%|5282.81 | | L44 | 4608 | 3520 | 585 | 503 | 89.1%|7696.62 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 276203.84 MB (Load=6361.84 | Prefill=138933.69 | Warmup=0.00 | Decode=130908.31 MB)
   SSD Data/Token (Decode)      : Avg=1022.721 MB/tok (Min=828.531 | P50=998.031 | P95=1204.406 | Max=1720.625 MB) | Prefill=271.355 MB/tok
   NVMe Batches / Requests      : 5639 Batches | 112046 Raw -> 110485 Merged (1561 LBA Merges, Avg 2559.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=109606
   SSD Read Bandwidth (Active)  : Min=0.46 | Avg=466.38 | Peak=4145.40 MB/s | WallAmort=292.58 MB/s
   OS Kernel I/O Verification   : Read=276212.87 MB | Write=0.01 MB | Syscalls=114570
   Sync Stall vs Async DMA      : SyncStall=300755.51 ms | AsyncOverlapped=577350.17 ms (65.7% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=5.72 GB/s | WallAmort=2.95 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=619.71s (65.6%, 138933.69 MB SSD) | Decode=324.32s (34.4%, 130908.31 MB SSD)
   CPU Time & Utilization       : User=1623.750s + Sys=28.141s (Wall=963.487s) | SysUtil=42.9% | ThrUtil=42.9% | 39.65 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 213954.51 ms (334303.9 us/tok | 22.66%)
   MoE AVX2 Q8 Expert Compute   : 268963.97 ms (420256.2 us/tok | 28.49%)
   Router + Lookahead Dispatch  :   4316.26 ms ( 6744.2 us/tok |  0.46%)
   LM Head Output Projection    :   3388.67 ms ( 5294.8 us/tok |  0.36%)
   Foreground NVMe Sync Stall   : 300755.51 ms (469930.5 us/tok | 31.86%)
   Unaccounted / OMP & Sampling : 152652.84 ms (238520.1 us/tok | 16.17%) | Total Wall=944031.75 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    54.88%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    17.50%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    16.55%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     9.01%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.06%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 138347.3ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='\nSummarize LBACoalesce in one sentence.\nSummarize LB'
[Stage 3] /v1/chat/completions (stream=true SSE) 56553.2ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5437.50 MB (580 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=0.84 tps | Avg=0.84 tps | Hit=90.6% | NVMe=505.1 MB/s (74277.59 MB, QD=64) | RSS=13925.4 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=0.82 tps | Avg=0.83 tps | Hit=90.4% | NVMe=511.1 MB/s (145295.52 MB, QD=64) | RSS=13924.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=0.82 tps | Avg=0.83 tps | Hit=90.4% | NVMe=513.1 MB/s (214799.34 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=0.76 tps | Avg=0.81 tps | Hit=90.4% | NVMe=514.8 MB/s (283922.65 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=0.82 tps | Avg=0.81 tps | Hit=90.5% | NVMe=516.4 MB/s (352711.65 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=0.81 tps | Avg=0.81 tps | Hit=90.5% | NVMe=518.1 MB/s (420869.27 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=0.81 tps | Avg=0.81 tps | Hit=90.5% | NVMe=518.5 MB/s (488245.34 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=0.82 tps | Avg=0.81 tps | Hit=90.6% | NVMe=519.5 MB/s (554073.90 MB, QD=64) | RSS=13925.7 MB
[LIVE-DECODE] 2/64 tok | Avg=0.33 tps | Hit=90.6% (LA:+10.0%) | NVMe=519.0 MB/s (556515.84 MB) | RSS=13927.3 MB
[LIVE-DECODE] 4/64 tok | Avg=0.28 tps | Hit=90.6% (LA:+10.1%) | NVMe=518.1 MB/s (559451.09 MB) | RSS=13724.1 MB
[LIVE-DECODE] 6/64 tok | Avg=0.29 tps | Hit=90.5% (LA:+10.1%) | NVMe=517.5 MB/s (561876.02 MB) | RSS=13611.9 MB
[LIVE-DECODE] 8/64 tok | Avg=0.30 tps | Hit=90.5% (LA:+10.1%) | NVMe=516.8 MB/s (564281.71 MB) | RSS=13528.3 MB
[LIVE-DECODE] 10/64 tok | Avg=0.31 tps | Hit=90.5% (LA:+10.1%) | NVMe=516.3 MB/s (566481.52 MB) | RSS=13457.6 MB
[LIVE-DECODE] 12/64 tok | Avg=0.31 tps | Hit=90.5% (LA:+10.1%) | NVMe=515.8 MB/s (568721.90 MB) | RSS=13407.2 MB
[LIVE-DECODE] 14/64 tok | Avg=0.32 tps | Hit=90.5% (LA:+10.1%) | NVMe=515.3 MB/s (570885.27 MB) | RSS=13371.5 MB
[LIVE-DECODE] 16/64 tok | Avg=0.32 tps | Hit=90.5% (LA:+10.1%) | NVMe=514.9 MB/s (573146.27 MB) | RSS=13348.4 MB
[LIVE-DECODE] 18/64 tok | Avg=0.33 tps | Hit=90.5% (LA:+10.2%) | NVMe=514.5 MB/s (575463.46 MB) | RSS=13338.9 MB
[LIVE-DECODE] 20/64 tok | Avg=0.33 tps | Hit=90.5% (LA:+10.2%) | NVMe=514.1 MB/s (577730.59 MB) | RSS=13338.9 MB
[LIVE-DECODE] 22/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=513.8 MB/s (579842.52 MB) | RSS=13339.0 MB
[LIVE-DECODE] 24/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=513.4 MB/s (582107.34 MB) | RSS=13339.0 MB
[LIVE-DECODE] 26/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=512.9 MB/s (584416.27 MB) | RSS=13339.0 MB
[LIVE-DECODE] 28/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=512.6 MB/s (586716.15 MB) | RSS=13338.9 MB
[LIVE-DECODE] 30/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=512.2 MB/s (588846.90 MB) | RSS=13338.9 MB
[LIVE-DECODE] 32/64 tok | Avg=0.35 tps | Hit=90.5% (LA:+10.2%) | NVMe=511.8 MB/s (590979.15 MB) | RSS=13338.9 MB
[LIVE-DECODE] 34/64 tok | Avg=0.35 tps | Hit=90.5% (LA:+10.3%) | NVMe=511.5 MB/s (592939.77 MB) | RSS=13338.9 MB
[LIVE-DECODE] 36/64 tok | Avg=0.35 tps | Hit=90.5% (LA:+10.3%) | NVMe=511.2 MB/s (595126.65 MB) | RSS=13338.9 MB
[LIVE-DECODE] 38/64 tok | Avg=0.35 tps | Hit=90.5% (LA:+10.3%) | NVMe=510.9 MB/s (597077.15 MB) | RSS=13338.9 MB
[LIVE-DECODE] 40/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=510.6 MB/s (599033.21 MB) | RSS=13338.9 MB
[LIVE-DECODE] 42/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=510.3 MB/s (601050.59 MB) | RSS=13323.8 MB
[LIVE-DECODE] 44/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=510.1 MB/s (602953.52 MB) | RSS=13329.6 MB
[LIVE-DECODE] 46/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=509.8 MB/s (604945.96 MB) | RSS=13329.5 MB
[LIVE-DECODE] 48/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=509.4 MB/s (607197.40 MB) | RSS=13338.9 MB
[LIVE-DECODE] 50/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=509.2 MB/s (609246.02 MB) | RSS=13338.9 MB
[LIVE-DECODE] 52/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.4%) | NVMe=508.8 MB/s (611688.52 MB) | RSS=13339.0 MB
[LIVE-DECODE] 54/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.4%) | NVMe=508.5 MB/s (613804.15 MB) | RSS=13338.9 MB
[LIVE-DECODE] 56/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=508.2 MB/s (615731.02 MB) | RSS=13338.9 MB
[LIVE-DECODE] 58/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=507.9 MB/s (617751.59 MB) | RSS=13338.9 MB
[LIVE-DECODE] 60/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=507.6 MB/s (619804.09 MB) | RSS=13326.1 MB
[LIVE-DECODE] 62/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=507.3 MB/s (621916.21 MB) | RSS=13326.1 MB
[LIVE-DECODE] 64/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=507.0 MB/s (623873.90 MB) | RSS=13326.1 MB

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
   LRFU Cache / Staging Ring    : 5437.50 MB (580/12384 exp = 4.68% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.77 MB | End=13326.07 MB | Peak=14016.58 MB
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
   |    1 |    1550 |  high          |   25.48 | 100.0% |     279 |   13.45 | 2525827.05 |  0 |  0 |  0 |     0.0 |
   |    2 |   42503 | -through       |   27.04 | 100.0% |   63308 |   16.24 | 3074.62 |130 |110 | 96 | 1250272.0 |
   |    3 |     628 | put            |   23.73 |  99.6% |   19183 |   17.58 | 3074.62 |  0 |  0 |  0 | 1250272.0 |
   |    4 |   19183 |  Mix           |   17.39 |  84.5% |   19705 |   14.33 | 4061.76 | 39 |215 | 82 | 1502848.0 |
   |    5 |   18482 | tures          |   16.37 |  54.3% |      68 |   15.04 | 4061.76 |  0 |  0 |  0 | 1502848.0 |
   |    6 |     315 |  of            |   13.92 |  18.4% |    8667 |   13.83 | 3143.48 |107 |148 | 81 | 1241568.0 |
   |    7 |   19183 |  Mix           |   18.45 |  89.7% |   57687 |   15.44 | 3143.48 |  0 |  0 |  0 | 1241568.0 |
   |    8 |   18482 | tures          |   16.65 |  62.5% |    4974 |   14.96 | 3100.41 |119 |137 | 80 | 1231712.0 |
   |    9 |    8667 | -of            |   17.27 |  47.5% |     315 |   17.04 | 3100.41 |  0 |  0 |  0 | 1231712.0 |
   |   52 |   18547 |  dual          |   14.99 |  20.4% |   86025 |   14.43 | 2999.66 |106 |150 | 80 | 1250560.0 |
   |   53 |   86025 |  lookahead     |   13.07 |   7.8% |    9270 |   12.69 | 2999.66 |  0 |  0 |  0 | 1250560.0 |
   |   16 |    4128 |  language      |   16.00 |  39.8% |   81623 |   15.32 | 2906.31 |133 |135 | 68 | 1157632.0 |
   |   62 |   21984 |  RAM           |   16.11 |  41.3% |   33742 |   15.25 | 2586.77 |142 |117 | 77 | 1081408.0 |
   |   63 |    2041 |  without       |   15.58 |  48.8% |   28891 |   13.67 | 2586.77 |  0 |  0 |  0 | 1081408.0 |
   |   64 |   13931 |  CPU           |   16.17 |  32.7% |   11315 |   14.94 | 2417.90 |141 |143 | 52 | 1002336.0 |
   |   65 |   11315 |  execution     |   14.77 |  16.3% |   15289 |   14.61 | 2417.90 |  0 |  0 |  0 | 1002336.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2525.827s, TTFT=2525827.05ms): Avg=0.81 | Min=0.76 | Max=0.84 tps
   Prefill Chunks (8): C1:256t/0.8tps/91% | C2:256t/0.8tps/90% | C3:256t/0.8tps/90% | C4:256t/0.8tps/90%
                       C5:256t/0.8tps/90% | C6:256t/0.8tps/90% | C7:256t/0.8tps/91% | C8:256t/0.8tps/91%
   Decode  (64 tok, 173.000s): Avg=0.37 | Min=0.25 | Max=0.43 tps
   Latency (ms) : Min=2303.94 | P10=2364.77 | P25=2469.35 | P50=2660.03 | P75=2826.64 | P90=3074.62 | P95=3143.48 | P99=4061.76 | Max=4061.76
   Mean/SD/Jitt : Mean=2703.13ms | StdDev=336.29ms | Jitter=110.87ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (698880): RawRAM=558754 (79.95%) | Lookahead=72975 (+10.44%) | ColdMiss=67151 (9.61%) | EFF HIT=90.39%
   Lookahead    : 17281 prefetched -> 14258 consumed (82.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.5% | @64= 90.4% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |16640 |12360 |2282 |1998 | 88.0%|18723.44 | | L24 |16640 |13262 |1869 |1509 | 90.9%|13419.06 |
   | L04 |16640 |12490 |2193 |1957 | 88.2%|18033.44 | | L25 |16640 |13525 |1616 |1499 | 91.0%|13735.31 |
   | L05 |16640 |12598 |2103 |1939 | 88.3%|17882.50 | | L26 |16640 |13417 |1703 |1520 | 90.9%|13605.94 |
   | L06 |16640 |12668 |2071 |1901 | 88.6%|17710.00 | | L27 |16640 |13394 |1640 |1606 | 90.3%|14633.75 |
   | L07 |16640 |12979 |1926 |1735 | 89.6%|15755.00 | | L28 |16640 |13263 |1772 |1605 | 90.4%|14439.69 |
   | L08 |16640 |13223 |1627 |1790 | 89.2%|16143.12 | | L29 |16640 |13165 |1969 |1506 | 90.9%|13685.00 |
   | L09 |16640 |12982 |1874 |1784 | 89.3%|16121.56 | | L30 |16640 |13053 |1994 |1593 | 90.4%|14224.06 |
   | L10 |16640 |12738 |2046 |1856 | 88.8%|16905.00 | | L31 |16640 |13512 |1518 |1610 | 90.3%|14583.44 |
   | L11 |16640 |13148 |1915 |1577 | 90.5%|19031.25 | | L32 |16640 |13026 |1988 |1626 | 90.2%|14727.19 |
   | L12 |16640 |13202 |1886 |1552 | 90.7%|16582.50 | | L33 |16640 |13444 |1736 |1460 | 91.2%|13591.56 |
   | L13 |16640 |13535 |1667 |1438 | 91.4%|12908.75 | | L34 |16640 |13616 |1501 |1523 | 90.8%|13720.94 |
   | L14 |16640 |14198 |1091 |1351 | 91.9%|12276.25 | | L35 |16640 |13671 |1391 |1578 | 90.5%|14245.62 |
   | L15 |16640 |14341 |1049 |1250 | 92.5%|11500.00 | | L36 |16640 |13309 |1719 |1612 | 90.3%|14461.25 |
   | L16 |16640 |13860 |1376 |1404 | 91.6%|12700.31 | | L37 |16640 |13515 |1517 |1608 | 90.3%|14195.31 |
   | L17 |16640 |13570 |1526 |1544 | 90.7%|13792.81 | | L38 |16640 |13452 |1575 |1613 | 90.3%|14310.31 |
   | L18 |16640 |13785 |1408 |1447 | 91.3%|13002.19 | | L39 |16640 |13182 |1777 |1681 | 89.9%|14856.56 |
   | L19 |16640 |13542 |1609 |1489 | 91.1%|13059.69 | | L40 |16640 |13442 |1564 |1634 | 90.2%|14389.38 |
   | L20 |16640 |13304 |1818 |1518 | 90.9%|13526.88 | | L41 |16640 |13193 |1802 |1645 | 90.1%|14763.12 |
   | L21 |16640 |13667 |1546 |1427 | 91.4%|12880.00 | | L42 |16640 |13089 |1989 |1562 | 90.6%|13879.06 |
   | L22 |16640 |13245 |1943 |1452 | 91.3%|13088.44 | | L43 |16640 |13288 |1817 |1535 | 90.8%|13814.38 |
   | L23 |16640 |13377 |1738 |1525 | 90.8%|13656.25 | | L44 |16640 |13124 |1824 |1692 | 89.8%|17579.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 623873.90 MB (Load=6361.84 | Prefill=547712.06 | Warmup=0.00 | Decode=69800.00 MB)
   SSD Data/Token (Decode)      : Avg=1090.625 MB/tok (Min=951.469 | P50=1081.688 | P95=1221.250 | Max=1467.625 MB) | Prefill=267.438 MB/tok
   NVMe Batches / Requests      : 4908 Batches | 255053 Raw -> 251075 Merged (3978 LBA Merges, Avg 2544.4 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=250196
   SSD Read Bandwidth (Active)  : Min=0.46 | Avg=506.97 | Peak=3899.26 MB/s | WallAmort=231.16 MB/s
   OS Kernel I/O Verification   : Read=623882.93 MB | Write=0.01 MB | Syscalls=255134
   Sync Stall vs Async DMA      : SyncStall=894619.00 ms | AsyncOverlapped=1215680.46 ms (57.6% Overlapped)
   RAM Traffic & Active BW      : 7358.13 GB moved | Active=4.33 GB/s | WallAmort=2.73 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2525.83s (93.6%, 547712.06 MB SSD) | Decode=173.00s (6.4%, 69800.00 MB SSD)
   CPU Time & Utilization       : User=5863.281s + Sys=64.938s (Wall=2717.798s) | SysUtil=54.5% | ThrUtil=54.5% | 50.44 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 801347.95 ms (379426.1 us/tok | 29.69%)
   MoE AVX2 Q8 Expert Compute   : 894387.40 ms (423478.9 us/tok | 33.14%)
   Router + Lookahead Dispatch  :  15382.17 ms ( 7283.2 us/tok |  0.57%)
   LM Head Output Projection    :   1716.59 ms (  812.8 us/tok |  0.06%)
   Foreground NVMe Sync Stall   : 894619.00 ms (423588.5 us/tok | 33.15%)
   Unaccounted / OMP & Sampling :  91374.14 ms (43264.3 us/tok |  3.39%) | Total Wall=2698827.26 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    62.05%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    13.23%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    12.76%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    10.19%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.77%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=239.0s | Competitor drastic-underperform cutoff=1195.0s (5x Apex)
=== [Colibri-GLM53] CMD: ./baselines/colibri/c/glm53.exe --model D:/apex_d_drive/models/glm53 --ids 1,8,15,22,29,36,43,50,57,64,71,78,85,92,99,106,113,120,127,134,141,148,155,162,169,176,183,190,197,204,211,218,225,232,239,246,253,260,267,274,281,288,295,302,309,316,323,330,337,344,351,358,365,372,379,386,393,400,407,414,421,428,435,442 --greedy 64 32 (5x cutoff=1195.0s) ===
  [Colibri-GLM53] [gguf] D:\apex_d_drive\models\glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: glm5-next, 4 part(s), 38435 tensors under the checkpoint's names (1283 renamed, 129 fused expert tensors split per expert, 0 kept as named), read in place
  [Colibri-GLM53] glm53: GGUF experts interleaved by 16 rows on 3 of 42 layers (G53_ILV16=0: the file's rows)
  [COMP-LIVE] Colibri-GLM53: elapsed=15.0s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=30.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=45.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=60.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=75.2s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=90.4s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=105.5s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=120.6s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=135.7s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=150.8s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=165.8s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=181.0s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=196.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=211.2s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=226.2s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=241.3s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=256.8s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=271.9s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=287.0s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=302.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=317.6s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=333.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=348.2s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=363.5s / cutoff=1195.0s
  [Colibri-GLM53] [STATS] 43008 selections across 6945 distinct experts -> D:/apex_d_drive/models/glm53/.coli_usage
  [Colibri-GLM53] teacher_forcing 5556 335 11 15 15 22 22 22 22 36 57 22 36 64 9 154850 154850 154850 123 121 127967 127501 243 104 253 237 154842 1986 197 220 220 0 220 154827 154827 154827 154827 220 83 220 274 220 220 274 295 83 279 8 220 1 1 2776 72 83 84 365 13 220 220 220 320 83 220 220
  [Colibri-GLM53] greedy 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330
  [Colibri-GLM53] decode 64 token in 246.0s = 0.260 tok/s (3.8 s/token)
  [Colibri-GLM53] experts hits 15425 miss 11249 bytes 111319384064
=== [Colibri-GLM53] Finished rc=0 elapsed=378.15s cancelled=False ===
================================================================================
 [Stage 5 Summary] GLM53 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 0.49 | 0.37 | 2697.57 | 77.60% | 456.57 | 13844.00 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 0.83 | 0.39 | 2471.21 | 89.19% | 466.38 | 14184.51 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 0.81 | 0.37 | 2660.03 | 90.39% | 506.97 | 14016.58 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.260 | - | 57.8% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 06:46 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 06:46 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.48 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    479.15 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1476.37 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8003.60 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10871.09 MB/s
   RND4K Q32T16 Read                  :    493.57 MB/s (  126353 IOPS)
   RND4K Q1T1  Read                   :    708.52 MB/s (Latency: 5.51 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     57.45 GB/s
   AVX2 256-bit Sequential Write BW   :     46.77 GB/s
   STREAM Triad (A = B + s*C) BW      :     31.51 GB/s
   Random Pointer-Chase Latency       :     93.22 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.38 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    197.06 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     22.16 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1380.69 tps | Avg=1380.69 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=73.7 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1215.56 tps | Avg=1292.87 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=73.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1096.67 tps | Avg=1220.11 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=74.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=972.88 tps | Avg=1147.23 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=74.5 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=886.85 tps | Avg=1083.60 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=74.8 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=804.62 tps | Avg=1024.40 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=75.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=749.70 tps | Avg=973.45 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=75.3 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=697.13 tps | Avg=927.49 tps | Hit=100.0% | NVMe=2633.5 MB/s (6.58 MB, QD=64) | RSS=75.5 MB
[LIVE-DECODE] 8/32 tok | Avg=198.03 tps | Hit=100.0% (LA:+0.0%) | NVMe=2633.5 MB/s (6.58 MB) | RSS=75.6 MB
[LIVE-DECODE] 16/32 tok | Avg=196.89 tps | Hit=100.0% (LA:+0.0%) | NVMe=2633.5 MB/s (6.58 MB) | RSS=75.6 MB
[LIVE-DECODE] 24/32 tok | Avg=194.74 tps | Hit=100.0% (LA:+0.0%) | NVMe=2633.5 MB/s (6.58 MB) | RSS=75.6 MB
[LIVE-DECODE] 32/32 tok | Avg=195.57 tps | Hit=100.0% (LA:+0.0%) | NVMe=2633.5 MB/s (6.58 MB) | RSS=75.6 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=75.55 MB | Peak=75.55 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2208.10 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.06 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.06 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.01 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.01 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.06 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.06 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.06 | 12 |  0 |  0 |     0.0 |
   |   18 |     246 | tok_246        |  185.81 | 100.0% |      55 |  160.85 |    5.35 | 12 |  0 |  0 |     0.0 |
   |   19 |     228 | tok_228        |   93.10 |  98.4% |      40 |   88.99 |    5.35 |  0 |  0 |  0 |     0.0 |
   |   20 |      86 | tok_86         |  167.81 |  99.1% |     246 |  163.11 |    5.28 | 12 |  0 |  0 |     0.0 |
   |   21 |      68 | tok_68         |  177.01 | 100.0% |     246 |  152.23 |    5.28 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.06 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.06 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.00 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.00 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.208s, TTFT=2208.10ms): Avg=927.49 | Min=697.13 | Max=1380.69 tps
   Prefill Chunks (8): C1:256t/1380.7tps/100% | C2:256t/1215.6tps/100% | C3:256t/1096.7tps/100% | C4:256t/972.9tps/100%
                       C5:256t/886.9tps/100% | C6:256t/804.6tps/100% | C7:256t/749.7tps/100% | C8:256t/697.1tps/100%
   Decode  (32 tok, 0.164s): Avg=195.57 | Min=187.02 | Max=199.99 tps
   Latency (ms) : Min=5.00 | P10=5.00 | P25=5.04 | P50=5.06 | P75=5.22 | P90=5.28 | P95=5.35 | P99=5.35 | Max=5.35
   Mean/SD/Jitt : Mean=5.11ms | StdDev=0.11ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=300.62 | Avg=2633.47 | Peak=6578.95 MB/s | WallAmort=2.77 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=1.11 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.64 GB/s | WallAmort=0.60 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.21s (93.1%, 0.00 MB SSD) | Decode=0.16s (6.9%, 0.00 MB SSD)
   CPU Time & Utilization       : User=2.906s + Sys=0.750s (Wall=2.390s) | SysUtil=38.2% | ThrUtil=38.2% | 35.37 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1995.53 ms (  959.4 us/tok | 84.14%)
   MoE AVX2 Q8 Expert Compute   :    251.09 ms (  120.7 us/tok | 10.59%)
   Router + Lookahead Dispatch  :     59.07 ms (   28.4 us/tok |  2.49%)
   LM Head Output Projection    :      5.98 ms (    2.9 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     60.06 ms (   28.9 us/tok |  2.53%) | Total Wall=2371.73 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    16.08%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.13%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.09%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    79.68%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.02%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1969.71 tps | Avg=1969.71 tps | Hit=99.2% | NVMe=2663.2 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1845.16 tps | Avg=1905.40 tps | Hit=99.2% | NVMe=3599.5 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1726.69 tps | Avg=1841.86 tps | Hit=99.2% | NVMe=4158.8 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1582.15 tps | Avg=1769.25 tps | Hit=99.2% | NVMe=4623.7 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1553.52 tps | Avg=1721.44 tps | Hit=99.2% | NVMe=4957.5 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1425.97 tps | Avg=1663.98 tps | Hit=99.2% | NVMe=5192.9 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1292.10 tps | Avg=1598.26 tps | Hit=99.2% | NVMe=5384.6 MB/s (133.27 MB, QD=64) | RSS=91.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1281.33 tps | Avg=1550.33 tps | Hit=99.2% | NVMe=5559.7 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=178.69 tps | Hit=99.2% (LA:+0.0%) | NVMe=5460.8 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=179.25 tps | Hit=99.2% (LA:+0.1%) | NVMe=5406.6 MB/s (153.28 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=179.06 tps | Hit=99.2% (LA:+0.1%) | NVMe=5308.4 MB/s (154.23 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=179.23 tps | Hit=99.2% (LA:+0.1%) | NVMe=5228.4 MB/s (155.14 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=91.78 MB | Peak=91.78 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1321.01 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    5.64 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    5.64 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    5.61 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    5.61 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    5.62 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    5.62 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    5.51 | 16 |  0 |  0 |    32.0 |
   |   10 |     254 | qtok_254       |   70.81 |  99.7% |      66 |   64.77 |    5.64 | 15 |  1 |  0 |    59.8 |
   |   11 |      49 | qtok_49        |   84.60 |  79.6% |     129 |   83.23 |    5.64 |  0 |  0 |  0 |    59.8 |
   |   20 |     193 | qtok_193       |   68.95 | 100.0% |      17 |   58.95 |    5.63 | 14 |  2 |  0 |    87.5 |
   |   21 |      63 | qtok_63        |   75.06 |  99.9% |     193 |   67.57 |    5.63 |  0 |  0 |  0 |    87.5 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.49 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.49 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.59 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.59 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.321s, TTFT=1321.01ms): Avg=1550.33 | Min=1281.33 | Max=1969.71 tps
   Prefill Chunks (8): C1:256t/1969.7tps/99% | C2:256t/1845.2tps/99% | C3:256t/1726.7tps/99% | C4:256t/1582.2tps/99%
                       C5:256t/1553.5tps/99% | C6:256t/1426.0tps/99% | C7:256t/1292.1tps/99% | C8:256t/1281.3tps/99%
   Decode  (32 tok, 0.179s): Avg=179.23 | Min=177.21 | Max=182.26 tps
   Latency (ms) : Min=5.49 | P10=5.51 | P25=5.55 | P50=5.59 | P75=5.62 | P90=5.64 | P95=5.64 | P99=5.64 | Max=5.64
   Mean/SD/Jitt : Mean=5.58ms | StdDev=0.05ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=438.51 | Avg=5228.36 | Peak=10603.91 MB/s | WallAmort=103.46 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=6.34 ms | AsyncOverlapped=27.79 ms (81.4% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.61 GB/s | WallAmort=1.40 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.32s (88.1%, 144.44 MB SSD) | Decode=0.18s (11.9%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.719s + Sys=0.469s (Wall=1.530s) | SysUtil=52.1% | ThrUtil=52.1% | 48.19 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    927.15 ms (  445.7 us/tok | 61.83%)
   MoE AVX2 Q8 Expert Compute   :    375.58 ms (  180.6 us/tok | 25.05%)
   Router + Lookahead Dispatch  :     81.43 ms (   39.1 us/tok |  5.43%)
   LM Head Output Projection    :      5.82 ms (    2.8 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :      6.34 ms (    3.0 us/tok |  0.42%)
   Unaccounted / OMP & Sampling :    103.23 ms (   49.6 us/tok |  6.88%) | Total Wall=1499.55 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    18.06%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.87%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.92%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    69.67%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.48%  |
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
    "ttft_ms": 238.43,
    "avg_tps": 687.82,
    "min_tps": 567.72,
    "max_tps": 796.7
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 141.26,
    "min_tps": 116.99,
    "max_tps": 150.78,
    "p50_ms": 6.84,
    "p90_ms": 8.29,
    "p99_ms": 8.55,
    "mean_ms": 7.08,
    "jitter_ms": 0.23
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
    "avg_mbs": 2370.23,
    "peak_mbs": 6127.45,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.83
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
    "dense_attention": 386.75,
    "moe_compute": 105.1,
    "router_lookahead": 7.23,
    "lm_head": 8.86,
    "unaccounted": 6.58
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 87.61,
    "ram_bandwidth_pinning": 1.9,
    "expert_cache_lrfu": 8.69,
    "lookahead_parallel_overlap": 1.41,
    "ssd_nvme_throughput": 0.39,
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
    "ttft_ms": 302.44,
    "avg_tps": 542.25,
    "min_tps": 383.62,
    "max_tps": 613.24
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 126.91,
    "min_tps": 115.19,
    "max_tps": 130.66,
    "p50_ms": 7.83,
    "p90_ms": 8.14,
    "p99_ms": 8.68,
    "mean_ms": 7.88,
    "jitter_ms": 0.2
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
    "avg_mbs": 2444.13,
    "peak_mbs": 8680.56,
    "sync_wait_ms": 4.73,
    "async_overlap_ms": 13.49
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
    "dense_attention": 344.83,
    "moe_compute": 200.36,
    "router_lookahead": 9.13,
    "lm_head": 8.4,
    "unaccounted": 42.29
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 81.31,
    "ram_bandwidth_pinning": 2.16,
    "expert_cache_lrfu": 9.04,
    "lookahead_parallel_overlap": 4.63,
    "ssd_nvme_throughput": 2.86,
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
   System Memory (RAM): 15.99 GB Total / 13.47 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    510.04 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1467.63 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8015.68 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10515.33 MB/s
   RND4K Q32T16 Read                  :    499.72 MB/s (  127928 IOPS)
   RND4K Q1T1  Read                   :    736.21 MB/s (Latency: 5.31 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     59.02 GB/s
   AVX2 256-bit Sequential Write BW   :     38.52 GB/s
   STREAM Triad (A = B + s*C) BW      :     41.90 GB/s
   Random Pointer-Chase Latency       :     56.58 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.29 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    190.98 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     22.97 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 30.98 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 165.50 MB/s (6.19s)
   Window #01 (300.0 MB in 0.51s):   593.82 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   391.64 MB/s (Uncached Direct Read)
   Window #03 (196.0 MB in 0.50s):   388.70 MB/s (Uncached Direct Read)
   Window #04 (216.0 MB in 0.54s):   403.41 MB/s (Uncached Direct Read)
   Window #05 (116.0 MB in 0.27s):   432.17 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   442.56 MB/s (Min=388.70 | Max=593.82 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 391.46 MB/s (2.62s)
   Window #01 (200.0 MB in 0.51s):   395.56 MB/s (Uncached Direct Read)
   Window #02 (216.0 MB in 0.55s):   391.69 MB/s (Uncached Direct Read)
   Window #03 (216.0 MB in 0.54s):   403.14 MB/s (Uncached Direct Read)
   Window #04 (196.0 MB in 0.50s):   389.10 MB/s (Uncached Direct Read)
   Window #05 (196.0 MB in 0.46s):   424.31 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   400.22 MB/s (Min=389.10 | Max=424.31 MB/s)
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
   System Memory (RAM): 15.99 GB Total / 13.55 GB Available
   Active Drive Space : 150.00 GB Total / 54.59 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    454.49 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1469.24 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7917.90 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10565.37 MB/s
   RND4K Q32T16 Read                  :    495.71 MB/s (  126901 IOPS)
   RND4K Q1T1  Read                   :    697.67 MB/s (Latency: 5.60 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     56.13 GB/s
   AVX2 256-bit Sequential Write BW   :     41.82 GB/s
   STREAM Triad (A = B + s*C) BW      :     38.93 GB/s
   Random Pointer-Chase Latency       :     85.77 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.42 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    196.58 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.60 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.50 tps | Avg=0.50 tps | Hit=76.8% | NVMe=480.0 MB/s (51661.71 MB, QD=64) | RSS=13929.9 MB

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
   LRFU Cache / Staging Ring    : 5521.88 MB (589/12384 exp = 4.76% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.83 MB | End=13393.82 MB | Peak=13999.27 MB
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
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 139720.40 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   18.90 |  53.4% |   15724 |   18.74 | 4010.77 | 20 |233 | 83 | 1565280.0 |
   |    3 |     397 | >\n            |   12.80 |   6.2% |     318 |   12.73 | 4010.77 |  0 |  0 |  0 | 1565280.0 |
   |    4 |   13699 | <th            |   14.70 |  18.4% |     334 |   14.61 | 2690.52 |148 |120 | 68 | 1037568.0 |
   |    5 |     766 | ink            |   22.04 |  99.6% |     307 |   14.17 | 2690.52 |  0 |  0 |  0 | 1037568.0 |
   |    6 |     397 | >\n            |   12.54 |  13.7% |      29 |   12.50 | 2779.75 |137 |140 | 59 | 1056160.0 |
   |    7 |   13699 | <th            |   16.29 |  41.2% |     522 |   16.02 | 2779.75 |  0 |  0 |  0 | 1056160.0 |
   |    8 |     397 | >\n            |   17.08 |  39.3% |    1339 |   16.33 | 1970.26 |195 | 96 | 45 | 752064.0 |
   |   36 |   29136 |  Gate          |   15.35 |  36.3% |     479 |   14.86 | 3196.04 | 84 |162 | 90 | 1315072.0 |
   |   37 |    3170 |  why           |   16.44 |  65.8% |   34464 |   13.18 | 3196.04 |  0 |  0 |  0 | 1315072.0 |
   |   20 |    3405 |  question      |   16.21 |  30.6% |     374 |   15.58 | 2854.31 |110 |165 | 61 | 1164032.0 |
   |   21 |     374 |  is            |   15.85 |  19.4% |   15504 |   14.87 | 2854.31 |  0 |  0 |  0 | 1164032.0 |
   |   62 |   24384 |  NV            |   15.58 |  36.6% |   50665 |   15.35 | 2336.31 |147 |130 | 59 | 996928.0 |
   |   63 |   50665 |  sequential    |   14.36 |  20.5% |   25372 |   14.09 | 2336.31 |  0 |  0 |  0 | 996928.0 |
   |   64 |   24384 |  NV            |   17.08 |  41.8% |   25372 |   17.00 | 2254.36 |165 |111 | 60 | 939264.0 |
   |   65 |   25372 |  DMA           |   17.65 |  62.3% |   81911 |   16.44 | 2254.36 |  0 |  0 |  0 | 939264.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 139.720s, TTFT=139720.40ms): Avg=0.50 | Min=0.50 | Max=0.50 tps
   Prefill Chunks (1): C1:70t/0.5tps/77%
   Decode  (64 tok, 166.574s): Avg=0.38 | Min=0.25 | Max=0.53 tps
   Latency (ms) : Min=1890.51 | P10=2027.10 | P25=2515.37 | P50=2641.09 | P75=2694.12 | P90=2819.34 | P95=3196.04 | P99=4010.77 | Max=4010.77
   Mean/SD/Jitt : Mean=2602.72ms | StdDev=375.05ms | Jitter=119.14ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=20241 (59.06%) | Lookahead=6547 (+19.10%) | ColdMiss=7484 (21.84%) | EFF HIT=78.16%
   Lookahead    : 7717 prefetched -> 5083 consumed (65.9% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 77.4% | @64= 78.2% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  347 | 149 | 320 | 60.8%|4348.44 | | L24 |  816 |  477 | 196 | 143 | 82.5%|2084.38 |
   | L04 |  816 |  335 | 187 | 294 | 64.0%|4010.62 | | L25 |  816 |  544 | 121 | 151 | 81.5%|2264.06 |
   | L05 |  816 |  341 | 215 | 260 | 68.1%|3687.19 | | L26 |  816 |  508 | 157 | 151 | 81.5%|2048.44 |
   | L06 |  816 |  370 | 220 | 226 | 72.3%|3435.62 | | L27 |  816 |  527 | 113 | 176 | 78.4%|2522.81 |
   | L07 |  816 |  419 | 205 | 192 | 76.5%|2918.12 | | L28 |  816 |  464 | 168 | 184 | 77.5%|2680.94 |
   | L08 |  816 |  398 | 196 | 222 | 72.8%|3320.62 | | L29 |  816 |  499 | 156 | 161 | 80.3%|2314.38 |
   | L09 |  816 |  399 | 185 | 232 | 71.6%|3234.38 | | L30 |  816 |  471 | 168 | 177 | 78.3%|2494.06 |
   | L10 |  816 |  365 | 231 | 220 | 73.0%|3234.38 | | L31 |  816 |  499 | 137 | 180 | 77.9%|2609.06 |
   | L11 |  816 |  458 | 164 | 194 | 76.2%|3618.75 | | L32 |  816 |  497 | 140 | 179 | 78.1%|2688.12 |
   | L12 |  816 |  477 | 162 | 177 | 78.3%|3199.25 | | L33 |  816 |  514 | 143 | 159 | 80.5%|2443.75 |
   | L13 |  816 |  522 | 113 | 181 | 77.8%|2508.44 | | L34 |  816 |  518 | 144 | 154 | 81.1%|2400.62 |
   | L14 |  816 |  473 | 153 | 190 | 76.7%|2839.06 | | L35 |  816 |  508 | 159 | 149 | 81.7%|2343.12 |
   | L15 |  816 |  516 | 123 | 177 | 78.3%|2515.62 | | L36 |  816 |  500 | 167 | 149 | 81.7%|2379.06 |
   | L16 |  816 |  458 | 173 | 185 | 77.3%|2637.81 | | L37 |  816 |  481 | 179 | 156 | 80.9%|2364.69 |
   | L17 |  816 |  463 | 175 | 178 | 78.2%|2666.56 | | L38 |  816 |  548 | 125 | 143 | 82.5%|2141.88 |
   | L18 |  816 |  567 |  96 | 153 | 81.2%|1983.75 | | L39 |  816 |  513 | 156 | 147 | 82.0%|2264.06 |
   | L19 |  816 |  547 | 112 | 157 | 80.8%|2098.75 | | L40 |  816 |  485 | 167 | 164 | 79.9%|2515.62 |
   | L20 |  816 |  590 |  91 | 135 | 83.5%|1897.50 | | L41 |  816 |  466 | 188 | 162 | 80.1%|2515.62 |
   | L21 |  816 |  565 | 100 | 151 | 81.5%|2134.69 | | L42 |  816 |  517 | 149 | 150 | 81.6%|2256.88 |
   | L22 |  816 |  549 | 129 | 138 | 83.1%|1976.56 | | L43 |  816 |  522 | 149 | 145 | 82.2%|2105.94 |
   | L23 |  816 |  550 | 116 | 150 | 81.6%|2070.00 | | L44 |  816 |  474 | 170 | 172 | 78.9%|3241.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 118497.27 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=66835.56 MB)
   SSD Data/Token (Decode)      : Avg=1044.306 MB/tok (Min=734.438 | P50=1072.312 | P95=1284.250 | Max=1528.594 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2669 Batches | 47273 Raw -> 46653 Merged (620 LBA Merges, Avg 2600.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=45774
   SSD Read Bandwidth (Active)  : Min=0.30 | Avg=447.64 | Peak=3876.13 MB/s | WallAmort=386.87 MB/s (100.0% of 454.5 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=119484.31 MB | Write=128.00 MB | Syscalls=58227
   Sync Stall vs Async DMA      : SyncStall=116383.99 ms | AsyncOverlapped=249811.52 ms (68.2% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=7.35 GB/s (18.9% STREAM) | WallAmort=2.54 GB/s (Max=38.93 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=139.72s (45.6%, 45299.88 MB SSD) | Decode=166.57s (54.4%, 66835.56 MB SSD)
   CPU Time & Utilization       : User=314.516s + Sys=12.109s (Wall=326.048s) | SysUtil=25.0% | ThrUtil=25.0% | 49.23 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  41063.26 ms (306442.2 us/tok | 13.41%)
   MoE AVX2 Q8 Expert Compute   :  62929.67 ms (469624.4 us/tok | 20.55%)
   Router + Lookahead Dispatch  :    842.00 ms ( 6283.6 us/tok |  0.27%)
   LM Head Output Projection    :   1690.05 ms (12612.3 us/tok |  0.55%)
   Foreground NVMe Sync Stall   : 116383.99 ms (868537.2 us/tok | 38.00%)
   Unaccounted / OMP & Sampling :  83385.75 ms (622281.7 us/tok | 27.22%) | Total Wall=306294.71 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    33.04%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    27.47%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.69%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.24%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.56%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_glm53_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5371.88 MB (573 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=76.5% | NVMe=487.3 MB/s (47437.59 MB, QD=64) | RSS=13770.9 MB
[LIVE-DECODE] 2/32 tok | Avg=0.25 tps | Hit=76.5% (LA:+10.1%) | NVMe=482.6 MB/s (50529.52 MB) | RSS=13728.8 MB
[LIVE-DECODE] 4/32 tok | Avg=0.28 tps | Hit=76.5% (LA:+10.8%) | NVMe=478.2 MB/s (52885.40 MB) | RSS=13651.4 MB
[LIVE-DECODE] 6/32 tok | Avg=0.29 tps | Hit=76.6% (LA:+11.5%) | NVMe=473.8 MB/s (55352.59 MB) | RSS=13522.0 MB
[LIVE-DECODE] 8/32 tok | Avg=0.31 tps | Hit=76.7% (LA:+12.0%) | NVMe=471.8 MB/s (57341.15 MB) | RSS=13502.4 MB
[LIVE-DECODE] 10/32 tok | Avg=0.33 tps | Hit=76.9% (LA:+12.6%) | NVMe=469.8 MB/s (59420.34 MB) | RSS=13468.9 MB
[LIVE-DECODE] 12/32 tok | Avg=0.33 tps | Hit=77.0% (LA:+13.2%) | NVMe=467.4 MB/s (61661.65 MB) | RSS=13409.7 MB
[LIVE-DECODE] 14/32 tok | Avg=0.34 tps | Hit=77.1% (LA:+13.7%) | NVMe=466.5 MB/s (63635.77 MB) | RSS=13406.9 MB
[LIVE-DECODE] 16/32 tok | Avg=0.36 tps | Hit=77.3% (LA:+13.9%) | NVMe=465.8 MB/s (65208.09 MB) | RSS=13406.8 MB
[LIVE-DECODE] 18/32 tok | Avg=0.35 tps | Hit=77.3% (LA:+14.5%) | NVMe=463.9 MB/s (67659.02 MB) | RSS=13406.8 MB
[LIVE-DECODE] 20/32 tok | Avg=0.35 tps | Hit=77.4% (LA:+14.9%) | NVMe=462.2 MB/s (69754.71 MB) | RSS=13337.1 MB
[LIVE-DECODE] 22/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+15.4%) | NVMe=460.9 MB/s (71761.77 MB) | RSS=13283.2 MB
[LIVE-DECODE] 24/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+15.8%) | NVMe=459.7 MB/s (74033.34 MB) | RSS=13272.6 MB
[LIVE-DECODE] 26/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+16.1%) | NVMe=458.7 MB/s (76170.52 MB) | RSS=13272.5 MB
[LIVE-DECODE] 28/32 tok | Avg=0.36 tps | Hit=77.6% (LA:+16.4%) | NVMe=457.8 MB/s (78374.77 MB) | RSS=13272.5 MB
[LIVE-DECODE] 30/32 tok | Avg=0.36 tps | Hit=77.6% (LA:+16.7%) | NVMe=456.9 MB/s (80399.84 MB) | RSS=13272.5 MB
[LIVE-DECODE] 32/32 tok | Avg=0.37 tps | Hit=77.6% (LA:+16.8%) | NVMe=456.6 MB/s (82344.15 MB) | RSS=13272.5 MB

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
   LRFU Cache / Staging Ring    : 5371.88 MB (573/12384 exp = 4.63% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13272.52 MB | Peak=13844.00 MB
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
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 129827.96 |  0 |  0 |  0 |     0.0 |
   |    2 |     220 |                |   14.20 |   9.2% |   24923 |   14.18 | 3989.04 | 21 |227 | 88 | 1583072.0 |
   |    3 |      16 | 1              |   18.33 |  26.6% |      19 |   17.27 | 3989.04 |  0 |  0 |  0 | 1583072.0 |
   |    4 |   15245 | -bit           |   13.67 |  13.4% |      13 |   13.56 | 3067.80 | 84 |190 | 62 | 1206208.0 |
   |    5 |    1112 | ...            |   13.59 |   8.9% |    1565 |   13.29 | 3067.80 |  0 |  0 |  0 | 1206208.0 |
   |    6 |    4398 |  More          |   11.74 |   8.2% |     508 |   10.90 | 3227.65 | 77 |196 | 63 | 1263200.0 |
   |    7 |     198 | \n             |   11.62 |   6.7% |     271 |   11.49 | 3227.65 |  0 |  0 |  0 | 1263200.0 |
   |    8 |      58 | [              |   13.68 |   7.4% |     785 |   13.10 | 2472.06 |125 |162 | 49 | 1018144.0 |
   |   18 |      16 | 1              |   14.79 |  37.1% |       8 |   12.48 | 3053.33 | 88 |179 | 69 | 1254880.0 |
   |   19 |   15245 | -bit           |   24.00 |  99.8% |    1455 |   16.07 | 3053.33 |  0 |  0 |  0 | 1254880.0 |
   |   12 |   21265 |  highlights    |   11.86 |  14.3% |    7998 |   11.70 | 2853.89 | 96 |194 | 46 | 1147552.0 |
   |   13 |   88737 | ???\n          |   14.28 |  12.8% |    9335 |   14.26 | 2853.89 |  0 |  0 |  0 | 1147552.0 |
   |   30 |    1506 | ized           |   16.47 |  78.5% |   10267 |   12.96 | 2495.31 |141 |124 | 71 | 1036832.0 |
   |   31 |     220 |                |   19.68 |  90.4% |      16 |   16.01 | 2495.31 |  0 |  0 |  0 | 1036832.0 |
   |   32 |      16 | 1              |   15.37 |  33.8% |      19 |   14.89 | 2328.55 |161 |107 | 68 | 995488.0 |
   |   33 |   15245 | -bit           |   25.55 | 100.0% |    1455 |   16.54 | 2328.55 |  0 |  0 |  0 | 995488.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 129.828s, TTFT=129827.96ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:64t/0.5tps/77%
   Decode  (32 tok, 87.658s): Avg=0.37 | Min=0.25 | Max=0.53 tps
   Latency (ms) : Min=1889.11 | P10=2328.55 | P25=2495.31 | P50=2697.57 | P75=3053.33 | P90=3227.65 | P95=3989.04 | P99=3989.04 | Max=3989.04
   Mean/SD/Jitt : Mean=2739.31ms | StdDev=451.13ms | Jitter=184.95ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=16332 (60.76%) | Lookahead=4528 (+16.85%) | ColdMiss=6020 (22.40%) | EFF HIT=77.60%
   Lookahead    : 4270 prefetched -> 3129 consumed (73.3% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 77.3% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  291 |  98 | 251 | 60.8%|2903.75 | | L24 |  640 |  443 |  75 | 122 | 80.9%|1466.25 |
   | L04 |  640 |  290 | 127 | 223 | 65.2%|2716.88 | | L25 |  640 |  409 |  97 | 134 | 79.1%|1681.88 |
   | L05 |  640 |  267 | 158 | 215 | 66.4%|2623.44 | | L26 |  640 |  435 |  98 | 107 | 83.3%|1423.12 |
   | L06 |  640 |  315 | 141 | 184 | 71.2%|2285.62 | | L27 |  640 |  414 |  97 | 129 | 79.8%|1581.25 |
   | L07 |  640 |  354 | 136 | 150 | 76.6%|1976.56 | | L28 |  640 |  406 | 103 | 131 | 79.5%|1617.19 |
   | L08 |  640 |  333 | 143 | 164 | 74.4%|2034.06 | | L29 |  640 |  385 | 114 | 141 | 78.0%|1753.75 |
   | L09 |  640 |  289 | 164 | 187 | 70.8%|2213.75 | | L30 |  640 |  396 | 103 | 141 | 78.0%|1653.12 |
   | L10 |  640 |  306 | 147 | 187 | 70.8%|2235.31 | | L31 |  640 |  383 | 116 | 141 | 78.0%|1725.00 |
   | L11 |  640 |  394 |  93 | 153 | 76.1%|2437.50 | | L32 |  640 |  361 | 143 | 136 | 78.8%|1775.31 |
   | L12 |  640 |  354 | 138 | 148 | 76.9%|2177.50 | | L33 |  640 |  376 | 133 | 131 | 79.5%|1581.25 |
   | L13 |  640 |  402 |  90 | 148 | 76.9%|1753.75 | | L34 |  640 |  433 |  91 | 116 | 81.9%|1466.25 |
   | L14 |  640 |  427 |  66 | 147 | 77.0%|1667.50 | | L35 |  640 |  374 | 139 | 127 | 80.2%|1595.62 |
   | L15 |  640 |  428 |  71 | 141 | 78.0%|1638.75 | | L36 |  640 |  356 | 152 | 132 | 79.4%|1631.56 |
   | L16 |  640 |  422 |  90 | 128 | 80.0%|1667.50 | | L37 |  640 |  385 | 115 | 140 | 78.1%|1840.00 |
   | L17 |  640 |  430 |  77 | 133 | 79.2%|1624.38 | | L38 |  640 |  405 | 104 | 131 | 79.5%|1610.00 |
   | L18 |  640 |  446 |  72 | 122 | 80.9%|1509.38 | | L39 |  640 |  404 | 108 | 128 | 80.0%|1588.44 |
   | L19 |  640 |  447 |  76 | 117 | 81.7%|1480.62 | | L40 |  640 |  421 |  89 | 130 | 79.7%|1538.12 |
   | L20 |  640 |  429 |  78 | 133 | 79.2%|1588.44 | | L41 |  640 |  408 |  92 | 140 | 78.1%|1674.69 |
   | L21 |  640 |  451 |  73 | 116 | 81.9%|1437.50 | | L42 |  640 |  362 | 157 | 121 | 81.1%|1444.69 |
   | L22 |  640 |  453 |  70 | 117 | 81.7%|1430.31 | | L43 |  640 |  424 | 105 | 111 | 82.7%|1509.38 |
   | L23 |  640 |  422 |  82 | 136 | 78.8%|1602.81 | | L44 |  640 |  402 | 107 | 131 | 79.5%|1951.38 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 82344.15 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=34906.56 MB)
   SSD Data/Token (Decode)      : Avg=1090.830 MB/tok (Min=786.156 | P50=1068.594 | P95=1545.969 | Max=1545.969 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1386 Batches | 32453 Raw -> 31982 Merged (471 LBA Merges, Avg 2636.5 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=31103
   SSD Read Bandwidth (Active)  : Min=0.32 | Avg=456.57 | Peak=4122.14 MB/s | WallAmort=378.62 MB/s
   OS Kernel I/O Verification   : Read=82353.18 MB | Write=0.00 MB | Syscalls=36018
   Sync Stall vs Async DMA      : SyncStall=90310.30 ms | AsyncOverlapped=165203.24 ms (64.7% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=5.95 GB/s | WallAmort=2.24 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=129.83s (59.7%, 41075.75 MB SSD) | Decode=87.66s (40.3%, 34906.56 MB SSD)
   CPU Time & Utilization       : User=238.641s + Sys=9.750s (Wall=236.996s) | SysUtil=26.2% | ThrUtil=26.2% | 24.24 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  34067.03 ms (354864.9 us/tok | 15.66%)
   MoE AVX2 Q8 Expert Compute   :  46864.71 ms (488174.1 us/tok | 21.55%)
   Router + Lookahead Dispatch  :    686.70 ms ( 7153.1 us/tok |  0.32%)
   LM Head Output Projection    :   1030.11 ms (10730.3 us/tok |  0.47%)
   Foreground NVMe Sync Stall   :  90310.30 ms (940732.3 us/tok | 41.52%)
   Unaccounted / OMP & Sampling :  44527.19 ms (463824.9 us/tok | 20.47%) | Total Wall=217486.03 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    35.63%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    24.84%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    28.75%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.71%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.07%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_glm53_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5606.25 MB (598 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.83 tps | Avg=0.83 tps | Hit=90.6% | NVMe=504.3 MB/s (74277.59 MB, QD=64) | RSS=14093.6 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.82 tps | Avg=0.83 tps | Hit=90.4% | NVMe=510.2 MB/s (145295.52 MB, QD=64) | RSS=14093.8 MB
[LIVE-DECODE] 2/128 tok | Avg=0.22 tps | Hit=90.4% (LA:+10.6%) | NVMe=507.6 MB/s (148736.77 MB) | RSS=14007.1 MB
[LIVE-DECODE] 4/128 tok | Avg=0.24 tps | Hit=90.3% (LA:+10.7%) | NVMe=504.7 MB/s (151480.96 MB) | RSS=13835.1 MB
[LIVE-DECODE] 6/128 tok | Avg=0.26 tps | Hit=90.3% (LA:+10.7%) | NVMe=502.4 MB/s (153889.77 MB) | RSS=13680.2 MB
[LIVE-DECODE] 8/128 tok | Avg=0.28 tps | Hit=90.3% (LA:+10.8%) | NVMe=501.0 MB/s (156170.65 MB) | RSS=13614.0 MB
[LIVE-DECODE] 10/128 tok | Avg=0.29 tps | Hit=90.3% (LA:+10.8%) | NVMe=499.9 MB/s (158190.65 MB) | RSS=13562.2 MB
[LIVE-DECODE] 12/128 tok | Avg=0.30 tps | Hit=90.2% (LA:+10.9%) | NVMe=498.7 MB/s (160325.34 MB) | RSS=13530.8 MB
[LIVE-DECODE] 14/128 tok | Avg=0.31 tps | Hit=90.2% (LA:+10.9%) | NVMe=497.5 MB/s (162419.46 MB) | RSS=13504.6 MB
[LIVE-DECODE] 16/128 tok | Avg=0.32 tps | Hit=90.2% (LA:+11.0%) | NVMe=496.5 MB/s (164537.59 MB) | RSS=13497.8 MB
[LIVE-DECODE] 18/128 tok | Avg=0.33 tps | Hit=90.2% (LA:+11.0%) | NVMe=495.4 MB/s (166678.84 MB) | RSS=13497.8 MB
[LIVE-DECODE] 20/128 tok | Avg=0.33 tps | Hit=90.1% (LA:+11.1%) | NVMe=494.5 MB/s (168777.27 MB) | RSS=13497.7 MB
[LIVE-DECODE] 22/128 tok | Avg=0.33 tps | Hit=90.1% (LA:+11.1%) | NVMe=493.4 MB/s (171002.34 MB) | RSS=13497.6 MB
[LIVE-DECODE] 24/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.2%) | NVMe=492.2 MB/s (173275.09 MB) | RSS=13497.6 MB
[LIVE-DECODE] 26/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.2%) | NVMe=491.2 MB/s (175474.52 MB) | RSS=13497.6 MB
[LIVE-DECODE] 28/128 tok | Avg=0.34 tps | Hit=90.0% (LA:+11.3%) | NVMe=490.3 MB/s (177539.65 MB) | RSS=13497.5 MB
[LIVE-DECODE] 30/128 tok | Avg=0.35 tps | Hit=90.0% (LA:+11.3%) | NVMe=489.7 MB/s (179410.09 MB) | RSS=13497.5 MB
[LIVE-DECODE] 32/128 tok | Avg=0.35 tps | Hit=90.0% (LA:+11.3%) | NVMe=489.3 MB/s (181160.52 MB) | RSS=13497.5 MB
[LIVE-DECODE] 34/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.4%) | NVMe=488.5 MB/s (183219.27 MB) | RSS=13497.5 MB
[LIVE-DECODE] 36/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.4%) | NVMe=487.6 MB/s (185402.96 MB) | RSS=13497.5 MB
[LIVE-DECODE] 38/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.5%) | NVMe=486.7 MB/s (187619.52 MB) | RSS=13497.6 MB
[LIVE-DECODE] 40/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.5%) | NVMe=486.0 MB/s (189600.34 MB) | RSS=13488.2 MB
[LIVE-DECODE] 42/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.5%) | NVMe=485.2 MB/s (191721.40 MB) | RSS=13488.2 MB
[LIVE-DECODE] 44/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.6%) | NVMe=484.2 MB/s (194119.34 MB) | RSS=13488.2 MB
[LIVE-DECODE] 46/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.7%) | NVMe=483.3 MB/s (196408.15 MB) | RSS=13488.2 MB
[LIVE-DECODE] 48/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.7%) | NVMe=482.6 MB/s (198518.71 MB) | RSS=13497.6 MB
[LIVE-DECODE] 50/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=481.8 MB/s (200712.84 MB) | RSS=13497.6 MB
[LIVE-DECODE] 52/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=481.2 MB/s (202668.52 MB) | RSS=13497.6 MB
[LIVE-DECODE] 54/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=480.8 MB/s (204536.71 MB) | RSS=13497.6 MB
[LIVE-DECODE] 56/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.9%) | NVMe=479.9 MB/s (206972.52 MB) | RSS=13497.6 MB
[LIVE-DECODE] 58/128 tok | Avg=0.36 tps | Hit=89.7% (LA:+12.0%) | NVMe=479.2 MB/s (209217.15 MB) | RSS=13497.6 MB
[LIVE-DECODE] 60/128 tok | Avg=0.36 tps | Hit=89.7% (LA:+12.0%) | NVMe=478.7 MB/s (211126.15 MB) | RSS=13497.6 MB
[LIVE-DECODE] 62/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.0%) | NVMe=478.1 MB/s (213078.96 MB) | RSS=13497.6 MB
[LIVE-DECODE] 64/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.1%) | NVMe=477.7 MB/s (214950.02 MB) | RSS=13497.6 MB
[LIVE-DECODE] 66/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.2%) | NVMe=477.1 MB/s (217120.71 MB) | RSS=13497.6 MB
[LIVE-DECODE] 68/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.2%) | NVMe=476.8 MB/s (219203.59 MB) | RSS=13507.0 MB
[LIVE-DECODE] 70/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.2%) | NVMe=476.3 MB/s (221131.84 MB) | RSS=13507.0 MB
[LIVE-DECODE] 72/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=475.8 MB/s (223088.84 MB) | RSS=13506.9 MB
[LIVE-DECODE] 74/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=475.3 MB/s (225066.52 MB) | RSS=13507.0 MB
[LIVE-DECODE] 76/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=474.8 MB/s (227095.21 MB) | RSS=13507.0 MB
[LIVE-DECODE] 78/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.4%) | NVMe=474.2 MB/s (229112.59 MB) | RSS=13488.2 MB
[LIVE-DECODE] 80/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.4%) | NVMe=473.9 MB/s (230932.09 MB) | RSS=13488.2 MB
[LIVE-DECODE] 82/128 tok | Avg=0.38 tps | Hit=89.6% (LA:+12.4%) | NVMe=473.6 MB/s (232589.15 MB) | RSS=13488.2 MB
[LIVE-DECODE] 84/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.4%) | NVMe=473.3 MB/s (234322.84 MB) | RSS=13488.2 MB
[LIVE-DECODE] 86/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=473.0 MB/s (236051.15 MB) | RSS=13488.2 MB
[LIVE-DECODE] 88/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.6 MB/s (237968.84 MB) | RSS=13488.2 MB
[LIVE-DECODE] 90/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.2 MB/s (239879.02 MB) | RSS=13488.2 MB
[LIVE-DECODE] 92/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.0 MB/s (241875.09 MB) | RSS=13497.6 MB
[LIVE-DECODE] 94/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.6%) | NVMe=471.6 MB/s (243864.34 MB) | RSS=13497.6 MB
[LIVE-DECODE] 96/128 tok | Avg=0.38 tps | Hit=89.4% (LA:+12.6%) | NVMe=471.3 MB/s (245669.15 MB) | RSS=13497.6 MB
[LIVE-DECODE] 98/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=470.9 MB/s (247630.59 MB) | RSS=13497.6 MB
[LIVE-DECODE] 100/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=470.7 MB/s (249443.46 MB) | RSS=13491.6 MB
[LIVE-DECODE] 102/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=470.3 MB/s (251289.21 MB) | RSS=13478.8 MB
[LIVE-DECODE] 104/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=469.9 MB/s (253249.52 MB) | RSS=13478.8 MB
[LIVE-DECODE] 106/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=469.7 MB/s (255233.15 MB) | RSS=13488.2 MB
[LIVE-DECODE] 108/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=469.3 MB/s (257254.21 MB) | RSS=13488.2 MB
[LIVE-DECODE] 110/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.9 MB/s (259203.65 MB) | RSS=13488.2 MB
[LIVE-DECODE] 112/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.6 MB/s (261099.90 MB) | RSS=13488.2 MB
[LIVE-DECODE] 114/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=468.3 MB/s (263146.46 MB) | RSS=13488.2 MB
[LIVE-DECODE] 116/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=468.0 MB/s (264962.59 MB) | RSS=13488.2 MB
[LIVE-DECODE] 118/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=467.7 MB/s (266796.96 MB) | RSS=13488.2 MB
[LIVE-DECODE] 120/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+12.9%) | NVMe=467.4 MB/s (268768.84 MB) | RSS=13488.2 MB
[LIVE-DECODE] 122/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=467.1 MB/s (270828.84 MB) | RSS=13488.2 MB
[LIVE-DECODE] 124/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.8 MB/s (272657.90 MB) | RSS=13488.2 MB
[LIVE-DECODE] 126/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.5 MB/s (274385.59 MB) | RSS=13488.2 MB
[LIVE-DECODE] 128/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.4 MB/s (276203.84 MB) | RSS=13488.2 MB

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
   LRFU Cache / Staging Ring    : 5606.25 MB (598/12384 exp = 4.83% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.79 MB | End=13488.16 MB | Peak=14184.51 MB
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
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 619707.82 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   24.96 | 100.0% |    1062 |   16.43 | 4516.12 | 35 |173 |128 | 1761920.0 |
   |    3 |   39929 |  LB            |   17.75 |  78.0% |   33903 |   16.24 | 4516.12 |  0 |  0 |  0 | 1761920.0 |
   |    4 |      32 | A              |   14.08 |  30.6% |    1911 |   13.59 | 3691.18 | 71 |173 | 92 | 1405024.0 |
   |    5 |   46254 | -sort          |   18.02 |  42.5% |    1331 |   17.61 | 3691.18 |  0 |  0 |  0 | 1405024.0 |
   |    6 |     287 | ing            |   14.36 |  38.6% |   11492 |   11.93 | 3182.19 |111 |152 | 73 | 1233312.0 |
   |    7 |   11492 |  coal          |   16.09 |  54.1% |    1207 |   14.51 | 3182.19 |  0 |  0 |  0 | 1233312.0 |
   |    8 |    3300 | esc            |   18.05 |  93.7% |     642 |   13.98 | 3006.86 |123 |138 | 75 | 1167808.0 |
   |   56 |  154842 | </think>       |   14.32 |  56.1% |     641 |   13.02 | 3066.43 | 90 |167 | 79 | 1247136.0 |
   |   57 |     641 | In             |   15.30 |  41.7% |     565 |   13.90 | 3066.43 |  0 |  0 |  0 | 1247136.0 |
   |    9 |     291 | ed             |   20.63 |  75.1% |     287 |   19.27 | 3006.86 |  0 |  0 |  0 | 1167808.0 |
   |   44 |    3170 |  why           |   17.45 |  85.5% |     419 |   13.32 | 2990.48 |114 |136 | 86 | 1227744.0 |
   |  126 |     291 | ed             |   14.96 |  32.3% |    1207 |   14.08 | 2137.12 |190 | 85 | 61 | 884576.0 |
   |  127 |    9421 | -block         |   17.23 |  54.2% |    7299 |   15.51 | 2137.12 |  0 |  0 |  0 | 884576.0 |
   |  128 |    9421 | -block         |   14.61 |  29.9% |    1207 |   13.52 | 2146.75 |189 | 94 | 53 | 930944.0 |
   |  129 |     291 | ed             |   20.50 |  98.5% |   29819 |   14.11 | 2146.75 |  0 |  0 |  0 | 930944.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 619.708s, TTFT=619707.82ms): Avg=0.83 | Min=0.82 | Max=0.83 tps
   Prefill Chunks (2): C1:256t/0.8tps/91% | C2:256t/0.8tps/90%
   Decode  (128 tok, 324.324s): Avg=0.39 | Min=0.22 | Max=0.49 tps
   Latency (ms) : Min=2042.43 | P10=2156.46 | P25=2314.79 | P50=2471.21 | P75=2683.51 | P90=2840.40 | P95=3066.43 | P99=4516.12 | Max=4516.12
   Mean/SD/Jitt : Mean=2533.78ms | StdDev=380.77ms | Jitter=91.10ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=147361 (76.14%) | Lookahead=25256 (+13.05%) | ColdMiss=20919 (10.81%) | EFF HIT=89.19%
   Lookahead    : 15757 prefetched -> 9727 consumed (61.7% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.2% | @64= 89.7% | @128= 89.2% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3154 | 741 | 713 | 84.5%|9228.75 | | L24 | 4608 | 3590 | 559 | 459 | 90.0%|5426.56 |
   | L04 | 4608 | 3238 | 676 | 694 | 84.9%|8826.25 | | L25 | 4608 | 3654 | 484 | 470 | 89.8%|6087.81 |
   | L05 | 4608 | 3184 | 797 | 627 | 86.4%|8244.06 | | L26 | 4608 | 3657 | 509 | 442 | 90.4%|5455.31 |
   | L06 | 4608 | 3253 | 787 | 568 | 87.7%|7755.31 | | L27 | 4608 | 3534 | 530 | 544 | 88.2%|7086.88 |
   | L07 | 4608 | 3369 | 755 | 484 | 89.5%|6504.69 | | L28 | 4608 | 3516 | 589 | 503 | 89.1%|6130.94 |
   | L08 | 4608 | 3455 | 629 | 524 | 88.6%|6907.19 | | L29 | 4608 | 3425 | 704 | 479 | 89.6%|6066.25 |
   | L09 | 4608 | 3308 | 724 | 576 | 87.5%|7065.31 | | L30 | 4608 | 3519 | 610 | 479 | 89.6%|5750.00 |
   | L10 | 4608 | 3264 | 757 | 587 | 87.3%|7424.69 | | L31 | 4608 | 3371 | 644 | 593 | 87.1%|7288.12 |
   | L11 | 4608 | 3486 | 596 | 526 | 88.6%|8568.75 | | L32 | 4608 | 3289 | 759 | 560 | 87.8%|6792.19 |
   | L12 | 4608 | 3449 | 665 | 494 | 89.3%|7152.25 | | L33 | 4608 | 3375 | 736 | 497 | 89.2%|6619.69 |
   | L13 | 4608 | 3596 | 543 | 469 | 89.8%|5764.38 | | L34 | 4608 | 3661 | 507 | 440 | 90.5%|5742.81 |
   | L14 | 4608 | 3625 | 487 | 496 | 89.2%|6210.00 | | L35 | 4608 | 3465 | 668 | 475 | 89.7%|6066.25 |
   | L15 | 4608 | 3618 | 500 | 490 | 89.4%|6008.75 | | L36 | 4608 | 3313 | 830 | 465 | 89.9%|6145.31 |
   | L16 | 4608 | 3638 | 498 | 472 | 89.8%|5994.38 | | L37 | 4608 | 3609 | 534 | 465 | 89.9%|5750.00 |
   | L17 | 4608 | 3739 | 394 | 475 | 89.7%|5771.56 | | L38 | 4608 | 3601 | 539 | 468 | 89.8%|5972.81 |
   | L18 | 4608 | 3814 | 345 | 449 | 90.3%|5498.44 | | L39 | 4608 | 3586 | 538 | 484 | 89.5%|5764.38 |
   | L19 | 4608 | 3742 | 455 | 411 | 91.1%|5124.69 | | L40 | 4608 | 3623 | 525 | 460 | 90.0%|5656.56 |
   | L20 | 4608 | 3636 | 535 | 437 | 90.5%|5354.69 | | L41 | 4608 | 3518 | 623 | 467 | 89.9%|6087.81 |
   | L21 | 4608 | 3727 | 438 | 443 | 90.4%|5383.44 | | L42 | 4608 | 3387 | 766 | 455 | 90.1%|5469.69 |
   | L22 | 4608 | 3689 | 496 | 423 | 90.8%|5232.50 | | L43 | 4608 | 3575 | 614 | 419 | 90.9%|5354.69 |
   | L23 | 4608 | 3589 | 585 | 434 | 90.6%|5282.81 | | L44 | 4608 | 3520 | 585 | 503 | 89.1%|7696.62 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 276203.84 MB (Load=6361.84 | Prefill=138933.69 | Warmup=0.00 | Decode=130908.31 MB)
   SSD Data/Token (Decode)      : Avg=1022.721 MB/tok (Min=828.531 | P50=998.031 | P95=1204.406 | Max=1720.625 MB) | Prefill=271.355 MB/tok
   NVMe Batches / Requests      : 5639 Batches | 112046 Raw -> 110485 Merged (1561 LBA Merges, Avg 2559.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=109606
   SSD Read Bandwidth (Active)  : Min=0.46 | Avg=466.38 | Peak=4145.40 MB/s | WallAmort=292.58 MB/s
   OS Kernel I/O Verification   : Read=276212.87 MB | Write=0.01 MB | Syscalls=114570
   Sync Stall vs Async DMA      : SyncStall=300755.51 ms | AsyncOverlapped=577350.17 ms (65.7% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=5.72 GB/s | WallAmort=2.95 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=619.71s (65.6%, 138933.69 MB SSD) | Decode=324.32s (34.4%, 130908.31 MB SSD)
   CPU Time & Utilization       : User=1623.750s + Sys=28.141s (Wall=963.487s) | SysUtil=42.9% | ThrUtil=42.9% | 39.65 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 213954.51 ms (334303.9 us/tok | 22.66%)
   MoE AVX2 Q8 Expert Compute   : 268963.97 ms (420256.2 us/tok | 28.49%)
   Router + Lookahead Dispatch  :   4316.26 ms ( 6744.2 us/tok |  0.46%)
   LM Head Output Projection    :   3388.67 ms ( 5294.8 us/tok |  0.36%)
   Foreground NVMe Sync Stall   : 300755.51 ms (469930.5 us/tok | 31.86%)
   Unaccounted / OMP & Sampling : 152652.84 ms (238520.1 us/tok | 16.17%) | Total Wall=944031.75 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    54.88%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    17.50%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    16.55%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     9.01%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.06%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_glm53_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "glm-5.3-flash-ud-iq2_xxs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "glm5-next (GLM-5.3-Flash)"}]}
[Stage 3] /v1/chat/completions (stream=false) 138347.3ms | usage={'prompt_tokens': 19, 'completion_tokens': 16, 'total_tokens': 35} | text='\nSummarize LBACoalesce in one sentence.\nSummarize LB'
[Stage 3] /v1/chat/completions (stream=true SSE) 56553.2ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_glm53_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5437.50 MB (580 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=0.84 tps | Avg=0.84 tps | Hit=90.6% | NVMe=505.1 MB/s (74277.59 MB, QD=64) | RSS=13925.4 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=0.82 tps | Avg=0.83 tps | Hit=90.4% | NVMe=511.1 MB/s (145295.52 MB, QD=64) | RSS=13924.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=0.82 tps | Avg=0.83 tps | Hit=90.4% | NVMe=513.1 MB/s (214799.34 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=0.76 tps | Avg=0.81 tps | Hit=90.4% | NVMe=514.8 MB/s (283922.65 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=0.82 tps | Avg=0.81 tps | Hit=90.5% | NVMe=516.4 MB/s (352711.65 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=0.81 tps | Avg=0.81 tps | Hit=90.5% | NVMe=518.1 MB/s (420869.27 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=0.81 tps | Avg=0.81 tps | Hit=90.5% | NVMe=518.5 MB/s (488245.34 MB, QD=64) | RSS=13925.0 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=0.82 tps | Avg=0.81 tps | Hit=90.6% | NVMe=519.5 MB/s (554073.90 MB, QD=64) | RSS=13925.7 MB
[LIVE-DECODE] 2/64 tok | Avg=0.33 tps | Hit=90.6% (LA:+10.0%) | NVMe=519.0 MB/s (556515.84 MB) | RSS=13927.3 MB
[LIVE-DECODE] 4/64 tok | Avg=0.28 tps | Hit=90.6% (LA:+10.1%) | NVMe=518.1 MB/s (559451.09 MB) | RSS=13724.1 MB
[LIVE-DECODE] 6/64 tok | Avg=0.29 tps | Hit=90.5% (LA:+10.1%) | NVMe=517.5 MB/s (561876.02 MB) | RSS=13611.9 MB
[LIVE-DECODE] 8/64 tok | Avg=0.30 tps | Hit=90.5% (LA:+10.1%) | NVMe=516.8 MB/s (564281.71 MB) | RSS=13528.3 MB
[LIVE-DECODE] 10/64 tok | Avg=0.31 tps | Hit=90.5% (LA:+10.1%) | NVMe=516.3 MB/s (566481.52 MB) | RSS=13457.6 MB
[LIVE-DECODE] 12/64 tok | Avg=0.31 tps | Hit=90.5% (LA:+10.1%) | NVMe=515.8 MB/s (568721.90 MB) | RSS=13407.2 MB
[LIVE-DECODE] 14/64 tok | Avg=0.32 tps | Hit=90.5% (LA:+10.1%) | NVMe=515.3 MB/s (570885.27 MB) | RSS=13371.5 MB
[LIVE-DECODE] 16/64 tok | Avg=0.32 tps | Hit=90.5% (LA:+10.1%) | NVMe=514.9 MB/s (573146.27 MB) | RSS=13348.4 MB
[LIVE-DECODE] 18/64 tok | Avg=0.33 tps | Hit=90.5% (LA:+10.2%) | NVMe=514.5 MB/s (575463.46 MB) | RSS=13338.9 MB
[LIVE-DECODE] 20/64 tok | Avg=0.33 tps | Hit=90.5% (LA:+10.2%) | NVMe=514.1 MB/s (577730.59 MB) | RSS=13338.9 MB
[LIVE-DECODE] 22/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=513.8 MB/s (579842.52 MB) | RSS=13339.0 MB
[LIVE-DECODE] 24/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=513.4 MB/s (582107.34 MB) | RSS=13339.0 MB
[LIVE-DECODE] 26/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=512.9 MB/s (584416.27 MB) | RSS=13339.0 MB
[LIVE-DECODE] 28/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=512.6 MB/s (586716.15 MB) | RSS=13338.9 MB
[LIVE-DECODE] 30/64 tok | Avg=0.34 tps | Hit=90.5% (LA:+10.2%) | NVMe=512.2 MB/s (588846.90 MB) | RSS=13338.9 MB
[LIVE-DECODE] 32/64 tok | Avg=0.35 tps | Hit=90.5% (LA:+10.2%) | NVMe=511.8 MB/s (590979.15 MB) | RSS=13338.9 MB
[LIVE-DECODE] 34/64 tok | Avg=0.35 tps | Hit=90.5% (LA:+10.3%) | NVMe=511.5 MB/s (592939.77 MB) | RSS=13338.9 MB
[LIVE-DECODE] 36/64 tok | Avg=0.35 tps | Hit=90.5% (LA:+10.3%) | NVMe=511.2 MB/s (595126.65 MB) | RSS=13338.9 MB
[LIVE-DECODE] 38/64 tok | Avg=0.35 tps | Hit=90.5% (LA:+10.3%) | NVMe=510.9 MB/s (597077.15 MB) | RSS=13338.9 MB
[LIVE-DECODE] 40/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=510.6 MB/s (599033.21 MB) | RSS=13338.9 MB
[LIVE-DECODE] 42/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=510.3 MB/s (601050.59 MB) | RSS=13323.8 MB
[LIVE-DECODE] 44/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=510.1 MB/s (602953.52 MB) | RSS=13329.6 MB
[LIVE-DECODE] 46/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=509.8 MB/s (604945.96 MB) | RSS=13329.5 MB
[LIVE-DECODE] 48/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=509.4 MB/s (607197.40 MB) | RSS=13338.9 MB
[LIVE-DECODE] 50/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.3%) | NVMe=509.2 MB/s (609246.02 MB) | RSS=13338.9 MB
[LIVE-DECODE] 52/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.4%) | NVMe=508.8 MB/s (611688.52 MB) | RSS=13339.0 MB
[LIVE-DECODE] 54/64 tok | Avg=0.36 tps | Hit=90.4% (LA:+10.4%) | NVMe=508.5 MB/s (613804.15 MB) | RSS=13338.9 MB
[LIVE-DECODE] 56/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=508.2 MB/s (615731.02 MB) | RSS=13338.9 MB
[LIVE-DECODE] 58/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=507.9 MB/s (617751.59 MB) | RSS=13338.9 MB
[LIVE-DECODE] 60/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=507.6 MB/s (619804.09 MB) | RSS=13326.1 MB
[LIVE-DECODE] 62/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=507.3 MB/s (621916.21 MB) | RSS=13326.1 MB
[LIVE-DECODE] 64/64 tok | Avg=0.37 tps | Hit=90.4% (LA:+10.4%) | NVMe=507.0 MB/s (623873.90 MB) | RSS=13326.1 MB

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
   LRFU Cache / Staging Ring    : 5437.50 MB (580/12384 exp = 4.68% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.77 MB | End=13326.07 MB | Peak=14016.58 MB
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
   |    1 |    1550 |  high          |   25.48 | 100.0% |     279 |   13.45 | 2525827.05 |  0 |  0 |  0 |     0.0 |
   |    2 |   42503 | -through       |   27.04 | 100.0% |   63308 |   16.24 | 3074.62 |130 |110 | 96 | 1250272.0 |
   |    3 |     628 | put            |   23.73 |  99.6% |   19183 |   17.58 | 3074.62 |  0 |  0 |  0 | 1250272.0 |
   |    4 |   19183 |  Mix           |   17.39 |  84.5% |   19705 |   14.33 | 4061.76 | 39 |215 | 82 | 1502848.0 |
   |    5 |   18482 | tures          |   16.37 |  54.3% |      68 |   15.04 | 4061.76 |  0 |  0 |  0 | 1502848.0 |
   |    6 |     315 |  of            |   13.92 |  18.4% |    8667 |   13.83 | 3143.48 |107 |148 | 81 | 1241568.0 |
   |    7 |   19183 |  Mix           |   18.45 |  89.7% |   57687 |   15.44 | 3143.48 |  0 |  0 |  0 | 1241568.0 |
   |    8 |   18482 | tures          |   16.65 |  62.5% |    4974 |   14.96 | 3100.41 |119 |137 | 80 | 1231712.0 |
   |    9 |    8667 | -of            |   17.27 |  47.5% |     315 |   17.04 | 3100.41 |  0 |  0 |  0 | 1231712.0 |
   |   52 |   18547 |  dual          |   14.99 |  20.4% |   86025 |   14.43 | 2999.66 |106 |150 | 80 | 1250560.0 |
   |   53 |   86025 |  lookahead     |   13.07 |   7.8% |    9270 |   12.69 | 2999.66 |  0 |  0 |  0 | 1250560.0 |
   |   16 |    4128 |  language      |   16.00 |  39.8% |   81623 |   15.32 | 2906.31 |133 |135 | 68 | 1157632.0 |
   |   62 |   21984 |  RAM           |   16.11 |  41.3% |   33742 |   15.25 | 2586.77 |142 |117 | 77 | 1081408.0 |
   |   63 |    2041 |  without       |   15.58 |  48.8% |   28891 |   13.67 | 2586.77 |  0 |  0 |  0 | 1081408.0 |
   |   64 |   13931 |  CPU           |   16.17 |  32.7% |   11315 |   14.94 | 2417.90 |141 |143 | 52 | 1002336.0 |
   |   65 |   11315 |  execution     |   14.77 |  16.3% |   15289 |   14.61 | 2417.90 |  0 |  0 |  0 | 1002336.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2525.827s, TTFT=2525827.05ms): Avg=0.81 | Min=0.76 | Max=0.84 tps
   Prefill Chunks (8): C1:256t/0.8tps/91% | C2:256t/0.8tps/90% | C3:256t/0.8tps/90% | C4:256t/0.8tps/90%
                       C5:256t/0.8tps/90% | C6:256t/0.8tps/90% | C7:256t/0.8tps/91% | C8:256t/0.8tps/91%
   Decode  (64 tok, 173.000s): Avg=0.37 | Min=0.25 | Max=0.43 tps
   Latency (ms) : Min=2303.94 | P10=2364.77 | P25=2469.35 | P50=2660.03 | P75=2826.64 | P90=3074.62 | P95=3143.48 | P99=4061.76 | Max=4061.76
   Mean/SD/Jitt : Mean=2703.13ms | StdDev=336.29ms | Jitter=110.87ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (698880): RawRAM=558754 (79.95%) | Lookahead=72975 (+10.44%) | ColdMiss=67151 (9.61%) | EFF HIT=90.39%
   Lookahead    : 17281 prefetched -> 14258 consumed (82.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.5% | @64= 90.4% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |16640 |12360 |2282 |1998 | 88.0%|18723.44 | | L24 |16640 |13262 |1869 |1509 | 90.9%|13419.06 |
   | L04 |16640 |12490 |2193 |1957 | 88.2%|18033.44 | | L25 |16640 |13525 |1616 |1499 | 91.0%|13735.31 |
   | L05 |16640 |12598 |2103 |1939 | 88.3%|17882.50 | | L26 |16640 |13417 |1703 |1520 | 90.9%|13605.94 |
   | L06 |16640 |12668 |2071 |1901 | 88.6%|17710.00 | | L27 |16640 |13394 |1640 |1606 | 90.3%|14633.75 |
   | L07 |16640 |12979 |1926 |1735 | 89.6%|15755.00 | | L28 |16640 |13263 |1772 |1605 | 90.4%|14439.69 |
   | L08 |16640 |13223 |1627 |1790 | 89.2%|16143.12 | | L29 |16640 |13165 |1969 |1506 | 90.9%|13685.00 |
   | L09 |16640 |12982 |1874 |1784 | 89.3%|16121.56 | | L30 |16640 |13053 |1994 |1593 | 90.4%|14224.06 |
   | L10 |16640 |12738 |2046 |1856 | 88.8%|16905.00 | | L31 |16640 |13512 |1518 |1610 | 90.3%|14583.44 |
   | L11 |16640 |13148 |1915 |1577 | 90.5%|19031.25 | | L32 |16640 |13026 |1988 |1626 | 90.2%|14727.19 |
   | L12 |16640 |13202 |1886 |1552 | 90.7%|16582.50 | | L33 |16640 |13444 |1736 |1460 | 91.2%|13591.56 |
   | L13 |16640 |13535 |1667 |1438 | 91.4%|12908.75 | | L34 |16640 |13616 |1501 |1523 | 90.8%|13720.94 |
   | L14 |16640 |14198 |1091 |1351 | 91.9%|12276.25 | | L35 |16640 |13671 |1391 |1578 | 90.5%|14245.62 |
   | L15 |16640 |14341 |1049 |1250 | 92.5%|11500.00 | | L36 |16640 |13309 |1719 |1612 | 90.3%|14461.25 |
   | L16 |16640 |13860 |1376 |1404 | 91.6%|12700.31 | | L37 |16640 |13515 |1517 |1608 | 90.3%|14195.31 |
   | L17 |16640 |13570 |1526 |1544 | 90.7%|13792.81 | | L38 |16640 |13452 |1575 |1613 | 90.3%|14310.31 |
   | L18 |16640 |13785 |1408 |1447 | 91.3%|13002.19 | | L39 |16640 |13182 |1777 |1681 | 89.9%|14856.56 |
   | L19 |16640 |13542 |1609 |1489 | 91.1%|13059.69 | | L40 |16640 |13442 |1564 |1634 | 90.2%|14389.38 |
   | L20 |16640 |13304 |1818 |1518 | 90.9%|13526.88 | | L41 |16640 |13193 |1802 |1645 | 90.1%|14763.12 |
   | L21 |16640 |13667 |1546 |1427 | 91.4%|12880.00 | | L42 |16640 |13089 |1989 |1562 | 90.6%|13879.06 |
   | L22 |16640 |13245 |1943 |1452 | 91.3%|13088.44 | | L43 |16640 |13288 |1817 |1535 | 90.8%|13814.38 |
   | L23 |16640 |13377 |1738 |1525 | 90.8%|13656.25 | | L44 |16640 |13124 |1824 |1692 | 89.8%|17579.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 623873.90 MB (Load=6361.84 | Prefill=547712.06 | Warmup=0.00 | Decode=69800.00 MB)
   SSD Data/Token (Decode)      : Avg=1090.625 MB/tok (Min=951.469 | P50=1081.688 | P95=1221.250 | Max=1467.625 MB) | Prefill=267.438 MB/tok
   NVMe Batches / Requests      : 4908 Batches | 255053 Raw -> 251075 Merged (3978 LBA Merges, Avg 2544.4 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=250196
   SSD Read Bandwidth (Active)  : Min=0.46 | Avg=506.97 | Peak=3899.26 MB/s | WallAmort=231.16 MB/s
   OS Kernel I/O Verification   : Read=623882.93 MB | Write=0.01 MB | Syscalls=255134
   Sync Stall vs Async DMA      : SyncStall=894619.00 ms | AsyncOverlapped=1215680.46 ms (57.6% Overlapped)
   RAM Traffic & Active BW      : 7358.13 GB moved | Active=4.33 GB/s | WallAmort=2.73 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2525.83s (93.6%, 547712.06 MB SSD) | Decode=173.00s (6.4%, 69800.00 MB SSD)
   CPU Time & Utilization       : User=5863.281s + Sys=64.938s (Wall=2717.798s) | SysUtil=54.5% | ThrUtil=54.5% | 50.44 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 801347.95 ms (379426.1 us/tok | 29.69%)
   MoE AVX2 Q8 Expert Compute   : 894387.40 ms (423478.9 us/tok | 33.14%)
   Router + Lookahead Dispatch  :  15382.17 ms ( 7283.2 us/tok |  0.57%)
   LM Head Output Projection    :   1716.59 ms (  812.8 us/tok |  0.06%)
   Foreground NVMe Sync Stall   : 894619.00 ms (423588.5 us/tok | 33.15%)
   Unaccounted / OMP & Sampling :  91374.14 ms (43264.3 us/tok |  3.39%) | Total Wall=2698827.26 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    62.05%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    13.23%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    12.76%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    10.19%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.77%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_glm53_colibri_bench.log`
```text
=== [Colibri-GLM53] CMD: ./baselines/colibri/c/glm53.exe --model D:/apex_d_drive/models/glm53 --ids 1,8,15,22,29,36,43,50,57,64,71,78,85,92,99,106,113,120,127,134,141,148,155,162,169,176,183,190,197,204,211,218,225,232,239,246,253,260,267,274,281,288,295,302,309,316,323,330,337,344,351,358,365,372,379,386,393,400,407,414,421,428,435,442 --greedy 64 32 (5x cutoff=1195.0s) ===
[gguf] D:\apex_d_drive\models\glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: glm5-next, 4 part(s), 38435 tensors under the checkpoint's names (1283 renamed, 129 fused expert tensors split per expert, 0 kept as named), read in place
glm53: GGUF experts interleaved by 16 rows on 3 of 42 layers (G53_ILV16=0: the file's rows)
  [COMP-LIVE] Colibri-GLM53: elapsed=15.0s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=30.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=45.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=60.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=75.2s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=90.4s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=105.5s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=120.6s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=135.7s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=150.8s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=165.8s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=181.0s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=196.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=211.2s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=226.2s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=241.3s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=256.8s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=271.9s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=287.0s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=302.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=317.6s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=333.1s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=348.2s / cutoff=1195.0s
  [COMP-LIVE] Colibri-GLM53: elapsed=363.5s / cutoff=1195.0s
[STATS] 43008 selections across 6945 distinct experts -> D:/apex_d_drive/models/glm53/.coli_usage
teacher_forcing 5556 335 11 15 15 22 22 22 22 36 57 22 36 64 9 154850 154850 154850 123 121 127967 127501 243 104 253 237 154842 1986 197 220 220 0 220 154827 154827 154827 154827 220 83 220 274 220 220 274 295 83 279 8 220 1 1 2776 72 83 84 365 13 220 220 220 320 83 220 220
greedy 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330 220 330
decode 64 token in 246.0s = 0.260 tok/s (3.8 s/token)
experts hits 15425 miss 11249 bytes 111319384064
=== [Colibri-GLM53] Finished rc=0 elapsed=378.15s cancelled=False ===
```

### 📄 `12_glm53_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] GLM53 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 0.49 | 0.37 | 2697.57 | 77.60% | 456.57 | 13844.00 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 0.83 | 0.39 | 2471.21 | 89.19% | 466.38 | 14184.51 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 0.81 | 0.37 | 2660.03 | 90.39% | 506.97 | 14016.58 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.260 | - | 57.8% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
