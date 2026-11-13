<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#19 (Run ID `43426126035`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43426126035)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-13 13:18:25 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-13T12:33:14.364Z] ================================================================================
[2026-11-13T12:33:14.385Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-13T12:33:14.387Z] ================================================================================
[2026-11-13T12:33:19.035Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-13T12:33:19.253Z] --------------------------------------------------------------------------------
[2026-11-13T12:33:19.255Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 31 GB / 149.89 GB
[2026-11-13T12:33:19.256Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-13T12:33:19.257Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.01 GB
[2026-11-13T12:33:19.273Z] --------------------------------------------------------------------------------
[2026-11-13T12:33:19.274Z]  [OK] Disk space verification passed: 178.01 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 846K Nov 13 12:33 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 846K Nov 13 12:33 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.46 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    412.11 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1470.13 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7165.77 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10063.88 MB/s
   RND4K Q32T16 Read                  :    458.49 MB/s (  117374 IOPS)
   RND4K Q1T1  Read                   :    620.89 MB/s (Latency: 6.29 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     48.73 GB/s
   AVX2 256-bit Sequential Write BW   :     31.89 GB/s
   STREAM Triad (A = B + s*C) BW      :     29.37 GB/s
   Random Pointer-Chase Latency       :     86.26 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     50.99 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    188.71 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.21 GB/s (FP32 Equiv)
================================================================================



=== [TEST] GLM-5.3-Flash 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_glm53_ud_iq2_xxs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : glm5-next (GLM-5.3-Flash)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] Qwen-3.8-Flash-Next 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_qwen38_ud_iq2_xs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] GLM-5.3-Flash 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_glm53_ud_iq2_xxs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=1.93 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1426.41 tps | Avg=1426.41 tps | Hit=99.5% | NVMe=1618.7 MB/s (6.19 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1234.90 tps | Avg=1323.76 tps | Hit=99.5% | NVMe=1560.3 MB/s (7.01 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1100.31 tps | Avg=1239.83 tps | Hit=99.5% | NVMe=1503.8 MB/s (7.78 MB, QD=64) | RSS=71.9 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=973.21 tps | Avg=1160.36 tps | Hit=99.5% | NVMe=1459.6 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=874.72 tps | Avg=1089.22 tps | Hit=99.5% | NVMe=1425.9 MB/s (9.33 MB, QD=64) | RSS=72.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=814.66 tps | Avg=1031.29 tps | Hit=99.5% | NVMe=1409.4 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=748.54 tps | Avg=978.49 tps | Hit=99.5% | NVMe=1386.8 MB/s (10.83 MB, QD=64) | RSS=72.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=689.87 tps | Avg=929.86 tps | Hit=99.5% | NVMe=1371.2 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=197.21 tps | Hit=99.5% (LA:+0.0%) | NVMe=1328.6 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=197.39 tps | Hit=99.5% (LA:+0.1%) | NVMe=1301.6 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=198.18 tps | Hit=99.5% (LA:+0.1%) | NVMe=1282.1 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=198.44 tps | Hit=99.5% (LA:+0.1%) | NVMe=1275.4 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=73.15 MB | Peak=73.15 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2202.47 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.13 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.13 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.16 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.16 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.00 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.00 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.00 | 11 |  1 |  0 |    49.5 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.13 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.13 |  0 |  0 |  0 |   173.2 |
   |   14 |     220 | tok_220        |  147.52 |  55.4% |      55 |  147.01 |    5.10 |  9 |  3 |  0 |   173.2 |
   |   15 |     197 | tok_197        |   65.84 |  97.8% |     133 |   62.03 |    5.10 |  0 |  0 |  0 |   173.2 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.02 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.02 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    4.96 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    4.96 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.202s, TTFT=2202.47ms): Avg=929.86 | Min=689.87 | Max=1426.41 tps
   Prefill Chunks (8): C1:256t/1426.4tps/99% | C2:256t/1234.9tps/99% | C3:256t/1100.3tps/99% | C4:256t/973.2tps/99%
                       C5:256t/874.7tps/99% | C6:256t/814.7tps/99% | C7:256t/748.5tps/99% | C8:256t/689.9tps/99%
   Decode  (32 tok, 0.161s): Avg=198.44 | Min=193.87 | Max=202.84 tps
   Latency (ms) : Min=4.93 | P10=4.96 | P25=5.00 | P50=5.03 | P75=5.10 | P90=5.13 | P95=5.16 | P99=5.16 | Max=5.16
   Mean/SD/Jitt : Mean=5.04ms | StdDev=0.06ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   NVMe Batches / Requests      : 41 Batches | 748 Reads | 438 LBA Merges (Avg 18.2 KB/req)
   SSD Read Bandwidth           : Avg=1275.45 MB/s | Peak=5952.38 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=6.75 ms | AsyncOverlapped=8.97 ms (57.1% Overlapped)
   RAM Traffic & Effective BW   : 1.43 GB moved | Eff=0.61 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=3.125s + Sys=0.781s (Wall=2.384s) | SysUtil=41.0% | ThrUtil=41.0% | 37.89 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1990.91 ms (  957.2 us/tok | 84.23%)
   MoE AVX2 Q8 Expert Compute   :    242.77 ms (  116.7 us/tok | 10.27%)
   Router + Lookahead Dispatch  :     59.68 ms (   28.7 us/tok |  2.52%)
   LM Head Output Projection    :      5.92 ms (    2.8 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      6.75 ms (    3.2 us/tok |  0.29%)
   Unaccounted / OMP & Sampling :     57.72 ms (   27.7 us/tok |  2.44%) | Total Wall=2363.74 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    28.13%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.10%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.52%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    67.52%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.73%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1872.94 tps | Avg=1872.94 tps | Hit=99.2% | NVMe=2408.3 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1785.88 tps | Avg=1828.37 tps | Hit=99.2% | NVMe=3148.3 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1749.01 tps | Avg=1801.13 tps | Hit=99.2% | NVMe=3596.3 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1645.46 tps | Avg=1759.52 tps | Hit=99.2% | NVMe=3951.9 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1483.47 tps | Avg=1696.38 tps | Hit=99.2% | NVMe=4145.8 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1438.08 tps | Avg=1647.08 tps | Hit=99.2% | NVMe=4358.0 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1262.66 tps | Avg=1578.43 tps | Hit=99.2% | NVMe=4492.1 MB/s (133.27 MB, QD=64) | RSS=91.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1239.80 tps | Avg=1526.32 tps | Hit=99.2% | NVMe=4651.5 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=177.66 tps | Hit=99.2% (LA:+0.0%) | NVMe=4527.5 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=178.54 tps | Hit=99.2% (LA:+0.1%) | NVMe=4435.4 MB/s (153.44 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=178.30 tps | Hit=99.2% (LA:+0.1%) | NVMe=4320.9 MB/s (154.78 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=178.79 tps | Hit=99.2% (LA:+0.1%) | NVMe=4229.3 MB/s (155.58 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=91.79 MB | Peak=91.79 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_129qtok_68qtok_209qtok_223qtok_113qtok_229qtok_24qtok_229qtok_148qtok_209qtok_193qtok_146qtok_148qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=92.5% | AvgMargin=9.488 | MinMargin=0.056
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 | 1341.79 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    5.61 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   94.59 | 100.0% |     177 |   84.92 |    5.61 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    5.64 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   85.06 |  99.7% |     177 |   78.63 |    5.64 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    5.57 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   82.87 |  99.7% |     129 |   77.18 |    5.57 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    5.69 | 16 |  0 |  0 |    32.0 |
   |    9 |      49 | qtok_49        |   83.22 |  99.9% |     129 |   76.57 |    5.69 |  0 |  0 |  0 |    32.0 |
   |   18 |     229 | qtok_229       |   80.70 | 100.0% |      33 |   70.24 |    5.69 | 10 |  6 |  0 |   170.8 |
   |   19 |     148 | qtok_148       |   68.09 |  43.4% |      67 |   67.82 |    5.69 |  0 |  0 |  0 |   170.8 |
   |   10 |     254 | qtok_254       |   71.08 |  99.9% |      66 |   64.40 |    5.64 | 15 |  1 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   71.22 |  99.9% |      66 |   64.31 |    5.54 | 14 |  2 |  0 |    87.5 |
   |   31 |      49 | qtok_49        |  125.25 | 100.0% |     177 |   99.98 |    5.54 |  0 |  0 |  0 |    87.5 |
   |   32 |     254 | qtok_254       |   71.45 |  98.0% |      66 |   67.49 |    5.58 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  131.17 | 100.0% |     129 |  104.87 |    5.58 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.342s, TTFT=1341.79ms): Avg=1526.32 | Min=1239.80 | Max=1872.94 tps
   Prefill Chunks (8): C1:256t/1872.9tps/99% | C2:256t/1785.9tps/99% | C3:256t/1749.0tps/99% | C4:256t/1645.5tps/99%
                       C5:256t/1483.5tps/99% | C6:256t/1438.1tps/99% | C7:256t/1262.7tps/99% | C8:256t/1239.8tps/99%
   Decode  (32 tok, 0.179s): Avg=178.79 | Min=175.65 | Max=183.12 tps
   Latency (ms) : Min=5.46 | P10=5.49 | P25=5.58 | P50=5.60 | P75=5.64 | P90=5.69 | P95=5.69 | P99=5.69 | Max=5.69
   Mean/SD/Jitt : Mean=5.59ms | StdDev=0.06ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33024): RawRAM=32720 (99.08%) | Lookahead=48 (+0.15%) | ColdMiss=256 (0.78%) | EFF HIT=99.22%
   Lookahead    : 60 prefetched -> 54 consumed (90.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8256 | 8190 |   2 |  64 | 99.2%|   3.58 | | L02 | 8256 | 8170 |  22 |  64 | 99.2%|   4.72 |
   | L01 | 8256 | 8184 |   8 |  64 | 99.2%|   4.12 | | L03 | 8256 | 8176 |  16 |  64 | 99.2%|   4.39 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 155.58 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=4.28 MB)
   SSD Data/Token (Decode)      : Avg=0.134 MB/tok (Min=0.031 | P50=0.113 | P95=0.523 | Max=0.523 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 95 Batches | 34221 Reads | 33838 LBA Merges (Avg 4.7 KB/req)
   SSD Read Bandwidth           : Avg=4229.31 MB/s | Peak=9975.86 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=24.69 MB | Write=0.00 MB | Syscalls=400
   Sync Stall vs Async DMA      : SyncStall=9.49 ms | AsyncOverlapped=35.24 ms (78.8% Overlapped)
   RAM Traffic & Effective BW   : 2.10 GB moved | Eff=1.38 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=2.734s + Sys=0.359s (Wall=1.553s) | SysUtil=49.8% | ThrUtil=49.8% | 46.06 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    937.04 ms (  450.5 us/tok | 61.62%)
   MoE AVX2 Q8 Expert Compute   :    380.81 ms (  183.1 us/tok | 25.04%)
   Router + Lookahead Dispatch  :     82.73 ms (   39.8 us/tok |  5.44%)
   LM Head Output Projection    :      5.74 ms (    2.8 us/tok |  0.38%)
   Foreground NVMe Sync Stall   :      9.49 ms (    4.6 us/tok |  0.62%)
   Unaccounted / OMP & Sampling :    104.95 ms (   50.5 us/tok |  6.90%) | Total Wall=1520.77 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.04%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.01%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.32%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    66.41%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.22%  |
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
    "ttft_ms": 243.74,
    "avg_tps": 672.83,
    "min_tps": 553.65,
    "max_tps": 783.36
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 140.71,
    "min_tps": 95.13,
    "max_tps": 148.66,
    "p50_ms": 6.98,
    "p90_ms": 7.29,
    "p99_ms": 10.51,
    "mean_ms": 7.11,
    "jitter_ms": 0.3
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
    "avg_mbs": 1160.53,
    "peak_mbs": 5733.94,
    "sync_wait_ms": 2.75,
    "async_overlap_ms": 5.84
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
    "dense_attention": 389.4,
    "moe_compute": 107.08,
    "router_lookahead": 7.8,
    "lm_head": 8.85,
    "unaccounted": 5.05
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 79.03,
    "ram_bandwidth_pinning": 1.7,
    "expert_cache_lrfu": 15.31,
    "lookahead_parallel_overlap": 2.43,
    "ssd_nvme_throughput": 1.53,
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
    "ttft_ms": 303.12,
    "avg_tps": 541.03,
    "min_tps": 382.58,
    "max_tps": 612.36
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 127.29,
    "min_tps": 106.01,
    "max_tps": 132.72,
    "p50_ms": 7.75,
    "p90_ms": 8.05,
    "p99_ms": 9.43,
    "mean_ms": 7.86,
    "jitter_ms": 0.22
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
    "avg_mbs": 1517.56,
    "peak_mbs": 7666.69,
    "sync_wait_ms": 7.55,
    "async_overlap_ms": 22.75
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
    "dense_attention": 344.17,
    "moe_compute": 197.79,
    "router_lookahead": 8.8,
    "lm_head": 8.65,
    "unaccounted": 42.55
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 74.26,
    "ram_bandwidth_pinning": 1.98,
    "expert_cache_lrfu": 13.39,
    "lookahead_parallel_overlap": 6.13,
    "ssd_nvme_throughput": 4.24,
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
 [3.2] Downloading Official Prebuilt llama.cpp AVX2 Windows Binaries
================================================================================
================================================================================
 [3.3] Cloning & Building ik_llama.cpp (CPU AVX2 Release)
================================================================================
Cloning into 'ik_llama'...
error: unable to create file examples/server/webui_llamacpp/src/lib/components/app/chat/ChatAttachments/ChatAttachmentsPreview/ChatAttachmentsPreviewCurrentItem/ChatAttachmentsPreviewCurrentItemUnavailable.svelte: Filename too long
Updating files:  87% (2469/2832)
Updating files:  88% (2493/2832)
Updating files:  89% (2521/2832)
Updating files:  90% (2549/2832)
Updating files:  91% (2578/2832)
Updating files:  92% (2606/2832)
Updating files:  93% (2634/2832)
Updating files:  94% (2663/2832)
Updating files:  95% (2691/2832)
Updating files:  96% (2719/2832)
Updating files:  97% (2748/2832)
Updating files:  98% (2776/2832)
Updating files:  99% (2804/2832)
Updating files: 100% (2832/2832)
Updating files: 100% (2832/2832), done.
fatal: unable to checkout working tree
warning: Clone succeeded, but checkout failed.
You can inspect what was checked out with 'git status'
and retry with 'git restore --source=HEAD :/'

-- Building for: Visual Studio 18 2026
-- The C compiler identification is MSVC 19.51.36260.0
-- The CXX compiler identification is MSVC 19.51.36260.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/Program Files/Microsoft Visual Studio/18/Enterprise/VC/Tools/MSVC/14.51.36231/bin/Hostx64/x64/cl.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/Program Files/Microsoft Visual Studio/18/Enterprise/VC/Tools/MSVC/14.51.36231/bin/Hostx64/x64/cl.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found Git: C:/Program Files/Git/ucrt64/bin/git.exe (found version "2.56.0.windows.4")
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Failed
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - not found
-- Found Threads: TRUE
-- Found OpenMP_C: -openmp (found version "2.0")
-- Found OpenMP_CXX: -openmp (found version "2.0")
-- Found OpenMP: TRUE (found version "2.0")
-- OpenMP found
-- Using optimized iqk matrix multiplications
-- Enabling IQK Flash Attention kernels
-- Including all IQK FA kernels
-- ccache found, compilation results will be cached. Disable with GGML_CCACHE=OFF.
-- CMAKE_SYSTEM_PROCESSOR: AMD64
-- CMAKE_GENERATOR_PLATFORM: 
-- x86 detected
CMake Warning at common/CMakeLists.txt:26 (message):
  Git index not found in git repository.


-- ARCH_FLAGS = 
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public/index.html.gz
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public_llamacpp/index_llamacpp.html.gz
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public_llamacpp/loading.html
-- Configuring done (19.6s)
-- Generating done (0.9s)
CMake Warning (unused-cli):
  Manually-specified variables were not used by the project:

    GGML_F16C


-- Build files have been written to: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build
MSBuild version 18.11.1-1.26513.3+940033be3 for .NET Framework

  1>Checking Build System
  Generating build details from Git
  -- Found Git: C:/Program Files/Git/ucrt64/bin/git.exe (found version "2.56.0.windows.4")
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/common/CMakeLists.txt
  build-info.cpp
  build_info.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\build_info.dir\Release\build_info.lib
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/ggml/src/CMakeLists.txt
  ggml.c
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(4020,13): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(4038,13): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25): warning C4477: 'fprintf' : format string '%ld' requires an argument of type 'long', but variadic argument 2 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 2 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 3 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 4 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 5 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 6 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 7 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 8 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 9 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
  ggml-alloc.c
  ggml-quants.c
C:\Program Files (x86)\Windows Kits\10\Include\10.0.26100.0\ucrt\assert.h(21,9): warning C4005: 'static_assert': macro redefinition [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  (compiling source file '../../../ggml/src/ggml-quants.c')
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-common.h(69,9):
      see previous definition of 'static_assert'
  
  ggml-aarch64.c
C:\Program Files (x86)\Windows Kits\10\Include\10.0.26100.0\ucrt\assert.h(21,9): warning C4005: 'static_assert': macro redefinition [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  (compiling source file '../../../ggml/src/ggml-aarch64.c')
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-common.h(69,9):
      see previous definition of 'static_assert'
  
  Generating Code...
  ggml-backend.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-backend.cpp(2124,30): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  ggml-moe-prefetch.cpp
  iqk_mul_mat.cpp
  iqk_kda.cpp
  iqk_flash_attn.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(141,94): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(141,82): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(179,13): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(187,25): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(188,61): warning C4244: '=': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(196,38): warning C4244: '=': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(273,112): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(281,119): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(298,22): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(346,80): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(346,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(394,80): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(394,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(481,24): warning C4244: '=': conversion from 'uint64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_fa_576_512.cpp
  iqk_fa_512_512.cpp
  iqk_fa_320_256.cpp
  iqk_fa_192_128.cpp
  iqk_fa_192_192.cpp
  iqk_fa_256_256.cpp
  iqk_fa_128_128.cpp
  iqk_fa_96_96.cpp
  iqk_fa_64_64.cpp
  iqk_gemm_floats.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_floats.cpp(637,9): warning C4065: switch statement contains 'default' but no 'case' labels [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_kquants.cpp
  iqk_gemm_ktquants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(174,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(174,23):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(103,8):
          while compiling class template '`anonymous-namespace'::Trellis3'
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(216,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(266,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_iquants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(316,30): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(332,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(365,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_iqk_quants.cpp
  iqk_gemm_1bit.cpp
  Generating Code...
  Compiling...
  iqk_gemm_legacy_quants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_legacy_quants.cpp(2623,29): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_quantize.cpp
  iqk_cpu_ops.cpp
  Generating Code...
  Auto build dll exports
     Creating library D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/ggml/src/Release/ggml.lib and object D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/ggml/src/Release/ggml.exp
  ggml.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\ggml.dll
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/src/CMakeLists.txt
  llama.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(683,52): warning C4805: '!=

... [TRUNCATED] ...

14854.95 MB, QD=64) | RSS=12978.7 MB
[LIVE-DECODE] 4/32 tok | Avg=1.36 tps | Hit=80.1% (LA:+1.2%) | NVMe=768.4 MB/s (16066.25 MB) | RSS=12983.0 MB
[LIVE-DECODE] 8/32 tok | Avg=1.56 tps | Hit=80.5% (LA:+2.0%) | NVMe=757.2 MB/s (17025.00 MB) | RSS=12983.0 MB
[LIVE-DECODE] 16/32 tok | Avg=1.94 tps | Hit=81.5% (LA:+3.1%) | NVMe=772.4 MB/s (18649.96 MB) | RSS=12975.2 MB
[LIVE-DECODE] 24/32 tok | Avg=2.22 tps | Hit=82.5% (LA:+3.7%) | NVMe=793.9 MB/s (19905.77 MB) | RSS=12944.2 MB
[LIVE-DECODE] 32/32 tok | Avg=2.41 tps | Hit=83.4% (LA:+4.1%) | NVMe=813.4 MB/s (21099.87 MB) | RSS=12914.7 MB

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
   LRFU Cache / Staging Ring    : 7070.19 MB (3407/25088 exp = 13.58% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=12914.71 MB | Peak=13406.62 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " 2!m!$!m! !! !! !! !! !! !!
! !!!!!!!! !!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=55.4% | AvgMargin=nan | MinMargin=0.001
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     220 |                |   15.42 |   8.1% |    2446 |   14.36 | 28598.56 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |   18.29 |  24.9% |      16 |   18.25 |  678.92 |243 |199 | 38 | 302169.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  678.92 |  0 |  0 |  0 | 302169.5 |
   |    4 |      76 | m              |   12.78 |   8.7% |   35716 |   12.51 |  791.15 |239 |190 | 51 | 318019.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  791.15 |  0 |  0 |  0 | 318019.5 |
   |    6 |       3 | $              |   12.89 |  12.8% |      12 |   12.22 |  686.66 |260 |185 | 35 | 302071.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  686.66 |  0 |  0 |  0 | 302071.5 |
   |    8 |      76 | m              |   11.94 |   4.3% |   35716 |   11.90 |  412.84 |383 | 86 | 11 | 188807.0 |
   |   10 |     729 |  !             |   11.55 |   7.7% |    1088 |   10.88 |  436.08 |347 |120 | 13 | 221757.0 |
   |   11 |       0 | !              |     nan | 100.0% |       1 |     nan |  436.08 |  0 |  0 |  0 | 221757.0 |
   |   14 |     729 |  !             |   12.06 |  12.6% |       0 |   10.58 |  416.41 |370 | 99 | 11 | 212607.0 |
   |   15 |       0 | !              |     nan | 100.0% |       1 |     nan |  416.41 |  0 |  0 |  0 | 212607.0 |
   |   30 |       0 | !              |   11.46 |   8.9% |     198 |   11.26 |  305.23 |424 | 56 |  0 | 152157.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  305.23 |  0 |  0 |  0 | 152157.0 |
   |   32 |     729 |  !             |   12.42 |  19.4% |   13682 |   11.09 |  305.89 |444 | 36 |  0 | 124694.5 |
   |   33 |       0 | !              |     nan | 100.0% |       1 |     nan |  305.89 |  0 |  0 |  0 | 124694.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 28.599s, TTFT=28598.56ms): Avg=2.24 | Min=2.24 | Max=2.24 tps
   Prefill Chunks (1): C1:64t/2.2tps/80%
   Decode  (32 tok, 13.297s): Avg=2.41 | Min=1.26 | Max=3.28 tps
   Latency (ms) : Min=305.23 | P10=305.89 | P25=312.13 | P50=349.06 | P75=436.08 | P90=686.66 | P95=791.15 | P99=791.15 | Max=791.15
   Mean/SD/Jitt : Mean=415.53ms | StdDev=152.88ms | Jitter=27.37ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (38400): RawRAM=30441 (79.27%) | Lookahead=1568 (+4.08%) | ColdMiss=6391 (16.64%) | EFF HIT=83.36%
   Lookahead    : 3327 prefetched -> 1728 consumed (51.9% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 81.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  800 |  537 |  26 | 237 | 70.4%| 443.04 | | L24 |  800 |  635 |  37 | 128 | 84.0%| 385.38 |
   | L01 |  800 |  605 |  23 | 172 | 78.5%| 398.44 | | L25 |  800 |  647 |  37 | 116 | 85.5%| 327.10 |
   | L02 |  800 |  599 |  23 | 178 | 77.8%| 534.01 | | L26 |  800 |  624 |  41 | 135 | 83.1%| 366.58 |
   | L03 |  800 |  697 |  11 |  92 | 88.5%| 325.22 | | L27 |  800 |  650 |  23 | 127 | 84.1%| 304.54 |
   | L04 |  800 |  655 |  20 | 125 | 84.4%| 421.26 | | L28 |  800 |  613 |  33 | 154 | 80.8%| 400.42 |
   | L05 |  800 |  621 |  17 | 162 | 79.8%| 409.81 | | L29 |  800 |  626 |  39 | 135 | 83.1%| 303.93 |
   | L06 |  800 |  609 |  27 | 164 | 79.5%| 422.97 | | L30 |  800 |  642 |  32 | 126 | 84.2%| 282.32 |
   | L07 |  800 |  598 |  35 | 167 | 79.1%| 390.82 | | L31 |  800 |  668 |  29 | 103 | 87.1%| 257.84 |
   | L08 |  800 |  646 |  30 | 124 | 84.5%| 215.41 | | L32 |  800 |  680 |  35 |  85 | 89.4%| 250.02 |
   | L09 |  800 |  658 |  29 | 113 | 85.9%| 191.75 | | L33 |  800 |  608 |  48 | 144 | 82.0%| 305.37 |
   | L10 |  800 |  636 |  31 | 133 | 83.4%| 226.61 | | L34 |  800 |  614 |  44 | 142 | 82.2%| 309.69 |
   | L11 |  800 |  640 |  38 | 122 | 84.8%| 237.82 | | L35 |  800 |  661 |  30 | 109 | 86.4%| 234.79 |
   | L12 |  800 |  602 |  36 | 162 | 79.8%| 402.29 | | L36 |  800 |  620 |  46 | 134 | 83.2%| 299.61 |
   | L13 |  800 |  598 |  57 | 145 | 81.9%| 326.98 | | L37 |  800 |  629 |  33 | 138 | 82.8%| 368.46 |
   | L14 |  800 |  617 |  58 | 125 | 84.4%| 309.69 | | L38 |  800 |  595 |  34 | 171 | 78.6%| 445.53 |
   | L15 |  800 |  667 |  26 | 107 | 86.6%| 336.50 | | L39 |  800 |  696 |  17 |  87 | 89.1%| 289.50 |
   | L16 |  800 |  672 |  25 | 103 | 87.1%| 266.94 | | L40 |  800 |  683 |  23 |  94 | 88.2%| 274.46 |
   | L17 |  800 |  645 |  36 | 119 | 85.1%| 325.22 | | L41 |  800 |  653 |  26 | 121 | 84.9%| 224.71 |
   | L18 |  800 |  600 |  50 | 150 | 81.2%| 428.61 | | L42 |  800 |  626 |  25 | 149 | 81.4%| 305.37 |
   | L19 |  800 |  653 |  42 | 105 | 86.9%| 254.96 | | L43 |  800 |  678 |  30 |  92 | 88.5%| 210.30 |
   | L20 |  800 |  615 |  40 | 145 | 81.9%| 301.05 | | L44 |  800 |  641 |  29 | 130 | 83.8%| 279.44 |
   | L21 |  800 |  603 |  55 | 142 | 82.2%| 445.53 | | L45 |  800 |  649 |  26 | 125 | 84.4%| 272.24 |
   | L22 |  800 |  575 |  45 | 180 | 77.5%| 490.65 | | L46 |  800 |  638 |  28 | 134 | 83.2%| 273.68 |
   | L23 |  800 |  676 |  24 | 100 | 87.5%| 224.71 | | L47 |  800 |  641 |  19 | 140 | 82.5%| 381.62 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 21099.87 MB (Load=4614.69 | Prefill=10240.25 | Warmup=0.00 | Decode=6244.92 MB)
   SSD Data/Token (Decode)      : Avg=195.154 MB/tok (Min=121.772 | P50=191.132 | P95=310.566 | Max=310.566 MB) | Prefill=160.004 MB/tok
   NVMe Batches / Requests      : 1299 Batches | 31542 Reads | 1 LBA Merges (Avg 685.0 KB/req)
   SSD Read Bandwidth           : Avg=813.36 MB/s | Peak=6613.94 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=21119.85 MB | Write=0.00 MB | Syscalls=41044
   Sync Stall vs Async DMA      : SyncStall=8071.18 ms | AsyncOverlapped=15405.33 ms (65.6% Overlapped)
   RAM Traffic & Effective BW   : 360.23 GB moved | Eff=8.60 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=89.094s + Sys=8.172s (Wall=56.943s) | SysUtil=42.7% | ThrUtil=42.7% | 39.50 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  13688.60 ms (142589.6 us/tok | 32.67%)
   MoE AVX2 Q8 Expert Compute   :  14157.15 ms (147470.3 us/tok | 33.79%)
   Router + Lookahead Dispatch  :    829.51 ms ( 8640.8 us/tok |  1.98%)
   LM Head Output Projection    :   1175.60 ms (12245.9 us/tok |  2.81%)
   Foreground NVMe Sync Stall   :   8071.18 ms (84074.8 us/tok | 19.26%)
   Unaccounted / OMP & Sampling :   3973.54 ms (41391.1 us/tok |  9.48%) | Total Wall=41895.59 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    66.09%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.46%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    12.05%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    10.29%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.11%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 58s

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
   Active Drive Space : 150.00 GB Total / 75.80 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    482.72 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1475.33 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7544.55 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9957.06 MB/s
   RND4K Q32T16 Read                  :    417.73 MB/s (  106938 IOPS)
   RND4K Q1T1  Read                   :    638.55 MB/s (Latency: 6.12 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     55.38 GB/s
   AVX2 256-bit Sequential Write BW   :     37.78 GB/s
   STREAM Triad (A = B + s*C) BW      :     37.63 GB/s
   Random Pointer-Chase Latency       :     94.66 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.07 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    196.68 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     13.35 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=2.19 tps | Avg=2.19 tps | Hit=79.2% | NVMe=825.7 MB/s (19608.86 MB, QD=64) | RSS=13687.2 MB

 >>> [Apex-Model-Response] <think>
!

!<|im_end|>!<|im_end|>!
!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   LRFU Cache / Staging Ring    : 7763.31 MB (3741/25088 exp = 14.91% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.63 MB | End=13580.52 MB | Peak=14106.34 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "<think>
!

!<|im_end|>!<|im_end|>!
!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=75.1% | AvgMargin=nan | MinMargin=0.002
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |  248068 | <think>        |   33.20 | 100.0% |  248045 |   12.51 | 41528.27 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |   21.37 |  52.8% |     271 |   21.25 |  327.39 |393 | 87 |  0 | 121294.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  327.39 |  0 |  0 |  0 | 121294.5 |
   |    4 |     271 | \n\n           |   12.49 |  23.2% |     198 |   12.29 |  326.47 |384 | 96 |  0 | 154532.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  326.47 |  0 |  0 |  0 | 154532.0 |
   |    6 |  248046 | <|im_end|>     |   12.66 |  20.5% |     198 |   12.53 |  311.37 |406 | 74 |  0 | 131859.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  311.37 |  0 |  0 |  0 | 131859.0 |
   |    8 |  248046 | <|im_end|>     |   12.42 |  16.9% |     198 |   12.17 |  316.84 |440 | 40 |  0 | 107994.5 |
   |   18 |       0 | !              |   13.98 |  52.8% |     198 |   11.63 |  603.41 |297 |143 | 40 | 280219.5 |
   |   19 |       0 | !              |     nan | 100.0% |       1 |     nan |  603.41 |  0 |  0 |  0 | 280219.5 |
   |   20 |       0 | !              |   11.85 |  14.0% |     198 |   11.17 |  468.17 |389 | 76 | 15 | 190607.0 |
   |   21 |       0 | !              |     nan | 100.0% |       1 |     nan |  468.17 |  0 |  0 |  0 | 190607.0 |
   |   62 |       0 | !              |   15.42 |  86.1% |     198 |   11.32 |  308.88 |422 | 58 |  0 | 165732.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  308.88 |  0 |  0 |  0 | 165732.0 |
   |   64 |       0 | !              |   13.95 |  58.2% |     198 |   11.37 |  328.43 |390 | 90 |  0 | 190482.0 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  328.43 |  0 |  0 |  0 | 190482.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 41.528s, TTFT=41528.27ms): Avg=2.19 | Min=2.19 | Max=2.19 tps
   Prefill Chunks (1): C1:91t/2.2tps/79%
   Decode  (64 tok, 21.589s): Avg=2.96 | Min=1.66 | Max=3.47 tps
   Latency (ms) : Min=288.48 | P10=304.67 | P25=310.27 | P50=319.59 | P75=341.82 | P90=391.54 | P95=468.17 | P99=603.41 | Max=603.41
   Mean/SD/Jitt : Mean=337.32ms | StdDev=58.79ms | Jitter=20.77ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (59040): RawRAM=47712 (80.81%) | Lookahead=2154 (+3.65%) | ColdMiss=9174 (15.54%) | EFF HIT=84.46%
   Lookahead    : 5207 prefetched -> 2474 consumed (47.5% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 80.8% | @64= 84.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1230 |  888 |  28 | 314 | 74.5%| 576.12 | | L24 | 1230 |  998 |  61 | 171 | 86.1%| 548.93 |
   | L01 | 1230 |  966 |  10 | 254 | 79.3%| 636.25 | | L25 | 1230 |  956 |  81 | 193 | 84.3%| 582.76 |
   | L02 | 1230 |  973 |  15 | 242 | 80.3%| 651.93 | | L26 | 1230 |  942 |  92 | 196 | 84.1%| 639.16 |
   | L03 | 1230 | 1068 |  14 | 148 | 88.0%| 580.88 | | L27 | 1230 |  975 |  85 | 170 | 86.2%| 556.45 |
   | L04 | 1230 | 1010 |  18 | 202 | 83.6%| 755.37 | | L28 | 1230 |  924 |  89 | 217 | 82.4%| 667.36 |
   | L05 | 1230 |  994 |  15 | 221 | 82.0%| 462.45 | | L29 | 1230 |  941 | 109 | 180 | 85.4%| 478.22 |
   | L06 | 1230 |  962 |  15 | 253 | 79.4%| 528.25 | | L30 | 1230 |  927 |  95 | 208 | 83.1%| 502.71 |
   | L07 | 1230 |  978 |  18 | 234 | 81.0%| 427.88 | | L31 | 1230 | 1030 |  62 | 138 | 88.8%| 422.05 |
   | L08 | 1230 | 1058 |  10 | 162 | 86.8%| 224.12 | | L32 | 1230 | 1004 |  76 | 150 | 87.8%| 511.33 |
   | L09 | 1230 | 1040 |  16 | 174 | 85.9%| 242.80 | | L33 | 1230 |  937 | 110 | 183 | 85.1%| 472.46 |
   | L10 | 1230 | 1029 |  16 | 185 | 85.0%| 262.72 | | L34 | 1230 |  978 |  64 | 188 | 84.7%| 507.03 |
   | L11 | 1230 | 1050 |  19 | 161 | 86.9%| 252.76 | | L35 | 1230 | 1007 |  65 | 158 | 87.2%| 373.07 |
   | L12 | 1230 |  992 |  25 | 213 | 82.7%| 505.69 | | L36 | 1230 |  994 |  55 | 181 | 85.3%| 445.09 |
   | L13 | 1230 | 1038 |  28 | 164 | 86.7%| 309.69 | | L37 | 1230 | 1030 |  30 | 170 | 86.2%| 464.33 |
   | L14 | 1230 |  974 |  60 | 196 | 84.1%| 476.78 | | L38 | 1230 |  942 |  39 | 249 | 79.8%| 646.68 |
   | L15 | 1230 | 1070 |  30 | 130 | 89.4%| 424.85 | | L39 | 1230 | 1046 |  36 | 148 | 88.0%| 483.13 |
   | L16 | 1230 | 1008 |  72 | 150 | 87.8%| 475.61 | | L40 | 1230 | 1012 |  43 | 175 | 85.8%| 456.81 |
   | L17 | 1230 |  965 |  82 | 183 | 85.1%| 586.52 | | L41 | 1230 | 1011 |  36 | 183 | 85.1%| 354.35 |
   | L18 | 1230 |  981 |  49 | 200 | 83.7%| 652.32 | | L42 | 1230 |  984 |  23 | 223 | 81.9%| 436.45 |
   | L19 | 1230 |  990 |  75 | 165 | 86.6%| 453.74 | | L43 | 1230 | 1025 |  36 | 169 | 86.3%| 319.78 |
   | L20 | 1230 |  983 |  55 | 192 | 84.4%| 423.49 | | L44 | 1230 | 1019 |  20 | 191 | 84.5%| 373.07 |
   | L21 | 1230 |  983 |  58 | 189 | 84.6%| 659.84 | | L45 | 1230 | 1030 |  12 | 188 | 84.7%| 329.86 |
   | L22 | 1230 |  942 |  26 | 262 | 78.7%| 759.47 | | L46 | 1230 | 1008 |  25 | 197 | 84.0%| 413.40 |
   | L23 | 1230 | 1033 |  39 | 158 | 87.2%| 374.51 | | L47 | 1230 | 1017 |  17 | 196 | 84.1%| 520.73 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 29425.52 MB (Load=4614.69 | Prefill=14994.17 | Warmup=0.00 | Decode=9816.65 MB)
   SSD Data/Token (Decode)      : Avg=153.385 MB/tok (Min=85.224 | P50=149.445 | P95=222.895 | Max=273.652 MB) | Prefill=164.771 MB/tok
   NVMe Batches / Requests      : 2027 Batches | 46219 Reads | 106 LBA Merges (Avg 651.9 KB/req)
   SSD Read Bandwidth           : Avg=921.69 MB/s | Peak=6922.22 MB/s (100.0% of 482.7 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=30423.11 MB | Write=128.00 MB | Syscalls=63165
   Sync Stall vs Async DMA      : SyncStall=13149.31 ms | AsyncOverlapped=21373.11 ms (61.9% Overlapped)
   RAM Traffic & Effective BW   : 622.87 GB moved | Eff=9.87 GB/s (STREAM Triad Max=37.63 GB/s)
   CPU Time & Utilization       : User=139.547s + Sys=13.391s (Wall=79.441s) | SysUtil=48.1% | ThrUtil=48.1% | 94.66 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  21345.59 ms (137713.5 us/tok | 33.82%)
   MoE AVX2 Q8 Expert Compute   :  21674.34 ms (139834.5 us/tok | 34.34%)
   Router + Lookahead Dispatch  :   1206.66 ms ( 7784.9 us/tok |  1.91%)
   LM Head Output Projection    :   2344.26 ms (15124.3 us/tok |  3.71%)
   Foreground NVMe Sync Stall   :  13149.31 ms (84834.3 us/tok | 20.83%)
   Unaccounted / OMP & Sampling :   3396.84 ms (21915.1 us/tok |  5.38%) | Total Wall=63117.01 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    66.03%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.57%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    11.54%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    11.62%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.24%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7781.98 MB (3750 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=2.97 tps | Avg=2.97 tps | Hit=90.7% | NVMe=1101.0 MB/s (23422.36 MB, QD=64) | RSS=13731.3 MB
[LIVE-PREFILL] 512/512 tok | Chunk=2.94 tps | Avg=2.95 tps | Hit=91.0% | NVMe=1251.0 MB/s (41012.20 MB, QD=64) | RSS=13741.3 MB
[LIVE-DECODE] 4/128 tok | Avg=1.17 tps | Hit=91.0% (LA:+0.2%) | NVMe=1186.7 MB/s (42251.10 MB) | RSS=13682.3 MB
[LIVE-DECODE] 8/128 tok | Avg=1.46 tps | Hit=91.0% (LA:+0.3%) | NVMe=1171.5 MB/s (43340.23 MB) | RSS=13640.5 MB
[LIVE-DECODE] 16/128 tok | Avg=1.94 tps | Hit=91.0% (LA:+0.6%) | NVMe=1188.8 MB/s (45414.07 MB) | RSS=13599.3 MB
[LIVE-DECODE] 24/128 tok | Avg=2.20 tps | Hit=91.1% (LA:+0.8%) | NVMe=1203.4 MB/s (47279.63 MB) | RSS=13599.2 MB
[LIVE-DECODE] 32/128 tok | Avg=2.38 tps | Hit=91.2% (LA:+1.0%) | NVMe=1215.4 MB/s (48876.90 MB) | RSS=13599.2 MB
[LIVE-DECODE] 40/128 tok | Avg=2.50 tps | Hit=91.2% (LA:+1.1%) | NVMe=1225.8 MB/s (50468.99 MB) | RSS=13599.2 MB
[LIVE-DECODE] 48/128 tok | Avg=2.52 tps | Hit=91.3% (LA:+1.3%) | NVMe=1227.1 MB/s (52345.73 MB) | RSS=13599.2 MB
[LIVE-DECODE] 56/128 tok | Avg=2.56 tps | Hit=91.4% (LA:+1.4%) | NVMe=1227.2 MB/s (53819.35 MB) | RSS=13599.2 MB
[LIVE-DECODE] 64/128 tok | Avg=2.57 tps | Hit=91.4% (LA:+1.6%) | NVMe=1224.1 MB/s (55552.75 MB) | RSS=13599.2 MB
[LIVE-DECODE] 72/128 tok | Avg=2.63 tps | Hit=91.5% (LA:+1.7%) | NVMe=1228.7 MB/s (56936.50 MB) | RSS=13599.2 MB
[LIVE-DECODE] 80/128 tok | Avg=2.67 tps | Hit=91.5% (LA:+1.8%) | NVMe=1234.2 MB/s (58271.83 MB) | RSS=13599.2 MB
[LIVE-DECODE] 88/128 tok | Avg=2.66 tps | Hit=91.6% (LA:+1.9%) | NVMe=1227.5 MB/s (59861.34 MB) | RSS=13599.2 MB
[LIVE-DECODE] 96/128 tok | Avg=2.70 tps | Hit=91.6% (LA:+2.0%) | NVMe=1232.8 MB/s (61166.96 MB) | RSS=13599.2 MB
[LIVE-DECODE] 104/128 tok | Avg=2.72 tps | Hit=91.7% (LA:+2.1%) | NVMe=1234.5 MB/s (62674.75 MB) | RSS=13599.2 MB
[LIVE-DECODE] 112/128 tok | Avg=2.74 tps | Hit=91.8% (LA:+2.2%) | NVMe=1238.8 MB/s (64147.29 MB) | RSS=13599.2 MB
[LIVE-DECODE] 120/128 tok | Avg=2.77 tps | Hit=91.8% (LA:+2.3%) | NVMe=1241.9 MB/s (65361.39 MB) | RSS=13599.2 MB
[LIVE-DECODE] 128/128 tok | Avg=2.77 tps | Hit=91.9% (LA:+2.4%) | NVMe=1242.1 MB/s (66924.50 MB) | RSS=13599.2 MB

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
   LRFU Cache / Staging Ring    : 7781.98 MB (3750/25088 exp = 14.95% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.68 MB | End=13599.16 MB | Peak=14160.26 MB
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

!!!

!

!

!

!

!!!

!

!!!

!

!!!

!!!

!!!!!

!

!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=82.9% | AvgMargin=nan | MinMargin=0.128
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    6000 |  layer         |   23.58 | 100.0% |     271 |   13.50 | 173290.27 |  0 |  0 |  0 |     0.0 |
   |    2 |   42962 | -wise          |   22.36 |  99.9% |    2543 |   13.89 |  603.28 |355 |113 | 12 | 221819.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  603.28 |  0 |  0 |  0 | 221819.5 |
   |    4 |     271 | \n\n           |   14.91 |  63.8% |    1249 |   12.72 | 1102.55 |121 |275 | 84 | 412496.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan | 1102.55 |  0 |  0 |  0 | 412496.5 |
   |    6 |     271 | \n\n           |   14.84 |  56.8% |      12 |   12.77 |  570.89 |269 |190 | 21 | 290382.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  570.89 |  0 |  0 |  0 | 290382.0 |
   |    8 |     271 | \n\n           |   15.00 |  60.6% |      12 |   12.20 |  453.94 |299 |168 | 13 | 267257.0 |
   |   84 |     271 | \n\n           |   14.72 |  72.4% |       0 |   12.28 |  506.06 |341 |108 | 31 | 252807.0 |
   |   85 |       0 | !              |     nan | 100.0% |       1 |     nan |  506.06 |  0 |  0 |  0 | 252807.0 |
   |   62 |     271 | \n\n           |   14.77 |  64.8% |       0 |   13.11 |  481.14 |322 |136 | 22 | 278544.5 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  481.14 |  0 |  0 |  0 | 278544.5 |
   |  126 |     271 | \n\n           |   15.34 |  72.4% |       0 |   13.40 |  328.67 |405 | 75 |  0 | 183619.5 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  328.67 |  0 |  0 |  0 | 183619.5 |
   |  128 |     271 | \n\n           |   15.03 |  61.6% |       0 |   13.75 |  304.06 |436 | 44 |  0 | 140269.5 |
   |  129 |       0 | !              |     nan | 100.0% |       1 |     nan |  304.06 |  0 |  0 |  0 | 140269.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 173.290s, TTFT=173290.27ms): Avg=2.95 | Min=2.94 | Max=2.97 tps
   Prefill Chunks (2): C1:256t/3.0tps/91% | C2:256t/2.9tps/91%
   Decode  (128 tok, 46.191s): Avg=2.77 | Min=0.91 | Max=3.37 tps
   Latency (ms) : Min=296.85 | P10=302.63 | P25=308.48 | P50=324.25 | P75=362.07 | P90=453.94 | P95=506.06 | P99=1102.55 | Max=1102.55
   Mean/SD/Jitt : Mean=360.87ms | StdDev=113.77ms | Jitter=29.20ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (276480): RawRAM=247465 (89.51%) | Lookahead=6542 (+2.37%) | ColdMiss=22473 (8.13%) | EFF HIT=91.87%
   Lookahead    : 14252 prefetched -> 7182 consumed (50.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 91.0% | @64= 91.4% | @128= 91.9% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 5760 | 5055 |  64 | 641 | 88.9%|1187.62 | | L24 | 5760 | 5141 | 207 | 412 | 92.8%|1706.93 |
   | L01 | 5760 | 5152 |  65 | 543 | 90.6%|1284.96 | | L25 | 5760 | 5161 | 172 | 427 | 92.6%|1300.88 |
   | L02 | 5760 | 5172 |  52 | 536 | 90.7%|1750.27 | | L26 | 5760 | 5050 | 236 | 474 | 91.8%|1635.50 |
   | L03 | 5760 | 5341 |  45 | 374 | 93.5%|1323.44 | | L27 | 5760 | 5116 | 207 | 437 | 92.4%|1404.27 |
   | L04 | 5760 | 5289 |  24 | 447 | 92.2%|1411.13 | | L28 | 5760 | 5086 | 200 | 474 | 91.8%|1483.23 |
   | L05 | 5760 | 5205 |  50 | 505 | 91.2%|1257.64 | | L29 | 5760 | 5014 | 247 | 499 | 91.3%|1274.78 |
   | L06 | 5760 | 5135 |  46 | 579 | 89.9%|1287.72 | | L30 | 5760 | 5017 | 263 | 480 | 91.7%|1287.74 |
   | L07 | 5760 | 5130 |  89 | 541 | 90.6%|1226.37 | | L31 | 5760 | 5186 | 202 | 372 | 93.5%|1215.72 |
   | L08 | 5760 | 5215 |  86 | 459 | 92.0%| 823.02 | | L32 | 5760 | 5186 | 194 | 380 | 93.4%|1312.16 |
   | L09 | 5760 | 5230 |  83 | 447 | 92.2%| 753.30 | | L33 | 5760 | 5003 | 248 | 509 | 91.2%|1245.97 |
   | L10 | 5760 | 5182 |  96 | 482 | 91.6%| 814.31 | | L34 | 5760 | 5064 | 208 | 488 | 91.5%|1310.79 |
   | L11 | 5760 | 5170 | 118 | 472 | 91.8%| 825.51 | | L35 | 5760 | 5171 | 131 | 458 | 92.0%| 985.25 |
   | L12 | 5760 | 5147 | 124 | 489 | 91.5%|1323.44 | | L36 | 5760 | 5180 | 112 | 468 | 91.9%| 969.41 |
   | L13 | 5760 | 5038 | 208 | 514 | 91.1%|1186.91 | | L37 | 5760 | 5182 | 104 | 474 | 91.8%|1353.52 |
   | L14 | 5760 | 5098 | 195 | 467 | 91.9%|1112.01 | | L38 | 5760 | 5094 | 125 | 541 | 90.6%|1498.27 |
   | L15 | 5760 | 5336 | 115 | 309 | 94.6%|1047.09 | | L39 | 5760 | 5248 | 108 | 404 | 93.0%|1270.80 |
   | L16 | 5760 | 5229 | 224 | 307 | 94.7%|1235.08 | | L40 | 5760 | 5254 |  99 | 407 | 92.9%|1065.89 |
   | L17 | 5760 | 5031 | 284 | 445 | 92.3%|1596.02 | | L41 | 5760 | 5165 | 101 | 494 | 91.4%| 975.17 |
   | L18 | 5760 | 5115 | 162 | 483 | 91.6%|1663.70 | | L42 | 5760 | 5150 | 109 | 501 | 91.3%|1156.67 |
   | L19 | 5760 | 5100 | 218 | 442 | 92.3%|1117.77 | | L43 | 5760 | 5271 |  78 | 411 | 92.9%| 890.19 |
   | L20 | 5760 | 5071 | 222 | 467 | 91.9%|1212.84 | | L44 | 5760 | 5192 |  77 | 491 | 91.5%|1088.96 |
   | L21 | 5760 | 5084 | 140 | 536 | 90.7%|1502.03 | | L45 | 5760 | 5223 |  67 | 470 | 91.8%| 999.66 |
   | L22 | 5760 | 5067 | 142 | 551 | 90.4%|1659.94 | | L46 | 5760 | 5281 |  50 | 429 | 92.6%|1006.86 |
   | L23 | 5760 | 5234 | 112 | 414 | 92.8%| 975.17 | | L47 | 5760 | 5204 |  33 | 523 | 90.9%|1069.65 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 66924.50 MB (Load=4614.69 | Prefill=36397.50 | Warmup=0.00 | Decode=25912.30 MB)
   SSD Data/Token (Decode)      : Avg=202.440 MB/tok (Min=126.386 | P50=199.299 | P95=270.686 | Max=402.829 MB) | Prefill=71.089 MB/tok
   NVMe Batches / Requests      : 5118 Batches | 120499 Reads | 59 LBA Merges (Avg 568.7 KB/req)
   SSD Read Bandwidth           : Avg=1242.11 MB/s | Peak=9726.91 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=66944.64 MB | Write=0.00 MB | Syscalls=129956
   Sync Stall vs Async DMA      : SyncStall=21994.75 ms | AsyncOverlapped=43305.01 ms (66.3% Overlapped)
   RAM Traffic & Effective BW   : 2072.99 GB moved | Eff=9.44 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=621.641s + Sys=26.438s (Wall=235.269s) | SysUtil=68.9% | ThrUtil=68.9% | 63.70 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  86697.89 ms (135465.4 us/tok | 39.50%)
   MoE AVX2 Q8 Expert Compute   :  90962.18 ms (142128.4 us/tok | 41.44%)
   Router + Lookahead Dispatch  :   5152.07 ms ( 8050.1 us/tok |  2.35%)
   LM Head Output Projection    :   4612.87 ms ( 7207.6 us/tok |  2.10%)
   Foreground NVMe Sync Stall   :  21994.75 ms (34366.8 us/tok | 10.02%)
   Unaccounted / OMP & Sampling :  10061.77 ms (15721.5 us/tok |  4.58%) | Total Wall=219481.53 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    71.48%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.95%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     5.47%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    13.13%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.97%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 29119.3ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\n\n<think>\nThe user is asking me to summarize "LBA-coalesced'
[Stage 3] /v1/chat/completions (stream=true SSE) 9209.1ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=5926.76 MB (2856 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3.01 tps | Avg=3.01 tps | Hit=90.7% | NVMe=1114.0 MB/s (23422.36 MB, QD=64) | RSS=11882.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.96 tps | Avg=2.99 tps | Hit=90.7% | NVMe=1305.3 MB/s (42266.54 MB, QD=64) | RSS=11905.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.95 tps | Avg=2.97 tps | Hit=90.6% | NVMe=1412.1 MB/s (61607.01 MB, QD=64) | RSS=11906.3 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.93 tps | Avg=2.96 tps | Hit=90.6% | NVMe=1490.3 MB/s (80739.91 MB, QD=64) | RSS=11906.7 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.92 tps | Avg=2.95 tps | Hit=90.6% | NVMe=1519.5 MB/s (98961.03 MB, QD=64) | RSS=11906.1 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.96 tps | Avg=2.95 tps | Hit=90.8% | NVMe=1556.7 MB/s (116266.34 MB, QD=64) | RSS=11906.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.94 tps | Avg=2.95 tps | Hit=90.8% | NVMe=1589.0 MB/s (134272.41 MB, QD=64) | RSS=11906.6 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.88 tps | Avg=2.94 tps | Hit=90.9% | NVMe=1598.5 MB/s (152057.01 MB, QD=64) | RSS=11907.1 MB
[LIVE-DECODE] 4/64 tok | Avg=1.14 tps | Hit=90.9% (LA:+0.0%) | NVMe=1565.4 MB/s (153548.54 MB) | RSS=11908.3 MB
[LIVE-DECODE] 8/64 tok | Avg=1.50 tps | Hit=90.9% (LA:+0.1%) | NVMe=1562.1 MB/s (154780.48 MB) | RSS=11907.3 MB
[LIVE-DECODE] 16/64 tok | Avg=1.98 tps | Hit=90.9% (LA:+0.2%) | NVMe=1571.2 MB/s (157215.64 MB) | RSS=11906.1 MB
[LIVE-DECODE] 24/64 tok | Avg=2.22 tps | Hit=90.9% (LA:+0.3%) | NVMe=1581.2 MB/s (159646.75 MB) | RSS=11892.3 MB
[LIVE-DECODE] 32/64 tok | Avg=2.37 tps | Hit=90.9% (LA:+0.4%) | NVMe=1590.7 MB/s (162087.99 MB) | RSS=11892.3 MB
[LIVE-DECODE] 40/64 tok | Avg=2.48 tps | Hit=90.9% (LA:+0.4%) | NVMe=1599.7 MB/s (164372.79 MB) | RSS=11892.3 MB
[LIVE-DECODE] 48/64 tok | Avg=2.55 tps | Hit=91.0% (LA:+0.5%) | NVMe=1607.3 MB/s (166524.45 MB) | RSS=11892.3 MB
[LIVE-DECODE] 56/64 tok | Avg=2.62 tps | Hit=91.0% (LA:+0.6%) | NVMe=1613.4 MB/s (168389.13 MB) | RSS=11889.4 MB
[LIVE-DECODE] 64/64 tok | Avg=2.68 tps | Hit=91.0% (LA:+0.6%) | NVMe=1618.4 MB/s (170140.04 MB) | RSS=11883.2 MB

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
   LRFU Cache / Staging Ring    : 5926.76 MB (2856/25088 exp = 11.38% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.72 MB | End=11883.24 MB | Peak=12305.49 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : " layer-wise!

!

!

!

!

!!!

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

!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=82.5% | AvgMargin=nan | MinMargin=0.039
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    6000 |  layer         |   21.48 |  99.8% |     271 |   15.00 | 695901.27 |  0 |  0 |  0 |     0.0 |
   |    2 |   42962 | -wise          |   19.25 |  98.0% |     271 |   14.61 |  564.06 |373 | 88 | 19 | 243544.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  564.06 |  0 |  0 |  0 | 243544.5 |
   |    4 |     271 | \n\n           |   16.03 |  83.1% |    1076 |   11.70 | 1195.71 | 27 |364 | 89 | 520121.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan | 1195.71 |  0 |  0 |  0 | 520121.5 |
   |    6 |     271 | \n\n           |   15.75 |  79.8% |  248046 |   11.70 |  559.98 |234 |226 | 20 | 333382.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  559.98 |  0 |  0 |  0 | 333382.0 |
   |    8 |     271 | \n\n           |   15.44 |  73.5% |       0 |   12.92 |  347.20 |287 |193 |  0 | 297369.5 |
   |   14 |       0 | !              |   15.60 |  58.4% |     271 |   14.90 |  362.36 |250 |230 |  0 | 324869.5 |
   |   15 |       0 | !              |     nan | 100.0% |       1 |     nan |  362.36 |  0 |  0 |  0 | 324869.5 |
   |   26 |       0 | !              |   16.45 |  77.6% |     271 |   14.92 |  355.64 |235 |245 |  0 | 341307.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  355.64 |  0 |  0 |  0 | 341307.0 |
   |   62 |     271 | \n\n           |   14.82 |  53.6% |       0 |   14.25 |  317.14 |359 |121 |  0 | 234894.5 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  317.14 |  0 |  0 |  0 | 234894.5 |
   |   64 |     271 | \n\n           |   14.52 |  56.7% |       0 |   13.52 |  313.32 |355 |125 |  0 | 220069.5 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  313.32 |  0 |  0 |  0 | 220069.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 695.901s, TTFT=695901.27ms): Avg=2.94 | Min=2.88 | Max=3.01 tps
   Prefill Chunks (8): C1:256t/3.0tps/91% | C2:256t/3.0tps/91% | C3:256t/2.9tps/91% | C4:256t/2.9tps/91%
                       C5:256t/2.9tps/91% | C6:256t/3.0tps/91% | C7:256t/2.9tps/91% | C8:256t/2.9tps/91%
   Decode  (64 tok, 23.894s): Avg=2.68 | Min=0.84 | Max=3.20 tps
   Latency (ms) : Min=312.87 | P10=315.76 | P25=324.87 | P50=335.36 | P75=341.70 | P90=362.36 | P95=564.06 | P99=1195.71 | Max=1195.71
   Mean/SD/Jitt : Mean=373.34ms | StdDev=158.26ms | Jitter=27.76ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (998400): RawRAM=902435 (90.39%) | Lookahead=6063 (+0.61%) | ColdMiss=89902 (9.00%) | EFF HIT=91.00%
   Lookahead    : 10211 prefetched -> 6383 consumed (62.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.9% | @64= 91.0% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |20800 |18000 | 221 |2579 | 87.6%|4716.80 | | L24 |20800 |18902 | 109 |1789 | 91.4%|3838.72 |
   | L01 |20800 |18386 | 153 |2261 | 89.1%|3242.29 | | L25 |20800 |18655 | 110 |2035 | 90.2%|4109.42 |
   | L02 |20800 |18267 | 147 |2386 | 88.5%|4647.73 | | L26 |20800 |18794 | 124 |1882 | 91.0%|3912.04 |
   | L03 |20800 |18782 | 143 |1875 | 91.0%|4116.94 | | L27 |20800 |18755 | 129 |1916 | 90.8%|3974.07 |
   | L04 |20800 |19071 |  87 |1642 | 92.1%|3722.90 | | L28 |20800 |18934 | 128 |1738 | 91.6%|3656.37 |
   | L05 |20800 |18581 | 170 |2049 | 90.1%|4346.29 | | L29 |20800 |18840 | 115 |1845 | 91.1%|2925.51 |
   | L06 |20800 |18473 |  86 |2241 | 89.2%|4500.44 | | L30 |20800 |18525 | 127 |2148 | 89.7%|3372.05 |
   | L07 |20800 |18476 | 178 |2146 | 89.7%|4014.33 | | L31 |20800 |18972 | 120 |1708 | 91.8%|2791.55 |
   | L08 |20800 |18871 | 166 |1763 | 91.5%|2495.21 | | L32 |20800 |18906 |  93 |1801 | 91.3%|3654.49 |
   | L09 |20800 |18938 | 152 |1710 | 91.8%|2366.97 | | L33 |20800 |18694 |  99 |2007 | 90.4%|3128.61 |
   | L10 |20800 |19015 | 114 |1671 | 92.0%|2282.30 | | L34 |20800 |18841 | 128 |1831 | 91.2%|2921.19 |
   | L11 |20800 |18956 | 176 |1668 | 92.0%|2354.52 | | L35 |20800 |18874 |  86 |1840 | 91.2%|2839.09 |
   | L12 |20800 |18976 | 179 |1645 | 92.1%|3532.30 | | L36 |20800 |18948 | 128 |1724 | 91.7%|2771.39 |
   | L13 |20800 |19115 | 138 |1547 | 92.6%|2493.38 | | L37 |20800 |18837 | 115 |1848 | 91.1%|3776.68 |
   | L14 |20800 |18865 | 153 |1782 | 91.4%|2901.03 | | L38 |20800 |18686 | 120 |1994 | 90.4%|4051.15 |
   | L15 |20800 |18994 | 141 |1665 | 92.0%|3566.14 | | L39 |20800 |19024 | 102 |1674 | 92.0%|3594.34 |
   | L16 |20800 |18840 | 196 |1764 | 91.5%|3861.28 | | L40 |20800 |18909 |  64 |1827 | 91.2%|3648.85 |
   | L17 |20800 |18823 | 167 |1810 | 91.3%|3838.72 | | L41 |20800 |18576 |  57 |2167 | 89.6%|3292.82 |
   | L18 |20800 |18857 | 168 |1775 | 91.5%|3801.12 | | L42 |20800 |18783 |  54 |1963 | 90.6%|3072.44 |
   | L19 |20800 |18808 | 151 |1841 | 91.1%|2986.01 | | L43 |20800 |18973 |  43 |1784 | 91.4%|2758.42 |
   | L20 |20800 |18599 | 180 |2021 | 90.3%|3304.35 | | L44 |20800 |18894 |  62 |1844 | 91.1%|2869.34 |
   | L21 |20800 |18979 | 158 |1663 | 92.0%|3569.90 | | L45 |20800 |18818 |  60 |1922 | 90.8%|2958.64 |
   | L22 |20800 |18948 | 181 |1671 | 92.0%|3673.29 | | L46 |20800 |19293 |  37 |1470 | 92.9%|2303.25 |
   | L23 |20800 |18759 | 144 |1897 | 90.9%|3096.92 | | L47 |20800 |18623 | 104 |2073 | 90.0%|4147.02 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 170140.04 MB (Load=4614.69 | Prefill=147442.31 | Warmup=0.00 | Decode=18083.03 MB)
   SSD Data/Token (Decode)      : Avg=282.547 MB/tok (Min=213.886 | P50=283.466 | P95=333.308 | Max=507.931 MB) | Prefill=71.993 MB/tok
   NVMe Batches / Requests      : 4578 Batches | 334727 Reads | 267 LBA Merges (Avg 520.5 KB/req)
   SSD Read Bandwidth           : Avg=1618.44 MB/s | Peak=10535.99 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=170160.58 MB | Write=0.00 MB | Syscalls=343974
   Sync Stall vs Async DMA      : SyncStall=84005.04 ms | AsyncOverlapped=94557.30 ms (53.0% Overlapped)
   RAM Traffic & Effective BW   : 5562.56 GB moved | Eff=7.73 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=2197.812s + Sys=58.469s (Wall=734.820s) | SysUtil=76.8% | ThrUtil=76.8% | 71.01 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 291560.68 ms (138049.6 us/tok | 40.51%)
   MoE AVX2 Q8 Expert Compute   : 316635.25 ms (149922.0 us/tok | 43.99%)
   Router + Lookahead Dispatch  :  17523.19 ms ( 8297.0 us/tok |  2.43%)
   LM Head Output Projection    :   2272.33 ms ( 1075.9 us/tok |  0.32%)
   Foreground NVMe Sync Stall   :  84005.04 ms (39775.1 us/tok | 11.67%)
   Unaccounted / OMP & Sampling :   7798.32 ms ( 3692.4 us/tok |  1.08%) | Total Wall=719794.81 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    70.90%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.01%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     4.82%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    15.59%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.68%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=58.0s | Competitor drastic-underperform cutoff=290.0s (5x Apex)
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 64 32 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=290.0s) ===
  [Colibri-Qwen38] [gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
  [Colibri-Qwen38] [gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
  [Colibri-Qwen38] reserved bits argument must be 2..8 (got 32)
=== [Colibri-Qwen38] Finished rc=1 elapsed=1.52s cancelled=False ===
=== [ik_llama.cpp] CMD: baselines/ik_llama/build\bin\Release\llama-bench.exe -m D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf -p 64 -n 32 -t 4 -r 1 (5x cutoff=290.0s) ===
  [COMP-LIVE] ik_llama.cpp: elapsed=15.0s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=30.0s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=45.0s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=60.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=75.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=90.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=105.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=120.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=135.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=150.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=165.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=180.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=195.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=210.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=225.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=240.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=255.3s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=270.3s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=285.3s / cutoff=290.0s

  [COMP-CANCEL] ik_llama.cpp exceeded 5x Apex wall time (290.3s > 290.0s); cancelling slow competitor.
=== [ik_llama.cpp] Finished rc=-9 elapsed=290.39s cancelled=True ===
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison (64p / 32g / 4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 2.24 | 2.41 | N/A | 83.36% | 813.36 | 13406.62 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 2.95 | 2.77 | N/A | 91.87% | 1242.11 | 14160.26 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.94 | 2.68 | N/A | 91.00% | 1618.44 | 12305.49 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | N/A | - | N/A | - | - | `Q38_MTP=1` / Native |
| **llama.cpp (`-lm mmap`)** | Unsupported/Fail | Unsupported/Fail | - | OS Cache | - | - | `64p/32g -t 4` |
| **llama.cpp (`-lm none`)** | Unsupported/Fail | Unsupported/Fail | - | - | - | - | `64p/32g -t 4` |
| **ikawrakow/ik_llama.cpp** | Cancelled (>5x) | Cancelled (>5x) | - | - | - | - | `64p/32g -t 4` |
================================================================================
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 846K Nov 13 12:33 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 846K Nov 13 12:33 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.46 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    412.11 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1470.13 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7165.77 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10063.88 MB/s
   RND4K Q32T16 Read                  :    458.49 MB/s (  117374 IOPS)
   RND4K Q1T1  Read                   :    620.89 MB/s (Latency: 6.29 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     48.73 GB/s
   AVX2 256-bit Sequential Write BW   :     31.89 GB/s
   STREAM Triad (A = B + s*C) BW      :     29.37 GB/s
   Random Pointer-Chase Latency       :     86.26 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     50.99 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    188.71 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.21 GB/s (FP32 Equiv)
================================================================================



=== [TEST] GLM-5.3-Flash 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_glm53_ud_iq2_xxs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : glm5-next (GLM-5.3-Flash)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] Qwen-3.8-Flash-Next 100% Greedy Parity: ./apex.exe verify-parity --model tests/synth_qwen38_ud_iq2_xs.gguf ===
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
[Apex-Parity] Model Architecture : qwen4exp (Qwen-3.8-Flash-Next)
[Apex-Parity] Max Logit ULP Diff : 0.000000000e+00
[Apex-Parity] Greedy Token Match : 16 / 16 (100.00% Parity)


=== [TEST] GLM-5.3-Flash 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_glm53_ud_iq2_xxs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: GLM-5.3-Flash-UD-IQ2_XXS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=3.48 MB | Expert Cache=1.93 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1426.41 tps | Avg=1426.41 tps | Hit=99.5% | NVMe=1618.7 MB/s (6.19 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1234.90 tps | Avg=1323.76 tps | Hit=99.5% | NVMe=1560.3 MB/s (7.01 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1100.31 tps | Avg=1239.83 tps | Hit=99.5% | NVMe=1503.8 MB/s (7.78 MB, QD=64) | RSS=71.9 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=973.21 tps | Avg=1160.36 tps | Hit=99.5% | NVMe=1459.6 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=874.72 tps | Avg=1089.22 tps | Hit=99.5% | NVMe=1425.9 MB/s (9.33 MB, QD=64) | RSS=72.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=814.66 tps | Avg=1031.29 tps | Hit=99.5% | NVMe=1409.4 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=748.54 tps | Avg=978.49 tps | Hit=99.5% | NVMe=1386.8 MB/s (10.83 MB, QD=64) | RSS=72.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=689.87 tps | Avg=929.86 tps | Hit=99.5% | NVMe=1371.2 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=197.21 tps | Hit=99.5% (LA:+0.0%) | NVMe=1328.6 MB/s (12.43 MB) | RSS=73.1 MB
[LIVE-DECODE] 16/32 tok | Avg=197.39 tps | Hit=99.5% (LA:+0.1%) | NVMe=1301.6 MB/s (13.10 MB) | RSS=73.1 MB
[LIVE-DECODE] 24/32 tok | Avg=198.18 tps | Hit=99.5% (LA:+0.1%) | NVMe=1282.1 MB/s (13.25 MB) | RSS=73.1 MB
[LIVE-DECODE] 32/32 tok | Avg=198.44 tps | Hit=99.5% (LA:+0.1%) | NVMe=1275.4 MB/s (13.30 MB) | RSS=73.1 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=73.15 MB | Peak=73.15 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2202.47 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.13 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.13 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.16 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.16 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.00 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.00 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.00 | 11 |  1 |  0 |    49.5 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.13 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.13 |  0 |  0 |  0 |   173.2 |
   |   14 |     220 | tok_220        |  147.52 |  55.4% |      55 |  147.01 |    5.10 |  9 |  3 |  0 |   173.2 |
   |   15 |     197 | tok_197        |   65.84 |  97.8% |     133 |   62.03 |    5.10 |  0 |  0 |  0 |   173.2 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.02 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.02 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    4.96 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    4.96 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.202s, TTFT=2202.47ms): Avg=929.86 | Min=689.87 | Max=1426.41 tps
   Prefill Chunks (8): C1:256t/1426.4tps/99% | C2:256t/1234.9tps/99% | C3:256t/1100.3tps/99% | C4:256t/973.2tps/99%
                       C5:256t/874.7tps/99% | C6:256t/814.7tps/99% | C7:256t/748.5tps/99% | C8:256t/689.9tps/99%
   Decode  (32 tok, 0.161s): Avg=198.44 | Min=193.87 | Max=202.84 tps
   Latency (ms) : Min=4.93 | P10=4.96 | P25=5.00 | P50=5.03 | P75=5.10 | P90=5.13 | P95=5.16 | P99=5.16 | Max=5.16
   Mean/SD/Jitt : Mean=5.04ms | StdDev=0.06ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   NVMe Batches / Requests      : 41 Batches | 748 Reads | 438 LBA Merges (Avg 18.2 KB/req)
   SSD Read Bandwidth           : Avg=1275.45 MB/s | Peak=5952.38 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=6.75 ms | AsyncOverlapped=8.97 ms (57.1% Overlapped)
   RAM Traffic & Effective BW   : 1.43 GB moved | Eff=0.61 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=3.125s + Sys=0.781s (Wall=2.384s) | SysUtil=41.0% | ThrUtil=41.0% | 37.89 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1990.91 ms (  957.2 us/tok | 84.23%)
   MoE AVX2 Q8 Expert Compute   :    242.77 ms (  116.7 us/tok | 10.27%)
   Router + Lookahead Dispatch  :     59.68 ms (   28.7 us/tok |  2.52%)
   LM Head Output Projection    :      5.92 ms (    2.8 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      6.75 ms (    3.2 us/tok |  0.29%)
   Unaccounted / OMP & Sampling :     57.72 ms (   27.7 us/tok |  2.44%) | Total Wall=2363.74 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    28.13%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.10%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.52%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    67.52%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.73%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1872.94 tps | Avg=1872.94 tps | Hit=99.2% | NVMe=2408.3 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1785.88 tps | Avg=1828.37 tps | Hit=99.2% | NVMe=3148.3 MB/s (42.92 MB, QD=64) | RSS=89.4 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1749.01 tps | Avg=1801.13 tps | Hit=99.2% | NVMe=3596.3 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1645.46 tps | Avg=1759.52 tps | Hit=99.2% | NVMe=3951.9 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1483.47 tps | Avg=1696.38 tps | Hit=99.2% | NVMe=4145.8 MB/s (97.14 MB, QD=64) | RSS=90.5 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1438.08 tps | Avg=1647.08 tps | Hit=99.2% | NVMe=4358.0 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1262.66 tps | Avg=1578.43 tps | Hit=99.2% | NVMe=4492.1 MB/s (133.27 MB, QD=64) | RSS=91.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1239.80 tps | Avg=1526.32 tps | Hit=99.2% | NVMe=4651.5 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=177.66 tps | Hit=99.2% (LA:+0.0%) | NVMe=4527.5 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=178.54 tps | Hit=99.2% (LA:+0.1%) | NVMe=4435.4 MB/s (153.44 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=178.30 tps | Hit=99.2% (LA:+0.1%) | NVMe=4320.9 MB/s (154.78 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=178.79 tps | Hit=99.2% (LA:+0.1%) | NVMe=4229.3 MB/s (155.58 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=91.79 MB | Peak=91.79 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (32 tok) : "qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_129qtok_68qtok_209qtok_223qtok_113qtok_229qtok_24qtok_229qtok_148qtok_209qtok_193qtok_146qtok_148qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49qtok_254qtok_49"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=92.5% | AvgMargin=9.488 | MinMargin=0.056
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 | 1341.79 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    5.61 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   94.59 | 100.0% |     177 |   84.92 |    5.61 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    5.64 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   85.06 |  99.7% |     177 |   78.63 |    5.64 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    5.57 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   82.87 |  99.7% |     129 |   77.18 |    5.57 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    5.69 | 16 |  0 |  0 |    32.0 |
   |    9 |      49 | qtok_49        |   83.22 |  99.9% |     129 |   76.57 |    5.69 |  0 |  0 |  0 |    32.0 |
   |   18 |     229 | qtok_229       |   80.70 | 100.0% |      33 |   70.24 |    5.69 | 10 |  6 |  0 |   170.8 |
   |   19 |     148 | qtok_148       |   68.09 |  43.4% |      67 |   67.82 |    5.69 |  0 |  0 |  0 |   170.8 |
   |   10 |     254 | qtok_254       |   71.08 |  99.9% |      66 |   64.40 |    5.64 | 15 |  1 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   71.22 |  99.9% |      66 |   64.31 |    5.54 | 14 |  2 |  0 |    87.5 |
   |   31 |      49 | qtok_49        |  125.25 | 100.0% |     177 |   99.98 |    5.54 |  0 |  0 |  0 |    87.5 |
   |   32 |     254 | qtok_254       |   71.45 |  98.0% |      66 |   67.49 |    5.58 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  131.17 | 100.0% |     129 |  104.87 |    5.58 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.342s, TTFT=1341.79ms): Avg=1526.32 | Min=1239.80 | Max=1872.94 tps
   Prefill Chunks (8): C1:256t/1872.9tps/99% | C2:256t/1785.9tps/99% | C3:256t/1749.0tps/99% | C4:256t/1645.5tps/99%
                       C5:256t/1483.5tps/99% | C6:256t/1438.1tps/99% | C7:256t/1262.7tps/99% | C8:256t/1239.8tps/99%
   Decode  (32 tok, 0.179s): Avg=178.79 | Min=175.65 | Max=183.12 tps
   Latency (ms) : Min=5.46 | P10=5.49 | P25=5.58 | P50=5.60 | P75=5.64 | P90=5.69 | P95=5.69 | P99=5.69 | Max=5.69
   Mean/SD/Jitt : Mean=5.59ms | StdDev=0.06ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (33024): RawRAM=32720 (99.08%) | Lookahead=48 (+0.15%) | ColdMiss=256 (0.78%) | EFF HIT=99.22%
   Lookahead    : 60 prefetched -> 54 consumed (90.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 99.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 8256 | 8190 |   2 |  64 | 99.2%|   3.58 | | L02 | 8256 | 8170 |  22 |  64 | 99.2%|   4.72 |
   | L01 | 8256 | 8184 |   8 |  64 | 99.2%|   4.12 | | L03 | 8256 | 8176 |  16 |  64 | 99.2%|   4.39 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 155.58 MB (Load=6.87 | Prefill=144.44 | Warmup=0.00 | Decode=4.28 MB)
   SSD Data/Token (Decode)      : Avg=0.134 MB/tok (Min=0.031 | P50=0.113 | P95=0.523 | Max=0.523 MB) | Prefill=0.071 MB/tok
   NVMe Batches / Requests      : 95 Batches | 34221 Reads | 33838 LBA Merges (Avg 4.7 KB/req)
   SSD Read Bandwidth           : Avg=4229.31 MB/s | Peak=9975.86 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=24.69 MB | Write=0.00 MB | Syscalls=400
   Sync Stall vs Async DMA      : SyncStall=9.49 ms | AsyncOverlapped=35.24 ms (78.8% Overlapped)
   RAM Traffic & Effective BW   : 2.10 GB moved | Eff=1.38 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=2.734s + Sys=0.359s (Wall=1.553s) | SysUtil=49.8% | ThrUtil=49.8% | 46.06 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    937.04 ms (  450.5 us/tok | 61.62%)
   MoE AVX2 Q8 Expert Compute   :    380.81 ms (  183.1 us/tok | 25.04%)
   Router + Lookahead Dispatch  :     82.73 ms (   39.8 us/tok |  5.44%)
   LM Head Output Projection    :      5.74 ms (    2.8 us/tok |  0.38%)
   Foreground NVMe Sync Stall   :      9.49 ms (    4.6 us/tok |  0.62%)
   Unaccounted / OMP & Sampling :    104.95 ms (   50.5 us/tok |  6.90%) | Total Wall=1520.77 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.04%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.01%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.32%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    66.41%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.22%  |
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
    "ttft_ms": 243.74,
    "avg_tps": 672.83,
    "min_tps": 553.65,
    "max_tps": 783.36
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 140.71,
    "min_tps": 95.13,
    "max_tps": 148.66,
    "p50_ms": 6.98,
    "p90_ms": 7.29,
    "p99_ms": 10.51,
    "mean_ms": 7.11,
    "jitter_ms": 0.3
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
    "avg_mbs": 1160.53,
    "peak_mbs": 5733.94,
    "sync_wait_ms": 2.75,
    "async_overlap_ms": 5.84
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
    "dense_attention": 389.4,
    "moe_compute": 107.08,
    "router_lookahead": 7.8,
    "lm_head": 8.85,
    "unaccounted": 5.05
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 79.03,
    "ram_bandwidth_pinning": 1.7,
    "expert_cache_lrfu": 15.31,
    "lookahead_parallel_overlap": 2.43,
    "ssd_nvme_throughput": 1.53,
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
    "ttft_ms": 303.12,
    "avg_tps": 541.03,
    "min_tps": 382.58,
    "max_tps": 612.36
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 127.29,
    "min_tps": 106.01,
    "max_tps": 132.72,
    "p50_ms": 7.75,
    "p90_ms": 8.05,
    "p99_ms": 9.43,
    "mean_ms": 7.86,
    "jitter_ms": 0.22
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
    "avg_mbs": 1517.56,
    "peak_mbs": 7666.69,
    "sync_wait_ms": 7.55,
    "async_overlap_ms": 22.75
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
    "dense_attention": 344.17,
    "moe_compute": 197.79,
    "router_lookahead": 8.8,
    "lm_head": 8.65,
    "unaccounted": 42.55
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 74.26,
    "ram_bandwidth_pinning": 1.98,
    "expert_cache_lrfu": 13.39,
    "lookahead_parallel_overlap": 6.13,
    "ssd_nvme_throughput": 4.24,
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
================================================================================
 [3.2] Downloading Official Prebuilt llama.cpp AVX2 Windows Binaries
================================================================================
================================================================================
 [3.3] Cloning & Building ik_llama.cpp (CPU AVX2 Release)
================================================================================
Cloning into 'ik_llama'...
error: unable to create file examples/server/webui_llamacpp/src/lib/components/app/chat/ChatAttachments/ChatAttachmentsPreview/ChatAttachmentsPreviewCurrentItem/ChatAttachmentsPreviewCurrentItemUnavailable.svelte: Filename too long
Updating files:  87% (2469/2832)
Updating files:  88% (2493/2832)
Updating files:  89% (2521/2832)
Updating files:  90% (2549/2832)
Updating files:  91% (2578/2832)
Updating files:  92% (2606/2832)
Updating files:  93% (2634/2832)
Updating files:  94% (2663/2832)
Updating files:  95% (2691/2832)
Updating files:  96% (2719/2832)
Updating files:  97% (2748/2832)
Updating files:  98% (2776/2832)
Updating files:  99% (2804/2832)
Updating files: 100% (2832/2832)
Updating files: 100% (2832/2832), done.
fatal: unable to checkout working tree
warning: Clone succeeded, but checkout failed.
You can inspect what was checked out with 'git status'
and retry with 'git restore --source=HEAD :/'

-- Building for: Visual Studio 18 2026
-- The C compiler identification is MSVC 19.51.36260.0
-- The CXX compiler identification is MSVC 19.51.36260.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/Program Files/Microsoft Visual Studio/18/Enterprise/VC/Tools/MSVC/14.51.36231/bin/Hostx64/x64/cl.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/Program Files/Microsoft Visual Studio/18/Enterprise/VC/Tools/MSVC/14.51.36231/bin/Hostx64/x64/cl.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found Git: C:/Program Files/Git/ucrt64/bin/git.exe (found version "2.56.0.windows.4")
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Failed
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - not found
-- Found Threads: TRUE
-- Found OpenMP_C: -openmp (found version "2.0")
-- Found OpenMP_CXX: -openmp (found version "2.0")
-- Found OpenMP: TRUE (found version "2.0")
-- OpenMP found
-- Using optimized iqk matrix multiplications
-- Enabling IQK Flash Attention kernels
-- Including all IQK FA kernels
-- ccache found, compilation results will be cached. Disable with GGML_CCACHE=OFF.
-- CMAKE_SYSTEM_PROCESSOR: AMD64
-- CMAKE_GENERATOR_PLATFORM: 
-- x86 detected
CMake Warning at common/CMakeLists.txt:26 (message):
  Git index not found in git repository.


-- ARCH_FLAGS = 
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public/index.html.gz
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public_llamacpp/index_llamacpp.html.gz
TARGET_SRCS contains: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/server/public_llamacpp/loading.html
-- Configuring done (19.6s)
-- Generating done (0.9s)
CMake Warning (unused-cli):
  Manually-specified variables were not used by the project:

    GGML_F16C


-- Build files have been written to: D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build
MSBuild version 18.11.1-1.26513.3+940033be3 for .NET Framework

  1>Checking Build System
  Generating build details from Git
  -- Found Git: C:/Program Files/Git/ucrt64/bin/git.exe (found version "2.56.0.windows.4")
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/common/CMakeLists.txt
  build-info.cpp
  build_info.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\build_info.dir\Release\build_info.lib
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/ggml/src/CMakeLists.txt
  ggml.c
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(4020,13): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(4038,13): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25): warning C4477: 'fprintf' : format string '%ld' requires an argument of type 'long', but variadic argument 2 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(6819,25):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 2 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 3 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 4 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 5 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 6 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 7 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 8 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16): warning C4477: 'printf' : format string '%ld' requires an argument of type 'long', but variadic argument 9 has type 'int64_t' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%lld' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%Id' in the format string
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml.c(11118,16):
      consider using '%I64d' in the format string
  
  ggml-alloc.c
  ggml-quants.c
C:\Program Files (x86)\Windows Kits\10\Include\10.0.26100.0\ucrt\assert.h(21,9): warning C4005: 'static_assert': macro redefinition [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  (compiling source file '../../../ggml/src/ggml-quants.c')
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-common.h(69,9):
      see previous definition of 'static_assert'
  
  ggml-aarch64.c
C:\Program Files (x86)\Windows Kits\10\Include\10.0.26100.0\ucrt\assert.h(21,9): warning C4005: 'static_assert': macro redefinition [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  (compiling source file '../../../ggml/src/ggml-aarch64.c')
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-common.h(69,9):
      see previous definition of 'static_assert'
  
  Generating Code...
  ggml-backend.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\ggml-backend.cpp(2124,30): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  ggml-moe-prefetch.cpp
  iqk_mul_mat.cpp
  iqk_kda.cpp
  iqk_flash_attn.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(141,94): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(141,82): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(179,13): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(187,25): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(188,61): warning C4244: '=': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(196,38): warning C4244: '=': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(273,112): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(281,119): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(298,22): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(346,80): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(346,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(394,80): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(394,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_flash_attn.cpp(481,24): warning C4244: '=': conversion from 'uint64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_fa_576_512.cpp
  iqk_fa_512_512.cpp
  iqk_fa_320_256.cpp
  iqk_fa_192_128.cpp
  iqk_fa_192_192.cpp
  iqk_fa_256_256.cpp
  iqk_fa_128_128.cpp
  iqk_fa_96_96.cpp
  iqk_fa_64_64.cpp
  iqk_gemm_floats.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_floats.cpp(637,9): warning C4065: switch statement contains 'default' but no 'case' labels [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_kquants.cpp
  iqk_gemm_ktquants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(174,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(174,23):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(103,8):
          while compiling class template '`anonymous-namespace'::Trellis3'
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(216,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_ktquants.cpp(266,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_iquants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(316,30): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(332,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_iquants.cpp(365,23): warning C4141: 'inline': used more than once [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_gemm_iqk_quants.cpp
  iqk_gemm_1bit.cpp
  Generating Code...
  Compiling...
  iqk_gemm_legacy_quants.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\ggml\src\iqk\iqk_gemm_legacy_quants.cpp(2623,29): warning C4068: unknown pragma 'GCC' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\ggml\src\ggml.vcxproj]
  iqk_quantize.cpp
  iqk_cpu_ops.cpp
  Generating Code...
  Auto build dll exports
     Creating library D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/ggml/src/Release/ggml.lib and object D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/ggml/src/Release/ggml.exp
  ggml.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\ggml.dll
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/src/CMakeLists.txt
  llama.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(683,52): warning C4805: '!=': unsafe mix of type 'const int' and type 'const bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(714,52): warning C4805: '!=': unsafe mix of type 'int' and type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4219,35): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4228,31): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4246,35): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4501,26): warning C4018: '>=': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4505,72): warning C4018: '>=': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4848,58): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(4960,37): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details. [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(5035,45): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details. [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(8053,65): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9544,29): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9559,29): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9747,60): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9667,9): warning C4297: 'llama_init_from_model': function assumed not to throw an exception but does [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama.cpp(9667,9):
      __declspec(nothrow), throw(), noexcept(true), or noexcept was specified on the function
  
  llama-spec-features.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-spec-features.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-spec-features.cpp')
  
  llama-spec-features-dflash.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-spec-features-dflash.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-spec-features-dflash.cpp')
  
  llama-dflash.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-dflash.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-dflash.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-dflash.cpp(533,122): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-dsv4.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-dsv4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-dsv4.cpp')
  
  llama-vocab.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-vocab.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-vocab.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(680,82): warning C4267: '=': conversion from 'size_t' to 'llm_symbol::index', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(683,61): warning C4267: '=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(784,25): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(784,25): warning C4267: 'initializing': conversion from 'size_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(1352,55): warning C4267: 'argument': conversion from 'size_t' to 'llama_token', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(1357,31): warning C4267: 'argument': conversion from 'size_t' to 'llama_token', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(2922,26): warning C4244: 'return': conversion from 'long' to 'uint8_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(2927,26): warning C4244: 'return': conversion from 'long' to 'uint8_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(3097,74): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(3100,70): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-vocab.cpp(3889,20): warning C4267: 'return': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-grammar.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-grammar.cpp(605,37): warning C4267: 'initializing': conversion from 'size_t' to 'uint32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-sampling.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(31,20): warning C4244: '=': conversion from 'time_t' to 'uint32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(42,23): warning C4267: '=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(138,23): warning C4267: '=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(411,33): warning C4244: '=': conversion from 'double' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(415,34): warning C4244: '/=': conversion from 'double' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(461,24): warning C4267: '=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(599,27): warning C4244: 'initializing': conversion from 'float' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(599,27): warning C4244: 'initializing': conversion from 'float' to 'const int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(619,61): warning C4244: 'argument': conversion from 'const int32_t' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(989,38): warning C4244: '=': conversion from 'float' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(1012,31): warning C4244: 'initializing': conversion from 'double' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-sampling.cpp(1241,68): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-mmap.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-mmap.cpp(120,89): warning C4267: 'argument': conversion from 'size_t' to 'DWORD', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-mmap.cpp(143,99): warning C4267: 'argument': conversion from 'size_t' to 'DWORD', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  llama-model-loader.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-model-loader.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/llama-model-loader.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(472,29): warning C4267: '=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1332,32): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1332,32): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1415,26): warning C4244: 'initializing': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1415,26): warning C4244: 'initializing': conversion from 'const int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1416,26): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1416,26): warning C4267: 'initializing': conversion from 'size_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1427,88): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1460,22): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1460,22): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267: 'argument': conversion from 'size_t' to 'const _Ty', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267:             _Ty=int32_t [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1461,80): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1485,87): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1971,61): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267: '=': conversion from 'size_t' to 'T', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267:             T=unsigned int [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(857,22):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1934,96):
          see reference to function template instantiation 'bool llama_model_loader::get_arr_n<unsigned int>(const std::string &,unsigned int &,bool)' being compiled
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244: '=': conversion from 'const int64_t' to 'OT', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:             OT=uint32_t [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1033,12):
          see reference to function template instantiation 'bool llama_model_loader::get_key<uint32_t>(const std::string &,T &,const bool)' being compiled
          with
          [
              T=uint32_t
          ]
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,42):
          see reference to class template instantiation 'GGUFMeta::GKV<uint32_t>' being compiled
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(194,21):
          while compiling class template member function 'bool GGUFMeta::GKV<uint32_t>::set(const gguf_context *,const int,T &,const llama_model_kv_override *)'
          with
          [
              T=uint32_t
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(204,13):
              see the first reference to 'GGUFMeta::GKV<uint32_t>::set' in 'GGUFMeta::GKV<uint32_t>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(208,13):
              see the first reference to 'GGUFMeta::GKV<uint32_t>::set' in 'GGUFMeta::GKV<uint32_t>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,22):
              see the first reference to 'GGUFMeta::GKV<uint32_t>::set' in 'llama_model_loader::get_key'
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(195,17):
          see reference to function template instantiation 'bool GGUFMeta::GKV<uint32_t>::try_override<T>(OT &,const llama_model_kv_override *)' being compiled
          with
          [
              T=uint32_t,
              OT=uint32_t
          ]
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244: '=': conversion from 'const int64_t' to 'OT', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:             OT=int [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(441,9):
          see reference to function template instantiation 'bool llama_model_loader::get_key<int>(const std::string &,T &,const bool)' being compiled
          with
          [
              T=int
          ]
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,42):
          see reference to class template instantiation 'GGUFMeta::GKV<int>' being compiled
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(194,21):
          while compiling class template member function 'bool GGUFMeta::GKV<int>::set(const gguf_context *,const int,T &,const llama_model_kv_override *)'
          with
          [
              T=int
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(204,13):
              see the first reference to 'GGUFMeta::GKV<int>::set' in 'GGUFMeta::GKV<int>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(208,13):
              see the first reference to 'GGUFMeta::GKV<int>::set' in 'GGUFMeta::GKV<int>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,22):
              see the first reference to 'GGUFMeta::GKV<int>::set' in 'llama_model_loader::get_key'
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(195,17):
          see reference to function template instantiation 'bool GGUFMeta::GKV<int>::try_override<T>(OT &,const llama_model_kv_override *)' being compiled
          with
          [
              T=int,
              OT=int
          ]
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244: '=': conversion from 'const int64_t' to 'OT', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:             OT=uint16_t [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30): warning C4244:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(168,30):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(385,86):
          see reference to class template instantiation 'GGUFMeta::GKV<uint16_t>' being compiled
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(194,21):
          while compiling class template member function 'bool GGUFMeta::GKV<uint16_t>::set(const gguf_context *,const int,T &,const llama_model_kv_override *)'
          with
          [
              T=uint16_t
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(204,13):
              see the first reference to 'GGUFMeta::GKV<uint16_t>::set' in 'GGUFMeta::GKV<uint16_t>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(208,13):
              see the first reference to 'GGUFMeta::GKV<uint16_t>::set' in 'GGUFMeta::GKV<uint16_t>::set'
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,22):
              see the first reference to 'GGUFMeta::GKV<uint16_t>::set' in 'llama_model_loader::get_key'
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(195,17):
          see reference to function template instantiation 'bool GGUFMeta::GKV<uint16_t>::try_override<T>(OT &,const llama_model_kv_override *)' being compiled
          with
          [
              T=uint16_t,
              OT=uint16_t
          ]
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244: '=': conversion from 'const double' to 'T', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244:             T=float [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30): warning C4244:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(178,30):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(1926,35):
          see reference to function template instantiation 'bool llama_model_loader::get_key<float>(llm_kv,float &,bool)' being compiled
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(964,12):
          see reference to function template instantiation 'bool llama_model_loader::get_key<T>(const std::string &,T &,const bool)' being compiled
          with
          [
              T=float
          ]
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,42):
          see reference to class template instantiation 'GGUFMeta::GKV<T>' being compiled
          with
          [
              T=float
          ]
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(194,21):
          while compiling class template member function 'bool GGUFMeta::GKV<T>::set(const gguf_context *,const int,T &,const llama_model_kv_override *)'
          with
          [
              T=float
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(204,13):
              see the first reference to 'GGUFMeta::GKV<T>::set' in 'GGUFMeta::GKV<T>::set'
          with
          [
              T=float
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(208,13):
              see the first reference to 'GGUFMeta::GKV<T>::set' in 'GGUFMeta::GKV<T>::set'
          with
          [
              T=float
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(953,22):
              see the first reference to 'GGUFMeta::GKV<T>::set' in 'llama_model_loader::get_key'
          with
          [
              T=float
          ]
              D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-model-loader.cpp(964,12):
              see the

... [TRUNCATED MIDDLE FOR README LIMIT] ...

_v41::<lambda_3>::operator ()<llama_context::dsv4_runtime::comp_context>(const _T1 &) const' being compiled
          with
          [
              _T1=llama_context::dsv4_runtime::comp_context
          ]
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2504,64): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2629,74): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2798,59): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2853,27): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_deepseek4.cpp(2853,27): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_openpangu.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_openpangu.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_openpangu.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(269,77): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(292,56): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(354,54): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(375,93): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(537,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(550,63): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(678,73): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(759,57): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(813,47): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(1186,28): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_openpangu.cpp(1186,28): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_glm4.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_glm4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_glm4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(17,62): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(17,49): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(43,40): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(43,40): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(70,72): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(72,72): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(170,36): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(170,36): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(217,71): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(220,65): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(297,62): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(297,49): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(392,40): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm4.cpp(392,40): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_bitnet.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bitnet.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bitnet.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bitnet.cpp(64,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bitnet.cpp(71,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bitnet.cpp(189,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bitnet.cpp(196,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_cohere2.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_cohere2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_cohere2.cpp')
  
  build_cohere2_moe.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_cohere2_moe.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_cohere2_moe.cpp')
  
  Generating Code...
  Compiling...
  build_t5.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_t5.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_t5.cpp')
  
  build_jais.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_jais.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_jais.cpp')
  
  build_chatglm.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_chatglm.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_chatglm.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_chatglm.cpp(50,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_chatglm.cpp(57,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_dots1.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_dots1.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_dots1.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_dots1.cpp(50,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_dots1.cpp(59,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_ernie45.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_ernie45.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_ernie45.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_ernie45.cpp(63,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_ernie45.cpp(66,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_hunyuan.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_hunyuan.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_hunyuan.cpp')
  
  build_mimo2.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_mimo2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_mimo2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_mimo2.cpp(26,36): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_mimo2.cpp(26,36): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_flint.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_flint.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_flint.cpp')
  
  build_openai.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_openai.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_openai.cpp')
  
  build_bailingmoe2.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bailingmoe2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bailingmoe2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(27,36): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(27,36): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(30,62): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(30,49): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(50,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe2.cpp(52,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_bailingmoe3.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bailingmoe3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_bailingmoe3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe3.cpp(31,58): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_bailingmoe3.cpp(31,51): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_glm5next.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_glm5next.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_glm5next.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm5next.cpp(44,60): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm5next.cpp(176,55): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_glm5next.cpp(198,63): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_raon1.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_raon1.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_raon1.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_raon1.cpp(45,78): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_raon1.cpp(45,71): warning C4244: 'argument': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_raon1.cpp(248,97): warning C4244: 'argument': conversion from 'int64_t' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_xing4.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_xing4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_xing4.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_xing4.cpp(21,60): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_xing4.cpp(123,94): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_xing4.cpp(124,94): warning C4244: 'argument': conversion from 'int64_t' to 'float', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_minimaxm2.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_minimaxm2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_minimaxm2.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(88,33): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(89,33): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(98,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(100,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(223,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm2.cpp(226,21): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_minimaxm3.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_minimaxm3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_minimaxm3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_minimaxm3.cpp(21,61): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_smollm3.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_smollm3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_smollm3.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_smollm3.cpp(45,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\graphs\build_smollm3.cpp(49,68): warning C4244: 'argument': conversion from 'const int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  build_spark2_5.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(146,40): warning C4305: 'initializing': truncation from 'double' to 'float' [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_spark2_5.cpp')
  
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\src\llama-hparams.h(378,47): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\src\llama.vcxproj]
  (compiling source file '../../src/graphs/build_spark2_5.cpp')
  
  Generating Code...
  Auto build dll exports
     Creating library D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/src/Release/llama.lib and object D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/build/src/Release/llama.exp
  llama.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\llama.dll
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/common/CMakeLists.txt
  chat-auto-parser-generator.cpp
  chat-auto-parser-helpers.cpp
  chat-diff-analyzer.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat-diff-analyzer.cpp(762,25): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat-diff-analyzer.cpp(763,25): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat-diff-analyzer.cpp(805,54): warning C4267: '-=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat-diff-analyzer.cpp(806,53): warning C4267: '+=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  chat-peg-parser.cpp
  common.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\common.cpp(1083,30): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details. [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  sampling.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(303,20): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(303,20): warning C4267: 'initializing': conversion from 'size_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267: '=': conversion from 'size_t' to '_Ty', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267:             _Ty=int [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(789,19): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(800,31): warning C4267: 'argument': conversion from 'size_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(939,5): warning C4804: '+=': unsafe use of type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(945,5): warning C4804: '-=': unsafe use of type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(968,30): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(981,34): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(986,34): warning C4018: '<': signed/unsigned mismatch [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1075,27): warning C4267: '+=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1079,27): warning C4267: '+=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1115,29): warning C4267: '-=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1116,47): warning C4267: '=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\sampling.cpp(1154,25): warning C4267: '-=': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  console.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\console.cpp(253,30): warning C4267: 'initializing': conversion from 'size_t' to 'DWORD', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\console.cpp(407,28): warning C4267: 'initializing': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  json-partial.cpp
  llguidance.cpp
  json-schema-to-grammar.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(97,46): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(97,37): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(112,50): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(112,41): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(173,20): warning C4244: 'initializing': conversion from 'int64_t' to 'char', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(192,29): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(203,33): warning C4267: 'argument': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(498,60): warning C4101: 'e': unreferenced local variable [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\json-schema-to-grammar.cpp(809,72): warning C4101: 'e': unreferenced local variable [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  train.cpp
  log.cpp
  ngram-cache.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-cache.cpp(20,51): warning C4244: 'argument': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-cache.cpp(212,31): warning C4267: 'initializing': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-cache.cpp(212,31): warning C4267: 'initializing': conversion from 'size_t' to 'const int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  ngram-map.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(158,58): warning C4267: '=': conversion from 'size_t' to 'uint32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(169,24): warning C4267: 'initializing': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267: '=': conversion from 'size_t' to '_Ty', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267:             _Ty=std::_Vbase [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(321,45): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267: '=': conversion from 'size_t' to '_Ty', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267:         with [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267:         [ [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267:             _Ty=std::_Vbase [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\ngram-map.cpp(330,41): warning C4267:         ] [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  peg-parser.cpp
  speculative.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(496,76): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(564,54): warning C4267: 'argument': conversion from 'size_t' to 'llama_pos', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(576,32): warning C4267: 'initializing': conversion from 'size_t' to 'llama_pos', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(576,32): warning C4267: 'initializing': conversion from 'size_t' to 'const llama_pos', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(1269,77): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\speculative.cpp(2571,59): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  spec-tuner.cpp
  unicode.cpp
  ngram-mod.cpp
  suffix-tree.cpp
  Generating Code...
  Compiling...
  regex-partial.cpp
  reasoning-budget.cpp
  chat.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat.cpp(52,32): warning C4101: 'e': unreferenced local variable [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat.cpp(3132,70): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\chat.cpp(3145,49): warning C4267: 'argument': conversion from 'size_t' to 'int32_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  lexer.cpp
  parser.cpp
  runtime.cpp
  value.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\jinja\value.cpp(738,28): warning C4244: 'initializing': conversion from 'int64_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\common\jinja\value.cpp(738,28): warning C4244: 'initializing': conversion from 'int64_t' to 'const int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  string.cpp
  caps.cpp
  Generating Code...
sampling.obj : warning LNK4006: "struct common_reasoning_budget_ctx * __cdecl common_reasoning_budget_init(struct llama_vocab const *,class std::vector<int,class std::allocator<int> > const &,class std::vector<int,class std::allocator<int> > const &,class std::vector<int,class std::allocator<int> > const &,int,enum common_reasoning_budget_state)" (?common_reasoning_budget_init@@YAPEAUcommon_reasoning_budget_ctx@@PEBUllama_vocab@@AEBV?$vector@HV?$allocator@H@std@@@std@@11HW4common_reasoning_budget_state@@@Z) already defined in reasoning-budget.obj; second definition ignored [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
sampling.obj : warning LNK4006: "enum common_reasoning_budget_state __cdecl common_reasoning_budget_get_state(struct common_reasoning_budget_ctx const *)" (?common_reasoning_budget_get_state@@YA?AW4common_reasoning_budget_state@@PEBUcommon_reasoning_budget_ctx@@@Z) already defined in reasoning-budget.obj; second definition ignored [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\common.vcxproj]
  common.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\Release\common.lib
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/llama-bench/CMakeLists.txt
  llama-bench.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(480,30): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details. [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\examples\llama-bench\llama-bench.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(1573,31): warning C4267: '=': conversion from 'size_t' to 'int', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\examples\llama-bench\llama-bench.vcxproj]
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(93,13): warning C4244: 'initializing': conversion from 'double' to 'size_t', possible loss of data [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\examples\llama-bench\llama-bench.vcxproj]
      D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(93,13):
      the template instantiation context (the oldest one first) is
          D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\llama-bench\llama-bench.cpp(1503,18):
          see reference to function template instantiation 'T stdev<size_t>(const std::vector<size_t,std::allocator<size_t>> &)' being compiled
          with
          [
              T=size_t
          ]
  
  llama-bench.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\llama-bench.exe
MSBuild version 18.11.1-1.26513.3+940033be3 for .NET Framework

  build_info.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\build_info.dir\Release\build_info.lib
  Auto build dll exports
  ggml.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\ggml.dll
  Auto build dll exports
  llama.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\llama.dll
  common.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\common\Release\common.lib
  Building Custom Rule D:/a/apex-inference-benchmarker/apex-inference-benchmarker/baselines/ik_llama/examples/main/CMakeLists.txt
  main.cpp
D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\examples\main\main.cpp(518,19): warning C4804: '>': unsafe use of type 'bool' in operation [D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\examples\main\llama-cli.vcxproj]
  llama-cli.vcxproj -> D:\a\apex-inference-benchmarker\apex-inference-benchmarker\baselines\ik_llama\build\bin\Release\llama-cli.exe
```

### 📄 `03_host_hardware_benchmark.log`
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
   System Memory (RAM): 15.99 GB Total / 13.30 GB Available
   Active Drive Space : 150.00 GB Total / 146.43 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    420.39 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1473.68 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7518.09 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9811.02 MB/s
   RND4K Q32T16 Read                  :    472.36 MB/s (  120924 IOPS)
   RND4K Q1T1  Read                   :    657.05 MB/s (Latency: 5.95 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     51.37 GB/s
   AVX2 256-bit Sequential Write BW   :     44.27 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.36 GB/s
   Random Pointer-Chase Latency       :    105.41 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     50.36 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    171.59 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     20.87 GB/s (FP32 Equiv)
================================================================================
```

### 📄 `04_qwen38_stage1_parity.log`
```text
[Apex-Parity] Verifying 100.00% Greedy Token & Batched-vs-Serial Bit Parity...
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
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 13.41 GB Available
   Active Drive Space : 150.00 GB Total / 75.80 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    482.72 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1475.33 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7544.55 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9957.06 MB/s
   RND4K Q32T16 Read                  :    417.73 MB/s (  106938 IOPS)
   RND4K Q1T1  Read                   :    638.55 MB/s (Latency: 6.12 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     55.38 GB/s
   AVX2 256-bit Sequential Write BW   :     37.78 GB/s
   STREAM Triad (A = B + s*C) BW      :     37.63 GB/s
   Random Pointer-Chase Latency       :     94.66 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.07 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    196.68 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     13.35 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=2.19 tps | Avg=2.19 tps | Hit=79.2% | NVMe=825.7 MB/s (19608.86 MB, QD=64) | RSS=13687.2 MB

 >>> [Apex-Model-Response] <think>
!

!<|im_end|>!<|im_end|>!
!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   LRFU Cache / Staging Ring    : 7763.31 MB (3741/25088 exp = 14.91% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.63 MB | End=13580.52 MB | Peak=14106.34 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (64 tok) : "<think>
!

!<|im_end|>!<|im_end|>!
!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=75.1% | AvgMargin=nan | MinMargin=0.002
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |  248068 | <think>        |   33.20 | 100.0% |  248045 |   12.51 | 41528.27 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |   21.37 |  52.8% |     271 |   21.25 |  327.39 |393 | 87 |  0 | 121294.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  327.39 |  0 |  0 |  0 | 121294.5 |
   |    4 |     271 | \n\n           |   12.49 |  23.2% |     198 |   12.29 |  326.47 |384 | 96 |  0 | 154532.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  326.47 |  0 |  0 |  0 | 154532.0 |
   |    6 |  248046 | <|im_end|>     |   12.66 |  20.5% |     198 |   12.53 |  311.37 |406 | 74 |  0 | 131859.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  311.37 |  0 |  0 |  0 | 131859.0 |
   |    8 |  248046 | <|im_end|>     |   12.42 |  16.9% |     198 |   12.17 |  316.84 |440 | 40 |  0 | 107994.5 |
   |   18 |       0 | !              |   13.98 |  52.8% |     198 |   11.63 |  603.41 |297 |143 | 40 | 280219.5 |
   |   19 |       0 | !              |     nan | 100.0% |       1 |     nan |  603.41 |  0 |  0 |  0 | 280219.5 |
   |   20 |       0 | !              |   11.85 |  14.0% |     198 |   11.17 |  468.17 |389 | 76 | 15 | 190607.0 |
   |   21 |       0 | !              |     nan | 100.0% |       1 |     nan |  468.17 |  0 |  0 |  0 | 190607.0 |
   |   62 |       0 | !              |   15.42 |  86.1% |     198 |   11.32 |  308.88 |422 | 58 |  0 | 165732.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  308.88 |  0 |  0 |  0 | 165732.0 |
   |   64 |       0 | !              |   13.95 |  58.2% |     198 |   11.37 |  328.43 |390 | 90 |  0 | 190482.0 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  328.43 |  0 |  0 |  0 | 190482.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 41.528s, TTFT=41528.27ms): Avg=2.19 | Min=2.19 | Max=2.19 tps
   Prefill Chunks (1): C1:91t/2.2tps/79%
   Decode  (64 tok, 21.589s): Avg=2.96 | Min=1.66 | Max=3.47 tps
   Latency (ms) : Min=288.48 | P10=304.67 | P25=310.27 | P50=319.59 | P75=341.82 | P90=391.54 | P95=468.17 | P99=603.41 | Max=603.41
   Mean/SD/Jitt : Mean=337.32ms | StdDev=58.79ms | Jitter=20.77ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (59040): RawRAM=47712 (80.81%) | Lookahead=2154 (+3.65%) | ColdMiss=9174 (15.54%) | EFF HIT=84.46%
   Lookahead    : 5207 prefetched -> 2474 consumed (47.5% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 80.8% | @64= 84.5% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1230 |  888 |  28 | 314 | 74.5%| 576.12 | | L24 | 1230 |  998 |  61 | 171 | 86.1%| 548.93 |
   | L01 | 1230 |  966 |  10 | 254 | 79.3%| 636.25 | | L25 | 1230 |  956 |  81 | 193 | 84.3%| 582.76 |
   | L02 | 1230 |  973 |  15 | 242 | 80.3%| 651.93 | | L26 | 1230 |  942 |  92 | 196 | 84.1%| 639.16 |
   | L03 | 1230 | 1068 |  14 | 148 | 88.0%| 580.88 | | L27 | 1230 |  975 |  85 | 170 | 86.2%| 556.45 |
   | L04 | 1230 | 1010 |  18 | 202 | 83.6%| 755.37 | | L28 | 1230 |  924 |  89 | 217 | 82.4%| 667.36 |
   | L05 | 1230 |  994 |  15 | 221 | 82.0%| 462.45 | | L29 | 1230 |  941 | 109 | 180 | 85.4%| 478.22 |
   | L06 | 1230 |  962 |  15 | 253 | 79.4%| 528.25 | | L30 | 1230 |  927 |  95 | 208 | 83.1%| 502.71 |
   | L07 | 1230 |  978 |  18 | 234 | 81.0%| 427.88 | | L31 | 1230 | 1030 |  62 | 138 | 88.8%| 422.05 |
   | L08 | 1230 | 1058 |  10 | 162 | 86.8%| 224.12 | | L32 | 1230 | 1004 |  76 | 150 | 87.8%| 511.33 |
   | L09 | 1230 | 1040 |  16 | 174 | 85.9%| 242.80 | | L33 | 1230 |  937 | 110 | 183 | 85.1%| 472.46 |
   | L10 | 1230 | 1029 |  16 | 185 | 85.0%| 262.72 | | L34 | 1230 |  978 |  64 | 188 | 84.7%| 507.03 |
   | L11 | 1230 | 1050 |  19 | 161 | 86.9%| 252.76 | | L35 | 1230 | 1007 |  65 | 158 | 87.2%| 373.07 |
   | L12 | 1230 |  992 |  25 | 213 | 82.7%| 505.69 | | L36 | 1230 |  994 |  55 | 181 | 85.3%| 445.09 |
   | L13 | 1230 | 1038 |  28 | 164 | 86.7%| 309.69 | | L37 | 1230 | 1030 |  30 | 170 | 86.2%| 464.33 |
   | L14 | 1230 |  974 |  60 | 196 | 84.1%| 476.78 | | L38 | 1230 |  942 |  39 | 249 | 79.8%| 646.68 |
   | L15 | 1230 | 1070 |  30 | 130 | 89.4%| 424.85 | | L39 | 1230 | 1046 |  36 | 148 | 88.0%| 483.13 |
   | L16 | 1230 | 1008 |  72 | 150 | 87.8%| 475.61 | | L40 | 1230 | 1012 |  43 | 175 | 85.8%| 456.81 |
   | L17 | 1230 |  965 |  82 | 183 | 85.1%| 586.52 | | L41 | 1230 | 1011 |  36 | 183 | 85.1%| 354.35 |
   | L18 | 1230 |  981 |  49 | 200 | 83.7%| 652.32 | | L42 | 1230 |  984 |  23 | 223 | 81.9%| 436.45 |
   | L19 | 1230 |  990 |  75 | 165 | 86.6%| 453.74 | | L43 | 1230 | 1025 |  36 | 169 | 86.3%| 319.78 |
   | L20 | 1230 |  983 |  55 | 192 | 84.4%| 423.49 | | L44 | 1230 | 1019 |  20 | 191 | 84.5%| 373.07 |
   | L21 | 1230 |  983 |  58 | 189 | 84.6%| 659.84 | | L45 | 1230 | 1030 |  12 | 188 | 84.7%| 329.86 |
   | L22 | 1230 |  942 |  26 | 262 | 78.7%| 759.47 | | L46 | 1230 | 1008 |  25 | 197 | 84.0%| 413.40 |
   | L23 | 1230 | 1033 |  39 | 158 | 87.2%| 374.51 | | L47 | 1230 | 1017 |  17 | 196 | 84.1%| 520.73 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 29425.52 MB (Load=4614.69 | Prefill=14994.17 | Warmup=0.00 | Decode=9816.65 MB)
   SSD Data/Token (Decode)      : Avg=153.385 MB/tok (Min=85.224 | P50=149.445 | P95=222.895 | Max=273.652 MB) | Prefill=164.771 MB/tok
   NVMe Batches / Requests      : 2027 Batches | 46219 Reads | 106 LBA Merges (Avg 651.9 KB/req)
   SSD Read Bandwidth           : Avg=921.69 MB/s | Peak=6922.22 MB/s (100.0% of 482.7 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=30423.11 MB | Write=128.00 MB | Syscalls=63165
   Sync Stall vs Async DMA      : SyncStall=13149.31 ms | AsyncOverlapped=21373.11 ms (61.9% Overlapped)
   RAM Traffic & Effective BW   : 622.87 GB moved | Eff=9.87 GB/s (STREAM Triad Max=37.63 GB/s)
   CPU Time & Utilization       : User=139.547s + Sys=13.391s (Wall=79.441s) | SysUtil=48.1% | ThrUtil=48.1% | 94.66 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  21345.59 ms (137713.5 us/tok | 33.82%)
   MoE AVX2 Q8 Expert Compute   :  21674.34 ms (139834.5 us/tok | 34.34%)
   Router + Lookahead Dispatch  :   1206.66 ms ( 7784.9 us/tok |  1.91%)
   LM Head Output Projection    :   2344.26 ms (15124.3 us/tok |  3.71%)
   Foreground NVMe Sync Stall   :  13149.31 ms (84834.3 us/tok | 20.83%)
   Unaccounted / OMP & Sampling :   3396.84 ms (21915.1 us/tok |  5.38%) | Total Wall=63117.01 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    66.03%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.57%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    11.54%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    11.62%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.24%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_qwen38_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7070.19 MB (3407 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=2.24 tps | Avg=2.24 tps | Hit=79.7% | NVMe=798.7 MB/s (14854.95 MB, QD=64) | RSS=12978.7 MB
[LIVE-DECODE] 4/32 tok | Avg=1.36 tps | Hit=80.1% (LA:+1.2%) | NVMe=768.4 MB/s (16066.25 MB) | RSS=12983.0 MB
[LIVE-DECODE] 8/32 tok | Avg=1.56 tps | Hit=80.5% (LA:+2.0%) | NVMe=757.2 MB/s (17025.00 MB) | RSS=12983.0 MB
[LIVE-DECODE] 16/32 tok | Avg=1.94 tps | Hit=81.5% (LA:+3.1%) | NVMe=772.4 MB/s (18649.96 MB) | RSS=12975.2 MB
[LIVE-DECODE] 24/32 tok | Avg=2.22 tps | Hit=82.5% (LA:+3.7%) | NVMe=793.9 MB/s (19905.77 MB) | RSS=12944.2 MB
[LIVE-DECODE] 32/32 tok | Avg=2.41 tps | Hit=83.4% (LA:+4.1%) | NVMe=813.4 MB/s (21099.87 MB) | RSS=12914.7 MB

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
   LRFU Cache / Staging Ring    : 7070.19 MB (3407/25088 exp = 13.58% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.89 MB | End=12914.71 MB | Peak=13406.62 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (32 tok) : " 2!m!$!m! !! !! !! !! !! !!
! !!!!!!!! !!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 33 Steps)]
   Logit Summary: AvgTop1Prob=55.4% | AvgMargin=nan | MinMargin=0.001
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     220 |                |   15.42 |   8.1% |    2446 |   14.36 | 28598.56 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |   18.29 |  24.9% |      16 |   18.25 |  678.92 |243 |199 | 38 | 302169.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  678.92 |  0 |  0 |  0 | 302169.5 |
   |    4 |      76 | m              |   12.78 |   8.7% |   35716 |   12.51 |  791.15 |239 |190 | 51 | 318019.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  791.15 |  0 |  0 |  0 | 318019.5 |
   |    6 |       3 | $              |   12.89 |  12.8% |      12 |   12.22 |  686.66 |260 |185 | 35 | 302071.5 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  686.66 |  0 |  0 |  0 | 302071.5 |
   |    8 |      76 | m              |   11.94 |   4.3% |   35716 |   11.90 |  412.84 |383 | 86 | 11 | 188807.0 |
   |   10 |     729 |  !             |   11.55 |   7.7% |    1088 |   10.88 |  436.08 |347 |120 | 13 | 221757.0 |
   |   11 |       0 | !              |     nan | 100.0% |       1 |     nan |  436.08 |  0 |  0 |  0 | 221757.0 |
   |   14 |     729 |  !             |   12.06 |  12.6% |       0 |   10.58 |  416.41 |370 | 99 | 11 | 212607.0 |
   |   15 |       0 | !              |     nan | 100.0% |       1 |     nan |  416.41 |  0 |  0 |  0 | 212607.0 |
   |   30 |       0 | !              |   11.46 |   8.9% |     198 |   11.26 |  305.23 |424 | 56 |  0 | 152157.0 |
   |   31 |       0 | !              |     nan | 100.0% |       1 |     nan |  305.23 |  0 |  0 |  0 | 152157.0 |
   |   32 |     729 |  !             |   12.42 |  19.4% |   13682 |   11.09 |  305.89 |444 | 36 |  0 | 124694.5 |
   |   33 |       0 | !              |     nan | 100.0% |       1 |     nan |  305.89 |  0 |  0 |  0 | 124694.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 28.599s, TTFT=28598.56ms): Avg=2.24 | Min=2.24 | Max=2.24 tps
   Prefill Chunks (1): C1:64t/2.2tps/80%
   Decode  (32 tok, 13.297s): Avg=2.41 | Min=1.26 | Max=3.28 tps
   Latency (ms) : Min=305.23 | P10=305.89 | P25=312.13 | P50=349.06 | P75=436.08 | P90=686.66 | P95=791.15 | P99=791.15 | Max=791.15
   Mean/SD/Jitt : Mean=415.53ms | StdDev=152.88ms | Jitter=27.37ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/32
   MTP Head     : 16/16 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (38400): RawRAM=30441 (79.27%) | Lookahead=1568 (+4.08%) | ColdMiss=6391 (16.64%) | EFF HIT=83.36%
   Lookahead    : 3327 prefetched -> 1728 consumed (51.9% util) | Warmup >=75%:1t, >=85%:-1t
   Trajectory   : @16= 81.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  800 |  537 |  26 | 237 | 70.4%| 443.04 | | L24 |  800 |  635 |  37 | 128 | 84.0%| 385.38 |
   | L01 |  800 |  605 |  23 | 172 | 78.5%| 398.44 | | L25 |  800 |  647 |  37 | 116 | 85.5%| 327.10 |
   | L02 |  800 |  599 |  23 | 178 | 77.8%| 534.01 | | L26 |  800 |  624 |  41 | 135 | 83.1%| 366.58 |
   | L03 |  800 |  697 |  11 |  92 | 88.5%| 325.22 | | L27 |  800 |  650 |  23 | 127 | 84.1%| 304.54 |
   | L04 |  800 |  655 |  20 | 125 | 84.4%| 421.26 | | L28 |  800 |  613 |  33 | 154 | 80.8%| 400.42 |
   | L05 |  800 |  621 |  17 | 162 | 79.8%| 409.81 | | L29 |  800 |  626 |  39 | 135 | 83.1%| 303.93 |
   | L06 |  800 |  609 |  27 | 164 | 79.5%| 422.97 | | L30 |  800 |  642 |  32 | 126 | 84.2%| 282.32 |
   | L07 |  800 |  598 |  35 | 167 | 79.1%| 390.82 | | L31 |  800 |  668 |  29 | 103 | 87.1%| 257.84 |
   | L08 |  800 |  646 |  30 | 124 | 84.5%| 215.41 | | L32 |  800 |  680 |  35 |  85 | 89.4%| 250.02 |
   | L09 |  800 |  658 |  29 | 113 | 85.9%| 191.75 | | L33 |  800 |  608 |  48 | 144 | 82.0%| 305.37 |
   | L10 |  800 |  636 |  31 | 133 | 83.4%| 226.61 | | L34 |  800 |  614 |  44 | 142 | 82.2%| 309.69 |
   | L11 |  800 |  640 |  38 | 122 | 84.8%| 237.82 | | L35 |  800 |  661 |  30 | 109 | 86.4%| 234.79 |
   | L12 |  800 |  602 |  36 | 162 | 79.8%| 402.29 | | L36 |  800 |  620 |  46 | 134 | 83.2%| 299.61 |
   | L13 |  800 |  598 |  57 | 145 | 81.9%| 326.98 | | L37 |  800 |  629 |  33 | 138 | 82.8%| 368.46 |
   | L14 |  800 |  617 |  58 | 125 | 84.4%| 309.69 | | L38 |  800 |  595 |  34 | 171 | 78.6%| 445.53 |
   | L15 |  800 |  667 |  26 | 107 | 86.6%| 336.50 | | L39 |  800 |  696 |  17 |  87 | 89.1%| 289.50 |
   | L16 |  800 |  672 |  25 | 103 | 87.1%| 266.94 | | L40 |  800 |  683 |  23 |  94 | 88.2%| 274.46 |
   | L17 |  800 |  645 |  36 | 119 | 85.1%| 325.22 | | L41 |  800 |  653 |  26 | 121 | 84.9%| 224.71 |
   | L18 |  800 |  600 |  50 | 150 | 81.2%| 428.61 | | L42 |  800 |  626 |  25 | 149 | 81.4%| 305.37 |
   | L19 |  800 |  653 |  42 | 105 | 86.9%| 254.96 | | L43 |  800 |  678 |  30 |  92 | 88.5%| 210.30 |
   | L20 |  800 |  615 |  40 | 145 | 81.9%| 301.05 | | L44 |  800 |  641 |  29 | 130 | 83.8%| 279.44 |
   | L21 |  800 |  603 |  55 | 142 | 82.2%| 445.53 | | L45 |  800 |  649 |  26 | 125 | 84.4%| 272.24 |
   | L22 |  800 |  575 |  45 | 180 | 77.5%| 490.65 | | L46 |  800 |  638 |  28 | 134 | 83.2%| 273.68 |
   | L23 |  800 |  676 |  24 | 100 | 87.5%| 224.71 | | L47 |  800 |  641 |  19 | 140 | 82.5%| 381.62 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 21099.87 MB (Load=4614.69 | Prefill=10240.25 | Warmup=0.00 | Decode=6244.92 MB)
   SSD Data/Token (Decode)      : Avg=195.154 MB/tok (Min=121.772 | P50=191.132 | P95=310.566 | Max=310.566 MB) | Prefill=160.004 MB/tok
   NVMe Batches / Requests      : 1299 Batches | 31542 Reads | 1 LBA Merges (Avg 685.0 KB/req)
   SSD Read Bandwidth           : Avg=813.36 MB/s | Peak=6613.94 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=21119.85 MB | Write=0.00 MB | Syscalls=41044
   Sync Stall vs Async DMA      : SyncStall=8071.18 ms | AsyncOverlapped=15405.33 ms (65.6% Overlapped)
   RAM Traffic & Effective BW   : 360.23 GB moved | Eff=8.60 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=89.094s + Sys=8.172s (Wall=56.943s) | SysUtil=42.7% | ThrUtil=42.7% | 39.50 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  13688.60 ms (142589.6 us/tok | 32.67%)
   MoE AVX2 Q8 Expert Compute   :  14157.15 ms (147470.3 us/tok | 33.79%)
   Router + Lookahead Dispatch  :    829.51 ms ( 8640.8 us/tok |  1.98%)
   LM Head Output Projection    :   1175.60 ms (12245.9 us/tok |  2.81%)
   Foreground NVMe Sync Stall   :   8071.18 ms (84074.8 us/tok | 19.26%)
   Unaccounted / OMP & Sampling :   3973.54 ms (41391.1 us/tok |  9.48%) | Total Wall=41895.59 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    66.09%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.46%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |    12.05%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    10.29%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.11%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_qwen38_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7781.98 MB (3750 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=2.97 tps | Avg=2.97 tps | Hit=90.7% | NVMe=1101.0 MB/s (23422.36 MB, QD=64) | RSS=13731.3 MB
[LIVE-PREFILL] 512/512 tok | Chunk=2.94 tps | Avg=2.95 tps | Hit=91.0% | NVMe=1251.0 MB/s (41012.20 MB, QD=64) | RSS=13741.3 MB
[LIVE-DECODE] 4/128 tok | Avg=1.17 tps | Hit=91.0% (LA:+0.2%) | NVMe=1186.7 MB/s (42251.10 MB) | RSS=13682.3 MB
[LIVE-DECODE] 8/128 tok | Avg=1.46 tps | Hit=91.0% (LA:+0.3%) | NVMe=1171.5 MB/s (43340.23 MB) | RSS=13640.5 MB
[LIVE-DECODE] 16/128 tok | Avg=1.94 tps | Hit=91.0% (LA:+0.6%) | NVMe=1188.8 MB/s (45414.07 MB) | RSS=13599.3 MB
[LIVE-DECODE] 24/128 tok | Avg=2.20 tps | Hit=91.1% (LA:+0.8%) | NVMe=1203.4 MB/s (47279.63 MB) | RSS=13599.2 MB
[LIVE-DECODE] 32/128 tok | Avg=2.38 tps | Hit=91.2% (LA:+1.0%) | NVMe=1215.4 MB/s (48876.90 MB) | RSS=13599.2 MB
[LIVE-DECODE] 40/128 tok | Avg=2.50 tps | Hit=91.2% (LA:+1.1%) | NVMe=1225.8 MB/s (50468.99 MB) | RSS=13599.2 MB
[LIVE-DECODE] 48/128 tok | Avg=2.52 tps | Hit=91.3% (LA:+1.3%) | NVMe=1227.1 MB/s (52345.73 MB) | RSS=13599.2 MB
[LIVE-DECODE] 56/128 tok | Avg=2.56 tps | Hit=91.4% (LA:+1.4%) | NVMe=1227.2 MB/s (53819.35 MB) | RSS=13599.2 MB
[LIVE-DECODE] 64/128 tok | Avg=2.57 tps | Hit=91.4% (LA:+1.6%) | NVMe=1224.1 MB/s (55552.75 MB) | RSS=13599.2 MB
[LIVE-DECODE] 72/128 tok | Avg=2.63 tps | Hit=91.5% (LA:+1.7%) | NVMe=1228.7 MB/s (56936.50 MB) | RSS=13599.2 MB
[LIVE-DECODE] 80/128 tok | Avg=2.67 tps | Hit=91.5% (LA:+1.8%) | NVMe=1234.2 MB/s (58271.83 MB) | RSS=13599.2 MB
[LIVE-DECODE] 88/128 tok | Avg=2.66 tps | Hit=91.6% (LA:+1.9%) | NVMe=1227.5 MB/s (59861.34 MB) | RSS=13599.2 MB
[LIVE-DECODE] 96/128 tok | Avg=2.70 tps | Hit=91.6% (LA:+2.0%) | NVMe=1232.8 MB/s (61166.96 MB) | RSS=13599.2 MB
[LIVE-DECODE] 104/128 tok | Avg=2.72 tps | Hit=91.7% (LA:+2.1%) | NVMe=1234.5 MB/s (62674.75 MB) | RSS=13599.2 MB
[LIVE-DECODE] 112/128 tok | Avg=2.74 tps | Hit=91.8% (LA:+2.2%) | NVMe=1238.8 MB/s (64147.29 MB) | RSS=13599.2 MB
[LIVE-DECODE] 120/128 tok | Avg=2.77 tps | Hit=91.8% (LA:+2.3%) | NVMe=1241.9 MB/s (65361.39 MB) | RSS=13599.2 MB
[LIVE-DECODE] 128/128 tok | Avg=2.77 tps | Hit=91.9% (LA:+2.4%) | NVMe=1242.1 MB/s (66924.50 MB) | RSS=13599.2 MB

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
   LRFU Cache / Staging Ring    : 7781.98 MB (3750/25088 exp = 14.95% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.68 MB | End=13599.16 MB | Peak=14160.26 MB
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

!!!

!

!

!

!

!!!

!

!!!

!

!!!

!!!

!!!!!

!

!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 129 Steps)]
   Logit Summary: AvgTop1Prob=82.9% | AvgMargin=nan | MinMargin=0.128
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    6000 |  layer         |   23.58 | 100.0% |     271 |   13.50 | 173290.27 |  0 |  0 |  0 |     0.0 |
   |    2 |   42962 | -wise          |   22.36 |  99.9% |    2543 |   13.89 |  603.28 |355 |113 | 12 | 221819.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  603.28 |  0 |  0 |  0 | 221819.5 |
   |    4 |     271 | \n\n           |   14.91 |  63.8% |    1249 |   12.72 | 1102.55 |121 |275 | 84 | 412496.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan | 1102.55 |  0 |  0 |  0 | 412496.5 |
   |    6 |     271 | \n\n           |   14.84 |  56.8% |      12 |   12.77 |  570.89 |269 |190 | 21 | 290382.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  570.89 |  0 |  0 |  0 | 290382.0 |
   |    8 |     271 | \n\n           |   15.00 |  60.6% |      12 |   12.20 |  453.94 |299 |168 | 13 | 267257.0 |
   |   84 |     271 | \n\n           |   14.72 |  72.4% |       0 |   12.28 |  506.06 |341 |108 | 31 | 252807.0 |
   |   85 |       0 | !              |     nan | 100.0% |       1 |     nan |  506.06 |  0 |  0 |  0 | 252807.0 |
   |   62 |     271 | \n\n           |   14.77 |  64.8% |       0 |   13.11 |  481.14 |322 |136 | 22 | 278544.5 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  481.14 |  0 |  0 |  0 | 278544.5 |
   |  126 |     271 | \n\n           |   15.34 |  72.4% |       0 |   13.40 |  328.67 |405 | 75 |  0 | 183619.5 |
   |  127 |       0 | !              |     nan | 100.0% |       1 |     nan |  328.67 |  0 |  0 |  0 | 183619.5 |
   |  128 |     271 | \n\n           |   15.03 |  61.6% |       0 |   13.75 |  304.06 |436 | 44 |  0 | 140269.5 |
   |  129 |       0 | !              |     nan | 100.0% |       1 |     nan |  304.06 |  0 |  0 |  0 | 140269.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 173.290s, TTFT=173290.27ms): Avg=2.95 | Min=2.94 | Max=2.97 tps
   Prefill Chunks (2): C1:256t/3.0tps/91% | C2:256t/2.9tps/91%
   Decode  (128 tok, 46.191s): Avg=2.77 | Min=0.91 | Max=3.37 tps
   Latency (ms) : Min=296.85 | P10=302.63 | P25=308.48 | P50=324.25 | P75=362.07 | P90=453.94 | P95=506.06 | P99=1102.55 | Max=1102.55
   Mean/SD/Jitt : Mean=360.87ms | StdDev=113.77ms | Jitter=29.20ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/128
   MTP Head     : 64/64 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (276480): RawRAM=247465 (89.51%) | Lookahead=6542 (+2.37%) | ColdMiss=22473 (8.13%) | EFF HIT=91.87%
   Lookahead    : 14252 prefetched -> 7182 consumed (50.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 91.0% | @64= 91.4% | @128= 91.9% | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 5760 | 5055 |  64 | 641 | 88.9%|1187.62 | | L24 | 5760 | 5141 | 207 | 412 | 92.8%|1706.93 |
   | L01 | 5760 | 5152 |  65 | 543 | 90.6%|1284.96 | | L25 | 5760 | 5161 | 172 | 427 | 92.6%|1300.88 |
   | L02 | 5760 | 5172 |  52 | 536 | 90.7%|1750.27 | | L26 | 5760 | 5050 | 236 | 474 | 91.8%|1635.50 |
   | L03 | 5760 | 5341 |  45 | 374 | 93.5%|1323.44 | | L27 | 5760 | 5116 | 207 | 437 | 92.4%|1404.27 |
   | L04 | 5760 | 5289 |  24 | 447 | 92.2%|1411.13 | | L28 | 5760 | 5086 | 200 | 474 | 91.8%|1483.23 |
   | L05 | 5760 | 5205 |  50 | 505 | 91.2%|1257.64 | | L29 | 5760 | 5014 | 247 | 499 | 91.3%|1274.78 |
   | L06 | 5760 | 5135 |  46 | 579 | 89.9%|1287.72 | | L30 | 5760 | 5017 | 263 | 480 | 91.7%|1287.74 |
   | L07 | 5760 | 5130 |  89 | 541 | 90.6%|1226.37 | | L31 | 5760 | 5186 | 202 | 372 | 93.5%|1215.72 |
   | L08 | 5760 | 5215 |  86 | 459 | 92.0%| 823.02 | | L32 | 5760 | 5186 | 194 | 380 | 93.4%|1312.16 |
   | L09 | 5760 | 5230 |  83 | 447 | 92.2%| 753.30 | | L33 | 5760 | 5003 | 248 | 509 | 91.2%|1245.97 |
   | L10 | 5760 | 5182 |  96 | 482 | 91.6%| 814.31 | | L34 | 5760 | 5064 | 208 | 488 | 91.5%|1310.79 |
   | L11 | 5760 | 5170 | 118 | 472 | 91.8%| 825.51 | | L35 | 5760 | 5171 | 131 | 458 | 92.0%| 985.25 |
   | L12 | 5760 | 5147 | 124 | 489 | 91.5%|1323.44 | | L36 | 5760 | 5180 | 112 | 468 | 91.9%| 969.41 |
   | L13 | 5760 | 5038 | 208 | 514 | 91.1%|1186.91 | | L37 | 5760 | 5182 | 104 | 474 | 91.8%|1353.52 |
   | L14 | 5760 | 5098 | 195 | 467 | 91.9%|1112.01 | | L38 | 5760 | 5094 | 125 | 541 | 90.6%|1498.27 |
   | L15 | 5760 | 5336 | 115 | 309 | 94.6%|1047.09 | | L39 | 5760 | 5248 | 108 | 404 | 93.0%|1270.80 |
   | L16 | 5760 | 5229 | 224 | 307 | 94.7%|1235.08 | | L40 | 5760 | 5254 |  99 | 407 | 92.9%|1065.89 |
   | L17 | 5760 | 5031 | 284 | 445 | 92.3%|1596.02 | | L41 | 5760 | 5165 | 101 | 494 | 91.4%| 975.17 |
   | L18 | 5760 | 5115 | 162 | 483 | 91.6%|1663.70 | | L42 | 5760 | 5150 | 109 | 501 | 91.3%|1156.67 |
   | L19 | 5760 | 5100 | 218 | 442 | 92.3%|1117.77 | | L43 | 5760 | 5271 |  78 | 411 | 92.9%| 890.19 |
   | L20 | 5760 | 5071 | 222 | 467 | 91.9%|1212.84 | | L44 | 5760 | 5192 |  77 | 491 | 91.5%|1088.96 |
   | L21 | 5760 | 5084 | 140 | 536 | 90.7%|1502.03 | | L45 | 5760 | 5223 |  67 | 470 | 91.8%| 999.66 |
   | L22 | 5760 | 5067 | 142 | 551 | 90.4%|1659.94 | | L46 | 5760 | 5281 |  50 | 429 | 92.6%|1006.86 |
   | L23 | 5760 | 5234 | 112 | 414 | 92.8%| 975.17 | | L47 | 5760 | 5204 |  33 | 523 | 90.9%|1069.65 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 66924.50 MB (Load=4614.69 | Prefill=36397.50 | Warmup=0.00 | Decode=25912.30 MB)
   SSD Data/Token (Decode)      : Avg=202.440 MB/tok (Min=126.386 | P50=199.299 | P95=270.686 | Max=402.829 MB) | Prefill=71.089 MB/tok
   NVMe Batches / Requests      : 5118 Batches | 120499 Reads | 59 LBA Merges (Avg 568.7 KB/req)
   SSD Read Bandwidth           : Avg=1242.11 MB/s | Peak=9726.91 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=66944.64 MB | Write=0.00 MB | Syscalls=129956
   Sync Stall vs Async DMA      : SyncStall=21994.75 ms | AsyncOverlapped=43305.01 ms (66.3% Overlapped)
   RAM Traffic & Effective BW   : 2072.99 GB moved | Eff=9.44 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=621.641s + Sys=26.438s (Wall=235.269s) | SysUtil=68.9% | ThrUtil=68.9% | 63.70 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  86697.89 ms (135465.4 us/tok | 39.50%)
   MoE AVX2 Q8 Expert Compute   :  90962.18 ms (142128.4 us/tok | 41.44%)
   Router + Lookahead Dispatch  :   5152.07 ms ( 8050.1 us/tok |  2.35%)
   LM Head Output Projection    :   4612.87 ms ( 7207.6 us/tok |  2.10%)
   Foreground NVMe Sync Stall   :  21994.75 ms (34366.8 us/tok | 10.02%)
   Unaccounted / OMP & Sampling :  10061.77 ms (15721.5 us/tok |  4.58%) | Total Wall=219481.53 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    71.48%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.95%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     5.47%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    13.13%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.97%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_qwen38_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 29119.3ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\n\n<think>\nThe user is asking me to summarize "LBA-coalesced'
[Stage 3] /v1/chat/completions (stream=true SSE) 9209.1ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_qwen38_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=5926.76 MB (2856 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3.01 tps | Avg=3.01 tps | Hit=90.7% | NVMe=1114.0 MB/s (23422.36 MB, QD=64) | RSS=11882.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.96 tps | Avg=2.99 tps | Hit=90.7% | NVMe=1305.3 MB/s (42266.54 MB, QD=64) | RSS=11905.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.95 tps | Avg=2.97 tps | Hit=90.6% | NVMe=1412.1 MB/s (61607.01 MB, QD=64) | RSS=11906.3 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.93 tps | Avg=2.96 tps | Hit=90.6% | NVMe=1490.3 MB/s (80739.91 MB, QD=64) | RSS=11906.7 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.92 tps | Avg=2.95 tps | Hit=90.6% | NVMe=1519.5 MB/s (98961.03 MB, QD=64) | RSS=11906.1 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.96 tps | Avg=2.95 tps | Hit=90.8% | NVMe=1556.7 MB/s (116266.34 MB, QD=64) | RSS=11906.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.94 tps | Avg=2.95 tps | Hit=90.8% | NVMe=1589.0 MB/s (134272.41 MB, QD=64) | RSS=11906.6 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.88 tps | Avg=2.94 tps | Hit=90.9% | NVMe=1598.5 MB/s (152057.01 MB, QD=64) | RSS=11907.1 MB
[LIVE-DECODE] 4/64 tok | Avg=1.14 tps | Hit=90.9% (LA:+0.0%) | NVMe=1565.4 MB/s (153548.54 MB) | RSS=11908.3 MB
[LIVE-DECODE] 8/64 tok | Avg=1.50 tps | Hit=90.9% (LA:+0.1%) | NVMe=1562.1 MB/s (154780.48 MB) | RSS=11907.3 MB
[LIVE-DECODE] 16/64 tok | Avg=1.98 tps | Hit=90.9% (LA:+0.2%) | NVMe=1571.2 MB/s (157215.64 MB) | RSS=11906.1 MB
[LIVE-DECODE] 24/64 tok | Avg=2.22 tps | Hit=90.9% (LA:+0.3%) | NVMe=1581.2 MB/s (159646.75 MB) | RSS=11892.3 MB
[LIVE-DECODE] 32/64 tok | Avg=2.37 tps | Hit=90.9% (LA:+0.4%) | NVMe=1590.7 MB/s (162087.99 MB) | RSS=11892.3 MB
[LIVE-DECODE] 40/64 tok | Avg=2.48 tps | Hit=90.9% (LA:+0.4%) | NVMe=1599.7 MB/s (164372.79 MB) | RSS=11892.3 MB
[LIVE-DECODE] 48/64 tok | Avg=2.55 tps | Hit=91.0% (LA:+0.5%) | NVMe=1607.3 MB/s (166524.45 MB) | RSS=11892.3 MB
[LIVE-DECODE] 56/64 tok | Avg=2.62 tps | Hit=91.0% (LA:+0.6%) | NVMe=1613.4 MB/s (168389.13 MB) | RSS=11889.4 MB
[LIVE-DECODE] 64/64 tok | Avg=2.68 tps | Hit=91.0% (LA:+0.6%) | NVMe=1618.4 MB/s (170140.04 MB) | RSS=11883.2 MB

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
   LRFU Cache / Staging Ring    : 5926.76 MB (2856/25088 exp = 11.38% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.72 MB | End=11883.24 MB | Peak=12305.49 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (64 tok) : " layer-wise!

!

!

!

!

!!!

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

!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 65 Steps)]
   Logit Summary: AvgTop1Prob=82.5% | AvgMargin=nan | MinMargin=0.039
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |    6000 |  layer         |   21.48 |  99.8% |     271 |   15.00 | 695901.27 |  0 |  0 |  0 |     0.0 |
   |    2 |   42962 | -wise          |   19.25 |  98.0% |     271 |   14.61 |  564.06 |373 | 88 | 19 | 243544.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  564.06 |  0 |  0 |  0 | 243544.5 |
   |    4 |     271 | \n\n           |   16.03 |  83.1% |    1076 |   11.70 | 1195.71 | 27 |364 | 89 | 520121.5 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan | 1195.71 |  0 |  0 |  0 | 520121.5 |
   |    6 |     271 | \n\n           |   15.75 |  79.8% |  248046 |   11.70 |  559.98 |234 |226 | 20 | 333382.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  559.98 |  0 |  0 |  0 | 333382.0 |
   |    8 |     271 | \n\n           |   15.44 |  73.5% |       0 |   12.92 |  347.20 |287 |193 |  0 | 297369.5 |
   |   14 |       0 | !              |   15.60 |  58.4% |     271 |   14.90 |  362.36 |250 |230 |  0 | 324869.5 |
   |   15 |       0 | !              |     nan | 100.0% |       1 |     nan |  362.36 |  0 |  0 |  0 | 324869.5 |
   |   26 |       0 | !              |   16.45 |  77.6% |     271 |   14.92 |  355.64 |235 |245 |  0 | 341307.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  355.64 |  0 |  0 |  0 | 341307.0 |
   |   62 |     271 | \n\n           |   14.82 |  53.6% |       0 |   14.25 |  317.14 |359 |121 |  0 | 234894.5 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  317.14 |  0 |  0 |  0 | 234894.5 |
   |   64 |     271 | \n\n           |   14.52 |  56.7% |       0 |   13.52 |  313.32 |355 |125 |  0 | 220069.5 |
   |   65 |       0 | !              |     nan | 100.0% |       1 |     nan |  313.32 |  0 |  0 |  0 | 220069.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 695.901s, TTFT=695901.27ms): Avg=2.94 | Min=2.88 | Max=3.01 tps
   Prefill Chunks (8): C1:256t/3.0tps/91% | C2:256t/3.0tps/91% | C3:256t/2.9tps/91% | C4:256t/2.9tps/91%
                       C5:256t/2.9tps/91% | C6:256t/3.0tps/91% | C7:256t/2.9tps/91% | C8:256t/2.9tps/91%
   Decode  (64 tok, 23.894s): Avg=2.68 | Min=0.84 | Max=3.20 tps
   Latency (ms) : Min=312.87 | P10=315.76 | P25=324.87 | P50=335.36 | P75=341.70 | P90=362.36 | P95=564.06 | P99=1195.71 | Max=1195.71
   Mean/SD/Jitt : Mean=373.34ms | StdDev=158.26ms | Jitter=27.76ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/64
   MTP Head     : 32/32 draft tokens emitted (100.0% direct 2-tok head | Net 2.00x)
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (998400): RawRAM=902435 (90.39%) | Lookahead=6063 (+0.61%) | ColdMiss=89902 (9.00%) | EFF HIT=91.00%
   Lookahead    : 10211 prefetched -> 6383 consumed (62.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.9% | @64= 91.0% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |20800 |18000 | 221 |2579 | 87.6%|4716.80 | | L24 |20800 |18902 | 109 |1789 | 91.4%|3838.72 |
   | L01 |20800 |18386 | 153 |2261 | 89.1%|3242.29 | | L25 |20800 |18655 | 110 |2035 | 90.2%|4109.42 |
   | L02 |20800 |18267 | 147 |2386 | 88.5%|4647.73 | | L26 |20800 |18794 | 124 |1882 | 91.0%|3912.04 |
   | L03 |20800 |18782 | 143 |1875 | 91.0%|4116.94 | | L27 |20800 |18755 | 129 |1916 | 90.8%|3974.07 |
   | L04 |20800 |19071 |  87 |1642 | 92.1%|3722.90 | | L28 |20800 |18934 | 128 |1738 | 91.6%|3656.37 |
   | L05 |20800 |18581 | 170 |2049 | 90.1%|4346.29 | | L29 |20800 |18840 | 115 |1845 | 91.1%|2925.51 |
   | L06 |20800 |18473 |  86 |2241 | 89.2%|4500.44 | | L30 |20800 |18525 | 127 |2148 | 89.7%|3372.05 |
   | L07 |20800 |18476 | 178 |2146 | 89.7%|4014.33 | | L31 |20800 |18972 | 120 |1708 | 91.8%|2791.55 |
   | L08 |20800 |18871 | 166 |1763 | 91.5%|2495.21 | | L32 |20800 |18906 |  93 |1801 | 91.3%|3654.49 |
   | L09 |20800 |18938 | 152 |1710 | 91.8%|2366.97 | | L33 |20800 |18694 |  99 |2007 | 90.4%|3128.61 |
   | L10 |20800 |19015 | 114 |1671 | 92.0%|2282.30 | | L34 |20800 |18841 | 128 |1831 | 91.2%|2921.19 |
   | L11 |20800 |18956 | 176 |1668 | 92.0%|2354.52 | | L35 |20800 |18874 |  86 |1840 | 91.2%|2839.09 |
   | L12 |20800 |18976 | 179 |1645 | 92.1%|3532.30 | | L36 |20800 |18948 | 128 |1724 | 91.7%|2771.39 |
   | L13 |20800 |19115 | 138 |1547 | 92.6%|2493.38 | | L37 |20800 |18837 | 115 |1848 | 91.1%|3776.68 |
   | L14 |20800 |18865 | 153 |1782 | 91.4%|2901.03 | | L38 |20800 |18686 | 120 |1994 | 90.4%|4051.15 |
   | L15 |20800 |18994 | 141 |1665 | 92.0%|3566.14 | | L39 |20800 |19024 | 102 |1674 | 92.0%|3594.34 |
   | L16 |20800 |18840 | 196 |1764 | 91.5%|3861.28 | | L40 |20800 |18909 |  64 |1827 | 91.2%|3648.85 |
   | L17 |20800 |18823 | 167 |1810 | 91.3%|3838.72 | | L41 |20800 |18576 |  57 |2167 | 89.6%|3292.82 |
   | L18 |20800 |18857 | 168 |1775 | 91.5%|3801.12 | | L42 |20800 |18783 |  54 |1963 | 90.6%|3072.44 |
   | L19 |20800 |18808 | 151 |1841 | 91.1%|2986.01 | | L43 |20800 |18973 |  43 |1784 | 91.4%|2758.42 |
   | L20 |20800 |18599 | 180 |2021 | 90.3%|3304.35 | | L44 |20800 |18894 |  62 |1844 | 91.1%|2869.34 |
   | L21 |20800 |18979 | 158 |1663 | 92.0%|3569.90 | | L45 |20800 |18818 |  60 |1922 | 90.8%|2958.64 |
   | L22 |20800 |18948 | 181 |1671 | 92.0%|3673.29 | | L46 |20800 |19293 |  37 |1470 | 92.9%|2303.25 |
   | L23 |20800 |18759 | 144 |1897 | 90.9%|3096.92 | | L47 |20800 |18623 | 104 |2073 | 90.0%|4147.02 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 170140.04 MB (Load=4614.69 | Prefill=147442.31 | Warmup=0.00 | Decode=18083.03 MB)
   SSD Data/Token (Decode)      : Avg=282.547 MB/tok (Min=213.886 | P50=283.466 | P95=333.308 | Max=507.931 MB) | Prefill=71.993 MB/tok
   NVMe Batches / Requests      : 4578 Batches | 334727 Reads | 267 LBA Merges (Avg 520.5 KB/req)
   SSD Read Bandwidth           : Avg=1618.44 MB/s | Peak=10535.99 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=170160.58 MB | Write=0.00 MB | Syscalls=343974
   Sync Stall vs Async DMA      : SyncStall=84005.04 ms | AsyncOverlapped=94557.30 ms (53.0% Overlapped)
   RAM Traffic & Effective BW   : 5562.56 GB moved | Eff=7.73 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=2197.812s + Sys=58.469s (Wall=734.820s) | SysUtil=76.8% | ThrUtil=76.8% | 71.01 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 291560.68 ms (138049.6 us/tok | 40.51%)
   MoE AVX2 Q8 Expert Compute   : 316635.25 ms (149922.0 us/tok | 43.99%)
   Router + Lookahead Dispatch  :  17523.19 ms ( 8297.0 us/tok |  2.43%)
   LM Head Output Projection    :   2272.33 ms ( 1075.9 us/tok |  0.32%)
   Foreground NVMe Sync Stall   :  84005.04 ms (39775.1 us/tok | 11.67%)
   Unaccounted / OMP & Sampling :   7798.32 ms ( 3692.4 us/tok |  1.08%) | Total Wall=719794.81 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    70.90%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.01%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     4.82%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    15.59%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.68%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_qwen38_colibri_bench.log`
```text
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 64 32 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=290.0s) ===
[gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
[gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
reserved bits argument must be 2..8 (got 32)
=== [Colibri-Qwen38] Finished rc=1 elapsed=1.52s cancelled=False ===
```

### 📄 `11b_qwen38_ik_llama_bench.log`
```text
=== [ik_llama.cpp] CMD: baselines/ik_llama/build\bin\Release\llama-bench.exe -m D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf -p 64 -n 32 -t 4 -r 1 (5x cutoff=290.0s) ===
  [COMP-LIVE] ik_llama.cpp: elapsed=15.0s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=30.0s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=45.0s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=60.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=75.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=90.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=105.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=120.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=135.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=150.1s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=165.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=180.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=195.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=210.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=225.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=240.2s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=255.3s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=270.3s / cutoff=290.0s
  [COMP-LIVE] ik_llama.cpp: elapsed=285.3s / cutoff=290.0s

  [COMP-CANCEL] ik_llama.cpp exceeded 5x Apex wall time (290.3s > 290.0s); cancelling slow competitor.
=== [ik_llama.cpp] Finished rc=-9 elapsed=290.39s cancelled=True ===
```

### 📄 `12_qwen38_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison (64p / 32g / 4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 2.24 | 2.41 | N/A | 83.36% | 813.36 | 13406.62 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 2.95 | 2.77 | N/A | 91.87% | 1242.11 | 14160.26 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.94 | 2.68 | N/A | 91.00% | 1618.44 | 12305.49 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | N/A | - | N/A | - | - | `Q38_MTP=1` / Native |
| **llama.cpp (`-lm mmap`)** | Unsupported/Fail | Unsupported/Fail | - | OS Cache | - | - | `64p/32g -t 4` |
| **llama.cpp (`-lm none`)** | Unsupported/Fail | Unsupported/Fail | - | - | - | - | `64p/32g -t 4` |
| **ikawrakow/ik_llama.cpp** | Cancelled (>5x) | Cancelled (>5x) | - | - | - | - | `64p/32g -t 4` |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
