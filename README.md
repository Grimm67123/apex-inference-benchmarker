<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#25 (Run ID `43563679876`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43563679876)
- **Status**: **SUCCESS**
- **Timestamp**: `2026-11-14 06:31:58 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T05:53:34.883Z] ================================================================================
[2026-11-14T05:53:34.908Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T05:53:34.910Z] ================================================================================
[2026-11-14T05:53:39.391Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T05:53:39.635Z] --------------------------------------------------------------------------------
[2026-11-14T05:53:39.637Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 30.99 GB / 149.89 GB
[2026-11-14T05:53:39.639Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.02 GB / 150 GB
[2026-11-14T05:53:39.641Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.01 GB
[2026-11-14T05:53:39.642Z] --------------------------------------------------------------------------------
[2026-11-14T05:53:39.644Z]  [OK] Disk space verification passed: 178.01 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
-rwxr-xr-x 1 runneradmin 197121 872K Nov 14 05:54 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 872K Nov 14 05:54 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.51 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    239.32 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    945.89 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4844.34 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7584.24 MB/s
   RND4K Q32T16 Read                  :    572.83 MB/s (  146643 IOPS)
   RND4K Q1T1  Read                   :    777.70 MB/s (Latency: 5.02 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     41.97 GB/s
   AVX2 256-bit Sequential Write BW   :     29.03 GB/s
   STREAM Triad (A = B + s*C) BW      :     27.51 GB/s
   Random Pointer-Chase Latency       :    122.15 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     43.70 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    164.18 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     16.56 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1373.45 tps | Avg=1373.45 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=73.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1252.26 tps | Avg=1310.06 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=73.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1079.42 tps | Avg=1222.96 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=74.1 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=952.30 tps | Avg=1141.83 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=74.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=863.88 tps | Avg=1072.79 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=74.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=764.76 tps | Avg=1005.31 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=74.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=725.53 tps | Avg=952.82 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=75.1 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=669.52 tps | Avg=904.95 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=75.4 MB
[LIVE-DECODE] 8/32 tok | Avg=172.42 tps | Hit=100.0% (LA:+0.0%) | NVMe=1778.8 MB/s (6.58 MB) | RSS=75.4 MB
[LIVE-DECODE] 16/32 tok | Avg=182.44 tps | Hit=100.0% (LA:+0.0%) | NVMe=1778.8 MB/s (6.58 MB) | RSS=75.4 MB
[LIVE-DECODE] 24/32 tok | Avg=183.02 tps | Hit=100.0% (LA:+0.0%) | NVMe=1778.8 MB/s (6.58 MB) | RSS=75.4 MB
[LIVE-DECODE] 32/32 tok | Avg=182.63 tps | Hit=100.0% (LA:+0.0%) | NVMe=1778.8 MB/s (6.58 MB) | RSS=75.4 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=75.44 MB | Peak=75.44 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2263.10 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.90 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.90 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.94 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.94 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.72 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.72 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.64 | 12 |  0 |  0 |     0.0 |
   |    9 |      68 | tok_68         |  176.71 | 100.0% |     228 |  144.43 |    5.64 |  0 |  0 |  0 |     0.0 |
   |   28 |     246 | tok_246        |  194.87 | 100.0% |      54 |  173.43 |    5.59 | 12 |  0 |  0 |     0.0 |
   |   29 |     229 | tok_229        |  172.54 | 100.0% |      70 |  154.16 |    5.59 |  0 |  0 |  0 |     0.0 |
   |   24 |     246 | tok_246        |  204.37 |  99.2% |      55 |  199.55 |    5.48 | 12 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.53 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.53 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.47 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.47 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.263s, TTFT=2263.10ms): Avg=904.95 | Min=669.52 | Max=1373.45 tps
   Prefill Chunks (8): C1:256t/1373.4tps/100% | C2:256t/1252.3tps/100% | C3:256t/1079.4tps/100% | C4:256t/952.3tps/100%
                       C5:256t/863.9tps/100% | C6:256t/764.8tps/100% | C7:256t/725.5tps/100% | C8:256t/669.5tps/100%
   Decode  (32 tok, 0.175s): Avg=182.63 | Min=168.25 | Max=198.35 tps
   Latency (ms) : Min=5.04 | P10=5.09 | P25=5.37 | P50=5.47 | P75=5.64 | P90=5.90 | P95=5.94 | P99=5.94 | Max=5.94
   Mean/SD/Jitt : Mean=5.48ms | StdDev=0.24ms | Jitter=0.05ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=203.97 | Avg=1778.85 | Peak=4770.99 MB/s | WallAmort=2.70 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=2.18 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.62 GB/s | WallAmort=0.59 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.26s (92.8%, 0.00 MB SSD) | Decode=0.18s (7.2%, 0.00 MB SSD)
   CPU Time & Utilization       : User=3.141s + Sys=0.641s (Wall=2.470s) | SysUtil=38.3% | ThrUtil=38.3% | 35.41 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2057.93 ms (  989.4 us/tok | 84.40%)
   MoE AVX2 Q8 Expert Compute   :    246.10 ms (  118.3 us/tok | 10.09%)
   Router + Lookahead Dispatch  :     61.13 ms (   29.4 us/tok |  2.51%)
   LM Head Output Projection    :      6.96 ms (    3.3 us/tok |  0.29%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     66.20 ms (   31.8 us/tok |  2.71%) | Total Wall=2438.32 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.65%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.04%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.12%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    74.35%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.84%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1968.56 tps | Avg=1968.56 tps | Hit=99.2% | NVMe=2160.9 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2012.71 tps | Avg=1990.39 tps | Hit=99.2% | NVMe=2844.0 MB/s (42.92 MB, QD=64) | RSS=89.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1779.74 tps | Avg=1914.84 tps | Hit=99.2% | NVMe=3277.6 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1705.05 tps | Avg=1857.70 tps | Hit=99.2% | NVMe=3557.4 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1594.30 tps | Avg=1798.28 tps | Hit=99.2% | NVMe=3756.4 MB/s (97.14 MB, QD=64) | RSS=90.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1478.13 tps | Avg=1735.62 tps | Hit=99.2% | NVMe=3923.1 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1334.94 tps | Avg=1664.26 tps | Hit=99.2% | NVMe=4057.0 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1331.47 tps | Avg=1613.84 tps | Hit=99.2% | NVMe=4181.2 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=155.31 tps | Hit=99.2% (LA:+0.0%) | NVMe=4094.3 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=156.90 tps | Hit=99.2% (LA:+0.1%) | NVMe=4046.1 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=157.20 tps | Hit=99.2% (LA:+0.1%) | NVMe=3969.8 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=158.80 tps | Hit=99.2% (LA:+0.1%) | NVMe=3907.7 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=91.68 MB | Peak=91.68 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1269.02 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    6.51 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    6.51 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    6.49 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    6.49 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    6.48 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    6.48 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    6.27 | 16 |  0 |  0 |    32.0 |
   |   22 |     128 | qtok_128       |   64.14 |  98.8% |       2 |   59.73 |    6.36 | 12 |  4 |  0 |   115.2 |
   |   23 |      63 | qtok_63        |   98.11 | 100.0% |     113 |   72.66 |    6.36 |  0 |  0 |  0 |   115.2 |
   |   26 |     194 | qtok_194       |   70.46 | 100.0% |     128 |   54.98 |    6.36 | 12 |  4 |  0 |   147.0 |
   |   27 |      49 | qtok_49        |   67.58 |  99.9% |     209 |   61.01 |    6.36 |  0 |  0 |  0 |   147.0 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.97 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.97 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.85 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.85 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.269s, TTFT=1269.02ms): Avg=1613.84 | Min=1331.47 | Max=2012.71 tps
   Prefill Chunks (8): C1:256t/1968.6tps/99% | C2:256t/2012.7tps/99% | C3:256t/1779.7tps/99% | C4:256t/1705.1tps/99%
                       C5:256t/1594.3tps/99% | C6:256t/1478.1tps/99% | C7:256t/1334.9tps/99% | C8:256t/1331.5tps/99%
   Decode  (32 tok, 0.202s): Avg=158.80 | Min=153.58 | Max=171.00 tps
   Latency (ms) : Min=5.85 | P10=5.97 | P25=6.27 | P50=6.34 | P75=6.36 | P90=6.49 | P95=6.51 | P99=6.51 | Max=6.51
   Mean/SD/Jitt : Mean=6.30ms | StdDev=0.17ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=256.99 | Avg=3907.73 | Peak=7590.95 MB/s | WallAmort=105.50 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=9.59 ms | AsyncOverlapped=37.98 ms (79.8% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.66 GB/s | WallAmort=1.43 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.27s (86.3%, 144.44 MB SSD) | Decode=0.20s (13.7%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.547s + Sys=0.297s (Wall=1.521s) | SysUtil=46.7% | ThrUtil=46.7% | 43.23 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    897.64 ms (  431.6 us/tok | 61.04%)
   MoE AVX2 Q8 Expert Compute   :    359.28 ms (  172.7 us/tok | 24.43%)
   Router + Lookahead Dispatch  :     79.58 ms (   38.3 us/tok |  5.41%)
   LM Head Output Projection    :      7.08 ms (    3.4 us/tok |  0.48%)
   Foreground NVMe Sync Stall   :      9.59 ms (    4.6 us/tok |  0.65%)
   Unaccounted / OMP & Sampling :    117.37 ms (   56.4 us/tok |  7.98%) | Total Wall=1470.54 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    23.04%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.05%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.49%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    64.15%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.27%  |
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
    "ttft_ms": 252.38,
    "avg_tps": 649.81,
    "min_tps": 491.09,
    "max_tps": 766.08
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 126.08,
    "min_tps": 105.57,
    "max_tps": 143.02,
    "p50_ms": 7.98,
    "p90_ms": 8.54,
    "p99_ms": 9.47,
    "mean_ms": 7.93,
    "jitter_ms": 0.26
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
    "avg_mbs": 1765.72,
    "peak_mbs": 4699.25,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 1.65
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
    "dense_attention": 422.97,
    "moe_compute": 114.06,
    "router_lookahead": 7.58,
    "lm_head": 9.91,
    "unaccounted": 7.18
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 85.9,
    "ram_bandwidth_pinning": 1.71,
    "expert_cache_lrfu": 10.47,
    "lookahead_parallel_overlap": 1.45,
    "ssd_nvme_throughput": 0.47,
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
    "ttft_ms": 304.99,
    "avg_tps": 537.73,
    "min_tps": 361.0,
    "max_tps": 643.36
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 123.15,
    "min_tps": 106.51,
    "max_tps": 132.6,
    "p50_ms": 7.8,
    "p90_ms": 9.06,
    "p99_ms": 9.39,
    "mean_ms": 8.12,
    "jitter_ms": 0.15
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
    "avg_mbs": 1904.5,
    "peak_mbs": 5931.24,
    "sync_wait_ms": 6.75,
    "async_overlap_ms": 17.69
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
    "dense_attention": 354.58,
    "moe_compute": 197.94,
    "router_lookahead": 9.27,
    "lm_head": 9.01,
    "unaccounted": 44.11
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 77.93,
    "ram_bandwidth_pinning": 2.04,
    "expert_cache_lrfu": 10.96,
    "lookahead_parallel_overlap": 5.51,
    "ssd_nvme_throughput": 3.56,
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
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    238.70 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    945.90 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4427.84 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   5911.57 MB/s
   RND4K Q32T16 Read                  :    554.92 MB/s (  142060 IOPS)
   RND4K Q1T1  Read                   :    810.60 MB/s (Latency: 4.82 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     42.38 GB/s
   AVX2 256-bit Sequential Write BW   :     26.27 GB/s
   STREAM Triad (A = B + s*C) BW      :     28.73 GB/s
   Random Pointer-Chase Latency       :    123.31 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     48.69 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    180.30 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     16.83 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 30.99 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 164.11 MB/s (6.24s)
   Window #01 (116.0 MB in 0.51s):   226.57 MB/s (Uncached Direct Read)
   Window #02 (120.0 MB in 0.50s):   239.72 MB/s (Uncached Direct Read)
   Window #03 (124.0 MB in 0.51s):   241.14 MB/s (Uncached Direct Read)
   Window #04 (116.0 MB in 0.50s):   230.95 MB/s (Uncached Direct Read)
   Window #05 (116.0 MB in 0.50s):   231.88 MB/s (Uncached Direct Read)
   Window #06 (120.0 MB in 0.50s):   239.13 MB/s (Uncached Direct Read)
   Window #07 (116.0 MB in 0.51s):   226.59 MB/s (Uncached Direct Read)
   Window #08 (120.0 MB in 0.50s):   239.36 MB/s (Uncached Direct Read)
   Window #09 ( 76.0 MB in 0.32s):   237.18 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   234.60 MB/s (Min=226.57 | Max=241.14 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 238.55 MB/s (4.29s)
   Window #01 (120.0 MB in 0.50s):   240.00 MB/s (Uncached Direct Read)
   Window #02 (120.0 MB in 0.50s):   240.00 MB/s (Uncached Direct Read)
   Window #03 (124.0 MB in 0.52s):   238.46 MB/s (Uncached Direct Read)
   Window #04 (120.0 MB in 0.50s):   239.98 MB/s (Uncached Direct Read)
   Window #05 (120.0 MB in 0.51s):   235.26 MB/s (Uncached Direct Read)
   Window #06 (124.0 MB in 0.52s):   238.53 MB/s (Uncached Direct Read)
   Window #07 (120.0 MB in 0.50s):   239.97 MB/s (Uncached Direct Read)
   Window #08 (120.0 MB in 0.50s):   239.98 MB/s (Uncached Direct Read)
   Window #09 ( 56.0 MB in 0.24s):   233.36 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   238.69 MB/s (Min=233.36 | Max=240.00 MB/s)
================================================================================

================================================================================
 >>> EXECUTING REAL MULTI-SHARD BENCHMARK SUITE FOR TARGET: qwen38 <<<
================================================================================

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (0.010 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 100.00% (0.01/0.01 GB) @ 40.2 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (43.792 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  11.42% (5.00/43.79 GB) @ 240.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  22.84% (10.00/43.79 GB) @ 237.6 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  34.25% (15.00/43.79 GB) @ 230.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  45.67% (20.00/43.79 GB) @ 224.8 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  57.09% (25.00/43.79 GB) @ 215.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  68.51% (30.00/43.79 GB) @ 216.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  79.92% (35.00/43.79 GB) @ 221.9 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf:  91.34% (40.00/43.79 GB) @ 200.7 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00002-of-00003.gguf: 100.00% (43.79/43.79 GB) @ 200.5 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/UD-IQ2_XS/Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (26.822 GB) -> D:/apex_d_drive/models/qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf (Sequential Non-Truncate)
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  18.64% (5.00/26.82 GB) @ 210.5 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  37.28% (10.00/26.82 GB) @ 207.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  55.92% (15.00/26.82 GB) @ 197.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  74.57% (20.00/26.82 GB) @ 93.0 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf:  93.21% (25.00/26.82 GB) @ 77.3 MB/s
  [DL] Qwen3.8-Flash-Next-UD-IQ2_XS-00003-of-00003.gguf: 100.00% (26.82/26.82 GB) @ 81.1 MB/s

[HF-MultiDrive-DL] Streaming unsloth/Qwen3.8-Flash-Next-GGUF/MTP/mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (2.595 GB) -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Sequential Non-Truncate)
  [DL] mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 100.00% (2.60/2.60 GB) @ 139.5 MB/s
  [RAID0-Link] Linked D:/apex_d_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf -> C:/apex_c_drive/models/qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf (Dual-Drive C: + D: active)

[Download Verification] Files=4 | Total Bytes=78,618,661,594 (73.22 GB) | Elapsed=585.17s
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
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7061.89 MB (3403 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=1.41 tps | Avg=1.41 tps | Hit=88.1% | NVMe=243.5 MB/s (10578.12 MB, QD=64) | RSS=12941.6 MB
[LIVE-DECODE] 2/32 tok | Avg=0.78 tps | Hit=88.4% (LA:+0.2%) | NVMe=242.8 MB/s (11028.56 MB) | RSS=12944.5 MB
[LIVE-DECODE] 8/32 tok | Avg=1.02 tps | Hit=89.2% (LA:+0.8%) | NVMe=250.7 MB/s (12231.74 MB) | RSS=12944.6 MB
[LIVE-DECODE] 16/32 tok | Avg=1.17 tps | Hit=90.2% (LA:+1.4%) | NVMe=264.1 MB/s (13640.67 MB) | RSS=12938.3 MB
[LIVE-DECODE] 24/32 tok | Avg=1.30 tps | Hit=91.1% (LA:+1.6%) | NVMe=279.4 MB/s (14781.47 MB) | RSS=12925.7 MB
[LIVE-DECODE] 31/32 tok | Avg=1.37 tps | Hit=91.7% (LA:+1.6%) | NVMe=291.5 MB/s (15706.04 MB) | RSS=12919.9 MB

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
   LRFU Cache / Staging Ring    : 7061.89 MB (3403/25088 exp = 13.56% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=12919.93 MB | Peak=13414.97 MB
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
   |    1 |     264 |  a             |   13.79 |  18.1% |     303 |   13.43 | 45470.82 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    9.55 |   2.3% |     467 |    8.54 | 1284.13 |874 | 60 | 26 | 230626.5 |
   |    3 |      11 | ,              |   13.78 |  50.0% |     198 |   12.15 | 1284.13 |  0 |  0 |  0 | 230626.5 |
   |    4 |     198 | \n             |   11.28 |  20.5% |     364 |    8.50 |  967.55 |429 | 40 | 11 | 227664.0 |
   |    5 |     277 | ar             |    9.86 |   2.9% |     261 |    9.53 |  991.16 |402 | 68 | 10 | 236389.0 |
   |    6 |      11 | ,              |    9.33 |   3.0% |      16 |    9.11 |  997.33 |427 | 42 | 11 | 233289.0 |
   |    7 |     198 | \n             |    9.90 |   8.3% |     286 |    7.83 |  930.84 |439 | 35 |  6 | 230714.0 |
   |    8 |     286 | ing            |    9.16 |   2.7% |     278 |    8.60 |  692.75 |455 | 21 |  4 | 138264.0 |
   |   14 |      17 | 2              |    9.40 |   4.0% |      15 |    8.88 |  967.65 |415 | 51 | 14 | 237914.0 |
   |   12 |      17 | 2              |    7.65 |   0.5% |     365 |    6.83 |  856.14 |435 | 32 | 13 | 206189.0 |
   |   15 |     198 | \n             |   11.71 |  23.3% |      17 |   11.53 |  795.06 |434 | 38 |  8 | 195443.0 |
   |   25 |     198 | \n             |   10.81 |  12.2% |      15 |   10.44 |  785.07 |423 | 50 |  7 | 229789.0 |
   |   29 |     198 | \n             |   11.56 |  29.2% |     271 |    9.34 |  564.47 |471 |  9 |  0 | 129368.0 |
   |   30 |      15 | 0              |    9.43 |   3.3% |      17 |    9.40 |  562.72 |473 |  7 |  0 | 129714.0 |
   |   31 |      16 | 1              |    9.74 |   4.3% |      17 |    9.38 |  601.56 |460 | 19 |  1 | 163964.0 |
   |   32 |     198 | \n             |   11.79 |  32.8% |      17 |    9.29 |  621.60 |460 | 18 |  2 | 163264.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 45.471s, TTFT=45470.82ms): Avg=1.41 | Min=1.41 | Max=1.41 tps
   Prefill Chunks (1): C1:64t/1.4tps/88%
   Decode  (31 tok, 22.554s): Avg=1.37 | Min=0.78 | Max=1.79 tps
   Latency (ms) : Min=558.78 | P10=563.66 | P25=575.56 | P50=623.43 | P75=856.14 | P90=991.16 | P95=1284.13 | P99=1284.13 | Max=1284.13
   Mean/SD/Jitt : Mean=727.55ms | StdDev=205.30ms | Jitter=79.28ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/31
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (45600): RawRAM=41079 (90.09%) | Lookahead=743 (+1.63%) | ColdMiss=3778 (8.29%) | EFF HIT=91.71%
   Lookahead    : 2985 prefetched -> 753 consumed (25.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  950 |  658 |  78 | 214 | 77.5%| 491.89 | | L24 |  950 |  892 |   9 |  49 | 94.8%| 142.87 |
   | L01 |  950 |  813 |  43 |  94 | 90.1%| 413.38 | | L25 |  950 |  890 |   8 |  52 | 94.5%| 114.67 |
   | L02 |  950 |  829 |  11 | 110 | 88.4%| 439.67 | | L26 |  950 |  866 |  15 |  69 | 92.7%| 199.27 |
   | L03 |  950 |  892 |   1 |  57 | 94.0%| 505.69 | | L27 |  950 |  868 |  16 |  66 | 93.1%| 225.59 |
   | L04 |  950 |  886 |   4 |  60 | 93.7%| 228.27 | | L28 |  950 |  833 |  27 |  90 | 90.5%| 327.10 |
   | L05 |  950 |  870 |   5 |  75 | 92.1%| 280.10 | | L29 |  950 |  857 |  14 |  79 | 91.7%| 171.41 |
   | L06 |  950 |  868 |  16 |  66 | 93.1%| 218.07 | | L30 |  950 |  820 |  27 | 103 | 89.2%| 233.35 |
   | L07 |  950 |  869 |  19 |  62 | 93.5%| 153.30 | | L31 |  950 |  828 |  22 | 100 | 89.5%| 226.15 |
   | L08 |  950 |  902 |   8 |  40 | 95.8%| 103.34 | | L32 |  950 |  850 |  18 |  82 | 91.4%| 266.94 |
   | L09 |  950 |  892 |   5 |  53 | 94.4%| 100.85 | | L33 |  950 |  843 |  20 |  87 | 90.8%| 188.70 |
   | L10 |  950 |  884 |   9 |  57 | 94.0%| 113.31 | | L34 |  950 |  848 |  15 |  87 | 90.8%| 187.26 |
   | L11 |  950 |  895 |   5 |  50 | 94.7%| 128.25 | | L35 |  950 |  868 |  12 |  70 | 92.6%| 133.96 |
   | L12 |  950 |  869 |  15 |  66 | 93.1%| 229.35 | | L36 |  950 |  849 |  15 |  86 | 90.9%| 305.37 |
   | L13 |  950 |  863 |  14 |  73 | 92.3%| 145.48 | | L37 |  950 |  871 |  12 |  67 | 92.9%| 159.79 |
   | L14 |  950 |  844 |  27 |  79 | 91.7%| 252.08 | | L38 |  950 |  875 |   6 |  69 | 92.7%| 246.26 |
   | L15 |  950 |  853 |  14 |  83 | 91.3%| 250.02 | | L39 |  950 |  863 |  11 |  76 | 92.0%| 270.70 |
   | L16 |  950 |  868 |  10 |  72 | 92.4%| 180.47 | | L40 |  950 |  848 |  11 |  91 | 90.4%| 281.98 |
   | L17 |  950 |  868 |  11 |  71 | 92.5%| 216.19 | | L41 |  950 |  849 |  12 |  89 | 90.6%| 152.69 |
   | L18 |  950 |  863 |  17 |  70 | 92.6%| 206.79 | | L42 |  950 |  824 |  14 | 112 | 88.2%| 289.53 |
   | L19 |  950 |  875 |   7 |  68 | 92.8%| 151.25 | | L43 |  950 |  858 |  13 |  79 | 91.7%| 200.22 |
   | L20 |  950 |  838 |  21 |  91 | 90.4%| 200.22 | | L44 |  950 |  848 |  14 |  88 | 90.7%| 165.65 |
   | L21 |  950 |  827 |  21 | 102 | 89.3%| 407.93 | | L45 |  950 |  823 |  28 |  99 | 89.6%| 270.80 |
   | L22 |  950 |  883 |  10 |  57 | 94.0%| 210.55 | | L46 |  950 |  877 |   7 |  66 | 93.1%| 243.43 |
   | L23 |  950 |  871 |  14 |  65 | 93.2%| 144.04 | | L47 |  950 |  851 |  12 |  87 | 90.8%| 261.30 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 15706.04 MB (Load=4614.69 | Prefill=5963.42 | Warmup=0.00 | Decode=5127.92 MB)
   SSD Data/Token (Decode)      : Avg=165.417 MB/tok (Min=111.517 | P50=149.798 | P95=230.849 | Max=232.338 MB) | Prefill=93.178 MB/tok
   NVMe Batches / Requests      : 1506 Batches | 22917 Raw -> 22142 Merged (775 LBA Merges, Avg 726.4 KB/io)
   SSD I/O Size Histogram       : <64K=1835 | 64K-512K=5562 | 512K-2M=14311 | >2M=434
   SSD Read Bandwidth (Active)  : Min=4.80 | Avg=291.48 | Peak=5168.37 MB/s | WallAmort=230.89 MB/s
   OS Kernel I/O Verification   : Read=15726.01 MB | Write=0.00 MB | Syscalls=31645
   Sync Stall vs Async DMA      : SyncStall=25391.39 ms | AsyncOverlapped=34997.93 ms (58.0% Overlapped)
   RAM Traffic & Active BW      : 392.99 GB moved | Active=10.57 GB/s | WallAmort=5.78 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=45.47s (66.8%, 5963.42 MB SSD) | Decode=22.55s (33.2%, 5127.92 MB SSD)
   CPU Time & Utilization       : User=116.656s + Sys=8.938s (Wall=94.506s) | SysUtil=33.2% | ThrUtil=33.2% | 30.73 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  19583.11 ms (206138.0 us/tok | 28.79%)
   MoE AVX2 Q8 Expert Compute   :  16378.86 ms (172409.1 us/tok | 24.08%)
   Router + Lookahead Dispatch  :   1023.44 ms (10773.1 us/tok |  1.50%)
   LM Head Output Projection    :   1225.55 ms (12900.5 us/tok |  1.80%)
   Foreground NVMe Sync Stall   :  25391.39 ms (267277.8 us/tok | 37.33%)
   Unaccounted / OMP & Sampling :   4422.45 ms (46552.1 us/tok |  6.50%) | Total Wall=68024.81 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    80.21%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.69%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     9.05%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.25%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.80%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

[Apex-Fair-Baseline] 64p/32g completed in 96s

================================================================================
   APEX INFERENCE v1 — PRE-FLIGHT HOST HARDWARE TELEMETRY & BENCHMARK REPORT
   (CrystalDiskMark NVMe Profile + PassMark PerformanceTest CPU/RAM Suite)
================================================================================
 [Host System Specifications]
   OS Platform        : Windows 11 / Server 2025 (x86_64)
   CPU Model          : INTEL(R) XEON(R) PLATINUM 8573C
   Cores / Threads    : 2 Physical / 4 Logical
   SIMD ISA Support   : AVX2=YES | FMA=YES | F16C=YES | AVX-VNNI=NO | AVX512-VNNI=YES
   System Memory (RAM): 15.99 GB Total / 14.58 GB Available
   Active Drive Space : 150.00 GB Total / 76.31 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    222.45 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    945.58 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   3575.13 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   6902.54 MB/s
   RND4K Q32T16 Read                  :    477.29 MB/s (  122187 IOPS)
   RND4K Q1T1  Read                   :    640.84 MB/s (Latency: 6.10 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     39.46 GB/s
   AVX2 256-bit Sequential Write BW   :     22.28 GB/s
   STREAM Triad (A = B + s*C) BW      :     28.16 GB/s
   Random Pointer-Chase Latency       :    191.87 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     45.18 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :     87.81 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     13.41 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=1.59 tps | Avg=1.59 tps | Hit=90.0% | NVMe=241.3 MB/s (11789.75 MB, QD=64) | RSS=13431.8 MB

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
   LRFU Cache / Staging Ring    : 7553.71 MB (3640/25088 exp = 14.51% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13380.36 MB | Peak=13910.10 MB
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
   |    1 |      65 | b              |    9.34 |   1.9% |      79 |    9.00 | 57315.17 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |   10.69 |  14.6% |     271 |    7.46 |  878.29 |902 | 54 |  4 | 147653.5 |
   |    3 |      15 | 0              |    9.12 |   1.0% |      79 |    8.96 |  878.29 |  0 |  0 |  0 | 147653.5 |
   |    4 |     198 | \n             |   11.23 |  26.1% |      65 |    7.68 |  837.20 |444 | 31 |  5 | 169014.0 |
   |    5 |      17 | 2              |    7.61 |   0.8% |      15 |    7.44 |  564.19 |472 |  8 |  0 | 89543.0 |
   |    6 |      17 | 2              |    9.33 |   3.4% |      16 |    8.85 |  764.82 |450 | 27 |  3 | 153389.0 |
   |    7 |      17 | 2              |   10.09 |   7.7% |      24 |   10.02 |  749.42 |440 | 31 |  9 | 176893.0 |
   |    8 |      22 | 7              |   11.04 |   9.6% |      17 |   10.99 |  634.02 |451 | 26 |  3 | 137218.0 |
   |   10 |      24 | 9              |   10.61 |   9.0% |      17 |   10.51 |  701.92 |450 | 24 |  6 | 164414.0 |
   |   33 |      17 | 2              |   11.35 |  15.6% |      18 |   10.52 |  666.90 |455 | 21 |  4 | 132564.0 |
   |   59 |      17 | 2              |   12.29 |  13.6% |      15 |   12.07 |  661.08 |452 | 27 |  1 | 158764.0 |
   |   11 |     198 | \n             |   11.25 |  22.6% |      16 |   10.26 |  656.01 |448 | 28 |  4 | 168889.0 |
   |   61 |      17 | 2              |   11.98 |  21.6% |      18 |   11.12 |  557.60 |478 |  2 |  0 | 117014.0 |
   |   62 |      16 | 1              |   12.20 |  17.7% |      17 |   12.06 |  558.84 |476 |  4 |  0 | 119168.0 |
   |   63 |      17 | 2              |   13.90 |  25.0% |      18 |   13.58 |  571.88 |479 |  1 |  0 | 100743.0 |
   |   64 |      17 | 2              |   12.55 |  17.2% |      16 |   12.28 |  552.11 |474 |  6 |  0 | 67443.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 57.315s, TTFT=57315.17ms): Avg=1.59 | Min=1.59 | Max=1.59 tps
   Prefill Chunks (1): C1:91t/1.6tps/90%
   Decode  (63 tok, 37.322s): Avg=1.69 | Min=1.14 | Max=1.85 tps
   Latency (ms) : Min=539.59 | P10=548.32 | P25=552.66 | P50=561.61 | P75=591.82 | P90=666.90 | P95=764.82 | P99=878.29 | Max=878.29
   Mean/SD/Jitt : Mean=592.42ms | StdDev=76.00ms | Jitter=32.73ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (73920): RawRAM=68887 (93.19%) | Lookahead=618 (+0.84%) | ColdMiss=4415 (5.97%) | EFF HIT=94.03%
   Lookahead    : 3808 prefetched -> 628 consumed (16.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 91.4% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1233 |  42 | 265 | 82.8%| 517.16 | | L24 | 1540 | 1480 |   4 |  56 | 96.4%| 144.75 |
   | L01 | 1540 | 1406 |  22 | 112 | 92.7%| 572.75 | | L25 | 1540 | 1464 |  10 |  66 | 95.7%| 150.39 |
   | L02 | 1540 | 1392 |   6 | 142 | 90.8%| 790.06 | | L26 | 1540 | 1433 |  14 |  93 | 94.0%| 246.26 |
   | L03 | 1540 | 1475 |   1 |  64 | 95.8%| 735.03 | | L27 | 1540 | 1456 |   9 |  75 | 95.1%| 197.39 |
   | L04 | 1540 | 1465 |   0 |  75 | 95.1%| 228.27 | | L28 | 1540 | 1383 |  36 | 121 | 92.1%| 421.09 |
   | L05 | 1540 | 1452 |   3 |  85 | 94.5%| 317.70 | | L29 | 1540 | 1425 |  23 |  92 | 94.0%| 256.40 |
   | L06 | 1540 | 1439 |  12 |  89 | 94.2%| 242.50 | | L30 | 1540 | 1393 |  27 | 120 | 92.2%| 290.97 |
   | L07 | 1540 | 1443 |  11 |  86 | 94.4%| 220.68 | | L31 | 1540 | 1402 |  21 | 117 | 92.4%| 273.68 |
   | L08 | 1540 | 1485 |   2 |  53 | 96.6%| 113.31 | | L32 | 1540 | 1439 |   8 |  93 | 94.0%| 306.42 |
   | L09 | 1540 | 1476 |   4 |  60 | 96.1%| 136.96 | | L33 | 1540 | 1411 |  34 |  95 | 93.8%| 208.86 |
   | L10 | 1540 | 1459 |   3 |  78 | 94.9%| 120.78 | | L34 | 1540 | 1420 |  23 |  97 | 93.7%| 217.50 |
   | L11 | 1540 | 1475 |   2 |  63 | 95.9%| 140.70 | | L35 | 1540 | 1451 |  14 |  75 | 95.1%| 149.80 |
   | L12 | 1540 | 1441 |  10 |  89 | 94.2%| 298.90 | | L36 | 1540 | 1424 |  14 | 102 | 93.4%| 252.08 |
   | L13 | 1540 | 1438 |  13 |  89 | 94.2%| 154.13 | | L37 | 1540 | 1446 |  13 |  81 | 94.7%| 195.51 |
   | L14 | 1540 | 1425 |  17 |  98 | 93.6%| 338.50 | | L38 | 1540 | 1457 |   9 |  74 | 95.2%| 272.58 |
   | L15 | 1540 | 1431 |  11 |  98 | 93.6%| 310.18 | | L39 | 1540 | 1440 |   9 |  91 | 94.1%| 349.66 |
   | L16 | 1540 | 1439 |   9 |  92 | 94.0%| 223.71 | | L40 | 1540 | 1425 |  11 | 104 | 93.2%| 355.30 |
   | L17 | 1540 | 1441 |   6 |  93 | 94.0%| 250.02 | | L41 | 1540 | 1437 |  10 |  93 | 94.0%| 171.41 |
   | L18 | 1540 | 1439 |  12 |  89 | 94.2%| 199.27 | | L42 | 1540 | 1411 |  26 | 103 | 93.3%| 306.81 |
   | L19 | 1540 | 1458 |   9 |  73 | 95.3%| 162.77 | | L43 | 1540 | 1453 |  11 |  76 | 95.1%| 256.40 |
   | L20 | 1540 | 1423 |  13 | 104 | 93.2%| 270.80 | | L44 | 1540 | 1433 |  18 |  89 | 94.2%| 276.56 |
   | L21 | 1540 | 1424 |  15 | 101 | 93.4%| 330.86 | | L45 | 1540 | 1432 |  19 |  89 | 94.2%| 302.49 |
   | L22 | 1540 | 1467 |   3 |  70 | 95.5%| 321.46 | | L46 | 1540 | 1467 |   6 |  67 | 95.6%| 334.18 |
   | L23 | 1540 | 1430 |  16 |  94 | 93.9%| 226.15 | | L47 | 1540 | 1449 |   7 |  84 | 94.5%| 214.31 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 18047.80 MB (Load=4614.69 | Prefill=7175.05 | Warmup=0.00 | Decode=6258.06 MB)
   SSD Data/Token (Decode)      : Avg=99.334 MB/tok (Min=45.135 | P50=90.199 | P95=160.561 | Max=172.747 MB) | Prefill=78.847 MB/tok
   NVMe Batches / Requests      : 2119 Batches | 28241 Raw -> 27219 Merged (1022 LBA Merges, Avg 679.0 KB/io)
   SSD I/O Size Histogram       : <64K=2674 | 64K-512K=7083 | 512K-2M=17028 | >2M=434
   SSD Read Bandwidth (Active)  : Min=4.73 | Avg=310.27 | Peak=5068.44 MB/s | WallAmort=190.70 MB/s (100.0% of 222.4 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=19045.39 MB | Write=128.00 MB | Syscalls=44271
   Sync Stall vs Async DMA      : SyncStall=30144.86 ms | AsyncOverlapped=39232.91 ms (56.5% Overlapped)
   RAM Traffic & Active BW      : 695.74 GB moved | Active=11.68 GB/s (41.5% STREAM) | WallAmort=7.35 GB/s (Max=28.16 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=57.32s (60.6%, 7175.05 MB SSD) | Decode=37.32s (39.4%, 6258.06 MB SSD)
   CPU Time & Utilization       : User=193.844s + Sys=12.922s (Wall=122.965s) | SysUtil=42.0% | ThrUtil=42.0% | 36.91 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  32236.92 ms (209330.6 us/tok | 34.06%)
   MoE AVX2 Q8 Expert Compute   :  25051.91 ms (162674.7 us/tok | 26.47%)
   Router + Lookahead Dispatch  :   1672.81 ms (10862.4 us/tok |  1.77%)
   LM Head Output Projection    :   2273.72 ms (14764.4 us/tok |  2.40%)
   Foreground NVMe Sync Stall   :  30144.86 ms (195745.8 us/tok | 31.85%)
   Unaccounted / OMP & Sampling :   3257.45 ms (21152.3 us/tok |  3.44%) | Total Wall=94637.67 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    83.55%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.41%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     6.67%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.50%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.87%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 2] Medium Prompt (512 tokens) + Domain Cache Warmup Trajectory (@16..@512)
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7773.68 MB (3746 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=2.28 tps | Avg=2.28 tps | Hit=95.4% | NVMe=241.9 MB/s (13785.34 MB, QD=64) | RSS=13712.8 MB
[LIVE-PREFILL] 512/512 tok | Chunk=2.80 tps | Avg=2.52 tps | Hit=96.7% | NVMe=242.0 MB/s (17920.18 MB, QD=64) | RSS=13714.3 MB
[LIVE-DECODE] 2/128 tok | Avg=1.10 tps | Hit=96.7% (LA:+0.0%) | NVMe=243.7 MB/s (18327.46 MB) | RSS=13710.8 MB
[LIVE-DECODE] 8/128 tok | Avg=1.49 tps | Hit=96.7% (LA:+0.1%) | NVMe=254.1 MB/s (19341.41 MB) | RSS=13710.2 MB
[LIVE-DECODE] 16/128 tok | Avg=1.38 tps | Hit=96.8% (LA:+0.1%) | NVMe=262.7 MB/s (20862.08 MB) | RSS=13621.8 MB
[LIVE-DECODE] 24/128 tok | Avg=1.45 tps | Hit=96.8% (LA:+0.2%) | NVMe=274.5 MB/s (22185.64 MB) | RSS=13606.4 MB
[LIVE-DECODE] 32/128 tok | Avg=1.52 tps | Hit=96.9% (LA:+0.3%) | NVMe=285.2 MB/s (23296.59 MB) | RSS=13606.1 MB
[LIVE-DECODE] 40/128 tok | Avg=1.54 tps | Hit=96.9% (LA:+0.3%) | NVMe=296.1 MB/s (24511.24 MB) | RSS=13584.9 MB
[LIVE-DECODE] 48/128 tok | Avg=1.57 tps | Hit=97.0% (LA:+0.3%) | NVMe=306.6 MB/s (25649.77 MB) | RSS=13584.9 MB
[LIVE-DECODE] 56/128 tok | Avg=1.60 tps | Hit=97.0% (LA:+0.3%) | NVMe=317.5 MB/s (26781.41 MB) | RSS=13584.8 MB
[LIVE-DECODE] 64/128 tok | Avg=1.61 tps | Hit=97.0% (LA:+0.4%) | NVMe=326.7 MB/s (27825.03 MB) | RSS=13584.8 MB
[LIVE-DECODE] 72/128 tok | Avg=1.62 tps | Hit=97.1% (LA:+0.4%) | NVMe=336.5 MB/s (28929.25 MB) | RSS=13584.8 MB
[LIVE-DECODE] 80/128 tok | Avg=1.64 tps | Hit=97.1% (LA:+0.4%) | NVMe=347.2 MB/s (30109.80 MB) | RSS=13584.8 MB
[LIVE-DECODE] 88/128 tok | Avg=1.65 tps | Hit=97.2% (LA:+0.4%) | NVMe=356.8 MB/s (31221.41 MB) | RSS=13580.7 MB
[LIVE-DECODE] 96/128 tok | Avg=1.65 tps | Hit=97.2% (LA:+0.4%) | NVMe=366.3 MB/s (32331.28 MB) | RSS=13580.7 MB
[LIVE-DECODE] 104/128 tok | Avg=1.66 tps | Hit=97.2% (LA:+0.5%) | NVMe=376.0 MB/s (33469.87 MB) | RSS=13580.7 MB
[LIVE-DECODE] 112/128 tok | Avg=1.67 tps | Hit=97.3% (LA:+0.5%) | NVMe=385.9 MB/s (34655.95 MB) | RSS=13580.7 MB
[LIVE-DECODE] 120/128 tok | Avg=1.67 tps | Hit=97.3% (LA:+0.5%) | NVMe=395.4 MB/s (35831.15 MB) | RSS=13581.3 MB
[LIVE-DECODE] 127/128 tok | Avg=1.68 tps | Hit=97.3% (LA:+0.5%) | NVMe=403.2 MB/s (36794.59 MB) | RSS=13581.3 MB

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
   LRFU Cache / Staging Ring    : 7773.68 MB (3746/25088 exp = 14.93% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.73 MB | End=13581.27 MB | Peak=14148.64 MB
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
   |    1 |      17 | 2              |   11.64 |   9.2% |      18 |   11.26 | 203453.54 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |   10.56 |   7.0% |      16 |    9.87 |  909.48 |899 | 50 | 11 | 208528.5 |
   |    3 |      17 | 2              |   11.11 |  10.8% |      18 |   10.99 |  909.48 |  0 |  0 |  0 | 208528.5 |
   |    4 |      17 | 2              |   11.51 |  15.9% |      22 |   10.88 |  638.08 |449 | 31 |  0 | 199468.0 |
   |    5 |      17 | 2              |    9.67 |   3.5% |      16 |    9.10 |  581.02 |469 | 11 |  0 | 162718.0 |
   |    6 |      17 | 2              |   11.31 |  11.8% |      18 |   11.07 |  556.91 |473 |  7 |  0 | 160593.0 |
   |    7 |      17 | 2              |   10.93 |   8.5% |      18 |   10.14 |  576.55 |466 | 13 |  1 | 158743.0 |
   |    8 |      17 | 2              |   11.36 |  11.1% |      18 |   11.13 |  563.95 |468 | 12 |  0 | 172443.0 |
   |   14 |      90 | {              |    7.71 |   0.7% |      64 |    7.56 |  981.80 |448 | 25 |  7 | 197939.0 |
   |   15 |     198 | \n             |    8.95 |   2.8% |      16 |    7.61 |  946.60 |435 | 35 | 10 | 217564.0 |
   |   13 |     286 | ing            |    8.50 |   1.4% |      68 |    7.85 |  925.89 |435 | 34 | 11 | 201618.0 |
   |   16 |      17 | 2              |    8.90 |   1.7% |     286 |    8.88 |  763.62 |434 | 41 |  5 | 200639.0 |
   |  125 |      17 | 2              |   11.67 |  19.1% |      18 |   10.97 |  562.39 |472 |  8 |  0 | 129139.0 |
   |  126 |      17 | 2              |   12.31 |  21.8% |     198 |   11.75 |  567.11 |469 | 11 |  0 | 143064.0 |
   |  127 |      17 | 2              |   10.79 |  11.3% |      16 |   10.64 |  551.52 |478 |  2 |  0 | 127793.0 |
   |  128 |      17 | 2              |   12.08 |  19.1% |      18 |   11.55 |  556.73 |475 |  5 |  0 | 152568.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 203.454s, TTFT=203453.54ms): Avg=2.52 | Min=2.28 | Max=2.80 tps
   Prefill Chunks (2): C1:256t/2.3tps/95% | C2:256t/2.8tps/97%
   Decode  (127 tok, 75.740s): Avg=1.68 | Min=1.02 | Max=1.82 tps
   Latency (ms) : Min=549.78 | P10=556.73 | P25=561.54 | P50=573.63 | P75=596.70 | P90=652.96 | P95=677.04 | P99=946.60 | Max=981.80
   Mean/SD/Jitt : Mean=596.38ms | StdDev=75.73ms | Jitter=27.75ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/127
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (306720): RawRAM=297008 (96.83%) | Lookahead=1520 (+0.50%) | ColdMiss=8192 (2.67%) | EFF HIT=97.33%
   Lookahead    : 11424 prefetched -> 1530 consumed (13.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.8% | @64= 97.0% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 6390 | 5713 | 136 | 541 | 91.5%|1140.45 | | L24 | 6390 | 6289 |   3 |  98 | 98.5%| 221.83 |
   | L01 | 6390 | 6128 |  72 | 190 | 97.0%|1497.88 | | L25 | 6390 | 6293 |   7 |  90 | 98.6%| 231.23 |
   | L02 | 6390 | 6138 |  21 | 231 | 96.4%|1561.60 | | L26 | 6390 | 6162 |  49 | 179 | 97.2%| 524.49 |
   | L03 | 6390 | 6316 |   1 |  73 | 98.9%|2229.54 | | L27 | 6390 | 6254 |  20 | 116 | 98.2%| 479.37 |
   | L04 | 6390 | 6276 |   3 | 111 | 98.3%| 676.51 | | L28 | 6390 | 6134 |  49 | 207 | 96.8%| 699.32 |
   | L05 | 6390 | 6233 |  16 | 141 | 97.8%|1146.73 | | L29 | 6390 | 6186 |  38 | 166 | 97.4%| 515.67 |
   | L06 | 6390 | 6250 |  18 | 122 | 98.1%| 656.08 | | L30 | 6390 | 6097 |  59 | 234 | 96.3%| 553.12 |
   | L07 | 6390 | 6242 |  11 | 137 | 97.9%| 528.96 | | L31 | 6390 | 6117 |  60 | 213 | 96.7%| 594.90 |
   | L08 | 6390 | 6319 |   3 |  68 | 98.9%| 250.27 | | L32 | 6390 | 6185 |  36 | 169 | 97.4%| 746.31 |
   | L09 | 6390 | 6318 |   4 |  68 | 98.9%| 107.08 | | L33 | 6390 | 6137 |  54 | 199 | 96.9%| 472.46 |
   | L10 | 6390 | 6284 |   5 | 101 | 98.4%| 174.32 | | L34 | 6390 | 6044 |  84 | 262 | 95.9%| 639.55 |
   | L11 | 6390 | 6321 |   2 |  67 | 99.0%| 180.54 | | L35 | 6390 | 6198 |  33 | 159 | 97.5%| 452.29 |
   | L12 | 6390 | 6277 |   5 | 108 | 98.3%| 629.76 | | L36 | 6390 | 6197 |  31 | 162 | 97.5%| 471.02 |
   | L13 | 6390 | 6237 |  24 | 129 | 98.0%| 252.08 | | L37 | 6390 | 6166 |  34 | 190 | 97.0%| 513.21 |
   | L14 | 6390 | 6222 |  39 | 129 | 98.0%| 623.71 | | L38 | 6390 | 6240 |  16 | 134 | 97.9%| 697.44 |
   | L15 | 6390 | 6186 |  36 | 168 | 97.4%| 565.84 | | L39 | 6390 | 6196 |  26 | 168 | 97.4%| 924.90 |
   | L16 | 6390 | 6190 |  17 | 183 | 97.1%| 485.01 | | L40 | 6390 | 6184 |  36 | 170 | 97.3%| 866.63 |
   | L17 | 6390 | 6174 |  18 | 198 | 96.9%| 603.44 | | L41 | 6390 | 6210 |  12 | 168 | 97.4%| 384.59 |
   | L18 | 6390 | 6173 |  31 | 186 | 97.1%| 565.84 | | L42 | 6390 | 6059 |  82 | 249 | 96.1%| 728.86 |
   | L19 | 6390 | 6220 |  15 | 155 | 97.6%| 329.86 | | L43 | 6390 | 6107 |  40 | 243 | 96.2%| 816.72 |
   | L20 | 6390 | 6124 |  29 | 237 | 96.3%| 882.98 | | L44 | 6390 | 6069 |  60 | 261 | 95.9%| 792.24 |
   | L21 | 6390 | 6144 |  33 | 213 | 96.7%|1315.92 | | L45 | 6390 | 6048 |  84 | 258 | 96.0%| 939.16 |
   | L22 | 6390 | 6284 |   4 | 102 | 98.4%| 419.21 | | L46 | 6390 | 6264 |  14 | 112 | 98.2%| 849.85 |
   | L23 | 6390 | 6199 |  30 | 161 | 97.5%| 616.50 | | L47 | 6390 | 6204 |  20 | 166 | 97.4%| 533.89 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 36794.59 MB (Load=4614.69 | Prefill=13305.49 | Warmup=0.00 | Decode=18874.41 MB)
   SSD Data/Token (Decode)      : Avg=148.617 MB/tok (Min=79.311 | P50=145.550 | P95=190.028 | Max=212.465 MB) | Prefill=25.987 MB/tok
   NVMe Batches / Requests      : 5285 Batches | 70180 Raw -> 68322 Merged (1858 LBA Merges, Avg 551.5 KB/io)
   SSD I/O Size Histogram       : <64K=10481 | 64K-512K=15800 | 512K-2M=41593 | >2M=448
   SSD Read Bandwidth (Active)  : Min=4.71 | Avg=403.20 | Peak=5180.88 MB/s | WallAmort=131.79 MB/s
   OS Kernel I/O Verification   : Read=36814.72 MB | Write=0.00 MB | Syscalls=77838
   Sync Stall vs Async DMA      : SyncStall=55132.81 ms | AsyncOverlapped=72319.82 ms (56.7% Overlapped)
   RAM Traffic & Active BW      : 2226.07 GB moved | Active=10.56 GB/s | WallAmort=7.97 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=203.45s (72.9%, 13305.49 MB SSD) | Decode=75.74s (27.1%, 18874.41 MB SSD)
   CPU Time & Utilization       : User=732.281s + Sys=27.219s (Wall=305.593s) | SysUtil=62.1% | ThrUtil=62.1% | 57.47 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 109454.19 ms (171289.8 us/tok | 39.20%)
   MoE AVX2 Q8 Expert Compute   :  96734.07 ms (151383.5 us/tok | 34.65%)
   Router + Lookahead Dispatch  :   6115.45 ms ( 9570.3 us/tok |  2.19%)
   LM Head Output Projection    :   4579.87 ms ( 7167.2 us/tok |  1.64%)
   Foreground NVMe Sync Stall   :  55132.81 ms (86279.8 us/tok | 19.75%)
   Unaccounted / OMP & Sampling :   7177.15 ms (11231.8 us/tok |  2.57%) | Total Wall=279193.54 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    87.28%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.11%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.48%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.01%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.12%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 3] Live OpenAI HTTP/SSE/Tool-Calling/Concurrent Stress Test on Real Shards
--------------------------------------------------------------------------------
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 33116.9ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\nu\n\n\nb2\n\n2\n\nu\n22'
[Stage 3] /v1/chat/completions (stream=true SSE) 7098.3ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
--------------------------------------------------------------------------------
 [Stage 4] Massive 2,048-Token Prompt (High KV Load) + MTP Always ON
--------------------------------------------------------------------------------
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6736.08 MB (3246 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2.31 tps | Avg=2.31 tps | Hit=95.4% | NVMe=242.9 MB/s (13785.34 MB, QD=64) | RSS=12696.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.76 tps | Avg=2.51 tps | Hit=96.5% | NVMe=247.3 MB/s (18878.21 MB, QD=64) | RSS=12712.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.84 tps | Avg=2.61 tps | Hit=96.8% | NVMe=256.4 MB/s (23644.17 MB, QD=64) | RSS=12711.5 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.83 tps | Avg=2.66 tps | Hit=97.0% | NVMe=264.4 MB/s (28400.75 MB, QD=64) | RSS=12721.2 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.82 tps | Avg=2.69 tps | Hit=97.2% | NVMe=271.0 MB/s (33089.62 MB, QD=64) | RSS=12721.1 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.82 tps | Avg=2.71 tps | Hit=97.3% | NVMe=276.5 MB/s (37768.73 MB, QD=64) | RSS=12720.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.76 tps | Avg=2.72 tps | Hit=97.3% | NVMe=279.9 MB/s (42475.39 MB, QD=64) | RSS=12720.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.76 tps | Avg=2.72 tps | Hit=97.4% | NVMe=283.0 MB/s (47007.18 MB, QD=64) | RSS=12704.3 MB
[LIVE-DECODE] 2/64 tok | Avg=0.94 tps | Hit=97.4% (LA:+0.0%) | NVMe=284.1 MB/s (47571.66 MB) | RSS=12705.2 MB
[LIVE-DECODE] 8/64 tok | Avg=1.18 tps | Hit=97.4% (LA:+0.0%) | NVMe=287.9 MB/s (48883.28 MB) | RSS=12705.2 MB
[LIVE-DECODE] 16/64 tok | Avg=1.32 tps | Hit=97.4% (LA:+0.1%) | NVMe=294.7 MB/s (50537.65 MB) | RSS=12705.2 MB
[LIVE-DECODE] 24/64 tok | Avg=1.39 tps | Hit=97.4% (LA:+0.1%) | NVMe=301.6 MB/s (52053.16 MB) | RSS=12705.2 MB
[LIVE-DECODE] 32/64 tok | Avg=1.44 tps | Hit=97.4% (LA:+0.1%) | NVMe=308.4 MB/s (53510.06 MB) | RSS=12701.4 MB
[LIVE-DECODE] 40/64 tok | Avg=1.48 tps | Hit=97.4% (LA:+0.1%) | NVMe=314.6 MB/s (54850.17 MB) | RSS=12701.4 MB
[LIVE-DECODE] 48/64 tok | Avg=1.49 tps | Hit=97.4% (LA:+0.1%) | NVMe=321.4 MB/s (56460.99 MB) | RSS=12701.3 MB
[LIVE-DECODE] 56/64 tok | Avg=1.48 tps | Hit=97.4% (LA:+0.2%) | NVMe=327.6 MB/s (58206.49 MB) | RSS=12701.3 MB
[LIVE-DECODE] 63/64 tok | Avg=1.49 tps | Hit=97.4% (LA:+0.2%) | NVMe=333.4 MB/s (59578.15 MB) | RSS=12701.3 MB

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
   LRFU Cache / Staging Ring    : 6736.08 MB (3246/25088 exp = 12.94% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.75 MB | End=12701.29 MB | Peak=13113.93 MB
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
   |    1 |     198 | \n             |    7.38 |   0.7% |      17 |    7.24 | 751717.74 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |    8.16 |   1.8% |      17 |    8.01 | 1063.26 |817 |120 | 23 | 289018.0 |
   |    3 |     198 | \n             |   11.22 |  32.9% |      16 |    8.68 | 1063.26 |  0 |  0 |  0 | 289018.0 |
   |    4 |      84 | u              |    8.57 |   2.2% |     198 |    8.18 |  741.55 |429 | 49 |  2 | 203793.0 |
   |    5 |      17 | 2              |    8.16 |   0.8% |      18 |    8.11 |  804.27 |438 | 34 |  8 | 236339.0 |
   |    6 |      16 | 1              |    9.33 |   2.9% |      64 |    9.01 |  772.31 |444 | 34 |  2 | 203564.0 |
   |    7 |     198 | \n             |   10.64 |  10.7% |      16 |   10.09 |  815.48 |421 | 56 |  3 | 239547.0 |
   |    8 |     220 |                |   13.43 |  30.8% |     198 |   12.44 |  758.94 |427 | 47 |  6 | 222514.0 |
   |   52 |      17 | 2              |   11.57 |  14.9% |      16 |   11.54 |  839.35 |415 | 59 |  6 | 260393.0 |
   |    9 |      17 | 2              |   10.57 |   7.3% |      16 |   10.29 |  762.02 |427 | 50 |  3 | 237339.0 |
   |   12 |      16 | 1              |   10.11 |  11.2% |      17 |    9.56 |  756.14 |423 | 53 |  4 | 234739.0 |
   |   57 |      16 | 1              |    9.58 |   2.9% |      17 |    8.84 |  725.17 |424 | 50 |  6 | 260539.0 |
   |   61 |      17 | 2              |   10.66 |  13.6% |      16 |   10.09 |  630.17 |461 | 19 |  0 | 194689.0 |
   |   62 |      16 | 1              |    9.62 |   7.7% |      17 |    9.40 |  608.34 |470 |  8 |  2 | 164639.0 |
   |   63 |      16 | 1              |   11.23 |   5.0% |      17 |   11.07 |  608.39 |467 | 13 |  0 | 188439.0 |
   |   64 |      17 | 2              |   11.22 |   9.4% |      18 |    9.84 |  605.97 |458 | 22 |  0 | 207193.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 751.718s, TTFT=751717.74ms): Avg=2.72 | Min=2.31 | Max=2.84 tps
   Prefill Chunks (8): C1:256t/2.3tps/95% | C2:256t/2.8tps/96% | C3:256t/2.8tps/97% | C4:256t/2.8tps/97%
                       C5:256t/2.8tps/97% | C6:256t/2.8tps/97% | C7:256t/2.8tps/97% | C8:256t/2.8tps/97%
   Decode  (63 tok, 42.144s): Avg=1.49 | Min=0.94 | Max=1.69 tps
   Latency (ms) : Min=591.92 | P10=604.74 | P25=614.64 | P50=634.42 | P75=690.25 | P90=762.02 | P95=815.48 | P99=1063.26 | Max=1063.26
   Mean/SD/Jitt : Mean=668.96ms | StdDev=92.02ms | Jitter=38.07ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1013280): RawRAM=985469 (97.26%) | Lookahead=1849 (+0.18%) | ColdMiss=25962 (2.56%) | EFF HIT=97.44%
   Lookahead    : 7521 prefetched -> 1859 consumed (24.7% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.4% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21110 |18861 | 200 |2049 | 90.3%|3788.60 | | L24 |21110 |20865 |  13 | 232 | 98.9%| 552.69 |
   | L01 |21110 |20389 | 117 | 604 | 97.1%|1430.64 | | L25 |21110 |20879 |  11 | 220 | 99.0%| 441.77 |
   | L02 |21110 |20404 |  28 | 678 | 96.8%|1795.75 | | L26 |21110 |20481 |  40 | 589 | 97.2%|1334.72 |
   | L03 |21110 |21027 |   3 |  80 | 99.6%| 926.78 | | L27 |21110 |20752 |  26 | 332 | 98.4%| 795.19 |
   | L04 |21110 |20789 |  14 | 307 | 98.5%|1035.52 | | L28 |21110 |20360 |  59 | 691 | 96.7%|1629.86 |
   | L05 |21110 |20707 |  25 | 378 | 98.2%|1195.61 | | L29 |21110 |20547 |  37 | 526 | 97.5%| 913.23 |
   | L06 |21110 |20722 |  40 | 348 | 98.4%| 960.62 | | L30 |21110 |20156 |  52 | 902 | 95.7%|1449.07 |
   | L07 |21110 |20711 |  43 | 356 | 98.3%| 744.58 | | L31 |21110 |20272 |  43 | 795 | 96.2%|1305.03 |
   | L08 |21110 |21035 |   4 |  71 | 99.7%| 178.05 | | L32 |21110 |20485 |  31 | 594 | 97.2%|1370.43 |
   | L09 |21110 |21031 |   2 |  77 | 99.6%| 108.33 | | L33 |21110 |20388 |  23 | 699 | 96.7%|1112.01 |
   | L10 |21110 |20860 |   5 | 245 | 98.8%| 337.43 | | L34 |21110 |20120 |  53 | 937 | 95.6%|1528.30 |
   | L11 |21110 |21034 |   3 |  73 | 99.7%| 159.38 | | L35 |21110 |20546 |  28 | 536 | 97.5%| 895.95 |
   | L12 |21110 |20906 |  11 | 193 | 99.1%| 594.04 | | L36 |21110 |20475 |  44 | 591 | 97.2%|1086.08 |
   | L13 |21110 |20783 |  28 | 299 | 98.6%| 532.96 | | L37 |21110 |20433 |  30 | 647 | 96.9%|1332.84 |
   | L14 |21110 |20676 |  67 | 367 | 98.3%| 872.90 | | L38 |21110 |20670 |  26 | 414 | 98.0%|1180.57 |
   | L15 |21110 |20523 |  74 | 513 | 97.6%|1218.16 | | L39 |21110 |20484 |  37 | 589 | 97.2%|1387.35 |
   | L16 |21110 |20479 |  26 | 605 | 97.1%|1272.68 | | L40 |21110 |20590 |  37 | 483 | 97.7%|1304.64 |
   | L17 |21110 |20299 |  48 | 763 | 96.4%|1656.18 | | L41 |21110 |20587 |  14 | 509 | 97.6%| 838.33 |
   | L18 |21110 |20374 |  36 | 700 | 96.7%|1486.99 | | L42 |21110 |20252 |  67 | 791 | 96.3%|1447.63 |
   | L19 |21110 |20580 |  36 | 494 | 97.7%| 823.93 | | L43 |21110 |20172 |  44 | 894 | 95.8%|1577.27 |
   | L20 |21110 |20216 |  43 | 851 | 96.0%|1486.52 | | L44 |21110 |20163 |  64 | 883 | 95.8%|1528.30 |
   | L21 |21110 |20316 |  65 | 729 | 96.5%|2032.15 | | L45 |21110 |20215 |  73 | 822 | 96.1%|1597.44 |
   | L22 |21110 |20842 |  14 | 254 | 98.8%| 652.32 | | L46 |21110 |20835 |  12 | 263 | 98.8%| 774.95 |
   | L23 |21110 |20466 |  39 | 605 | 97.1%|1148.02 | | L47 |21110 |20712 |  14 | 384 | 98.2%| 956.86 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 59578.15 MB (Load=4614.69 | Prefill=42392.48 | Warmup=0.00 | Decode=12570.98 MB)
   SSD Data/Token (Decode)      : Avg=199.539 MB/tok (Min=150.429 | P50=200.746 | P95=233.933 | Max=282.244 MB) | Prefill=20.699 MB/tok
   NVMe Batches / Requests      : 4103 Batches | 135333 Raw -> 130268 Merged (5065 LBA Merges, Avg 468.3 KB/io)
   SSD I/O Size Histogram       : <64K=33825 | 64K-512K=24544 | 512K-2M=71388 | >2M=511
   SSD Read Bandwidth (Active)  : Min=4.79 | Avg=333.40 | Peak=5151.78 MB/s | WallAmort=75.05 MB/s
   OS Kernel I/O Verification   : Read=59598.69 MB | Write=0.00 MB | Syscalls=139782
   Sync Stall vs Async DMA      : SyncStall=146749.79 ms | AsyncOverlapped=159753.86 ms (52.1% Overlapped)
   RAM Traffic & Active BW      : 5635.43 GB moved | Active=9.09 GB/s | WallAmort=7.10 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=751.72s (94.7%, 42392.48 MB SSD) | Decode=42.14s (5.3%, 12570.98 MB SSD)
   CPU Time & Utilization       : User=2297.828s + Sys=38.062s (Wall=819.788s) | SysUtil=71.2% | ThrUtil=71.2% | 65.89 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 312190.31 ms (147887.4 us/tok | 39.33%)
   MoE AVX2 Q8 Expert Compute   : 305735.46 ms (144829.7 us/tok | 38.51%)
   Router + Lookahead Dispatch  :  18224.08 ms ( 8632.9 us/tok |  2.30%)
   LM Head Output Projection    :   2352.94 ms ( 1114.6 us/tok |  0.30%)
   Foreground NVMe Sync Stall   : 146749.79 ms (69516.7 us/tok | 18.49%)
   Unaccounted / OMP & Sampling :   8609.47 ms ( 4078.4 us/tok |  1.08%) | Total Wall=793862.05 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    91.55%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.17%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.02%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     3.86%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.40%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================

--------------------------------------------------------------------------------
 [Stage 5] Fair Head-to-Head Competitor Suite (Exact 64p / 32g / 4-Thread Parity)
--------------------------------------------------------------------------------
[Fair-Runner] Apex 64p/32g wall=96.0s | Competitor drastic-underperform cutoff=480.0s (5x Apex)
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=480.0s) ===
  [Colibri-Qwen38] [gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
  [Colibri-Qwen38] [gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
  [Colibri-Qwen38] == Qwen3.8-Flash-Next native text engine | cache=72/layer | CPU ==
  [Colibri-Qwen38] [tok] loaded 248320 base pieces + 33 added tokens (max id 248319) from D:/apex_d_drive/models/qwen38/tokenizer.json
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=480.0s
  [Colibri-Qwen38] [qwen38] native text weights: prefix=model, 48 layers, PLE=1, cache=72/layer, FP8=native, BF16=native (resident matrices 4.40 GiB)
  [Colibri-Qwen38] [qwen38] MTP head mtp.*: wiring b (a norm per stream, fc_hidden per stream), RoPE base 1e+07, 96.86 MiB resident; routed experts Q8_0 from the snapshot (its own GGUF), cache 72 (Q38_MTP_CAP) x 4.98 MiB = 0.35 GiB full
  [Colibri-Qwen38] [qwen38] MTP norm weights, mean: embedding -0.7642, hidden -0.3284, mixer 3.7881 (q38_rms0 scales by 1+w; a plain norm's weights would sit near 1)
  [Colibri-Qwen38] [qwen38] trunk: 62 matrices int8 on the CPU (0.08 GiB, 0.28 GiB of BF16 released) in 0.3s; Q38_TRUNK_CPU_INT8=0 keeps BF16
  [Colibri-Qwen38] [qwen38 MTP] draft vocabulary: the lm_head has no int8 rows on the host, so the head scores the whole vocabulary (Q38_MTP_VOCAB=0 silences this)
  [Colibri-Qwen38] [qwen38] routed experts: GGUF IQ2_XXS/IQ2_XXS/IQ4_NL (layer 0), 1.68 MiB per expert; cache 72/layer
  [Colibri-Qwen38] [qwen38] trunk: 62 int8 matrices interleaved by 16 for the CPU in 0.03s (Q38_ILV16=0 keeps the rows)
  [Colibri-Qwen38] resident weights loaded in 20.5s | RSS after load: 4.60 GB
  [Colibri-Qwen38] [qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.0s / cutoff=480.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=480.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=60.1s / cutoff=480.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=75.1s / cutoff=480.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=90.1s / cutoff=480.0s
  [Colibri-Qwen38] TTFT: 42.37 s (time to first token)
  [Colibri-Qwen38] [qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
  [Colibri-Qwen38] [qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
  [Colibri-Qwen38] [qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes
  [Colibri-Qwen38] 
  [Colibri-Qwen38] PEAK RSS: 10.76 GB
  [Colibri-Qwen38] Expert cache hit rate: 62.0% (hit=15849 miss=9733)
  [Colibri-Qwen38] Speed: 0.39 tok/s (81.8s for 32 tokens)
  [Colibri-Qwen38] [STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage
  [COMP-LIVE] Colibri-Qwen38: elapsed=105.2s / cutoff=480.0s
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
=== [Colibri-Qwen38] Finished rc=1 elapsed=106.17s cancelled=False ===
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 1.41 | 1.37 | 623.43 | 91.71% | 291.48 | 13414.97 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 2.52 | 1.68 | 573.63 | 97.33% | 403.20 | 14148.64 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.72 | 1.49 | 634.42 | 97.44% | 333.40 | 13113.93 MB | Native GGUF + MTP ON |
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
-rwxr-xr-x 1 runneradmin 197121 872K Nov 14 05:54 ./apex.exe
-rwxr-xr-x 1 runneradmin 197121 872K Nov 14 05:54 build/apex.exe
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
   System Memory (RAM): 15.99 GB Total / 13.51 GB Available
   Active Drive Space : 150.00 GB Total / 147.00 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    239.32 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    945.89 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4844.34 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   7584.24 MB/s
   RND4K Q32T16 Read                  :    572.83 MB/s (  146643 IOPS)
   RND4K Q1T1  Read                   :    777.70 MB/s (Latency: 5.02 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     41.97 GB/s
   AVX2 256-bit Sequential Write BW   :     29.03 GB/s
   STREAM Triad (A = B + s*C) BW      :     27.51 GB/s
   Random Pointer-Chase Latency       :    122.15 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     43.70 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    164.18 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     16.56 GB/s (FP32 Equiv)
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
[LIVE-PREFILL] 256/2048 tok | Chunk=1373.45 tps | Avg=1373.45 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=73.6 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=1252.26 tps | Avg=1310.06 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=73.8 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1079.42 tps | Avg=1222.96 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=74.1 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=952.30 tps | Avg=1141.83 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=74.3 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=863.88 tps | Avg=1072.79 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=74.6 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=764.76 tps | Avg=1005.31 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=74.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=725.53 tps | Avg=952.82 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=75.1 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=669.52 tps | Avg=904.95 tps | Hit=100.0% | NVMe=1778.8 MB/s (6.58 MB, QD=64) | RSS=75.4 MB
[LIVE-DECODE] 8/32 tok | Avg=172.42 tps | Hit=100.0% (LA:+0.0%) | NVMe=1778.8 MB/s (6.58 MB) | RSS=75.4 MB
[LIVE-DECODE] 16/32 tok | Avg=182.44 tps | Hit=100.0% (LA:+0.0%) | NVMe=1778.8 MB/s (6.58 MB) | RSS=75.4 MB
[LIVE-DECODE] 24/32 tok | Avg=183.02 tps | Hit=100.0% (LA:+0.0%) | NVMe=1778.8 MB/s (6.58 MB) | RSS=75.4 MB
[LIVE-DECODE] 32/32 tok | Avg=182.63 tps | Hit=100.0% (LA:+0.0%) | NVMe=1778.8 MB/s (6.58 MB) | RSS=75.4 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=75.44 MB | Peak=75.44 MB
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
   |    1 |      55 | tok_55         |  190.69 |  99.3% |     246 |  185.76 | 2263.10 |  0 |  0 |  0 |     0.0 |
   |    2 |      55 | tok_55         |  179.98 | 100.0% |     246 |  150.29 |    5.90 | 12 |  0 |  0 |     0.0 |
   |    3 |     175 | tok_175        |   77.47 |  67.6% |     179 |   76.74 |    5.90 |  0 |  0 |  0 |     0.0 |
   |    4 |      55 | tok_55         |  178.88 | 100.0% |     119 |  162.42 |    5.94 | 12 |  0 |  0 |     0.0 |
   |    5 |      39 | tok_39         |  158.03 | 100.0% |     246 |  148.54 |    5.94 |  0 |  0 |  0 |     0.0 |
   |    6 |      55 | tok_55         |  191.28 |  98.6% |     119 |  187.05 |    5.72 | 12 |  0 |  0 |     0.0 |
   |    7 |      36 | tok_36         |   70.07 | 100.0% |     145 |   61.63 |    5.72 |  0 |  0 |  0 |     0.0 |
   |    8 |     246 | tok_246        |  205.36 | 100.0% |      86 |  185.83 |    5.64 | 12 |  0 |  0 |     0.0 |
   |    9 |      68 | tok_68         |  176.71 | 100.0% |     228 |  144.43 |    5.64 |  0 |  0 |  0 |     0.0 |
   |   28 |     246 | tok_246        |  194.87 | 100.0% |      54 |  173.43 |    5.59 | 12 |  0 |  0 |     0.0 |
   |   29 |     229 | tok_229        |  172.54 | 100.0% |      70 |  154.16 |    5.59 |  0 |  0 |  0 |     0.0 |
   |   24 |     246 | tok_246        |  204.37 |  99.2% |      55 |  199.55 |    5.48 | 12 |  0 |  0 |     0.0 |
   |   30 |     246 | tok_246        |  176.20 | 100.0% |     124 |  160.53 |    5.53 | 12 |  0 |  0 |     0.0 |
   |   31 |     229 | tok_229        |  171.33 | 100.0% |      70 |  153.29 |    5.53 |  0 |  0 |  0 |     0.0 |
   |   32 |      21 | tok_21         |  222.52 |  97.9% |      86 |  218.66 |    5.47 | 12 |  0 |  0 |     0.0 |
   |   33 |     246 | tok_246        |  115.62 | 100.0% |     232 |   96.08 |    5.47 |  0 |  0 |  0 |     0.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 2.263s, TTFT=2263.10ms): Avg=904.95 | Min=669.52 | Max=1373.45 tps
   Prefill Chunks (8): C1:256t/1373.4tps/100% | C2:256t/1252.3tps/100% | C3:256t/1079.4tps/100% | C4:256t/952.3tps/100%
                       C5:256t/863.9tps/100% | C6:256t/764.8tps/100% | C7:256t/725.5tps/100% | C8:256t/669.5tps/100%
   Decode  (32 tok, 0.175s): Avg=182.63 | Min=168.25 | Max=198.35 tps
   Latency (ms) : Min=5.04 | P10=5.09 | P25=5.37 | P50=5.47 | P75=5.64 | P90=5.90 | P95=5.94 | P99=5.94 | Max=5.94
   Mean/SD/Jitt : Mean=5.48ms | StdDev=0.24ms | Jitter=0.05ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=203.97 | Avg=1778.85 | Peak=4770.99 MB/s | WallAmort=2.70 MB/s
   OS Kernel I/O Verification   : Read=6.59 MB | Write=0.00 MB | Syscalls=160
   Sync Stall vs Async DMA      : SyncStall=0.00 ms | AsyncOverlapped=2.18 ms (100.0% Overlapped)
   RAM Traffic & Active BW      : 1.43 GB moved | Active=0.62 GB/s | WallAmort=0.59 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=2.26s (92.8%, 0.00 MB SSD) | Decode=0.18s (7.2%, 0.00 MB SSD)
   CPU Time & Utilization       : User=3.141s + Sys=0.641s (Wall=2.470s) | SysUtil=38.3% | ThrUtil=38.3% | 35.41 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :   2057.93 ms (  989.4 us/tok | 84.40%)
   MoE AVX2 Q8 Expert Compute   :    246.10 ms (  118.3 us/tok | 10.09%)
   Router + Lookahead Dispatch  :     61.13 ms (   29.4 us/tok |  2.51%)
   LM Head Output Projection    :      6.96 ms (    3.3 us/tok |  0.29%)
   Foreground NVMe Sync Stall   :      0.00 ms (    0.0 us/tok |  0.00%)
   Unaccounted / OMP & Sampling :     66.20 ms (   31.8 us/tok |  2.71%) | Total Wall=2438.32 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    21.65%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.04%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     0.12%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    74.35%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.84%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================



=== [TEST] Qwen-3.8-Flash-Next 2048-Token Prefill & Decode + MTP Off/On A/B Benchmark: ./apex.exe bench --model tests/synth_qwen38_ud_iq2_xs.gguf --prompt-tokens 2048 --gen-tokens 32 --mtp on --no-hwtest ===
[Apex-Init] Model Loaded: Qwen3.8-Flash-Next-UD-IQ2_XS-Synthetic | Layers=4 | Hidden=256 | Experts=16 (Top-4) | Pinned Trunk=4.70 MB | Expert Cache=2.17 MB (40 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=1968.56 tps | Avg=1968.56 tps | Hit=99.2% | NVMe=2160.9 MB/s (24.91 MB, QD=64) | RSS=89.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2012.71 tps | Avg=1990.39 tps | Hit=99.2% | NVMe=2844.0 MB/s (42.92 MB, QD=64) | RSS=89.3 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=1779.74 tps | Avg=1914.84 tps | Hit=99.2% | NVMe=3277.6 MB/s (61.04 MB, QD=64) | RSS=89.7 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=1705.05 tps | Avg=1857.70 tps | Hit=99.2% | NVMe=3557.4 MB/s (79.10 MB, QD=64) | RSS=90.0 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=1594.30 tps | Avg=1798.28 tps | Hit=99.2% | NVMe=3756.4 MB/s (97.14 MB, QD=64) | RSS=90.4 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=1478.13 tps | Avg=1735.62 tps | Hit=99.2% | NVMe=3923.1 MB/s (115.20 MB, QD=64) | RSS=90.9 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=1334.94 tps | Avg=1664.26 tps | Hit=99.2% | NVMe=4057.0 MB/s (133.27 MB, QD=64) | RSS=91.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=1331.47 tps | Avg=1613.84 tps | Hit=99.2% | NVMe=4181.2 MB/s (151.30 MB, QD=64) | RSS=91.7 MB
[LIVE-DECODE] 8/32 tok | Avg=155.31 tps | Hit=99.2% (LA:+0.0%) | NVMe=4094.3 MB/s (152.70 MB) | RSS=91.7 MB
[LIVE-DECODE] 16/32 tok | Avg=156.90 tps | Hit=99.2% (LA:+0.1%) | NVMe=4046.1 MB/s (153.28 MB) | RSS=91.7 MB
[LIVE-DECODE] 24/32 tok | Avg=157.20 tps | Hit=99.2% (LA:+0.1%) | NVMe=3969.8 MB/s (154.23 MB) | RSS=91.7 MB
[LIVE-DECODE] 32/32 tok | Avg=158.80 tps | Hit=99.2% (LA:+0.1%) | NVMe=3907.7 MB/s (155.14 MB) | RSS=91.7 MB

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
   Process RSS (Start/End/Peak) : Start=4.87 MB | End=91.68 MB | Peak=91.68 MB
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
   |    1 |      49 | qtok_49        |   63.71 |  97.6% |     254 |   59.93 | 1269.02 |  0 |  0 |  0 |     0.0 |
   |    2 |     254 | qtok_254       |   63.01 | 100.0% |       2 |   54.14 |    6.51 |  6 | 10 |  0 |   535.5 |
   |    3 |      49 | qtok_49        |   93.73 | 100.0% |     177 |   84.12 |    6.51 |  0 |  0 |  0 |   535.5 |
   |    4 |     254 | qtok_254       |   65.57 | 100.0% |       2 |   56.25 |    6.49 | 15 |  1 |  0 |    59.8 |
   |    5 |      49 | qtok_49        |   84.71 |  99.7% |     177 |   78.29 |    6.49 |  0 |  0 |  0 |    59.8 |
   |    6 |     254 | qtok_254       |   70.80 | 100.0% |       2 |   58.38 |    6.48 | 15 |  1 |  0 |    87.5 |
   |    7 |      49 | qtok_49        |   83.85 |  99.9% |     129 |   77.09 |    6.48 |  0 |  0 |  0 |    87.5 |
   |    8 |     254 | qtok_254       |   72.14 | 100.0% |      66 |   61.47 |    6.27 | 16 |  0 |  0 |    32.0 |
   |   22 |     128 | qtok_128       |   64.14 |  98.8% |       2 |   59.73 |    6.36 | 12 |  4 |  0 |   115.2 |
   |   23 |      63 | qtok_63        |   98.11 | 100.0% |     113 |   72.66 |    6.36 |  0 |  0 |  0 |   115.2 |
   |   26 |     194 | qtok_194       |   70.46 | 100.0% |     128 |   54.98 |    6.36 | 12 |  4 |  0 |   147.0 |
   |   27 |      49 | qtok_49        |   67.58 |  99.9% |     209 |   61.01 |    6.36 |  0 |  0 |  0 |   147.0 |
   |   30 |     254 | qtok_254       |   59.08 |  96.0% |      49 |   55.91 |    5.97 | 14 |  2 |  0 |   115.2 |
   |   31 |      48 | qtok_48        |  139.73 | 100.0% |      49 |  108.61 |    5.97 |  0 |  0 |  0 |   115.2 |
   |   32 |     254 | qtok_254       |   53.74 |  72.9% |     194 |   52.16 |    5.85 | 14 |  2 |  0 |    87.5 |
   |   33 |      49 | qtok_49        |  132.17 | 100.0% |      48 |  102.59 |    5.85 |  0 |  0 |  0 |    87.5 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 1.269s, TTFT=1269.02ms): Avg=1613.84 | Min=1331.47 | Max=2012.71 tps
   Prefill Chunks (8): C1:256t/1968.6tps/99% | C2:256t/2012.7tps/99% | C3:256t/1779.7tps/99% | C4:256t/1705.1tps/99%
                       C5:256t/1594.3tps/99% | C6:256t/1478.1tps/99% | C7:256t/1334.9tps/99% | C8:256t/1331.5tps/99%
   Decode  (32 tok, 0.202s): Avg=158.80 | Min=153.58 | Max=171.00 tps
   Latency (ms) : Min=5.85 | P10=5.97 | P25=6.27 | P50=6.34 | P75=6.36 | P90=6.49 | P95=6.51 | P99=6.51 | Max=6.51
   Mean/SD/Jitt : Mean=6.30ms | StdDev=0.17ms | Jitter=0.03ms | Hist(<25/50/100/200/>200ms): 32/0/0/0/0
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
   SSD Read Bandwidth (Active)  : Min=256.99 | Avg=3907.73 | Peak=7590.95 MB/s | WallAmort=105.50 MB/s
   OS Kernel I/O Verification   : Read=24.31 MB | Write=0.00 MB | Syscalls=388
   Sync Stall vs Async DMA      : SyncStall=9.59 ms | AsyncOverlapped=37.98 ms (79.8% Overlapped)
   RAM Traffic & Active BW      : 2.10 GB moved | Active=1.66 GB/s | WallAmort=1.43 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=1.27s (86.3%, 144.44 MB SSD) | Decode=0.20s (13.7%, 3.83 MB SSD)
   CPU Time & Utilization       : User=2.547s + Sys=0.297s (Wall=1.521s) | SysUtil=46.7% | ThrUtil=46.7% | 43.23 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :    897.64 ms (  431.6 us/tok | 61.04%)
   MoE AVX2 Q8 Expert Compute   :    359.28 ms (  172.7 us/tok | 24.43%)
   Router + Lookahead Dispatch  :     79.58 ms (   38.3 us/tok |  5.41%)
   LM Head Output Projection    :      7.08 ms (    3.4 us/tok |  0.48%)
   Foreground NVMe Sync Stall   :      9.59 ms (    4.6 us/tok |  0.65%)
   Unaccounted / OMP & Sampling :    117.37 ms (   56.4 us/tok |  7.98%) | Total Wall=1470.54 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    23.04%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     6.05%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.49%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |    64.15%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     4.27%  |
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
    "ttft_ms": 252.38,
    "avg_tps": 649.81,
    "min_tps": 491.09,
    "max_tps": 766.08
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 126.08,
    "min_tps": 105.57,
    "max_tps": 143.02,
    "p50_ms": 7.98,
    "p90_ms": 8.54,
    "p99_ms": 9.47,
    "mean_ms": 7.93,
    "jitter_ms": 0.26
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
    "avg_mbs": 1765.72,
    "peak_mbs": 4699.25,
    "sync_wait_ms": 0.0,
    "async_overlap_ms": 1.65
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
    "dense_attention": 422.97,
    "moe_compute": 114.06,
    "router_lookahead": 7.58,
    "lm_head": 9.91,
    "unaccounted": 7.18
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 85.9,
    "ram_bandwidth_pinning": 1.71,
    "expert_cache_lrfu": 10.47,
    "lookahead_parallel_overlap": 1.45,
    "ssd_nvme_throughput": 0.47,
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
    "ttft_ms": 304.99,
    "avg_tps": 537.73,
    "min_tps": 361.0,
    "max_tps": 643.36
  },
  "decode": {
    "tokens": 39,
    "avg_tps": 123.15,
    "min_tps": 106.51,
    "max_tps": 132.6,
    "p50_ms": 7.8,
    "p90_ms": 9.06,
    "p99_ms": 9.39,
    "mean_ms": 8.12,
    "jitter_ms": 0.15
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
    "avg_mbs": 1904.5,
    "peak_mbs": 5931.24,
    "sync_wait_ms": 6.75,
    "async_overlap_ms": 17.69
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
    "dense_attention": 354.58,
    "moe_compute": 197.94,
    "router_lookahead": 9.27,
    "lm_head": 9.01,
    "unaccounted": 44.11
  },
  "resource_contribution_pct": {
    "cpu_avx2_fma": 77.93,
    "ram_bandwidth_pinning": 2.04,
    "expert_cache_lrfu": 10.96,
    "lookahead_parallel_overlap": 5.51,
    "ssd_nvme_throughput": 3.56,
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
   Active Drive Space : 150.00 GB Total / 146.95 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    238.70 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    945.90 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   4427.84 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   5911.57 MB/s
   RND4K Q32T16 Read                  :    554.92 MB/s (  142060 IOPS)
   RND4K Q1T1  Read                   :    810.60 MB/s (Latency: 4.82 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     42.38 GB/s
   AVX2 256-bit Sequential Write BW   :     26.27 GB/s
   STREAM Triad (A = B + s*C) BW      :     28.73 GB/s
   Random Pointer-Chase Latency       :    123.31 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     48.69 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :    180.30 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     16.83 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on C:/apex_c_drive
   Drive Free: 30.99 GB / 149.89 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 164.11 MB/s (6.24s)
   Window #01 (116.0 MB in 0.51s):   226.57 MB/s (Uncached Direct Read)
   Window #02 (120.0 MB in 0.50s):   239.72 MB/s (Uncached Direct Read)
   Window #03 (124.0 MB in 0.51s):   241.14 MB/s (Uncached Direct Read)
   Window #04 (116.0 MB in 0.50s):   230.95 MB/s (Uncached Direct Read)
   Window #05 (116.0 MB in 0.50s):   231.88 MB/s (Uncached Direct Read)
   Window #06 (120.0 MB in 0.50s):   239.13 MB/s (Uncached Direct Read)
   Window #07 (116.0 MB in 0.51s):   226.59 MB/s (Uncached Direct Read)
   Window #08 (120.0 MB in 0.50s):   239.36 MB/s (Uncached Direct Read)
   Window #09 ( 76.0 MB in 0.32s):   237.18 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   234.60 MB/s (Min=226.57 | Max=241.14 MB/s)
================================================================================


================================================================================
 [Disk Throttle Probe] 1024 MB Uncached Direct I/O Test on D:/apex_d_drive
   Drive Free: 146.95 GB / 150.00 GB | Bypassing OS Page Cache (Direct/Unbuffered)
--------------------------------------------------------------------------------
   Uncached Write (1024 MB)      : 238.55 MB/s (4.29s)
   Window #01 (120.0 MB in 0.50s):   240.00 MB/s (Uncached Direct Read)
   Window #02 (120.0 MB in 0.50s):   240.00 MB/s (Uncached Direct Read)
   Window #03 (124.0 MB in 0.52s):   238.46 MB/s (Uncached Direct Read)
   Window #04 (120.0 MB in 0.50s):   239.98 MB/s (Uncached Direct Read)
   Window #05 (120.0 MB in 0.51s):   235.26 MB/s (Uncached Direct Read)
   Window #06 (124.0 MB in 0.52s):   238.53 MB/s (Uncached Direct Read)
   Window #07 (120.0 MB in 0.50s):   239.97 MB/s (Uncached Direct Read)
   Window #08 (120.0 MB in 0.50s):   239.98 MB/s (Uncached Direct Read)
   Window #09 ( 56.0 MB in 0.24s):   233.36 MB/s (Uncached Direct Read)
   Sustained Uncached Read Avg  :   238.69 MB/s (Min=233.36 | Max=240.00 MB/s)
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
   System Memory (RAM): 15.99 GB Total / 14.58 GB Available
   Active Drive Space : 150.00 GB Total / 76.31 GB Free
--------------------------------------------------------------------------------
 [CrystalDiskMark-Style NVMe SSD Storage Benchmark]
   SEQ1M Direct Uncached NVMe Read    :    222.45 MB/s (Hardware Floor)
   SEQ1M Q8T1  Read (OS-Cached Max)   :    945.58 MB/s
   SEQ1M Q1T1  Read (Single Queue)    :   3575.13 MB/s
   SEQ128K Q32T1 Expert-Stripe Read   :   6902.54 MB/s
   RND4K Q32T16 Read                  :    477.29 MB/s (  122187 IOPS)
   RND4K Q1T1  Read                   :    640.84 MB/s (Latency: 6.10 us)
--------------------------------------------------------------------------------
 [PassMark / STREAM System RAM Bandwidth & Latency Benchmark]
   AVX2 256-bit Sequential Read BW    :     39.46 GB/s
   AVX2 256-bit Sequential Write BW   :     22.28 GB/s
   STREAM Triad (A = B + s*C) BW      :     28.16 GB/s
   Random Pointer-Chase Latency       :    191.87 ns
--------------------------------------------------------------------------------
 [PassMark-Style CPU AVX2+FMA Compute & IQ2 Kernel Benchmark]
   Single-Core AVX2+FMA Throughput    :     45.18 GFLOPS
   Multi-Core  AVX2+FMA Throughput    :     87.81 GFLOPS
   IQ2_XXS/XS Fused Dot Effective BW  :     13.41 GB/s (FP32 Equiv)
================================================================================


================================================================================
 [Apex-Run] Interactive Prompt & Streaming Model Generation
================================================================================
 >>> User Prompt   : "Explain why hybrid Gated DeltaNet + Kimi Delta Attention with 512 Mixture-of-Experts and LBA-coalesced 128KB-1MB sequential NVMe DMA achieves high token generation throughput on 16GB RAM:"
 >>> Chat Template : 91 tokenized input IDs
[LIVE-PREFILL] 91/91 tok | Chunk=1.59 tps | Avg=1.59 tps | Hit=90.0% | NVMe=241.3 MB/s (11789.75 MB, QD=64) | RSS=13431.8 MB

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
   LRFU Cache / Staging Ring    : 7553.71 MB (3640/25088 exp = 14.51% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.84 MB | End=13380.36 MB | Peak=13910.10 MB
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
   |    1 |      65 | b              |    9.34 |   1.9% |      79 |    9.00 | 57315.17 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |   10.69 |  14.6% |     271 |    7.46 |  878.29 |902 | 54 |  4 | 147653.5 |
   |    3 |      15 | 0              |    9.12 |   1.0% |      79 |    8.96 |  878.29 |  0 |  0 |  0 | 147653.5 |
   |    4 |     198 | \n             |   11.23 |  26.1% |      65 |    7.68 |  837.20 |444 | 31 |  5 | 169014.0 |
   |    5 |      17 | 2              |    7.61 |   0.8% |      15 |    7.44 |  564.19 |472 |  8 |  0 | 89543.0 |
   |    6 |      17 | 2              |    9.33 |   3.4% |      16 |    8.85 |  764.82 |450 | 27 |  3 | 153389.0 |
   |    7 |      17 | 2              |   10.09 |   7.7% |      24 |   10.02 |  749.42 |440 | 31 |  9 | 176893.0 |
   |    8 |      22 | 7              |   11.04 |   9.6% |      17 |   10.99 |  634.02 |451 | 26 |  3 | 137218.0 |
   |   10 |      24 | 9              |   10.61 |   9.0% |      17 |   10.51 |  701.92 |450 | 24 |  6 | 164414.0 |
   |   33 |      17 | 2              |   11.35 |  15.6% |      18 |   10.52 |  666.90 |455 | 21 |  4 | 132564.0 |
   |   59 |      17 | 2              |   12.29 |  13.6% |      15 |   12.07 |  661.08 |452 | 27 |  1 | 158764.0 |
   |   11 |     198 | \n             |   11.25 |  22.6% |      16 |   10.26 |  656.01 |448 | 28 |  4 | 168889.0 |
   |   61 |      17 | 2              |   11.98 |  21.6% |      18 |   11.12 |  557.60 |478 |  2 |  0 | 117014.0 |
   |   62 |      16 | 1              |   12.20 |  17.7% |      17 |   12.06 |  558.84 |476 |  4 |  0 | 119168.0 |
   |   63 |      17 | 2              |   13.90 |  25.0% |      18 |   13.58 |  571.88 |479 |  1 |  0 | 100743.0 |
   |   64 |      17 | 2              |   12.55 |  17.2% |      16 |   12.28 |  552.11 |474 |  6 |  0 | 67443.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (91 tok, 57.315s, TTFT=57315.17ms): Avg=1.59 | Min=1.59 | Max=1.59 tps
   Prefill Chunks (1): C1:91t/1.6tps/90%
   Decode  (63 tok, 37.322s): Avg=1.69 | Min=1.14 | Max=1.85 tps
   Latency (ms) : Min=539.59 | P10=548.32 | P25=552.66 | P50=561.61 | P75=591.82 | P90=666.90 | P95=764.82 | P99=878.29 | Max=878.29
   Mean/SD/Jitt : Mean=592.42ms | StdDev=76.00ms | Jitter=32.73ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (73920): RawRAM=68887 (93.19%) | Lookahead=618 (+0.84%) | ColdMiss=4415 (5.97%) | EFF HIT=94.03%
   Lookahead    : 3808 prefetched -> 628 consumed (16.5% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 91.4% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 1540 | 1233 |  42 | 265 | 82.8%| 517.16 | | L24 | 1540 | 1480 |   4 |  56 | 96.4%| 144.75 |
   | L01 | 1540 | 1406 |  22 | 112 | 92.7%| 572.75 | | L25 | 1540 | 1464 |  10 |  66 | 95.7%| 150.39 |
   | L02 | 1540 | 1392 |   6 | 142 | 90.8%| 790.06 | | L26 | 1540 | 1433 |  14 |  93 | 94.0%| 246.26 |
   | L03 | 1540 | 1475 |   1 |  64 | 95.8%| 735.03 | | L27 | 1540 | 1456 |   9 |  75 | 95.1%| 197.39 |
   | L04 | 1540 | 1465 |   0 |  75 | 95.1%| 228.27 | | L28 | 1540 | 1383 |  36 | 121 | 92.1%| 421.09 |
   | L05 | 1540 | 1452 |   3 |  85 | 94.5%| 317.70 | | L29 | 1540 | 1425 |  23 |  92 | 94.0%| 256.40 |
   | L06 | 1540 | 1439 |  12 |  89 | 94.2%| 242.50 | | L30 | 1540 | 1393 |  27 | 120 | 92.2%| 290.97 |
   | L07 | 1540 | 1443 |  11 |  86 | 94.4%| 220.68 | | L31 | 1540 | 1402 |  21 | 117 | 92.4%| 273.68 |
   | L08 | 1540 | 1485 |   2 |  53 | 96.6%| 113.31 | | L32 | 1540 | 1439 |   8 |  93 | 94.0%| 306.42 |
   | L09 | 1540 | 1476 |   4 |  60 | 96.1%| 136.96 | | L33 | 1540 | 1411 |  34 |  95 | 93.8%| 208.86 |
   | L10 | 1540 | 1459 |   3 |  78 | 94.9%| 120.78 | | L34 | 1540 | 1420 |  23 |  97 | 93.7%| 217.50 |
   | L11 | 1540 | 1475 |   2 |  63 | 95.9%| 140.70 | | L35 | 1540 | 1451 |  14 |  75 | 95.1%| 149.80 |
   | L12 | 1540 | 1441 |  10 |  89 | 94.2%| 298.90 | | L36 | 1540 | 1424 |  14 | 102 | 93.4%| 252.08 |
   | L13 | 1540 | 1438 |  13 |  89 | 94.2%| 154.13 | | L37 | 1540 | 1446 |  13 |  81 | 94.7%| 195.51 |
   | L14 | 1540 | 1425 |  17 |  98 | 93.6%| 338.50 | | L38 | 1540 | 1457 |   9 |  74 | 95.2%| 272.58 |
   | L15 | 1540 | 1431 |  11 |  98 | 93.6%| 310.18 | | L39 | 1540 | 1440 |   9 |  91 | 94.1%| 349.66 |
   | L16 | 1540 | 1439 |   9 |  92 | 94.0%| 223.71 | | L40 | 1540 | 1425 |  11 | 104 | 93.2%| 355.30 |
   | L17 | 1540 | 1441 |   6 |  93 | 94.0%| 250.02 | | L41 | 1540 | 1437 |  10 |  93 | 94.0%| 171.41 |
   | L18 | 1540 | 1439 |  12 |  89 | 94.2%| 199.27 | | L42 | 1540 | 1411 |  26 | 103 | 93.3%| 306.81 |
   | L19 | 1540 | 1458 |   9 |  73 | 95.3%| 162.77 | | L43 | 1540 | 1453 |  11 |  76 | 95.1%| 256.40 |
   | L20 | 1540 | 1423 |  13 | 104 | 93.2%| 270.80 | | L44 | 1540 | 1433 |  18 |  89 | 94.2%| 276.56 |
   | L21 | 1540 | 1424 |  15 | 101 | 93.4%| 330.86 | | L45 | 1540 | 1432 |  19 |  89 | 94.2%| 302.49 |
   | L22 | 1540 | 1467 |   3 |  70 | 95.5%| 321.46 | | L46 | 1540 | 1467 |   6 |  67 | 95.6%| 334.18 |
   | L23 | 1540 | 1430 |  16 |  94 | 93.9%| 226.15 | | L47 | 1540 | 1449 |   7 |  84 | 94.5%| 214.31 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 18047.80 MB (Load=4614.69 | Prefill=7175.05 | Warmup=0.00 | Decode=6258.06 MB)
   SSD Data/Token (Decode)      : Avg=99.334 MB/tok (Min=45.135 | P50=90.199 | P95=160.561 | Max=172.747 MB) | Prefill=78.847 MB/tok
   NVMe Batches / Requests      : 2119 Batches | 28241 Raw -> 27219 Merged (1022 LBA Merges, Avg 679.0 KB/io)
   SSD I/O Size Histogram       : <64K=2674 | 64K-512K=7083 | 512K-2M=17028 | >2M=434
   SSD Read Bandwidth (Active)  : Min=4.73 | Avg=310.27 | Peak=5068.44 MB/s | WallAmort=190.70 MB/s (100.0% of 222.4 MB/s Direct NVMe)
   OS Kernel I/O Verification   : Read=19045.39 MB | Write=128.00 MB | Syscalls=44271
   Sync Stall vs Async DMA      : SyncStall=30144.86 ms | AsyncOverlapped=39232.91 ms (56.5% Overlapped)
   RAM Traffic & Active BW      : 695.74 GB moved | Active=11.68 GB/s (41.5% STREAM) | WallAmort=7.35 GB/s (Max=28.16 GB/s)
   Stage Breakdown (Pref/Dec)   : Prefill=57.32s (60.6%, 7175.05 MB SSD) | Decode=37.32s (39.4%, 6258.06 MB SSD)
   CPU Time & Utilization       : User=193.844s + Sys=12.922s (Wall=122.965s) | SysUtil=42.0% | ThrUtil=42.0% | 36.91 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  32236.92 ms (209330.6 us/tok | 34.06%)
   MoE AVX2 Q8 Expert Compute   :  25051.91 ms (162674.7 us/tok | 26.47%)
   Router + Lookahead Dispatch  :   1672.81 ms (10862.4 us/tok |  1.77%)
   LM Head Output Projection    :   2273.72 ms (14764.4 us/tok |  2.40%)
   Foreground NVMe Sync Stall   :  30144.86 ms (195745.8 us/tok | 31.85%)
   Unaccounted / OMP & Sampling :   3257.45 ms (21152.3 us/tok |  3.44%) | Total Wall=94637.67 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    83.55%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     3.41%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     6.67%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.50%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.87%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `05a_qwen38_stage1_fair_64p_32g.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7061.89 MB (3403 slots)
