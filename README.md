# Group-7-Deep-Dive-Cuda

## Group Members
##### 1. CABRERA, JAMES TAN
##### 2. CHEUNG, TSZ MAN
##### 3. CORPUZ, GERALD JUSTINE ESPERA
##### 4. MANAOIS, CHRISCEL JOHN MANZANO

## Project Specifications
<img width="535.5" height="142.5" alt="image" src="https://github.com/user-attachments/assets/84a25eec-9333-4558-bedf-0b1aa0cc068c" />

##### Variants: 

i.) a C/C++ program version 

ii.) a CUDA program version using a grid-stride loop without prefetch and without mem advise 

iii.) a CUDA program version using a grid-stride loop with prefetching but without page creation and without mem advise

iv.) a CUDA program version using a grid-stride loop with prefetch, with page creation but without mem advise 

v.) a CUDA program version using a grid-stride loop with prefetch, with page creation, and with mem advise 

vi.) Classic MemCopy method (no Unified memory) 

vii.) Another CUDA kernel that initializes the data

## AI Usage Declaration

i.) 

ii.) 

iii.)

## 1. Screenshot of the program output with correctness check AND execution time for all cases

##### C screenshot
<img width="1070" height="489" alt="image" src="https://github.com/user-attachments/assets/7e0797db-72d8-4b02-9480-e122d89fe6f0" />

##### CUDA Grid Stride Loop screenshot
<img width="1073" height="575" alt="image" src="https://github.com/user-attachments/assets/ef39a81a-8889-453d-98f3-bf0228c59611" />

##### CUDA Grid Stride Loop nvprof log
<img width="1078" height="313" alt="image" src="https://github.com/user-attachments/assets/b40033e7-2329-4272-9b73-e9e28afe5a5c" />

##### CUDA Grid Stride Loop with Prefetch
<img width="1073" height="327" alt="image" src="https://github.com/user-attachments/assets/bd7fd787-baad-49d8-bb09-b1319d2ceeb5" />

##### CUDA Grid Stride Loop with Prefetch nvprof log
<img width="1076" height="340" alt="image" src="https://github.com/user-attachments/assets/bfe8e8aa-8660-4e80-9441-8bc6b0c03b3d" />

##### CUDA Grid Stride Loop with Prefetch and Page Creation
<img width="1073" height="322" alt="image" src="https://github.com/user-attachments/assets/c0b43496-6446-458c-a5f5-4b57e9332f0e" />

##### CUDA Grid Stride Loop with Prefetch and Page Creation nvprof log
<img width="1076" height="313" alt="image" src="https://github.com/user-attachments/assets/a80f1dcb-244a-4e10-b1ec-4d578679bf13" />

##### CUDA Grid Stride Loop with Prefetch, Page Creation, and Mem Advise
<img width="1077" height="323" alt="image" src="https://github.com/user-attachments/assets/7ff61daa-4bf7-459a-8e12-4075b583b8e3" />

## 2. Screenshot of nSight for all CUDA variants

## 3. Comparative table of execution time (C, CUDA variants, x86-64, XMM, YMM) (see below some guide questions)

***Speedup {Number of blocks/grid = max (as per formula), multiple kernel run}***
Baseline C execution time = ---------------------

| | Kernel time (up to the point necessary data to return to error checking part) (do not time the error checking routine) | Speedup vs baseline C program |
| :--- | :--- | :--- |
| 2^28 elements | | |
| CUDA block size = 1024 | | |
| x86-64 | | |
| x86-64 SIMD XMM | | |
| x86-64 SIMD YMM | | |
| CUDA Unified | | |
| CUDA Prefetch | | |
| CUDA Prefetch+page creation | | |
| CUDA Prefetch+Page creatittion+memadvise | | |
| CUDA classic MEMCPY | | |
| CUDA data init in a CUDA kernel | | |

## 4. Analysis of results
    - Justify your kernel execution time.  
    - Analysis of speed performance across all platforms
    
a.) What overheads are included in the GPU execution time (up to the point where the data is transferred back to the CPU for error checking)? Is it different for each CUDA variant?

b.) How does block size affect execution time (observing various elements and using max blocks)?  Which block size will you recommend?

c) Is prefetching always recommended, or should CUDA manage memory?  Give some use cases in which one is better than the other.

d.) Between SIMD and SIMT, which one is faster? Give some use cases in which one is better than the other.

## 5. Discuss the problems encountered and solutions made, unique methodology used, AHA moments, etc.

## 6. Discuss, based on your experience on the particular project use case, the differences between SIMD and SIMT in handling parallelism.  Include also the PROS and CONS of using SIMD and SIMT in your use case.
