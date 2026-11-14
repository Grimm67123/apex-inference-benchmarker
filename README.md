<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#29 (Run ID `43579936566`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43579936566)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-14 09:45:24 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T09:18:41.573Z] ================================================================================
[2026-11-14T09:18:41.592Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T09:18:41.594Z] ================================================================================
[2026-11-14T09:18:46.137Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T09:18:46.366Z] --------------------------------------------------------------------------------
[2026-11-14T09:18:46.368Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 31 GB / 149.89 GB
[2026-11-14T09:18:46.369Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-14T09:18:46.371Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.01 GB
[2026-11-14T09:18:46.385Z] --------------------------------------------------------------------------------
[2026-11-14T09:18:46.387Z]  [OK] Disk space verification passed: 178.01 GB >= 150.00 GB.
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
   System Memory (RAM): 15.99 GB Total / 13.46 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    430.00 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1623.86 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7844.96 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10492.75 MB/s
   RND4K Q32T16 Read                  :    484.50 MB/s (  124033 IOPS)
   RND4K Q1T1  Read                   :    664.32 MB/s (Latency: 5.88 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     58.30 GB/s
   AVX2 256-bit Sequential Write BW   :     40.06 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.95 GB/s
   Random Pointer-Chase Latency       :     51.85 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     50.96 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    101.03 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     18.95 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1423.48 tps | Avg=1423.48 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=60.5 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1235.44 tps | Avg=1322.81 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=60.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1116.87 tps | Avg=1246.22 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=61.1 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=964.12 tps | Avg=1161.27 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=61.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=900.95 tps | Avg=1097.83 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=61.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=806.78 tps | Avg=1035.57 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=61.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=755.78 tps | Avg=983.55 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=62.1 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=691.58 tps | Avg=934.25 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=62.4 MB
[LIVE-DECODE] 8/32 tok | Avg=196.08 tps | Hit=100.0% (LA:+0.0%) | NVMe=2558.3 MB/s (6.58 MB) | RSS=62.4 MB
[LIVE-DECODE] 16/32 tok | Avg=196.73 tps | Hit=100.0% (LA:+0.0%) | NVMe=2558.3 MB/s (6.58 MB) | RSS=62.4 MB
[LIVE-DECODE] 24/32 tok | Avg=197.15 tps | Hit=100.0% (LA:+0.0%) | NVMe=2558.3 MB/s (6.58 MB) | RSS=62.4 MB
[LIVE-DECODE] 32/32 tok | Avg=197.00 tps | Hit=100.0% (LA:+0.0%) | NVMe=2558.3 MB/s (6.58 MB) | RSS=62.4 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=62.41 MB | Peak=62.41 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2192.14 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.08 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.08 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.05 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.05 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.16 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.16 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.10 | 12 |  0 |  0 |     0.0 |
   |   28 |     246 | tok_246        |  194.87 | 100.0% |      54 |  173.43 |    5.13 | 12 |  0 |  0 |     0.0 |
   |   29 |     229 | tok_229        |  172.54 | 100.0% |      70 |  154.16 |    5.13 |  0 |  0 |  0 |     0.0 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.10 | 12 |  0 |  0 |     0.0 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.10 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.08 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.08 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.06 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.06 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.192s, TTFT=2192.14ms): Avg=934.25 | Min=691.58 | Max=1423.48 tps
   Prefill Chunks (8): C1:256t/1423.5tps/100% | C2:256t/1235.4tps/100% | C3:256t/1116.9tps/100% | C4:256t/964.1tps/100%
                       C5:256t/901.0tps/100% | C6:256t/806.8tps/100% | C7:256t/755.8tps/100% | C8:256t/691.6tps/100%
   Decode  (32 tok, 0.162s): Avg=197.00 | Min=193.72 | Max=198.98 tps
   Latency (ms) : Min=5.03 | P10=5.04 | P25=5.05 | P50=5.08 | P75=5.10 | P90=5.13 | P95=5.16 | P99=5.16 | Max=5.16
   Mean/SD/Jitt : Mean=5.08ms | StdDev=0.03ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=247.52 | Avg=2558.28 | Peak=6443.30 MB/s | WallAmort=2.79 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=1.22 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.41 GB moved | Active=0.63 GB/s | WallAmort=0.60 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.19s (93.1%, 0.00 MB SSD) | Decode=0.16s (6.9%, 0.00 MB SSD)
   CPU Time & Utilization       : User=2.938s + Sys=0.734s (Wall=2.371s) | SysUtil=38.7% | ThrUtil=38.7% | 35.82 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1983.01 ms (  953.4 us/tok | 84.22%)
   MoE AVX2 Q8 Expert Compute   :    249.12 ms (  119.8 us/tok | 10.58%)
   Router + Lookahead Dispatch  :     59.48 ms (   28.6 us/tok |  2.53%)
   LM Head Output Projection    :      5.71 ms (    2.7 us/tok |  0.24%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     57.26 ms (   27.5 us/tok |  2.43%) | Total Wall=2354.58 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    16.56%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.15%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.09%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    79.20%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.00%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1881.55 tps | Avg=1881.55 tps | Hit=99.2% | NVMe=2630.7 MB/s (24.91 MB, QD=64) | RSS=85.7 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1839.90 tps | Avg=1860.49 tps | Hit=99.2% | NVMe=3642.9 MB/s (42.92 MB, QD=64) | RSS=85.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1698.00 tps | Avg=1802.98 tps | Hit=99.2% | NVMe=4227.4 MB/s (61.04 MB, QD=64) | RSS=86.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1583.47 tps | Avg=1742.59 tps | Hit=99.2% | NVMe=4672.8 MB/s (79.10 MB, QD=64) | RSS=86.5 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1532.98 tps | Avg=1696.20 tps | Hit=99.2% | NVMe=5003.8 MB/s (97.14 MB, QD=64) | RSS=87.0 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1437.07 tps | Avg=1646.71 tps | Hit=99.2% | NVMe=5240.8 MB/s (115.20 MB, QD=64) | RSS=87.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1319.63 tps | Avg=1590.40 tps | Hit=99.2% | NVMe=5455.6 MB/s (133.27 MB, QD=64) | RSS=87.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1284.94 tps | Avg=1544.50 tps | Hit=99.2% | NVMe=5675.4 MB/s (151.30 MB, QD=64) | RSS=88.2 MB
[LIVE-DECODE] 8/32 tok | Avg=177.42 tps | Hit=99.2% (LA:+0.0%) | NVMe=5570.0 MB/s (152.70 MB) | RSS=88.3 MB
[LIVE-DECODE] 16/32 tok | Avg=178.05 tps | Hit=99.2% (LA:+0.1%) | NVMe=5518.3 MB/s (153.28 MB) | RSS=88.3 MB
[LIVE-DECODE] 24/32 tok | Avg=178.14 tps | Hit=99.2% (LA:+0.1%) | NVMe=5423.9 MB/s (154.23 MB) | RSS=88.3 MB
[LIVE-DECODE] 32/32 tok | Avg=178.43 tps | Hit=99.2% (LA:+0.1%) | NVMe=5333.8 MB/s (155.30 MB) | RSS=88.3 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=88.26 MB | Peak=88.26 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1325.99 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    5.69 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    5.69 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    5.58 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    5.58 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    5.63 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    5.63 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    5.66 | 16 |  0 |  0 |    32.0 |
   |   28 |      49 | qtok_49        |   65.10 | 100.0% |      18 |   55.78 |    5.66 | 10 |  6 |  0 |   198.5 |
   |   29 |     148 | qtok_148       |   77.89 | 100.0% |     127 |   51.09 |    5.66 |  0 |  0 |  0 |   198.5 |
   |    9 |      49 | qtok_49        |   84.72 | 100.0% |     129 |   76.64 |    5.66 |  0 |  0 |  0 |    32.0 |
   |   10 |     254 | qtok_254       |   70.81 |  99.7% |      66 |   64.77 |    5.64 | 15 |  1 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.55 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.55 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.56 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.56 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.326s, TTFT=1325.99ms): Avg=1544.50 | Min=1284.94 | Max=1881.55 tps
   Prefill Chunks (8): C1:256t/1881.5tps/99% | C2:256t/1839.9tps/99% | C3:256t/1698.0tps/99% | C4:256t/1583.5tps/99%
                       C5:256t/1533.0tps/99% | C6:256t/1437.1tps/99% | C7:256t/1319.6tps/99% | C8:256t/1284.9tps/99%
   Decode  (32 tok, 0.179s): Avg=178.43 | Min=175.87 | Max=180.68 tps
   Latency (ms) : Min=5.53 | P10=5.55 | P25=5.57 | P50=5.62 | P75=5.64 | P90=5.66 | P95=5.69 | P99=5.69 | Max=5.69
   Mean/SD/Jitt : Mean=5.60ms | StdDev=0.04ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=453.93 | Avg=5333.82 | Peak=11397.55 MB/s | WallAmort=103.17 MB/s
   OS Kernel I/O Verification   : Read=24.47 MB | Write=0.00 MB | Syscalls=391
   Sync Stall vs Async DMA      : SyncStall=5.80 ms | AsyncOverlapped=27.10 ms (82.4% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.60 GB/s | WallAmort=1.40 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.33s (88.1%, 144.44 MB SSD) | Decode=0.18s (11.9%, 4.00 MB SSD)
   CPU Time & Utilization       : User=2.812s + Sys=0.500s (Wall=1.538s) | SysUtil=53.9% | ThrUtil=53.9% | 49.81 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    933.76 ms (  448.9 us/tok | 62.03%)
   MoE AVX2 Q8 Expert Compute   :    375.65 ms (  180.6 us/tok | 24.95%)
   Router + Lookahead Dispatch  :     81.78 ms (   39.3 us/tok |  5.43%)
   LM Head Output Projection    :      5.86 ms (    2.8 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :      5.80 ms (    2.8 us/tok |  0.39%)
   Unaccounted / OMP & Sampling :    102.48 ms (   49.3 us/tok |  6.81%) | Total Wall=1505.34 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    17.72%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.85%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.86%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    70.09%  |
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
  "kv_cache_ram_bytes": 10797056,
  "kv_bytes_per_token": 2560,
  "expert_cache_ram_bytes": 2534400,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 237.77,
    "avg_tps": 689.75,
    "min_tps": 564.19,
    "max_tps": 784.91
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 143.26,
    "min_tps": 129.12,
    "max_tps": 146.89,
    "p50_ms": 6.91,
    "p90_ms": 7.26,
    "p99_ms": 7.74,
    "mean_ms": 6.98,
    "jitter_ms": 0.16
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
    "avg_mbs": 2606.72,
    "peak_mbs": 5813.95,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.86
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
    "dense_attention": 381.3,
    "moe_compute": 106.07,
    "router_lookahead": 7.25,
    "lm_head": 8.97,
    "unaccounted": 6.41
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 88.25,
    "ram_bandwidth_pinning": 1.92,
    "expert_cache_lrfu": 8.03,
    "lookahead_parallel_overlap": 1.44,
    "ssd_nvme_throughput": 0.36,
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
    "ttft_ms": 307.15,
    "avg_tps": 533.95,
    "min_tps": 378.06,
    "max_tps": 613.33
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 123.08,
    "min_tps": 98.61,
    "max_tps": 129.4,
    "p50_ms": 7.89,
    "p90_ms": 9.0,
    "p99_ms": 10.14,
    "mean_ms": 8.12,
    "jitter_ms": 0.25
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
    "avg_mbs": 2682.39,
    "peak_mbs": 9432.87,
    "sync_wait_ms": 4.57,
    "async_overlap_ms": 12.34
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
    "dense_attention": 355.28,
    "moe_compute": 203.06,
    "router_lookahead": 9.2,
    "lm_head": 8.94,
    "unaccounted": 42.96
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.66,
    "ram_bandwidth_pinning": 2.14,
    "expert_cache_lrfu": 8.17,
    "lookahead_parallel_overlap": 4.39,
    "ssd_nvme_throughput": 2.64,
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
   System Memory (RAM): 15.99 GB Total / 13.45 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    495.52 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1469.92 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8190.95 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10639.14 MB/s
   RND4K Q32T16 Read                  :    481.64 MB/s (  123300 IOPS)
   RND4K Q1T1  Read                   :    742.78 MB/s (Latency: 5.26 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     60.72 GB/s
   AVX2 256-bit Sequential Write BW   :     49.87 GB/s
   STREAM Triad (A = B + s*C) BW      :     41.33 GB/s
   Random Pointer-Chase Latency       :     51.89 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.03 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    183.09 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.47 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 31.00 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 133.65 MB/s (7.66s)
   Window #01 (256.0 MB in 0.50s):   511.38 MB/s (Uncached Direct Read)
   Window #02 (244.0 MB in 0.53s):   458.53 MB/s (Uncached Direct Read)
   Window #03 (196.0 MB in 0.51s):   386.85 MB/s (Uncached Direct Read)
   Window #04 (216.0 MB in 0.55s):   390.73 MB/s (Uncached Direct Read)
   Window #05 (112.0 MB in 0.24s):   457.54 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   438.16 MB/s (Min=386.85 | Max=511.38 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 397.55 MB/s (2.58s)
   Window #01 (184.0 MB in 0.50s):   366.73 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   389.35 MB/s (Uncached Direct Read)
   Window #03 (216.0 MB in 0.55s):   392.32 MB/s (Uncached Direct Read)
   Window #04 (220.0 MB in 0.54s):   408.96 MB/s (Uncached Direct Read)
   Window #05 (196.0 MB in 0.50s):   388.26 MB/s (Uncached Direct Read)
   Window #06 ( 12.0 MB in 0.00s):  2649.24 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   393.39 MB/s (Min=366.73 | Max=2649.24 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: qwen38 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (0.010 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 100.00% (0.01/0.01 GB) @ 17.6 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (43.792 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  11.42% (5.00/43.79 GB) @ 355.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  22.84% (10.00/43.79 GB) @ 317.1 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  34.25% (15.00/43.79 GB) @ 323.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  45.67% (20.00/43.79 GB) @ 326.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  57.09% (25.00/43.79 GB) @ 322.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  68.51% (30.00/43.79 GB) @ 318.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  79.92% (35.00/43.79 GB) @ 299.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  91.34% (40.00/43.79 GB) @ 291.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf: 100.00% (43.79/43.79 GB) @ 280.0 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (26.822 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  18.64% (5.00/26.82 GB) @ 186.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  37.28% (10.00/26.82 GB) @ 229.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  55.92% (15.00/26.82 GB) @ 257.4 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  74.57% (20.00/26.82 GB) @ 262.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  93.21% (25.00/26.82 GB) @ 269.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf: 100.00% (26.82/26.82 GB) @ 270.5 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/MTP/mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (2.595 GB) -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Sequential Non-Truncate)
  [DL] mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 100.00% (2.60/2.60 GB) @ 117.6 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=78,618,661,594 (73.22 GB) | Elapsed=286.27s
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
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7999.88 MB (3855 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=2.75 tps | Avg=2.75 tps | Hit=88.1% | NVMe=780.1 MB/s (10578.12 MB, QD=64) | RSS=13794.6 MB
[LIVE-DECODE] 8/32 tok | Avg=1.72 tps | Hit=89.4% (LA:+0.9%) | NVMe=829.8 MB/s (12068.83 MB) | RSS=13771.4 MB
[LIVE-DECODE] 16/32 tok | Avg=1.80 tps | Hit=90.5% (LA:+1.2%) | NVMe=873.2 MB/s (13291.94 MB) | RSS=13743.2 MB
[LIVE-DECODE] 24/32 tok | Avg=1.83 tps | Hit=91.4% (LA:+1.3%) | NVMe=914.1 MB/s (14367.80 MB) | RSS=13736.1 MB
[LIVE-DECODE] 31/32 tok | Avg=1.85 tps | Hit=92.0% (LA:+1.5%) | NVMe=942.8 MB/s (15318.39 MB) | RSS=13735.4 MB

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
   LRFU Cache / Staging Ring    : 7999.88 MB (3855/25088 exp = 15.37% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13735.40 MB | Peak=14033.30 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (31 tok) : " a2

as
2:
2u
ar
22
22
0
2223

<|im_start|>

u"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 32 Steps)]
   Logit Summary: AvgTop1Prob=10.8% | AvgMargin=1.072 | MinMargin=0.004
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.79 |  18.1% |     303 |   13.43 | 23272.16 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    8.52 |   0.6% |     286 |    8.17 |  648.94 |889 | 71 |  0 | 237101.5 |
   |    3 |     198 | \n             |   14.17 |  53.5% |      11 |   12.36 |  648.94 |  0 |  0 |  0 | 237101.5 |
   |    4 |     198 | \n             |    9.66 |   5.1% |     350 |    7.90 |  694.00 |418 | 61 |  1 | 227289.0 |
   |    5 |     299 | as             |    8.80 |   1.5% |      64 |    8.72 |  519.67 |456 | 24 |  0 | 131518.0 |
   |    6 |     198 | \n             |   10.44 |  11.5% |      25 |    9.21 |  566.27 |441 | 39 |  0 | 199143.0 |
   |    7 |      17 | 2              |   10.14 |   5.4% |      18 |    9.57 |  514.26 |454 | 26 |  0 | 131872.0 |
   |    8 |      25 | :              |    9.71 |   7.4% |     198 |    8.84 |  521.68 |448 | 32 |  0 | 159664.0 |
   |   19 |      17 | 2              |    9.23 |   2.8% |      16 |    9.20 |  613.21 |472 |  8 |  0 | 143339.0 |
   |   17 |     198 | \n             |    9.98 |   5.6% |      24 |    8.90 |  555.65 |441 | 39 |  0 | 213793.0 |
   |   27 |     198 | \n             |   11.97 |  38.6% |      17 |    9.61 |  542.69 |442 | 38 |  0 | 194564.0 |
   |   10 |      17 | 2              |    9.02 |   2.6% |     198 |    8.66 |  539.91 |463 | 17 |  0 | 126814.0 |
   |   29 |  248045 | <|im_start|>   |    8.43 |   1.2% |      17 |    7.65 |  503.57 |467 | 13 |  0 | 108043.0 |
   |   30 |     198 | \n             |   10.29 |   7.2% |      84 |    8.09 |  538.25 |449 | 31 |  0 | 160314.0 |
   |   31 |     198 | \n             |    8.42 |   1.1% |      17 |    7.79 |  509.40 |471 |  9 |  0 | 104364.0 |
   |   32 |      84 | u              |    8.39 |   0.9% |      17 |    7.95 |  507.41 |472 |  8 |  0 | 102693.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 23.272s, TTFT=23272.16ms): Avg=2.75 | Min=2.75 | Max=2.75 tps
   Prefill Chunks (1): C1:64t/2.8tps/88%
   Decode  (31 tok, 16.713s): Avg=1.85 | Min=1.44 | Max=1.99 tps
   Latency (ms) : Min=503.40 | P10=505.23 | P25=509.71 | P50=521.68 | P75=539.91 | P90=613.21 | P95=648.94 | P99=694.00 | Max=694.00
   Mean/SD/Jitt : Mean=539.12ms | StdDev=46.78ms | Jitter=30.20ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/31
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (45600): RawRAM=41269 (90.50%) | Lookahead=682 (+1.50%) | ColdMiss=3649 (8.00%) | EFF HIT=92.00%
   Lookahead    : 2843 prefetched -> 692 consumed (24.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  950 |  666 |  70 | 214 | 77.5%| 475.05 | | L24 |  950 |  894 |   9 |  47 | 95.1%| 116.55 |
   | L01 |  950 |  815 |  41 |  94 | 90.1%| 393.46 | | L25 |  950 |  890 |   8 |  52 | 94.5%| 116.55 |
   | L02 |  950 |  824 |  24 | 102 | 89.3%| 405.98 | | L26 |  950 |  866 |  17 |  67 | 92.9%| 191.75 |
   | L03 |  950 |  892 |   3 |  55 | 94.2%| 552.69 | | L27 |  950 |  872 |  14 |  64 | 93.3%| 265.06 |
   | L04 |  950 |  885 |   7 |  58 | 93.9%| 315.43 | | L28 |  950 |  850 |  22 |  78 | 91.8%| 233.11 |
   | L05 |  950 |  870 |  10 |  70 | 92.6%| 317.70 | | L29 |  950 |  862 |  10 |  78 | 91.8%| 164.21 |
   | L06 |  950 |  873 |  16 |  61 | 93.6%| 221.83 | | L30 |  950 |  836 |  15 |  99 | 89.6%| 200.22 |
   | L07 |  950 |  874 |  16 |  60 | 93.7%| 165.09 | | L31 |  950 |  833 |  21 |  96 | 89.9%| 207.42 |
   | L08 |  950 |  900 |  10 |  40 | 95.8%| 109.57 | | L32 |  950 |  863 |   8 |  79 | 91.7%| 193.63 |
   | L09 |  950 |  894 |   3 |  53 | 94.4%|  98.36 | | L33 |  950 |  855 |  13 |  82 | 91.4%| 151.25 |
   | L10 |  950 |  882 |  11 |  57 | 94.0%| 118.29 | | L34 |  950 |  863 |   6 |  81 | 91.5%| 162.77 |
   | L11 |  950 |  895 |   5 |  50 | 94.7%| 144.43 | | L35 |  950 |  878 |   4 |  68 | 92.8%| 116.67 |
   | L12 |  950 |  870 |  16 |  64 | 93.3%| 233.11 | | L36 |  950 |  856 |  14 |  80 | 91.6%| 241.99 |
   | L13 |  950 |  861 |  17 |  72 | 92.4%| 146.92 | | L37 |  950 |  878 |   7 |  65 | 93.2%| 140.99 |
   | L14 |  950 |  853 |  19 |  78 | 91.8%| 214.62 | | L38 |  950 |  874 |  12 |  64 | 93.3%| 246.26 |
   | L15 |  950 |  857 |  12 |  81 | 91.5%| 233.11 | | L39 |  950 |  864 |  12 |  74 | 92.2%| 334.62 |
   | L16 |  950 |  868 |  10 |  72 | 92.4%| 182.35 | | L40 |  950 |  855 |  11 |  84 | 91.2%| 255.66 |
   | L17 |  950 |  868 |  13 |  69 | 92.7%| 187.99 | | L41 |  950 |  857 |   4 |  89 | 90.6%| 136.84 |
   | L18 |  950 |  862 |  18 |  70 | 92.6%| 186.11 | | L42 |  950 |  824 |  17 | 109 | 88.5%| 259.28 |
   | L19 |  950 |  872 |  10 |  68 | 92.8%| 159.89 | | L43 |  950 |  864 |   8 |  78 | 91.8%| 180.05 |
   | L20 |  950 |  844 |  16 |  90 | 90.5%| 184.38 | | L44 |  950 |  853 |   9 |  88 | 90.7%| 164.21 |
   | L21 |  950 |  831 |  31 |  88 | 90.7%| 404.17 | | L45 |  950 |  839 |  15 |  96 | 89.9%| 223.27 |
   | L22 |  950 |  884 |  14 |  52 | 94.5%| 238.75 | | L46 |  950 |  876 |  10 |  64 | 93.3%| 218.95 |
   | L23 |  950 |  876 |  10 |  64 | 93.3%| 162.77 | | L47 |  950 |  851 |  14 |  85 | 91.1%| 274.46 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 15318.39 MB (Load=4614.69 | Prefill=5963.42 | Warmup=0.00 | Decode=4740.28 MB)
   SSD Data/Token (Decode)      : Avg=152.912 MB/tok (Min=100.286 | P50=143.666 | P95=221.962 | Max=231.544 MB) | Prefill=93.178 MB/tok
   NVMe Batches / Requests      : 1446 Batches | 22104 Raw -> 21338 Merged (766 LBA Merges, Avg 735.1 KB/io)
   SSD I/O Size Histogram       : <64K=1835 | 64K-512K=5284 | 512K-2M=13785 | >2M=434
   SSD Read Bandwidth (Active)  : Min=2.33 | Avg=942.82 | Peak=9264.26 MB/s | WallAmort=383.11 MB/s
   OS Kernel I/O Verification   : Read=15338.37 MB | Write=0.00 MB | Syscalls=30840
   Sync Stall vs Async DMA      : SyncStall=2850.73 ms | AsyncOverlapped=5582.09 ms (66.2% Overlapped)
   RAM Traffic & Active BW      : 392.99 GB moved | Active=11.21 GB/s | WallAmort=9.83 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=23.27s (58.2%, 5963.42 MB SSD) | Decode=16.71s (41.8%, 4740.28 MB SSD)
   CPU Time & Utilization       : User=107.406s + Sys=8.609s (Wall=55.275s) | SysUtil=52.5% | ThrUtil=52.5% | 48.54 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  17615.16 ms (185422.8 us/tok | 44.05%)
   MoE AVX2 Q8 Expert Compute   :  16245.92 ms (171009.7 us/tok | 40.63%)
   Router + Lookahead Dispatch  :    991.14 ms (10433.0 us/tok |  2.48%)
   LM Head Output Projection    :   1182.99 ms (12452.6 us/tok |  2.96%)
   Foreground NVMe Sync Stall   :   2850.73 ms (30007.7 us/tok |  7.13%)
   Unaccounted / OMP & Sampling :   1098.88 ms (11567.1 us/tok |  2.75%) | Total Wall=39984.83 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    73.91%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.41%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     6.47%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    11.88%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.33%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 57s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 14.74 GB Available
   Active Drive Space : 150.00 GB Total / 76.31 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    447.53 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1515.50 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7953.47 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10172.58 MB/s
   RND4K Q32T16 Read                  :    420.33 MB/s (  107603 IOPS)
   RND4K Q1T1  Read                   :    439.30 MB/s (Latency: 8.89 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     62.67 GB/s
   AVX2 256-bit Sequential Write BW   :     51.77 GB/s
   STREAM Triad (A = B + s*C) BW      :     44.13 GB/s
   Random Pointer-Chase Latency       :     47.84 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.39 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    191.26 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     20.65 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=3.88 tps | Avg=3.88 tps | Hit=91.8% | NVMe=477.1 MB/s (5364.89 MB, QD=64) | RSS=14219.6 MB

 >>> [Apex-Model-Response] !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   LRFU Cache / Staging Ring    : 8483.40 MB (4088/25088 exp = 16.29% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=14235.63 MB | Peak=14475.04 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (63 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 23434.55 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  817.94 |952 |  8 |  0 | 39476.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  817.94 |  0 |  0 |  0 | 39476.5 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  656.28 |480 |  0 |  0 |    64.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  687.62 |479 |  1 |  0 |  3064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  656.55 |480 |  0 |  0 |  1339.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  670.73 |480 |  0 |  0 |    64.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  666.56 |480 |  0 |  0 |    64.0 |
   |   23 |       0 | !              |     nan | 100.0% |       1 |     nan |  689.06 |480 |  0 |  0 |    64.0 |
   |   32 |       0 | !              |     nan | 100.0% |       1 |     nan |  688.00 |480 |  0 |  0 |    64.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  686.62 |480 |  0 |  0 |    64.0 |
   |   30 |       0 | !              |     nan | 100.0% |       1 |     nan |  686.03 |480 |  0 |  0 |    64.0 |
   |   61 |       0 | !              |     nan | 100.0% |       1 |     nan |  483.38 |480 |  0 |  0 |    64.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  484.15 |480 |  0 |  0 |    64.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  481.59 |480 |  0 |  0 |    64.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  482.12 |480 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 23.435s, TTFT=23434.55ms): Avg=3.88 | Min=3.88 | Max=3.88 tps
   Prefill Chunks (1): C1:91t/3.9tps/92%
   Decode  (63 tok, 39.373s): Avg=1.60 | Min=1.22 | Max=2.13 tps
   Latency (ms) : Min=470.46 | P10=483.76 | P25=549.24 | P50=659.82 | P75=675.34 | P90=686.03 | P95=688.00 | P99=817.94 | Max=817.94
   Mean/SD/Jitt : Mean=624.98ms | StdDev=85.80ms | Jitter=17.08ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (35877): RawRAM=35404 (98.68%) | Lookahead=9 (+0.03%) | ColdMiss=464 (1.29%) | EFF HIT=98.71%
   Lookahead    : 23 prefetched -> 10 consumed (43.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1266 |   9 | 265 | 82.8%| 461.57 | | L24 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L01 |  946 |  865 |   0 |  81 | 91.4%| 117.04 | | L25 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L02 |  946 |  873 |   0 |  73 | 92.3%| 122.97 | | L26 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L03 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L27 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L04 |  721 |  720 |   0 |   1 | 99.9%|   2.08 | | L28 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L05 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L29 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L06 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L30 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L07 |  721 |  720 |   0 |   1 | 99.9%|   1.68 | | L31 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L08 |  721 |  720 |   0 |   1 | 99.9%|   1.25 | | L32 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L09 |  721 |  720 |   0 |   1 | 99.9%|   1.25 | | L33 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L10 |  721 |  720 |   0 |   1 | 99.9%|   1.25 | | L34 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L11 |  721 |  720 |   0 |   1 | 99.9%|   1.25 | | L35 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L12 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L36 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L13 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L37 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L14 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L38 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L15 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L39 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L16 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L40 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L17 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L41 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L18 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L42 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L19 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L43 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L20 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L44 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L21 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L45 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L22 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L46 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L23 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L47 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 5449.98 MB (Load=4614.69 | Prefill=750.20 | Warmup=0.00 | Decode=85.09 MB)
   SSD Data/Token (Decode)      : Avg=1.351 MB/tok (Min=0.062 | P50=0.062 | P95=0.062 | Max=38.551 MB) | Prefill=8.244 MB/tok
   NVMe Batches / Requests      : 127 Batches | 5060 Raw -> 4853 Merged (207 LBA Merges, Avg 1150.0 KB/io)
   SSD I/O Size Histogram       : <64K=2674 | 64K-512K=1137 | 512K-2M=636 | >2M=406
   SSD Read Bandwidth (Active)  : Min=0.81 | Avg=477.57 | Peak=3911.27 MB/s | WallAmort=86.77 MB/s (100.0% of 447.5 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=6288.31 MB | Write=128.00 MB | Syscalls=21905
   Sync Stall vs Async DMA      : SyncStall=604.28 ms | AsyncOverlapped=703.38 ms (53.8% Overlapped)
   RAM Traffic & Active BW      : 497.06 GB moved | Active=8.37 GB/s (19.0% STREAM) | WallAmort=7.91 GB/s (Max=44.13 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=23.43s (37.3%, 750.20 MB SSD) | Decode=39.37s (62.7%, 85.09 MB SSD)
   CPU Time & Utilization       : User=128.703s + Sys=12.172s (Wall=79.096s) | SysUtil=44.5% | ThrUtil=44.5% | 85.16 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  40117.40 ms (260502.6 us/tok | 63.87%)
   MoE AVX2 Q8 Expert Compute   :  16076.96 ms (104395.8 us/tok | 25.60%)
   Router + Lookahead Dispatch  :   1622.80 ms (10537.7 us/tok |  2.58%)
   LM Head Output Projection    :   3186.01 ms (20688.4 us/tok |  5.07%)
   Foreground NVMe Sync Stall   :    604.28 ms ( 3923.9 us/tok |  0.96%)
   Unaccounted / OMP & Sampling :   1200.53 ms ( 7795.6 us/tok |  1.91%) | Total Wall=62807.99 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    81.29%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     0.51%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.65%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    13.07%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.48%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=8421.14 MB (4058 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=3.25 tps | Avg=3.25 tps | Hit=95.5% | NVMe=912.9 MB/s (13596.60 MB, QD=64) | RSS=14257.9 MB
[LIVE-PREFILL] 512/512 tok | Chunk=3.39 tps | Avg=3.32 tps | Hit=96.9% | NVMe=1027.8 MB/s (17151.58 MB, QD=64) | RSS=14255.2 MB
[LIVE-DECODE] 8/128 tok | Avg=1.75 tps | Hit=96.9% (LA:+0.1%) | NVMe=1052.2 MB/s (18591.91 MB) | RSS=14209.3 MB
[LIVE-DECODE] 16/128 tok | Avg=1.82 tps | Hit=97.0% (LA:+0.1%) | NVMe=1079.1 MB/s (19742.73 MB) | RSS=14179.8 MB
[LIVE-DECODE] 24/128 tok | Avg=1.83 tps | Hit=97.0% (LA:+0.2%) | NVMe=1096.1 MB/s (20841.93 MB) | RSS=14164.8 MB
[LIVE-DECODE] 32/128 tok | Avg=1.86 tps | Hit=97.1% (LA:+0.2%) | NVMe=1125.1 MB/s (21969.92 MB) | RSS=14163.1 MB
[LIVE-DECODE] 40/128 tok | Avg=1.87 tps | Hit=97.1% (LA:+0.2%) | NVMe=1148.9 MB/s (23058.13 MB) | RSS=14152.8 MB
[LIVE-DECODE] 48/128 tok | Avg=1.88 tps | Hit=97.2% (LA:+0.2%) | NVMe=1169.6 MB/s (24122.65 MB) | RSS=14154.4 MB
[LIVE-DECODE] 56/128 tok | Avg=1.89 tps | Hit=97.2% (LA:+0.2%) | NVMe=1195.6 MB/s (25166.91 MB) | RSS=14152.4 MB
[LIVE-DECODE] 64/128 tok | Avg=1.89 tps | Hit=97.2% (LA:+0.2%) | NVMe=1218.8 MB/s (26282.04 MB) | RSS=14152.4 MB
[LIVE-DECODE] 72/128 tok | Avg=1.90 tps | Hit=97.3% (LA:+0.3%) | NVMe=1234.8 MB/s (27443.47 MB) | RSS=14151.1 MB
[LIVE-DECODE] 80/128 tok | Avg=1.85 tps | Hit=97.3% (LA:+0.3%) | NVMe=1240.2 MB/s (28552.29 MB) | RSS=14149.0 MB
[LIVE-DECODE] 88/128 tok | Avg=1.83 tps | Hit=97.3% (LA:+0.3%) | NVMe=1247.3 MB/s (29619.65 MB) | RSS=14151.1 MB
[LIVE-DECODE] 96/128 tok | Avg=1.83 tps | Hit=97.4% (LA:+0.3%) | NVMe=1260.8 MB/s (30774.35 MB) | RSS=14150.7 MB
[LIVE-DECODE] 104/128 tok | Avg=1.83 tps | Hit=97.4% (LA:+0.3%) | NVMe=1267.2 MB/s (31927.50 MB) | RSS=14163.5 MB
[LIVE-DECODE] 112/128 tok | Avg=1.83 tps | Hit=97.4% (LA:+0.3%) | NVMe=1278.5 MB/s (32917.93 MB) | RSS=14151.1 MB
[LIVE-DECODE] 120/128 tok | Avg=1.84 tps | Hit=97.5% (LA:+0.3%) | NVMe=1288.9 MB/s (34056.09 MB) | RSS=14151.1 MB
[LIVE-DECODE] 127/128 tok | Avg=1.84 tps | Hit=97.5% (LA:+0.4%) | NVMe=1293.5 MB/s (35098.77 MB) | RSS=14156.5 MB

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
   LRFU Cache / Staging Ring    : 8421.14 MB (4058/25088 exp = 16.18% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=14156.54 MB | Peak=14479.07 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (127 tok) : "2709
7222221222277222202022222022202272222221222222222222222222222232232223222223332223922222222221
27922722232331222322j222212p"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 128 Steps)]
   Logit Summary: AvgTop1Prob=14.4% | AvgMargin=0.598 | MinMargin=0.006
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      17 | 2              |   11.54 |   5.6% |      22 |   11.02 | 154166.66 |  0 |  0 |  0 |     0.0 |
   |    2 |      22 | 7              |   12.22 |   9.7% |      17 |   11.35 |  627.11 |899 | 61 |  0 | 208239.0 |
   |    3 |      15 | 0              |   12.04 |  16.2% |      18 |   11.66 |  627.11 |  0 |  0 |  0 | 208239.0 |
   |    4 |      24 | 9              |    9.76 |   3.6% |      18 |    9.46 |  573.35 |440 | 40 |  0 | 217818.0 |
   |    5 |     198 | \n             |   10.19 |  12.1% |      17 |    8.96 |  571.46 |466 | 14 |  0 | 150193.0 |
   |    6 |      22 | 7              |    9.69 |   4.0% |      17 |    9.42 |  554.87 |440 | 40 |  0 | 177789.0 |
   |    7 |      17 | 2              |    8.00 |   1.2% |      16 |    7.73 |  545.34 |444 | 36 |  0 | 193914.0 |
   |    8 |      17 | 2              |   10.11 |   6.0% |      18 |    9.42 |  546.00 |468 | 12 |  0 | 153643.0 |
   |   78 |      17 | 2              |   13.61 |  31.2% |      18 |   12.89 |  844.78 |478 |  2 |  0 | 122468.0 |
   |   81 |      18 | 3              |   12.27 |  27.1% |      17 |   12.04 |  810.86 |477 |  3 |  0 | 145118.0 |
   |   82 |      18 | 3              |   11.59 |  16.7% |      17 |   10.59 |  761.78 |474 |  6 |  0 | 139589.0 |
   |   79 |      17 | 2              |   14.75 |  33.9% |      18 |   13.95 |  759.07 |476 |  4 |  0 | 139543.0 |
   |  125 |      17 | 2              |    9.93 |   5.5% |      19 |    9.22 |  518.16 |477 |  3 |  0 | 141793.0 |
   |  126 |      16 | 1              |   10.55 |  10.3% |      15 |   10.48 |  523.64 |474 |  6 |  0 | 122743.0 |
   |  127 |      17 | 2              |   11.23 |   8.7% |      15 |   11.04 |  534.34 |467 | 13 |  0 | 143139.0 |
   |  128 |      79 | p              |    8.80 |   1.3% |      18 |    8.34 |  609.13 |473 |  7 |  0 | 151293.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 154.167s, TTFT=154166.66ms): Avg=3.32 | Min=3.25 | Max=3.39 tps
   Prefill Chunks (2): C1:256t/3.3tps/96% | C2:256t/3.4tps/97%
   Decode  (127 tok, 69.085s): Avg=1.84 | Min=1.18 | Max=2.03 tps
   Latency (ms) : Min=493.14 | P10=511.09 | P25=516.10 | P50=525.20 | P75=540.58 | P90=602.04 | P95=696.99 | P99=810.86 | Max=844.78
   Mean/SD/Jitt : Mean=543.97ms | StdDev=58.91ms | Jitter=22.45ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/127
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (306720): RawRAM=297949 (97.14%) | Lookahead=1117 (+0.36%) | ColdMiss=7654 (2.50%) | EFF HIT=97.50%
   Lookahead    : 10918 prefetched -> 1127 consumed (10.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.0% | @64= 97.2% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 6390 | 5769 |  86 | 535 | 91.6%|1046.12 | | L24 | 6390 | 6294 |   3 |  93 | 98.5%| 250.02 |
   | L01 | 6390 | 6167 |  42 | 181 | 97.2%|1451.81 | | L25 | 6390 | 6293 |  10 |  87 | 98.6%| 257.54 |
   | L02 | 6390 | 6154 |  15 | 221 | 96.5%|1821.02 | | L26 | 6390 | 6199 |  26 | 165 | 97.4%| 511.33 |
   | L03 | 6390 | 6315 |   2 |  73 | 98.9%|2372.41 | | L27 | 6390 | 6272 |  14 | 104 | 98.4%| 485.01 |
   | L04 | 6390 | 6288 |   2 | 100 | 98.4%| 722.17 | | L28 | 6390 | 6161 |  32 | 197 | 96.9%| 618.48 |
   | L05 | 6390 | 6252 |  12 | 126 | 98.0%|1107.25 | | L29 | 6390 | 6200 |  31 | 159 | 97.5%| 403.32 |
   | L06 | 6390 | 6261 |  11 | 118 | 98.2%| 661.72 | | L30 | 6390 | 6112 |  58 | 220 | 96.6%| 577.61 |
   | L07 | 6390 | 6256 |  10 | 124 | 98.1%| 560.96 | | L31 | 6390 | 6127 |  48 | 215 | 96.6%| 518.55 |
   | L08 | 6390 | 6320 |   3 |  67 | 99.0%| 276.42 | | L32 | 6390 | 6203 |  28 | 159 | 97.5%| 678.64 |
   | L09 | 6390 | 6320 |   2 |  68 | 98.9%|  95.87 | | L33 | 6390 | 6171 |  39 | 180 | 97.2%| 422.05 |
   | L10 | 6390 | 6294 |   4 |  92 | 98.6%| 141.94 | | L34 | 6390 | 6083 |  67 | 240 | 96.2%| 579.05 |
   | L11 | 6390 | 6319 |   3 |  68 | 98.9%| 179.30 | | L35 | 6390 | 6215 |  19 | 156 | 97.6%| 373.07 |
   | L12 | 6390 | 6283 |   3 | 104 | 98.4%| 603.44 | | L36 | 6390 | 6197 |  23 | 170 | 97.3%| 458.06 |
   | L13 | 6390 | 6261 |  14 | 115 | 98.2%| 282.32 | | L37 | 6390 | 6206 |  26 | 158 | 97.5%| 464.33 |
   | L14 | 6390 | 6249 |  24 | 117 | 98.2%| 501.27 | | L38 | 6390 | 6266 |   9 | 115 | 98.2%| 761.35 |
   | L15 | 6390 | 6211 |  18 | 161 | 97.5%| 428.61 | | L39 | 6390 | 6216 |  11 | 163 | 97.4%| 701.20 |
   | L16 | 6390 | 6207 |   8 | 175 | 97.3%| 406.05 | | L40 | 6390 | 6218 |  33 | 139 | 97.8%| 729.39 |
   | L17 | 6390 | 6187 |  11 | 192 | 97.0%| 479.37 | | L41 | 6390 | 6224 |  16 | 150 | 97.7%| 290.97 |
   | L18 | 6390 | 6205 |  16 | 169 | 97.4%| 406.05 | | L42 | 6390 | 6106 |  56 | 228 | 96.4%| 737.50 |
   | L19 | 6390 | 6248 |  10 | 132 | 97.9%| 344.26 | | L43 | 6390 | 6123 |  42 | 225 | 96.5%| 617.94 |
   | L20 | 6390 | 6138 |  15 | 237 | 96.3%| 956.45 | | L44 | 6390 | 6121 |  51 | 218 | 96.6%| 600.66 |
   | L21 | 6390 | 6168 |  17 | 205 | 96.8%|1158.01 | | L45 | 6390 | 6065 |  93 | 232 | 96.4%| 858.50 |
   | L22 | 6390 | 6293 |   4 |  93 | 98.5%| 434.25 | | L46 | 6390 | 6267 |  22 | 101 | 98.4%| 962.21 |
   | L23 | 6390 | 6212 |  19 | 159 | 97.5%| 604.98 | | L47 | 6390 | 6233 |   9 | 148 | 97.7%| 494.41 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 35098.77 MB (Load=4614.69 | Prefill=12536.88 | Warmup=0.00 | Decode=17947.19 MB)
   SSD Data/Token (Decode)      : Avg=141.316 MB/tok (Min=99.188 | P50=138.222 | P95=175.014 | Max=212.713 MB) | Prefill=24.486 MB/tok
   NVMe Batches / Requests      : 5059 Batches | 67048 Raw -> 65368 Merged (1680 LBA Merges, Avg 549.8 KB/io)
   SSD I/O Size Histogram       : <64K=10481 | 64K-512K=15396 | 512K-2M=39049 | >2M=442
   SSD Read Bandwidth (Active)  : Min=1.21 | Avg=1293.51 | Peak=9657.59 MB/s | WallAmort=157.22 MB/s
   OS Kernel I/O Verification   : Read=35114.32 MB | Write=0.00 MB | Syscalls=74883
   Sync Stall vs Async DMA      : SyncStall=5450.29 ms | AsyncOverlapped=16336.65 ms (75.0% Overlapped)
   RAM Traffic & Active BW      : 2226.07 GB moved | Active=10.69 GB/s | WallAmort=9.97 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=154.17s (69.1%, 12536.88 MB SSD) | Decode=69.08s (30.9%, 17947.19 MB SSD)
   CPU Time & Utilization       : User=696.781s + Sys=28.797s (Wall=239.205s) | SysUtil=75.8% | ThrUtil=75.8% | 70.14 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 104440.44 ms (163443.6 us/tok | 46.78%)
   MoE AVX2 Q8 Expert Compute   :  98796.51 ms (154611.1 us/tok | 44.25%)
   Router + Lookahead Dispatch  :   5846.60 ms ( 9149.6 us/tok |  2.62%)
   LM Head Output Projection    :   4964.00 ms ( 7768.4 us/tok |  2.22%)
   Foreground NVMe Sync Stall   :   5450.29 ms ( 8529.4 us/tok |  2.44%)
   Unaccounted / OMP & Sampling :   3753.50 ms ( 5874.0 us/tok |  1.68%) | Total Wall=223251.35 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    76.48%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.53%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.17%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    13.88%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.94%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 17975.8ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\n\n\n\n\n\n\n\n\n\n\n\n\n\n1\n'
[Stage 3] /v1/chat/completions (stream=true SSE) 6332.2ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7458.25 MB (3594 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3.32 tps | Avg=3.32 tps | Hit=95.4% | NVMe=969.1 MB/s (13785.34 MB, QD=64) | RSS=13296.5 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=3.40 tps | Avg=3.36 tps | Hit=96.6% | NVMe=1123.3 MB/s (18190.57 MB, QD=64) | RSS=13296.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=3.38 tps | Avg=3.36 tps | Hit=97.1% | NVMe=1240.6 MB/s (22243.29 MB, QD=64) | RSS=13296.6 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=3.35 tps | Avg=3.36 tps | Hit=97.3% | NVMe=1336.4 MB/s (26270.16 MB, QD=64) | RSS=13297.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=3.33 tps | Avg=3.36 tps | Hit=97.5% | NVMe=1419.1 MB/s (30169.43 MB, QD=64) | RSS=13296.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=3.31 tps | Avg=3.35 tps | Hit=97.6% | NVMe=1493.1 MB/s (34071.32 MB, QD=64) | RSS=13297.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=3.29 tps | Avg=3.34 tps | Hit=97.6% | NVMe=1554.0 MB/s (37985.28 MB, QD=64) | RSS=13296.7 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=3.26 tps | Avg=3.33 tps | Hit=97.7% | NVMe=1603.3 MB/s (41748.61 MB, QD=64) | RSS=13297.9 MB
[LIVE-DECODE] 8/64 tok | Avg=1.65 tps | Hit=97.7% (LA:+0.0%) | NVMe=1603.4 MB/s (43411.55 MB) | RSS=13304.9 MB
[LIVE-DECODE] 16/64 tok | Avg=1.70 tps | Hit=97.7% (LA:+0.0%) | NVMe=1606.9 MB/s (44820.37 MB) | RSS=13304.9 MB
[LIVE-DECODE] 24/64 tok | Avg=1.73 tps | Hit=97.7% (LA:+0.1%) | NVMe=1612.4 MB/s (46139.48 MB) | RSS=13302.8 MB
[LIVE-DECODE] 32/64 tok | Avg=1.74 tps | Hit=97.7% (LA:+0.1%) | NVMe=1617.0 MB/s (47382.70 MB) | RSS=13302.6 MB
[LIVE-DECODE] 40/64 tok | Avg=1.75 tps | Hit=97.7% (LA:+0.1%) | NVMe=1621.2 MB/s (48669.10 MB) | RSS=13295.1 MB
[LIVE-DECODE] 48/64 tok | Avg=1.75 tps | Hit=97.7% (LA:+0.1%) | NVMe=1628.1 MB/s (49922.31 MB) | RSS=13281.8 MB
[LIVE-DECODE] 56/64 tok | Avg=1.76 tps | Hit=97.8% (LA:+0.1%) | NVMe=1631.1 MB/s (51276.47 MB) | RSS=13267.9 MB
[LIVE-DECODE] 63/64 tok | Avg=1.76 tps | Hit=97.8% (LA:+0.1%) | NVMe=1632.6 MB/s (52637.35 MB) | RSS=13262.1 MB

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
   LRFU Cache / Staging Ring    : 7458.25 MB (3594/25088 exp = 14.33% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.75 MB | End=13262.09 MB | Peak=13533.90 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (63 tok) : "
221221121221
2223722212221722120722212222272227121222272777d77a"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=11.7% | AvgMargin=0.454 | MinMargin=0.008
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     198 | \n             |    7.38 |   0.7% |      17 |    7.24 | 615230.27 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    8.65 |   1.9% |      22 |    8.24 |  666.44 |852 |108 |  0 | 263714.0 |
   |    3 |      17 | 2              |   12.45 |  20.9% |      18 |   11.82 |  666.44 |  0 |  0 |  0 | 263714.0 |
   |    4 |      16 | 1              |   10.53 |   8.3% |      17 |   10.14 |  615.14 |448 | 32 |  0 | 205068.0 |
   |    5 |      17 | 2              |   11.00 |   7.6% |      15 |   10.61 |  590.20 |437 | 43 |  0 | 207814.0 |
   |    6 |      17 | 2              |   10.56 |  11.0% |      16 |   10.50 |  592.28 |445 | 35 |  0 | 209668.0 |
   |    7 |      16 | 1              |    8.55 |   2.2% |      15 |    8.11 |  580.67 |464 | 16 |  0 | 165718.0 |
   |    8 |      16 | 1              |   10.85 |  16.6% |      17 |   10.31 |  575.24 |447 | 33 |  0 | 186664.0 |
   |   10 |      16 | 1              |   10.43 |   9.8% |      17 |   10.35 |  612.18 |458 | 22 |  0 | 178089.0 |
   |   15 |      17 | 2              |    9.13 |   5.3% |     198 |    8.72 |  586.01 |426 | 54 |  0 | 226664.0 |
   |   44 |      22 | 7              |   10.66 |  11.5% |      17 |    9.77 |  585.12 |466 | 14 |  0 | 167593.0 |
   |   60 |      22 | 7              |   13.90 |  27.1% |      18 |   13.41 |  584.93 |450 | 30 |  0 | 205764.0 |
   |   61 |      67 | d              |   12.02 |   7.7% |      64 |   11.63 |  579.06 |448 | 32 |  0 | 221039.0 |
   |   62 |      22 | 7              |   13.02 |  18.4% |      20 |   12.37 |  576.33 |462 | 18 |  0 | 174414.0 |
   |   63 |      22 | 7              |   16.44 |  44.2% |      20 |   15.12 |  559.67 |463 | 17 |  0 | 173039.0 |
   |   64 |      64 | a              |   10.35 |   4.4% |      77 |   10.10 |  573.64 |451 | 29 |  0 | 227139.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 615.230s, TTFT=615230.27ms): Avg=3.33 | Min=3.26 | Max=3.40 tps
   Prefill Chunks (8): C1:256t/3.3tps/95% | C2:256t/3.4tps/97% | C3:256t/3.4tps/97% | C4:256t/3.4tps/97%
                       C5:256t/3.3tps/97% | C6:256t/3.3tps/98% | C7:256t/3.3tps/98% | C8:256t/3.3tps/98%
   Decode  (63 tok, 35.836s): Avg=1.76 | Min=1.50 | Max=1.83 tps
   Latency (ms) : Min=546.81 | P10=551.98 | P25=556.12 | P50=562.88 | P75=573.64 | P90=586.01 | P95=612.18 | P99=666.44 | Max=666.44
   Mean/SD/Jitt : Mean=568.83ms | StdDev=22.40ms | Jitter=10.81ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1013280): RawRAM=989335 (97.64%) | Lookahead=1245 (+0.12%) | ColdMiss=22700 (2.24%) | EFF HIT=97.76%
   Lookahead    : 6593 prefetched -> 1255 consumed (19.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.7% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21110 |19023 |  97 |1990 | 90.6%|3515.70 | | L24 |21110 |20928 |   6 | 176 | 99.2%| 396.66 |
   | L01 |21110 |20546 |  38 | 526 | 97.5%|1257.57 | | L25 |21110 |20927 |   7 | 176 | 99.2%| 359.06 |
   | L02 |21110 |20501 |  14 | 595 | 97.2%|1682.89 | | L26 |21110 |20575 |  24 | 511 | 97.6%|1221.92 |
   | L03 |21110 |21032 |   1 |  77 | 99.6%|1035.82 | | L27 |21110 |20824 |  18 | 268 | 98.7%| 635.40 |
   | L04 |21110 |20881 |   7 | 222 | 98.9%| 774.05 | | L28 |21110 |20473 |  25 | 612 | 97.1%|1355.40 |
   | L05 |21110 |20801 |  19 | 290 | 98.6%|1017.02 | | L29 |21110 |20643 |  21 | 446 | 97.9%| 754.79 |
   | L06 |21110 |20817 |  30 | 263 | 98.8%| 838.43 | | L30 |21110 |20239 |  51 | 820 | 96.1%|1342.48 |
   | L07 |21110 |20818 |  22 | 270 | 98.7%| 534.01 | | L31 |21110 |20348 |  42 | 720 | 96.6%|1209.96 |
   | L08 |21110 |21038 |   1 |  71 | 99.7%| 155.64 | | L32 |21110 |20569 |  21 | 520 | 97.5%|1205.00 |
   | L09 |21110 |21035 |   0 |  75 | 99.6%|  95.87 | | L33 |21110 |20444 |  39 | 627 | 97.0%|1052.95 |
   | L10 |21110 |20935 |   4 | 171 | 99.2%| 232.84 | | L34 |21110 |20190 |  55 | 865 | 95.9%|1414.50 |
   | L11 |21110 |21036 |   1 |  73 | 99.7%| 120.78 | | L35 |21110 |20616 |  33 | 461 | 97.8%| 815.28 |
   | L12 |21110 |20975 |   2 | 133 | 99.4%| 443.65 | | L36 |21110 |20556 |  41 | 513 | 97.6%| 917.55 |
   | L13 |21110 |20877 |   6 | 227 | 98.9%| 394.68 | | L37 |21110 |20512 |  24 | 574 | 97.3%|1197.49 |
   | L14 |21110 |20779 |  44 | 287 | 98.6%| 701.49 | | L38 |21110 |20750 |  13 | 347 | 98.4%| 894.82 |
   | L15 |21110 |20631 |  43 | 436 | 97.9%|1009.50 | | L39 |21110 |20565 |  30 | 515 | 97.6%|1255.76 |
   | L16 |21110 |20563 |  20 | 527 | 97.5%|1099.73 | | L40 |21110 |20673 |  29 | 408 | 98.1%|1035.82 |
   | L17 |21110 |20407 |  22 | 681 | 96.8%|1479.47 | | L41 |21110 |20656 |  15 | 439 | 97.9%| 741.82 |
   | L18 |21110 |20456 |  37 | 617 | 97.1%|1306.52 | | L42 |21110 |20358 |  38 | 714 | 96.6%|1271.90 |
   | L19 |21110 |20661 |  36 | 413 | 98.0%| 711.57 | | L43 |21110 |20261 |  33 | 816 | 96.1%|1424.58 |
   | L20 |21110 |20295 |  44 | 771 | 96.3%|1426.03 | | L44 |21110 |20264 |  40 | 806 | 96.2%|1325.20 |
   | L21 |21110 |20427 |  37 | 646 | 96.9%|1812.21 | | L45 |21110 |20321 |  54 | 735 | 96.5%|1387.13 |
   | L22 |21110 |20907 |  10 | 193 | 99.1%| 496.29 | | L46 |21110 |20882 |  10 | 218 | 99.0%| 620.83 |
   | L23 |21110 |20550 |  28 | 532 | 97.5%|1070.24 | | L47 |21110 |20770 |  13 | 327 | 98.5%| 789.55 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 52637.35 MB (Load=4614.69 | Prefill=37133.91 | Warmup=0.00 | Decode=10888.75 MB)
   SSD Data/Token (Decode)      : Avg=172.837 MB/tok (Min=130.336 | P50=168.983 | P95=216.347 | Max=257.533 MB) | Prefill=18.132 MB/tok
   NVMe Batches / Requests      : 3779 Batches | 122763 Raw -> 118378 Merged (4385 LBA Merges, Avg 455.3 KB/io)
   SSD I/O Size Histogram       : <64K=33825 | 64K-512K=21873 | 512K-2M=62189 | >2M=491
   SSD Read Bandwidth (Active)  : Min=0.85 | Avg=1632.62 | Peak=9620.69 MB/s | WallAmort=80.85 MB/s
   OS Kernel I/O Verification   : Read=52657.89 MB | Write=0.00 MB | Syscalls=127891
   Sync Stall vs Async DMA      : SyncStall=14042.00 ms | AsyncOverlapped=21540.58 ms (60.5% Overlapped)
   RAM Traffic & Active BW      : 5635.43 GB moved | Active=9.20 GB/s | WallAmort=8.66 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=615.23s (94.5%, 37133.91 MB SSD) | Decode=35.84s (5.5%, 10888.75 MB SSD)
   CPU Time & Utilization       : User=2244.953s + Sys=39.500s (Wall=666.329s) | SysUtil=85.7% | ThrUtil=85.7% | 79.28 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 300570.55 ms (142383.0 us/tok | 46.17%)
   MoE AVX2 Q8 Expert Compute   : 309593.00 ms (146657.0 us/tok | 47.55%)
   Router + Lookahead Dispatch  :  18604.02 ms ( 8812.9 us/tok |  2.86%)
   LM Head Output Projection    :   2412.17 ms ( 1142.7 us/tok |  0.37%)
   Foreground NVMe Sync Stall   :  14042.00 ms ( 6651.8 us/tok |  2.16%)
   Unaccounted / OMP & Sampling :   5844.87 ms ( 2768.8 us/tok |  0.90%) | Total Wall=651066.61 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    76.54%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.04%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.17%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    15.53%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.72%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=57.0s | Competitor drastic-underperform cutoff=285.0s (5x Apex)
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=285.0s) ===
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
  [Colibri-Qwen38] resident weights loaded in 11.4s | RSS after load: 4.60 GB
  [Colibri-Qwen38] [qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=285.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.1s / cutoff=285.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=285.0s
  [Colibri-Qwen38] TTFT: 22.32 s (time to first token)
  [Colibri-Qwen38] [qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
  [Colibri-Qwen38] [qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
  [Colibri-Qwen38] [qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes
  [Colibri-Qwen38] 
  [Colibri-Qwen38] PEAK RSS: 10.72 GB
  [Colibri-Qwen38] Expert cache hit rate: 62.0% (hit=15849 miss=9733)
  [Colibri-Qwen38] Speed: 0.74 tok/s (43.2s for 32 tokens)
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
=== [Colibri-Qwen38] Finished rc=1 elapsed=57.66s cancelled=False ===
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 2.75 | 1.85 | 521.68 | 92.00% | 942.82 | 14033.30 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 3.32 | 1.84 | 525.20 | 97.50% | 1293.51 | 14479.07 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 3.33 | 1.76 | 562.88 | 97.76% | 1632.62 | 13533.90 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.74 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
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
   System Memory (RAM): 15.99 GB Total / 13.46 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    430.00 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1623.86 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7844.96 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10492.75 MB/s
   RND4K Q32T16 Read                  :    484.50 MB/s (  124033 IOPS)
   RND4K Q1T1  Read                   :    664.32 MB/s (Latency: 5.88 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     58.30 GB/s
   AVX2 256-bit Sequential Write BW   :     40.06 GB/s
   STREAM Triad (A = B + s*C) BW      :     34.95 GB/s
   Random Pointer-Chase Latency       :     51.85 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     50.96 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    101.03 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     18.95 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1423.48 tps | Avg=1423.48 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=60.5 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1235.44 tps | Avg=1322.81 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=60.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1116.87 tps | Avg=1246.22 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=61.1 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=964.12 tps | Avg=1161.27 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=61.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=900.95 tps | Avg=1097.83 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=61.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=806.78 tps | Avg=1035.57 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=61.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=755.78 tps | Avg=983.55 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=62.1 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=691.58 tps | Avg=934.25 tps | Hit=100.0% | NVMe=2558.3 MB/s (6.58 MB, QD=64) | RSS=62.4 MB
[LIVE-DECODE] 8/32 tok | Avg=196.08 tps | Hit=100.0% (LA:+0.0%) | NVMe=2558.3 MB/s (6.58 MB) | RSS=62.4 MB
[LIVE-DECODE] 16/32 tok | Avg=196.73 tps | Hit=100.0% (LA:+0.0%) | NVMe=2558.3 MB/s (6.58 MB) | RSS=62.4 MB
[LIVE-DECODE] 24/32 tok | Avg=197.15 tps | Hit=100.0% (LA:+0.0%) | NVMe=2558.3 MB/s (6.58 MB) | RSS=62.4 MB
[LIVE-DECODE] 32/32 tok | Avg=197.00 tps | Hit=100.0% (LA:+0.0%) | NVMe=2558.3 MB/s (6.58 MB) | RSS=62.4 MB

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
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=62.41 MB | Peak=62.41 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2192.14 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.08 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.08 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.05 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.05 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.16 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.16 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.10 | 12 |  0 |  0 |     0.0 |
   |   28 |     246 | tok_246        |  194.87 | 100.0% |      54 |  173.43 |    5.13 | 12 |  0 |  0 |     0.0 |
   |   29 |     229 | tok_229        |  172.54 | 100.0% |      70 |  154.16 |    5.13 |  0 |  0 |  0 |     0.0 |
   |   12 |      86 | tok_86         |  168.49 |  89.7% |     246 |  166.31 |    5.10 | 12 |  0 |  0 |     0.0 |
   |   13 |      68 | tok_68         |  148.39 | 100.0% |     104 |  119.46 |    5.10 |  0 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.08 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.08 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.06 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.06 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.192s, TTFT=2192.14ms): Avg=934.25 | Min=691.58 | Max=1423.48 tps
   Prefill Chunks (8): C1:256t/1423.5tps/100% | C2:256t/1235.4tps/100% | C3:256t/1116.9tps/100% | C4:256t/964.1tps/100%
                       C5:256t/901.0tps/100% | C6:256t/806.8tps/100% | C7:256t/755.8tps/100% | C8:256t/691.6tps/100%
   Decode  (32 tok, 0.162s): Avg=197.00 | Min=193.72 | Max=198.98 tps
   Latency (ms) : Min=5.03 | P10=5.04 | P25=5.05 | P50=5.08 | P75=5.10 | P90=5.13 | P95=5.16 | P99=5.16 | Max=5.16
   Mean/SD/Jitt : Mean=5.08ms | StdDev=0.03ms | Jitter=0.02ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=247.52 | Avg=2558.28 | Peak=6443.30 MB/s | WallAmort=2.79 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=1.22 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.41 GB moved | Active=0.63 GB/s | WallAmort=0.60 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.19s (93.1%, 0.00 MB SSD) | Decode=0.16s (6.9%, 0.00 MB SSD)
   CPU Time & Utilization       : User=2.938s + Sys=0.734s (Wall=2.371s) | SysUtil=38.7% | ThrUtil=38.7% | 35.82 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   1983.01 ms (  953.4 us/tok | 84.22%)
   MoE AVX2 Q8 Expert Compute   :    249.12 ms (  119.8 us/tok | 10.58%)
   Router + Lookahead Dispatch  :     59.48 ms (   28.6 us/tok |  2.53%)
   LM Head Output Projection    :      5.71 ms (    2.7 us/tok |  0.24%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     57.26 ms (   27.5 us/tok |  2.43%) | Total Wall=2354.58 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    16.56%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.15%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.09%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    79.20%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.00%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1881.55 tps | Avg=1881.55 tps | Hit=99.2% | NVMe=2630.7 MB/s (24.91 MB, QD=64) | RSS=85.7 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1839.90 tps | Avg=1860.49 tps | Hit=99.2% | NVMe=3642.9 MB/s (42.92 MB, QD=64) | RSS=85.9 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1698.00 tps | Avg=1802.98 tps | Hit=99.2% | NVMe=4227.4 MB/s (61.04 MB, QD=64) | RSS=86.2 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1583.47 tps | Avg=1742.59 tps | Hit=99.2% | NVMe=4672.8 MB/s (79.10 MB, QD=64) | RSS=86.5 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1532.98 tps | Avg=1696.20 tps | Hit=99.2% | NVMe=5003.8 MB/s (97.14 MB, QD=64) | RSS=87.0 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1437.07 tps | Avg=1646.71 tps | Hit=99.2% | NVMe=5240.8 MB/s (115.20 MB, QD=64) | RSS=87.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1319.63 tps | Avg=1590.40 tps | Hit=99.2% | NVMe=5455.6 MB/s (133.27 MB, QD=64) | RSS=87.9 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1284.94 tps | Avg=1544.50 tps | Hit=99.2% | NVMe=5675.4 MB/s (151.30 MB, QD=64) | RSS=88.2 MB
[LIVE-DECODE] 8/32 tok | Avg=177.42 tps | Hit=99.2% (LA:+0.0%) | NVMe=5570.0 MB/s (152.70 MB) | RSS=88.3 MB
[LIVE-DECODE] 16/32 tok | Avg=178.05 tps | Hit=99.2% (LA:+0.1%) | NVMe=5518.3 MB/s (153.28 MB) | RSS=88.3 MB
[LIVE-DECODE] 24/32 tok | Avg=178.14 tps | Hit=99.2% (LA:+0.1%) | NVMe=5423.9 MB/s (154.23 MB) | RSS=88.3 MB
[LIVE-DECODE] 32/32 tok | Avg=178.43 tps | Hit=99.2% (LA:+0.1%) | NVMe=5333.8 MB/s (155.30 MB) | RSS=88.3 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=88.26 MB | Peak=88.26 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1325.99 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    5.69 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    5.69 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    5.58 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    5.58 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    5.63 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    5.63 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    5.66 | 16 |  0 |  0 |    32.0 |
   |   28 |      49 | qtok_49        |   65.10 | 100.0% |      18 |   55.78 |    5.66 | 10 |  6 |  0 |   198.5 |
   |   29 |     148 | qtok_148       |   77.89 | 100.0% |     127 |   51.09 |    5.66 |  0 |  0 |  0 |   198.5 |
   |    9 |      49 | qtok_49        |   84.72 | 100.0% |     129 |   76.64 |    5.66 |  0 |  0 |  0 |    32.0 |
   |   10 |     254 | qtok_254       |   70.81 |  99.7% |      66 |   64.77 |    5.64 | 15 |  1 |  0 |    59.8 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.55 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.55 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.56 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.56 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.326s, TTFT=1325.99ms): Avg=1544.50 | Min=1284.94 | Max=1881.55 tps
   Prefill Chunks (8): C1:256t/1881.5tps/99% | C2:256t/1839.9tps/99% | C3:256t/1698.0tps/99% | C4:256t/1583.5tps/99%
                       C5:256t/1533.0tps/99% | C6:256t/1437.1tps/99% | C7:256t/1319.6tps/99% | C8:256t/1284.9tps/99%
   Decode  (32 tok, 0.179s): Avg=178.43 | Min=175.87 | Max=180.68 tps
   Latency (ms) : Min=5.53 | P10=5.55 | P25=5.57 | P50=5.62 | P75=5.64 | P90=5.66 | P95=5.69 | P99=5.69 | Max=5.69
   Mean/SD/Jitt : Mean=5.60ms | StdDev=0.04ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=453.93 | Avg=5333.82 | Peak=11397.55 MB/s | WallAmort=103.17 MB/s
   OS Kernel I/O Verification   : Read=24.47 MB | Write=0.00 MB | Syscalls=391
   Sync Stall vs Async DMA      : SyncStall=5.80 ms | AsyncOverlapped=27.10 ms (82.4% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.60 GB/s | WallAmort=1.40 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.33s (88.1%, 144.44 MB SSD) | Decode=0.18s (11.9%, 4.00 MB SSD)
   CPU Time & Utilization       : User=2.812s + Sys=0.500s (Wall=1.538s) | SysUtil=53.9% | ThrUtil=53.9% | 49.81 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    933.76 ms (  448.9 us/tok | 62.03%)
   MoE AVX2 Q8 Expert Compute   :    375.65 ms (  180.6 us/tok | 24.95%)
   Router + Lookahead Dispatch  :     81.78 ms (   39.3 us/tok |  5.43%)
   LM Head Output Projection    :      5.86 ms (    2.8 us/tok |  0.39%)
   Foreground NVMe Sync Stall   :      5.80 ms (    2.8 us/tok |  0.39%)
   Unaccounted / OMP & Sampling :    102.48 ms (   49.3 us/tok |  6.81%) | Total Wall=1505.34 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    17.72%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     5.85%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.86%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    70.09%  |
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
  "kv_cache_ram_bytes": 10797056,
  "kv_bytes_per_token": 2560,
  "expert_cache_ram_bytes": 2534400,
  "ssd_offloaded_expert_bytes": 2433024,
  "prefill": {
    "tokens": 164,
    "ttft_ms": 237.77,
    "avg_tps": 689.75,
    "min_tps": 564.19,
    "max_tps": 784.91
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 143.26,
    "min_tps": 129.12,
    "max_tps": 146.89,
    "p50_ms": 6.91,
    "p90_ms": 7.26,
    "p99_ms": 7.74,
    "mean_ms": 6.98,
    "jitter_ms": 0.16
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
    "avg_mbs": 2606.72,
    "peak_mbs": 5813.95,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 0.86
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
    "dense_attention": 381.3,
    "moe_compute": 106.07,
    "router_lookahead": 7.25,
    "lm_head": 8.97,
    "unaccounted": 6.41
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 88.25,
    "ram_bandwidth_pinning": 1.92,
    "expert_cache_lrfu": 8.03,
    "lookahead_parallel_overlap": 1.44,
    "ssd_nvme_throughput": 0.36,
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
    "ttft_ms": 307.15,
    "avg_tps": 533.95,
    "min_tps": 378.06,
    "max_tps": 613.33
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 123.08,
    "min_tps": 98.61,
    "max_tps": 129.4,
    "p50_ms": 7.89,
    "p90_ms": 9.0,
    "p99_ms": 10.14,
    "mean_ms": 8.12,
    "jitter_ms": 0.25
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
    "avg_mbs": 2682.39,
    "peak_mbs": 9432.87,
    "sync_wait_ms": 4.57,
    "async_overlap_ms": 12.34
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
    "dense_attention": 355.28,
    "moe_compute": 203.06,
    "router_lookahead": 9.2,
    "lm_head": 8.94,
    "unaccounted": 42.96
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 82.66,
    "ram_bandwidth_pinning": 2.14,
    "expert_cache_lrfu": 8.17,
    "lookahead_parallel_overlap": 4.39,
    "ssd_nvme_throughput": 2.64,
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
   System Memory (RAM): 15.99 GB Total / 13.45 GB Available
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    495.52 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1469.92 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   8190.95 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10639.14 MB/s
   RND4K Q32T16 Read                  :    481.64 MB/s (  123300 IOPS)
   RND4K Q1T1  Read                   :    742.78 MB/s (Latency: 5.26 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     60.72 GB/s
   AVX2 256-bit Sequential Write BW   :     49.87 GB/s
   STREAM Triad (A = B + s*C) BW      :     41.33 GB/s
   Random Pointer-Chase Latency       :     51.89 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.03 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    183.09 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     21.47 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 31.00 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 133.65 MB/s (7.66s)
   Window #01 (256.0 MB in 0.50s):   511.38 MB/s (Uncached Direct Read)
   Window #02 (244.0 MB in 0.53s):   458.53 MB/s (Uncached Direct Read)
   Window #03 (196.0 MB in 0.51s):   386.85 MB/s (Uncached Direct Read)
   Window #04 (216.0 MB in 0.55s):   390.73 MB/s (Uncached Direct Read)
   Window #05 (112.0 MB in 0.24s):   457.54 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   438.16 MB/s (Min=386.85 | Max=511.38 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 397.55 MB/s (2.58s)
   Window #01 (184.0 MB in 0.50s):   366.73 MB/s (Uncached Direct Read)
   Window #02 (196.0 MB in 0.50s):   389.35 MB/s (Uncached Direct Read)
   Window #03 (216.0 MB in 0.55s):   392.32 MB/s (Uncached Direct Read)
   Window #04 (220.0 MB in 0.54s):   408.96 MB/s (Uncached Direct Read)
   Window #05 (196.0 MB in 0.50s):   388.26 MB/s (Uncached Direct Read)
   Window #06 ( 12.0 MB in 0.00s):  2649.24 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   393.39 MB/s (Min=366.73 | Max=2649.24 MB/s)
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
   CPU Model          : AMD EPYC 7763 64-Core Processor                
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=NO
   System Memory (RAM): 15.99 GB Total / 14.74 GB Available
   Active Drive Space : 150.00 GB Total / 76.31 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    447.53 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :   1515.50 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   7953.47 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :  10172.58 MB/s
   RND4K Q32T16 Read                  :    420.33 MB/s (  107603 IOPS)
   RND4K Q1T1  Read                   :    439.30 MB/s (Latency: 8.89 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     62.67 GB/s
   AVX2 256-bit Sequential Write BW   :     51.77 GB/s
   STREAM Triad (A = B + s*C) BW      :     44.13 GB/s
   Random Pointer-Chase Latency       :     47.84 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     51.39 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    191.26 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     20.65 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=3.88 tps | Avg=3.88 tps | Hit=91.8% | NVMe=477.1 MB/s (5364.89 MB, QD=64) | RSS=14219.6 MB

 >>> [Apex-Model-Response] !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
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
   LRFU Cache / Staging Ring    : 8483.40 MB (4088/25088 exp = 16.29% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=14235.63 MB | Peak=14475.04 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (91 tok)   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
   RESPONSE (63 tok) : "!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=100.0% | AvgMargin=0.000 | MinMargin=1000000000.000
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |       0 | !              |     nan | 100.0% |       1 |     nan | 23434.55 |  0 |  0 |  0 |     0.0 |
   |    2 |       0 | !              |     nan | 100.0% |       1 |     nan |  817.94 |952 |  8 |  0 | 39476.5 |
   |    3 |       0 | !              |     nan | 100.0% |       1 |     nan |  817.94 |  0 |  0 |  0 | 39476.5 |
   |    4 |       0 | !              |     nan | 100.0% |       1 |     nan |  656.28 |480 |  0 |  0 |    64.0 |
   |    5 |       0 | !              |     nan | 100.0% |       1 |     nan |  687.62 |479 |  1 |  0 |  3064.0 |
   |    6 |       0 | !              |     nan | 100.0% |       1 |     nan |  656.55 |480 |  0 |  0 |  1339.0 |
   |    7 |       0 | !              |     nan | 100.0% |       1 |     nan |  670.73 |480 |  0 |  0 |    64.0 |
   |    8 |       0 | !              |     nan | 100.0% |       1 |     nan |  666.56 |480 |  0 |  0 |    64.0 |
   |   23 |       0 | !              |     nan | 100.0% |       1 |     nan |  689.06 |480 |  0 |  0 |    64.0 |
   |   32 |       0 | !              |     nan | 100.0% |       1 |     nan |  688.00 |480 |  0 |  0 |    64.0 |
   |   27 |       0 | !              |     nan | 100.0% |       1 |     nan |  686.62 |480 |  0 |  0 |    64.0 |
   |   30 |       0 | !              |     nan | 100.0% |       1 |     nan |  686.03 |480 |  0 |  0 |    64.0 |
   |   61 |       0 | !              |     nan | 100.0% |       1 |     nan |  483.38 |480 |  0 |  0 |    64.0 |
   |   62 |       0 | !              |     nan | 100.0% |       1 |     nan |  484.15 |480 |  0 |  0 |    64.0 |
   |   63 |       0 | !              |     nan | 100.0% |       1 |     nan |  481.59 |480 |  0 |  0 |    64.0 |
   |   64 |       0 | !              |     nan | 100.0% |       1 |     nan |  482.12 |480 |  0 |  0 |    64.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 23.435s, TTFT=23434.55ms): Avg=3.88 | Min=3.88 | Max=3.88 tps
   Prefill Chunks (1): C1:91t/3.9tps/92%
   Decode  (63 tok, 39.373s): Avg=1.60 | Min=1.22 | Max=2.13 tps
   Latency (ms) : Min=470.46 | P10=483.76 | P25=549.24 | P50=659.82 | P75=675.34 | P90=686.03 | P95=688.00 | P99=817.94 | Max=817.94
   Mean/SD/Jitt : Mean=624.98ms | StdDev=85.80ms | Jitter=17.08ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (35877): RawRAM=35404 (98.68%) | Lookahead=9 (+0.03%) | ColdMiss=464 (1.29%) | EFF HIT=98.71%
   Lookahead    : 23 prefetched -> 10 consumed (43.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1266 |   9 | 265 | 82.8%| 461.57 | | L24 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L01 |  946 |  865 |   0 |  81 | 91.4%| 117.04 | | L25 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L02 |  946 |  873 |   0 |  73 | 92.3%| 122.97 | | L26 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L03 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L27 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L04 |  721 |  720 |   0 |   1 | 99.9%|   2.08 | | L28 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L05 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L29 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L06 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L30 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L07 |  721 |  720 |   0 |   1 | 99.9%|   1.68 | | L31 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L08 |  721 |  720 |   0 |   1 | 99.9%|   1.25 | | L32 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L09 |  721 |  720 |   0 |   1 | 99.9%|   1.25 | | L33 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L10 |  721 |  720 |   0 |   1 | 99.9%|   1.25 | | L34 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L11 |  721 |  720 |   0 |   1 | 99.9%|   1.25 | | L35 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L12 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L36 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L13 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L37 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L14 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L38 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L15 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L39 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L16 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L40 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   | L17 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L41 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L18 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L42 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L19 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L43 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L20 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L44 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L21 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L45 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L22 |  721 |  720 |   0 |   1 | 99.9%|   1.88 | | L46 |  721 |  720 |   0 |   1 | 99.9%|   1.44 |
   | L23 |  721 |  720 |   0 |   1 | 99.9%|   1.44 | | L47 |  721 |  720 |   0 |   1 | 99.9%|   1.88 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 5449.98 MB (Load=4614.69 | Prefill=750.20 | Warmup=0.00 | Decode=85.09 MB)
   SSD Data/Token (Decode)      : Avg=1.351 MB/tok (Min=0.062 | P50=0.062 | P95=0.062 | Max=38.551 MB) | Prefill=8.244 MB/tok
   NVMe Batches / Requests      : 127 Batches | 5060 Raw -> 4853 Merged (207 LBA Merges, Avg 1150.0 KB/io)
   SSD I/O Size Histogram       : <64K=2674 | 64K-512K=1137 | 512K-2M=636 | >2M=406
   SSD Read Bandwidth (Active)  : Min=0.81 | Avg=477.57 | Peak=3911.27 MB/s | WallAmort=86.77 MB/s (100.0% of 447.5 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=6288.31 MB | Write=128.00 MB | Syscalls=21905
   Sync Stall vs Async DMA      : SyncStall=604.28 ms | AsyncOverlapped=703.38 ms (53.8% Overlapped)
   RAM Traffic & Active BW      : 497.06 GB moved | Active=8.37 GB/s (19.0% STREAM) | WallAmort=7.91 GB/s (Max=44.13 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=23.43s (37.3%, 750.20 MB SSD) | Decode=39.37s (62.7%, 85.09 MB SSD)
   CPU Time & Utilization       : User=128.703s + Sys=12.172s (Wall=79.096s) | SysUtil=44.5% | ThrUtil=44.5% | 85.16 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  40117.40 ms (260502.6 us/tok | 63.87%)
   MoE AVX2 Q8 Expert Compute   :  16076.96 ms (104395.8 us/tok | 25.60%)
   Router + Lookahead Dispatch  :   1622.80 ms (10537.7 us/tok |  2.58%)
   LM Head Output Projection    :   3186.01 ms (20688.4 us/tok |  5.07%)
   Foreground NVMe Sync Stall   :    604.28 ms ( 3923.9 us/tok |  0.96%)
   Unaccounted / OMP & Sampling :   1200.53 ms ( 7795.6 us/tok |  1.91%) | Total Wall=62807.99 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    81.29%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     0.51%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.65%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    13.07%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.48%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_qwen38_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7999.88 MB (3855 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=2.75 tps | Avg=2.75 tps | Hit=88.1% | NVMe=780.1 MB/s (10578.12 MB, QD=64) | RSS=13794.6 MB
[LIVE-DECODE] 8/32 tok | Avg=1.72 tps | Hit=89.4% (LA:+0.9%) | NVMe=829.8 MB/s (12068.83 MB) | RSS=13771.4 MB
[LIVE-DECODE] 16/32 tok | Avg=1.80 tps | Hit=90.5% (LA:+1.2%) | NVMe=873.2 MB/s (13291.94 MB) | RSS=13743.2 MB
[LIVE-DECODE] 24/32 tok | Avg=1.83 tps | Hit=91.4% (LA:+1.3%) | NVMe=914.1 MB/s (14367.80 MB) | RSS=13736.1 MB
[LIVE-DECODE] 31/32 tok | Avg=1.85 tps | Hit=92.0% (LA:+1.5%) | NVMe=942.8 MB/s (15318.39 MB) | RSS=13735.4 MB

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
   LRFU Cache / Staging Ring    : 7999.88 MB (3855/25088 exp = 15.37% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=13735.40 MB | Peak=14033.30 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (64 tok)   : "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency..."
   RESPONSE (31 tok) : " a2

as
2:
2u
ar
22
22
0
2223

<|im_start|>

u"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 32 Steps)]
   Logit Summary: AvgTop1Prob=10.8% | AvgMargin=1.072 | MinMargin=0.004
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     264 |  a             |   13.79 |  18.1% |     303 |   13.43 | 23272.16 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    8.52 |   0.6% |     286 |    8.17 |  648.94 |889 | 71 |  0 | 237101.5 |
   |    3 |     198 | \n             |   14.17 |  53.5% |      11 |   12.36 |  648.94 |  0 |  0 |  0 | 237101.5 |
   |    4 |     198 | \n             |    9.66 |   5.1% |     350 |    7.90 |  694.00 |418 | 61 |  1 | 227289.0 |
   |    5 |     299 | as             |    8.80 |   1.5% |      64 |    8.72 |  519.67 |456 | 24 |  0 | 131518.0 |
   |    6 |     198 | \n             |   10.44 |  11.5% |      25 |    9.21 |  566.27 |441 | 39 |  0 | 199143.0 |
   |    7 |      17 | 2              |   10.14 |   5.4% |      18 |    9.57 |  514.26 |454 | 26 |  0 | 131872.0 |
   |    8 |      25 | :              |    9.71 |   7.4% |     198 |    8.84 |  521.68 |448 | 32 |  0 | 159664.0 |
   |   19 |      17 | 2              |    9.23 |   2.8% |      16 |    9.20 |  613.21 |472 |  8 |  0 | 143339.0 |
   |   17 |     198 | \n             |    9.98 |   5.6% |      24 |    8.90 |  555.65 |441 | 39 |  0 | 213793.0 |
   |   27 |     198 | \n             |   11.97 |  38.6% |      17 |    9.61 |  542.69 |442 | 38 |  0 | 194564.0 |
   |   10 |      17 | 2              |    9.02 |   2.6% |     198 |    8.66 |  539.91 |463 | 17 |  0 | 126814.0 |
   |   29 |  248045 | <|im_start|>   |    8.43 |   1.2% |      17 |    7.65 |  503.57 |467 | 13 |  0 | 108043.0 |
   |   30 |     198 | \n             |   10.29 |   7.2% |      84 |    8.09 |  538.25 |449 | 31 |  0 | 160314.0 |
   |   31 |     198 | \n             |    8.42 |   1.1% |      17 |    7.79 |  509.40 |471 |  9 |  0 | 104364.0 |
   |   32 |      84 | u              |    8.39 |   0.9% |      17 |    7.95 |  507.41 |472 |  8 |  0 | 102693.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 23.272s, TTFT=23272.16ms): Avg=2.75 | Min=2.75 | Max=2.75 tps
   Prefill Chunks (1): C1:64t/2.8tps/88%
   Decode  (31 tok, 16.713s): Avg=1.85 | Min=1.44 | Max=1.99 tps
   Latency (ms) : Min=503.40 | P10=505.23 | P25=509.71 | P50=521.68 | P75=539.91 | P90=613.21 | P95=648.94 | P99=694.00 | Max=694.00
   Mean/SD/Jitt : Mean=539.12ms | StdDev=46.78ms | Jitter=30.20ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/31
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (45600): RawRAM=41269 (90.50%) | Lookahead=682 (+1.50%) | ColdMiss=3649 (8.00%) | EFF HIT=92.00%
   Lookahead    : 2843 prefetched -> 692 consumed (24.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.5% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  950 |  666 |  70 | 214 | 77.5%| 475.05 | | L24 |  950 |  894 |   9 |  47 | 95.1%| 116.55 |
   | L01 |  950 |  815 |  41 |  94 | 90.1%| 393.46 | | L25 |  950 |  890 |   8 |  52 | 94.5%| 116.55 |
   | L02 |  950 |  824 |  24 | 102 | 89.3%| 405.98 | | L26 |  950 |  866 |  17 |  67 | 92.9%| 191.75 |
   | L03 |  950 |  892 |   3 |  55 | 94.2%| 552.69 | | L27 |  950 |  872 |  14 |  64 | 93.3%| 265.06 |
   | L04 |  950 |  885 |   7 |  58 | 93.9%| 315.43 | | L28 |  950 |  850 |  22 |  78 | 91.8%| 233.11 |
   | L05 |  950 |  870 |  10 |  70 | 92.6%| 317.70 | | L29 |  950 |  862 |  10 |  78 | 91.8%| 164.21 |
   | L06 |  950 |  873 |  16 |  61 | 93.6%| 221.83 | | L30 |  950 |  836 |  15 |  99 | 89.6%| 200.22 |
   | L07 |  950 |  874 |  16 |  60 | 93.7%| 165.09 | | L31 |  950 |  833 |  21 |  96 | 89.9%| 207.42 |
   | L08 |  950 |  900 |  10 |  40 | 95.8%| 109.57 | | L32 |  950 |  863 |   8 |  79 | 91.7%| 193.63 |
   | L09 |  950 |  894 |   3 |  53 | 94.4%|  98.36 | | L33 |  950 |  855 |  13 |  82 | 91.4%| 151.25 |
   | L10 |  950 |  882 |  11 |  57 | 94.0%| 118.29 | | L34 |  950 |  863 |   6 |  81 | 91.5%| 162.77 |
   | L11 |  950 |  895 |   5 |  50 | 94.7%| 144.43 | | L35 |  950 |  878 |   4 |  68 | 92.8%| 116.67 |
   | L12 |  950 |  870 |  16 |  64 | 93.3%| 233.11 | | L36 |  950 |  856 |  14 |  80 | 91.6%| 241.99 |
   | L13 |  950 |  861 |  17 |  72 | 92.4%| 146.92 | | L37 |  950 |  878 |   7 |  65 | 93.2%| 140.99 |
   | L14 |  950 |  853 |  19 |  78 | 91.8%| 214.62 | | L38 |  950 |  874 |  12 |  64 | 93.3%| 246.26 |
   | L15 |  950 |  857 |  12 |  81 | 91.5%| 233.11 | | L39 |  950 |  864 |  12 |  74 | 92.2%| 334.62 |
   | L16 |  950 |  868 |  10 |  72 | 92.4%| 182.35 | | L40 |  950 |  855 |  11 |  84 | 91.2%| 255.66 |
   | L17 |  950 |  868 |  13 |  69 | 92.7%| 187.99 | | L41 |  950 |  857 |   4 |  89 | 90.6%| 136.84 |
   | L18 |  950 |  862 |  18 |  70 | 92.6%| 186.11 | | L42 |  950 |  824 |  17 | 109 | 88.5%| 259.28 |
   | L19 |  950 |  872 |  10 |  68 | 92.8%| 159.89 | | L43 |  950 |  864 |   8 |  78 | 91.8%| 180.05 |
   | L20 |  950 |  844 |  16 |  90 | 90.5%| 184.38 | | L44 |  950 |  853 |   9 |  88 | 90.7%| 164.21 |
   | L21 |  950 |  831 |  31 |  88 | 90.7%| 404.17 | | L45 |  950 |  839 |  15 |  96 | 89.9%| 223.27 |
   | L22 |  950 |  884 |  14 |  52 | 94.5%| 238.75 | | L46 |  950 |  876 |  10 |  64 | 93.3%| 218.95 |
   | L23 |  950 |  876 |  10 |  64 | 93.3%| 162.77 | | L47 |  950 |  851 |  14 |  85 | 91.1%| 274.46 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 15318.39 MB (Load=4614.69 | Prefill=5963.42 | Warmup=0.00 | Decode=4740.28 MB)
   SSD Data/Token (Decode)      : Avg=152.912 MB/tok (Min=100.286 | P50=143.666 | P95=221.962 | Max=231.544 MB) | Prefill=93.178 MB/tok
   NVMe Batches / Requests      : 1446 Batches | 22104 Raw -> 21338 Merged (766 LBA Merges, Avg 735.1 KB/io)
   SSD I/O Size Histogram       : <64K=1835 | 64K-512K=5284 | 512K-2M=13785 | >2M=434
   SSD Read Bandwidth (Active)  : Min=2.33 | Avg=942.82 | Peak=9264.26 MB/s | WallAmort=383.11 MB/s
   OS Kernel I/O Verification   : Read=15338.37 MB | Write=0.00 MB | Syscalls=30840
   Sync Stall vs Async DMA      : SyncStall=2850.73 ms | AsyncOverlapped=5582.09 ms (66.2% Overlapped)
   RAM Traffic & Active BW      : 392.99 GB moved | Active=11.21 GB/s | WallAmort=9.83 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=23.27s (58.2%, 5963.42 MB SSD) | Decode=16.71s (41.8%, 4740.28 MB SSD)
   CPU Time & Utilization       : User=107.406s + Sys=8.609s (Wall=55.275s) | SysUtil=52.5% | ThrUtil=52.5% | 48.54 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  17615.16 ms (185422.8 us/tok | 44.05%)
   MoE AVX2 Q8 Expert Compute   :  16245.92 ms (171009.7 us/tok | 40.63%)
   Router + Lookahead Dispatch  :    991.14 ms (10433.0 us/tok |  2.48%)
   LM Head Output Projection    :   1182.99 ms (12452.6 us/tok |  2.96%)
   Foreground NVMe Sync Stall   :   2850.73 ms (30007.7 us/tok |  7.13%)
   Unaccounted / OMP & Sampling :   1098.88 ms (11567.1 us/tok |  2.75%) | Total Wall=39984.83 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    73.91%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.41%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     6.47%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    11.88%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.33%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_qwen38_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=8421.14 MB (4058 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=3.25 tps | Avg=3.25 tps | Hit=95.5% | NVMe=912.9 MB/s (13596.60 MB, QD=64) | RSS=14257.9 MB
[LIVE-PREFILL] 512/512 tok | Chunk=3.39 tps | Avg=3.32 tps | Hit=96.9% | NVMe=1027.8 MB/s (17151.58 MB, QD=64) | RSS=14255.2 MB
[LIVE-DECODE] 8/128 tok | Avg=1.75 tps | Hit=96.9% (LA:+0.1%) | NVMe=1052.2 MB/s (18591.91 MB) | RSS=14209.3 MB
[LIVE-DECODE] 16/128 tok | Avg=1.82 tps | Hit=97.0% (LA:+0.1%) | NVMe=1079.1 MB/s (19742.73 MB) | RSS=14179.8 MB
[LIVE-DECODE] 24/128 tok | Avg=1.83 tps | Hit=97.0% (LA:+0.2%) | NVMe=1096.1 MB/s (20841.93 MB) | RSS=14164.8 MB
[LIVE-DECODE] 32/128 tok | Avg=1.86 tps | Hit=97.1% (LA:+0.2%) | NVMe=1125.1 MB/s (21969.92 MB) | RSS=14163.1 MB
[LIVE-DECODE] 40/128 tok | Avg=1.87 tps | Hit=97.1% (LA:+0.2%) | NVMe=1148.9 MB/s (23058.13 MB) | RSS=14152.8 MB
[LIVE-DECODE] 48/128 tok | Avg=1.88 tps | Hit=97.2% (LA:+0.2%) | NVMe=1169.6 MB/s (24122.65 MB) | RSS=14154.4 MB
[LIVE-DECODE] 56/128 tok | Avg=1.89 tps | Hit=97.2% (LA:+0.2%) | NVMe=1195.6 MB/s (25166.91 MB) | RSS=14152.4 MB
[LIVE-DECODE] 64/128 tok | Avg=1.89 tps | Hit=97.2% (LA:+0.2%) | NVMe=1218.8 MB/s (26282.04 MB) | RSS=14152.4 MB
[LIVE-DECODE] 72/128 tok | Avg=1.90 tps | Hit=97.3% (LA:+0.3%) | NVMe=1234.8 MB/s (27443.47 MB) | RSS=14151.1 MB
[LIVE-DECODE] 80/128 tok | Avg=1.85 tps | Hit=97.3% (LA:+0.3%) | NVMe=1240.2 MB/s (28552.29 MB) | RSS=14149.0 MB
[LIVE-DECODE] 88/128 tok | Avg=1.83 tps | Hit=97.3% (LA:+0.3%) | NVMe=1247.3 MB/s (29619.65 MB) | RSS=14151.1 MB
[LIVE-DECODE] 96/128 tok | Avg=1.83 tps | Hit=97.4% (LA:+0.3%) | NVMe=1260.8 MB/s (30774.35 MB) | RSS=14150.7 MB
[LIVE-DECODE] 104/128 tok | Avg=1.83 tps | Hit=97.4% (LA:+0.3%) | NVMe=1267.2 MB/s (31927.50 MB) | RSS=14163.5 MB
[LIVE-DECODE] 112/128 tok | Avg=1.83 tps | Hit=97.4% (LA:+0.3%) | NVMe=1278.5 MB/s (32917.93 MB) | RSS=14151.1 MB
[LIVE-DECODE] 120/128 tok | Avg=1.84 tps | Hit=97.5% (LA:+0.3%) | NVMe=1288.9 MB/s (34056.09 MB) | RSS=14151.1 MB
[LIVE-DECODE] 127/128 tok | Avg=1.84 tps | Hit=97.5% (LA:+0.4%) | NVMe=1293.5 MB/s (35098.77 MB) | RSS=14156.5 MB

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
   LRFU Cache / Staging Ring    : 8421.14 MB (4058/25088 exp = 16.18% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.86 MB | End=14156.54 MB | Peak=14479.07 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (512 tok)   : "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequenc..."
   RESPONSE (127 tok) : "2709
7222221222277222202022222022202272222221222222222222222222222232232223222223332223922222222221
27922722232331222322j222212p"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 128 Steps)]
   Logit Summary: AvgTop1Prob=14.4% | AvgMargin=0.598 | MinMargin=0.006
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |      17 | 2              |   11.54 |   5.6% |      22 |   11.02 | 154166.66 |  0 |  0 |  0 |     0.0 |
   |    2 |      22 | 7              |   12.22 |   9.7% |      17 |   11.35 |  627.11 |899 | 61 |  0 | 208239.0 |
   |    3 |      15 | 0              |   12.04 |  16.2% |      18 |   11.66 |  627.11 |  0 |  0 |  0 | 208239.0 |
   |    4 |      24 | 9              |    9.76 |   3.6% |      18 |    9.46 |  573.35 |440 | 40 |  0 | 217818.0 |
   |    5 |     198 | \n             |   10.19 |  12.1% |      17 |    8.96 |  571.46 |466 | 14 |  0 | 150193.0 |
   |    6 |      22 | 7              |    9.69 |   4.0% |      17 |    9.42 |  554.87 |440 | 40 |  0 | 177789.0 |
   |    7 |      17 | 2              |    8.00 |   1.2% |      16 |    7.73 |  545.34 |444 | 36 |  0 | 193914.0 |
   |    8 |      17 | 2              |   10.11 |   6.0% |      18 |    9.42 |  546.00 |468 | 12 |  0 | 153643.0 |
   |   78 |      17 | 2              |   13.61 |  31.2% |      18 |   12.89 |  844.78 |478 |  2 |  0 | 122468.0 |
   |   81 |      18 | 3              |   12.27 |  27.1% |      17 |   12.04 |  810.86 |477 |  3 |  0 | 145118.0 |
   |   82 |      18 | 3              |   11.59 |  16.7% |      17 |   10.59 |  761.78 |474 |  6 |  0 | 139589.0 |
   |   79 |      17 | 2              |   14.75 |  33.9% |      18 |   13.95 |  759.07 |476 |  4 |  0 | 139543.0 |
   |  125 |      17 | 2              |    9.93 |   5.5% |      19 |    9.22 |  518.16 |477 |  3 |  0 | 141793.0 |
   |  126 |      16 | 1              |   10.55 |  10.3% |      15 |   10.48 |  523.64 |474 |  6 |  0 | 122743.0 |
   |  127 |      17 | 2              |   11.23 |   8.7% |      15 |   11.04 |  534.34 |467 | 13 |  0 | 143139.0 |
   |  128 |      79 | p              |    8.80 |   1.3% |      18 |    8.34 |  609.13 |473 |  7 |  0 | 151293.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 154.167s, TTFT=154166.66ms): Avg=3.32 | Min=3.25 | Max=3.39 tps
   Prefill Chunks (2): C1:256t/3.3tps/96% | C2:256t/3.4tps/97%
   Decode  (127 tok, 69.085s): Avg=1.84 | Min=1.18 | Max=2.03 tps
   Latency (ms) : Min=493.14 | P10=511.09 | P25=516.10 | P50=525.20 | P75=540.58 | P90=602.04 | P95=696.99 | P99=810.86 | Max=844.78
   Mean/SD/Jitt : Mean=543.97ms | StdDev=58.91ms | Jitter=22.45ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/127
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (306720): RawRAM=297949 (97.14%) | Lookahead=1117 (+0.36%) | ColdMiss=7654 (2.50%) | EFF HIT=97.50%
   Lookahead    : 10918 prefetched -> 1127 consumed (10.3% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.0% | @64= 97.2% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 6390 | 5769 |  86 | 535 | 91.6%|1046.12 | | L24 | 6390 | 6294 |   3 |  93 | 98.5%| 250.02 |
   | L01 | 6390 | 6167 |  42 | 181 | 97.2%|1451.81 | | L25 | 6390 | 6293 |  10 |  87 | 98.6%| 257.54 |
   | L02 | 6390 | 6154 |  15 | 221 | 96.5%|1821.02 | | L26 | 6390 | 6199 |  26 | 165 | 97.4%| 511.33 |
   | L03 | 6390 | 6315 |   2 |  73 | 98.9%|2372.41 | | L27 | 6390 | 6272 |  14 | 104 | 98.4%| 485.01 |
   | L04 | 6390 | 6288 |   2 | 100 | 98.4%| 722.17 | | L28 | 6390 | 6161 |  32 | 197 | 96.9%| 618.48 |
   | L05 | 6390 | 6252 |  12 | 126 | 98.0%|1107.25 | | L29 | 6390 | 6200 |  31 | 159 | 97.5%| 403.32 |
   | L06 | 6390 | 6261 |  11 | 118 | 98.2%| 661.72 | | L30 | 6390 | 6112 |  58 | 220 | 96.6%| 577.61 |
   | L07 | 6390 | 6256 |  10 | 124 | 98.1%| 560.96 | | L31 | 6390 | 6127 |  48 | 215 | 96.6%| 518.55 |
   | L08 | 6390 | 6320 |   3 |  67 | 99.0%| 276.42 | | L32 | 6390 | 6203 |  28 | 159 | 97.5%| 678.64 |
   | L09 | 6390 | 6320 |   2 |  68 | 98.9%|  95.87 | | L33 | 6390 | 6171 |  39 | 180 | 97.2%| 422.05 |
   | L10 | 6390 | 6294 |   4 |  92 | 98.6%| 141.94 | | L34 | 6390 | 6083 |  67 | 240 | 96.2%| 579.05 |
   | L11 | 6390 | 6319 |   3 |  68 | 98.9%| 179.30 | | L35 | 6390 | 6215 |  19 | 156 | 97.6%| 373.07 |
   | L12 | 6390 | 6283 |   3 | 104 | 98.4%| 603.44 | | L36 | 6390 | 6197 |  23 | 170 | 97.3%| 458.06 |
   | L13 | 6390 | 6261 |  14 | 115 | 98.2%| 282.32 | | L37 | 6390 | 6206 |  26 | 158 | 97.5%| 464.33 |
   | L14 | 6390 | 6249 |  24 | 117 | 98.2%| 501.27 | | L38 | 6390 | 6266 |   9 | 115 | 98.2%| 761.35 |
   | L15 | 6390 | 6211 |  18 | 161 | 97.5%| 428.61 | | L39 | 6390 | 6216 |  11 | 163 | 97.4%| 701.20 |
   | L16 | 6390 | 6207 |   8 | 175 | 97.3%| 406.05 | | L40 | 6390 | 6218 |  33 | 139 | 97.8%| 729.39 |
   | L17 | 6390 | 6187 |  11 | 192 | 97.0%| 479.37 | | L41 | 6390 | 6224 |  16 | 150 | 97.7%| 290.97 |
   | L18 | 6390 | 6205 |  16 | 169 | 97.4%| 406.05 | | L42 | 6390 | 6106 |  56 | 228 | 96.4%| 737.50 |
   | L19 | 6390 | 6248 |  10 | 132 | 97.9%| 344.26 | | L43 | 6390 | 6123 |  42 | 225 | 96.5%| 617.94 |
   | L20 | 6390 | 6138 |  15 | 237 | 96.3%| 956.45 | | L44 | 6390 | 6121 |  51 | 218 | 96.6%| 600.66 |
   | L21 | 6390 | 6168 |  17 | 205 | 96.8%|1158.01 | | L45 | 6390 | 6065 |  93 | 232 | 96.4%| 858.50 |
   | L22 | 6390 | 6293 |   4 |  93 | 98.5%| 434.25 | | L46 | 6390 | 6267 |  22 | 101 | 98.4%| 962.21 |
   | L23 | 6390 | 6212 |  19 | 159 | 97.5%| 604.98 | | L47 | 6390 | 6233 |   9 | 148 | 97.7%| 494.41 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 35098.77 MB (Load=4614.69 | Prefill=12536.88 | Warmup=0.00 | Decode=17947.19 MB)
   SSD Data/Token (Decode)      : Avg=141.316 MB/tok (Min=99.188 | P50=138.222 | P95=175.014 | Max=212.713 MB) | Prefill=24.486 MB/tok
   NVMe Batches / Requests      : 5059 Batches | 67048 Raw -> 65368 Merged (1680 LBA Merges, Avg 549.8 KB/io)
   SSD I/O Size Histogram       : <64K=10481 | 64K-512K=15396 | 512K-2M=39049 | >2M=442
   SSD Read Bandwidth (Active)  : Min=1.21 | Avg=1293.51 | Peak=9657.59 MB/s | WallAmort=157.22 MB/s
   OS Kernel I/O Verification   : Read=35114.32 MB | Write=0.00 MB | Syscalls=74883
   Sync Stall vs Async DMA      : SyncStall=5450.29 ms | AsyncOverlapped=16336.65 ms (75.0% Overlapped)
   RAM Traffic & Active BW      : 2226.07 GB moved | Active=10.69 GB/s | WallAmort=9.97 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=154.17s (69.1%, 12536.88 MB SSD) | Decode=69.08s (30.9%, 17947.19 MB SSD)
   CPU Time & Utilization       : User=696.781s + Sys=28.797s (Wall=239.205s) | SysUtil=75.8% | ThrUtil=75.8% | 70.14 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 104440.44 ms (163443.6 us/tok | 46.78%)
   MoE AVX2 Q8 Expert Compute   :  98796.51 ms (154611.1 us/tok | 44.25%)
   Router + Lookahead Dispatch  :   5846.60 ms ( 9149.6 us/tok |  2.62%)
   LM Head Output Projection    :   4964.00 ms ( 7768.4 us/tok |  2.22%)
   Foreground NVMe Sync Stall   :   5450.29 ms ( 8529.4 us/tok |  2.44%)
   Unaccounted / OMP & Sampling :   3753.50 ms ( 5874.0 us/tok |  1.68%) | Total Wall=223251.35 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    76.48%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.53%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.17%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    13.88%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.94%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_qwen38_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 17975.8ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\n\n\n\n\n\n\n\n\n\n\n\n\n\n1\n'
[Stage 3] /v1/chat/completions (stream=true SSE) 6332.2ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_qwen38_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7458.25 MB (3594 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=3.32 tps | Avg=3.32 tps | Hit=95.4% | NVMe=969.1 MB/s (13785.34 MB, QD=64) | RSS=13296.5 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=3.40 tps | Avg=3.36 tps | Hit=96.6% | NVMe=1123.3 MB/s (18190.57 MB, QD=64) | RSS=13296.5 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=3.38 tps | Avg=3.36 tps | Hit=97.1% | NVMe=1240.6 MB/s (22243.29 MB, QD=64) | RSS=13296.6 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=3.35 tps | Avg=3.36 tps | Hit=97.3% | NVMe=1336.4 MB/s (26270.16 MB, QD=64) | RSS=13297.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=3.33 tps | Avg=3.36 tps | Hit=97.5% | NVMe=1419.1 MB/s (30169.43 MB, QD=64) | RSS=13296.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=3.31 tps | Avg=3.35 tps | Hit=97.6% | NVMe=1493.1 MB/s (34071.32 MB, QD=64) | RSS=13297.0 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=3.29 tps | Avg=3.34 tps | Hit=97.6% | NVMe=1554.0 MB/s (37985.28 MB, QD=64) | RSS=13296.7 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=3.26 tps | Avg=3.33 tps | Hit=97.7% | NVMe=1603.3 MB/s (41748.61 MB, QD=64) | RSS=13297.9 MB
[LIVE-DECODE] 8/64 tok | Avg=1.65 tps | Hit=97.7% (LA:+0.0%) | NVMe=1603.4 MB/s (43411.55 MB) | RSS=13304.9 MB
[LIVE-DECODE] 16/64 tok | Avg=1.70 tps | Hit=97.7% (LA:+0.0%) | NVMe=1606.9 MB/s (44820.37 MB) | RSS=13304.9 MB
[LIVE-DECODE] 24/64 tok | Avg=1.73 tps | Hit=97.7% (LA:+0.1%) | NVMe=1612.4 MB/s (46139.48 MB) | RSS=13302.8 MB
[LIVE-DECODE] 32/64 tok | Avg=1.74 tps | Hit=97.7% (LA:+0.1%) | NVMe=1617.0 MB/s (47382.70 MB) | RSS=13302.6 MB
[LIVE-DECODE] 40/64 tok | Avg=1.75 tps | Hit=97.7% (LA:+0.1%) | NVMe=1621.2 MB/s (48669.10 MB) | RSS=13295.1 MB
[LIVE-DECODE] 48/64 tok | Avg=1.75 tps | Hit=97.7% (LA:+0.1%) | NVMe=1628.1 MB/s (49922.31 MB) | RSS=13281.8 MB
[LIVE-DECODE] 56/64 tok | Avg=1.76 tps | Hit=97.8% (LA:+0.1%) | NVMe=1631.1 MB/s (51276.47 MB) | RSS=13267.9 MB
[LIVE-DECODE] 63/64 tok | Avg=1.76 tps | Hit=97.8% (LA:+0.1%) | NVMe=1632.6 MB/s (52637.35 MB) | RSS=13262.1 MB

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
   LRFU Cache / Staging Ring    : 7458.25 MB (3594/25088 exp = 14.33% pinned) | Staging=66.41 MB
   Process RSS (Start/End/Peak) : Start=4.75 MB | End=13262.09 MB | Peak=13533.90 MB
--------------------------------------------------------------------------------
 [3. Input Prompt & Model Response Transcript]
   PROMPT (2048 tok)   : "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequen..."
   RESPONSE (63 tok) : "
221221121221
2223722212221722120722212222272227121222272777d77a"
--------------------------------------------------------------------------------
 [4. Decode Token Trace (First 8 + Top-4 Slowest Outliers + Last 4 of 64 Steps)]
   Logit Summary: AvgTop1Prob=11.7% | AvgMargin=0.454 | MinMargin=0.008
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   | Step | Tok ID  | Piece          | Top1Lgt | Prob%  | Top2 ID | Top2Lgt | Lat(ms) |Raw | LA |Miss| SSD(KB) |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
   |    1 |     198 | \n             |    7.38 |   0.7% |      17 |    7.24 | 615230.27 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    8.65 |   1.9% |      22 |    8.24 |  666.44 |852 |108 |  0 | 263714.0 |
   |    3 |      17 | 2              |   12.45 |  20.9% |      18 |   11.82 |  666.44 |  0 |  0 |  0 | 263714.0 |
   |    4 |      16 | 1              |   10.53 |   8.3% |      17 |   10.14 |  615.14 |448 | 32 |  0 | 205068.0 |
   |    5 |      17 | 2              |   11.00 |   7.6% |      15 |   10.61 |  590.20 |437 | 43 |  0 | 207814.0 |
   |    6 |      17 | 2              |   10.56 |  11.0% |      16 |   10.50 |  592.28 |445 | 35 |  0 | 209668.0 |
   |    7 |      16 | 1              |    8.55 |   2.2% |      15 |    8.11 |  580.67 |464 | 16 |  0 | 165718.0 |
   |    8 |      16 | 1              |   10.85 |  16.6% |      17 |   10.31 |  575.24 |447 | 33 |  0 | 186664.0 |
   |   10 |      16 | 1              |   10.43 |   9.8% |      17 |   10.35 |  612.18 |458 | 22 |  0 | 178089.0 |
   |   15 |      17 | 2              |    9.13 |   5.3% |     198 |    8.72 |  586.01 |426 | 54 |  0 | 226664.0 |
   |   44 |      22 | 7              |   10.66 |  11.5% |      17 |    9.77 |  585.12 |466 | 14 |  0 | 167593.0 |
   |   60 |      22 | 7              |   13.90 |  27.1% |      18 |   13.41 |  584.93 |450 | 30 |  0 | 205764.0 |
   |   61 |      67 | d              |   12.02 |   7.7% |      64 |   11.63 |  579.06 |448 | 32 |  0 | 221039.0 |
   |   62 |      22 | 7              |   13.02 |  18.4% |      20 |   12.37 |  576.33 |462 | 18 |  0 | 174414.0 |
   |   63 |      22 | 7              |   16.44 |  44.2% |      20 |   15.12 |  559.67 |463 | 17 |  0 | 173039.0 |
   |   64 |      64 | a              |   10.35 |   4.4% |      77 |   10.10 |  573.64 |451 | 29 |  0 | 227139.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 615.230s, TTFT=615230.27ms): Avg=3.33 | Min=3.26 | Max=3.40 tps
   Prefill Chunks (8): C1:256t/3.3tps/95% | C2:256t/3.4tps/97% | C3:256t/3.4tps/97% | C4:256t/3.4tps/97%
                       C5:256t/3.3tps/97% | C6:256t/3.3tps/98% | C7:256t/3.3tps/98% | C8:256t/3.3tps/98%
   Decode  (63 tok, 35.836s): Avg=1.76 | Min=1.50 | Max=1.83 tps
   Latency (ms) : Min=546.81 | P10=551.98 | P25=556.12 | P50=562.88 | P75=573.64 | P90=586.01 | P95=612.18 | P99=666.44 | Max=666.44
   Mean/SD/Jitt : Mean=568.83ms | StdDev=22.40ms | Jitter=10.81ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1013280): RawRAM=989335 (97.64%) | Lookahead=1245 (+0.12%) | ColdMiss=22700 (2.24%) | EFF HIT=97.76%
   Lookahead    : 6593 prefetched -> 1255 consumed (19.0% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.7% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21110 |19023 |  97 |1990 | 90.6%|3515.70 | | L24 |21110 |20928 |   6 | 176 | 99.2%| 396.66 |
   | L01 |21110 |20546 |  38 | 526 | 97.5%|1257.57 | | L25 |21110 |20927 |   7 | 176 | 99.2%| 359.06 |
   | L02 |21110 |20501 |  14 | 595 | 97.2%|1682.89 | | L26 |21110 |20575 |  24 | 511 | 97.6%|1221.92 |
   | L03 |21110 |21032 |   1 |  77 | 99.6%|1035.82 | | L27 |21110 |20824 |  18 | 268 | 98.7%| 635.40 |
   | L04 |21110 |20881 |   7 | 222 | 98.9%| 774.05 | | L28 |21110 |20473 |  25 | 612 | 97.1%|1355.40 |
   | L05 |21110 |20801 |  19 | 290 | 98.6%|1017.02 | | L29 |21110 |20643 |  21 | 446 | 97.9%| 754.79 |
   | L06 |21110 |20817 |  30 | 263 | 98.8%| 838.43 | | L30 |21110 |20239 |  51 | 820 | 96.1%|1342.48 |
   | L07 |21110 |20818 |  22 | 270 | 98.7%| 534.01 | | L31 |21110 |20348 |  42 | 720 | 96.6%|1209.96 |
   | L08 |21110 |21038 |   1 |  71 | 99.7%| 155.64 | | L32 |21110 |20569 |  21 | 520 | 97.5%|1205.00 |
   | L09 |21110 |21035 |   0 |  75 | 99.6%|  95.87 | | L33 |21110 |20444 |  39 | 627 | 97.0%|1052.95 |
   | L10 |21110 |20935 |   4 | 171 | 99.2%| 232.84 | | L34 |21110 |20190 |  55 | 865 | 95.9%|1414.50 |
   | L11 |21110 |21036 |   1 |  73 | 99.7%| 120.78 | | L35 |21110 |20616 |  33 | 461 | 97.8%| 815.28 |
   | L12 |21110 |20975 |   2 | 133 | 99.4%| 443.65 | | L36 |21110 |20556 |  41 | 513 | 97.6%| 917.55 |
   | L13 |21110 |20877 |   6 | 227 | 98.9%| 394.68 | | L37 |21110 |20512 |  24 | 574 | 97.3%|1197.49 |
   | L14 |21110 |20779 |  44 | 287 | 98.6%| 701.49 | | L38 |21110 |20750 |  13 | 347 | 98.4%| 894.82 |
   | L15 |21110 |20631 |  43 | 436 | 97.9%|1009.50 | | L39 |21110 |20565 |  30 | 515 | 97.6%|1255.76 |
   | L16 |21110 |20563 |  20 | 527 | 97.5%|1099.73 | | L40 |21110 |20673 |  29 | 408 | 98.1%|1035.82 |
   | L17 |21110 |20407 |  22 | 681 | 96.8%|1479.47 | | L41 |21110 |20656 |  15 | 439 | 97.9%| 741.82 |
   | L18 |21110 |20456 |  37 | 617 | 97.1%|1306.52 | | L42 |21110 |20358 |  38 | 714 | 96.6%|1271.90 |
   | L19 |21110 |20661 |  36 | 413 | 98.0%| 711.57 | | L43 |21110 |20261 |  33 | 816 | 96.1%|1424.58 |
   | L20 |21110 |20295 |  44 | 771 | 96.3%|1426.03 | | L44 |21110 |20264 |  40 | 806 | 96.2%|1325.20 |
   | L21 |21110 |20427 |  37 | 646 | 96.9%|1812.21 | | L45 |21110 |20321 |  54 | 735 | 96.5%|1387.13 |
   | L22 |21110 |20907 |  10 | 193 | 99.1%| 496.29 | | L46 |21110 |20882 |  10 | 218 | 99.0%| 620.83 |
   | L23 |21110 |20550 |  28 | 532 | 97.5%|1070.24 | | L47 |21110 |20770 |  13 | 327 | 98.5%| 789.55 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 52637.35 MB (Load=4614.69 | Prefill=37133.91 | Warmup=0.00 | Decode=10888.75 MB)
   SSD Data/Token (Decode)      : Avg=172.837 MB/tok (Min=130.336 | P50=168.983 | P95=216.347 | Max=257.533 MB) | Prefill=18.132 MB/tok
   NVMe Batches / Requests      : 3779 Batches | 122763 Raw -> 118378 Merged (4385 LBA Merges, Avg 455.3 KB/io)
   SSD I/O Size Histogram       : <64K=33825 | 64K-512K=21873 | 512K-2M=62189 | >2M=491
   SSD Read Bandwidth (Active)  : Min=0.85 | Avg=1632.62 | Peak=9620.69 MB/s | WallAmort=80.85 MB/s
   OS Kernel I/O Verification   : Read=52657.89 MB | Write=0.00 MB | Syscalls=127891
   Sync Stall vs Async DMA      : SyncStall=14042.00 ms | AsyncOverlapped=21540.58 ms (60.5% Overlapped)
   RAM Traffic & Active BW      : 5635.43 GB moved | Active=9.20 GB/s | WallAmort=8.66 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=615.23s (94.5%, 37133.91 MB SSD) | Decode=35.84s (5.5%, 10888.75 MB SSD)
   CPU Time & Utilization       : User=2244.953s + Sys=39.500s (Wall=666.329s) | SysUtil=85.7% | ThrUtil=85.7% | 79.28 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 300570.55 ms (142383.0 us/tok | 46.17%)
   MoE AVX2 Q8 Expert Compute   : 309593.00 ms (146657.0 us/tok | 47.55%)
   Router + Lookahead Dispatch  :  18604.02 ms ( 8812.9 us/tok |  2.86%)
   LM Head Output Projection    :   2412.17 ms ( 1142.7 us/tok |  0.37%)
   Foreground NVMe Sync Stall   :  14042.00 ms ( 6651.8 us/tok |  2.16%)
   Unaccounted / OMP & Sampling :   5844.87 ms ( 2768.8 us/tok |  0.90%) | Total Wall=651066.61 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    76.54%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.04%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     1.17%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    15.53%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     5.72%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_qwen38_colibri_bench.log`
```text
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=285.0s) ===
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
resident weights loaded in 11.4s | RSS after load: 4.60 GB
[qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=285.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.1s / cutoff=285.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=285.0s
TTFT: 22.32 s (time to first token)
[qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
[qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
[qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes

PEAK RSS: 10.72 GB
Expert cache hit rate: 62.0% (hit=15849 miss=9733)
Speed: 0.74 tok/s (43.2s for 32 tokens)
[STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage

Reference: 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 
C engine : 220 248046 198 248045 74455 198 248068 198 760 1156 682 3106 1092 7701 310 381 264 7132 36412 2805 269 82987 886 314 5587 13 6558 728 22903 411 25 271 Text      :  <|im_end|>
<|im_start|>assistant
<think>
The user has sent what appears to be a garbled/corrupted string of characters. Let me analyze this:



Matching tokens: 0/32
=== [Colibri-Qwen38] Finished rc=1 elapsed=57.66s cancelled=False ===
```

### 📄 `12_qwen38_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 2.75 | 1.85 | 521.68 | 92.00% | 942.82 | 14033.30 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 3.32 | 1.84 | 525.20 | 97.50% | 1293.51 | 14479.07 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 3.33 | 1.76 | 562.88 | 97.76% | 1632.62 | 13533.90 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.74 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
