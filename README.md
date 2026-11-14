<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#26 (Run ID `43563684564`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43563684564)
- **Status**: **CANCELLED**
- **Timestamp**: `2026-11-14 06:31:21 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T05:53:38.628Z] ================================================================================
[2026-11-14T05:53:38.648Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T05:53:38.649Z] ================================================================================
[2026-11-14T05:53:43.930Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T05:53:44.132Z] --------------------------------------------------------------------------------
[2026-11-14T05:53:44.133Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 30.98 GB / 149.89 GB
[2026-11-14T05:53:44.135Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-14T05:53:44.136Z]  [Disk Telemetry] Total Combined Usable Free Space: 177.99 GB
[2026-11-14T05:53:44.150Z] --------------------------------------------------------------------------------
[2026-11-14T05:53:44.152Z]  [OK] Disk space verification passed: 177.99 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 05:54 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 05:54 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.52 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    512.92 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1475.58 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7887.50 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10339.17 MB/s
   RND4K Q32T16 Read                  :    443.37 MB/s (  113502 IOPS)
   RND4K Q1T1  Read                   :    694.57 MB/s (Latency: 5.62 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     65.51 GB/s
   AVX2 256-bit Sequential Write BW   :     46.71 GB/s
   STREAM Triad (A = B + s*C) BW      :     19.42 GB/s
   Random Pointer-Chase Latency       :     54.94 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.33 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    181.88 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.79 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1429.03 tps | Avg=1429.03 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=73.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1211.18 tps | Avg=1311.12 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=73.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1070.55 tps | Avg=1219.75 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=74.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=988.87 tps | Avg=1152.48 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=74.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=871.39 tps | Avg=1082.63 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=74.7 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=816.94 tps | Avg=1026.97 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=74.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=748.41 tps | Avg=975.12 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=75.2 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=693.30 tps | Avg=927.97 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=75.5 MB
[LIVE-DECODE] 8/32 tok | Avg=195.72 tps | Hit=100.0% (LA:+0.0%) | NVMe=2549.0 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 16/32 tok | Avg=196.63 tps | Hit=100.0% (LA:+0.0%) | NVMe=2549.0 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 24/32 tok | Avg=196.87 tps | Hit=100.0% (LA:+0.0%) | NVMe=2549.0 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 32/32 tok | Avg=197.00 tps | Hit=100.0% (LA:+0.0%) | NVMe=2549.0 MB/s (6.58 MB) | RSS=75.5 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=75.50 MB | Peak=75.50 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2206.97 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.14 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.14 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.10 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.10 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.06 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.06 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.14 | 12 |  0 |  0 |     0.0 |
   |    9 |      68 | tok_68         |  176.71 | 100.0% |     228 |  144.43 |    5.14 |  0 |  0 |  0 |     0.0 |
   |   24 |     246 | tok_246        |  204.37 |  99.2% |      55 |  199.55 |    5.13 | 12 |  0 |  0 |     0.0 |
   |   25 |     229 | tok_229        |  171.20 | 100.0% |      70 |  154.08 |    5.13 |  0 |  0 |  0 |     0.0 |
   |   26 |     246 | tok_246        |  195.41 | 100.0% |      54 |  174.46 |    5.12 | 12 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.10 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.10 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.02 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.02 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.207s, TTFT=2206.97ms): Avg=927.97 | Min=693.30 | Max=1429.03 tps
   Prefill Chunks (8): C1:256t/1429.0tps/100% | C2:256t/1211.2tps/100% | C3:256t/1070.5tps/100% | C4:256t/988.9tps/100%
                       C5:256t/871.4tps/100% | C6:256t/816.9tps/100% | C7:256t/748.4tps/100% | C8:256t/693.3tps/100%
   Decode  (32 tok, 0.162s): Avg=197.00 | Min=194.38 | Max=199.67 tps
   Latency (ms) : Min=5.01 | P10=5.01 | P25=5.03 | P50=5.09 | P75=5.12 | P90=5.14 | P95=5.14 | P99=5.14 | Max=5.14
   Mean/SD/Jitt : Mean=5.08ms | StdDev=0.05ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=364.55 | Avg=2548.96 | Peak=6188.12 MB/s | WallAmort=2.78 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=1.25 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.64 GB/s | WallAmort=0.60 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.21s (93.1%, 0.00 MB SSD) | Decode=0.16s (6.9%, 0.00 MB SSD)
   CPU Time & Utilization       : User=3.062s + Sys=0.703s (Wall=2.388s) | SysUtil=39.4% | ThrUtil=39.4% | 36.46 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1996.49 ms (  959.9 us/tok | 84.26%)
   MoE AVX2 Q8 Expert Compute   :    247.69 ms (  119.1 us/tok | 10.45%)
   Router + Lookahead Dispatch  :     60.18 ms (   28.9 us/tok |  2.54%)
   LM Head Output Projection    :      5.98 ms (    2.9 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     59.08 ms (   28.4 us/tok |  2.49%) | Total Wall=2369.41 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    16.53%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.16%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.10%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    79.20%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.01%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1924.28 tps | Avg=1924.28 tps | Hit=99.2% | NVMe=2807.5 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1719.68 tps | Avg=1816.23 tps | Hit=99.2% | NVMe=3721.3 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1759.27 tps | Avg=1796.84 tps | Hit=99.2% | NVMe=4302.8 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1651.71 tps | Avg=1758.22 tps | Hit=99.2% | NVMe=4699.2 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1549.18 tps | Avg=1712.02 tps | Hit=99.2% | NVMe=4988.2 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1359.47 tps | Avg=1641.09 tps | Hit=99.2% | NVMe=5192.5 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1358.47 tps | Avg=1593.72 tps | Hit=99.2% | NVMe=5380.6 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1239.34 tps | Avg=1538.72 tps | Hit=99.2% | NVMe=5567.0 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=171.50 tps | Hit=99.2% (LA:+0.0%) | NVMe=5463.0 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=174.73 tps | Hit=99.2% (LA:+0.1%) | NVMe=5404.3 MB/s (153.28 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=175.98 tps | Hit=99.2% (LA:+0.1%) | NVMe=5299.3 MB/s (154.23 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=176.67 tps | Hit=99.2% (LA:+0.1%) | NVMe=5220.7 MB/s (155.14 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=91.76 MB | Peak=91.76 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1330.97 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    5.90 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    5.90 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    5.88 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    5.88 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    5.85 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    5.85 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    5.70 | 16 |  0 |  0 |    32.0 |
   |    9 |      49 | qtok_49        |   84.72 | 100.0% |     129 |   76.64 |    5.70 |  0 |  0 |  0 |    32.0 |
   |   24 |     128 | qtok_128       |   60.98 |  67.3% |     194 |   60.03 |    5.70 | 13 |  3 |  0 |   115.2 |
   |   25 |      63 | qtok_63        |  124.60 | 100.0% |      19 |   87.54 |    5.70 |  0 |  0 |  0 |   115.2 |
   |   16 |     223 | qtok_223       |   65.44 |  87.6% |     159 |   63.48 |    5.68 | 15 |  1 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.55 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.55 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.59 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.59 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.331s, TTFT=1330.97ms): Avg=1538.72 | Min=1239.34 | Max=1924.28 tps
   Prefill Chunks (8): C1:256t/1924.3tps/99% | C2:256t/1719.7tps/99% | C3:256t/1759.3tps/99% | C4:256t/1651.7tps/99%
                       C5:256t/1549.2tps/99% | C6:256t/1359.5tps/99% | C7:256t/1358.5tps/99% | C8:256t/1239.3tps/99%
   Decode  (32 tok, 0.181s): Avg=176.67 | Min=169.48 | Max=180.26 tps
   Latency (ms) : Min=5.55 | P10=5.56 | P25=5.58 | P50=5.63 | P75=5.70 | P90=5.88 | P95=5.90 | P99=5.90 | Max=5.90
   Mean/SD/Jitt : Mean=5.66ms | StdDev=0.11ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=223.32 | Avg=5220.67 | Peak=10810.46 MB/s | WallAmort=102.60 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=6.73 ms | AsyncOverlapped=28.12 ms (80.7% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.59 GB/s | WallAmort=1.39 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.33s (88.0%, 144.44 MB SSD) | Decode=0.18s (12.0%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.734s + Sys=0.328s (Wall=1.542s) | SysUtil=49.7% | ThrUtil=49.7% | 45.94 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    936.90 ms (  450.4 us/tok | 61.96%)
   MoE AVX2 Q8 Expert Compute   :    376.17 ms (  180.9 us/tok | 24.88%)
   Router + Lookahead Dispatch  :     80.03 ms (   38.5 us/tok |  5.29%)
   LM Head Output Projection    :      5.91 ms (    2.8 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :      6.73 ms (    3.2 us/tok |  0.45%)
   Unaccounted / OMP & Sampling :    106.37 ms (   51.1 us/tok |  7.03%) | Total Wall=1512.10 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    17.99%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.78%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.94%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    69.84%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.45%  |
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
    "ttft_ms": 236.15,
    "avg_tps": 694.48,
    "min_tps": 571.51,
    "max_tps": 777.75
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 143.39,
    "min_tps": 127.3,
    "max_tps": 147.99,
    "p50_ms": 6.88,
    "p90_ms": 7.4,
    "p99_ms": 7.86,
    "mean_ms": 6.97,
    "jitter_ms": 0.14
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
    "avg_mbs": 2246.34,
    "peak_mbs": 5703.82,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.92
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
    "dense_attention": 379.83,
    "moe_compute": 105.32,
    "router_lookahead": 7.52,
    "lm_head": 8.99,
    "unaccounted": 6.47
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 86.96,
    "ram_bandwidth_pinning": 1.92,
    "expert_cache_lrfu": 9.23,
    "lookahead_parallel_overlap": 1.49,
    "ssd_nvme_throughput": 0.4,
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
    "ttft_ms": 307.91,
    "avg_tps": 532.63,
    "min_tps": 386.75,
    "max_tps": 615.35
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 124.42,
    "min_tps": 98.17,
    "max_tps": 130.98,
    "p50_ms": 7.84,
    "p90_ms": 9.35,
    "p99_ms": 10.19,
    "mean_ms": 8.04,
    "jitter_ms": 0.23
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
    "avg_mbs": 2558.78,
    "peak_mbs": 8246.23,
    "sync_wait_ms": 4.69,
    "async_overlap_ms": 12.97
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
    "dense_attention": 351.68,
    "moe_compute": 204.1,
    "router_lookahead": 9.36,
    "lm_head": 8.81,
    "unaccounted": 42.74
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.06,
    "ram_bandwidth_pinning": 2.13,
    "expert_cache_lrfu": 8.54,
    "lookahead_parallel_overlap": 4.53,
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
   System Memory (RAM): 15.99 GB Total / 13.41 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    623.23 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1461.02 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7874.31 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10417.39 MB/s
   RND4K Q32T16 Read                  :    480.53 MB/s (  123016 IOPS)
   RND4K Q1T1  Read                   :    668.14 MB/s (Latency: 5.85 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     60.15 GB/s
   AVX2 256-bit Sequential Write BW   :     46.37 GB/s
   STREAM Triad (A = B + s*C) BW      :     40.97 GB/s
   Random Pointer-Chase Latency       :     64.00 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.41 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    100.13 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     20.52 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 30.99 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 166.49 MB/s (6.15s)
   Window #01 (304.0 MB in 0.50s):   605.95 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   391.90 MB/s (Uncached Direct Read)
   Window #03 ( 88.0 MB in 0.69s):   127.74 MB/s (Uncached Direct Read)
   Window #04 ( 88.0 MB in 0.52s):   168.27 MB/s (Uncached Direct Read)
   Window #05 ( 20.0 MB in 0.97s):    20.72 MB/s (Uncached Direct Read)
   Window #06 ( 56.0 MB in 0.57s):    98.22 MB/s (Uncached Direct Read)
   Window #07 ( 28.0 MB in 0.75s):    37.54 MB/s (Uncached Direct Read)
   Window #08 ( 12.0 MB in 0.57s):    20.98 MB/s (Uncached Direct Read)
   Window #09 ( 72.0 MB in 0.52s):   138.02 MB/s (Uncached Direct Read)
   Window #10 (156.0 MB in 0.50s):   311.23 MB/s (Uncached Direct Read)
   Window #11 (  4.0 MB in 0.00s):   920.24 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   168.03 MB/s (Min=20.72 | Max=920.24 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 351.61 MB/s (2.91s)
   Window #01 (196.0 MB in 0.50s):   390.01 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   388.14 MB/s (Uncached Direct Read)
   Window #03 (216.0 MB in 0.54s):   401.77 MB/s (Uncached Direct Read)
   Window #04 (196.0 MB in 0.51s):   386.72 MB/s (Uncached Direct Read)
   Window #05 (196.0 MB in 0.51s):   387.98 MB/s (Uncached Direct Read)
   Window #06 ( 24.0 MB in 0.05s):   482.12 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   392.79 MB/s (Min=386.72 | Max=482.12 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: glm53 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (0.009 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: 100.00% (0.01/0.01 GB) @ 53.1 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (46.470 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  10.76% (5.00/46.47 GB) @ 474.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  21.52% (10.00/46.47 GB) @ 351.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  32.28% (15.00/46.47 GB) @ 344.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  43.04% (20.00/46.47 GB) @ 349.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  53.80% (25.00/46.47 GB) @ 320.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  64.56% (30.00/46.47 GB) @ 320.2 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  75.32% (35.00/46.47 GB) @ 314.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  86.08% (40.00/46.47 GB) @ 309.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  96.84% (45.00/46.47 GB) @ 298.7 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf: 100.00% (46.47/46.47 GB) @ 294.5 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (45.866 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  10.90% (5.00/45.87 GB) @ 347.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  21.80% (10.00/45.87 GB) @ 342.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  32.70% (15.00/45.87 GB) @ 308.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  43.61% (20.00/45.87 GB) @ 314.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  54.51% (25.00/45.87 GB) @ 300.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  65.41% (30.00/45.87 GB) @ 301.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  76.31% (35.00/45.87 GB) @ 298.5 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  87.21% (40.00/45.87 GB) @ 302.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  98.11% (45.00/45.87 GB) @ 276.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf: 100.00% (45.87/45.87 GB) @ 278.9 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (2.506 GB) -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf: 100.00% (2.51/2.51 GB) @ 19.9 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=101,844,951,904 (94.85 GB) | Elapsed=462.42s
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
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5221.88 MB (557 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.51 tps | Avg=0.51 tps | Hit=76.5% | NVMe=489.0 MB/s (47437.59 MB, QD=64) | RSS=13620.2 MB
[LIVE-DECODE] 2/32 tok | Avg=0.24 tps | Hit=76.5% (LA:+10.1%) | NVMe=483.8 MB/s (50577.40 MB) | RSS=13555.0 MB
[LIVE-DECODE] 4/32 tok | Avg=0.28 tps | Hit=76.5% (LA:+10.8%) | NVMe=478.9 MB/s (52976.40 MB) | RSS=13462.8 MB
[LIVE-DECODE] 6/32 tok | Avg=0.28 tps | Hit=76.6% (LA:+11.5%) | NVMe=475.0 MB/s (55522.65 MB) | RSS=13378.8 MB
[LIVE-DECODE] 8/32 tok | Avg=0.31 tps | Hit=76.7% (LA:+12.1%) | NVMe=473.2 MB/s (57549.34 MB) | RSS=13359.6 MB
[LIVE-DECODE] 10/32 tok | Avg=0.32 tps | Hit=76.8% (LA:+12.6%) | NVMe=471.3 MB/s (59675.02 MB) | RSS=13314.5 MB
[LIVE-DECODE] 12/32 tok | Avg=0.32 tps | Hit=77.0% (LA:+13.3%) | NVMe=468.9 MB/s (61945.09 MB) | RSS=13254.1 MB
[LIVE-DECODE] 14/32 tok | Avg=0.33 tps | Hit=77.1% (LA:+13.8%) | NVMe=467.9 MB/s (63947.96 MB) | RSS=13234.8 MB
[LIVE-DECODE] 16/32 tok | Avg=0.35 tps | Hit=77.2% (LA:+14.0%) | NVMe=467.5 MB/s (65593.34 MB) | RSS=13226.8 MB
[LIVE-DECODE] 18/32 tok | Avg=0.35 tps | Hit=77.3% (LA:+14.6%) | NVMe=466.2 MB/s (68065.84 MB) | RSS=13181.0 MB
[LIVE-DECODE] 20/32 tok | Avg=0.35 tps | Hit=77.4% (LA:+15.1%) | NVMe=464.4 MB/s (70194.46 MB) | RSS=13132.0 MB
[LIVE-DECODE] 22/32 tok | Avg=0.35 tps | Hit=77.4% (LA:+15.5%) | NVMe=463.2 MB/s (72230.27 MB) | RSS=13121.9 MB
[LIVE-DECODE] 24/32 tok | Avg=0.35 tps | Hit=77.5% (LA:+15.9%) | NVMe=461.9 MB/s (74543.46 MB) | RSS=13121.9 MB
[LIVE-DECODE] 26/32 tok | Avg=0.35 tps | Hit=77.5% (LA:+16.3%) | NVMe=461.0 MB/s (76723.77 MB) | RSS=13121.9 MB
[LIVE-DECODE] 28/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+16.5%) | NVMe=459.9 MB/s (78868.71 MB) | RSS=13121.9 MB
[LIVE-DECODE] 30/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+16.8%) | NVMe=459.3 MB/s (80921.02 MB) | RSS=13121.9 MB
[LIVE-DECODE] 32/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+17.0%) | NVMe=459.0 MB/s (82851.65 MB) | RSS=13121.9 MB

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
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13121.93 MB | Peak=13698.61 MB
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
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 126246.70 |  0 |  0 |  0 |     0.0 |
   |    2 |     220 |                |   14.20 |   9.2% |   24923 |   14.18 | 4100.87 | 19 |229 | 88 | 1607584.0 |
   |    3 |      16 | 1              |   18.33 |  26.6% |      19 |   17.27 | 4100.87 |  0 |  0 |  0 | 1607584.0 |
   |    4 |   15245 | -bit           |   13.67 |  13.4% |      13 |   13.56 | 3160.53 | 79 |194 | 63 | 1228288.0 |
   |    5 |    1112 | ...            |   13.59 |   8.9% |    1565 |   13.29 | 3160.53 |  0 |  0 |  0 | 1228288.0 |
   |    6 |    4398 |  More          |   11.74 |   8.2% |     508 |   10.90 | 3271.49 | 73 |199 | 64 | 1303680.0 |
   |    7 |     198 | \n             |   11.62 |   6.7% |     271 |   11.49 | 3271.49 |  0 |  0 |  0 | 1303680.0 |
   |    8 |      58 | [              |   13.68 |   7.4% |     785 |   13.10 | 2485.52 |121 |167 | 48 | 1037664.0 |
   |   18 |      16 | 1              |   14.79 |  37.1% |       8 |   12.48 | 3202.50 | 86 |184 | 66 | 1265920.0 |
   |   19 |   15245 | -bit           |   24.00 |  99.8% |    1455 |   16.07 | 3202.50 |  0 |  0 |  0 | 1265920.0 |
   |   12 |   21265 |  highlights    |   11.86 |  14.3% |    7998 |   11.70 | 2879.59 | 94 |196 | 46 | 1162272.0 |
   |   13 |   88737 | ???\n          |   14.28 |  12.8% |    9335 |   14.26 | 2879.59 |  0 |  0 |  0 | 1162272.0 |
   |   30 |    1506 | ized           |   16.47 |  78.5% |   10267 |   12.96 | 2479.86 |136 |128 | 72 | 1050784.0 |
   |   31 |     220 |                |   19.68 |  90.4% |      16 |   16.01 | 2479.86 |  0 |  0 |  0 | 1050784.0 |
   |   32 |      16 | 1              |   15.37 |  33.8% |      19 |   14.89 | 2272.92 |153 |113 | 70 | 988480.0 |
   |   33 |   15245 | -bit           |   25.55 | 100.0% |    1455 |   16.54 | 2272.92 |  0 |  0 |  0 | 988480.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 126.247s, TTFT=126246.70ms): Avg=0.51 | Min=0.51 | Max=0.51 tps
   Prefill Chunks (1): C1:64t/0.5tps/77%
   Decode  (32 tok, 88.203s): Avg=0.36 | Min=0.24 | Max=0.52 tps
   Latency (ms) : Min=1929.97 | P10=2272.92 | P25=2485.52 | P50=2645.20 | P75=3160.53 | P90=3271.49 | P95=4100.87 | P99=4100.87 | Max=4100.87
   Mean/SD/Jitt : Mean=2756.35ms | StdDev=485.05ms | Jitter=194.10ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=16266 (60.51%) | Lookahead=4571 (+17.01%) | ColdMiss=6043 (22.48%) | EFF HIT=77.52%
   Lookahead    : 4329 prefetched -> 3172 consumed (73.3% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 77.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  290 |  92 | 258 | 59.7%|2910.94 | | L24 |  640 |  442 |  74 | 124 | 80.6%|1473.44 |
   | L04 |  640 |  289 | 128 | 223 | 65.2%|2724.06 | | L25 |  640 |  409 |  97 | 134 | 79.1%|1681.88 |
   | L05 |  640 |  267 | 155 | 218 | 65.9%|2623.44 | | L26 |  640 |  430 | 101 | 109 | 83.0%|1437.50 |
   | L06 |  640 |  315 | 139 | 186 | 70.9%|2285.62 | | L27 |  640 |  411 | 100 | 129 | 79.8%|1602.81 |
   | L07 |  640 |  353 | 137 | 150 | 76.6%|1983.75 | | L28 |  640 |  403 | 105 | 132 | 79.4%|1653.12 |
   | L08 |  640 |  332 | 143 | 165 | 74.2%|2041.25 | | L29 |  640 |  384 | 118 | 138 | 78.4%|1760.94 |
   | L09 |  640 |  288 | 165 | 187 | 70.8%|2235.31 | | L30 |  640 |  395 | 104 | 141 | 78.0%|1660.31 |
   | L10 |  640 |  305 | 148 | 187 | 70.8%|2242.50 | | L31 |  640 |  382 | 117 | 141 | 78.0%|1732.19 |
   | L11 |  640 |  392 |  95 | 153 | 76.1%|2465.62 | | L32 |  640 |  358 | 146 | 136 | 78.8%|1796.88 |
   | L12 |  640 |  354 | 139 | 147 | 77.0%|2211.00 | | L33 |  640 |  375 | 134 | 131 | 79.5%|1588.44 |
   | L13 |  640 |  400 |  91 | 149 | 76.7%|1768.12 | | L34 |  640 |  430 |  94 | 116 | 81.9%|1487.81 |
   | L14 |  640 |  424 |  68 | 148 | 76.9%|1696.25 | | L35 |  640 |  374 | 139 | 127 | 80.2%|1588.44 |
   | L15 |  640 |  426 |  69 | 145 | 77.3%|1703.44 | | L36 |  640 |  354 | 153 | 133 | 79.2%|1645.94 |
   | L16 |  640 |  421 |  91 | 128 | 80.0%|1681.88 | | L37 |  640 |  382 | 120 | 138 | 78.4%|1861.56 |
   | L17 |  640 |  427 |  79 | 134 | 79.1%|1660.31 | | L38 |  640 |  405 | 104 | 131 | 79.5%|1610.00 |
   | L18 |  640 |  446 |  72 | 122 | 80.9%|1516.56 | | L39 |  640 |  402 | 110 | 128 | 80.0%|1602.81 |
   | L19 |  640 |  441 |  80 | 119 | 81.4%|1509.38 | | L40 |  640 |  418 |  91 | 131 | 79.5%|1552.50 |
   | L20 |  640 |  428 |  79 | 133 | 79.2%|1610.00 | | L41 |  640 |  407 |  93 | 140 | 78.1%|1703.44 |
   | L21 |  640 |  450 |  73 | 117 | 81.7%|1437.50 | | L42 |  640 |  361 | 158 | 121 | 81.1%|1459.06 |
   | L22 |  640 |  452 |  71 | 117 | 81.7%|1430.31 | | L43 |  640 |  422 | 108 | 110 | 82.8%|1523.75 |
   | L23 |  640 |  422 |  83 | 135 | 78.9%|1588.44 | | L44 |  640 |  400 | 108 | 132 | 79.4%|1968.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 82851.65 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=35414.06 MB)
   SSD Data/Token (Decode)      : Avg=1106.689 MB/tok (Min=822.688 | P50=1072.469 | P95=1569.906 | Max=1569.906 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1390 Batches | 32666 Raw -> 32192 Merged (474 LBA Merges, Avg 2635.4 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=31313
   SSD Read Bandwidth (Active)  : Min=0.49 | Avg=459.03 | Peak=3585.77 MB/s | WallAmort=386.35 MB/s
   OS Kernel I/O Verification   : Read=82860.68 MB | Write=0.00 MB | Syscalls=36228
   Sync Stall vs Async DMA      : SyncStall=89908.70 ms | AsyncOverlapped=165853.72 ms (64.8% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=6.31 GB/s | WallAmort=2.27 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=126.25s (58.9%, 41075.75 MB SSD) | Decode=88.20s (41.1%, 35414.06 MB SSD)
   CPU Time & Utilization       : User=240.328s + Sys=8.922s (Wall=233.047s) | SysUtil=26.7% | ThrUtil=26.7% | 24.73 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  31189.18 ms (324887.3 us/tok | 14.54%)
   MoE AVX2 Q8 Expert Compute   :  45292.54 ms (471797.2 us/tok | 21.12%)
   Router + Lookahead Dispatch  :    662.35 ms ( 6899.4 us/tok |  0.31%)
   LM Head Output Projection    :    842.50 ms ( 8776.0 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :  89908.70 ms (936549.0 us/tok | 41.93%)
   Unaccounted / OMP & Sampling :  46554.50 ms (484942.7 us/tok | 21.71%) | Total Wall=214449.76 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    35.57%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    25.11%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    28.95%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.28%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.09%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 235s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 13.45 GB Available
   Active Drive Space : 150.00 GB Total / 54.59 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    533.17 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1520.60 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8000.65 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10394.88 MB/s
   RND4K Q32T16 Read                  :    469.59 MB/s (  120214 IOPS)
   RND4K Q1T1  Read                   :    690.61 MB/s (Latency: 5.66 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     38.97 GB/s
   AVX2 256-bit Sequential Write BW   :     30.62 GB/s
   STREAM Triad (A = B + s*C) BW      :     38.51 GB/s
   Random Pointer-Chase Latency       :     73.85 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.00 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    194.94 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.14 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.51 tps | Avg=0.51 tps | Hit=76.8% | NVMe=481.7 MB/s (51661.71 MB, QD=64) | RSS=13958.1 MB

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
   LRFU Cache / Staging Ring    : 5550.00 MB (592/12384 exp = 4.78% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.68 MB | End=13421.96 MB | Peak=14027.79 MB
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
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 137994.74 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   18.90 |  53.4% |   15724 |   18.74 | 3884.79 | 20 |233 | 83 | 1537696.0 |
   |    3 |     397 | >\n            |   12.80 |   6.2% |     318 |   12.73 | 3884.79 |  0 |  0 |  0 | 1537696.0 |
   |    4 |   13699 | <th            |   14.70 |  18.4% |     334 |   14.61 | 2735.48 |148 |121 | 67 | 1037568.0 |
   |    5 |     766 | ink            |   22.04 |  99.6% |     307 |   14.17 | 2735.48 |  0 |  0 |  0 | 1037568.0 |
   |    6 |     397 | >\n            |   12.54 |  13.7% |      29 |   12.50 | 2646.30 |137 |139 | 60 | 1030432.0 |
   |    7 |   13699 | <th            |   16.29 |  41.2% |     522 |   16.02 | 2646.30 |  0 |  0 |  0 | 1030432.0 |
   |    8 |     397 | >\n            |   17.08 |  39.3% |    1339 |   16.33 | 1982.20 |195 | 98 | 43 | 770464.0 |
   |   36 |   29136 |  Gate          |   15.35 |  36.3% |     479 |   14.86 | 3189.80 | 84 |162 | 90 | 1315072.0 |
   |   37 |    3170 |  why           |   16.44 |  65.8% |   34464 |   13.18 | 3189.80 |  0 |  0 |  0 | 1315072.0 |
   |   22 |     264 |  a             |   18.05 |  79.7% |     458 |   15.32 | 2910.97 |103 |178 | 55 | 1195328.0 |
   |   23 |    3405 |  question      |   16.11 |  14.3% |    1681 |   15.86 | 2910.97 |  0 |  0 |  0 | 1195328.0 |
   |   62 |   24384 |  NV            |   15.58 |  36.6% |   50665 |   15.35 | 2348.78 |147 |129 | 60 | 996928.0 |
   |   63 |   50665 |  sequential    |   14.36 |  20.5% |   25372 |   14.09 | 2348.78 |  0 |  0 |  0 | 996928.0 |
   |   64 |   24384 |  NV            |   17.08 |  41.8% |   25372 |   17.00 | 2300.07 |165 |111 | 60 | 953664.0 |
   |   65 |   25372 |  DMA           |   17.65 |  62.3% |   81911 |   16.44 | 2300.07 |  0 |  0 |  0 | 953664.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 137.995s, TTFT=137994.74ms): Avg=0.51 | Min=0.51 | Max=0.51 tps
   Prefill Chunks (1): C1:70t/0.5tps/77%
   Decode  (64 tok, 166.431s): Avg=0.38 | Min=0.26 | Max=0.52 tps
   Latency (ms) : Min=1917.55 | P10=1995.65 | P25=2518.26 | P50=2640.94 | P75=2727.80 | P90=2824.42 | P95=3189.80 | P99=3884.79 | Max=3884.79
   Mean/SD/Jitt : Mean=2600.48ms | StdDev=360.01ms | Jitter=119.73ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=20241 (59.06%) | Lookahead=6547 (+19.10%) | ColdMiss=7484 (21.84%) | EFF HIT=78.16%
   Lookahead    : 7730 prefetched -> 5083 consumed (65.8% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 77.5% | @64= 78.2% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  347 | 143 | 326 | 60.0%|4348.44 | | L24 |  816 |  477 | 196 | 143 | 82.5%|2091.56 |
   | L04 |  816 |  335 | 186 | 295 | 63.8%|3981.88 | | L25 |  816 |  544 | 121 | 151 | 81.5%|2264.06 |
   | L05 |  816 |  341 | 215 | 260 | 68.1%|3687.19 | | L26 |  816 |  508 | 160 | 148 | 81.9%|2041.25 |
   | L06 |  816 |  370 | 221 | 225 | 72.4%|3435.62 | | L27 |  816 |  527 | 115 | 174 | 78.7%|2501.25 |
   | L07 |  816 |  419 | 205 | 192 | 76.5%|2918.12 | | L28 |  816 |  464 | 168 | 184 | 77.5%|2680.94 |
   | L08 |  816 |  398 | 196 | 222 | 72.8%|3320.62 | | L29 |  816 |  499 | 155 | 162 | 80.1%|2314.38 |
   | L09 |  816 |  399 | 185 | 232 | 71.6%|3234.38 | | L30 |  816 |  471 | 168 | 177 | 78.3%|2494.06 |
   | L10 |  816 |  365 | 231 | 220 | 73.0%|3234.38 | | L31 |  816 |  499 | 138 | 179 | 78.1%|2609.06 |
   | L11 |  816 |  458 | 164 | 194 | 76.2%|3646.88 | | L32 |  816 |  497 | 140 | 179 | 78.1%|2688.12 |
   | L12 |  816 |  477 | 160 | 179 | 78.1%|3123.88 | | L33 |  816 |  514 | 144 | 158 | 80.6%|2443.75 |
   | L13 |  816 |  522 | 113 | 181 | 77.8%|2508.44 | | L34 |  816 |  518 | 144 | 154 | 81.1%|2400.62 |
   | L14 |  816 |  473 | 153 | 190 | 76.7%|2839.06 | | L35 |  816 |  508 | 157 | 151 | 81.5%|2343.12 |
   | L15 |  816 |  516 | 123 | 177 | 78.3%|2515.62 | | L36 |  816 |  500 | 166 | 150 | 81.6%|2386.25 |
   | L16 |  816 |  458 | 173 | 185 | 77.3%|2637.81 | | L37 |  816 |  481 | 179 | 156 | 80.9%|2364.69 |
   | L17 |  816 |  463 | 175 | 178 | 78.2%|2666.56 | | L38 |  816 |  548 | 128 | 140 | 82.8%|2141.88 |
   | L18 |  816 |  567 |  97 | 152 | 81.4%|2098.75 | | L39 |  816 |  513 | 157 | 146 | 82.1%|2271.25 |
   | L19 |  816 |  547 | 112 | 157 | 80.8%|2134.69 | | L40 |  816 |  485 | 167 | 164 | 79.9%|2515.62 |
   | L20 |  816 |  590 |  88 | 138 | 83.1%|1911.88 | | L41 |  816 |  466 | 188 | 162 | 80.1%|2515.62 |
   | L21 |  816 |  566 | 103 | 147 | 82.0%|2127.50 | | L42 |  816 |  517 | 149 | 150 | 81.6%|2256.88 |
   | L22 |  816 |  548 | 131 | 137 | 83.2%|1998.12 | | L43 |  816 |  522 | 147 | 147 | 82.0%|2105.94 |
   | L23 |  816 |  550 | 116 | 150 | 81.6%|2062.81 | | L44 |  816 |  474 | 170 | 172 | 78.9%|3241.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 118569.21 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=66907.50 MB)
   SSD Data/Token (Decode)      : Avg=1045.430 MB/tok (Min=752.406 | P50=1067.969 | P95=1284.250 | Max=1501.656 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2672 Batches | 47306 Raw -> 46686 Merged (620 LBA Merges, Avg 2600.7 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=45807
   SSD Read Bandwidth (Active)  : Min=0.49 | Avg=447.60 | Peak=3846.05 MB/s | WallAmort=389.49 MB/s (100.0% of 533.2 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=119556.24 MB | Write=128.00 MB | Syscalls=58260
   Sync Stall vs Async DMA      : SyncStall=116176.52 ms | AsyncOverlapped=250190.13 ms (68.3% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=7.48 GB/s (19.4% STREAM) | WallAmort=2.55 GB/s (Max=38.51 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=137.99s (45.3%, 45299.88 MB SSD) | Decode=166.43s (54.7%, 66907.50 MB SSD)
   CPU Time & Utilization       : User=316.672s + Sys=11.984s (Wall=324.025s) | SysUtil=25.4% | ThrUtil=25.4% | 49.43 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  40222.14 ms (300165.2 us/tok | 13.21%)
   MoE AVX2 Q8 Expert Compute   :  62010.34 ms (462763.8 us/tok | 20.37%)
   Router + Lookahead Dispatch  :    855.89 ms ( 6387.3 us/tok |  0.28%)
   LM Head Output Projection    :   1725.31 ms (12875.5 us/tok |  0.57%)
   Foreground NVMe Sync Stall   : 116176.52 ms (866989.0 us/tok | 38.16%)
   Unaccounted / OMP & Sampling :  83435.13 ms (622650.2 us/tok | 27.41%) | Total Wall=304425.34 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    33.07%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    27.51%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.74%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.11%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.57%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5625.00 MB (600 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.83 tps | Avg=0.83 tps | Hit=90.6% | NVMe=504.4 MB/s (74277.59 MB, QD=64) | RSS=14111.5 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.82 tps | Avg=0.83 tps | Hit=90.4% | NVMe=510.0 MB/s (145295.52 MB, QD=64) | RSS=14111.6 MB
[LIVE-DECODE] 2/128 tok | Avg=0.22 tps | Hit=90.4% (LA:+10.6%) | NVMe=507.3 MB/s (148708.02 MB) | RSS=14007.8 MB
[LIVE-DECODE] 4/128 tok | Avg=0.24 tps | Hit=90.3% (LA:+10.7%) | NVMe=504.2 MB/s (151445.02 MB) | RSS=13828.3 MB
[LIVE-DECODE] 6/128 tok | Avg=0.26 tps | Hit=90.3% (LA:+10.7%) | NVMe=502.0 MB/s (153853.84 MB) | RSS=13684.2 MB
[LIVE-DECODE] 8/128 tok | Avg=0.28 tps | Hit=90.3% (LA:+10.8%) | NVMe=500.1 MB/s (156127.52 MB) | RSS=13591.6 MB
[LIVE-DECODE] 10/128 tok | Avg=0.30 tps | Hit=90.3% (LA:+10.8%) | NVMe=498.8 MB/s (158161.90 MB) | RSS=13534.7 MB
[LIVE-DECODE] 12/128 tok | Avg=0.31 tps | Hit=90.2% (LA:+10.9%) | NVMe=497.4 MB/s (160289.40 MB) | RSS=13508.3 MB
[LIVE-DECODE] 14/128 tok | Avg=0.32 tps | Hit=90.2% (LA:+10.9%) | NVMe=496.4 MB/s (162361.96 MB) | RSS=13507.3 MB
[LIVE-DECODE] 16/128 tok | Avg=0.32 tps | Hit=90.2% (LA:+11.0%) | NVMe=495.7 MB/s (164487.27 MB) | RSS=13516.7 MB
[LIVE-DECODE] 18/128 tok | Avg=0.33 tps | Hit=90.2% (LA:+11.0%) | NVMe=494.7 MB/s (166621.34 MB) | RSS=13516.7 MB
[LIVE-DECODE] 20/128 tok | Avg=0.33 tps | Hit=90.1% (LA:+11.1%) | NVMe=493.7 MB/s (168719.77 MB) | RSS=13516.7 MB
[LIVE-DECODE] 22/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.1%) | NVMe=492.7 MB/s (170966.40 MB) | RSS=13515.4 MB
[LIVE-DECODE] 24/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.2%) | NVMe=491.5 MB/s (173239.09 MB) | RSS=13515.4 MB
[LIVE-DECODE] 26/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.2%) | NVMe=490.5 MB/s (175409.77 MB) | RSS=13515.4 MB
[LIVE-DECODE] 28/128 tok | Avg=0.34 tps | Hit=90.0% (LA:+11.2%) | NVMe=489.6 MB/s (177474.90 MB) | RSS=13515.4 MB
[LIVE-DECODE] 30/128 tok | Avg=0.35 tps | Hit=90.0% (LA:+11.3%) | NVMe=489.0 MB/s (179345.34 MB) | RSS=13515.4 MB
[LIVE-DECODE] 32/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.3%) | NVMe=488.6 MB/s (181102.96 MB) | RSS=13515.4 MB
[LIVE-DECODE] 34/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.4%) | NVMe=487.8 MB/s (183168.90 MB) | RSS=13515.4 MB
[LIVE-DECODE] 36/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.4%) | NVMe=486.9 MB/s (185331.02 MB) | RSS=13504.3 MB
[LIVE-DECODE] 38/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.4%) | NVMe=486.1 MB/s (187518.84 MB) | RSS=13496.7 MB
[LIVE-DECODE] 40/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.5%) | NVMe=485.4 MB/s (189514.02 MB) | RSS=13496.7 MB
[LIVE-DECODE] 42/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.5%) | NVMe=484.5 MB/s (191685.40 MB) | RSS=13496.7 MB
[LIVE-DECODE] 44/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.6%) | NVMe=483.5 MB/s (194068.96 MB) | RSS=13506.1 MB
[LIVE-DECODE] 46/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.6%) | NVMe=482.7 MB/s (196357.77 MB) | RSS=13506.1 MB
[LIVE-DECODE] 48/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.7%) | NVMe=482.2 MB/s (198533.02 MB) | RSS=13515.5 MB
[LIVE-DECODE] 50/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.7%) | NVMe=481.5 MB/s (200755.90 MB) | RSS=13515.4 MB
[LIVE-DECODE] 52/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=480.9 MB/s (202725.96 MB) | RSS=13515.4 MB
[LIVE-DECODE] 54/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=480.4 MB/s (204601.34 MB) | RSS=13510.8 MB
[LIVE-DECODE] 56/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.9%) | NVMe=479.5 MB/s (207051.52 MB) | RSS=13515.4 MB
[LIVE-DECODE] 58/128 tok | Avg=0.36 tps | Hit=89.7% (LA:+11.9%) | NVMe=478.9 MB/s (209287.46 MB) | RSS=13515.4 MB
[LIVE-DECODE] 60/128 tok | Avg=0.36 tps | Hit=89.7% (LA:+12.0%) | NVMe=478.4 MB/s (211210.84 MB) | RSS=13515.4 MB
[LIVE-DECODE] 62/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.0%) | NVMe=477.8 MB/s (213163.65 MB) | RSS=13515.4 MB
[LIVE-DECODE] 64/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.1%) | NVMe=477.4 MB/s (215034.71 MB) | RSS=13515.4 MB
[LIVE-DECODE] 66/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.1%) | NVMe=476.9 MB/s (217176.65 MB) | RSS=13506.1 MB
[LIVE-DECODE] 68/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.2%) | NVMe=476.5 MB/s (219252.34 MB) | RSS=13524.8 MB
[LIVE-DECODE] 70/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.2%) | NVMe=476.0 MB/s (221187.77 MB) | RSS=13524.8 MB
[LIVE-DECODE] 72/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.2%) | NVMe=475.5 MB/s (223144.77 MB) | RSS=13524.8 MB
[LIVE-DECODE] 74/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=475.1 MB/s (225079.34 MB) | RSS=13524.8 MB
[LIVE-DECODE] 76/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=474.5 MB/s (227115.21 MB) | RSS=13524.8 MB
[LIVE-DECODE] 78/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.4%) | NVMe=474.1 MB/s (229118.21 MB) | RSS=13506.1 MB
[LIVE-DECODE] 80/128 tok | Avg=0.38 tps | Hit=89.6% (LA:+12.4%) | NVMe=473.7 MB/s (230910.46 MB) | RSS=13506.1 MB
[LIVE-DECODE] 82/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.4%) | NVMe=473.4 MB/s (232524.40 MB) | RSS=13506.1 MB
[LIVE-DECODE] 84/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.4%) | NVMe=473.0 MB/s (234236.52 MB) | RSS=13506.1 MB
[LIVE-DECODE] 86/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.7 MB/s (236029.52 MB) | RSS=13506.1 MB
[LIVE-DECODE] 88/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.4 MB/s (237975.96 MB) | RSS=13506.1 MB
[LIVE-DECODE] 90/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.0 MB/s (239864.59 MB) | RSS=13506.1 MB
[LIVE-DECODE] 92/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=471.9 MB/s (241853.46 MB) | RSS=13515.5 MB
[LIVE-DECODE] 94/128 tok | Avg=0.38 tps | Hit=89.4% (LA:+12.6%) | NVMe=471.5 MB/s (243871.46 MB) | RSS=13515.5 MB
[LIVE-DECODE] 96/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=471.2 MB/s (245661.90 MB) | RSS=13515.4 MB
[LIVE-DECODE] 98/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=470.8 MB/s (247608.96 MB) | RSS=13514.4 MB
[LIVE-DECODE] 100/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=470.6 MB/s (249500.90 MB) | RSS=13496.7 MB
[LIVE-DECODE] 102/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=470.2 MB/s (251302.02 MB) | RSS=13496.7 MB
[LIVE-DECODE] 104/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=469.8 MB/s (253255.15 MB) | RSS=13496.7 MB
[LIVE-DECODE] 106/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.7%) | NVMe=469.6 MB/s (255274.71 MB) | RSS=13506.1 MB
[LIVE-DECODE] 108/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=469.3 MB/s (257281.40 MB) | RSS=13506.1 MB
[LIVE-DECODE] 110/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.9 MB/s (259266.77 MB) | RSS=13506.1 MB
[LIVE-DECODE] 112/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.6 MB/s (261141.46 MB) | RSS=13506.1 MB
[LIVE-DECODE] 114/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.3 MB/s (263180.84 MB) | RSS=13506.1 MB
[LIVE-DECODE] 116/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=468.0 MB/s (265017.27 MB) | RSS=13506.1 MB
[LIVE-DECODE] 118/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=467.7 MB/s (266837.27 MB) | RSS=13506.1 MB
[LIVE-DECODE] 120/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+12.9%) | NVMe=467.4 MB/s (268794.77 MB) | RSS=13506.1 MB
[LIVE-DECODE] 122/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=467.0 MB/s (270811.65 MB) | RSS=13506.1 MB
[LIVE-DECODE] 124/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.7 MB/s (272705.40 MB) | RSS=13506.1 MB
[LIVE-DECODE] 126/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.5 MB/s (274418.71 MB) | RSS=13506.1 MB
[LIVE-DECODE] 128/128 tok | Avg=0.40 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.3 MB/s (276221.09 MB) | RSS=13506.1 MB

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
   LRFU Cache / Staging Ring    : 5625.00 MB (600/12384 exp = 4.84% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.72 MB | End=13506.05 MB | Peak=14166.19 MB
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
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 619921.66 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   24.96 | 100.0% |    1062 |   16.43 | 4467.27 | 35 |167 |134 | 1747200.0 |
   |    3 |   39929 |  LB            |   17.75 |  78.0% |   33903 |   16.24 | 4467.27 |  0 |  0 |  0 | 1747200.0 |
   |    4 |      32 | A              |   14.08 |  30.6% |    1911 |   13.59 | 3728.00 | 72 |172 | 92 | 1401344.0 |
   |    5 |   46254 | -sort          |   18.02 |  42.5% |    1331 |   17.61 | 3728.00 |  0 |  0 |  0 | 1401344.0 |
   |    6 |     287 | ing            |   14.36 |  38.6% |   11492 |   11.93 | 3177.08 |111 |152 | 73 | 1233312.0 |
   |    7 |   11492 |  coal          |   16.09 |  54.1% |    1207 |   14.51 | 3177.08 |  0 |  0 |  0 | 1233312.0 |
   |    8 |    3300 | esc            |   18.05 |  93.7% |     642 |   13.98 | 2966.71 |124 |134 | 78 | 1164128.0 |
   |   56 |  154842 | </think>       |   14.32 |  56.1% |     641 |   13.02 | 3092.77 | 88 |168 | 80 | 1254496.0 |
   |   57 |     641 | In             |   15.30 |  41.7% |     565 |   13.90 | 3092.77 |  0 |  0 |  0 | 1254496.0 |
   |   44 |    3170 |  why           |   17.45 |  85.5% |     419 |   13.32 | 3002.49 |114 |136 | 86 | 1220384.0 |
   |   45 |   42687 |  elimination   |   15.17 |  16.8% |   21673 |   14.81 | 3002.49 |  0 |  0 |  0 | 1220384.0 |
   |  126 |     291 | ed             |   14.96 |  32.3% |    1207 |   14.08 | 2093.03 |190 | 87 | 59 | 877216.0 |
   |  127 |    9421 | -block         |   17.23 |  54.2% |    7299 |   15.51 | 2093.03 |  0 |  0 |  0 | 877216.0 |
   |  128 |    9421 | -block         |   14.61 |  29.9% |    1207 |   13.52 | 2155.56 |189 | 93 | 54 | 922816.0 |
   |  129 |     291 | ed             |   20.50 |  98.5% |   29819 |   14.11 | 2155.56 |  0 |  0 |  0 | 922816.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 619.922s, TTFT=619921.66ms): Avg=0.83 | Min=0.82 | Max=0.83 tps
   Prefill Chunks (2): C1:256t/0.8tps/91% | C2:256t/0.8tps/90%
   Decode  (128 tok, 323.992s): Avg=0.40 | Min=0.22 | Max=0.50 tps
   Latency (ms) : Min=2008.80 | P10=2178.39 | P25=2300.48 | P50=2459.05 | P75=2676.55 | P90=2832.37 | P95=3092.77 | P99=4467.27 | Max=4467.27
   Mean/SD/Jitt : Mean=2531.18ms | StdDev=378.88ms | Jitter=89.44ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=147367 (76.14%) | Lookahead=25237 (+13.04%) | ColdMiss=20932 (10.82%) | EFF HIT=89.18%
   Lookahead    : 15747 prefetched -> 9708 consumed (61.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.2% | @64= 89.7% | @128= 89.2% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3156 | 729 | 723 | 84.3%|9221.56 | | L24 | 4608 | 3590 | 559 | 459 | 90.0%|5498.44 |
   | L04 | 4608 | 3238 | 678 | 692 | 85.0%|8790.31 | | L25 | 4608 | 3654 | 484 | 470 | 89.8%|6087.81 |
   | L05 | 4608 | 3184 | 800 | 624 | 86.5%|8265.62 | | L26 | 4608 | 3657 | 507 | 444 | 90.4%|5426.56 |
   | L06 | 4608 | 3253 | 788 | 567 | 87.7%|7784.06 | | L27 | 4608 | 3534 | 530 | 544 | 88.2%|7086.88 |
   | L07 | 4608 | 3370 | 754 | 484 | 89.5%|6504.69 | | L28 | 4608 | 3516 | 589 | 503 | 89.1%|6130.94 |
   | L08 | 4608 | 3453 | 629 | 526 | 88.6%|6914.38 | | L29 | 4608 | 3426 | 709 | 473 | 89.7%|6059.06 |
   | L09 | 4608 | 3308 | 721 | 579 | 87.4%|7137.19 | | L30 | 4608 | 3513 | 614 | 481 | 89.6%|5793.12 |
   | L10 | 4608 | 3264 | 757 | 587 | 87.3%|7424.69 | | L31 | 4608 | 3371 | 644 | 593 | 87.1%|7288.12 |
   | L11 | 4608 | 3486 | 596 | 526 | 88.6%|8568.75 | | L32 | 4608 | 3289 | 762 | 557 | 87.9%|6777.81 |
   | L12 | 4608 | 3449 | 665 | 494 | 89.3%|7244.38 | | L33 | 4608 | 3375 | 736 | 497 | 89.2%|6619.69 |
   | L13 | 4608 | 3596 | 541 | 471 | 89.8%|5656.56 | | L34 | 4608 | 3661 | 507 | 440 | 90.5%|5742.81 |
   | L14 | 4608 | 3624 | 491 | 493 | 89.3%|6253.12 | | L35 | 4608 | 3466 | 667 | 475 | 89.7%|6059.06 |
   | L15 | 4608 | 3618 | 499 | 491 | 89.3%|6123.75 | | L36 | 4608 | 3313 | 830 | 465 | 89.9%|6138.12 |
   | L16 | 4608 | 3638 | 498 | 472 | 89.8%|6015.94 | | L37 | 4608 | 3609 | 538 | 461 | 90.0%|5742.81 |
   | L17 | 4608 | 3739 | 394 | 475 | 89.7%|5692.50 | | L38 | 4608 | 3602 | 535 | 471 | 89.8%|5965.62 |
   | L18 | 4608 | 3814 | 345 | 449 | 90.3%|5534.38 | | L39 | 4608 | 3588 | 541 | 479 | 89.6%|5771.56 |
   | L19 | 4608 | 3741 | 455 | 412 | 91.1%|5045.62 | | L40 | 4608 | 3623 | 528 | 457 | 90.1%|5663.75 |
   | L20 | 4608 | 3641 | 529 | 438 | 90.5%|5318.75 | | L41 | 4608 | 3518 | 622 | 468 | 89.8%|6080.62 |
   | L21 | 4608 | 3728 | 433 | 447 | 90.3%|5383.44 | | L42 | 4608 | 3387 | 766 | 455 | 90.1%|5469.69 |
   | L22 | 4608 | 3690 | 489 | 429 | 90.7%|5210.94 | | L43 | 4608 | 3577 | 614 | 417 | 91.0%|5347.50 |
   | L23 | 4608 | 3588 | 582 | 438 | 90.5%|5210.94 | | L44 | 4608 | 3520 | 582 | 506 | 89.0%|7696.62 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 276221.09 MB (Load=6361.84 | Prefill=138933.69 | Warmup=0.00 | Decode=130925.56 MB)
   SSD Data/Token (Decode)      : Avg=1022.856 MB/tok (Min=806.969 | P50=1003.344 | P95=1204.406 | Max=1706.250 MB) | Prefill=271.355 MB/tok
   NVMe Batches / Requests      : 5644 Batches | 112049 Raw -> 110491 Merged (1558 LBA Merges, Avg 2559.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=109612
   SSD Read Bandwidth (Active)  : Min=0.43 | Avg=466.33 | Peak=4180.50 MB/s | WallAmort=292.63 MB/s
   OS Kernel I/O Verification   : Read=276230.12 MB | Write=0.01 MB | Syscalls=114576
   Sync Stall vs Async DMA      : SyncStall=301140.30 ms | AsyncOverlapped=577607.13 ms (65.7% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=5.76 GB/s | WallAmort=2.95 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=619.92s (65.7%, 138933.69 MB SSD) | Decode=323.99s (34.3%, 130925.56 MB SSD)
   CPU Time & Utilization       : User=1628.453s + Sys=27.844s (Wall=963.130s) | SysUtil=43.0% | ThrUtil=43.0% | 39.77 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 212757.19 ms (332433.1 us/tok | 22.54%)
   MoE AVX2 Q8 Expert Compute   : 267182.99 ms (417473.4 us/tok | 28.31%)
   Router + Lookahead Dispatch  :   4343.96 ms ( 6787.4 us/tok |  0.46%)
   LM Head Output Projection    :   3364.13 ms ( 5256.4 us/tok |  0.36%)
   Foreground NVMe Sync Stall   : 301140.30 ms (470531.7 us/tok | 31.90%)
   Unaccounted / OMP & Sampling : 155124.73 ms (242382.4 us/tok | 16.43%) | Total Wall=943913.30 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    54.91%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    17.51%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    16.56%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.96%  |
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
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 05:54 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 880K Nov 14 05:54 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.52 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    512.92 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1475.58 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7887.50 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10339.17 MB/s
   RND4K Q32T16 Read                  :    443.37 MB/s (  113502 IOPS)
   RND4K Q1T1  Read                   :    694.57 MB/s (Latency: 5.62 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     65.51 GB/s
   AVX2 256-bit Sequential Write BW   :     46.71 GB/s
   STREAM Triad (A = B + s*C) BW      :     19.42 GB/s
   Random Pointer-Chase Latency       :     54.94 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.33 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    181.88 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.79 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1429.03 tps | Avg=1429.03 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=73.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1211.18 tps | Avg=1311.12 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=73.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1070.55 tps | Avg=1219.75 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=74.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=988.87 tps | Avg=1152.48 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=74.4 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=871.39 tps | Avg=1082.63 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=74.7 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=816.94 tps | Avg=1026.97 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=74.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=748.41 tps | Avg=975.12 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=75.2 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=693.30 tps | Avg=927.97 tps | Hit=100.0% | NVMe=2549.0 MB/s (6.58 MB, QD=64) | RSS=75.5 MB
[LIVE-DECODE] 8/32 tok | Avg=195.72 tps | Hit=100.0% (LA:+0.0%) | NVMe=2549.0 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 16/32 tok | Avg=196.63 tps | Hit=100.0% (LA:+0.0%) | NVMe=2549.0 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 24/32 tok | Avg=196.87 tps | Hit=100.0% (LA:+0.0%) | NVMe=2549.0 MB/s (6.58 MB) | RSS=75.5 MB
[LIVE-DECODE] 32/32 tok | Avg=197.00 tps | Hit=100.0% (LA:+0.0%) | NVMe=2549.0 MB/s (6.58 MB) | RSS=75.5 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=75.50 MB | Peak=75.50 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2206.97 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.14 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.14 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.10 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.10 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.06 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.06 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.14 | 12 |  0 |  0 |     0.0 |
   |    9 |      68 | tok_68         |  176.71 | 100.0% |     228 |  144.43 |    5.14 |  0 |  0 |  0 |     0.0 |
   |   24 |     246 | tok_246        |  204.37 |  99.2% |      55 |  199.55 |    5.13 | 12 |  0 |  0 |     0.0 |
   |   25 |     229 | tok_229        |  171.20 | 100.0% |      70 |  154.08 |    5.13 |  0 |  0 |  0 |     0.0 |
   |   26 |     246 | tok_246        |  195.41 | 100.0% |      54 |  174.46 |    5.12 | 12 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.10 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.10 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.02 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.02 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.207s, TTFT=2206.97ms): Avg=927.97 | Min=693.30 | Max=1429.03 tps
   Prefill Chunks (8): C1:256t/1429.0tps/100% | C2:256t/1211.2tps/100% | C3:256t/1070.5tps/100% | C4:256t/988.9tps/100%
                       C5:256t/871.4tps/100% | C6:256t/816.9tps/100% | C7:256t/748.4tps/100% | C8:256t/693.3tps/100%
   Decode  (32 tok, 0.162s): Avg=197.00 | Min=194.38 | Max=199.67 tps
   Latency (ms) : Min=5.01 | P10=5.01 | P25=5.03 | P50=5.09 | P75=5.12 | P90=5.14 | P95=5.14 | P99=5.14 | Max=5.14
   Mean/SD/Jitt : Mean=5.08ms | StdDev=0.05ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=364.55 | Avg=2548.96 | Peak=6188.12 MB/s | WallAmort=2.78 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=1.25 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.64 GB/s | WallAmort=0.60 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.21s (93.1%, 0.00 MB SSD) | Decode=0.16s (6.9%, 0.00 MB SSD)
   CPU Time & Utilization       : User=3.062s + Sys=0.703s (Wall=2.388s) | SysUtil=39.4% | ThrUtil=39.4% | 36.46 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1996.49 ms (  959.9 us/tok | 84.26%)
   MoE AVX2 Q8 Expert Compute   :    247.69 ms (  119.1 us/tok | 10.45%)
   Router + Lookahead Dispatch  :     60.18 ms (   28.9 us/tok |  2.54%)
   LM Head Output Projection    :      5.98 ms (    2.9 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     59.08 ms (   28.4 us/tok |  2.49%) | Total Wall=2369.41 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    16.53%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.16%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.10%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    79.20%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.01%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1924.28 tps | Avg=1924.28 tps | Hit=99.2% | NVMe=2807.5 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1719.68 tps | Avg=1816.23 tps | Hit=99.2% | NVMe=3721.3 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1759.27 tps | Avg=1796.84 tps | Hit=99.2% | NVMe=4302.8 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1651.71 tps | Avg=1758.22 tps | Hit=99.2% | NVMe=4699.2 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1549.18 tps | Avg=1712.02 tps | Hit=99.2% | NVMe=4988.2 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1359.47 tps | Avg=1641.09 tps | Hit=99.2% | NVMe=5192.5 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1358.47 tps | Avg=1593.72 tps | Hit=99.2% | NVMe=5380.6 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1239.34 tps | Avg=1538.72 tps | Hit=99.2% | NVMe=5567.0 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=171.50 tps | Hit=99.2% (LA:+0.0%) | NVMe=5463.0 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=174.73 tps | Hit=99.2% (LA:+0.1%) | NVMe=5404.3 MB/s (153.28 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=175.98 tps | Hit=99.2% (LA:+0.1%) | NVMe=5299.3 MB/s (154.23 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=176.67 tps | Hit=99.2% (LA:+0.1%) | NVMe=5220.7 MB/s (155.14 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=91.76 MB | Peak=91.76 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1330.97 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    5.90 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    5.90 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    5.88 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    5.88 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    5.85 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    5.85 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    5.70 | 16 |  0 |  0 |    32.0 |
   |    9 |      49 | qtok_49        |   84.72 | 100.0% |     129 |   76.64 |    5.70 |  0 |  0 |  0 |    32.0 |
   |   24 |     128 | qtok_128       |   60.98 |  67.3% |     194 |   60.03 |    5.70 | 13 |  3 |  0 |   115.2 |
   |   25 |      63 | qtok_63        |  124.60 | 100.0% |      19 |   87.54 |    5.70 |  0 |  0 |  0 |   115.2 |
   |   16 |     223 | qtok_223       |   65.44 |  87.6% |     159 |   63.48 |    5.68 | 15 |  1 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.55 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.55 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.59 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.59 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.331s, TTFT=1330.97ms): Avg=1538.72 | Min=1239.34 | Max=1924.28 tps
   Prefill Chunks (8): C1:256t/1924.3tps/99% | C2:256t/1719.7tps/99% | C3:256t/1759.3tps/99% | C4:256t/1651.7tps/99%
                       C5:256t/1549.2tps/99% | C6:256t/1359.5tps/99% | C7:256t/1358.5tps/99% | C8:256t/1239.3tps/99%
   Decode  (32 tok, 0.181s): Avg=176.67 | Min=169.48 | Max=180.26 tps
   Latency (ms) : Min=5.55 | P10=5.56 | P25=5.58 | P50=5.63 | P75=5.70 | P90=5.88 | P95=5.90 | P99=5.90 | Max=5.90
   Mean/SD/Jitt : Mean=5.66ms | StdDev=0.11ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=223.32 | Avg=5220.67 | Peak=10810.46 MB/s | WallAmort=102.60 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=6.73 ms | AsyncOverlapped=28.12 ms (80.7% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.59 GB/s | WallAmort=1.39 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.33s (88.0%, 144.44 MB SSD) | Decode=0.18s (12.0%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.734s + Sys=0.328s (Wall=1.542s) | SysUtil=49.7% | ThrUtil=49.7% | 45.94 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    936.90 ms (  450.4 us/tok | 61.96%)
   MoE AVX2 Q8 Expert Compute   :    376.17 ms (  180.9 us/tok | 24.88%)
   Router + Lookahead Dispatch  :     80.03 ms (   38.5 us/tok |  5.29%)
   LM Head Output Projection    :      5.91 ms (    2.8 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :      6.73 ms (    3.2 us/tok |  0.45%)
   Unaccounted / OMP & Sampling :    106.37 ms (   51.1 us/tok |  7.03%) | Total Wall=1512.10 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    17.99%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.78%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.94%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    69.84%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.45%  |
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
    "ttft_ms": 236.15,
    "avg_tps": 694.48,
    "min_tps": 571.51,
    "max_tps": 777.75
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 143.39,
    "min_tps": 127.3,
    "max_tps": 147.99,
    "p50_ms": 6.88,
    "p90_ms": 7.4,
    "p99_ms": 7.86,
    "mean_ms": 6.97,
    "jitter_ms": 0.14
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
    "avg_mbs": 2246.34,
    "peak_mbs": 5703.82,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.92
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
    "dense_attention": 379.83,
    "moe_compute": 105.32,
    "router_lookahead": 7.52,
    "lm_head": 8.99,
    "unaccounted": 6.47
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 86.96,
    "ram_bandwidth_pinning": 1.92,
    "expert_cache_lrfu": 9.23,
    "lookahead_parallel_overlap": 1.49,
    "ssd_nvme_throughput": 0.4,
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
    "ttft_ms": 307.91,
    "avg_tps": 532.63,
    "min_tps": 386.75,
    "max_tps": 615.35
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 124.42,
    "min_tps": 98.17,
    "max_tps": 130.98,
    "p50_ms": 7.84,
    "p90_ms": 9.35,
    "p99_ms": 10.19,
    "mean_ms": 8.04,
    "jitter_ms": 0.23
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
    "avg_mbs": 2558.78,
    "peak_mbs": 8246.23,
    "sync_wait_ms": 4.69,
    "async_overlap_ms": 12.97
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
    "dense_attention": 351.68,
    "moe_compute": 204.1,
    "router_lookahead": 9.36,
    "lm_head": 8.81,
    "unaccounted": 42.74
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.06,
    "ram_bandwidth_pinning": 2.13,
    "expert_cache_lrfu": 8.54,
    "lookahead_parallel_overlap": 4.53,
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
   System Memory (RAM): 15.99 GB Total / 13.41 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    623.23 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1461.02 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7874.31 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10417.39 MB/s
   RND4K Q32T16 Read                  :    480.53 MB/s (  123016 IOPS)
   RND4K Q1T1  Read                   :    668.14 MB/s (Latency: 5.85 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     60.15 GB/s
   AVX2 256-bit Sequential Write BW   :     46.37 GB/s
   STREAM Triad (A = B + s*C) BW      :     40.97 GB/s
   Random Pointer-Chase Latency       :     64.00 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.41 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    100.13 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     20.52 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 30.99 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 166.49 MB/s (6.15s)
   Window #01 (304.0 MB in 0.50s):   605.95 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   391.90 MB/s (Uncached Direct Read)
   Window #03 ( 88.0 MB in 0.69s):   127.74 MB/s (Uncached Direct Read)
   Window #04 ( 88.0 MB in 0.52s):   168.27 MB/s (Uncached Direct Read)
   Window #05 ( 20.0 MB in 0.97s):    20.72 MB/s (Uncached Direct Read)
   Window #06 ( 56.0 MB in 0.57s):    98.22 MB/s (Uncached Direct Read)
   Window #07 ( 28.0 MB in 0.75s):    37.54 MB/s (Uncached Direct Read)
   Window #08 ( 12.0 MB in 0.57s):    20.98 MB/s (Uncached Direct Read)
   Window #09 ( 72.0 MB in 0.52s):   138.02 MB/s (Uncached Direct Read)
   Window #10 (156.0 MB in 0.50s):   311.23 MB/s (Uncached Direct Read)
   Window #11 (  4.0 MB in 0.00s):   920.24 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   168.03 MB/s (Min=20.72 | Max=920.24 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 351.61 MB/s (2.91s)
   Window #01 (196.0 MB in 0.50s):   390.01 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   388.14 MB/s (Uncached Direct Read)
   Window #03 (216.0 MB in 0.54s):   401.77 MB/s (Uncached Direct Read)
   Window #04 (196.0 MB in 0.51s):   386.72 MB/s (Uncached Direct Read)
   Window #05 (196.0 MB in 0.51s):   387.98 MB/s (Uncached Direct Read)
   Window #06 ( 24.0 MB in 0.05s):   482.12 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   392.79 MB/s (Min=386.72 | Max=482.12 MB/s)
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
   System Memory (RAM): 15.99 GB Total / 13.45 GB Available
   Active Drive Space : 150.00 GB Total / 54.59 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    533.17 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1520.60 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8000.65 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10394.88 MB/s
   RND4K Q32T16 Read                  :    469.59 MB/s (  120214 IOPS)
   RND4K Q1T1  Read                   :    690.61 MB/s (Latency: 5.66 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     38.97 GB/s
   AVX2 256-bit Sequential Write BW   :     30.62 GB/s
   STREAM Triad (A = B + s*C) BW      :     38.51 GB/s
   Random Pointer-Chase Latency       :     73.85 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.00 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    194.94 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.14 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.51 tps | Avg=0.51 tps | Hit=76.8% | NVMe=481.7 MB/s (51661.71 MB, QD=64) | RSS=13958.1 MB

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
   LRFU Cache / Staging Ring    : 5550.00 MB (592/12384 exp = 4.78% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.68 MB | End=13421.96 MB | Peak=14027.79 MB
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
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 137994.74 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   18.90 |  53.4% |   15724 |   18.74 | 3884.79 | 20 |233 | 83 | 1537696.0 |
   |    3 |     397 | >\n            |   12.80 |   6.2% |     318 |   12.73 | 3884.79 |  0 |  0 |  0 | 1537696.0 |
   |    4 |   13699 | <th            |   14.70 |  18.4% |     334 |   14.61 | 2735.48 |148 |121 | 67 | 1037568.0 |
   |    5 |     766 | ink            |   22.04 |  99.6% |     307 |   14.17 | 2735.48 |  0 |  0 |  0 | 1037568.0 |
   |    6 |     397 | >\n            |   12.54 |  13.7% |      29 |   12.50 | 2646.30 |137 |139 | 60 | 1030432.0 |
   |    7 |   13699 | <th            |   16.29 |  41.2% |     522 |   16.02 | 2646.30 |  0 |  0 |  0 | 1030432.0 |
   |    8 |     397 | >\n            |   17.08 |  39.3% |    1339 |   16.33 | 1982.20 |195 | 98 | 43 | 770464.0 |
   |   36 |   29136 |  Gate          |   15.35 |  36.3% |     479 |   14.86 | 3189.80 | 84 |162 | 90 | 1315072.0 |
   |   37 |    3170 |  why           |   16.44 |  65.8% |   34464 |   13.18 | 3189.80 |  0 |  0 |  0 | 1315072.0 |
   |   22 |     264 |  a             |   18.05 |  79.7% |     458 |   15.32 | 2910.97 |103 |178 | 55 | 1195328.0 |
   |   23 |    3405 |  question      |   16.11 |  14.3% |    1681 |   15.86 | 2910.97 |  0 |  0 |  0 | 1195328.0 |
   |   62 |   24384 |  NV            |   15.58 |  36.6% |   50665 |   15.35 | 2348.78 |147 |129 | 60 | 996928.0 |
   |   63 |   50665 |  sequential    |   14.36 |  20.5% |   25372 |   14.09 | 2348.78 |  0 |  0 |  0 | 996928.0 |
   |   64 |   24384 |  NV            |   17.08 |  41.8% |   25372 |   17.00 | 2300.07 |165 |111 | 60 | 953664.0 |
   |   65 |   25372 |  DMA           |   17.65 |  62.3% |   81911 |   16.44 | 2300.07 |  0 |  0 |  0 | 953664.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 137.995s, TTFT=137994.74ms): Avg=0.51 | Min=0.51 | Max=0.51 tps
   Prefill Chunks (1): C1:70t/0.5tps/77%
   Decode  (64 tok, 166.431s): Avg=0.38 | Min=0.26 | Max=0.52 tps
   Latency (ms) : Min=1917.55 | P10=1995.65 | P25=2518.26 | P50=2640.94 | P75=2727.80 | P90=2824.42 | P95=3189.80 | P99=3884.79 | Max=3884.79
   Mean/SD/Jitt : Mean=2600.48ms | StdDev=360.01ms | Jitter=119.73ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=20241 (59.06%) | Lookahead=6547 (+19.10%) | ColdMiss=7484 (21.84%) | EFF HIT=78.16%
   Lookahead    : 7730 prefetched -> 5083 consumed (65.8% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 77.5% | @64= 78.2% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  347 | 143 | 326 | 60.0%|4348.44 | | L24 |  816 |  477 | 196 | 143 | 82.5%|2091.56 |
   | L04 |  816 |  335 | 186 | 295 | 63.8%|3981.88 | | L25 |  816 |  544 | 121 | 151 | 81.5%|2264.06 |
   | L05 |  816 |  341 | 215 | 260 | 68.1%|3687.19 | | L26 |  816 |  508 | 160 | 148 | 81.9%|2041.25 |
   | L06 |  816 |  370 | 221 | 225 | 72.4%|3435.62 | | L27 |  816 |  527 | 115 | 174 | 78.7%|2501.25 |
   | L07 |  816 |  419 | 205 | 192 | 76.5%|2918.12 | | L28 |  816 |  464 | 168 | 184 | 77.5%|2680.94 |
   | L08 |  816 |  398 | 196 | 222 | 72.8%|3320.62 | | L29 |  816 |  499 | 155 | 162 | 80.1%|2314.38 |
   | L09 |  816 |  399 | 185 | 232 | 71.6%|3234.38 | | L30 |  816 |  471 | 168 | 177 | 78.3%|2494.06 |
   | L10 |  816 |  365 | 231 | 220 | 73.0%|3234.38 | | L31 |  816 |  499 | 138 | 179 | 78.1%|2609.06 |
   | L11 |  816 |  458 | 164 | 194 | 76.2%|3646.88 | | L32 |  816 |  497 | 140 | 179 | 78.1%|2688.12 |
   | L12 |  816 |  477 | 160 | 179 | 78.1%|3123.88 | | L33 |  816 |  514 | 144 | 158 | 80.6%|2443.75 |
   | L13 |  816 |  522 | 113 | 181 | 77.8%|2508.44 | | L34 |  816 |  518 | 144 | 154 | 81.1%|2400.62 |
   | L14 |  816 |  473 | 153 | 190 | 76.7%|2839.06 | | L35 |  816 |  508 | 157 | 151 | 81.5%|2343.12 |
   | L15 |  816 |  516 | 123 | 177 | 78.3%|2515.62 | | L36 |  816 |  500 | 166 | 150 | 81.6%|2386.25 |
   | L16 |  816 |  458 | 173 | 185 | 77.3%|2637.81 | | L37 |  816 |  481 | 179 | 156 | 80.9%|2364.69 |
   | L17 |  816 |  463 | 175 | 178 | 78.2%|2666.56 | | L38 |  816 |  548 | 128 | 140 | 82.8%|2141.88 |
   | L18 |  816 |  567 |  97 | 152 | 81.4%|2098.75 | | L39 |  816 |  513 | 157 | 146 | 82.1%|2271.25 |
   | L19 |  816 |  547 | 112 | 157 | 80.8%|2134.69 | | L40 |  816 |  485 | 167 | 164 | 79.9%|2515.62 |
   | L20 |  816 |  590 |  88 | 138 | 83.1%|1911.88 | | L41 |  816 |  466 | 188 | 162 | 80.1%|2515.62 |
   | L21 |  816 |  566 | 103 | 147 | 82.0%|2127.50 | | L42 |  816 |  517 | 149 | 150 | 81.6%|2256.88 |
   | L22 |  816 |  548 | 131 | 137 | 83.2%|1998.12 | | L43 |  816 |  522 | 147 | 147 | 82.0%|2105.94 |
   | L23 |  816 |  550 | 116 | 150 | 81.6%|2062.81 | | L44 |  816 |  474 | 170 | 172 | 78.9%|3241.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 118569.21 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=66907.50 MB)
   SSD Data/Token (Decode)      : Avg=1045.430 MB/tok (Min=752.406 | P50=1067.969 | P95=1284.250 | Max=1501.656 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2672 Batches | 47306 Raw -> 46686 Merged (620 LBA Merges, Avg 2600.7 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=45807
   SSD Read Bandwidth (Active)  : Min=0.49 | Avg=447.60 | Peak=3846.05 MB/s | WallAmort=389.49 MB/s (100.0% of 533.2 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=119556.24 MB | Write=128.00 MB | Syscalls=58260
   Sync Stall vs Async DMA      : SyncStall=116176.52 ms | AsyncOverlapped=250190.13 ms (68.3% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=7.48 GB/s (19.4% STREAM) | WallAmort=2.55 GB/s (Max=38.51 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=137.99s (45.3%, 45299.88 MB SSD) | Decode=166.43s (54.7%, 66907.50 MB SSD)
   CPU Time & Utilization       : User=316.672s + Sys=11.984s (Wall=324.025s) | SysUtil=25.4% | ThrUtil=25.4% | 49.43 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  40222.14 ms (300165.2 us/tok | 13.21%)
   MoE AVX2 Q8 Expert Compute   :  62010.34 ms (462763.8 us/tok | 20.37%)
   Router + Lookahead Dispatch  :    855.89 ms ( 6387.3 us/tok |  0.28%)
   LM Head Output Projection    :   1725.31 ms (12875.5 us/tok |  0.57%)
   Foreground NVMe Sync Stall   : 116176.52 ms (866989.0 us/tok | 38.16%)
   Unaccounted / OMP & Sampling :  83435.13 ms (622650.2 us/tok | 27.41%) | Total Wall=304425.34 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    33.07%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    27.51%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.74%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.11%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.57%  |
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
[LIVE-PREFILL] 64/64 tok | Chunk=0.51 tps | Avg=0.51 tps | Hit=76.5% | NVMe=489.0 MB/s (47437.59 MB, QD=64) | RSS=13620.2 MB
[LIVE-DECODE] 2/32 tok | Avg=0.24 tps | Hit=76.5% (LA:+10.1%) | NVMe=483.8 MB/s (50577.40 MB) | RSS=13555.0 MB
[LIVE-DECODE] 4/32 tok | Avg=0.28 tps | Hit=76.5% (LA:+10.8%) | NVMe=478.9 MB/s (52976.40 MB) | RSS=13462.8 MB
[LIVE-DECODE] 6/32 tok | Avg=0.28 tps | Hit=76.6% (LA:+11.5%) | NVMe=475.0 MB/s (55522.65 MB) | RSS=13378.8 MB
[LIVE-DECODE] 8/32 tok | Avg=0.31 tps | Hit=76.7% (LA:+12.1%) | NVMe=473.2 MB/s (57549.34 MB) | RSS=13359.6 MB
[LIVE-DECODE] 10/32 tok | Avg=0.32 tps | Hit=76.8% (LA:+12.6%) | NVMe=471.3 MB/s (59675.02 MB) | RSS=13314.5 MB
[LIVE-DECODE] 12/32 tok | Avg=0.32 tps | Hit=77.0% (LA:+13.3%) | NVMe=468.9 MB/s (61945.09 MB) | RSS=13254.1 MB
[LIVE-DECODE] 14/32 tok | Avg=0.33 tps | Hit=77.1% (LA:+13.8%) | NVMe=467.9 MB/s (63947.96 MB) | RSS=13234.8 MB
[LIVE-DECODE] 16/32 tok | Avg=0.35 tps | Hit=77.2% (LA:+14.0%) | NVMe=467.5 MB/s (65593.34 MB) | RSS=13226.8 MB
[LIVE-DECODE] 18/32 tok | Avg=0.35 tps | Hit=77.3% (LA:+14.6%) | NVMe=466.2 MB/s (68065.84 MB) | RSS=13181.0 MB
[LIVE-DECODE] 20/32 tok | Avg=0.35 tps | Hit=77.4% (LA:+15.1%) | NVMe=464.4 MB/s (70194.46 MB) | RSS=13132.0 MB
[LIVE-DECODE] 22/32 tok | Avg=0.35 tps | Hit=77.4% (LA:+15.5%) | NVMe=463.2 MB/s (72230.27 MB) | RSS=13121.9 MB
[LIVE-DECODE] 24/32 tok | Avg=0.35 tps | Hit=77.5% (LA:+15.9%) | NVMe=461.9 MB/s (74543.46 MB) | RSS=13121.9 MB
[LIVE-DECODE] 26/32 tok | Avg=0.35 tps | Hit=77.5% (LA:+16.3%) | NVMe=461.0 MB/s (76723.77 MB) | RSS=13121.9 MB
[LIVE-DECODE] 28/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+16.5%) | NVMe=459.9 MB/s (78868.71 MB) | RSS=13121.9 MB
[LIVE-DECODE] 30/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+16.8%) | NVMe=459.3 MB/s (80921.02 MB) | RSS=13121.9 MB
[LIVE-DECODE] 32/32 tok | Avg=0.36 tps | Hit=77.5% (LA:+17.0%) | NVMe=459.0 MB/s (82851.65 MB) | RSS=13121.9 MB

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
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13121.93 MB | Peak=13698.61 MB
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
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 126246.70 |  0 |  0 |  0 |     0.0 |
   |    2 |     220 |                |   14.20 |   9.2% |   24923 |   14.18 | 4100.87 | 19 |229 | 88 | 1607584.0 |
   |    3 |      16 | 1              |   18.33 |  26.6% |      19 |   17.27 | 4100.87 |  0 |  0 |  0 | 1607584.0 |
   |    4 |   15245 | -bit           |   13.67 |  13.4% |      13 |   13.56 | 3160.53 | 79 |194 | 63 | 1228288.0 |
   |    5 |    1112 | ...            |   13.59 |   8.9% |    1565 |   13.29 | 3160.53 |  0 |  0 |  0 | 1228288.0 |
   |    6 |    4398 |  More          |   11.74 |   8.2% |     508 |   10.90 | 3271.49 | 73 |199 | 64 | 1303680.0 |
   |    7 |     198 | \n             |   11.62 |   6.7% |     271 |   11.49 | 3271.49 |  0 |  0 |  0 | 1303680.0 |
   |    8 |      58 | [              |   13.68 |   7.4% |     785 |   13.10 | 2485.52 |121 |167 | 48 | 1037664.0 |
   |   18 |      16 | 1              |   14.79 |  37.1% |       8 |   12.48 | 3202.50 | 86 |184 | 66 | 1265920.0 |
   |   19 |   15245 | -bit           |   24.00 |  99.8% |    1455 |   16.07 | 3202.50 |  0 |  0 |  0 | 1265920.0 |
   |   12 |   21265 |  highlights    |   11.86 |  14.3% |    7998 |   11.70 | 2879.59 | 94 |196 | 46 | 1162272.0 |
   |   13 |   88737 | ???\n          |   14.28 |  12.8% |    9335 |   14.26 | 2879.59 |  0 |  0 |  0 | 1162272.0 |
   |   30 |    1506 | ized           |   16.47 |  78.5% |   10267 |   12.96 | 2479.86 |136 |128 | 72 | 1050784.0 |
   |   31 |     220 |                |   19.68 |  90.4% |      16 |   16.01 | 2479.86 |  0 |  0 |  0 | 1050784.0 |
   |   32 |      16 | 1              |   15.37 |  33.8% |      19 |   14.89 | 2272.92 |153 |113 | 70 | 988480.0 |
   |   33 |   15245 | -bit           |   25.55 | 100.0% |    1455 |   16.54 | 2272.92 |  0 |  0 |  0 | 988480.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 126.247s, TTFT=126246.70ms): Avg=0.51 | Min=0.51 | Max=0.51 tps
   Prefill Chunks (1): C1:64t/0.5tps/77%
   Decode  (32 tok, 88.203s): Avg=0.36 | Min=0.24 | Max=0.52 tps
   Latency (ms) : Min=1929.97 | P10=2272.92 | P25=2485.52 | P50=2645.20 | P75=3160.53 | P90=3271.49 | P95=4100.87 | P99=4100.87 | Max=4100.87
   Mean/SD/Jitt : Mean=2756.35ms | StdDev=485.05ms | Jitter=194.10ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=16266 (60.51%) | Lookahead=4571 (+17.01%) | ColdMiss=6043 (22.48%) | EFF HIT=77.52%
   Lookahead    : 4329 prefetched -> 3172 consumed (73.3% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 77.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  290 |  92 | 258 | 59.7%|2910.94 | | L24 |  640 |  442 |  74 | 124 | 80.6%|1473.44 |
   | L04 |  640 |  289 | 128 | 223 | 65.2%|2724.06 | | L25 |  640 |  409 |  97 | 134 | 79.1%|1681.88 |
   | L05 |  640 |  267 | 155 | 218 | 65.9%|2623.44 | | L26 |  640 |  430 | 101 | 109 | 83.0%|1437.50 |
   | L06 |  640 |  315 | 139 | 186 | 70.9%|2285.62 | | L27 |  640 |  411 | 100 | 129 | 79.8%|1602.81 |
   | L07 |  640 |  353 | 137 | 150 | 76.6%|1983.75 | | L28 |  640 |  403 | 105 | 132 | 79.4%|1653.12 |
   | L08 |  640 |  332 | 143 | 165 | 74.2%|2041.25 | | L29 |  640 |  384 | 118 | 138 | 78.4%|1760.94 |
   | L09 |  640 |  288 | 165 | 187 | 70.8%|2235.31 | | L30 |  640 |  395 | 104 | 141 | 78.0%|1660.31 |
   | L10 |  640 |  305 | 148 | 187 | 70.8%|2242.50 | | L31 |  640 |  382 | 117 | 141 | 78.0%|1732.19 |
   | L11 |  640 |  392 |  95 | 153 | 76.1%|2465.62 | | L32 |  640 |  358 | 146 | 136 | 78.8%|1796.88 |
   | L12 |  640 |  354 | 139 | 147 | 77.0%|2211.00 | | L33 |  640 |  375 | 134 | 131 | 79.5%|1588.44 |
   | L13 |  640 |  400 |  91 | 149 | 76.7%|1768.12 | | L34 |  640 |  430 |  94 | 116 | 81.9%|1487.81 |
   | L14 |  640 |  424 |  68 | 148 | 76.9%|1696.25 | | L35 |  640 |  374 | 139 | 127 | 80.2%|1588.44 |
   | L15 |  640 |  426 |  69 | 145 | 77.3%|1703.44 | | L36 |  640 |  354 | 153 | 133 | 79.2%|1645.94 |
   | L16 |  640 |  421 |  91 | 128 | 80.0%|1681.88 | | L37 |  640 |  382 | 120 | 138 | 78.4%|1861.56 |
   | L17 |  640 |  427 |  79 | 134 | 79.1%|1660.31 | | L38 |  640 |  405 | 104 | 131 | 79.5%|1610.00 |
   | L18 |  640 |  446 |  72 | 122 | 80.9%|1516.56 | | L39 |  640 |  402 | 110 | 128 | 80.0%|1602.81 |
   | L19 |  640 |  441 |  80 | 119 | 81.4%|1509.38 | | L40 |  640 |  418 |  91 | 131 | 79.5%|1552.50 |
   | L20 |  640 |  428 |  79 | 133 | 79.2%|1610.00 | | L41 |  640 |  407 |  93 | 140 | 78.1%|1703.44 |
   | L21 |  640 |  450 |  73 | 117 | 81.7%|1437.50 | | L42 |  640 |  361 | 158 | 121 | 81.1%|1459.06 |
   | L22 |  640 |  452 |  71 | 117 | 81.7%|1430.31 | | L43 |  640 |  422 | 108 | 110 | 82.8%|1523.75 |
   | L23 |  640 |  422 |  83 | 135 | 78.9%|1588.44 | | L44 |  640 |  400 | 108 | 132 | 79.4%|1968.12 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 82851.65 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=35414.06 MB)
   SSD Data/Token (Decode)      : Avg=1106.689 MB/tok (Min=822.688 | P50=1072.469 | P95=1569.906 | Max=1569.906 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1390 Batches | 32666 Raw -> 32192 Merged (474 LBA Merges, Avg 2635.4 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=31313
   SSD Read Bandwidth (Active)  : Min=0.49 | Avg=459.03 | Peak=3585.77 MB/s | WallAmort=386.35 MB/s
   OS Kernel I/O Verification   : Read=82860.68 MB | Write=0.00 MB | Syscalls=36228
   Sync Stall vs Async DMA      : SyncStall=89908.70 ms | AsyncOverlapped=165853.72 ms (64.8% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=6.31 GB/s | WallAmort=2.27 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=126.25s (58.9%, 41075.75 MB SSD) | Decode=88.20s (41.1%, 35414.06 MB SSD)
   CPU Time & Utilization       : User=240.328s + Sys=8.922s (Wall=233.047s) | SysUtil=26.7% | ThrUtil=26.7% | 24.73 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  31189.18 ms (324887.3 us/tok | 14.54%)
   MoE AVX2 Q8 Expert Compute   :  45292.54 ms (471797.2 us/tok | 21.12%)
   Router + Lookahead Dispatch  :    662.35 ms ( 6899.4 us/tok |  0.31%)
   LM Head Output Projection    :    842.50 ms ( 8776.0 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :  89908.70 ms (936549.0 us/tok | 41.93%)
   Unaccounted / OMP & Sampling :  46554.50 ms (484942.7 us/tok | 21.71%) | Total Wall=214449.76 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    35.57%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    25.11%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    28.95%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.28%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.09%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_glm53_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5625.00 MB (600 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.83 tps | Avg=0.83 tps | Hit=90.6% | NVMe=504.4 MB/s (74277.59 MB, QD=64) | RSS=14111.5 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.82 tps | Avg=0.83 tps | Hit=90.4% | NVMe=510.0 MB/s (145295.52 MB, QD=64) | RSS=14111.6 MB
[LIVE-DECODE] 2/128 tok | Avg=0.22 tps | Hit=90.4% (LA:+10.6%) | NVMe=507.3 MB/s (148708.02 MB) | RSS=14007.8 MB
[LIVE-DECODE] 4/128 tok | Avg=0.24 tps | Hit=90.3% (LA:+10.7%) | NVMe=504.2 MB/s (151445.02 MB) | RSS=13828.3 MB
[LIVE-DECODE] 6/128 tok | Avg=0.26 tps | Hit=90.3% (LA:+10.7%) | NVMe=502.0 MB/s (153853.84 MB) | RSS=13684.2 MB
[LIVE-DECODE] 8/128 tok | Avg=0.28 tps | Hit=90.3% (LA:+10.8%) | NVMe=500.1 MB/s (156127.52 MB) | RSS=13591.6 MB
[LIVE-DECODE] 10/128 tok | Avg=0.30 tps | Hit=90.3% (LA:+10.8%) | NVMe=498.8 MB/s (158161.90 MB) | RSS=13534.7 MB
[LIVE-DECODE] 12/128 tok | Avg=0.31 tps | Hit=90.2% (LA:+10.9%) | NVMe=497.4 MB/s (160289.40 MB) | RSS=13508.3 MB
[LIVE-DECODE] 14/128 tok | Avg=0.32 tps | Hit=90.2% (LA:+10.9%) | NVMe=496.4 MB/s (162361.96 MB) | RSS=13507.3 MB
[LIVE-DECODE] 16/128 tok | Avg=0.32 tps | Hit=90.2% (LA:+11.0%) | NVMe=495.7 MB/s (164487.27 MB) | RSS=13516.7 MB
[LIVE-DECODE] 18/128 tok | Avg=0.33 tps | Hit=90.2% (LA:+11.0%) | NVMe=494.7 MB/s (166621.34 MB) | RSS=13516.7 MB
[LIVE-DECODE] 20/128 tok | Avg=0.33 tps | Hit=90.1% (LA:+11.1%) | NVMe=493.7 MB/s (168719.77 MB) | RSS=13516.7 MB
[LIVE-DECODE] 22/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.1%) | NVMe=492.7 MB/s (170966.40 MB) | RSS=13515.4 MB
[LIVE-DECODE] 24/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.2%) | NVMe=491.5 MB/s (173239.09 MB) | RSS=13515.4 MB
[LIVE-DECODE] 26/128 tok | Avg=0.34 tps | Hit=90.1% (LA:+11.2%) | NVMe=490.5 MB/s (175409.77 MB) | RSS=13515.4 MB
[LIVE-DECODE] 28/128 tok | Avg=0.34 tps | Hit=90.0% (LA:+11.2%) | NVMe=489.6 MB/s (177474.90 MB) | RSS=13515.4 MB
[LIVE-DECODE] 30/128 tok | Avg=0.35 tps | Hit=90.0% (LA:+11.3%) | NVMe=489.0 MB/s (179345.34 MB) | RSS=13515.4 MB
[LIVE-DECODE] 32/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.3%) | NVMe=488.6 MB/s (181102.96 MB) | RSS=13515.4 MB
[LIVE-DECODE] 34/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.4%) | NVMe=487.8 MB/s (183168.90 MB) | RSS=13515.4 MB
[LIVE-DECODE] 36/128 tok | Avg=0.36 tps | Hit=90.0% (LA:+11.4%) | NVMe=486.9 MB/s (185331.02 MB) | RSS=13504.3 MB
[LIVE-DECODE] 38/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.4%) | NVMe=486.1 MB/s (187518.84 MB) | RSS=13496.7 MB
[LIVE-DECODE] 40/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.5%) | NVMe=485.4 MB/s (189514.02 MB) | RSS=13496.7 MB
[LIVE-DECODE] 42/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.5%) | NVMe=484.5 MB/s (191685.40 MB) | RSS=13496.7 MB
[LIVE-DECODE] 44/128 tok | Avg=0.36 tps | Hit=89.9% (LA:+11.6%) | NVMe=483.5 MB/s (194068.96 MB) | RSS=13506.1 MB
[LIVE-DECODE] 46/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.6%) | NVMe=482.7 MB/s (196357.77 MB) | RSS=13506.1 MB
[LIVE-DECODE] 48/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.7%) | NVMe=482.2 MB/s (198533.02 MB) | RSS=13515.5 MB
[LIVE-DECODE] 50/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.7%) | NVMe=481.5 MB/s (200755.90 MB) | RSS=13515.4 MB
[LIVE-DECODE] 52/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=480.9 MB/s (202725.96 MB) | RSS=13515.4 MB
[LIVE-DECODE] 54/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.8%) | NVMe=480.4 MB/s (204601.34 MB) | RSS=13510.8 MB
[LIVE-DECODE] 56/128 tok | Avg=0.36 tps | Hit=89.8% (LA:+11.9%) | NVMe=479.5 MB/s (207051.52 MB) | RSS=13515.4 MB
[LIVE-DECODE] 58/128 tok | Avg=0.36 tps | Hit=89.7% (LA:+11.9%) | NVMe=478.9 MB/s (209287.46 MB) | RSS=13515.4 MB
[LIVE-DECODE] 60/128 tok | Avg=0.36 tps | Hit=89.7% (LA:+12.0%) | NVMe=478.4 MB/s (211210.84 MB) | RSS=13515.4 MB
[LIVE-DECODE] 62/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.0%) | NVMe=477.8 MB/s (213163.65 MB) | RSS=13515.4 MB
[LIVE-DECODE] 64/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.1%) | NVMe=477.4 MB/s (215034.71 MB) | RSS=13515.4 MB
[LIVE-DECODE] 66/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.1%) | NVMe=476.9 MB/s (217176.65 MB) | RSS=13506.1 MB
[LIVE-DECODE] 68/128 tok | Avg=0.37 tps | Hit=89.7% (LA:+12.2%) | NVMe=476.5 MB/s (219252.34 MB) | RSS=13524.8 MB
[LIVE-DECODE] 70/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.2%) | NVMe=476.0 MB/s (221187.77 MB) | RSS=13524.8 MB
[LIVE-DECODE] 72/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.2%) | NVMe=475.5 MB/s (223144.77 MB) | RSS=13524.8 MB
[LIVE-DECODE] 74/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=475.1 MB/s (225079.34 MB) | RSS=13524.8 MB
[LIVE-DECODE] 76/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.3%) | NVMe=474.5 MB/s (227115.21 MB) | RSS=13524.8 MB
[LIVE-DECODE] 78/128 tok | Avg=0.37 tps | Hit=89.6% (LA:+12.4%) | NVMe=474.1 MB/s (229118.21 MB) | RSS=13506.1 MB
[LIVE-DECODE] 80/128 tok | Avg=0.38 tps | Hit=89.6% (LA:+12.4%) | NVMe=473.7 MB/s (230910.46 MB) | RSS=13506.1 MB
[LIVE-DECODE] 82/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.4%) | NVMe=473.4 MB/s (232524.40 MB) | RSS=13506.1 MB
[LIVE-DECODE] 84/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.4%) | NVMe=473.0 MB/s (234236.52 MB) | RSS=13506.1 MB
[LIVE-DECODE] 86/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.7 MB/s (236029.52 MB) | RSS=13506.1 MB
[LIVE-DECODE] 88/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.4 MB/s (237975.96 MB) | RSS=13506.1 MB
[LIVE-DECODE] 90/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=472.0 MB/s (239864.59 MB) | RSS=13506.1 MB
[LIVE-DECODE] 92/128 tok | Avg=0.38 tps | Hit=89.5% (LA:+12.5%) | NVMe=471.9 MB/s (241853.46 MB) | RSS=13515.5 MB
[LIVE-DECODE] 94/128 tok | Avg=0.38 tps | Hit=89.4% (LA:+12.6%) | NVMe=471.5 MB/s (243871.46 MB) | RSS=13515.5 MB
[LIVE-DECODE] 96/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=471.2 MB/s (245661.90 MB) | RSS=13515.4 MB
[LIVE-DECODE] 98/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=470.8 MB/s (247608.96 MB) | RSS=13514.4 MB
[LIVE-DECODE] 100/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.6%) | NVMe=470.6 MB/s (249500.90 MB) | RSS=13496.7 MB
[LIVE-DECODE] 102/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=470.2 MB/s (251302.02 MB) | RSS=13496.7 MB
[LIVE-DECODE] 104/128 tok | Avg=0.39 tps | Hit=89.4% (LA:+12.7%) | NVMe=469.8 MB/s (253255.15 MB) | RSS=13496.7 MB
[LIVE-DECODE] 106/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.7%) | NVMe=469.6 MB/s (255274.71 MB) | RSS=13506.1 MB
[LIVE-DECODE] 108/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=469.3 MB/s (257281.40 MB) | RSS=13506.1 MB
[LIVE-DECODE] 110/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.9 MB/s (259266.77 MB) | RSS=13506.1 MB
[LIVE-DECODE] 112/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.6 MB/s (261141.46 MB) | RSS=13506.1 MB
[LIVE-DECODE] 114/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.8%) | NVMe=468.3 MB/s (263180.84 MB) | RSS=13506.1 MB
[LIVE-DECODE] 116/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=468.0 MB/s (265017.27 MB) | RSS=13506.1 MB
[LIVE-DECODE] 118/128 tok | Avg=0.39 tps | Hit=89.3% (LA:+12.9%) | NVMe=467.7 MB/s (266837.27 MB) | RSS=13506.1 MB
[LIVE-DECODE] 120/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+12.9%) | NVMe=467.4 MB/s (268794.77 MB) | RSS=13506.1 MB
[LIVE-DECODE] 122/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=467.0 MB/s (270811.65 MB) | RSS=13506.1 MB
[LIVE-DECODE] 124/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.7 MB/s (272705.40 MB) | RSS=13506.1 MB
[LIVE-DECODE] 126/128 tok | Avg=0.39 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.5 MB/s (274418.71 MB) | RSS=13506.1 MB
[LIVE-DECODE] 128/128 tok | Avg=0.40 tps | Hit=89.2% (LA:+13.0%) | NVMe=466.3 MB/s (276221.09 MB) | RSS=13506.1 MB

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
   LRFU Cache / Staging Ring    : 5625.00 MB (600/12384 exp = 4.84% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.72 MB | End=13506.05 MB | Peak=14166.19 MB
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
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 619921.66 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   24.96 | 100.0% |    1062 |   16.43 | 4467.27 | 35 |167 |134 | 1747200.0 |
   |    3 |   39929 |  LB            |   17.75 |  78.0% |   33903 |   16.24 | 4467.27 |  0 |  0 |  0 | 1747200.0 |
   |    4 |      32 | A              |   14.08 |  30.6% |    1911 |   13.59 | 3728.00 | 72 |172 | 92 | 1401344.0 |
   |    5 |   46254 | -sort          |   18.02 |  42.5% |    1331 |   17.61 | 3728.00 |  0 |  0 |  0 | 1401344.0 |
   |    6 |     287 | ing            |   14.36 |  38.6% |   11492 |   11.93 | 3177.08 |111 |152 | 73 | 1233312.0 |
   |    7 |   11492 |  coal          |   16.09 |  54.1% |    1207 |   14.51 | 3177.08 |  0 |  0 |  0 | 1233312.0 |
   |    8 |    3300 | esc            |   18.05 |  93.7% |     642 |   13.98 | 2966.71 |124 |134 | 78 | 1164128.0 |
   |   56 |  154842 | </think>       |   14.32 |  56.1% |     641 |   13.02 | 3092.77 | 88 |168 | 80 | 1254496.0 |
   |   57 |     641 | In             |   15.30 |  41.7% |     565 |   13.90 | 3092.77 |  0 |  0 |  0 | 1254496.0 |
   |   44 |    3170 |  why           |   17.45 |  85.5% |     419 |   13.32 | 3002.49 |114 |136 | 86 | 1220384.0 |
   |   45 |   42687 |  elimination   |   15.17 |  16.8% |   21673 |   14.81 | 3002.49 |  0 |  0 |  0 | 1220384.0 |
   |  126 |     291 | ed             |   14.96 |  32.3% |    1207 |   14.08 | 2093.03 |190 | 87 | 59 | 877216.0 |
   |  127 |    9421 | -block         |   17.23 |  54.2% |    7299 |   15.51 | 2093.03 |  0 |  0 |  0 | 877216.0 |
   |  128 |    9421 | -block         |   14.61 |  29.9% |    1207 |   13.52 | 2155.56 |189 | 93 | 54 | 922816.0 |
   |  129 |     291 | ed             |   20.50 |  98.5% |   29819 |   14.11 | 2155.56 |  0 |  0 |  0 | 922816.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 619.922s, TTFT=619921.66ms): Avg=0.83 | Min=0.82 | Max=0.83 tps
   Prefill Chunks (2): C1:256t/0.8tps/91% | C2:256t/0.8tps/90%
   Decode  (128 tok, 323.992s): Avg=0.40 | Min=0.22 | Max=0.50 tps
   Latency (ms) : Min=2008.80 | P10=2178.39 | P25=2300.48 | P50=2459.05 | P75=2676.55 | P90=2832.37 | P95=3092.77 | P99=4467.27 | Max=4467.27
   Mean/SD/Jitt : Mean=2531.18ms | StdDev=378.88ms | Jitter=89.44ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=147367 (76.14%) | Lookahead=25237 (+13.04%) | ColdMiss=20932 (10.82%) | EFF HIT=89.18%
   Lookahead    : 15747 prefetched -> 9708 consumed (61.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.2% | @64= 89.7% | @128= 89.2% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3156 | 729 | 723 | 84.3%|9221.56 | | L24 | 4608 | 3590 | 559 | 459 | 90.0%|5498.44 |
   | L04 | 4608 | 3238 | 678 | 692 | 85.0%|8790.31 | | L25 | 4608 | 3654 | 484 | 470 | 89.8%|6087.81 |
   | L05 | 4608 | 3184 | 800 | 624 | 86.5%|8265.62 | | L26 | 4608 | 3657 | 507 | 444 | 90.4%|5426.56 |
   | L06 | 4608 | 3253 | 788 | 567 | 87.7%|7784.06 | | L27 | 4608 | 3534 | 530 | 544 | 88.2%|7086.88 |
   | L07 | 4608 | 3370 | 754 | 484 | 89.5%|6504.69 | | L28 | 4608 | 3516 | 589 | 503 | 89.1%|6130.94 |
   | L08 | 4608 | 3453 | 629 | 526 | 88.6%|6914.38 | | L29 | 4608 | 3426 | 709 | 473 | 89.7%|6059.06 |
   | L09 | 4608 | 3308 | 721 | 579 | 87.4%|7137.19 | | L30 | 4608 | 3513 | 614 | 481 | 89.6%|5793.12 |
   | L10 | 4608 | 3264 | 757 | 587 | 87.3%|7424.69 | | L31 | 4608 | 3371 | 644 | 593 | 87.1%|7288.12 |
   | L11 | 4608 | 3486 | 596 | 526 | 88.6%|8568.75 | | L32 | 4608 | 3289 | 762 | 557 | 87.9%|6777.81 |
   | L12 | 4608 | 3449 | 665 | 494 | 89.3%|7244.38 | | L33 | 4608 | 3375 | 736 | 497 | 89.2%|6619.69 |
   | L13 | 4608 | 3596 | 541 | 471 | 89.8%|5656.56 | | L34 | 4608 | 3661 | 507 | 440 | 90.5%|5742.81 |
   | L14 | 4608 | 3624 | 491 | 493 | 89.3%|6253.12 | | L35 | 4608 | 3466 | 667 | 475 | 89.7%|6059.06 |
   | L15 | 4608 | 3618 | 499 | 491 | 89.3%|6123.75 | | L36 | 4608 | 3313 | 830 | 465 | 89.9%|6138.12 |
   | L16 | 4608 | 3638 | 498 | 472 | 89.8%|6015.94 | | L37 | 4608 | 3609 | 538 | 461 | 90.0%|5742.81 |
   | L17 | 4608 | 3739 | 394 | 475 | 89.7%|5692.50 | | L38 | 4608 | 3602 | 535 | 471 | 89.8%|5965.62 |
   | L18 | 4608 | 3814 | 345 | 449 | 90.3%|5534.38 | | L39 | 4608 | 3588 | 541 | 479 | 89.6%|5771.56 |
   | L19 | 4608 | 3741 | 455 | 412 | 91.1%|5045.62 | | L40 | 4608 | 3623 | 528 | 457 | 90.1%|5663.75 |
   | L20 | 4608 | 3641 | 529 | 438 | 90.5%|5318.75 | | L41 | 4608 | 3518 | 622 | 468 | 89.8%|6080.62 |
   | L21 | 4608 | 3728 | 433 | 447 | 90.3%|5383.44 | | L42 | 4608 | 3387 | 766 | 455 | 90.1%|5469.69 |
   | L22 | 4608 | 3690 | 489 | 429 | 90.7%|5210.94 | | L43 | 4608 | 3577 | 614 | 417 | 91.0%|5347.50 |
   | L23 | 4608 | 3588 | 582 | 438 | 90.5%|5210.94 | | L44 | 4608 | 3520 | 582 | 506 | 89.0%|7696.62 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 276221.09 MB (Load=6361.84 | Prefill=138933.69 | Warmup=0.00 | Decode=130925.56 MB)
   SSD Data/Token (Decode)      : Avg=1022.856 MB/tok (Min=806.969 | P50=1003.344 | P95=1204.406 | Max=1706.250 MB) | Prefill=271.355 MB/tok
   NVMe Batches / Requests      : 5644 Batches | 112049 Raw -> 110491 Merged (1558 LBA Merges, Avg 2559.9 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=109612
   SSD Read Bandwidth (Active)  : Min=0.43 | Avg=466.33 | Peak=4180.50 MB/s | WallAmort=292.63 MB/s
   OS Kernel I/O Verification   : Read=276230.12 MB | Write=0.01 MB | Syscalls=114576
   Sync Stall vs Async DMA      : SyncStall=301140.30 ms | AsyncOverlapped=577607.13 ms (65.7% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=5.76 GB/s | WallAmort=2.95 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=619.92s (65.7%, 138933.69 MB SSD) | Decode=323.99s (34.3%, 130925.56 MB SSD)
   CPU Time & Utilization       : User=1628.453s + Sys=27.844s (Wall=963.130s) | SysUtil=43.0% | ThrUtil=43.0% | 39.77 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 212757.19 ms (332433.1 us/tok | 22.54%)
   MoE AVX2 Q8 Expert Compute   : 267182.99 ms (417473.4 us/tok | 28.31%)
   Router + Lookahead Dispatch  :   4343.96 ms ( 6787.4 us/tok |  0.46%)
   LM Head Output Projection    :   3364.13 ms ( 5256.4 us/tok |  0.36%)
   Foreground NVMe Sync Stall   : 301140.30 ms (470531.7 us/tok | 31.90%)
   Unaccounted / OMP & Sampling : 155124.73 ms (242382.4 us/tok | 16.43%) | Total Wall=943913.30 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    54.91%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    17.51%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    16.56%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.96%  |
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
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
