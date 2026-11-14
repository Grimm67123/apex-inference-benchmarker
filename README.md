<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#31 (Run ID `43597877427`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43597877427)
- **Status**: **FAILURE**
- **Timestamp**: `2026-11-14 13:04:45 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T13:04:09.634Z] ================================================================================
[2026-11-14T13:04:09.650Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T13:04:09.653Z] ================================================================================
[2026-11-14T13:04:13.914Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T13:04:14.110Z] --------------------------------------------------------------------------------
[2026-11-14T13:04:14.112Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.12 GB / 149.89 GB
[2026-11-14T13:04:14.114Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-14T13:04:14.115Z]  [Disk Telemetry] Total Combined Usable Free Space: 247.99 GB
[2026-11-14T13:04:14.117Z] --------------------------------------------------------------------------------
[2026-11-14T13:04:14.118Z]  [OK] Disk space verification passed: 247.99 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5239): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x8770): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x9507): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x9565): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xa0ba): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xa783): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xb1a5): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5756): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5bf6): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5c32): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5c72): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5cc1): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccASemTx.o:apex_telemetry.cpp:(.text+0x2d9): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x53db): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x8844): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xab20): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5936): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5d75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5e76): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5e9d): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5ecf): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x88c8): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x951d): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x9578): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x9cba): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xaba0): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xb7fd): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xbee0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xbf41): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x55bb): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x8a44): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xad20): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x5b36): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x5f75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x6076): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x609d): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x60cf): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x8ac8): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x971d): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x9778): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x9eba): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xada0): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xb9fd): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xc0e0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xc141): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x968): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x970): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xa2d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xa35): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xaa8): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xab0): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xb82): undefined reference to `apex_prompt_cache_prepare'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xef0): undefined reference to `apex_spec_record_tokens'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xefe): undefined reference to `apex_prompt_cache_commit'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x10df): undefined reference to `apex_spec_decode_step'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x12bb): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x12cb): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x1315): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x132d): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x64a): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x652): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x145d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x1465): undefined reference to `apex_spec_free'
collect2.exe: error: ld returned 1 exit status
```

### 📄 `00_workflow_master.log`
```text
[2026-11-14T13:04:09.634Z] ================================================================================
[2026-11-14T13:04:09.650Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T13:04:09.653Z] ================================================================================
[2026-11-14T13:04:13.914Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T13:04:14.110Z] --------------------------------------------------------------------------------
[2026-11-14T13:04:14.112Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 28.12 GB / 149.89 GB
[2026-11-14T13:04:14.114Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 219.87 GB / 219.98 GB
[2026-11-14T13:04:14.115Z]  [Disk Telemetry] Total Combined Usable Free Space: 247.99 GB
[2026-11-14T13:04:14.117Z] --------------------------------------------------------------------------------
[2026-11-14T13:04:14.118Z]  [OK] Disk space verification passed: 247.99 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5239): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x8770): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x9507): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x9565): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xa0ba): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xa783): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xb1a5): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5756): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5bf6): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5c32): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5c72): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5cc1): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccASemTx.o:apex_telemetry.cpp:(.text+0x2d9): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x53db): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x8844): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xab20): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5936): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5d75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5e76): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5e9d): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5ecf): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x88c8): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x951d): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x9578): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x9cba): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xaba0): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xb7fd): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xbee0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xbf41): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x55bb): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x8a44): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xad20): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x5b36): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x5f75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x6076): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x609d): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x60cf): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x8ac8): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x971d): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x9778): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x9eba): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xada0): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xb9fd): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xc0e0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xc141): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x968): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x970): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xa2d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xa35): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xaa8): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xab0): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xb82): undefined reference to `apex_prompt_cache_prepare'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xef0): undefined reference to `apex_spec_record_tokens'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xefe): undefined reference to `apex_prompt_cache_commit'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x10df): undefined reference to `apex_spec_decode_step'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x12bb): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x12cb): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x1315): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x132d): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x64a): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x652): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x145d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x1465): undefined reference to `apex_spec_free'
collect2.exe: error: ld returned 1 exit status
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
cc1plus.exe: warning: '-mavx10.1' is aliased to 512 bit since GCC14.3 and GCC15.1 while '-mavx10.1-256' and '-mavx10.1-512' will be deprecated in GCC 16 due to all machines 512 bit vector size supported
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5239): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x8770): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x9507): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x9565): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xa0ba): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xa783): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0xb1a5): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5756): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5bf6): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5c32): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5c72): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccO2IcBg.o:apex_hw_bench.cpp:(.text+0x5cc1): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccASemTx.o:apex_telemetry.cpp:(.text+0x2d9): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x53db): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x8844): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xab20): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5936): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5d75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5e76): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5e9d): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x5ecf): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x88c8): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x951d): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x9578): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0x9cba): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xaba0): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xb7fd): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xbee0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccSahy7D.o:model_glm53_run.cpp:(.text+0xbf41): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x55bb): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x8a44): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xad20): undefined reference to `apex_cpu_has_avx512_vnni'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x5b36): undefined reference to `apex_avx512_dot_f32'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x5f75): undefined reference to `apex_avx512_dot_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x6076): undefined reference to `apex_avx512_dot_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x609d): undefined reference to `apex_avx512_dot_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x60cf): undefined reference to `apex_avx512_dot_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x8ac8): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x971d): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x9778): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0x9eba): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xada0): undefined reference to `apex_avx512_dot2_iq2_xxs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xb9fd): undefined reference to `apex_avx512_dot2_iq2_xs_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xc0e0): undefined reference to `apex_avx512_dot2_bf16'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\cc3BjqcV.o:model_qwen38_run.cpp:(.text+0xc141): undefined reference to `apex_avx512_dot2_q8_0_q8'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x968): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x970): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xa2d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xa35): undefined reference to `apex_spec_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xaa8): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xab0): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xb82): undefined reference to `apex_prompt_cache_prepare'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xef0): undefined reference to `apex_spec_record_tokens'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0xefe): undefined reference to `apex_prompt_cache_commit'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x10df): undefined reference to `apex_spec_decode_step'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x12bb): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x12cb): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x1315): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text+0x132d): undefined reference to `apex_prompt_cache_advance'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x64a): undefined reference to `apex_spec_reset'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x652): undefined reference to `apex_prompt_cache_invalidate_ram'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x145d): undefined reference to `apex_prompt_cache_free'
C:/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/15.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: C:\Users\RUNNER~1\AppData\Local\Temp\ccIcpx66.o:main.cpp:(.text.startup+0x1465): undefined reference to `apex_spec_free'
collect2.exe: error: ld returned 1 exit status
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
