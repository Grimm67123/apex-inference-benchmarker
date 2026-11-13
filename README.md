<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#17 (Run ID `43423844244`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43423844244)
- **Status**: **FAILURE**
- **Timestamp**: `2026-11-13 12:18:47 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-13T12:17:04.379Z] ================================================================================
[2026-11-13T12:17:04.401Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-13T12:17:04.403Z] ================================================================================
[2026-11-13T12:17:09.574Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-13T12:17:09.810Z] --------------------------------------------------------------------------------
[2026-11-13T12:17:09.813Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 31 GB / 149.89 GB
[2026-11-13T12:17:09.815Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-13T12:17:09.816Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.01 GB
[2026-11-13T12:17:09.834Z] --------------------------------------------------------------------------------
[2026-11-13T12:17:09.836Z]  [OK] Disk space verification passed: 178.01 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 846K Nov 13 12:17 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 846K Nov 13 12:17 build/apex.exe
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
   SEQ1M Direct Uncached NVMe Read    :    462.95 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1468.96 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7310.65 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9622.00 MB/s
   RND4K Q32T16 Read                  :    508.21 MB/s (  130102 IOPS)
   RND4K Q1T1  Read                   :    641.48 MB/s (Latency: 6.09 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     43.27 GB/s
   AVX2 256-bit Sequential Write BW   :     37.82 GB/s
   STREAM Triad (A = B + s*C) BW      :     25.27 GB/s
   Random Pointer-Chase Latency       :    113.43 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.33 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    172.48 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.50 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1420.51 tps | Avg=1420.51 tps | Hit=99.5% | NVMe=1569.1 MB/s (6.19 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1242.30 tps | Avg=1325.44 tps | Hit=99.5% | NVMe=1526.2 MB/s (7.01 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1018.61 tps | Avg=1204.50 tps | Hit=99.5% | NVMe=1459.0 MB/s (7.78 MB, QD=64) | RSS=71.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=976.98 tps | Avg=1138.23 tps | Hit=99.5% | NVMe=1434.4 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=864.07 tps | Avg=1070.31 tps | Hit=99.5% | NVMe=1392.0 MB/s (9.33 MB, QD=64) | RSS=72.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=810.51 tps | Avg=1016.03 tps | Hit=99.5% | NVMe=1370.9 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=740.67 tps | Avg=964.79 tps | Hit=99.5% | NVMe=1353.2 MB/s (10.83 MB, QD=64) | RSS=72.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=686.38 tps | Avg=918.24 tps | Hit=99.5% | NVMe=1336.8 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=193.59 tps | Hit=99.5% (LA:+0.0%) | NVMe=1230.2 MB/s (12.43 MB) | RSS=73.2 MB
[LIVE-DECODE] 16/32 tok | Avg=194.76 tps | Hit=99.5% (LA:+0.1%) | NVMe=1210.2 MB/s (13.10 MB) | RSS=73.2 MB
[LIVE-DECODE] 24/32 tok | Avg=195.54 tps | Hit=99.5% (LA:+0.1%) | NVMe=1187.1 MB/s (13.25 MB) | RSS=73.2 MB
[LIVE-DECODE] 32/32 tok | Avg=196.10 tps | Hit=99.5% (LA:+0.1%) | NVMe=1179.7 MB/s (13.30 MB) | RSS=73.2 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=73.17 MB | Peak=73.17 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2230.37 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.26 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.26 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.19 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.19 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.08 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.08 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.14 | 11 |  1 |  0 |    49.5 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.17 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.17 |  0 |  0 |  0 |   173.2 |
   |    9 |      68 | tok_68         |  176.71 | 100.0% |     228 |  144.43 |    5.14 |  0 |  0 |  0 |    49.5 |
   |   20 |      86 | tok_86         |  167.81 |  99.1% |     246 |  163.11 |    5.13 | 12 |  0 |  0 |    24.8 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.06 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.06 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.02 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.02 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.230s, TTFT=2230.37ms): Avg=918.24 | Min=686.38 | Max=1420.51 tps
   Prefill Chunks (8): C1:256t/1420.5tps/99% | C2:256t/1242.3tps/99% | C3:256t/1018.6tps/99% | C4:256t/977.0tps/99%
                       C5:256t/864.1tps/99% | C6:256t/810.5tps/99% | C7:256t/740.7tps/99% | C8:256t/686.4tps/99%
   Decode  (32 tok, 0.163s): Avg=196.10 | Min=190.18 | Max=201.18 tps
   Latency (ms) : Min=4.97 | P10=5.02 | P25=5.06 | P50=5.09 | P75=5.14 | P90=5.19 | P95=5.26 | P99=5.26 | Max=5.26
   Mean/SD/Jitt : Mean=5.10ms | StdDev=0.07ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth           : Avg=1179.65 MB/s | Peak=5555.56 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=6.99 ms | AsyncOverlapped=9.80 ms (58.4% Overlapped)
   RAM Traffic & Effective BW   : 1.43 GB moved | Eff=0.60 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=3.266s + Sys=0.703s (Wall=2.414s) | SysUtil=41.1% | ThrUtil=41.1% | 38.01 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2010.23 ms (  966.5 us/tok | 83.99%)
   MoE AVX2 Q8 Expert Compute   :    248.83 ms (  119.6 us/tok | 10.40%)
   Router + Lookahead Dispatch  :     61.81 ms (   29.7 us/tok |  2.58%)
   LM Head Output Projection    :      5.87 ms (    2.8 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      6.99 ms (    3.4 us/tok |  0.29%)
   Unaccounted / OMP & Sampling :     59.81 ms (   28.8 us/tok |  2.50%) | Total Wall=2393.55 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    29.48%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.13%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.53%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    66.19%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.67%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1933.54 tps | Avg=1933.54 tps | Hit=99.2% | NVMe=2312.5 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1666.26 tps | Avg=1789.98 tps | Hit=99.2% | NVMe=3092.0 MB/s (42.92 MB, QD=64) | RSS=89.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1731.94 tps | Avg=1770.20 tps | Hit=99.2% | NVMe=3553.0 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1644.34 tps | Avg=1736.96 tps | Hit=99.2% | NVMe=3890.9 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1509.47 tps | Avg=1686.14 tps | Hit=99.2% | NVMe=4126.9 MB/s (97.14 MB, QD=64) | RSS=90.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1325.56 tps | Avg=1613.01 tps | Hit=99.2% | NVMe=4221.2 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1348.83 tps | Avg=1569.11 tps | Hit=99.2% | NVMe=4348.5 MB/s (133.27 MB, QD=64) | RSS=91.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1236.84 tps | Avg=1518.13 tps | Hit=99.2% | NVMe=4511.3 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=174.37 tps | Hit=99.2% (LA:+0.0%) | NVMe=4383.0 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=175.98 tps | Hit=99.2% (LA:+0.1%) | NVMe=4293.7 MB/s (153.44 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=177.00 tps | Hit=99.2% (LA:+0.1%) | NVMe=4171.2 MB/s (154.78 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=177.27 tps | Hit=99.2% (LA:+0.1%) | NVMe=4072.5 MB/s (155.58 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=91.82 MB | Peak=91.82 MB
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
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 | 1349.03 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    5.92 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   94.59 | 100.0% |     177 |   84.92 |    5.92 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    5.80 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   85.06 |  99.7% |     177 |   78.63 |    5.80 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    5.64 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   82.87 |  99.7% |     129 |   77.18 |    5.64 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    5.58 | 16 |  0 |  0 |    32.0 |
   |   14 |     223 | qtok_223       |   66.25 |  89.5% |     159 |   64.10 |    5.70 | 16 |  0 |  0 |    32.0 |
   |   15 |     113 | qtok_113       |  105.20 | 100.0% |      33 |   89.25 |    5.70 |  0 |  0 |  0 |    32.0 |
   |   10 |     254 | qtok_254       |   71.08 |  99.9% |      66 |   64.40 |    5.66 | 15 |  1 |  0 |    59.8 |
   |   11 |     129 | qtok_129       |   83.90 |  51.4% |      49 |   83.85 |    5.66 |  0 |  0 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   71.22 |  99.9% |      66 |   64.31 |    5.61 | 14 |  2 |  0 |    87.5 |
   |   31 |      49 | qtok_49        |  125.25 | 100.0% |     177 |   99.98 |    5.61 |  0 |  0 |  0 |    87.5 |
   |   32 |     254 | qtok_254       |   71.45 |  98.0% |      66 |   67.49 |    5.68 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  131.17 | 100.0% |     129 |  104.87 |    5.68 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.349s, TTFT=1349.03ms): Avg=1518.13 | Min=1236.84 | Max=1933.54 tps
   Prefill Chunks (8): C1:256t/1933.5tps/99% | C2:256t/1666.3tps/99% | C3:256t/1731.9tps/99% | C4:256t/1644.3tps/99%
                       C5:256t/1509.5tps/99% | C6:256t/1325.6tps/99% | C7:256t/1348.8tps/99% | C8:256t/1236.8tps/99%
   Decode  (32 tok, 0.181s): Avg=177.27 | Min=168.99 | Max=180.66 tps
   Latency (ms) : Min=5.54 | P10=5.55 | P25=5.58 | P50=5.62 | P75=5.68 | P90=5.80 | P95=5.92 | P99=5.92 | Max=5.92
   Mean/SD/Jitt : Mean=5.64ms | StdDev=0.10ms | Jitter=0.04ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth           : Avg=4072.45 MB/s | Peak=9865.94 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=24.69 MB | Write=0.00 MB | Syscalls=400
   Sync Stall vs Async DMA      : SyncStall=9.87 ms | AsyncOverlapped=36.60 ms (78.8% Overlapped)
   RAM Traffic & Effective BW   : 2.10 GB moved | Eff=1.37 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=2.547s + Sys=0.594s (Wall=1.564s) | SysUtil=50.2% | ThrUtil=50.2% | 46.42 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    950.48 ms (  457.0 us/tok | 62.14%)
   MoE AVX2 Q8 Expert Compute   :    376.70 ms (  181.1 us/tok | 24.63%)
   Router + Lookahead Dispatch  :     80.90 ms (   38.9 us/tok |  5.29%)
   LM Head Output Projection    :      5.86 ms (    2.8 us/tok |  0.38%)
   Foreground NVMe Sync Stall   :      9.87 ms (    4.7 us/tok |  0.65%)
   Unaccounted / OMP & Sampling :    105.74 ms (   50.8 us/tok |  6.91%) | Total Wall=1529.54 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.56%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.91%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.38%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    65.99%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.16%  |
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
    "ttft_ms": 238.82,
    "avg_tps": 686.7,
    "min_tps": 561.62,
    "max_tps": 779.74
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 144.13,
    "min_tps": 135.22,
    "max_tps": 148.3,
    "p50_ms": 6.91,
    "p90_ms": 7.14,
    "p99_ms": 7.4,
    "mean_ms": 6.94,
    "jitter_ms": 0.14
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
    "avg_mbs": 1083.84,
    "peak_mbs": 5760.37,
    "sync_wait_ms": 2.73,
    "async_overlap_ms": 6.29
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
    "dense_attention": 381.24,
    "moe_compute": 104.07,
    "router_lookahead": 7.42,
    "lm_head": 8.79,
    "unaccounted": 5.16
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 77.73,
    "ram_bandwidth_pinning": 1.71,
    "expert_cache_lrfu": 16.49,
    "lookahead_parallel_overlap": 2.45,
    "ssd_nvme_throughput": 1.62,
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
    "ttft_ms": 315.27,
    "avg_tps": 520.18,
    "min_tps": 372.88,
    "max_tps": 585.71
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 125.04,
    "min_tps": 107.93,
    "max_tps": 131.98,
    "p50_ms": 7.86,
    "p90_ms": 9.01,
    "p99_ms": 9.27,
    "mean_ms": 8.0,
    "jitter_ms": 0.2
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
    "avg_mbs": 1392.81,
    "peak_mbs": 7314.4,
    "sync_wait_ms": 8.07,
    "async_overlap_ms": 24.49
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
    "dense_attention": 352.89,
    "moe_compute": 203.14,
    "router_lookahead": 9.42,
    "lm_head": 8.91,
    "unaccounted": 44.75
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 73.31,
    "ram_bandwidth_pinning": 1.9,
    "expert_cache_lrfu": 14.03,
    "lookahead_parallel_overlap": 6.33,
    "ssd_nvme_throughput": 4.43,
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
  File "<stdin>", line 8
    data = json.loads(resp.read().decode())
    ^^^^
IndentationError: expected an indented block after 'with' statement on line 7
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 846K Nov 13 12:17 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 846K Nov 13 12:17 build/apex.exe
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
   SEQ1M Direct Uncached NVMe Read    :    462.95 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1468.96 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7310.65 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   9622.00 MB/s
   RND4K Q32T16 Read                  :    508.21 MB/s (  130102 IOPS)
   RND4K Q1T1  Read                   :    641.48 MB/s (Latency: 6.09 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     43.27 GB/s
   AVX2 256-bit Sequential Write BW   :     37.82 GB/s
   STREAM Triad (A = B + s*C) BW      :     25.27 GB/s
   Random Pointer-Chase Latency       :    113.43 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.33 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    172.48 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.50 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1420.51 tps | Avg=1420.51 tps | Hit=99.5% | NVMe=1569.1 MB/s (6.19 MB, QD=64) | RSS=71.3 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1242.30 tps | Avg=1325.44 tps | Hit=99.5% | NVMe=1526.2 MB/s (7.01 MB, QD=64) | RSS=71.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1018.61 tps | Avg=1204.50 tps | Hit=99.5% | NVMe=1459.0 MB/s (7.78 MB, QD=64) | RSS=71.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=976.98 tps | Avg=1138.23 tps | Hit=99.5% | NVMe=1434.4 MB/s (8.61 MB, QD=64) | RSS=72.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=864.07 tps | Avg=1070.31 tps | Hit=99.5% | NVMe=1392.0 MB/s (9.33 MB, QD=64) | RSS=72.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=810.51 tps | Avg=1016.03 tps | Hit=99.5% | NVMe=1370.9 MB/s (10.06 MB, QD=64) | RSS=72.6 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=740.67 tps | Avg=964.79 tps | Hit=99.5% | NVMe=1353.2 MB/s (10.83 MB, QD=64) | RSS=72.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=686.38 tps | Avg=918.24 tps | Hit=99.5% | NVMe=1336.8 MB/s (11.60 MB, QD=64) | RSS=73.1 MB
[LIVE-DECODE] 8/32 tok | Avg=193.59 tps | Hit=99.5% (LA:+0.0%) | NVMe=1230.2 MB/s (12.43 MB) | RSS=73.2 MB
[LIVE-DECODE] 16/32 tok | Avg=194.76 tps | Hit=99.5% (LA:+0.1%) | NVMe=1210.2 MB/s (13.10 MB) | RSS=73.2 MB
[LIVE-DECODE] 24/32 tok | Avg=195.54 tps | Hit=99.5% (LA:+0.1%) | NVMe=1187.1 MB/s (13.25 MB) | RSS=73.2 MB
[LIVE-DECODE] 32/32 tok | Avg=196.10 tps | Hit=99.5% (LA:+0.1%) | NVMe=1179.7 MB/s (13.30 MB) | RSS=73.2 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=73.17 MB | Peak=73.17 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2230.37 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.26 |  7 |  5 |  0 |   321.8 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.26 |  0 |  0 |  0 |   321.8 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.19 | 12 |  0 |  0 |    49.5 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.19 |  0 |  0 |  0 |    49.5 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.08 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.08 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.14 | 11 |  1 |  0 |    49.5 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.17 |  6 |  6 |  0 |   173.2 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.17 |  0 |  0 |  0 |   173.2 |
   |    9 |      68 | tok_68         |  176.71 | 100.0% |     228 |  144.43 |    5.14 |  0 |  0 |  0 |    49.5 |
   |   20 |      86 | tok_86         |  167.81 |  99.1% |     246 |  163.11 |    5.13 | 12 |  0 |  0 |    24.8 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.06 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.06 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.02 |  8 |  4 |  0 |    24.8 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.02 |  0 |  0 |  0 |    24.8 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.230s, TTFT=2230.37ms): Avg=918.24 | Min=686.38 | Max=1420.51 tps
   Prefill Chunks (8): C1:256t/1420.5tps/99% | C2:256t/1242.3tps/99% | C3:256t/1018.6tps/99% | C4:256t/977.0tps/99%
                       C5:256t/864.1tps/99% | C6:256t/810.5tps/99% | C7:256t/740.7tps/99% | C8:256t/686.4tps/99%
   Decode  (32 tok, 0.163s): Avg=196.10 | Min=190.18 | Max=201.18 tps
   Latency (ms) : Min=4.97 | P10=5.02 | P25=5.06 | P50=5.09 | P75=5.14 | P90=5.19 | P95=5.26 | P99=5.26 | Max=5.26
   Mean/SD/Jitt : Mean=5.10ms | StdDev=0.07ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth           : Avg=1179.65 MB/s | Peak=5555.56 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=13.31 MB | Write=0.00 MB | Syscalls=327
   Sync Stall vs Async DMA      : SyncStall=6.99 ms | AsyncOverlapped=9.80 ms (58.4% Overlapped)
   RAM Traffic & Effective BW   : 1.43 GB moved | Eff=0.60 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=3.266s + Sys=0.703s (Wall=2.414s) | SysUtil=41.1% | ThrUtil=41.1% | 38.01 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2010.23 ms (  966.5 us/tok | 83.99%)
   MoE AVX2 Q8 Expert Compute   :    248.83 ms (  119.6 us/tok | 10.40%)
   Router + Lookahead Dispatch  :     61.81 ms (   29.7 us/tok |  2.58%)
   LM Head Output Projection    :      5.87 ms (    2.8 us/tok |  0.25%)
   Foreground NVMe Sync Stall   :      6.99 ms (    3.4 us/tok |  0.29%)
   Unaccounted / OMP & Sampling :     59.81 ms (   28.8 us/tok |  2.50%) | Total Wall=2393.55 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    29.48%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.13%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.53%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    66.19%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.67%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1933.54 tps | Avg=1933.54 tps | Hit=99.2% | NVMe=2312.5 MB/s (24.91 MB, QD=64) | RSS=89.2 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1666.26 tps | Avg=1789.98 tps | Hit=99.2% | NVMe=3092.0 MB/s (42.92 MB, QD=64) | RSS=89.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1731.94 tps | Avg=1770.20 tps | Hit=99.2% | NVMe=3553.0 MB/s (61.04 MB, QD=64) | RSS=89.8 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1644.34 tps | Avg=1736.96 tps | Hit=99.2% | NVMe=3890.9 MB/s (79.10 MB, QD=64) | RSS=90.1 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1509.47 tps | Avg=1686.14 tps | Hit=99.2% | NVMe=4126.9 MB/s (97.14 MB, QD=64) | RSS=90.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1325.56 tps | Avg=1613.01 tps | Hit=99.2% | NVMe=4221.2 MB/s (115.20 MB, QD=64) | RSS=91.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1348.83 tps | Avg=1569.11 tps | Hit=99.2% | NVMe=4348.5 MB/s (133.27 MB, QD=64) | RSS=91.5 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1236.84 tps | Avg=1518.13 tps | Hit=99.2% | NVMe=4511.3 MB/s (151.30 MB, QD=64) | RSS=91.8 MB
[LIVE-DECODE] 8/32 tok | Avg=174.37 tps | Hit=99.2% (LA:+0.0%) | NVMe=4383.0 MB/s (152.70 MB) | RSS=91.8 MB
[LIVE-DECODE] 16/32 tok | Avg=175.98 tps | Hit=99.2% (LA:+0.1%) | NVMe=4293.7 MB/s (153.44 MB) | RSS=91.8 MB
[LIVE-DECODE] 24/32 tok | Avg=177.00 tps | Hit=99.2% (LA:+0.1%) | NVMe=4171.2 MB/s (154.78 MB) | RSS=91.8 MB
[LIVE-DECODE] 32/32 tok | Avg=177.27 tps | Hit=99.2% (LA:+0.1%) | NVMe=4072.5 MB/s (155.58 MB) | RSS=91.8 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=91.82 MB | Peak=91.82 MB
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
   |    1 |      49 | qtok_49        |   64.27 |  98.4% |     254 |   60.04 | 1349.03 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.20 | 100.0% |       2 |   54.20 |    5.92 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   94.59 | 100.0% |     177 |   84.92 |    5.92 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.79 | 100.0% |       2 |   56.49 |    5.80 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   85.06 |  99.7% |     177 |   78.63 |    5.80 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   71.17 | 100.0% |       2 |   58.64 |    5.64 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   82.87 |  99.7% |     129 |   77.18 |    5.64 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.31 | 100.0% |      66 |   61.15 |    5.58 | 16 |  0 |  0 |    32.0 |
   |   14 |     223 | qtok_223       |   66.25 |  89.5% |     159 |   64.10 |    5.70 | 16 |  0 |  0 |    32.0 |
   |   15 |     113 | qtok_113       |  105.20 | 100.0% |      33 |   89.25 |    5.70 |  0 |  0 |  0 |    32.0 |
   |   10 |     254 | qtok_254       |   71.08 |  99.9% |      66 |   64.40 |    5.66 | 15 |  1 |  0 |    59.8 |
   |   11 |     129 | qtok_129       |   83.90 |  51.4% |      49 |   83.85 |    5.66 |  0 |  0 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   71.22 |  99.9% |      66 |   64.31 |    5.61 | 14 |  2 |  0 |    87.5 |
   |   31 |      49 | qtok_49        |  125.25 | 100.0% |     177 |   99.98 |    5.61 |  0 |  0 |  0 |    87.5 |
   |   32 |     254 | qtok_254       |   71.45 |  98.0% |      66 |   67.49 |    5.68 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  131.17 | 100.0% |     129 |  104.87 |    5.68 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.349s, TTFT=1349.03ms): Avg=1518.13 | Min=1236.84 | Max=1933.54 tps
   Prefill Chunks (8): C1:256t/1933.5tps/99% | C2:256t/1666.3tps/99% | C3:256t/1731.9tps/99% | C4:256t/1644.3tps/99%
                       C5:256t/1509.5tps/99% | C6:256t/1325.6tps/99% | C7:256t/1348.8tps/99% | C8:256t/1236.8tps/99%
   Decode  (32 tok, 0.181s): Avg=177.27 | Min=168.99 | Max=180.66 tps
   Latency (ms) : Min=5.54 | P10=5.55 | P25=5.58 | P50=5.62 | P75=5.68 | P90=5.80 | P95=5.92 | P99=5.92 | Max=5.92
   Mean/SD/Jitt : Mean=5.64ms | StdDev=0.10ms | Jitter=0.04ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth           : Avg=4072.45 MB/s | Peak=9865.94 MB/s (Pre-flight hwtest skipped)
   OS Kernel I/O Verification   : Read=24.69 MB | Write=0.00 MB | Syscalls=400
   Sync Stall vs Async DMA      : SyncStall=9.87 ms | AsyncOverlapped=36.60 ms (78.8% Overlapped)
   RAM Traffic & Effective BW   : 2.10 GB moved | Eff=1.37 GB/s (STREAM hwtest skipped)
   CPU Time & Utilization       : User=2.547s + Sys=0.594s (Wall=1.564s) | SysUtil=50.2% | ThrUtil=50.2% | 46.42 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    950.48 ms (  457.0 us/tok | 62.14%)
   MoE AVX2 Q8 Expert Compute   :    376.70 ms (  181.1 us/tok | 24.63%)
   Router + Lookahead Dispatch  :     80.90 ms (   38.9 us/tok |  5.29%)
   LM Head Output Projection    :      5.86 ms (    2.8 us/tok |  0.38%)
   Foreground NVMe Sync Stall   :      9.87 ms (    4.7 us/tok |  0.65%)
   Unaccounted / OMP & Sampling :    105.74 ms (   50.8 us/tok |  6.91%) | Total Wall=1529.54 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.56%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.91%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.38%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    65.99%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.16%  |
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
    "ttft_ms": 238.82,
    "avg_tps": 686.7,
    "min_tps": 561.62,
    "max_tps": 779.74
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 144.13,
    "min_tps": 135.22,
    "max_tps": 148.3,
    "p50_ms": 6.91,
    "p90_ms": 7.14,
    "p99_ms": 7.4,
    "mean_ms": 6.94,
    "jitter_ms": 0.14
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
    "avg_mbs": 1083.84,
    "peak_mbs": 5760.37,
    "sync_wait_ms": 2.73,
    "async_overlap_ms": 6.29
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
    "dense_attention": 381.24,
    "moe_compute": 104.07,
    "router_lookahead": 7.42,
    "lm_head": 8.79,
    "unaccounted": 5.16
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 77.73,
    "ram_bandwidth_pinning": 1.71,
    "expert_cache_lrfu": 16.49,
    "lookahead_parallel_overlap": 2.45,
    "ssd_nvme_throughput": 1.62,
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
    "ttft_ms": 315.27,
    "avg_tps": 520.18,
    "min_tps": 372.88,
    "max_tps": 585.71
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 125.04,
    "min_tps": 107.93,
    "max_tps": 131.98,
    "p50_ms": 7.86,
    "p90_ms": 9.01,
    "p99_ms": 9.27,
    "mean_ms": 8.0,
    "jitter_ms": 0.2
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
    "avg_mbs": 1392.81,
    "peak_mbs": 7314.4,
    "sync_wait_ms": 8.07,
    "async_overlap_ms": 24.49
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
    "dense_attention": 352.89,
    "moe_compute": 203.14,
    "router_lookahead": 9.42,
    "lm_head": 8.91,
    "unaccounted": 44.75
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 73.31,
    "ram_bandwidth_pinning": 1.9,
    "expert_cache_lrfu": 14.03,
    "lookahead_parallel_overlap": 6.33,
    "ssd_nvme_throughput": 4.43,
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
  File "<stdin>", line 8
    data = json.loads(resp.read().decode())
    ^^^^
IndentationError: expected an indented block after 'with' statement on line 7
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
