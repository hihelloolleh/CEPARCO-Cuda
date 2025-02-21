[Youtube Link] (https://youtu.be/bXDDBPPE9Ho)
[Colab] (https://colab.research.google.com/drive/1cOsu8Wu5qaSVcEg7zTNYJu8o2hs9gwQq#scrollTo=cbdwazgdzfke)

Shared memory is an operating-system feature that allows database server threads and processes to share data efficiently by providing access to common memory pools. This feature enhances system performance by reducing memory usage and disk I/O while enabling high-speed communication between processes (IBM, 2023). 

## Check if CUDA is present
<img width="1147" alt="Screenshot 2025-02-21 at 9 44 48 PM" src="https://github.com/user-attachments/assets/11c9dd58-db27-409e-972e-99f90cbb711d" />

# Comparative table of execution times

## Avg time for 30 loop
| Language | Trial | --- | 
| --- | --- | --- | 
| c | 1099821.3 ms | <img width="977" alt="Screenshot 2025-02-21 at 6 57 41 PM" src="https://github.com/user-attachments/assets/7ba691e0-dd62-4515-a0fe-eb15bfd5d6c2" /> |
| Cuda w/o shared memory | 12.442811 ms | <img width="984" alt="Screenshot 2025-02-21 at 7 02 49 PM" src="https://github.com/user-attachments/assets/e0ef2b30-d3ce-43ba-99ec-53dc32600a45" /> |
| Cuda w/ shared memory | 11.130256 ms | <img width="1345" alt="Screenshot 2025-02-21 at 7 19 25 PM" src="https://github.com/user-attachments/assets/81dba982-2201-4890-b1c9-fba012c0dcad" /> |
| Cuda C w/ shared memory | 9.512620 ms | <img width="1344" alt="Screenshot 2025-02-21 at 7 09 03 PM" src="https://github.com/user-attachments/assets/eb3c0d84-ac1b-4dc0-87ca-efaf754fd322" /> |
| Cuda C w/o shared memory | 9.852160 ms | <img width="1345" alt="Screenshot 2025-02-21 at 7 11 07 PM" src="https://github.com/user-attachments/assets/2f556c9d-dcda-4612-ad61-64d0d6ed2267" /> |

# Discussion
The table presents the execution times of different implementations of the SAXPY operation, comparing performance between CPU-based execution in C and various CUDA-based implementations leveraging GPU parallelism. The results demonstrate the significant speedup achieved by utilizing CUDA, particularly with shared memory optimization.

## Analysis of Execution Times
  The **C Implementation** records an average execution time of **1,099,821.3 ms**, which is significantly higher than any of the CUDA implementations. This vast difference highlights the limitations of CPU-based execution when handling large vector computations in a sequential manner.

  The execution time for **CUDA without shared memory** is **12.442811 ms**, showcasing a dramatic improvement over the serial C execution. This speedup is attributed to the parallel processing capabilities of the GPU, where multiple threads process vector elements concurrently. On the other hand, the execution time for **CUDA with shared memory** is further reduced to **12.005183 ms**. The marginal improvement indicates that, for this specific operation, global memory access is already optimized, and shared memory does not provide substantial additional benefits.

  For **CUDA C implementation**, using *shared memory* achieves the fastest execution time of **9.512620 ms**. This suggests that optimizations at both the memory access level and computational efficiency have been effectively implemented. **Without the shared memory**, the execution time is **9.852160 ms**, slightly slower than the shared memory variant. This difference indicates that shared memory provides some advantage, but the impact is relatively minor in this particular case.

  The comparative results highlight the superiority of GPU-based execution over traditional CPU processing for vector operations. There are some slight advantages to using shared memory, indicating that global memory access patterns are already effective. Among the tested implementations, CUDA C with shared memory offers the best performance, proving that optimizing both computation and memory access is crucial in high-performance computing applications. The difference in execution times among the CUDA implementations is relatively small. However, when working with significantly larger datasets, these differences may become more pronounced, further emphasizing the need for efficient memory management and computation optimization.
