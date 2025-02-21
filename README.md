#Overview

Shared memory is an operating-system feature that allows database server threads and processes to share data efficiently by providing access to common memory pools. This feature enhances system performance by reducing memory usage and disk I/O while enabling high-speed communication between processes (IBM, 2023). 

# Comparative table of execution times

## Avg time for 30 loop
| Language | Trial | --- | 
| --- | --- | --- | 
| c | 1099821.3 ms | <img width="977" alt="Screenshot 2025-02-21 at 6 57 41 PM" src="https://github.com/user-attachments/assets/7ba691e0-dd62-4515-a0fe-eb15bfd5d6c2" /> |
| Cuda w/o shared memory | 12.442811 ms | <img width="984" alt="Screenshot 2025-02-21 at 7 02 49 PM" src="https://github.com/user-attachments/assets/e0ef2b30-d3ce-43ba-99ec-53dc32600a45" /> |
| Cuda w/ shared memory | 11.130256 ms | <img width="1345" alt="Screenshot 2025-02-21 at 7 19 25 PM" src="https://github.com/user-attachments/assets/81dba982-2201-4890-b1c9-fba012c0dcad" /> |
| Cuda C w/ shared memory | 9.512620 ms | <img width="1344" alt="Screenshot 2025-02-21 at 7 09 03 PM" src="https://github.com/user-attachments/assets/eb3c0d84-ac1b-4dc0-87ca-efaf754fd322" /> |
| Cuda C w/o shared memory | 9.852160 ms | <img width="1345" alt="Screenshot 2025-02-21 at 7 11 07 PM" src="https://github.com/user-attachments/assets/2f556c9d-dcda-4612-ad61-64d0d6ed2267" /> |



