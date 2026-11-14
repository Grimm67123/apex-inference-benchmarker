<!-- APEX_BENCHMARK_LOGS_START -->
# 📊 Latest GitHub Actions Benchmark & Diagnostic Telemetry Logs

- **Workflow Run**: [#35 (Run ID `43602698397`)](https://github.com/Grimm67123/apex-inference-benchmarker/actions/runs/43602698397)
- **Status**: **FAILURE**
- **Timestamp**: `2026-11-14 14:02:36 UTC`

### 🖥️ Consolidated Master Workflow Log (`00_workflow_master.log`)
```text
[2026-11-14T14:01:45.989Z] ================================================================================
[2026-11-14T14:01:46.008Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T14:01:46.010Z] ================================================================================
[2026-11-14T14:01:51.200Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T14:01:51.444Z] --------------------------------------------------------------------------------
[2026-11-14T14:01:51.446Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 30.94 GB / 149.89 GB
[2026-11-14T14:01:51.447Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-14T14:01:51.449Z]  [Disk Telemetry] Total Combined Usable Free Space: 177.95 GB
[2026-11-14T14:01:51.465Z] --------------------------------------------------------------------------------
[2026-11-14T14:01:51.466Z]  [OK] Disk space verification passed: 177.95 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
In file included from C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/immintrin.h:63,
                 from include/apex_common.h:30,
                 from src/apex_avx512.cpp:10:
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h: In function 'float apex_avx512_dot_q8_0_q8(const uint8_t*, const int8_t*, const float*, int)':
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

### 📄 `00_workflow_master.log`
```text
[2026-11-14T14:01:45.989Z] ================================================================================
[2026-11-14T14:01:46.008Z]  [Step 1] Configuring Windows Defender Exclusions & Reclaiming Runner Storage
[2026-11-14T14:01:46.010Z] ================================================================================
[2026-11-14T14:01:51.200Z]  [Step 1] Windows Defender exclusions active on C:\ and D:\.
[2026-11-14T14:01:51.444Z] --------------------------------------------------------------------------------
[2026-11-14T14:01:51.446Z]  [Disk Telemetry] Drive C (C:/apex_c_drive) Free : 30.94 GB / 149.89 GB
[2026-11-14T14:01:51.447Z]  [Disk Telemetry] Drive D (D:/apex_d_drive) Free : 147.01 GB / 150 GB
[2026-11-14T14:01:51.449Z]  [Disk Telemetry] Total Combined Usable Free Space: 177.95 GB
[2026-11-14T14:01:51.465Z] --------------------------------------------------------------------------------
[2026-11-14T14:01:51.466Z]  [OK] Disk space verification passed: 177.95 GB >= 150.00 GB.
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
In file included from C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/immintrin.h:63,
                 from include/apex_common.h:30,
                 from src/apex_avx512.cpp:10:
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h: In function 'float apex_avx512_dot_q8_0_q8(const uint8_t*, const int8_t*, const float*, int)':
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

### 📄 `01_checkout_and_build.log`
```text
================================================================================
 [Step 2] Cloning Private Repository Grimm67123/apex-inference-v1
================================================================================
Cloning into 'Apex-Inference-v1'...
 [Step 2] Compiling Apex Inference v1 (C++17 AVX2+FMA+F16C+OpenMP)...
In file included from C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/immintrin.h:63,
                 from include/apex_common.h:30,
                 from src/apex_avx512.cpp:10:
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h: In function 'float apex_avx512_dot_q8_0_q8(const uint8_t*, const int8_t*, const float*, int)':
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
C:/mingw64/lib/gcc/x86_64-w64-mingw32/15.2.0/include/avx512dqintrin.h:2401:1: error: inlining failed in call to 'always_inline' '__m512 _mm512_insertf32x8(__m512, __m256, int)': target specific option mismatch
 2401 | _mm512_insertf32x8 (__m512 __A, __m256 __B, const int __imm)
      | ^~~~~~~~~~~~~~~~~~
src/apex_avx512.cpp:160:46: note: called from here
  160 |         const __m512 scv = _mm512_insertf32x8(_mm512_castps256_ps512(_mm256_set1_ps(sc0)), _mm256_set1_ps(sc1), 1);
      |                            ~~~~~~~~~~~~~~~~~~^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<!-- APEX_BENCHMARK_LOGS_END -->

# apex-inference-benchmarker
does the runs
