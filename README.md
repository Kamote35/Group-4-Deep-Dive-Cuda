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

**Generative AI** has been used to help students further their understanding on CUDA C since the main point of this project is for the learners to "Deep Dive" on CUDA C. Usage of AI tools such as: Chat-GPT, Gemini, and Copilot;includes: Performing error checks on the coding of the various programs (to see if they are being implemented the way the specs intend them to be), Helping students understand which parts of the Nsight Systems timeline are important for analysis and comparison of this project, Creating an outline for the report (README.md).



## 1. Screenshot of the program output with correctness check AND execution time for all cases

##### C screenshot
<img width="1070" height="489" alt="image" src="https://github.com/user-attachments/assets/7e0797db-72d8-4b02-9480-e122d89fe6f0" />

##### x86-64
<img width="1097" height="242" alt="image" src="https://github.com/user-attachments/assets/fcbf106c-4dd0-4d98-ac5b-24ed38357516" />

##### x86-64 SIMD XMM 
<img width="1108" height="242" alt="image" src="https://github.com/user-attachments/assets/34e211b0-45a5-46d4-87f8-814e705edd4e" />

##### x86-64 SIMD YMM 
<img width="1105" height="235" alt="image" src="https://github.com/user-attachments/assets/847f9032-d320-4715-9be1-35127155da7b" />

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
<img width="1074" height="328" alt="image" src="https://github.com/user-attachments/assets/7b85d1b8-7110-4454-b183-9d4a4eb6a0fe" />

##### CUDA Grid Stride Loop with Prefetch, Page Creation, and Mem Advise nvprof log
<img width="1077" height="323" alt="image" src="https://github.com/user-attachments/assets/7ff61daa-4bf7-459a-8e12-4075b583b8e3" />

##### Classic MemCopy method (no Unified memory)
<img width="1067" height="454" alt="image" src="https://github.com/user-attachments/assets/e9418e39-70a1-4b93-90f0-ade06d2cacef" />

##### Classic MemCopy method (no Unified memory) nvprof log
<img width="1077" height="255" alt="image" src="https://github.com/user-attachments/assets/9a69bdcb-e463-4c24-a069-e66447a3292b" />

##### Another CUDA kernel that initializes the data

##### Another CUDA kernel that initializes the data nvprof log

## 2. Screenshot of nSight for all CUDA variants
##### CUDA Mvp2 Nsight (GPU page faults)
<img width="1247" height="410" alt="image" src="https://github.com/user-attachments/assets/4e81a05d-5211-4985-a9d4-fece06c833ae" />

##### CUDA Mvp3 Nsight (Prefetching)
<img width="1248" height="405" alt="image" src="https://github.com/user-attachments/assets/a676c313-0407-4b8b-8bca-a9c17d5e0aef" />

##### CUDA Mvp4 Nsight (Prefetching + Page creation)
<img width="1247" height="410" alt="image" src="https://github.com/user-attachments/assets/0531189f-24b7-4c1e-93a9-0586120d999c" />

##### CUDS Mvp5 Nsight (Prefetch + Page creation + Mem advise)
<img width="1246" height="410" alt="image" src="https://github.com/user-attachments/assets/bd149138-bb1e-4e50-8979-80ccc6a360fa" />

## 3. Comparative table of execution time (C, CUDA variants, x86-64, XMM, YMM) (see below some guide questions)

***Speedup {Number of blocks/grid = max (as per formula), multiple kernel run}***
Baseline C execution time = 2078.384433 ms

