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

## 2. Screenshot of nSight for all CUDA variants

## 3. Comparative table of execution time (C, CUDA variants, x86-64, XMM, YMM) (see below some guide questions)

## 4. Analysis of results
    - Justify your kernel execution time.  
    - Analysis of speed performance across all platforms
    
a.) What overheads are included in the GPU execution time (up to the point where the data is transferred back to the CPU for error checking)? Is it different for each CUDA variant?

b.) How does block size affect execution time (observing various elements and using max blocks)?  Which block size will you recommend?

c) Is prefetching always recommended, or should CUDA manage memory?  Give some use cases in which one is better than the other.

d.) Between SIMD and SIMT, which one is faster? Give some use cases in which one is better than the other.

## 5. Discuss the problems encountered and solutions made, unique methodology used, AHA moments, etc.

## 6. Discuss, based on your experience on the particular project use case, the differences between SIMD and SIMT in handling parallelism.  Include also the PROS and CONS of using SIMD and SIMT in your use case.
