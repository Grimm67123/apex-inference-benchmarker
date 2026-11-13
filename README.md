<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#24 (Run ID `43464219439`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43464219439)
- **Status**: **CANCELLED**
- **Timestamp**: `2026-11-13 17:12:28 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-13T16:35:24.982Z] ================================================================================
[2026-11-13T16:35:25.002Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-13T16:35:25.004Z] ================================================================================
[2026-11-13T16:35:29.768Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-13T16:35:29.970Z] --------------------------------------------------------------------------------
[2026-11-13T16:35:29.972Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 31 GB / 149.89 GB
[2026-11-13T16:35:29.973Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-13T16:35:29.974Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.01 GB
[2026-11-13T16:35:29.988Z] --------------------------------------------------------------------------------
[2026-11-13T16:35:29.990Z]  [OK] Disk space verification passed: 178.01 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 855K Nov 13 16:36 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 855K Nov 13 16:36 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.50 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    476.72 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1495.09 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7628.40 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10062.26 MB/s
   RND4K Q32T16 Read                  :    481.78 MB/s (  123335 IOPS)
   RND4K Q1T1  Read                   :    720.64 MB/s (Latency: 5.42 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     60.78 GB/s
   AVX2 256-bit Sequential Write BW   :     48.98 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.29 GB/s
   Random Pointer-Chase Latency       :     52.70 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.35 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    197.50 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     22.42 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1434.18 tps | Avg=1434.18 tps | Hit=99.5% | NVMe=2531.9 MB/s (6.19 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1209.48 tps | Avg=1312.28 tps | Hit=99.5% | NVMe=2498.6 MB/s (7.01 MB, QD=64) | RSS=71.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1093.31 tps | Avg=1230.15 tps | Hit=99.5% | NVMe=2473.4 MB/s (7.78 MB, QD=64) | RSS=71.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=986.74 tps | Avg=1158.69 tps | Hit=99.5% | NVMe=2483.2 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=893.01 tps | Avg=1093.62 tps | Hit=99.5% | NVMe=2493.6 MB/s (9.33 MB, QD=64) | RSS=72.3 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=805.38 tps | Avg=1032.06 tps | Hit=99.5% | NVMe=2428.6 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=744.41 tps | Avg=978.07 tps | Hit=99.5% | NVMe=2391.6 MB/s (10.83 MB, QD=64) | RSS=72.8 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=681.83 tps | Avg=927.68 tps | Hit=99.5% | NVMe=2356.6 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=196.02 tps | Hit=99.5% (LA:+0.0%) | NVMe=2289.5 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=195.66 tps | Hit=99.5% (LA:+0.1%) | NVMe=2233.6 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=196.16 tps | Hit=99.5% (LA:+0.1%) | NVMe=2206.6 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=196.77 tps | Hit=99.5% (LA:+0.1%) | NVMe=2195.6 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=73.08 MB | Peak=73.08 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2207.65 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.21 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.21 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.09 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.09 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.08 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.08 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.03 | 11 |  1 |  0 |    49.5 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.15 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.15 |  0 |  0 |  0 |   173.2 |
   |   16 |     246 | tok_246        |  170.49 |  98.4% |      55 |  166.39 |    5.13 | 12 |  0 |  0 |     0.0 |
   |   17 |     228 | tok_228        |   91.50 | 100.0% |     246 |   70.88 |    5.13 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.02 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.02 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.01 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.01 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.208s, TTFT=2207.65ms): Avg=927.68 | Min=681.83 | Max=1434.18 tps
   Prefill Chunks (8): C1:256t/1434.2tps/99% | C2:256t/1209.5tps/99% | C3:256t/1093.3tps/99% | C4:256t/986.7tps/99%
                       C5:256t/893.0tps/99% | C6:256t/805.4tps/99% | C7:256t/744.4tps/99% | C8:256t/681.8tps/99%
   Decode  (32 tok, 0.163s): Avg=196.77 | Min=191.96 | Max=199.75 tps
   Latency (ms) : Min=5.01 | P10=5.02 | P25=5.05 | P50=5.08 | P75=5.12 | P90=5.15 | P95=5.21 | P99=5.21 | Max=5.21
   Mean/SD/Jitt : Mean=5.08ms | StdDev=0.05ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=357.28 | Avg=2195.61 | Peak=6038.65 MB/s | WallAmort=5.61 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=4.00 ms | AsyncOverlapped=4.77 ms (54.4% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.64 GB/s | WallAmort=0.60 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.21s (93.1%, 6.19 MB SSD) | Decode=0.16s (6.9%, 1.69 MB SSD)
   CPU Time & Utilization       : User=3.188s + Sys=0.750s (Wall=2.388s) | SysUtil=41.2% | ThrUtil=41.2% | 38.14 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1992.45 ms (  957.9 us/tok | 84.06%)
   MoE AVX2 Q8 Expert Compute   :    249.30 ms (  119.9 us/tok | 10.52%)
   Router + Lookahead Dispatch  :     61.13 ms (   29.4 us/tok |  2.58%)
   LM Head Output Projection    :      6.05 ms (    2.9 us/tok |  0.26%)
   Foreground NVMe Sync Stall   :      4.00 ms (    1.9 us/tok |  0.17%)
   Unaccounted / OMP & Sampling :     57.34 ms (   27.6 us/tok |  2.42%) | Total Wall=2370.27 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    18.54%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.28%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.34%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    76.88%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.96%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1978.82 tps | Avg=1978.82 tps | Hit=99.2% | NVMe=2889.1 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1718.29 tps | Avg=1839.37 tps | Hit=99.2% | NVMe=3855.2 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1763.14 tps | Avg=1813.24 tps | Hit=99.2% | NVMe=4449.8 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1660.23 tps | Avg=1772.40 tps | Hit=99.2% | NVMe=4910.4 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1550.74 tps | Avg=1723.14 tps | Hit=99.2% | NVMe=5272.6 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1457.91 tps | Avg=1672.43 tps | Hit=99.2% | NVMe=5537.2 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1372.01 tps | Avg=1621.70 tps | Hit=99.2% | NVMe=5768.0 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1287.71 tps | Avg=1570.78 tps | Hit=99.2% | NVMe=5960.9 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=179.97 tps | Hit=99.2% (LA:+0.0%) | NVMe=5848.8 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=179.66 tps | Hit=99.2% (LA:+0.1%) | NVMe=5786.1 MB/s (153.28 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=179.17 tps | Hit=99.2% (LA:+0.1%) | NVMe=5683.0 MB/s (154.23 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=179.41 tps | Hit=99.2% (LA:+0.1%) | NVMe=5582.5 MB/s (155.14 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=91.79 MB | Peak=91.79 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1303.81 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    5.67 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    5.67 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    5.53 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    5.53 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    5.51 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    5.51 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    5.53 | 16 |  0 |  0 |    32.0 |
   |   20 |     193 | qtok_193       |   68.95 | 100.0% |      17 |   58.95 |    5.66 | 14 |  2 |  0 |    87.5 |
   |   21 |      63 | qtok_63        |   75.06 |  99.9% |     193 |   67.57 |    5.66 |  0 |  0 |  0 |    87.5 |
   |   10 |     254 | qtok_254       |   70.81 |  99.7% |      66 |   64.77 |    5.62 | 15 |  1 |  0 |    59.8 |
   |   11 |      49 | qtok_49        |   84.60 |  79.6% |     129 |   83.23 |    5.62 |  0 |  0 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.57 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.57 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.54 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.54 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.304s, TTFT=1303.81ms): Avg=1570.78 | Min=1287.71 | Max=1978.82 tps
   Prefill Chunks (8): C1:256t/1978.8tps/99% | C2:256t/1718.3tps/99% | C3:256t/1763.1tps/99% | C4:256t/1660.2tps/99%
                       C5:256t/1550.7tps/99% | C6:256t/1457.9tps/99% | C7:256t/1372.0tps/99% | C8:256t/1287.7tps/99%
   Decode  (32 tok, 0.178s): Avg=179.41 | Min=176.50 | Max=181.59 tps
   Latency (ms) : Min=5.51 | P10=5.53 | P25=5.54 | P50=5.57 | P75=5.62 | P90=5.66 | P95=5.67 | P99=5.67 | Max=5.67
   Mean/SD/Jitt : Mean=5.57ms | StdDev=0.05ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=326.70 | Avg=5582.53 | Peak=11628.06 MB/s | WallAmort=104.67 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=5.41 ms | AsyncOverlapped=26.33 ms (83.0% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.62 GB/s | WallAmort=1.42 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.30s (88.0%, 144.44 MB SSD) | Decode=0.18s (12.0%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.172s + Sys=0.609s (Wall=1.510s) | SysUtil=46.1% | ThrUtil=46.1% | 42.60 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    916.91 ms (  440.8 us/tok | 61.86%)
   MoE AVX2 Q8 Expert Compute   :    372.16 ms (  178.9 us/tok | 25.11%)
   Router + Lookahead Dispatch  :     80.48 ms (   38.7 us/tok |  5.43%)
   LM Head Output Projection    :      5.80 ms (    2.8 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :      5.41 ms (    2.6 us/tok |  0.37%)
   Unaccounted / OMP & Sampling :    101.41 ms (   48.8 us/tok |  6.84%) | Total Wall=1482.17 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    17.29%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.86%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.80%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    70.47%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.58%  |
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
    "ttft_ms": 235.14,
    "avg_tps": 697.46,
    "min_tps": 566.18,
    "max_tps": 786.89
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 145.7,
    "min_tps": 139.35,
    "max_tps": 147.82,
    "p50_ms": 6.84,
    "p90_ms": 6.96,
    "p99_ms": 7.18,
    "mean_ms": 6.86,
    "jitter_ms": 0.07
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
    "avg_mbs": 2128.3,
    "peak_mbs": 6009.62,
    "sync_wait_ms": 1.59,
    "async_overlap_ms": 2.69
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
    "dense_attention": 376.51,
    "moe_compute": 104.08,
    "router_lookahead": 7.35,
    "lm_head": 8.81,
    "unaccounted": 4.48
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 85.83,
    "ram_bandwidth_pinning": 1.91,
    "expert_cache_lrfu": 9.36,
    "lookahead_parallel_overlap": 1.95,
    "ssd_nvme_throughput": 0.95,
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
    "ttft_ms": 306.65,
    "avg_tps": 534.8,
    "min_tps": 378.5,
    "max_tps": 605.8
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 128.16,
    "min_tps": 121.97,
    "max_tps": 131.0,
    "p50_ms": 7.78,
    "p90_ms": 7.92,
    "p99_ms": 8.2,
    "mean_ms": 7.8,
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
    "avg_mbs": 2700.87,
    "peak_mbs": 8794.46,
    "sync_wait_ms": 4.42,
    "async_overlap_ms": 12.29
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
    "dense_attention": 346.06,
    "moe_compute": 200.88,
    "router_lookahead": 8.79,
    "lm_head": 8.43,
    "unaccounted": 42.38
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.54,
    "ram_bandwidth_pinning": 2.18,
    "expert_cache_lrfu": 8.29,
    "lookahead_parallel_overlap": 4.34,
    "ssd_nvme_throughput": 2.65,
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
   System Memory (RAM): 15.99 GB Total / 13.51 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    414.13 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1609.85 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7740.17 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9638.88 MB/s
   RND4K Q32T16 Read                  :    509.05 MB/s (  130316 IOPS)
   RND4K Q1T1  Read                   :    710.76 MB/s (Latency: 5.50 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     59.01 GB/s
   AVX2 256-bit Sequential Write BW   :     47.95 GB/s
   STREAM Triad (A = B + s*C) BW      :     41.90 GB/s
   Random Pointer-Chase Latency       :     48.50 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.35 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    197.20 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     22.12 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 31.00 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 165.62 MB/s (6.18s)
   Window #01 (312.0 MB in 0.53s):   591.37 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.51s):   385.86 MB/s (Uncached Direct Read)
   Window #03 (200.0 MB in 0.50s):   397.61 MB/s (Uncached Direct Read)
   Window #04 (204.0 MB in 0.50s):   406.70 MB/s (Uncached Direct Read)
   Window #05 (112.0 MB in 0.30s):   372.89 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   437.50 MB/s (Min=372.89 | Max=591.37 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 397.09 MB/s (2.58s)
   Window #01 (212.0 MB in 0.54s):   393.95 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   388.31 MB/s (Uncached Direct Read)
   Window #03 (196.0 MB in 0.51s):   388.07 MB/s (Uncached Direct Read)
   Window #04 (216.0 MB in 0.55s):   392.11 MB/s (Uncached Direct Read)
   Window #05 (204.0 MB in 0.49s):   416.69 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   395.60 MB/s (Min=388.07 | Max=416.69 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: glm53 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (0.009 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00001-of-00004.gguf: 100.00% (0.01/0.01 GB) @ 54.8 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (46.470 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  10.76% (5.00/46.47 GB) @ 242.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  21.52% (10.00/46.47 GB) @ 214.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  32.28% (15.00/46.47 GB) @ 226.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  43.04% (20.00/46.47 GB) @ 242.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  53.80% (25.00/46.47 GB) @ 215.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  64.56% (30.00/46.47 GB) @ 222.1 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  75.32% (35.00/46.47 GB) @ 206.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  86.08% (40.00/46.47 GB) @ 214.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf:  96.84% (45.00/46.47 GB) @ 217.2 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00002-of-00004.gguf: 100.00% (46.47/46.47 GB) @ 214.7 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (45.866 GB) -> D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  10.90% (5.00/45.87 GB) @ 194.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  21.80% (10.00/45.87 GB) @ 208.0 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  32.70% (15.00/45.87 GB) @ 244.4 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  43.61% (20.00/45.87 GB) @ 254.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  54.51% (25.00/45.87 GB) @ 256.6 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  65.41% (30.00/45.87 GB) @ 257.9 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  76.31% (35.00/45.87 GB) @ 252.8 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  87.21% (40.00/45.87 GB) @ 256.3 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf:  98.11% (45.00/45.87 GB) @ 250.2 MB/s
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00003-of-00004.gguf: 100.00% (45.87/45.87 GB) @ 251.5 MB/s

[HF-MultiDrive-DL] Streaming unsloth/GLM-5.3-Flash-GGUF/UD-IQ2_XXS/GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (2.506 GB) -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Sequential Non-Truncate)
  [DL] GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf: 100.00% (2.51/2.51 GB) @ 124.7 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf -> C:/apex_c_drive/models/glm53\GLM-5.3-Flash-UD-IQ2_XXS-00004-of-00004.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=101,844,951,904 (94.85 GB) | Elapsed=435.36s
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
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5203.12 MB (555 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=73.8% | NVMe=513.4 MB/s (47437.59 MB, QD=64) | RSS=13591.9 MB
[LIVE-DECODE] 2/32 tok | Avg=0.26 tps | Hit=73.9% (LA:+1.1%) | NVMe=507.3 MB/s (50457.65 MB) | RSS=13594.5 MB
[LIVE-DECODE] 4/32 tok | Avg=0.30 tps | Hit=74.0% (LA:+1.8%) | NVMe=502.3 MB/s (52765.34 MB) | RSS=13595.5 MB
[LIVE-DECODE] 6/32 tok | Avg=0.33 tps | Hit=74.1% (LA:+2.5%) | NVMe=499.0 MB/s (54681.46 MB) | RSS=13578.0 MB
[LIVE-DECODE] 8/32 tok | Avg=0.35 tps | Hit=74.3% (LA:+2.8%) | NVMe=496.1 MB/s (56327.27 MB) | RSS=13519.8 MB
[LIVE-DECODE] 10/32 tok | Avg=0.37 tps | Hit=74.5% (LA:+3.3%) | NVMe=494.0 MB/s (58041.65 MB) | RSS=13496.8 MB
[LIVE-DECODE] 12/32 tok | Avg=0.38 tps | Hit=74.6% (LA:+3.7%) | NVMe=491.3 MB/s (59835.96 MB) | RSS=13465.1 MB
[LIVE-DECODE] 14/32 tok | Avg=0.39 tps | Hit=74.6% (LA:+4.1%) | NVMe=488.8 MB/s (61670.71 MB) | RSS=13465.0 MB
[LIVE-DECODE] 16/32 tok | Avg=0.39 tps | Hit=74.7% (LA:+4.5%) | NVMe=486.6 MB/s (63722.46 MB) | RSS=13457.8 MB
[LIVE-DECODE] 18/32 tok | Avg=0.40 tps | Hit=74.8% (LA:+4.9%) | NVMe=484.4 MB/s (65481.09 MB) | RSS=13435.7 MB
[LIVE-DECODE] 20/32 tok | Avg=0.40 tps | Hit=74.9% (LA:+5.2%) | NVMe=482.9 MB/s (67395.96 MB) | RSS=13416.0 MB
[LIVE-DECODE] 22/32 tok | Avg=0.40 tps | Hit=74.9% (LA:+5.5%) | NVMe=480.5 MB/s (69254.84 MB) | RSS=13371.7 MB
[LIVE-DECODE] 24/32 tok | Avg=0.40 tps | Hit=75.0% (LA:+5.8%) | NVMe=479.0 MB/s (71112.21 MB) | RSS=13343.7 MB
[LIVE-DECODE] 26/32 tok | Avg=0.40 tps | Hit=75.1% (LA:+6.1%) | NVMe=477.0 MB/s (73006.90 MB) | RSS=13331.7 MB
[LIVE-DECODE] 28/32 tok | Avg=0.41 tps | Hit=75.2% (LA:+6.4%) | NVMe=475.8 MB/s (74890.96 MB) | RSS=13293.6 MB
[LIVE-DECODE] 30/32 tok | Avg=0.41 tps | Hit=75.2% (LA:+6.6%) | NVMe=474.5 MB/s (76786.34 MB) | RSS=13266.5 MB
[LIVE-DECODE] 32/32 tok | Avg=0.41 tps | Hit=75.3% (LA:+6.9%) | NVMe=473.2 MB/s (78667.46 MB) | RSS=13258.4 MB

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
   LRFU Cache / Staging Ring    : 5203.12 MB (555/12384 exp = 4.48% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13258.37 MB | Peak=13679.70 MB
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
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 130824.14 |  0 |  0 |  0 |     0.0 |
   |    2 |   24923 |  persistent    |   14.20 |   9.2% |     220 |   14.17 | 3794.95 | 18 |239 | 79 | 1546272.0 |
   |    3 |   54443 |  CUDA          |   14.65 |  11.4% |    9996 |   14.41 | 3794.95 |  0 |  0 |  0 | 1546272.0 |
   |    4 |    4269 |  stream        |   14.37 |  14.3% |   11292 |   13.81 | 2937.33 |100 |166 | 70 | 1181536.0 |
   |    5 |   47414 |  pinned        |   14.48 |  22.4% |   12675 |   13.14 | 2937.33 |  0 |  0 |  0 | 1181536.0 |
   |    6 |   63637 | -memory        |   18.96 |  91.2% |    3468 |   15.18 | 2442.99 |140 |147 | 49 | 981056.0 |
   |    7 |   47414 |  pinned        |   16.01 |  30.3% |    7314 |   15.09 | 2442.99 |  0 |  0 |  0 | 981056.0 |
   |    8 |   63637 | -memory        |   16.32 |  36.5% |   47414 |   15.67 | 2117.74 |185 | 97 | 54 | 842656.0 |
   |   16 |   47414 |  pinned        |   16.87 |  71.1% |   25372 |   13.63 | 2475.94 |153 |109 | 74 | 1050496.0 |
   |   17 |   63637 | -memory        |   19.08 |  72.7% |   47414 |   17.80 | 2475.94 |  0 |  0 |  0 | 1050496.0 |
   |   26 |   47414 |  pinned        |   16.50 |  47.0% |   63637 |   16.31 | 2396.68 |174 | 93 | 69 | 970080.0 |
   |   27 |   63637 | -memory        |   21.82 |  96.1% |   47414 |   18.39 | 2396.68 |  0 |  0 |  0 | 970080.0 |
   |   30 |   47414 |  pinned        |   17.05 |  51.0% |   63637 |   16.85 | 2310.65 |184 | 81 | 71 | 970432.0 |
   |   31 |   63637 | -memory        |   21.56 |  94.1% |   47414 |   18.55 | 2310.65 |  0 |  0 |  0 | 970432.0 |
   |   32 |   63637 | -memory        |   17.13 |  66.4% |   47414 |   16.08 | 2273.25 |169 |102 | 65 | 963136.0 |
   |   33 |   47414 |  pinned        |   21.73 |  98.5% |   63637 |   16.47 | 2273.25 |  0 |  0 |  0 | 963136.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 130.824s, TTFT=130824.14ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:64t/0.5tps/74%
   Decode  (32 tok, 78.012s): Avg=0.41 | Min=0.26 | Max=0.47 tps
   Latency (ms) : Min=2117.74 | P10=2192.51 | P25=2273.25 | P50=2309.06 | P75=2442.99 | P90=2937.33 | P95=3794.95 | P99=3794.95 | Max=3794.95
   Mean/SD/Jitt : Mean=2437.86ms | StdDev=391.93ms | Jitter=92.48ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=18383 (68.39%) | Lookahead=1855 (+6.90%) | ColdMiss=6642 (24.71%) | EFF HIT=75.29%
   Lookahead    : 3217 prefetched -> 1855 consumed (57.7% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.7% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  352 |  77 | 211 | 67.0%|2070.00 | | L24 |  640 |  464 |  41 | 135 | 78.9%|1502.19 |
   | L04 |  640 |  331 |  49 | 260 | 59.4%|2666.56 | | L25 |  640 |  464 |  32 | 144 | 77.5%|1523.75 |
   | L05 |  640 |  349 |  53 | 238 | 62.8%|2371.88 | | L26 |  640 |  466 |  48 | 126 | 80.3%|1430.31 |
   | L06 |  640 |  373 |  61 | 206 | 67.8%|2127.50 | | L27 |  640 |  428 |  53 | 159 | 75.2%|1854.38 |
   | L07 |  640 |  402 |  62 | 176 | 72.5%|1861.56 | | L28 |  640 |  452 |  42 | 146 | 77.2%|1595.62 |
   | L08 |  640 |  416 |  39 | 185 | 71.1%|1969.38 | | L29 |  640 |  438 |  47 | 155 | 75.8%|1696.25 |
   | L09 |  640 |  375 |  45 | 220 | 65.6%|2213.75 | | L30 |  640 |  445 |  40 | 155 | 75.8%|1653.12 |
   | L10 |  640 |  383 |  44 | 213 | 66.7%|2084.38 | | L31 |  640 |  430 |  43 | 167 | 73.9%|1703.44 |
   | L11 |  640 |  416 |  48 | 176 | 72.5%|2409.38 | | L32 |  640 |  417 |  59 | 164 | 74.4%|1825.62 |
   | L12 |  640 |  433 |  48 | 159 | 75.2%|1959.75 | | L33 |  640 |  448 |  43 | 149 | 76.7%|1732.19 |
   | L13 |  640 |  440 |  45 | 155 | 75.8%|1653.12 | | L34 |  640 |  450 |  52 | 138 | 78.4%|1588.44 |
   | L14 |  640 |  454 |  34 | 152 | 76.2%|1653.12 | | L35 |  640 |  449 |  49 | 142 | 77.8%|1552.50 |
   | L15 |  640 |  452 |  34 | 154 | 75.9%|1566.88 | | L36 |  640 |  445 |  45 | 150 | 76.6%|1617.19 |
   | L16 |  640 |  457 |  45 | 138 | 78.4%|1502.19 | | L37 |  640 |  449 |  39 | 152 | 76.2%|1538.12 |
   | L17 |  640 |  453 |  42 | 145 | 77.3%|1566.88 | | L38 |  640 |  449 |  45 | 146 | 77.2%|1581.25 |
   | L18 |  640 |  473 |  31 | 136 | 78.8%|1466.25 | | L39 |  640 |  452 |  53 | 135 | 78.9%|1423.12 |
   | L19 |  640 |  463 |  35 | 142 | 77.8%|1509.38 | | L40 |  640 |  456 |  40 | 144 | 77.5%|1502.19 |
   | L20 |  640 |  462 |  40 | 138 | 78.4%|1581.25 | | L41 |  640 |  471 |  29 | 140 | 78.1%|1372.81 |
   | L21 |  640 |  464 |  50 | 126 | 80.3%|1466.25 | | L42 |  640 |  490 |  25 | 125 | 80.5%|1229.06 |
   | L22 |  640 |  465 |  45 | 130 | 79.7%|1495.00 | | L43 |  640 |  491 |  36 | 113 | 82.3%|1236.25 |
   | L23 |  640 |  437 |  39 | 164 | 74.4%|1796.88 | | L44 |  640 |  479 |  28 | 133 | 79.2%|1809.00 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 78667.46 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=31229.88 MB)
   SSD Data/Token (Decode)      : Avg=975.934 MB/tok (Min=822.906 | P50=942.031 | P95=1510.031 | Max=1510.031 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1327 Batches | 30980 Raw -> 30656 Merged (324 LBA Merges, Avg 2627.7 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=29777
   SSD Read Bandwidth (Active)  : Min=0.45 | Avg=473.23 | Peak=3458.02 MB/s | WallAmort=376.70 MB/s
   OS Kernel I/O Verification   : Read=78676.49 MB | Write=0.00 MB | Syscalls=34692
   Sync Stall vs Async DMA      : SyncStall=96870.27 ms | AsyncOverlapped=151459.49 ms (61.0% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=6.53 GB/s | WallAmort=2.34 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=130.82s (62.6%, 41075.75 MB SSD) | Decode=78.01s (37.4%, 31229.88 MB SSD)
   CPU Time & Utilization       : User=239.047s + Sys=8.141s (Wall=227.252s) | SysUtil=27.2% | ThrUtil=27.2% | 25.15 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  30318.52 ms (315817.9 us/tok | 14.52%)
   MoE AVX2 Q8 Expert Compute   :  43455.66 ms (452663.1 us/tok | 20.81%)
   Router + Lookahead Dispatch  :    689.73 ms ( 7184.6 us/tok |  0.33%)
   LM Head Output Projection    :    885.35 ms ( 9222.4 us/tok |  0.42%)
   Foreground NVMe Sync Stall   :  96870.27 ms (1009065.3 us/tok | 46.39%)
   Unaccounted / OMP & Sampling :  36616.20 ms (381418.8 us/tok | 17.53%) | Total Wall=208835.72 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    40.43%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    19.90%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.21%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.29%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.17%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 230s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 13.95 GB Available
   Active Drive Space : 150.00 GB Total / 54.59 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    433.08 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1615.54 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7583.39 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9863.34 MB/s
   RND4K Q32T16 Read                  :    448.73 MB/s (  114875 IOPS)
   RND4K Q1T1  Read                   :    687.33 MB/s (Latency: 5.68 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     54.76 GB/s
   AVX2 256-bit Sequential Write BW   :     45.81 GB/s
   STREAM Triad (A = B + s*C) BW      :     39.39 GB/s
   Random Pointer-Chase Latency       :     54.54 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.26 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    189.94 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.06 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=73.6% | NVMe=522.1 MB/s (51661.71 MB, QD=64) | RSS=13947.8 MB

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
   LRFU Cache / Staging Ring    : 5550.00 MB (592/12384 exp = 4.78% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13431.58 MB | Peak=14027.35 MB
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
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 142742.15 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   20.50 |  79.8% |   15724 |   19.10 | 3801.04 | 20 |239 | 77 | 1512544.0 |
   |    3 |    1339 | >\n\n          |   14.01 |  20.8% |     397 |   12.96 | 3801.04 |  0 |  0 |  0 | 1512544.0 |
   |    4 |   10056 | Let            |   15.28 |  31.5% |     334 |   14.78 | 2625.59 |142 |135 | 59 | 996096.0 |
   |    5 |     752 |  me            |   16.52 |  72.1% |     594 |   14.85 | 2625.59 |  0 |  0 |  0 | 996096.0 |
   |    6 |    1744 |  think         |   15.53 |  38.0% |   23578 |   13.60 | 2827.05 |120 |166 | 50 | 1071552.0 |
   |    7 |    1526 |  through       |   17.47 |  63.7% |   15504 |   14.79 | 2827.05 |  0 |  0 |  0 | 1071552.0 |
   |    8 |     419 |  this          |   17.34 |  55.6% |     279 |   16.09 | 2959.89 |107 |175 | 54 | 1147072.0 |
   |    9 |   15504 |  carefully     |   14.89 |   6.9% |    3019 |   14.71 | 2959.89 |  0 |  0 |  0 | 1147072.0 |
   |   12 |   32559 |  reasoning     |   14.05 |   8.5% |    1681 |   14.01 | 2661.75 |124 |156 | 56 | 1064640.0 |
   |   13 |    1526 |  through       |   16.95 |  33.1% |    1128 |   15.76 | 2661.75 |  0 |  0 |  0 | 1064640.0 |
   |   10 |    1128 |  what          |   16.98 |  28.3% |      13 |   16.45 | 2628.82 |117 |177 | 42 | 1061216.0 |
   |   62 |    1526 |  through       |   17.43 |  49.9% |     594 |   17.31 | 2427.02 |180 | 71 | 85 | 1035424.0 |
   |   63 |     594 | 's             |   21.37 |  93.3% |    1526 |   17.99 | 2427.02 |  0 |  0 |  0 | 1035424.0 |
   |   64 |     594 | 's             |   17.28 |  49.5% |    1526 |   17.16 | 2603.95 |160 |104 | 72 | 1093440.0 |
   |   65 |    1526 |  through       |   21.46 |  88.7% |     594 |   18.70 | 2603.95 |  0 |  0 |  0 | 1093440.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 142.742s, TTFT=142742.15ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:70t/0.5tps/74%
   Decode  (64 tok, 150.785s): Avg=0.42 | Min=0.26 | Max=0.62 tps
   Latency (ms) : Min=1621.78 | P10=1900.18 | P25=2147.78 | P50=2356.84 | P75=2603.95 | P90=2661.75 | P95=2959.89 | P99=3801.04 | Max=3801.04
   Mean/SD/Jitt : Mean=2356.01ms | StdDev=402.02ms | Jitter=143.41ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=22521 (65.71%) | Lookahead=3727 (+10.87%) | ColdMiss=8024 (23.41%) | EFF HIT=76.59%
   Lookahead    : 6501 prefetched -> 3727 consumed (57.3% util) | Warmup >=75%:21t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64= 76.6% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  475 | 131 | 210 | 74.3%|2450.94 | | L24 |  816 |  579 |  83 | 154 | 81.1%|2170.62 |
   | L04 |  816 |  438 | 116 | 262 | 67.9%|3478.75 | | L25 |  816 |  569 |  62 | 185 | 77.3%|2371.88 |
   | L05 |  816 |  442 | 106 | 268 | 67.2%|3306.25 | | L26 |  816 |  554 |  89 | 173 | 78.8%|2307.19 |
   | L06 |  816 |  479 |  99 | 238 | 70.8%|2846.25 | | L27 |  816 |  538 | 104 | 174 | 78.7%|2515.62 |
   | L07 |  816 |  498 | 120 | 198 | 75.7%|2645.00 | | L28 |  816 |  521 |  97 | 198 | 75.7%|2565.94 |
   | L08 |  816 |  516 |  59 | 241 | 70.5%|3040.31 | | L29 |  816 |  531 |  98 | 187 | 77.1%|2522.81 |
   | L09 |  816 |  457 |  97 | 262 | 67.9%|3212.81 | | L30 |  816 |  531 |  80 | 205 | 74.9%|2515.62 |
   | L10 |  816 |  471 | 104 | 241 | 70.5%|2968.44 | | L31 |  816 |  514 | 107 | 195 | 76.1%|2637.81 |
   | L11 |  816 |  469 | 104 | 243 | 70.2%|4087.50 | | L32 |  816 |  513 | 119 | 184 | 77.5%|2666.56 |
   | L12 |  816 |  526 |  75 | 215 | 73.7%|3115.50 | | L33 |  816 |  573 |  86 | 157 | 80.8%|2206.56 |
   | L13 |  816 |  554 |  63 | 199 | 75.6%|2357.50 | | L34 |  816 |  511 | 121 | 184 | 77.5%|2522.81 |
   | L14 |  816 |  541 |  67 | 208 | 74.5%|2731.25 | | L35 |  816 |  527 | 116 | 173 | 78.8%|2400.62 |
   | L15 |  816 |  541 |  98 | 177 | 78.3%|2379.06 | | L36 |  816 |  534 | 102 | 180 | 77.9%|2379.06 |
   | L16 |  816 |  554 |  75 | 187 | 77.1%|2278.44 | | L37 |  816 |  554 |  91 | 171 | 79.0%|2199.38 |
   | L17 |  816 |  557 |  51 | 208 | 74.5%|2371.88 | | L38 |  816 |  565 |  88 | 163 | 80.0%|2228.12 |
   | L18 |  816 |  596 |  56 | 164 | 79.9%|2127.50 | | L39 |  816 |  546 | 104 | 166 | 79.7%|2185.00 |
   | L19 |  816 |  580 |  71 | 165 | 79.8%|2084.38 | | L40 |  816 |  496 | 109 | 211 | 74.1%|2910.94 |
   | L20 |  816 |  617 |  54 | 145 | 82.2%|1796.88 | | L41 |  816 |  544 |  98 | 174 | 78.7%|2328.75 |
   | L21 |  816 |  591 |  74 | 151 | 81.5%|2055.62 | | L42 |  816 |  593 |  56 | 167 | 79.5%|2077.19 |
   | L22 |  816 |  582 |  69 | 165 | 79.8%|2314.38 | | L43 |  816 |  596 |  69 | 151 | 81.5%|2105.94 |
   | L23 |  816 |  583 |  73 | 160 | 80.4%|1983.75 | | L44 |  816 |  565 |  86 | 165 | 79.8%|2730.25 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 113116.27 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=61454.56 MB)
   SSD Data/Token (Decode)      : Avg=960.228 MB/tok (Min=689.969 | P50=972.750 | P95=1120.188 | Max=1477.094 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2508 Batches | 45056 Raw -> 44547 Merged (509 LBA Merges, Avg 2600.2 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=43668
   SSD Read Bandwidth (Active)  : Min=0.32 | Avg=471.23 | Peak=4404.65 MB/s | WallAmort=385.37 MB/s (100.0% of 433.1 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=114103.31 MB | Write=128.00 MB | Syscalls=56121
   Sync Stall vs Async DMA      : SyncStall=118823.89 ms | AsyncOverlapped=225196.83 ms (65.5% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=7.59 GB/s (19.3% STREAM) | WallAmort=2.65 GB/s (Max=39.39 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=142.74s (48.6%, 45299.88 MB SSD) | Decode=150.78s (51.4%, 61454.56 MB SSD)
   CPU Time & Utilization       : User=315.250s + Sys=13.469s (Wall=313.072s) | SysUtil=26.2% | ThrUtil=26.2% | 49.86 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  40856.26 ms (304897.5 us/tok | 13.92%)
   MoE AVX2 Q8 Expert Compute   :  59914.90 ms (447126.1 us/tok | 20.41%)
   Router + Lookahead Dispatch  :    896.89 ms ( 6693.2 us/tok |  0.31%)
   LM Head Output Projection    :   1625.30 ms (12129.1 us/tok |  0.55%)
   Foreground NVMe Sync Stall   : 118823.89 ms (886745.4 us/tok | 40.48%)
   Unaccounted / OMP & Sampling :  71409.45 ms (532906.4 us/tok | 24.33%) | Total Wall=293526.69 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    37.02%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    23.24%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.65%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.46%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.63%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5587.50 MB (596 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.79 tps | Avg=0.79 tps | Hit=89.2% | NVMe=524.1 MB/s (74277.59 MB, QD=64) | RSS=14063.4 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.78 tps | Avg=0.78 tps | Hit=88.9% | NVMe=529.4 MB/s (145295.52 MB, QD=64) | RSS=14064.4 MB
[LIVE-DECODE] 2/128 tok | Avg=0.24 tps | Hit=88.9% (LA:+0.1%) | NVMe=526.6 MB/s (148504.46 MB) | RSS=14001.6 MB
[LIVE-DECODE] 4/128 tok | Avg=0.27 tps | Hit=88.9% (LA:+0.2%) | NVMe=523.5 MB/s (150963.96 MB) | RSS=13819.5 MB
[LIVE-DECODE] 6/128 tok | Avg=0.29 tps | Hit=88.8% (LA:+0.3%) | NVMe=521.2 MB/s (153161.96 MB) | RSS=13722.8 MB
[LIVE-DECODE] 8/128 tok | Avg=0.31 tps | Hit=88.8% (LA:+0.4%) | NVMe=519.5 MB/s (155246.96 MB) | RSS=13671.2 MB
[LIVE-DECODE] 10/128 tok | Avg=0.31 tps | Hit=88.8% (LA:+0.4%) | NVMe=517.5 MB/s (157532.27 MB) | RSS=13608.6 MB
[LIVE-DECODE] 12/128 tok | Avg=0.32 tps | Hit=88.8% (LA:+0.5%) | NVMe=515.6 MB/s (159631.59 MB) | RSS=13563.9 MB
[LIVE-DECODE] 14/128 tok | Avg=0.32 tps | Hit=88.8% (LA:+0.6%) | NVMe=513.7 MB/s (161874.96 MB) | RSS=13494.8 MB
[LIVE-DECODE] 16/128 tok | Avg=0.33 tps | Hit=88.8% (LA:+0.7%) | NVMe=512.4 MB/s (163925.21 MB) | RSS=13487.4 MB
[LIVE-DECODE] 18/128 tok | Avg=0.33 tps | Hit=88.7% (LA:+0.8%) | NVMe=510.8 MB/s (166300.09 MB) | RSS=13487.3 MB
[LIVE-DECODE] 20/128 tok | Avg=0.33 tps | Hit=88.7% (LA:+0.8%) | NVMe=509.4 MB/s (168625.59 MB) | RSS=13487.3 MB
[LIVE-DECODE] 22/128 tok | Avg=0.34 tps | Hit=88.7% (LA:+0.9%) | NVMe=508.4 MB/s (170615.90 MB) | RSS=13487.4 MB
[LIVE-DECODE] 24/128 tok | Avg=0.35 tps | Hit=88.7% (LA:+1.0%) | NVMe=507.7 MB/s (172457.90 MB) | RSS=13487.4 MB
[LIVE-DECODE] 26/128 tok | Avg=0.35 tps | Hit=88.7% (LA:+1.1%) | NVMe=506.4 MB/s (174613.15 MB) | RSS=13487.3 MB
[LIVE-DECODE] 28/128 tok | Avg=0.35 tps | Hit=88.7% (LA:+1.1%) | NVMe=505.3 MB/s (176746.52 MB) | RSS=13487.3 MB
[LIVE-DECODE] 30/128 tok | Avg=0.36 tps | Hit=88.6% (LA:+1.2%) | NVMe=504.5 MB/s (178774.27 MB) | RSS=13487.3 MB
[LIVE-DECODE] 32/128 tok | Avg=0.36 tps | Hit=88.6% (LA:+1.2%) | NVMe=504.0 MB/s (180521.84 MB) | RSS=13487.3 MB
[LIVE-DECODE] 34/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.3%) | NVMe=503.5 MB/s (182249.40 MB) | RSS=13487.3 MB
[LIVE-DECODE] 36/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.4%) | NVMe=502.3 MB/s (184559.21 MB) | RSS=13487.3 MB
[LIVE-DECODE] 38/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.4%) | NVMe=501.3 MB/s (186649.71 MB) | RSS=13487.3 MB
[LIVE-DECODE] 40/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.5%) | NVMe=500.5 MB/s (188617.27 MB) | RSS=13482.9 MB
[LIVE-DECODE] 42/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.5%) | NVMe=499.8 MB/s (190469.59 MB) | RSS=13482.9 MB
[LIVE-DECODE] 44/128 tok | Avg=0.37 tps | Hit=88.5% (LA:+1.6%) | NVMe=498.9 MB/s (192667.21 MB) | RSS=13487.3 MB
[LIVE-DECODE] 46/128 tok | Avg=0.37 tps | Hit=88.5% (LA:+1.7%) | NVMe=498.2 MB/s (194748.46 MB) | RSS=13487.3 MB
[LIVE-DECODE] 48/128 tok | Avg=0.37 tps | Hit=88.5% (LA:+1.8%) | NVMe=497.3 MB/s (196906.09 MB) | RSS=13487.3 MB
[LIVE-DECODE] 50/128 tok | Avg=0.38 tps | Hit=88.5% (LA:+1.8%) | NVMe=496.7 MB/s (198765.46 MB) | RSS=13487.3 MB
[LIVE-DECODE] 52/128 tok | Avg=0.38 tps | Hit=88.5% (LA:+1.9%) | NVMe=496.0 MB/s (200648.21 MB) | RSS=13487.3 MB
[LIVE-DECODE] 54/128 tok | Avg=0.38 tps | Hit=88.5% (LA:+1.9%) | NVMe=495.2 MB/s (202595.46 MB) | RSS=13477.9 MB
[LIVE-DECODE] 56/128 tok | Avg=0.38 tps | Hit=88.4% (LA:+2.0%) | NVMe=494.4 MB/s (204736.84 MB) | RSS=13477.9 MB
[LIVE-DECODE] 58/128 tok | Avg=0.38 tps | Hit=88.4% (LA:+2.0%) | NVMe=493.9 MB/s (206676.59 MB) | RSS=13477.9 MB
[LIVE-DECODE] 60/128 tok | Avg=0.38 tps | Hit=88.4% (LA:+2.1%) | NVMe=493.1 MB/s (208921.27 MB) | RSS=13477.9 MB
[LIVE-DECODE] 62/128 tok | Avg=0.38 tps | Hit=88.4% (LA:+2.1%) | NVMe=492.7 MB/s (210691.21 MB) | RSS=13477.9 MB
[LIVE-DECODE] 64/128 tok | Avg=0.39 tps | Hit=88.4% (LA:+2.2%) | NVMe=492.2 MB/s (212524.96 MB) | RSS=13487.3 MB
[LIVE-DECODE] 66/128 tok | Avg=0.39 tps | Hit=88.4% (LA:+2.3%) | NVMe=491.5 MB/s (214584.15 MB) | RSS=13487.3 MB
[LIVE-DECODE] 68/128 tok | Avg=0.39 tps | Hit=88.4% (LA:+2.3%) | NVMe=491.0 MB/s (216439.34 MB) | RSS=13487.3 MB
[LIVE-DECODE] 70/128 tok | Avg=0.39 tps | Hit=88.4% (LA:+2.4%) | NVMe=491.0 MB/s (218265.90 MB) | RSS=13496.7 MB
[LIVE-DECODE] 72/128 tok | Avg=0.39 tps | Hit=88.3% (LA:+2.4%) | NVMe=490.7 MB/s (220025.77 MB) | RSS=13496.7 MB
[LIVE-DECODE] 74/128 tok | Avg=0.39 tps | Hit=88.3% (LA:+2.5%) | NVMe=490.5 MB/s (221728.84 MB) | RSS=13496.7 MB
[LIVE-DECODE] 76/128 tok | Avg=0.39 tps | Hit=88.3% (LA:+2.5%) | NVMe=490.1 MB/s (223579.27 MB) | RSS=13496.7 MB
[LIVE-DECODE] 78/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.5%) | NVMe=489.7 MB/s (225411.71 MB) | RSS=13496.7 MB
[LIVE-DECODE] 80/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.6%) | NVMe=489.3 MB/s (227409.09 MB) | RSS=13496.7 MB
[LIVE-DECODE] 82/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.6%) | NVMe=488.9 MB/s (229313.46 MB) | RSS=13496.7 MB
[LIVE-DECODE] 84/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.7%) | NVMe=488.4 MB/s (231090.65 MB) | RSS=13477.9 MB
[LIVE-DECODE] 86/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.7%) | NVMe=487.9 MB/s (232962.46 MB) | RSS=13477.9 MB
[LIVE-DECODE] 88/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.8%) | NVMe=487.5 MB/s (234761.15 MB) | RSS=13477.9 MB
[LIVE-DECODE] 90/128 tok | Avg=0.40 tps | Hit=88.2% (LA:+2.8%) | NVMe=487.1 MB/s (236870.40 MB) | RSS=13477.9 MB
[LIVE-DECODE] 92/128 tok | Avg=0.40 tps | Hit=88.2% (LA:+2.8%) | NVMe=486.8 MB/s (238604.46 MB) | RSS=13477.9 MB
[LIVE-DECODE] 94/128 tok | Avg=0.40 tps | Hit=88.2% (LA:+2.9%) | NVMe=486.5 MB/s (240339.77 MB) | RSS=13477.9 MB
[LIVE-DECODE] 96/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+2.9%) | NVMe=486.2 MB/s (241964.84 MB) | RSS=13477.9 MB
[LIVE-DECODE] 98/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+2.9%) | NVMe=485.9 MB/s (243708.77 MB) | RSS=13477.9 MB
[LIVE-DECODE] 100/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+3.0%) | NVMe=485.5 MB/s (245508.15 MB) | RSS=13477.9 MB
[LIVE-DECODE] 102/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+3.0%) | NVMe=485.3 MB/s (247169.34 MB) | RSS=13477.9 MB
[LIVE-DECODE] 104/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+3.0%) | NVMe=485.1 MB/s (248673.09 MB) | RSS=13477.9 MB
[LIVE-DECODE] 106/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.1%) | NVMe=484.5 MB/s (250988.59 MB) | RSS=13472.6 MB
[LIVE-DECODE] 108/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.1%) | NVMe=484.2 MB/s (252761.21 MB) | RSS=13463.9 MB
[LIVE-DECODE] 110/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.1%) | NVMe=483.8 MB/s (254899.77 MB) | RSS=13477.9 MB
[LIVE-DECODE] 112/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.2%) | NVMe=483.2 MB/s (257283.84 MB) | RSS=13496.6 MB
[LIVE-DECODE] 114/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.3%) | NVMe=482.8 MB/s (259204.96 MB) | RSS=13496.6 MB
[LIVE-DECODE] 116/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.3%) | NVMe=482.5 MB/s (260941.46 MB) | RSS=13496.7 MB
[LIVE-DECODE] 118/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.4%) | NVMe=482.1 MB/s (262842.34 MB) | RSS=13496.7 MB
[LIVE-DECODE] 120/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.4%) | NVMe=481.6 MB/s (264711.02 MB) | RSS=13496.6 MB
[LIVE-DECODE] 122/128 tok | Avg=0.41 tps | Hit=88.0% (LA:+3.5%) | NVMe=481.4 MB/s (266394.34 MB) | RSS=13496.7 MB
[LIVE-DECODE] 124/128 tok | Avg=0.41 tps | Hit=88.0% (LA:+3.5%) | NVMe=481.1 MB/s (268115.21 MB) | RSS=13496.7 MB
[LIVE-DECODE] 126/128 tok | Avg=0.41 tps | Hit=88.0% (LA:+3.6%) | NVMe=481.0 MB/s (269794.84 MB) | RSS=13496.7 MB
[LIVE-DECODE] 128/128 tok | Avg=0.42 tps | Hit=88.0% (LA:+3.6%) | NVMe=480.9 MB/s (271300.27 MB) | RSS=13496.7 MB

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
   LRFU Cache / Staging Ring    : 5587.50 MB (596/12384 exp = 4.81% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13496.68 MB | Peak=14128.75 MB
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
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 653146.29 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   21.27 |  96.3% |    1062 |   17.44 | 4173.03 | 43 |175 |118 | 1642976.0 |
   |    3 |   22412 | -co            |   14.00 |  19.9% |   11492 |   13.04 | 4173.03 |  0 |  0 |  0 | 1642976.0 |
   |    4 |    3831 | ales           |   20.23 |  56.4% |     278 |   19.95 | 3330.63 | 89 |171 | 76 | 1259264.0 |
   |    5 |    1998 | ced            |   23.84 |  95.9% |    6125 |   20.05 | 3330.63 |  0 |  0 |  0 | 1259264.0 |
   |    6 |     291 | ed             |   13.00 |  12.2% |      11 |   12.82 | 2855.43 |123 |145 | 68 | 1125376.0 |
   |    7 |     291 | ed             |   17.54 |  71.5% |   11492 |   15.78 | 2855.43 |  0 |  0 |  0 | 1125376.0 |
   |    8 |   39929 |  LB            |   16.46 |  74.9% |      11 |   14.17 | 2679.34 |152 |123 | 61 | 1067520.0 |
   |  112 |      12 | -              |   17.05 |  71.2% |     220 |   14.83 | 3200.16 |100 |162 | 74 | 1220640.0 |
   |  113 |      17 | 2              |   22.18 |  99.2% |      16 |   15.80 | 3200.16 |  0 |  0 |  0 | 1220640.0 |
   |   18 |   10772 | GE             |   14.71 |  27.6% |    3391 |   13.95 | 2945.24 |114 |139 | 83 | 1215936.0 |
   |   19 |    9772 | -and           |   15.11 |  24.5% |      12 |   14.29 | 2945.24 |  0 |  0 |  0 | 1215936.0 |
   |  126 |   10772 | GE             |   14.45 |  16.7% |    2646 |   14.40 | 1948.58 |193 | 92 | 51 | 859968.0 |
   |  127 |   50127 | KK             |   13.12 |  16.3% |      42 |   12.88 | 1948.58 |  0 |  0 |  0 | 859968.0 |
   |  128 |   50127 | KK             |   14.93 |  24.1% |      42 |   14.93 | 1783.38 |211 | 86 | 39 | 770784.0 |
   |  129 |   10772 | GE             |   18.90 |  83.6% |   22197 |   15.87 | 1783.38 |  0 |  0 |  0 | 770784.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 653.146s, TTFT=653146.29ms): Avg=0.78 | Min=0.78 | Max=0.79 tps
   Prefill Chunks (2): C1:256t/0.8tps/89% | C2:256t/0.8tps/89%
   Decode  (128 tok, 307.638s): Avg=0.42 | Min=0.24 | Max=0.56 tps
   Latency (ms) : Min=1774.11 | P10=1986.13 | P25=2127.93 | P50=2317.54 | P75=2669.86 | P90=2866.66 | P95=2945.24 | P99=4173.03 | Max=4173.03
   Mean/SD/Jitt : Mean=2403.42ms | StdDev=400.35ms | Jitter=138.04ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=163422 (84.44%) | Lookahead=6970 (+3.60%) | ColdMiss=23144 (11.96%) | EFF HIT=88.04%
   Lookahead    : 12994 prefetched -> 6970 consumed (53.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 88.8% | @64= 88.4% | @128= 88.0% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3720 | 331 | 557 | 87.9%|6382.50 | | L24 | 4608 | 3996 | 122 | 490 | 89.4%|5146.25 |
   | L04 | 4608 | 3802 | 163 | 643 | 86.0%|7568.44 | | L25 | 4608 | 3917 | 140 | 551 | 88.0%|6475.94 |
   | L05 | 4608 | 3763 | 183 | 662 | 85.6%|7784.06 | | L26 | 4608 | 3951 | 152 | 505 | 89.0%|5663.75 |
   | L06 | 4608 | 3754 | 225 | 629 | 86.3%|7065.31 | | L27 | 4608 | 3863 | 169 | 576 | 87.5%|6871.25 |
   | L07 | 4608 | 3879 | 202 | 527 | 88.6%|5900.94 | | L28 | 4608 | 3848 | 189 | 571 | 87.6%|6418.44 |
   | L08 | 4608 | 3882 | 136 | 590 | 87.2%|6820.94 | | L29 | 4608 | 3881 | 202 | 525 | 88.6%|5994.38 |
   | L09 | 4608 | 3861 | 158 | 589 | 87.2%|6281.88 | | L30 | 4608 | 3811 | 198 | 599 | 87.0%|6806.56 |
   | L10 | 4608 | 3842 | 150 | 616 | 86.6%|6382.50 | | L31 | 4608 | 3836 | 140 | 632 | 86.3%|7058.12 |
   | L11 | 4608 | 3872 | 176 | 560 | 87.8%|8137.50 | | L32 | 4608 | 3807 | 165 | 636 | 86.2%|7007.81 |
   | L12 | 4608 | 3899 | 170 | 539 | 88.3%|6976.38 | | L33 | 4608 | 3823 | 194 | 591 | 87.2%|7015.00 |
   | L13 | 4608 | 3956 | 138 | 514 | 88.8%|5735.62 | | L34 | 4608 | 3847 | 233 | 528 | 88.5%|6267.50 |
   | L14 | 4608 | 3964 | 106 | 538 | 88.3%|5721.25 | | L35 | 4608 | 3813 | 226 | 569 | 87.7%|6634.06 |
   | L15 | 4608 | 3927 | 138 | 543 | 88.2%|5893.75 | | L36 | 4608 | 3802 | 264 | 542 | 88.2%|6461.56 |
   | L16 | 4608 | 3929 | 157 | 522 | 88.7%|5685.31 | | L37 | 4608 | 3893 | 180 | 535 | 88.4%|5699.69 |
   | L17 | 4608 | 3916 | 123 | 569 | 87.7%|6281.88 | | L38 | 4608 | 3880 | 186 | 542 | 88.2%|6188.44 |
   | L18 | 4608 | 3985 | 112 | 511 | 88.9%|5764.38 | | L39 | 4608 | 3862 | 204 | 542 | 88.2%|6059.06 |
   | L19 | 4608 | 3980 | 125 | 503 | 89.1%|5656.56 | | L40 | 4608 | 3870 | 184 | 554 | 88.0%|6253.12 |
   | L20 | 4608 | 3978 | 125 | 505 | 89.0%|5412.19 | | L41 | 4608 | 3953 | 138 | 517 | 88.8%|5541.56 |
   | L21 | 4608 | 3974 | 138 | 496 | 89.2%|5304.38 | | L42 | 4608 | 4013 | 104 | 491 | 89.3%|5433.75 |
   | L22 | 4608 | 3982 | 140 | 486 | 89.5%|5541.56 | | L43 | 4608 | 4022 | 117 | 469 | 89.8%|5052.81 |
   | L23 | 4608 | 3928 | 145 | 535 | 88.4%|5987.19 | | L44 | 4608 | 3941 | 122 | 545 | 88.2%|7336.50 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 271300.27 MB (Load=6361.84 | Prefill=138933.69 | Warmup=0.00 | Decode=126004.75 MB)
   SSD Data/Token (Decode)      : Avg=984.412 MB/tok (Min=751.875 | P50=952.188 | P95=1187.438 | Max=1604.469 MB) | Prefill=271.355 MB/tok
   NVMe Batches / Requests      : 5189 Batches | 110135 Raw -> 108758 Merged (1377 LBA Merges, Avg 2554.4 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=107879
   SSD Read Bandwidth (Active)  : Min=0.47 | Avg=480.91 | Peak=4142.25 MB/s | WallAmort=282.37 MB/s
   OS Kernel I/O Verification   : Read=271309.31 MB | Write=0.01 MB | Syscalls=112843
   Sync Stall vs Async DMA      : SyncStall=334178.54 ms | AsyncOverlapped=549247.48 ms (62.2% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=5.82 GB/s | WallAmort=2.90 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=653.15s (68.0%, 138933.69 MB SSD) | Decode=307.64s (32.0%, 126004.75 MB SSD)
   CPU Time & Utilization       : User=1622.875s + Sys=27.469s (Wall=979.608s) | SysUtil=42.1% | ThrUtil=42.1% | 38.96 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 213441.83 ms (333502.9 us/tok | 22.22%)
   MoE AVX2 Q8 Expert Compute   : 261571.51 ms (408705.5 us/tok | 27.22%)
   Router + Lookahead Dispatch  :   4513.38 ms ( 7052.2 us/tok |  0.47%)
   LM Head Output Projection    :   3377.91 ms ( 5278.0 us/tok |  0.35%)
   Foreground NVMe Sync Stall   : 334178.54 ms (522154.0 us/tok | 34.78%)
   Unaccounted / OMP & Sampling : 143700.85 ms (224532.6 us/tok | 14.96%) | Total Wall=960784.02 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    59.79%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.28%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    16.86%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.98%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.09%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 855K Nov 13 16:36 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 855K Nov 13 16:36 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.50 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    476.72 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1495.09 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7628.40 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10062.26 MB/s
   RND4K Q32T16 Read                  :    481.78 MB/s (  123335 IOPS)
   RND4K Q1T1  Read                   :    720.64 MB/s (Latency: 5.42 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     60.78 GB/s
   AVX2 256-bit Sequential Write BW   :     48.98 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.29 GB/s
   Random Pointer-Chase Latency       :     52.70 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.35 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    197.50 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     22.42 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1434.18 tps | Avg=1434.18 tps | Hit=99.5% | NVMe=2531.9 MB/s (6.19 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1209.48 tps | Avg=1312.28 tps | Hit=99.5% | NVMe=2498.6 MB/s (7.01 MB, QD=64) | RSS=71.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1093.31 tps | Avg=1230.15 tps | Hit=99.5% | NVMe=2473.4 MB/s (7.78 MB, QD=64) | RSS=71.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=986.74 tps | Avg=1158.69 tps | Hit=99.5% | NVMe=2483.2 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=893.01 tps | Avg=1093.62 tps | Hit=99.5% | NVMe=2493.6 MB/s (9.33 MB, QD=64) | RSS=72.3 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=805.38 tps | Avg=1032.06 tps | Hit=99.5% | NVMe=2428.6 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=744.41 tps | Avg=978.07 tps | Hit=99.5% | NVMe=2391.6 MB/s (10.83 MB, QD=64) | RSS=72.8 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=681.83 tps | Avg=927.68 tps | Hit=99.5% | NVMe=2356.6 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=196.02 tps | Hit=99.5% (LA:+0.0%) | NVMe=2289.5 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=195.66 tps | Hit=99.5% (LA:+0.1%) | NVMe=2233.6 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=196.16 tps | Hit=99.5% (LA:+0.1%) | NVMe=2206.6 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=196.77 tps | Hit=99.5% (LA:+0.1%) | NVMe=2195.6 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=73.08 MB | Peak=73.08 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2207.65 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.21 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.21 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.09 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.09 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.08 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.08 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.03 | 11 |  1 |  0 |    49.5 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.15 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.15 |  0 |  0 |  0 |   173.2 |
   |   16 |     246 | tok_246        |  170.49 |  98.4% |      55 |  166.39 |    5.13 | 12 |  0 |  0 |     0.0 |
   |   17 |     228 | tok_228        |   91.50 | 100.0% |     246 |   70.88 |    5.13 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.02 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.02 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.01 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.01 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.208s, TTFT=2207.65ms): Avg=927.68 | Min=681.83 | Max=1434.18 tps
   Prefill Chunks (8): C1:256t/1434.2tps/99% | C2:256t/1209.5tps/99% | C3:256t/1093.3tps/99% | C4:256t/986.7tps/99%
                       C5:256t/893.0tps/99% | C6:256t/805.4tps/99% | C7:256t/744.4tps/99% | C8:256t/681.8tps/99%
   Decode  (32 tok, 0.163s): Avg=196.77 | Min=191.96 | Max=199.75 tps
   Latency (ms) : Min=5.01 | P10=5.02 | P25=5.05 | P50=5.08 | P75=5.12 | P90=5.15 | P95=5.21 | P99=5.21 | Max=5.21
   Mean/SD/Jitt : Mean=5.08ms | StdDev=0.05ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=357.28 | Avg=2195.61 | Peak=6038.65 MB/s | WallAmort=5.61 MB/s
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=4.00 ms | AsyncOverlapped=4.77 ms (54.4% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.64 GB/s | WallAmort=0.60 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.21s (93.1%, 6.19 MB SSD) | Decode=0.16s (6.9%, 1.69 MB SSD)
   CPU Time & Utilization       : User=3.188s + Sys=0.750s (Wall=2.388s) | SysUtil=41.2% | ThrUtil=41.2% | 38.14 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1992.45 ms (  957.9 us/tok | 84.06%)
   MoE AVX2 Q8 Expert Compute   :    249.30 ms (  119.9 us/tok | 10.52%)
   Router + Lookahead Dispatch  :     61.13 ms (   29.4 us/tok |  2.58%)
   LM Head Output Projection    :      6.05 ms (    2.9 us/tok |  0.26%)
   Foreground NVMe Sync Stall   :      4.00 ms (    1.9 us/tok |  0.17%)
   Unaccounted / OMP & Sampling :     57.34 ms (   27.6 us/tok |  2.42%) | Total Wall=2370.27 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    18.54%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.28%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.34%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    76.88%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.96%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1978.82 tps | Avg=1978.82 tps | Hit=99.2% | NVMe=2889.1 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1718.29 tps | Avg=1839.37 tps | Hit=99.2% | NVMe=3855.2 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1763.14 tps | Avg=1813.24 tps | Hit=99.2% | NVMe=4449.8 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1660.23 tps | Avg=1772.40 tps | Hit=99.2% | NVMe=4910.4 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1550.74 tps | Avg=1723.14 tps | Hit=99.2% | NVMe=5272.6 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1457.91 tps | Avg=1672.43 tps | Hit=99.2% | NVMe=5537.2 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1372.01 tps | Avg=1621.70 tps | Hit=99.2% | NVMe=5768.0 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1287.71 tps | Avg=1570.78 tps | Hit=99.2% | NVMe=5960.9 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=179.97 tps | Hit=99.2% (LA:+0.0%) | NVMe=5848.8 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=179.66 tps | Hit=99.2% (LA:+0.1%) | NVMe=5786.1 MB/s (153.28 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=179.17 tps | Hit=99.2% (LA:+0.1%) | NVMe=5683.0 MB/s (154.23 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=179.41 tps | Hit=99.2% (LA:+0.1%) | NVMe=5582.5 MB/s (155.14 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.85 MB | End=91.79 MB | Peak=91.79 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1303.81 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    5.67 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    5.67 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    5.53 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    5.53 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    5.51 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    5.51 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    5.53 | 16 |  0 |  0 |    32.0 |
   |   20 |     193 | qtok_193       |   68.95 | 100.0% |      17 |   58.95 |    5.66 | 14 |  2 |  0 |    87.5 |
   |   21 |      63 | qtok_63        |   75.06 |  99.9% |     193 |   67.57 |    5.66 |  0 |  0 |  0 |    87.5 |
   |   10 |     254 | qtok_254       |   70.81 |  99.7% |      66 |   64.77 |    5.62 | 15 |  1 |  0 |    59.8 |
   |   11 |      49 | qtok_49        |   84.60 |  79.6% |     129 |   83.23 |    5.62 |  0 |  0 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.57 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.57 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.54 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.54 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.304s, TTFT=1303.81ms): Avg=1570.78 | Min=1287.71 | Max=1978.82 tps
   Prefill Chunks (8): C1:256t/1978.8tps/99% | C2:256t/1718.3tps/99% | C3:256t/1763.1tps/99% | C4:256t/1660.2tps/99%
                       C5:256t/1550.7tps/99% | C6:256t/1457.9tps/99% | C7:256t/1372.0tps/99% | C8:256t/1287.7tps/99%
   Decode  (32 tok, 0.178s): Avg=179.41 | Min=176.50 | Max=181.59 tps
   Latency (ms) : Min=5.51 | P10=5.53 | P25=5.54 | P50=5.57 | P75=5.62 | P90=5.66 | P95=5.67 | P99=5.67 | Max=5.67
   Mean/SD/Jitt : Mean=5.57ms | StdDev=0.05ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=326.70 | Avg=5582.53 | Peak=11628.06 MB/s | WallAmort=104.67 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=5.41 ms | AsyncOverlapped=26.33 ms (83.0% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.62 GB/s | WallAmort=1.42 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.30s (88.0%, 144.44 MB SSD) | Decode=0.18s (12.0%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.172s + Sys=0.609s (Wall=1.510s) | SysUtil=46.1% | ThrUtil=46.1% | 42.60 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    916.91 ms (  440.8 us/tok | 61.86%)
   MoE AVX2 Q8 Expert Compute   :    372.16 ms (  178.9 us/tok | 25.11%)
   Router + Lookahead Dispatch  :     80.48 ms (   38.7 us/tok |  5.43%)
   LM Head Output Projection    :      5.80 ms (    2.8 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :      5.41 ms (    2.6 us/tok |  0.37%)
   Unaccounted / OMP & Sampling :    101.41 ms (   48.8 us/tok |  6.84%) | Total Wall=1482.17 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    17.29%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.86%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.80%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    70.47%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.58%  |
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
    "ttft_ms": 235.14,
    "avg_tps": 697.46,
    "min_tps": 566.18,
    "max_tps": 786.89
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 145.7,
    "min_tps": 139.35,
    "max_tps": 147.82,
    "p50_ms": 6.84,
    "p90_ms": 6.96,
    "p99_ms": 7.18,
    "mean_ms": 6.86,
    "jitter_ms": 0.07
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
    "avg_mbs": 2128.3,
    "peak_mbs": 6009.62,
    "sync_wait_ms": 1.59,
    "async_overlap_ms": 2.69
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
    "dense_attention": 376.51,
    "moe_compute": 104.08,
    "router_lookahead": 7.35,
    "lm_head": 8.81,
    "unaccounted": 4.48
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 85.83,
    "ram_bandwidth_pinning": 1.91,
    "expert_cache_lrfu": 9.36,
    "lookahead_parallel_overlap": 1.95,
    "ssd_nvme_throughput": 0.95,
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
    "ttft_ms": 306.65,
    "avg_tps": 534.8,
    "min_tps": 378.5,
    "max_tps": 605.8
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 128.16,
    "min_tps": 121.97,
    "max_tps": 131.0,
    "p50_ms": 7.78,
    "p90_ms": 7.92,
    "p99_ms": 8.2,
    "mean_ms": 7.8,
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
    "avg_mbs": 2700.87,
    "peak_mbs": 8794.46,
    "sync_wait_ms": 4.42,
    "async_overlap_ms": 12.29
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
    "dense_attention": 346.06,
    "moe_compute": 200.88,
    "router_lookahead": 8.79,
    "lm_head": 8.43,
    "unaccounted": 42.38
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.54,
    "ram_bandwidth_pinning": 2.18,
    "expert_cache_lrfu": 8.29,
    "lookahead_parallel_overlap": 4.34,
    "ssd_nvme_throughput": 2.65,
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
   System Memory (RAM): 15.99 GB Total / 13.51 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    414.13 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1609.85 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7740.17 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9638.88 MB/s
   RND4K Q32T16 Read                  :    509.05 MB/s (  130316 IOPS)
   RND4K Q1T1  Read                   :    710.76 MB/s (Latency: 5.50 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     59.01 GB/s
   AVX2 256-bit Sequential Write BW   :     47.95 GB/s
   STREAM Triad (A = B + s*C) BW      :     41.90 GB/s
   Random Pointer-Chase Latency       :     48.50 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.35 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    197.20 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     22.12 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 31.00 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 165.62 MB/s (6.18s)
   Window #01 (312.0 MB in 0.53s):   591.37 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.51s):   385.86 MB/s (Uncached Direct Read)
   Window #03 (200.0 MB in 0.50s):   397.61 MB/s (Uncached Direct Read)
   Window #04 (204.0 MB in 0.50s):   406.70 MB/s (Uncached Direct Read)
   Window #05 (112.0 MB in 0.30s):   372.89 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   437.50 MB/s (Min=372.89 | Max=591.37 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 397.09 MB/s (2.58s)
   Window #01 (212.0 MB in 0.54s):   393.95 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   388.31 MB/s (Uncached Direct Read)
   Window #03 (196.0 MB in 0.51s):   388.07 MB/s (Uncached Direct Read)
   Window #04 (216.0 MB in 0.55s):   392.11 MB/s (Uncached Direct Read)
   Window #05 (204.0 MB in 0.49s):   416.69 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   395.60 MB/s (Min=388.07 | Max=416.69 MB/s)
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
   System Memory (RAM): 15.99 GB Total / 13.95 GB Available
   Active Drive Space : 150.00 GB Total / 54.59 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    433.08 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1615.54 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7583.39 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9863.34 MB/s
   RND4K Q32T16 Read                  :    448.73 MB/s (  114875 IOPS)
   RND4K Q1T1  Read                   :    687.33 MB/s (Latency: 5.68 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     54.76 GB/s
   AVX2 256-bit Sequential Write BW   :     45.81 GB/s
   STREAM Triad (A = B + s*C) BW      :     39.39 GB/s
   Random Pointer-Chase Latency       :     54.54 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.26 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    189.94 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.06 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 70 tokenized input IDs
[LIVE-PREFILL] 70/70 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=73.6% | NVMe=522.1 MB/s (51661.71 MB, QD=64) | RSS=13947.8 MB

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
   LRFU Cache / Staging Ring    : 5550.00 MB (592/12384 exp = 4.78% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13431.58 MB | Peak=14027.35 MB
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
   |    1 |   13699 | <th            |   17.30 |  47.4% |   32169 |   16.35 | 142742.15 |  0 |  0 |  0 |     0.0 |
   |    2 |     766 | ink            |   20.50 |  79.8% |   15724 |   19.10 | 3801.04 | 20 |239 | 77 | 1512544.0 |
   |    3 |    1339 | >\n\n          |   14.01 |  20.8% |     397 |   12.96 | 3801.04 |  0 |  0 |  0 | 1512544.0 |
   |    4 |   10056 | Let            |   15.28 |  31.5% |     334 |   14.78 | 2625.59 |142 |135 | 59 | 996096.0 |
   |    5 |     752 |  me            |   16.52 |  72.1% |     594 |   14.85 | 2625.59 |  0 |  0 |  0 | 996096.0 |
   |    6 |    1744 |  think         |   15.53 |  38.0% |   23578 |   13.60 | 2827.05 |120 |166 | 50 | 1071552.0 |
   |    7 |    1526 |  through       |   17.47 |  63.7% |   15504 |   14.79 | 2827.05 |  0 |  0 |  0 | 1071552.0 |
   |    8 |     419 |  this          |   17.34 |  55.6% |     279 |   16.09 | 2959.89 |107 |175 | 54 | 1147072.0 |
   |    9 |   15504 |  carefully     |   14.89 |   6.9% |    3019 |   14.71 | 2959.89 |  0 |  0 |  0 | 1147072.0 |
   |   12 |   32559 |  reasoning     |   14.05 |   8.5% |    1681 |   14.01 | 2661.75 |124 |156 | 56 | 1064640.0 |
   |   13 |    1526 |  through       |   16.95 |  33.1% |    1128 |   15.76 | 2661.75 |  0 |  0 |  0 | 1064640.0 |
   |   10 |    1128 |  what          |   16.98 |  28.3% |      13 |   16.45 | 2628.82 |117 |177 | 42 | 1061216.0 |
   |   62 |    1526 |  through       |   17.43 |  49.9% |     594 |   17.31 | 2427.02 |180 | 71 | 85 | 1035424.0 |
   |   63 |     594 | 's             |   21.37 |  93.3% |    1526 |   17.99 | 2427.02 |  0 |  0 |  0 | 1035424.0 |
   |   64 |     594 | 's             |   17.28 |  49.5% |    1526 |   17.16 | 2603.95 |160 |104 | 72 | 1093440.0 |
   |   65 |    1526 |  through       |   21.46 |  88.7% |     594 |   18.70 | 2603.95 |  0 |  0 |  0 | 1093440.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (70 tok, 142.742s, TTFT=142742.15ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:70t/0.5tps/74%
   Decode  (64 tok, 150.785s): Avg=0.42 | Min=0.26 | Max=0.62 tps
   Latency (ms) : Min=1621.78 | P10=1900.18 | P25=2147.78 | P50=2356.84 | P75=2603.95 | P90=2661.75 | P95=2959.89 | P99=3801.04 | Max=3801.04
   Mean/SD/Jitt : Mean=2356.01ms | StdDev=402.02ms | Jitter=143.41ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (34272): RawRAM=22521 (65.71%) | Lookahead=3727 (+10.87%) | ColdMiss=8024 (23.41%) | EFF HIT=76.59%
   Lookahead    : 6501 prefetched -> 3727 consumed (57.3% util) | Warmup >=75%:21t, >=85%:-1t
   Trajectory   : @16= 74.6% | @64= 76.6% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  816 |  475 | 131 | 210 | 74.3%|2450.94 | | L24 |  816 |  579 |  83 | 154 | 81.1%|2170.62 |
   | L04 |  816 |  438 | 116 | 262 | 67.9%|3478.75 | | L25 |  816 |  569 |  62 | 185 | 77.3%|2371.88 |
   | L05 |  816 |  442 | 106 | 268 | 67.2%|3306.25 | | L26 |  816 |  554 |  89 | 173 | 78.8%|2307.19 |
   | L06 |  816 |  479 |  99 | 238 | 70.8%|2846.25 | | L27 |  816 |  538 | 104 | 174 | 78.7%|2515.62 |
   | L07 |  816 |  498 | 120 | 198 | 75.7%|2645.00 | | L28 |  816 |  521 |  97 | 198 | 75.7%|2565.94 |
   | L08 |  816 |  516 |  59 | 241 | 70.5%|3040.31 | | L29 |  816 |  531 |  98 | 187 | 77.1%|2522.81 |
   | L09 |  816 |  457 |  97 | 262 | 67.9%|3212.81 | | L30 |  816 |  531 |  80 | 205 | 74.9%|2515.62 |
   | L10 |  816 |  471 | 104 | 241 | 70.5%|2968.44 | | L31 |  816 |  514 | 107 | 195 | 76.1%|2637.81 |
   | L11 |  816 |  469 | 104 | 243 | 70.2%|4087.50 | | L32 |  816 |  513 | 119 | 184 | 77.5%|2666.56 |
   | L12 |  816 |  526 |  75 | 215 | 73.7%|3115.50 | | L33 |  816 |  573 |  86 | 157 | 80.8%|2206.56 |
   | L13 |  816 |  554 |  63 | 199 | 75.6%|2357.50 | | L34 |  816 |  511 | 121 | 184 | 77.5%|2522.81 |
   | L14 |  816 |  541 |  67 | 208 | 74.5%|2731.25 | | L35 |  816 |  527 | 116 | 173 | 78.8%|2400.62 |
   | L15 |  816 |  541 |  98 | 177 | 78.3%|2379.06 | | L36 |  816 |  534 | 102 | 180 | 77.9%|2379.06 |
   | L16 |  816 |  554 |  75 | 187 | 77.1%|2278.44 | | L37 |  816 |  554 |  91 | 171 | 79.0%|2199.38 |
   | L17 |  816 |  557 |  51 | 208 | 74.5%|2371.88 | | L38 |  816 |  565 |  88 | 163 | 80.0%|2228.12 |
   | L18 |  816 |  596 |  56 | 164 | 79.9%|2127.50 | | L39 |  816 |  546 | 104 | 166 | 79.7%|2185.00 |
   | L19 |  816 |  580 |  71 | 165 | 79.8%|2084.38 | | L40 |  816 |  496 | 109 | 211 | 74.1%|2910.94 |
   | L20 |  816 |  617 |  54 | 145 | 82.2%|1796.88 | | L41 |  816 |  544 |  98 | 174 | 78.7%|2328.75 |
   | L21 |  816 |  591 |  74 | 151 | 81.5%|2055.62 | | L42 |  816 |  593 |  56 | 167 | 79.5%|2077.19 |
   | L22 |  816 |  582 |  69 | 165 | 79.8%|2314.38 | | L43 |  816 |  596 |  69 | 151 | 81.5%|2105.94 |
   | L23 |  816 |  583 |  73 | 160 | 80.4%|1983.75 | | L44 |  816 |  565 |  86 | 165 | 79.8%|2730.25 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 113116.27 MB (Load=6361.84 | Prefill=45299.88 | Warmup=0.00 | Decode=61454.56 MB)
   SSD Data/Token (Decode)      : Avg=960.228 MB/tok (Min=689.969 | P50=972.750 | P95=1120.188 | Max=1477.094 MB) | Prefill=647.141 MB/tok
   NVMe Batches / Requests      : 2508 Batches | 45056 Raw -> 44547 Merged (509 LBA Merges, Avg 2600.2 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=43668
   SSD Read Bandwidth (Active)  : Min=0.32 | Avg=471.23 | Peak=4404.65 MB/s | WallAmort=385.37 MB/s (100.0% of 433.1 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=114103.31 MB | Write=128.00 MB | Syscalls=56121
   Sync Stall vs Async DMA      : SyncStall=118823.89 ms | AsyncOverlapped=225196.83 ms (65.5% Overlapped)
   RAM Traffic & Active BW      : 777.28 GB moved | Active=7.59 GB/s (19.3% STREAM) | WallAmort=2.65 GB/s (Max=39.39 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=142.74s (48.6%, 45299.88 MB SSD) | Decode=150.78s (51.4%, 61454.56 MB SSD)
   CPU Time & Utilization       : User=315.250s + Sys=13.469s (Wall=313.072s) | SysUtil=26.2% | ThrUtil=26.2% | 49.86 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  40856.26 ms (304897.5 us/tok | 13.92%)
   MoE AVX2 Q8 Expert Compute   :  59914.90 ms (447126.1 us/tok | 20.41%)
   Router + Lookahead Dispatch  :    896.89 ms ( 6693.2 us/tok |  0.31%)
   LM Head Output Projection    :   1625.30 ms (12129.1 us/tok |  0.55%)
   Foreground NVMe Sync Stall   : 118823.89 ms (886745.4 us/tok | 40.48%)
   Unaccounted / OMP & Sampling :  71409.45 ms (532906.4 us/tok | 24.33%) | Total Wall=293526.69 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    37.02%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    23.24%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.65%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.46%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.63%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_glm53_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5203.12 MB (555 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=0.49 tps | Avg=0.49 tps | Hit=73.8% | NVMe=513.4 MB/s (47437.59 MB, QD=64) | RSS=13591.9 MB
[LIVE-DECODE] 2/32 tok | Avg=0.26 tps | Hit=73.9% (LA:+1.1%) | NVMe=507.3 MB/s (50457.65 MB) | RSS=13594.5 MB
[LIVE-DECODE] 4/32 tok | Avg=0.30 tps | Hit=74.0% (LA:+1.8%) | NVMe=502.3 MB/s (52765.34 MB) | RSS=13595.5 MB
[LIVE-DECODE] 6/32 tok | Avg=0.33 tps | Hit=74.1% (LA:+2.5%) | NVMe=499.0 MB/s (54681.46 MB) | RSS=13578.0 MB
[LIVE-DECODE] 8/32 tok | Avg=0.35 tps | Hit=74.3% (LA:+2.8%) | NVMe=496.1 MB/s (56327.27 MB) | RSS=13519.8 MB
[LIVE-DECODE] 10/32 tok | Avg=0.37 tps | Hit=74.5% (LA:+3.3%) | NVMe=494.0 MB/s (58041.65 MB) | RSS=13496.8 MB
[LIVE-DECODE] 12/32 tok | Avg=0.38 tps | Hit=74.6% (LA:+3.7%) | NVMe=491.3 MB/s (59835.96 MB) | RSS=13465.1 MB
[LIVE-DECODE] 14/32 tok | Avg=0.39 tps | Hit=74.6% (LA:+4.1%) | NVMe=488.8 MB/s (61670.71 MB) | RSS=13465.0 MB
[LIVE-DECODE] 16/32 tok | Avg=0.39 tps | Hit=74.7% (LA:+4.5%) | NVMe=486.6 MB/s (63722.46 MB) | RSS=13457.8 MB
[LIVE-DECODE] 18/32 tok | Avg=0.40 tps | Hit=74.8% (LA:+4.9%) | NVMe=484.4 MB/s (65481.09 MB) | RSS=13435.7 MB
[LIVE-DECODE] 20/32 tok | Avg=0.40 tps | Hit=74.9% (LA:+5.2%) | NVMe=482.9 MB/s (67395.96 MB) | RSS=13416.0 MB
[LIVE-DECODE] 22/32 tok | Avg=0.40 tps | Hit=74.9% (LA:+5.5%) | NVMe=480.5 MB/s (69254.84 MB) | RSS=13371.7 MB
[LIVE-DECODE] 24/32 tok | Avg=0.40 tps | Hit=75.0% (LA:+5.8%) | NVMe=479.0 MB/s (71112.21 MB) | RSS=13343.7 MB
[LIVE-DECODE] 26/32 tok | Avg=0.40 tps | Hit=75.1% (LA:+6.1%) | NVMe=477.0 MB/s (73006.90 MB) | RSS=13331.7 MB
[LIVE-DECODE] 28/32 tok | Avg=0.41 tps | Hit=75.2% (LA:+6.4%) | NVMe=475.8 MB/s (74890.96 MB) | RSS=13293.6 MB
[LIVE-DECODE] 30/32 tok | Avg=0.41 tps | Hit=75.2% (LA:+6.6%) | NVMe=474.5 MB/s (76786.34 MB) | RSS=13266.5 MB
[LIVE-DECODE] 32/32 tok | Avg=0.41 tps | Hit=75.3% (LA:+6.9%) | NVMe=473.2 MB/s (78667.46 MB) | RSS=13258.4 MB

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
   LRFU Cache / Staging Ring    : 5203.12 MB (555/12384 exp = 4.48% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13258.37 MB | Peak=13679.70 MB
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
   |    1 |     264 |  a             |   13.92 |  10.6% |   47414 |   13.42 | 130824.14 |  0 |  0 |  0 |     0.0 |
   |    2 |   24923 |  persistent    |   14.20 |   9.2% |     220 |   14.17 | 3794.95 | 18 |239 | 79 | 1546272.0 |
   |    3 |   54443 |  CUDA          |   14.65 |  11.4% |    9996 |   14.41 | 3794.95 |  0 |  0 |  0 | 1546272.0 |
   |    4 |    4269 |  stream        |   14.37 |  14.3% |   11292 |   13.81 | 2937.33 |100 |166 | 70 | 1181536.0 |
   |    5 |   47414 |  pinned        |   14.48 |  22.4% |   12675 |   13.14 | 2937.33 |  0 |  0 |  0 | 1181536.0 |
   |    6 |   63637 | -memory        |   18.96 |  91.2% |    3468 |   15.18 | 2442.99 |140 |147 | 49 | 981056.0 |
   |    7 |   47414 |  pinned        |   16.01 |  30.3% |    7314 |   15.09 | 2442.99 |  0 |  0 |  0 | 981056.0 |
   |    8 |   63637 | -memory        |   16.32 |  36.5% |   47414 |   15.67 | 2117.74 |185 | 97 | 54 | 842656.0 |
   |   16 |   47414 |  pinned        |   16.87 |  71.1% |   25372 |   13.63 | 2475.94 |153 |109 | 74 | 1050496.0 |
   |   17 |   63637 | -memory        |   19.08 |  72.7% |   47414 |   17.80 | 2475.94 |  0 |  0 |  0 | 1050496.0 |
   |   26 |   47414 |  pinned        |   16.50 |  47.0% |   63637 |   16.31 | 2396.68 |174 | 93 | 69 | 970080.0 |
   |   27 |   63637 | -memory        |   21.82 |  96.1% |   47414 |   18.39 | 2396.68 |  0 |  0 |  0 | 970080.0 |
   |   30 |   47414 |  pinned        |   17.05 |  51.0% |   63637 |   16.85 | 2310.65 |184 | 81 | 71 | 970432.0 |
   |   31 |   63637 | -memory        |   21.56 |  94.1% |   47414 |   18.55 | 2310.65 |  0 |  0 |  0 | 970432.0 |
   |   32 |   63637 | -memory        |   17.13 |  66.4% |   47414 |   16.08 | 2273.25 |169 |102 | 65 | 963136.0 |
   |   33 |   47414 |  pinned        |   21.73 |  98.5% |   63637 |   16.47 | 2273.25 |  0 |  0 |  0 | 963136.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 130.824s, TTFT=130824.14ms): Avg=0.49 | Min=0.49 | Max=0.49 tps
   Prefill Chunks (1): C1:64t/0.5tps/74%
   Decode  (32 tok, 78.012s): Avg=0.41 | Min=0.26 | Max=0.47 tps
   Latency (ms) : Min=2117.74 | P10=2192.51 | P25=2273.25 | P50=2309.06 | P75=2442.99 | P90=2937.33 | P95=3794.95 | P99=3794.95 | Max=3794.95
   Mean/SD/Jitt : Mean=2437.86ms | StdDev=391.93ms | Jitter=92.48ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (26880): RawRAM=18383 (68.39%) | Lookahead=1855 (+6.90%) | ColdMiss=6642 (24.71%) | EFF HIT=75.29%
   Lookahead    : 3217 prefetched -> 1855 consumed (57.7% util) | Warmup >=75%:23t, >=85%:-1t
   Trajectory   : @16= 74.7% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 |  640 |  352 |  77 | 211 | 67.0%|2070.00 | | L24 |  640 |  464 |  41 | 135 | 78.9%|1502.19 |
   | L04 |  640 |  331 |  49 | 260 | 59.4%|2666.56 | | L25 |  640 |  464 |  32 | 144 | 77.5%|1523.75 |
   | L05 |  640 |  349 |  53 | 238 | 62.8%|2371.88 | | L26 |  640 |  466 |  48 | 126 | 80.3%|1430.31 |
   | L06 |  640 |  373 |  61 | 206 | 67.8%|2127.50 | | L27 |  640 |  428 |  53 | 159 | 75.2%|1854.38 |
   | L07 |  640 |  402 |  62 | 176 | 72.5%|1861.56 | | L28 |  640 |  452 |  42 | 146 | 77.2%|1595.62 |
   | L08 |  640 |  416 |  39 | 185 | 71.1%|1969.38 | | L29 |  640 |  438 |  47 | 155 | 75.8%|1696.25 |
   | L09 |  640 |  375 |  45 | 220 | 65.6%|2213.75 | | L30 |  640 |  445 |  40 | 155 | 75.8%|1653.12 |
   | L10 |  640 |  383 |  44 | 213 | 66.7%|2084.38 | | L31 |  640 |  430 |  43 | 167 | 73.9%|1703.44 |
   | L11 |  640 |  416 |  48 | 176 | 72.5%|2409.38 | | L32 |  640 |  417 |  59 | 164 | 74.4%|1825.62 |
   | L12 |  640 |  433 |  48 | 159 | 75.2%|1959.75 | | L33 |  640 |  448 |  43 | 149 | 76.7%|1732.19 |
   | L13 |  640 |  440 |  45 | 155 | 75.8%|1653.12 | | L34 |  640 |  450 |  52 | 138 | 78.4%|1588.44 |
   | L14 |  640 |  454 |  34 | 152 | 76.2%|1653.12 | | L35 |  640 |  449 |  49 | 142 | 77.8%|1552.50 |
   | L15 |  640 |  452 |  34 | 154 | 75.9%|1566.88 | | L36 |  640 |  445 |  45 | 150 | 76.6%|1617.19 |
   | L16 |  640 |  457 |  45 | 138 | 78.4%|1502.19 | | L37 |  640 |  449 |  39 | 152 | 76.2%|1538.12 |
   | L17 |  640 |  453 |  42 | 145 | 77.3%|1566.88 | | L38 |  640 |  449 |  45 | 146 | 77.2%|1581.25 |
   | L18 |  640 |  473 |  31 | 136 | 78.8%|1466.25 | | L39 |  640 |  452 |  53 | 135 | 78.9%|1423.12 |
   | L19 |  640 |  463 |  35 | 142 | 77.8%|1509.38 | | L40 |  640 |  456 |  40 | 144 | 77.5%|1502.19 |
   | L20 |  640 |  462 |  40 | 138 | 78.4%|1581.25 | | L41 |  640 |  471 |  29 | 140 | 78.1%|1372.81 |
   | L21 |  640 |  464 |  50 | 126 | 80.3%|1466.25 | | L42 |  640 |  490 |  25 | 125 | 80.5%|1229.06 |
   | L22 |  640 |  465 |  45 | 130 | 79.7%|1495.00 | | L43 |  640 |  491 |  36 | 113 | 82.3%|1236.25 |
   | L23 |  640 |  437 |  39 | 164 | 74.4%|1796.88 | | L44 |  640 |  479 |  28 | 133 | 79.2%|1809.00 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 78667.46 MB (Load=6361.84 | Prefill=41075.75 | Warmup=0.00 | Decode=31229.88 MB)
   SSD Data/Token (Decode)      : Avg=975.934 MB/tok (Min=822.906 | P50=942.031 | P95=1510.031 | Max=1510.031 MB) | Prefill=641.809 MB/tok
   NVMe Batches / Requests      : 1327 Batches | 30980 Raw -> 30656 Merged (324 LBA Merges, Avg 2627.7 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=29777
   SSD Read Bandwidth (Active)  : Min=0.45 | Avg=473.23 | Peak=3458.02 MB/s | WallAmort=376.70 MB/s
   OS Kernel I/O Verification   : Read=78676.49 MB | Write=0.00 MB | Syscalls=34692
   Sync Stall vs Async DMA      : SyncStall=96870.27 ms | AsyncOverlapped=151459.49 ms (61.0% Overlapped)
   RAM Traffic & Active BW      : 487.81 GB moved | Active=6.53 GB/s | WallAmort=2.34 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=130.82s (62.6%, 41075.75 MB SSD) | Decode=78.01s (37.4%, 31229.88 MB SSD)
   CPU Time & Utilization       : User=239.047s + Sys=8.141s (Wall=227.252s) | SysUtil=27.2% | ThrUtil=27.2% | 25.15 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  30318.52 ms (315817.9 us/tok | 14.52%)
   MoE AVX2 Q8 Expert Compute   :  43455.66 ms (452663.1 us/tok | 20.81%)
   Router + Lookahead Dispatch  :    689.73 ms ( 7184.6 us/tok |  0.33%)
   LM Head Output Projection    :    885.35 ms ( 9222.4 us/tok |  0.42%)
   Foreground NVMe Sync Stall   :  96870.27 ms (1009065.3 us/tok | 46.39%)
   Unaccounted / OMP & Sampling :  36616.20 ms (381418.8 us/tok | 17.53%) | Total Wall=208835.72 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    40.43%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    19.90%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    29.21%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.29%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.17%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_glm53_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: GLM 5.3 Flash | Layers=45 | Hidden=4096 | Experts=288 (Top-8) | Pinned Trunk=6460.98 MB | Expert Cache=5587.50 MB (596 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=0.79 tps | Avg=0.79 tps | Hit=89.2% | NVMe=524.1 MB/s (74277.59 MB, QD=64) | RSS=14063.4 MB
[LIVE-PREFILL] 512/512 tok | Chunk=0.78 tps | Avg=0.78 tps | Hit=88.9% | NVMe=529.4 MB/s (145295.52 MB, QD=64) | RSS=14064.4 MB
[LIVE-DECODE] 2/128 tok | Avg=0.24 tps | Hit=88.9% (LA:+0.1%) | NVMe=526.6 MB/s (148504.46 MB) | RSS=14001.6 MB
[LIVE-DECODE] 4/128 tok | Avg=0.27 tps | Hit=88.9% (LA:+0.2%) | NVMe=523.5 MB/s (150963.96 MB) | RSS=13819.5 MB
[LIVE-DECODE] 6/128 tok | Avg=0.29 tps | Hit=88.8% (LA:+0.3%) | NVMe=521.2 MB/s (153161.96 MB) | RSS=13722.8 MB
[LIVE-DECODE] 8/128 tok | Avg=0.31 tps | Hit=88.8% (LA:+0.4%) | NVMe=519.5 MB/s (155246.96 MB) | RSS=13671.2 MB
[LIVE-DECODE] 10/128 tok | Avg=0.31 tps | Hit=88.8% (LA:+0.4%) | NVMe=517.5 MB/s (157532.27 MB) | RSS=13608.6 MB
[LIVE-DECODE] 12/128 tok | Avg=0.32 tps | Hit=88.8% (LA:+0.5%) | NVMe=515.6 MB/s (159631.59 MB) | RSS=13563.9 MB
[LIVE-DECODE] 14/128 tok | Avg=0.32 tps | Hit=88.8% (LA:+0.6%) | NVMe=513.7 MB/s (161874.96 MB) | RSS=13494.8 MB
[LIVE-DECODE] 16/128 tok | Avg=0.33 tps | Hit=88.8% (LA:+0.7%) | NVMe=512.4 MB/s (163925.21 MB) | RSS=13487.4 MB
[LIVE-DECODE] 18/128 tok | Avg=0.33 tps | Hit=88.7% (LA:+0.8%) | NVMe=510.8 MB/s (166300.09 MB) | RSS=13487.3 MB
[LIVE-DECODE] 20/128 tok | Avg=0.33 tps | Hit=88.7% (LA:+0.8%) | NVMe=509.4 MB/s (168625.59 MB) | RSS=13487.3 MB
[LIVE-DECODE] 22/128 tok | Avg=0.34 tps | Hit=88.7% (LA:+0.9%) | NVMe=508.4 MB/s (170615.90 MB) | RSS=13487.4 MB
[LIVE-DECODE] 24/128 tok | Avg=0.35 tps | Hit=88.7% (LA:+1.0%) | NVMe=507.7 MB/s (172457.90 MB) | RSS=13487.4 MB
[LIVE-DECODE] 26/128 tok | Avg=0.35 tps | Hit=88.7% (LA:+1.1%) | NVMe=506.4 MB/s (174613.15 MB) | RSS=13487.3 MB
[LIVE-DECODE] 28/128 tok | Avg=0.35 tps | Hit=88.7% (LA:+1.1%) | NVMe=505.3 MB/s (176746.52 MB) | RSS=13487.3 MB
[LIVE-DECODE] 30/128 tok | Avg=0.36 tps | Hit=88.6% (LA:+1.2%) | NVMe=504.5 MB/s (178774.27 MB) | RSS=13487.3 MB
[LIVE-DECODE] 32/128 tok | Avg=0.36 tps | Hit=88.6% (LA:+1.2%) | NVMe=504.0 MB/s (180521.84 MB) | RSS=13487.3 MB
[LIVE-DECODE] 34/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.3%) | NVMe=503.5 MB/s (182249.40 MB) | RSS=13487.3 MB
[LIVE-DECODE] 36/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.4%) | NVMe=502.3 MB/s (184559.21 MB) | RSS=13487.3 MB
[LIVE-DECODE] 38/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.4%) | NVMe=501.3 MB/s (186649.71 MB) | RSS=13487.3 MB
[LIVE-DECODE] 40/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.5%) | NVMe=500.5 MB/s (188617.27 MB) | RSS=13482.9 MB
[LIVE-DECODE] 42/128 tok | Avg=0.37 tps | Hit=88.6% (LA:+1.5%) | NVMe=499.8 MB/s (190469.59 MB) | RSS=13482.9 MB
[LIVE-DECODE] 44/128 tok | Avg=0.37 tps | Hit=88.5% (LA:+1.6%) | NVMe=498.9 MB/s (192667.21 MB) | RSS=13487.3 MB
[LIVE-DECODE] 46/128 tok | Avg=0.37 tps | Hit=88.5% (LA:+1.7%) | NVMe=498.2 MB/s (194748.46 MB) | RSS=13487.3 MB
[LIVE-DECODE] 48/128 tok | Avg=0.37 tps | Hit=88.5% (LA:+1.8%) | NVMe=497.3 MB/s (196906.09 MB) | RSS=13487.3 MB
[LIVE-DECODE] 50/128 tok | Avg=0.38 tps | Hit=88.5% (LA:+1.8%) | NVMe=496.7 MB/s (198765.46 MB) | RSS=13487.3 MB
[LIVE-DECODE] 52/128 tok | Avg=0.38 tps | Hit=88.5% (LA:+1.9%) | NVMe=496.0 MB/s (200648.21 MB) | RSS=13487.3 MB
[LIVE-DECODE] 54/128 tok | Avg=0.38 tps | Hit=88.5% (LA:+1.9%) | NVMe=495.2 MB/s (202595.46 MB) | RSS=13477.9 MB
[LIVE-DECODE] 56/128 tok | Avg=0.38 tps | Hit=88.4% (LA:+2.0%) | NVMe=494.4 MB/s (204736.84 MB) | RSS=13477.9 MB
[LIVE-DECODE] 58/128 tok | Avg=0.38 tps | Hit=88.4% (LA:+2.0%) | NVMe=493.9 MB/s (206676.59 MB) | RSS=13477.9 MB
[LIVE-DECODE] 60/128 tok | Avg=0.38 tps | Hit=88.4% (LA:+2.1%) | NVMe=493.1 MB/s (208921.27 MB) | RSS=13477.9 MB
[LIVE-DECODE] 62/128 tok | Avg=0.38 tps | Hit=88.4% (LA:+2.1%) | NVMe=492.7 MB/s (210691.21 MB) | RSS=13477.9 MB
[LIVE-DECODE] 64/128 tok | Avg=0.39 tps | Hit=88.4% (LA:+2.2%) | NVMe=492.2 MB/s (212524.96 MB) | RSS=13487.3 MB
[LIVE-DECODE] 66/128 tok | Avg=0.39 tps | Hit=88.4% (LA:+2.3%) | NVMe=491.5 MB/s (214584.15 MB) | RSS=13487.3 MB
[LIVE-DECODE] 68/128 tok | Avg=0.39 tps | Hit=88.4% (LA:+2.3%) | NVMe=491.0 MB/s (216439.34 MB) | RSS=13487.3 MB
[LIVE-DECODE] 70/128 tok | Avg=0.39 tps | Hit=88.4% (LA:+2.4%) | NVMe=491.0 MB/s (218265.90 MB) | RSS=13496.7 MB
[LIVE-DECODE] 72/128 tok | Avg=0.39 tps | Hit=88.3% (LA:+2.4%) | NVMe=490.7 MB/s (220025.77 MB) | RSS=13496.7 MB
[LIVE-DECODE] 74/128 tok | Avg=0.39 tps | Hit=88.3% (LA:+2.5%) | NVMe=490.5 MB/s (221728.84 MB) | RSS=13496.7 MB
[LIVE-DECODE] 76/128 tok | Avg=0.39 tps | Hit=88.3% (LA:+2.5%) | NVMe=490.1 MB/s (223579.27 MB) | RSS=13496.7 MB
[LIVE-DECODE] 78/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.5%) | NVMe=489.7 MB/s (225411.71 MB) | RSS=13496.7 MB
[LIVE-DECODE] 80/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.6%) | NVMe=489.3 MB/s (227409.09 MB) | RSS=13496.7 MB
[LIVE-DECODE] 82/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.6%) | NVMe=488.9 MB/s (229313.46 MB) | RSS=13496.7 MB
[LIVE-DECODE] 84/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.7%) | NVMe=488.4 MB/s (231090.65 MB) | RSS=13477.9 MB
[LIVE-DECODE] 86/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.7%) | NVMe=487.9 MB/s (232962.46 MB) | RSS=13477.9 MB
[LIVE-DECODE] 88/128 tok | Avg=0.40 tps | Hit=88.3% (LA:+2.8%) | NVMe=487.5 MB/s (234761.15 MB) | RSS=13477.9 MB
[LIVE-DECODE] 90/128 tok | Avg=0.40 tps | Hit=88.2% (LA:+2.8%) | NVMe=487.1 MB/s (236870.40 MB) | RSS=13477.9 MB
[LIVE-DECODE] 92/128 tok | Avg=0.40 tps | Hit=88.2% (LA:+2.8%) | NVMe=486.8 MB/s (238604.46 MB) | RSS=13477.9 MB
[LIVE-DECODE] 94/128 tok | Avg=0.40 tps | Hit=88.2% (LA:+2.9%) | NVMe=486.5 MB/s (240339.77 MB) | RSS=13477.9 MB
[LIVE-DECODE] 96/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+2.9%) | NVMe=486.2 MB/s (241964.84 MB) | RSS=13477.9 MB
[LIVE-DECODE] 98/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+2.9%) | NVMe=485.9 MB/s (243708.77 MB) | RSS=13477.9 MB
[LIVE-DECODE] 100/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+3.0%) | NVMe=485.5 MB/s (245508.15 MB) | RSS=13477.9 MB
[LIVE-DECODE] 102/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+3.0%) | NVMe=485.3 MB/s (247169.34 MB) | RSS=13477.9 MB
[LIVE-DECODE] 104/128 tok | Avg=0.41 tps | Hit=88.2% (LA:+3.0%) | NVMe=485.1 MB/s (248673.09 MB) | RSS=13477.9 MB
[LIVE-DECODE] 106/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.1%) | NVMe=484.5 MB/s (250988.59 MB) | RSS=13472.6 MB
[LIVE-DECODE] 108/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.1%) | NVMe=484.2 MB/s (252761.21 MB) | RSS=13463.9 MB
[LIVE-DECODE] 110/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.1%) | NVMe=483.8 MB/s (254899.77 MB) | RSS=13477.9 MB
[LIVE-DECODE] 112/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.2%) | NVMe=483.2 MB/s (257283.84 MB) | RSS=13496.6 MB
[LIVE-DECODE] 114/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.3%) | NVMe=482.8 MB/s (259204.96 MB) | RSS=13496.6 MB
[LIVE-DECODE] 116/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.3%) | NVMe=482.5 MB/s (260941.46 MB) | RSS=13496.7 MB
[LIVE-DECODE] 118/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.4%) | NVMe=482.1 MB/s (262842.34 MB) | RSS=13496.7 MB
[LIVE-DECODE] 120/128 tok | Avg=0.41 tps | Hit=88.1% (LA:+3.4%) | NVMe=481.6 MB/s (264711.02 MB) | RSS=13496.6 MB
[LIVE-DECODE] 122/128 tok | Avg=0.41 tps | Hit=88.0% (LA:+3.5%) | NVMe=481.4 MB/s (266394.34 MB) | RSS=13496.7 MB
[LIVE-DECODE] 124/128 tok | Avg=0.41 tps | Hit=88.0% (LA:+3.5%) | NVMe=481.1 MB/s (268115.21 MB) | RSS=13496.7 MB
[LIVE-DECODE] 126/128 tok | Avg=0.41 tps | Hit=88.0% (LA:+3.6%) | NVMe=481.0 MB/s (269794.84 MB) | RSS=13496.7 MB
[LIVE-DECODE] 128/128 tok | Avg=0.42 tps | Hit=88.0% (LA:+3.6%) | NVMe=480.9 MB/s (271300.27 MB) | RSS=13496.7 MB

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
   LRFU Cache / Staging Ring    : 5587.50 MB (596/12384 exp = 4.81% pinned) | Staging=600.00 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13496.68 MB | Peak=14128.75 MB
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
   |    1 |    3175 |  single        |   26.48 | 100.0% |   15326 |   16.87 | 653146.29 |  0 |  0 |  0 |     0.0 |
   |    2 |   11492 |  coal          |   21.27 |  96.3% |    1062 |   17.44 | 4173.03 | 43 |175 |118 | 1642976.0 |
   |    3 |   22412 | -co            |   14.00 |  19.9% |   11492 |   13.04 | 4173.03 |  0 |  0 |  0 | 1642976.0 |
   |    4 |    3831 | ales           |   20.23 |  56.4% |     278 |   19.95 | 3330.63 | 89 |171 | 76 | 1259264.0 |
   |    5 |    1998 | ced            |   23.84 |  95.9% |    6125 |   20.05 | 3330.63 |  0 |  0 |  0 | 1259264.0 |
   |    6 |     291 | ed             |   13.00 |  12.2% |      11 |   12.82 | 2855.43 |123 |145 | 68 | 1125376.0 |
   |    7 |     291 | ed             |   17.54 |  71.5% |   11492 |   15.78 | 2855.43 |  0 |  0 |  0 | 1125376.0 |
   |    8 |   39929 |  LB            |   16.46 |  74.9% |      11 |   14.17 | 2679.34 |152 |123 | 61 | 1067520.0 |
   |  112 |      12 | -              |   17.05 |  71.2% |     220 |   14.83 | 3200.16 |100 |162 | 74 | 1220640.0 |
   |  113 |      17 | 2              |   22.18 |  99.2% |      16 |   15.80 | 3200.16 |  0 |  0 |  0 | 1220640.0 |
   |   18 |   10772 | GE             |   14.71 |  27.6% |    3391 |   13.95 | 2945.24 |114 |139 | 83 | 1215936.0 |
   |   19 |    9772 | -and           |   15.11 |  24.5% |      12 |   14.29 | 2945.24 |  0 |  0 |  0 | 1215936.0 |
   |  126 |   10772 | GE             |   14.45 |  16.7% |    2646 |   14.40 | 1948.58 |193 | 92 | 51 | 859968.0 |
   |  127 |   50127 | KK             |   13.12 |  16.3% |      42 |   12.88 | 1948.58 |  0 |  0 |  0 | 859968.0 |
   |  128 |   50127 | KK             |   14.93 |  24.1% |      42 |   14.93 | 1783.38 |211 | 86 | 39 | 770784.0 |
   |  129 |   10772 | GE             |   18.90 |  83.6% |   22197 |   15.87 | 1783.38 |  0 |  0 |  0 | 770784.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 653.146s, TTFT=653146.29ms): Avg=0.78 | Min=0.78 | Max=0.79 tps
   Prefill Chunks (2): C1:256t/0.8tps/89% | C2:256t/0.8tps/89%
   Decode  (128 tok, 307.638s): Avg=0.42 | Min=0.24 | Max=0.56 tps
   Latency (ms) : Min=1774.11 | P10=1986.13 | P25=2127.93 | P50=2317.54 | P75=2669.86 | P90=2866.66 | P95=2945.24 | P99=4173.03 | Max=4173.03
   Mean/SD/Jitt : Mean=2403.42ms | StdDev=400.35ms | Jitter=138.04ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (193536): RawRAM=163422 (84.44%) | Lookahead=6970 (+3.60%) | ColdMiss=23144 (11.96%) | EFF HIT=88.04%
   Lookahead    : 12994 prefetched -> 6970 consumed (53.6% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 88.8% | @64= 88.4% | @128= 88.0% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L03 | 4608 | 3720 | 331 | 557 | 87.9%|6382.50 | | L24 | 4608 | 3996 | 122 | 490 | 89.4%|5146.25 |
   | L04 | 4608 | 3802 | 163 | 643 | 86.0%|7568.44 | | L25 | 4608 | 3917 | 140 | 551 | 88.0%|6475.94 |
   | L05 | 4608 | 3763 | 183 | 662 | 85.6%|7784.06 | | L26 | 4608 | 3951 | 152 | 505 | 89.0%|5663.75 |
   | L06 | 4608 | 3754 | 225 | 629 | 86.3%|7065.31 | | L27 | 4608 | 3863 | 169 | 576 | 87.5%|6871.25 |
   | L07 | 4608 | 3879 | 202 | 527 | 88.6%|5900.94 | | L28 | 4608 | 3848 | 189 | 571 | 87.6%|6418.44 |
   | L08 | 4608 | 3882 | 136 | 590 | 87.2%|6820.94 | | L29 | 4608 | 3881 | 202 | 525 | 88.6%|5994.38 |
   | L09 | 4608 | 3861 | 158 | 589 | 87.2%|6281.88 | | L30 | 4608 | 3811 | 198 | 599 | 87.0%|6806.56 |
   | L10 | 4608 | 3842 | 150 | 616 | 86.6%|6382.50 | | L31 | 4608 | 3836 | 140 | 632 | 86.3%|7058.12 |
   | L11 | 4608 | 3872 | 176 | 560 | 87.8%|8137.50 | | L32 | 4608 | 3807 | 165 | 636 | 86.2%|7007.81 |
   | L12 | 4608 | 3899 | 170 | 539 | 88.3%|6976.38 | | L33 | 4608 | 3823 | 194 | 591 | 87.2%|7015.00 |
   | L13 | 4608 | 3956 | 138 | 514 | 88.8%|5735.62 | | L34 | 4608 | 3847 | 233 | 528 | 88.5%|6267.50 |
   | L14 | 4608 | 3964 | 106 | 538 | 88.3%|5721.25 | | L35 | 4608 | 3813 | 226 | 569 | 87.7%|6634.06 |
   | L15 | 4608 | 3927 | 138 | 543 | 88.2%|5893.75 | | L36 | 4608 | 3802 | 264 | 542 | 88.2%|6461.56 |
   | L16 | 4608 | 3929 | 157 | 522 | 88.7%|5685.31 | | L37 | 4608 | 3893 | 180 | 535 | 88.4%|5699.69 |
   | L17 | 4608 | 3916 | 123 | 569 | 87.7%|6281.88 | | L38 | 4608 | 3880 | 186 | 542 | 88.2%|6188.44 |
   | L18 | 4608 | 3985 | 112 | 511 | 88.9%|5764.38 | | L39 | 4608 | 3862 | 204 | 542 | 88.2%|6059.06 |
   | L19 | 4608 | 3980 | 125 | 503 | 89.1%|5656.56 | | L40 | 4608 | 3870 | 184 | 554 | 88.0%|6253.12 |
   | L20 | 4608 | 3978 | 125 | 505 | 89.0%|5412.19 | | L41 | 4608 | 3953 | 138 | 517 | 88.8%|5541.56 |
   | L21 | 4608 | 3974 | 138 | 496 | 89.2%|5304.38 | | L42 | 4608 | 4013 | 104 | 491 | 89.3%|5433.75 |
   | L22 | 4608 | 3982 | 140 | 486 | 89.5%|5541.56 | | L43 | 4608 | 4022 | 117 | 469 | 89.8%|5052.81 |
   | L23 | 4608 | 3928 | 145 | 535 | 88.4%|5987.19 | | L44 | 4608 | 3941 | 122 | 545 | 88.2%|7336.50 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 271300.27 MB (Load=6361.84 | Prefill=138933.69 | Warmup=0.00 | Decode=126004.75 MB)
   SSD Data/Token (Decode)      : Avg=984.412 MB/tok (Min=751.875 | P50=952.188 | P95=1187.438 | Max=1604.469 MB) | Prefill=271.355 MB/tok
   NVMe Batches / Requests      : 5189 Batches | 110135 Raw -> 108758 Merged (1377 LBA Merges, Avg 2554.4 KB/io)
   SSD I/O Size Histogram       : <64K=481 | 64K-512K=226 | 512K-2M=172 | >2M=107879
   SSD Read Bandwidth (Active)  : Min=0.47 | Avg=480.91 | Peak=4142.25 MB/s | WallAmort=282.37 MB/s
   OS Kernel I/O Verification   : Read=271309.31 MB | Write=0.01 MB | Syscalls=112843
   Sync Stall vs Async DMA      : SyncStall=334178.54 ms | AsyncOverlapped=549247.48 ms (62.2% Overlapped)
   RAM Traffic & Active BW      : 2783.29 GB moved | Active=5.82 GB/s | WallAmort=2.90 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=653.15s (68.0%, 138933.69 MB SSD) | Decode=307.64s (32.0%, 126004.75 MB SSD)
   CPU Time & Utilization       : User=1622.875s + Sys=27.469s (Wall=979.608s) | SysUtil=42.1% | ThrUtil=42.1% | 38.96 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 213441.83 ms (333502.9 us/tok | 22.22%)
   MoE AVX2 Q8 Expert Compute   : 261571.51 ms (408705.5 us/tok | 27.22%)
   Router + Lookahead Dispatch  :   4513.38 ms ( 7052.2 us/tok |  0.47%)
   LM Head Output Projection    :   3377.91 ms ( 5278.0 us/tok |  0.35%)
   Foreground NVMe Sync Stall   : 334178.54 ms (522154.0 us/tok | 34.78%)
   Unaccounted / OMP & Sampling : 143700.85 ms (224532.6 us/tok | 14.96%) | Total Wall=960784.02 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    59.79%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |    12.28%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    16.86%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     8.98%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.09%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_glm53_stage3_openai_stress.log`
```text

```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