| 2^28 elements CUDA (block size = 1024) | Kernel time (up to the point necessary data to return to error checking part) (do not time the error checking routine) | Speedup vs baseline C program |
| :--- | :--- | :--- |
| x86-64 | 287.654 ms | 7.2253 |
| x86-64 SIMD XMM | 86.490 ms | 24.0303 |
| x86-64 SIMD YMM | 63.964 ms | 32.4930 |
| CUDA Unified | 954.2172 ms | 2.1781 |
| CUDA Prefetch | 761.8129 ms | 2.7282 |
| CUDA Prefetch+page creation | 454.08ms | 4.5771 |
| CUDA Prefetch+Page creation+memadvise | 14.4472 ms | 143.8607 |
| CUDA classic MEMCPY | 13.2952 ms | 156.3259 |
| CUDA data init in a CUDA kernel | | |

## 4. Analysis of results

The kernel execution time varies significantly depending on the memory management strategy used. The CUDA Unified Memory version has the longest execution time (954.22 ms) because the GPU performs on-demand page migrations from host to device, causing frequent page faults and stalling execution. When prefetching is applied, the runtime improves to 761.81 ms since data is moved to GPU memory before kernel launch, reducing migration overhead. Adding page creation further lowers the time to 454.08 ms by pre-allocating pages and reducing setup delays. With memory advice (cudaMemAdvise), execution time drops dramatically to 14.45 ms because the GPU can now optimize data placement and access patterns, eliminating most migration and synchronization delays. The classic memcpy approach achieves the fastest time (13.30 ms) since data transfers are explicitly managed and fully reside in GPU global memory before execution, avoiding all Unified Memory overhead. These results show that the kernel is primarily memory-bound, and improving memory handling directly enhances execution efficiency.

Across all platforms, performance improves as memory handling and parallelization become more efficient. On the CPU side, the x86-64 scalar version serves as the baseline (287.65 ms), while SIMD XMM and SIMD YMM versions achieve 86.49 ms and 63.96 ms respectively, showing expected gains from wider vector processing. The CUDA Unified Memory version is initially slower than CPU SIMD implementations due to its heavy page migration overhead. However, as optimizations are added—prefetching, page creation, and memory advice the GPU performance improves drastically, ultimately surpassing all CPU versions. The CUDA Prefetch + Page Creation + Memadvise and Classic memcpy implementations achieve speedups of 143.86× and 156.33× over the baseline, respectively, highlighting the GPU’s superior parallel capability when memory access is efficiently managed. Overall, while Unified Memory simplifies programming, explicit memory management remains essential for maximizing GPU performance, especially for large-scale data processing.
    
a.) What overheads are included in the GPU execution time (up to the point where the data is transferred back to the CPU for error checking)? Is it different for each CUDA variant?

Unified Memory variants include additional runtime migration and management overheads, while explicit memory management isolates computation from data transfer, resulting in the lowest execution overhead and highest performance.

b.) How does block size affect execution time (observing various elements and using max blocks)?  Which block size will you recommend?

Block size affects GPU occupancy and efficiency. If the block size is too small, it underutilizes GPU resources, extending execution times. Increasing it improves parallelism and hides memory latency, reducing runtime. If the blocks are too large, close to 1024 threads can cause register and shared memory pressure, slightly lowering performance. Block size of 512 threads offers the best balance between occupancy and resource use, giving consistently fast execution for large datasets.

c) Is prefetching always recommended, or should CUDA manage memory?  Give some use cases in which one is better than the other.

Prefetching is good for large predictable GPU workloads like matrix multiplication, image processing and simulation. CUDA-managed memory is better for mixed CPU–GPU tasks, adaptive algorithms, or when programming simplicity is more important than peak performance.

d.) Between SIMD and SIMT, which one is faster? Give some use cases in which one is better than the other.

SIMT is generally faster for massively parallel tasks like image processing, deep learning, and scientific simulations. SIMD is better for smaller-scale, low-latency tasks such as signal processing, vector math, or data compression. 

## 5. Discuss the problems encountered and solutions made, unique methodology used, AHA moments, etc.

## 6. Discuss, based on your experience on the particular project use case, the differences between SIMD and SIMT in handling parallelism.  Include also the PROS and CONS of using SIMD and SIMT in your use case.
