<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#32 (Run ID `43597882632`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43597882632)
- **Status**: **FAILURE**
- **Timestamp**: `2026-11-14 13:04:57 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T13:04:13.255Z] ================================================================================
[2026-11-14T13:04:13.276Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T13:04:13.278Z] ================================================================================
[2026-11-14T13:04:17.867Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T13:04:18.090Z] --------------------------------------------------------------------------------
[2026-11-14T13:04:18.092Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 31 GB / 149.89 GB
[2026-11-14T13:04:18.093Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-14T13:04:18.094Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.01 GB
[2026-11-14T13:04:18.096Z] --------------------------------------------------------------------------------
[2026-11-14T13:04:18.097Z]  [OK] Disk space verification passed: 178.01 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5239): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x87e0): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x957f): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x95dd): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xa134): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xa803): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xb227): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5796): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5c26): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5c62): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5ca2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5cf1): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccBJFac1.o:apex_telemetry.cpp:(.text+0x2d9): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x541b): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x88c4): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xabd0): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5976): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5db5): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5ebb): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5ee2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5f14): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x8948): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x95b5): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x9610): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x9d6a): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xac50): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xb8d5): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xbfb8): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xc019): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x55bb): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x8a84): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xad90): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x5b36): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x5f75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x607b): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x60a2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x60d4): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x8b08): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x9775): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x97d0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x9f2a): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xae10): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xba95): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xc178): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xc1d9): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x9b8): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x9c0): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xa7d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xa85): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xaf8): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xb00): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xbd2): undefined reference to `apex_prompt_cache_prepare'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xf40): undefined reference to `apex_spec_record_tokens'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xf4e): undefined reference to `apex_prompt_cache_commit'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x113f): undefined reference to `apex_spec_decode_step'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x131c): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x132c): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x1375): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x138d): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x67a): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x682): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x14dd): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x14e5): undefined reference to `apex_spec_free'
collect2.exe: error: ld returned 1 exit status
```

### 📄 `00_workflow_master.log`
```text
[2026-11-14T13:04:13.255Z] ================================================================================
[2026-11-14T13:04:13.276Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T13:04:13.278Z] ================================================================================
[2026-11-14T13:04:17.867Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T13:04:18.090Z] --------------------------------------------------------------------------------
[2026-11-14T13:04:18.092Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 31 GB / 149.89 GB
[2026-11-14T13:04:18.093Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-14T13:04:18.094Z]  [Disk Telemetry] Total Combined Usable Free Space: 178.01 GB
[2026-11-14T13:04:18.096Z] --------------------------------------------------------------------------------
[2026-11-14T13:04:18.097Z]  [OK] Disk space verification passed: 178.01 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5239): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x87e0): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x957f): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x95dd): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xa134): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xa803): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xb227): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5796): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5c26): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5c62): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5ca2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5cf1): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccBJFac1.o:apex_telemetry.cpp:(.text+0x2d9): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x541b): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x88c4): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xabd0): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5976): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5db5): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5ebb): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5ee2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5f14): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x8948): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x95b5): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x9610): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x9d6a): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xac50): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xb8d5): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xbfb8): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xc019): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x55bb): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x8a84): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xad90): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x5b36): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x5f75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x607b): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x60a2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x60d4): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x8b08): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x9775): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x97d0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x9f2a): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xae10): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xba95): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xc178): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xc1d9): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x9b8): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x9c0): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xa7d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xa85): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xaf8): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xb00): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xbd2): undefined reference to `apex_prompt_cache_prepare'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xf40): undefined reference to `apex_spec_record_tokens'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xf4e): undefined reference to `apex_prompt_cache_commit'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x113f): undefined reference to `apex_spec_decode_step'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x131c): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x132c): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x1375): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x138d): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x67a): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x682): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x14dd): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x14e5): undefined reference to `apex_spec_free'
collect2.exe: error: ld returned 1 exit status
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5239): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x87e0): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x957f): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x95dd): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xa134): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xa803): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0xb227): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5796): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5c26): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5c62): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5ca2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc7lHGzR.o:apex_hw_bench.cpp:(.text+0x5cf1): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccBJFac1.o:apex_telemetry.cpp:(.text+0x2d9): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x541b): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x88c4): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xabd0): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5976): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5db5): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5ebb): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5ee2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x5f14): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x8948): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x95b5): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x9610): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0x9d6a): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xac50): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xb8d5): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xbfb8): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccqzkwer.o:model_glm53_run.cpp:(.text+0xc019): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x55bb): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x8a84): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xad90): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x5b36): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x5f75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x607b): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x60a2): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x60d4): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x8b08): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x9775): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x97d0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0x9f2a): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xae10): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xba95): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xc178): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cccOvgEj.o:model_qwen38_run.cpp:(.text+0xc1d9): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x9b8): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x9c0): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xa7d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xa85): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xaf8): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xb00): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xbd2): undefined reference to `apex_prompt_cache_prepare'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xf40): undefined reference to `apex_spec_record_tokens'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0xf4e): undefined reference to `apex_prompt_cache_commit'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x113f): undefined reference to `apex_spec_decode_step'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x131c): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x132c): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x1375): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text+0x138d): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x67a): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x682): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x14dd): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccV1L50n.o:main.cpp:(.text.startup+0x14e5): undefined reference to `apex_spec_free'
collect2.exe: error: ld returned 1 exit status
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