[Apex-Prompt] Input (64 tokens): "[64-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 64/64 tok | Chunk=1.41 tps | Avg=1.41 tps | Hit=88.1% | NVMe=243.5 MB/s (10578.12 MB, QD=64) | RSS=12941.6 MB
[LIVE-DECODE] 2/32 tok | Avg=0.78 tps | Hit=88.4% (LA:+0.2%) | NVMe=242.8 MB/s (11028.56 MB) | RSS=12944.5 MB
[LIVE-DECODE] 8/32 tok | Avg=1.02 tps | Hit=89.2% (LA:+0.8%) | NVMe=250.7 MB/s (12231.74 MB) | RSS=12944.6 MB
[LIVE-DECODE] 16/32 tok | Avg=1.17 tps | Hit=90.2% (LA:+1.4%) | NVMe=264.1 MB/s (13640.67 MB) | RSS=12938.3 MB
[LIVE-DECODE] 24/32 tok | Avg=1.30 tps | Hit=91.1% (LA:+1.6%) | NVMe=279.4 MB/s (14781.47 MB) | RSS=12925.7 MB
[LIVE-DECODE] 31/32 tok | Avg=1.37 tps | Hit=91.7% (LA:+1.6%) | NVMe=291.5 MB/s (15706.04 MB) | RSS=12919.9 MB

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
   LRFU Cache / Staging Ring    : 7061.89 MB (3403/25088 exp = 13.56% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.88 MB | End=12919.93 MB | Peak=13414.97 MB
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
   |    1 |     264 |  a             |   13.79 |  18.1% |     303 |   13.43 | 45470.82 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |    9.55 |   2.3% |     467 |    8.54 | 1284.13 |874 | 60 | 26 | 230626.5 |
   |    3 |      11 | ,              |   13.78 |  50.0% |     198 |   12.15 | 1284.13 |  0 |  0 |  0 | 230626.5 |
   |    4 |     198 | \n             |   11.28 |  20.5% |     364 |    8.50 |  967.55 |429 | 40 | 11 | 227664.0 |
   |    5 |     277 | ar             |    9.86 |   2.9% |     261 |    9.53 |  991.16 |402 | 68 | 10 | 236389.0 |
   |    6 |      11 | ,              |    9.33 |   3.0% |      16 |    9.11 |  997.33 |427 | 42 | 11 | 233289.0 |
   |    7 |     198 | \n             |    9.90 |   8.3% |     286 |    7.83 |  930.84 |439 | 35 |  6 | 230714.0 |
   |    8 |     286 | ing            |    9.16 |   2.7% |     278 |    8.60 |  692.75 |455 | 21 |  4 | 138264.0 |
   |   14 |      17 | 2              |    9.40 |   4.0% |      15 |    8.88 |  967.65 |415 | 51 | 14 | 237914.0 |
   |   12 |      17 | 2              |    7.65 |   0.5% |     365 |    6.83 |  856.14 |435 | 32 | 13 | 206189.0 |
   |   15 |     198 | \n             |   11.71 |  23.3% |      17 |   11.53 |  795.06 |434 | 38 |  8 | 195443.0 |
   |   25 |     198 | \n             |   10.81 |  12.2% |      15 |   10.44 |  785.07 |423 | 50 |  7 | 229789.0 |
   |   29 |     198 | \n             |   11.56 |  29.2% |     271 |    9.34 |  564.47 |471 |  9 |  0 | 129368.0 |
   |   30 |      15 | 0              |    9.43 |   3.3% |      17 |    9.40 |  562.72 |473 |  7 |  0 | 129714.0 |
   |   31 |      16 | 1              |    9.74 |   4.3% |      17 |    9.38 |  601.56 |460 | 19 |  1 | 163964.0 |
   |   32 |     198 | \n             |   11.79 |  32.8% |      17 |    9.29 |  621.60 |460 | 18 |  2 | 163264.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (64 tok, 45.471s, TTFT=45470.82ms): Avg=1.41 | Min=1.41 | Max=1.41 tps
   Prefill Chunks (1): C1:64t/1.4tps/88%
   Decode  (31 tok, 22.554s): Avg=1.37 | Min=0.78 | Max=1.79 tps
   Latency (ms) : Min=558.78 | P10=563.66 | P25=575.56 | P50=623.43 | P75=856.14 | P90=991.16 | P95=1284.13 | P99=1284.13 | Max=1284.13
   Mean/SD/Jitt : Mean=727.55ms | StdDev=205.30ms | Jitter=79.28ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/31
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (45600): RawRAM=41079 (90.09%) | Lookahead=743 (+1.63%) | ColdMiss=3778 (8.29%) | EFF HIT=91.71%
   Lookahead    : 2985 prefetched -> 753 consumed (25.2% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 90.2% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |  950 |  658 |  78 | 214 | 77.5%| 491.89 | | L24 |  950 |  892 |   9 |  49 | 94.8%| 142.87 |
   | L01 |  950 |  813 |  43 |  94 | 90.1%| 413.38 | | L25 |  950 |  890 |   8 |  52 | 94.5%| 114.67 |
   | L02 |  950 |  829 |  11 | 110 | 88.4%| 439.67 | | L26 |  950 |  866 |  15 |  69 | 92.7%| 199.27 |
   | L03 |  950 |  892 |   1 |  57 | 94.0%| 505.69 | | L27 |  950 |  868 |  16 |  66 | 93.1%| 225.59 |
   | L04 |  950 |  886 |   4 |  60 | 93.7%| 228.27 | | L28 |  950 |  833 |  27 |  90 | 90.5%| 327.10 |
   | L05 |  950 |  870 |   5 |  75 | 92.1%| 280.10 | | L29 |  950 |  857 |  14 |  79 | 91.7%| 171.41 |
   | L06 |  950 |  868 |  16 |  66 | 93.1%| 218.07 | | L30 |  950 |  820 |  27 | 103 | 89.2%| 233.35 |
   | L07 |  950 |  869 |  19 |  62 | 93.5%| 153.30 | | L31 |  950 |  828 |  22 | 100 | 89.5%| 226.15 |
   | L08 |  950 |  902 |   8 |  40 | 95.8%| 103.34 | | L32 |  950 |  850 |  18 |  82 | 91.4%| 266.94 |
   | L09 |  950 |  892 |   5 |  53 | 94.4%| 100.85 | | L33 |  950 |  843 |  20 |  87 | 90.8%| 188.70 |
   | L10 |  950 |  884 |   9 |  57 | 94.0%| 113.31 | | L34 |  950 |  848 |  15 |  87 | 90.8%| 187.26 |
   | L11 |  950 |  895 |   5 |  50 | 94.7%| 128.25 | | L35 |  950 |  868 |  12 |  70 | 92.6%| 133.96 |
   | L12 |  950 |  869 |  15 |  66 | 93.1%| 229.35 | | L36 |  950 |  849 |  15 |  86 | 90.9%| 305.37 |
   | L13 |  950 |  863 |  14 |  73 | 92.3%| 145.48 | | L37 |  950 |  871 |  12 |  67 | 92.9%| 159.79 |
   | L14 |  950 |  844 |  27 |  79 | 91.7%| 252.08 | | L38 |  950 |  875 |   6 |  69 | 92.7%| 246.26 |
   | L15 |  950 |  853 |  14 |  83 | 91.3%| 250.02 | | L39 |  950 |  863 |  11 |  76 | 92.0%| 270.70 |
   | L16 |  950 |  868 |  10 |  72 | 92.4%| 180.47 | | L40 |  950 |  848 |  11 |  91 | 90.4%| 281.98 |
   | L17 |  950 |  868 |  11 |  71 | 92.5%| 216.19 | | L41 |  950 |  849 |  12 |  89 | 90.6%| 152.69 |
   | L18 |  950 |  863 |  17 |  70 | 92.6%| 206.79 | | L42 |  950 |  824 |  14 | 112 | 88.2%| 289.53 |
   | L19 |  950 |  875 |   7 |  68 | 92.8%| 151.25 | | L43 |  950 |  858 |  13 |  79 | 91.7%| 200.22 |
   | L20 |  950 |  838 |  21 |  91 | 90.4%| 200.22 | | L44 |  950 |  848 |  14 |  88 | 90.7%| 165.65 |
   | L21 |  950 |  827 |  21 | 102 | 89.3%| 407.93 | | L45 |  950 |  823 |  28 |  99 | 89.6%| 270.80 |
   | L22 |  950 |  883 |  10 |  57 | 94.0%| 210.55 | | L46 |  950 |  877 |   7 |  66 | 93.1%| 243.43 |
   | L23 |  950 |  871 |  14 |  65 | 93.2%| 144.04 | | L47 |  950 |  851 |  12 |  87 | 90.8%| 261.30 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 15706.04 MB (Load=4614.69 | Prefill=5963.42 | Warmup=0.00 | Decode=5127.92 MB)
   SSD Data/Token (Decode)      : Avg=165.417 MB/tok (Min=111.517 | P50=149.798 | P95=230.849 | Max=232.338 MB) | Prefill=93.178 MB/tok
   NVMe Batches / Requests      : 1506 Batches | 22917 Raw -> 22142 Merged (775 LBA Merges, Avg 726.4 KB/io)
   SSD I/O Size Histogram       : <64K=1835 | 64K-512K=5562 | 512K-2M=14311 | >2M=434
   SSD Read Bandwidth (Active)  : Min=4.80 | Avg=291.48 | Peak=5168.37 MB/s | WallAmort=230.89 MB/s
   OS Kernel I/O Verification   : Read=15726.01 MB | Write=0.00 MB | Syscalls=31645
   Sync Stall vs Async DMA      : SyncStall=25391.39 ms | AsyncOverlapped=34997.93 ms (58.0% Overlapped)
   RAM Traffic & Active BW      : 392.99 GB moved | Active=10.57 GB/s | WallAmort=5.78 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=45.47s (66.8%, 5963.42 MB SSD) | Decode=22.55s (33.2%, 5127.92 MB SSD)
   CPU Time & Utilization       : User=116.656s + Sys=8.938s (Wall=94.506s) | SysUtil=33.2% | ThrUtil=33.2% | 30.73 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM :  19583.11 ms (206138.0 us/tok | 28.79%)
   MoE AVX2 Q8 Expert Compute   :  16378.86 ms (172409.1 us/tok | 24.08%)
   Router + Lookahead Dispatch  :   1023.44 ms (10773.1 us/tok |  1.50%)
   LM Head Output Projection    :   1225.55 ms (12900.5 us/tok |  1.80%)
   Foreground NVMe Sync Stall   :  25391.39 ms (267277.8 us/tok | 37.33%)
   Unaccounted / OMP & Sampling :   4422.45 ms (46552.1 us/tok |  6.50%) | Total Wall=68024.81 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    80.21%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     4.69%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     9.05%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     4.25%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.80%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `06_qwen38_stage2_512_warmup.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=7773.68 MB (3746 slots)
[Apex-Prompt] Input (512 tokens): "[512-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/512 tok | Chunk=2.28 tps | Avg=2.28 tps | Hit=95.4% | NVMe=241.9 MB/s (13785.34 MB, QD=64) | RSS=13712.8 MB
[LIVE-PREFILL] 512/512 tok | Chunk=2.80 tps | Avg=2.52 tps | Hit=96.7% | NVMe=242.0 MB/s (17920.18 MB, QD=64) | RSS=13714.3 MB
[LIVE-DECODE] 2/128 tok | Avg=1.10 tps | Hit=96.7% (LA:+0.0%) | NVMe=243.7 MB/s (18327.46 MB) | RSS=13710.8 MB
[LIVE-DECODE] 8/128 tok | Avg=1.49 tps | Hit=96.7% (LA:+0.1%) | NVMe=254.1 MB/s (19341.41 MB) | RSS=13710.2 MB
[LIVE-DECODE] 16/128 tok | Avg=1.38 tps | Hit=96.8% (LA:+0.1%) | NVMe=262.7 MB/s (20862.08 MB) | RSS=13621.8 MB
[LIVE-DECODE] 24/128 tok | Avg=1.45 tps | Hit=96.8% (LA:+0.2%) | NVMe=274.5 MB/s (22185.64 MB) | RSS=13606.4 MB
[LIVE-DECODE] 32/128 tok | Avg=1.52 tps | Hit=96.9% (LA:+0.3%) | NVMe=285.2 MB/s (23296.59 MB) | RSS=13606.1 MB
[LIVE-DECODE] 40/128 tok | Avg=1.54 tps | Hit=96.9% (LA:+0.3%) | NVMe=296.1 MB/s (24511.24 MB) | RSS=13584.9 MB
[LIVE-DECODE] 48/128 tok | Avg=1.57 tps | Hit=97.0% (LA:+0.3%) | NVMe=306.6 MB/s (25649.77 MB) | RSS=13584.9 MB
[LIVE-DECODE] 56/128 tok | Avg=1.60 tps | Hit=97.0% (LA:+0.3%) | NVMe=317.5 MB/s (26781.41 MB) | RSS=13584.8 MB
[LIVE-DECODE] 64/128 tok | Avg=1.61 tps | Hit=97.0% (LA:+0.4%) | NVMe=326.7 MB/s (27825.03 MB) | RSS=13584.8 MB
[LIVE-DECODE] 72/128 tok | Avg=1.62 tps | Hit=97.1% (LA:+0.4%) | NVMe=336.5 MB/s (28929.25 MB) | RSS=13584.8 MB
[LIVE-DECODE] 80/128 tok | Avg=1.64 tps | Hit=97.1% (LA:+0.4%) | NVMe=347.2 MB/s (30109.80 MB) | RSS=13584.8 MB
[LIVE-DECODE] 88/128 tok | Avg=1.65 tps | Hit=97.2% (LA:+0.4%) | NVMe=356.8 MB/s (31221.41 MB) | RSS=13580.7 MB
[LIVE-DECODE] 96/128 tok | Avg=1.65 tps | Hit=97.2% (LA:+0.4%) | NVMe=366.3 MB/s (32331.28 MB) | RSS=13580.7 MB
[LIVE-DECODE] 104/128 tok | Avg=1.66 tps | Hit=97.2% (LA:+0.5%) | NVMe=376.0 MB/s (33469.87 MB) | RSS=13580.7 MB
[LIVE-DECODE] 112/128 tok | Avg=1.67 tps | Hit=97.3% (LA:+0.5%) | NVMe=385.9 MB/s (34655.95 MB) | RSS=13580.7 MB
[LIVE-DECODE] 120/128 tok | Avg=1.67 tps | Hit=97.3% (LA:+0.5%) | NVMe=395.4 MB/s (35831.15 MB) | RSS=13581.3 MB
[LIVE-DECODE] 127/128 tok | Avg=1.68 tps | Hit=97.3% (LA:+0.5%) | NVMe=403.2 MB/s (36794.59 MB) | RSS=13581.3 MB

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
   LRFU Cache / Staging Ring    : 7773.68 MB (3746/25088 exp = 14.93% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.73 MB | End=13581.27 MB | Peak=14148.64 MB
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
   |    1 |      17 | 2              |   11.64 |   9.2% |      18 |   11.26 | 203453.54 |  0 |  0 |  0 |     0.0 |
   |    2 |      17 | 2              |   10.56 |   7.0% |      16 |    9.87 |  909.48 |899 | 50 | 11 | 208528.5 |
   |    3 |      17 | 2              |   11.11 |  10.8% |      18 |   10.99 |  909.48 |  0 |  0 |  0 | 208528.5 |
   |    4 |      17 | 2              |   11.51 |  15.9% |      22 |   10.88 |  638.08 |449 | 31 |  0 | 199468.0 |
   |    5 |      17 | 2              |    9.67 |   3.5% |      16 |    9.10 |  581.02 |469 | 11 |  0 | 162718.0 |
   |    6 |      17 | 2              |   11.31 |  11.8% |      18 |   11.07 |  556.91 |473 |  7 |  0 | 160593.0 |
   |    7 |      17 | 2              |   10.93 |   8.5% |      18 |   10.14 |  576.55 |466 | 13 |  1 | 158743.0 |
   |    8 |      17 | 2              |   11.36 |  11.1% |      18 |   11.13 |  563.95 |468 | 12 |  0 | 172443.0 |
   |   14 |      90 | {              |    7.71 |   0.7% |      64 |    7.56 |  981.80 |448 | 25 |  7 | 197939.0 |
   |   15 |     198 | \n             |    8.95 |   2.8% |      16 |    7.61 |  946.60 |435 | 35 | 10 | 217564.0 |
   |   13 |     286 | ing            |    8.50 |   1.4% |      68 |    7.85 |  925.89 |435 | 34 | 11 | 201618.0 |
   |   16 |      17 | 2              |    8.90 |   1.7% |     286 |    8.88 |  763.62 |434 | 41 |  5 | 200639.0 |
   |  125 |      17 | 2              |   11.67 |  19.1% |      18 |   10.97 |  562.39 |472 |  8 |  0 | 129139.0 |
   |  126 |      17 | 2              |   12.31 |  21.8% |     198 |   11.75 |  567.11 |469 | 11 |  0 | 143064.0 |
   |  127 |      17 | 2              |   10.79 |  11.3% |      16 |   10.64 |  551.52 |478 |  2 |  0 | 127793.0 |
   |  128 |      17 | 2              |   12.08 |  19.1% |      18 |   11.55 |  556.73 |475 |  5 |  0 | 152568.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (512 tok, 203.454s, TTFT=203453.54ms): Avg=2.52 | Min=2.28 | Max=2.80 tps
   Prefill Chunks (2): C1:256t/2.3tps/95% | C2:256t/2.8tps/97%
   Decode  (127 tok, 75.740s): Avg=1.68 | Min=1.02 | Max=1.82 tps
   Latency (ms) : Min=549.78 | P10=556.73 | P25=561.54 | P50=573.63 | P75=596.70 | P90=652.96 | P95=677.04 | P99=946.60 | Max=981.80
   Mean/SD/Jitt : Mean=596.38ms | StdDev=75.73ms | Jitter=27.75ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/127
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (306720): RawRAM=297008 (96.83%) | Lookahead=1520 (+0.50%) | ColdMiss=8192 (2.67%) | EFF HIT=97.33%
   Lookahead    : 11424 prefetched -> 1530 consumed (13.4% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 96.8% | @64= 97.0% | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 | 6390 | 5713 | 136 | 541 | 91.5%|1140.45 | | L24 | 6390 | 6289 |   3 |  98 | 98.5%| 221.83 |
   | L01 | 6390 | 6128 |  72 | 190 | 97.0%|1497.88 | | L25 | 6390 | 6293 |   7 |  90 | 98.6%| 231.23 |
   | L02 | 6390 | 6138 |  21 | 231 | 96.4%|1561.60 | | L26 | 6390 | 6162 |  49 | 179 | 97.2%| 524.49 |
   | L03 | 6390 | 6316 |   1 |  73 | 98.9%|2229.54 | | L27 | 6390 | 6254 |  20 | 116 | 98.2%| 479.37 |
   | L04 | 6390 | 6276 |   3 | 111 | 98.3%| 676.51 | | L28 | 6390 | 6134 |  49 | 207 | 96.8%| 699.32 |
   | L05 | 6390 | 6233 |  16 | 141 | 97.8%|1146.73 | | L29 | 6390 | 6186 |  38 | 166 | 97.4%| 515.67 |
   | L06 | 6390 | 6250 |  18 | 122 | 98.1%| 656.08 | | L30 | 6390 | 6097 |  59 | 234 | 96.3%| 553.12 |
   | L07 | 6390 | 6242 |  11 | 137 | 97.9%| 528.96 | | L31 | 6390 | 6117 |  60 | 213 | 96.7%| 594.90 |
   | L08 | 6390 | 6319 |   3 |  68 | 98.9%| 250.27 | | L32 | 6390 | 6185 |  36 | 169 | 97.4%| 746.31 |
   | L09 | 6390 | 6318 |   4 |  68 | 98.9%| 107.08 | | L33 | 6390 | 6137 |  54 | 199 | 96.9%| 472.46 |
   | L10 | 6390 | 6284 |   5 | 101 | 98.4%| 174.32 | | L34 | 6390 | 6044 |  84 | 262 | 95.9%| 639.55 |
   | L11 | 6390 | 6321 |   2 |  67 | 99.0%| 180.54 | | L35 | 6390 | 6198 |  33 | 159 | 97.5%| 452.29 |
   | L12 | 6390 | 6277 |   5 | 108 | 98.3%| 629.76 | | L36 | 6390 | 6197 |  31 | 162 | 97.5%| 471.02 |
   | L13 | 6390 | 6237 |  24 | 129 | 98.0%| 252.08 | | L37 | 6390 | 6166 |  34 | 190 | 97.0%| 513.21 |
   | L14 | 6390 | 6222 |  39 | 129 | 98.0%| 623.71 | | L38 | 6390 | 6240 |  16 | 134 | 97.9%| 697.44 |
   | L15 | 6390 | 6186 |  36 | 168 | 97.4%| 565.84 | | L39 | 6390 | 6196 |  26 | 168 | 97.4%| 924.90 |
   | L16 | 6390 | 6190 |  17 | 183 | 97.1%| 485.01 | | L40 | 6390 | 6184 |  36 | 170 | 97.3%| 866.63 |
   | L17 | 6390 | 6174 |  18 | 198 | 96.9%| 603.44 | | L41 | 6390 | 6210 |  12 | 168 | 97.4%| 384.59 |
   | L18 | 6390 | 6173 |  31 | 186 | 97.1%| 565.84 | | L42 | 6390 | 6059 |  82 | 249 | 96.1%| 728.86 |
   | L19 | 6390 | 6220 |  15 | 155 | 97.6%| 329.86 | | L43 | 6390 | 6107 |  40 | 243 | 96.2%| 816.72 |
   | L20 | 6390 | 6124 |  29 | 237 | 96.3%| 882.98 | | L44 | 6390 | 6069 |  60 | 261 | 95.9%| 792.24 |
   | L21 | 6390 | 6144 |  33 | 213 | 96.7%|1315.92 | | L45 | 6390 | 6048 |  84 | 258 | 96.0%| 939.16 |
   | L22 | 6390 | 6284 |   4 | 102 | 98.4%| 419.21 | | L46 | 6390 | 6264 |  14 | 112 | 98.2%| 849.85 |
   | L23 | 6390 | 6199 |  30 | 161 | 97.5%| 616.50 | | L47 | 6390 | 6204 |  20 | 166 | 97.4%| 533.89 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 36794.59 MB (Load=4614.69 | Prefill=13305.49 | Warmup=0.00 | Decode=18874.41 MB)
   SSD Data/Token (Decode)      : Avg=148.617 MB/tok (Min=79.311 | P50=145.550 | P95=190.028 | Max=212.465 MB) | Prefill=25.987 MB/tok
   NVMe Batches / Requests      : 5285 Batches | 70180 Raw -> 68322 Merged (1858 LBA Merges, Avg 551.5 KB/io)
   SSD I/O Size Histogram       : <64K=10481 | 64K-512K=15800 | 512K-2M=41593 | >2M=448
   SSD Read Bandwidth (Active)  : Min=4.71 | Avg=403.20 | Peak=5180.88 MB/s | WallAmort=131.79 MB/s
   OS Kernel I/O Verification   : Read=36814.72 MB | Write=0.00 MB | Syscalls=77838
   Sync Stall vs Async DMA      : SyncStall=55132.81 ms | AsyncOverlapped=72319.82 ms (56.7% Overlapped)
   RAM Traffic & Active BW      : 2226.07 GB moved | Active=10.56 GB/s | WallAmort=7.97 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=203.45s (72.9%, 13305.49 MB SSD) | Decode=75.74s (27.1%, 18874.41 MB SSD)
   CPU Time & Utilization       : User=732.281s + Sys=27.219s (Wall=305.593s) | SysUtil=62.1% | ThrUtil=62.1% | 57.47 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 109454.19 ms (171289.8 us/tok | 39.20%)
   MoE AVX2 Q8 Expert Compute   :  96734.07 ms (151383.5 us/tok | 34.65%)
   Router + Lookahead Dispatch  :   6115.45 ms ( 9570.3 us/tok |  2.19%)
   LM Head Output Projection    :   4579.87 ms ( 7167.2 us/tok |  1.64%)
   Foreground NVMe Sync Stall   :  55132.81 ms (86279.8 us/tok | 19.75%)
   Unaccounted / OMP & Sampling :   7177.15 ms (11231.8 us/tok |  2.57%) | Total Wall=279193.54 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    87.28%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     2.11%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     3.48%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     5.01%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     2.12%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `07_qwen38_stage3_openai_stress.log`
```text
[Stage 3] /v1/models: {"object": "list", "data": [{"id": "qwen-3.8-flash-next-ud-iq2_xs", "object": "model", "created": 1770000000, "owned_by": "apex-inference-v1", "architecture": "qwen4exp (Qwen-3.8-Flash-Next)"}]}
[Stage 3] /v1/chat/completions (stream=false) 33116.9ms | usage={'prompt_tokens': 18, 'completion_tokens': 16, 'total_tokens': 34} | text='\nu\n\n\nb2\n\n2\n\nu\n22'
[Stage 3] /v1/chat/completions (stream=true SSE) 7098.3ms | chunks=3 | DONE=True
[Stage 3] Tool Call Response: finish_reason=tool_calls | fn=get_nvme_telemetry
[Stage 3] Full OpenAI + llama.cpp API parity (/responses, /completions, /tokenize, /detokenize, /props) PASSED!
```

### 📄 `08_qwen38_stage4_2048_mtp_ab.log`
```text
[Apex-Init] Model Loaded: Qwen3.8 Flash Next | Layers=48 | Hidden=2560 | Experts=512 (Top-10) | Pinned Trunk=4614.77 MB | Expert Cache=6736.08 MB (3246 slots)
[Apex-Prompt] Input (2048 tokens): "[2048-Token Technical Systems Prompt] In high-throughput Mixture-of-Experts (MoE) language model inference with NVMe SSD weight offloading, achieving low-latency token generation requires overlapping PCIe Gen3/Gen4 DMA transfers with AVX2+FMA matrix-vector compute on pinned dense attention and recurrent linear state trunks. By combining a Window-LRFU frequency-aware expert cache in locked system RAM with dual-horizon router lookahead and empirical Markov co-activation prefetching, over 80% of expert activations are served directly from RAM without stalling the CPU execution pipeline. During prefill of long 2048-token contexts, layer-wise inverted expert routing tables group all tokens routed to each unique expert into a single coalesced LBA-sorted QD32 NVMe read and register-blocked multi-row AVX2 Q8_K GEMM pass. Explain why this architecture eliminates PCIe read amplification and derive the asymptotic decode throughput."
[LIVE-PREFILL] 256/2048 tok | Chunk=2.31 tps | Avg=2.31 tps | Hit=95.4% | NVMe=242.9 MB/s (13785.34 MB, QD=64) | RSS=12696.1 MB
[LIVE-PREFILL] 512/2048 tok | Chunk=2.76 tps | Avg=2.51 tps | Hit=96.5% | NVMe=247.3 MB/s (18878.21 MB, QD=64) | RSS=12712.6 MB
[LIVE-PREFILL] 768/2048 tok | Chunk=2.84 tps | Avg=2.61 tps | Hit=96.8% | NVMe=256.4 MB/s (23644.17 MB, QD=64) | RSS=12711.5 MB
[LIVE-PREFILL] 1024/2048 tok | Chunk=2.83 tps | Avg=2.66 tps | Hit=97.0% | NVMe=264.4 MB/s (28400.75 MB, QD=64) | RSS=12721.2 MB
[LIVE-PREFILL] 1280/2048 tok | Chunk=2.82 tps | Avg=2.69 tps | Hit=97.2% | NVMe=271.0 MB/s (33089.62 MB, QD=64) | RSS=12721.1 MB
[LIVE-PREFILL] 1536/2048 tok | Chunk=2.82 tps | Avg=2.71 tps | Hit=97.3% | NVMe=276.5 MB/s (37768.73 MB, QD=64) | RSS=12720.5 MB
[LIVE-PREFILL] 1792/2048 tok | Chunk=2.76 tps | Avg=2.72 tps | Hit=97.3% | NVMe=279.9 MB/s (42475.39 MB, QD=64) | RSS=12720.4 MB
[LIVE-PREFILL] 2048/2048 tok | Chunk=2.76 tps | Avg=2.72 tps | Hit=97.4% | NVMe=283.0 MB/s (47007.18 MB, QD=64) | RSS=12704.3 MB
[LIVE-DECODE] 2/64 tok | Avg=0.94 tps | Hit=97.4% (LA:+0.0%) | NVMe=284.1 MB/s (47571.66 MB) | RSS=12705.2 MB
[LIVE-DECODE] 8/64 tok | Avg=1.18 tps | Hit=97.4% (LA:+0.0%) | NVMe=287.9 MB/s (48883.28 MB) | RSS=12705.2 MB
[LIVE-DECODE] 16/64 tok | Avg=1.32 tps | Hit=97.4% (LA:+0.1%) | NVMe=294.7 MB/s (50537.65 MB) | RSS=12705.2 MB
[LIVE-DECODE] 24/64 tok | Avg=1.39 tps | Hit=97.4% (LA:+0.1%) | NVMe=301.6 MB/s (52053.16 MB) | RSS=12705.2 MB
[LIVE-DECODE] 32/64 tok | Avg=1.44 tps | Hit=97.4% (LA:+0.1%) | NVMe=308.4 MB/s (53510.06 MB) | RSS=12701.4 MB
[LIVE-DECODE] 40/64 tok | Avg=1.48 tps | Hit=97.4% (LA:+0.1%) | NVMe=314.6 MB/s (54850.17 MB) | RSS=12701.4 MB
[LIVE-DECODE] 48/64 tok | Avg=1.49 tps | Hit=97.4% (LA:+0.1%) | NVMe=321.4 MB/s (56460.99 MB) | RSS=12701.3 MB
[LIVE-DECODE] 56/64 tok | Avg=1.48 tps | Hit=97.4% (LA:+0.2%) | NVMe=327.6 MB/s (58206.49 MB) | RSS=12701.3 MB
[LIVE-DECODE] 63/64 tok | Avg=1.49 tps | Hit=97.4% (LA:+0.2%) | NVMe=333.4 MB/s (59578.15 MB) | RSS=12701.3 MB

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
   LRFU Cache / Staging Ring    : 6736.08 MB (3246/25088 exp = 12.94% pinned) | Staging=132.81 MB
   Process RSS (Start/End/Peak) : Start=4.75 MB | End=12701.29 MB | Peak=13113.93 MB
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
   |    1 |     198 | \n             |    7.38 |   0.7% |      17 |    7.24 | 751717.74 |  0 |  0 |  0 |     0.0 |
   |    2 |     198 | \n             |    8.16 |   1.8% |      17 |    8.01 | 1063.26 |817 |120 | 23 | 289018.0 |
   |    3 |     198 | \n             |   11.22 |  32.9% |      16 |    8.68 | 1063.26 |  0 |  0 |  0 | 289018.0 |
   |    4 |      84 | u              |    8.57 |   2.2% |     198 |    8.18 |  741.55 |429 | 49 |  2 | 203793.0 |
   |    5 |      17 | 2              |    8.16 |   0.8% |      18 |    8.11 |  804.27 |438 | 34 |  8 | 236339.0 |
   |    6 |      16 | 1              |    9.33 |   2.9% |      64 |    9.01 |  772.31 |444 | 34 |  2 | 203564.0 |
   |    7 |     198 | \n             |   10.64 |  10.7% |      16 |   10.09 |  815.48 |421 | 56 |  3 | 239547.0 |
   |    8 |     220 |                |   13.43 |  30.8% |     198 |   12.44 |  758.94 |427 | 47 |  6 | 222514.0 |
   |   52 |      17 | 2              |   11.57 |  14.9% |      16 |   11.54 |  839.35 |415 | 59 |  6 | 260393.0 |
   |    9 |      17 | 2              |   10.57 |   7.3% |      16 |   10.29 |  762.02 |427 | 50 |  3 | 237339.0 |
   |   12 |      16 | 1              |   10.11 |  11.2% |      17 |    9.56 |  756.14 |423 | 53 |  4 | 234739.0 |
   |   57 |      16 | 1              |    9.58 |   2.9% |      17 |    8.84 |  725.17 |424 | 50 |  6 | 260539.0 |
   |   61 |      17 | 2              |   10.66 |  13.6% |      16 |   10.09 |  630.17 |461 | 19 |  0 | 194689.0 |
   |   62 |      16 | 1              |    9.62 |   7.7% |      17 |    9.40 |  608.34 |470 |  8 |  2 | 164639.0 |
   |   63 |      16 | 1              |   11.23 |   5.0% |      17 |   11.07 |  608.39 |467 | 13 |  0 | 188439.0 |
   |   64 |      17 | 2              |   11.22 |   9.4% |      18 |    9.84 |  605.97 |458 | 22 |  0 | 207193.0 |
   +------+---------+----------------+---------+--------+---------+---------+---------+----+----+----+---------+
--------------------------------------------------------------------------------
 [5. Prefill & Decode Throughput (TPS), TTFT & 12-Point Latency Distribution]
   Prefill (2048 tok, 751.718s, TTFT=751717.74ms): Avg=2.72 | Min=2.31 | Max=2.84 tps
   Prefill Chunks (8): C1:256t/2.3tps/95% | C2:256t/2.8tps/96% | C3:256t/2.8tps/97% | C4:256t/2.8tps/97%
                       C5:256t/2.8tps/97% | C6:256t/2.8tps/97% | C7:256t/2.8tps/97% | C8:256t/2.8tps/97%
   Decode  (63 tok, 42.144s): Avg=1.49 | Min=0.94 | Max=1.69 tps
   Latency (ms) : Min=591.92 | P10=604.74 | P25=614.64 | P50=634.42 | P75=690.25 | P90=762.02 | P95=815.48 | P99=1063.26 | Max=1063.26
   Mean/SD/Jitt : Mean=668.96ms | StdDev=92.02ms | Jitter=38.07ms | Hist(<25/50/100/200/>200ms): 0/0/0/0/63
--------------------------------------------------------------------------------
 [6. Intelligent Window-LRFU Expert Cache, Warmup & Parallel Lookahead]
   Activations (1013280): RawRAM=985469 (97.26%) | Lookahead=1849 (+0.18%) | ColdMiss=25962 (2.56%) | EFF HIT=97.44%
   Lookahead    : 7521 prefetched -> 1859 consumed (24.7% util) | Warmup >=75%:1t, >=85%:1t
   Trajectory   : @16= 97.4% | @64=  N/A | @128=  N/A | @256=  N/A | @512=  N/A
--------------------------------------------------------------------------------
 [7. Complete Per-Layer MoE Expert Cache & NVMe Traffic (All Active Layers)]
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)| | Lyr |  Act |  Raw |  LA |Miss | Eff% | SSD(MB)|
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
   | L00 |21110 |18861 | 200 |2049 | 90.3%|3788.60 | | L24 |21110 |20865 |  13 | 232 | 98.9%| 552.69 |
   | L01 |21110 |20389 | 117 | 604 | 97.1%|1430.64 | | L25 |21110 |20879 |  11 | 220 | 99.0%| 441.77 |
   | L02 |21110 |20404 |  28 | 678 | 96.8%|1795.75 | | L26 |21110 |20481 |  40 | 589 | 97.2%|1334.72 |
   | L03 |21110 |21027 |   3 |  80 | 99.6%| 926.78 | | L27 |21110 |20752 |  26 | 332 | 98.4%| 795.19 |
   | L04 |21110 |20789 |  14 | 307 | 98.5%|1035.52 | | L28 |21110 |20360 |  59 | 691 | 96.7%|1629.86 |
   | L05 |21110 |20707 |  25 | 378 | 98.2%|1195.61 | | L29 |21110 |20547 |  37 | 526 | 97.5%| 913.23 |
   | L06 |21110 |20722 |  40 | 348 | 98.4%| 960.62 | | L30 |21110 |20156 |  52 | 902 | 95.7%|1449.07 |
   | L07 |21110 |20711 |  43 | 356 | 98.3%| 744.58 | | L31 |21110 |20272 |  43 | 795 | 96.2%|1305.03 |
   | L08 |21110 |21035 |   4 |  71 | 99.7%| 178.05 | | L32 |21110 |20485 |  31 | 594 | 97.2%|1370.43 |
   | L09 |21110 |21031 |   2 |  77 | 99.6%| 108.33 | | L33 |21110 |20388 |  23 | 699 | 96.7%|1112.01 |
   | L10 |21110 |20860 |   5 | 245 | 98.8%| 337.43 | | L34 |21110 |20120 |  53 | 937 | 95.6%|1528.30 |
   | L11 |21110 |21034 |   3 |  73 | 99.7%| 159.38 | | L35 |21110 |20546 |  28 | 536 | 97.5%| 895.95 |
   | L12 |21110 |20906 |  11 | 193 | 99.1%| 594.04 | | L36 |21110 |20475 |  44 | 591 | 97.2%|1086.08 |
   | L13 |21110 |20783 |  28 | 299 | 98.6%| 532.96 | | L37 |21110 |20433 |  30 | 647 | 96.9%|1332.84 |
   | L14 |21110 |20676 |  67 | 367 | 98.3%| 872.90 | | L38 |21110 |20670 |  26 | 414 | 98.0%|1180.57 |
   | L15 |21110 |20523 |  74 | 513 | 97.6%|1218.16 | | L39 |21110 |20484 |  37 | 589 | 97.2%|1387.35 |
   | L16 |21110 |20479 |  26 | 605 | 97.1%|1272.68 | | L40 |21110 |20590 |  37 | 483 | 97.7%|1304.64 |
   | L17 |21110 |20299 |  48 | 763 | 96.4%|1656.18 | | L41 |21110 |20587 |  14 | 509 | 97.6%| 838.33 |
   | L18 |21110 |20374 |  36 | 700 | 96.7%|1486.99 | | L42 |21110 |20252 |  67 | 791 | 96.3%|1447.63 |
   | L19 |21110 |20580 |  36 | 494 | 97.7%| 823.93 | | L43 |21110 |20172 |  44 | 894 | 95.8%|1577.27 |
   | L20 |21110 |20216 |  43 | 851 | 96.0%|1486.52 | | L44 |21110 |20163 |  64 | 883 | 95.8%|1528.30 |
   | L21 |21110 |20316 |  65 | 729 | 96.5%|2032.15 | | L45 |21110 |20215 |  73 | 822 | 96.1%|1597.44 |
   | L22 |21110 |20842 |  14 | 254 | 98.8%| 652.32 | | L46 |21110 |20835 |  12 | 263 | 98.8%| 774.95 |
   | L23 |21110 |20466 |  39 | 605 | 97.1%|1148.02 | | L47 |21110 |20712 |  14 | 384 | 98.2%| 956.86 |
   +-----+------+------+-----+-----+------+--------+ +-----+------+------+-----+-----+------+--------+
--------------------------------------------------------------------------------
 [8. NVMe SSD I/O, OS Kernel Verification, RAM Traffic & CPU Utilization]
   I/O Backend                  : Windows 11 Async Overlapped IOCP + Multi-Queue NVMe DMA (QD64)
   Engine SSD Transfer Total    : 59578.15 MB (Load=4614.69 | Prefill=42392.48 | Warmup=0.00 | Decode=12570.98 MB)
   SSD Data/Token (Decode)      : Avg=199.539 MB/tok (Min=150.429 | P50=200.746 | P95=233.933 | Max=282.244 MB) | Prefill=20.699 MB/tok
   NVMe Batches / Requests      : 4103 Batches | 135333 Raw -> 130268 Merged (5065 LBA Merges, Avg 468.3 KB/io)
   SSD I/O Size Histogram       : <64K=33825 | 64K-512K=24544 | 512K-2M=71388 | >2M=511
   SSD Read Bandwidth (Active)  : Min=4.79 | Avg=333.40 | Peak=5151.78 MB/s | WallAmort=75.05 MB/s
   OS Kernel I/O Verification   : Read=59598.69 MB | Write=0.00 MB | Syscalls=139782
   Sync Stall vs Async DMA      : SyncStall=146749.79 ms | AsyncOverlapped=159753.86 ms (52.1% Overlapped)
   RAM Traffic & Active BW      : 5635.43 GB moved | Active=9.09 GB/s | WallAmort=7.10 GB/s
   Stage Breakdown (Pref/Dec)   : Prefill=751.72s (94.7%, 42392.48 MB SSD) | Decode=42.14s (5.3%, 12570.98 MB SSD)
   CPU Time & Utilization       : User=2297.828s + Sys=38.062s (Wall=819.788s) | SysUtil=71.2% | ThrUtil=71.2% | 65.89 GFLOPS
--------------------------------------------------------------------------------
 [9. Kernel Wall-Time Audit (100% of Inference Wall Time Accounted)]
   Dense + Attention/Linear SSM : 312190.31 ms (147887.4 us/tok | 39.33%)
   MoE AVX2 Q8 Expert Compute   : 305735.46 ms (144829.7 us/tok | 38.51%)
   Router + Lookahead Dispatch  :  18224.08 ms ( 8632.9 us/tok |  2.30%)
   LM Head Output Projection    :   2352.94 ms ( 1114.6 us/tok |  0.30%)
   Foreground NVMe Sync Stall   : 146749.79 ms (69516.7 us/tok | 18.49%)
   Unaccounted / OMP & Sampling :   8609.47 ms ( 4078.4 us/tok |  1.08%) | Total Wall=793862.05 ms
--------------------------------------------------------------------------------
 [10. Computer Resource Speed Contribution Breakdown (Sum = 100.00%)]
   +------------------------------------------------------+------------+
   | Subsystem / Architectural Contributor                | Share (%)  |
   +------------------------------------------------------+------------+
   | 1. Domain Expert RAM Cache & Prefill Bulk-Warmup     |    91.55%  |
   | 2. Parallel Async SSD Lookahead (L+1/L+2) Overlap    |     1.17%  |
   | 3. LBA-Coalesced 128KB-1MB Sequential NVMe DMA       |     2.02%  |
   | 4. AVX2+FMA MR=4 IQ2xQ8_K & Single-Barrier OpenMP    |     3.86%  |
   | 5. Pinned Dense Trunk & Zero-Malloc Arena Arch       |     1.40%  |
   +------------------------------------------------------+------------+
   | TOTAL RESOURCE CONTRIBUTION                          |   100.00%  |
   +------------------------------------------------------+------------+
   Basis: Avoided SSD stall ns (Cache/LA) + NVMe DMA ns + Kernel Compute ns + RAM BW ns.
================================================================================
```

### 📄 `09_qwen38_colibri_bench.log`
```text
=== [Colibri-Qwen38] CMD: ./baselines/colibri/c/qwen38.exe 72 2 D:/apex_d_drive/models/qwen38\ref.json (5x cutoff=480.0s) ===
[gguf] MTP head C:\apex_c_drive\models\qwen38\mtp-Qwen3.8-Flash-Next-shared-Q8_0.gguf: 32 tensors
[gguf] D:\apex_d_drive\models\qwen38\Qwen3.8-Flash-Next-UD-IQ2_XS-00001-of-00003.gguf: 3 file(s), 1224 tensors, read in place (native ggml types, no conversion)
== Qwen3.8-Flash-Next native text engine | cache=72/layer | CPU ==
[tok] loaded 248320 base pieces + 33 added tokens (max id 248319) from D:/apex_d_drive/models/qwen38/tokenizer.json
  [COMP-LIVE] Colibri-Qwen38: elapsed=15.0s / cutoff=480.0s
[qwen38] native text weights: prefix=model, 48 layers, PLE=1, cache=72/layer, FP8=native, BF16=native (resident matrices 4.40 GiB)
[qwen38] MTP head mtp.*: wiring b (a norm per stream, fc_hidden per stream), RoPE base 1e+07, 96.86 MiB resident; routed experts Q8_0 from the snapshot (its own GGUF), cache 72 (Q38_MTP_CAP) x 4.98 MiB = 0.35 GiB full
[qwen38] MTP norm weights, mean: embedding -0.7642, hidden -0.3284, mixer 3.7881 (q38_rms0 scales by 1+w; a plain norm's weights would sit near 1)
[qwen38] trunk: 62 matrices int8 on the CPU (0.08 GiB, 0.28 GiB of BF16 released) in 0.3s; Q38_TRUNK_CPU_INT8=0 keeps BF16
[qwen38 MTP] draft vocabulary: the lm_head has no int8 rows on the host, so the head scores the whole vocabulary (Q38_MTP_VOCAB=0 silences this)
[qwen38] routed experts: GGUF IQ2_XXS/IQ2_XXS/IQ4_NL (layer 0), 1.68 MiB per expert; cache 72/layer
[qwen38] trunk: 62 int8 matrices interleaved by 16 for the CPU in 0.03s (Q38_ILV16=0 keeps the rows)
resident weights loaded in 20.5s | RSS after load: 4.60 GB
[qwen38] decode rows' routed experts grouped by expert, one parallel region a layer (Q38_MOE_GROUPED=0: one expert at a time)
  [COMP-LIVE] Colibri-Qwen38: elapsed=30.0s / cutoff=480.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=45.1s / cutoff=480.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=60.1s / cutoff=480.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=75.1s / cutoff=480.0s
  [COMP-LIVE] Colibri-Qwen38: elapsed=90.1s / cutoff=480.0s
TTFT: 42.37 s (time to first token)
[qwen38 MTP] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 82.6% (19/23 drafts) | wiring b | fixed depth, by position: 1 91.7% (11/12) 2 72.7% (8/11) 3 0.0% (0/0)
[qwen38 spec gate] run: T(1) 0.0 ms, rows 2:1.50 3:2.00, rho 0.50, acceptance by position 0.50 0.50 0.50 0.50 0.50
[qwen38 lookup] run: 2.58 tokens/forward (12 forwards per 31 tokens) | acceptance 0.0% (0/0 drafts in 0 verifies) | gate on, 0 declined, 0 probes

PEAK RSS: 10.76 GB
Expert cache hit rate: 62.0% (hit=15849 miss=9733)
Speed: 0.39 tok/s (81.8s for 32 tokens)
[STATS] 48560 selections across 8462 distinct experts -> D:/apex_d_drive/models/qwen38/.coli_usage
  [COMP-LIVE] Colibri-Qwen38: elapsed=105.2s / cutoff=480.0s

Reference: 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 
C engine : 220 248046 198 248045 74455 198 248068 198 760 1156 682 3106 1092 7701 310 381 264 7132 36412 2805 269 82987 886 314 5587 13 6558 728 22903 411 25 271 Text      :  <|im_end|>
<|im_start|>assistant
<think>
The user has sent what appears to be a garbled/corrupted string of characters. Let me analyze this:



Matching tokens: 0/32
=== [Colibri-Qwen38] Finished rc=1 elapsed=106.17s cancelled=False ===
```

### 📄 `12_qwen38_competitor_comparison.log`
```text
================================================================================
 [Stage 5 Summary] QWEN38 Fair Head-to-Head Comparison vs Colibri (4T)
================================================================================
| Engine / Stage | Prefill (tps) | Decode (tps) | P50 (ms) | Eff Hit% | SSD Avg (MB/s) | Peak RSS | Notes |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **Apex v1 (Fair 64p/32g)** | 1.41 | 1.37 | 623.43 | 91.71% | 291.48 | 13414.97 MB | Native GGUF + MTP ON |
| **Apex v1 (512p/128g)** | 2.52 | 1.68 | 573.63 | 97.33% | 403.20 | 14148.64 MB | Native GGUF + MTP ON |
| **Apex v1 (2048p/64g)** | 2.72 | 1.49 | 634.42 | 97.44% | 333.40 | 13113.93 MB | Native GGUF + MTP ON |
| **JustVugg/colibri (64p/32g)** | - | 0.39 | - | 62.0% | - | - | `Q38_MTP=1` / Native |
================================================================================
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
