# MFQS

Multi-level feedback queue scheduler Q consists of 3 linear queues, i.e., Q1, Q2, and Q3.
- Q1 is round robin with time quantum 8,
- Q2 is round robin with time quantum 16, and
- Q3 follows FIFO
- The process cannot be executed in the lower queue if there are any jobs in all higher
queues. For example, Q1 has 5 processes, Q2 has 1 process, and Q3 has 1 process.
Then, first the process in Q1 should be executed (and completed), and then a
process in Q2 is executed. Finally, Q3 will get CPU resource.
-  A new process enters queue Q1 which is served RR8.
-  When it gains CPU, a process receives 8 milliseconds.
-  If it does not finished in 8 milliseconds, the process is moved to queue Q2.
-  At Q2 process is again served RR16 and receives 16 additional milliseconds.
-  If it still does not complete, it is preempted and moved to queue Q3.
-  At Q3 process is executed by first come first serve.
-  If it still does not complete, it is processed at Q2 until completed.

OUTPUT:
The remaining time of processes in each queue level, total waiting time and total turnaround time are displayed.
![](https://user-images.githubusercontent.com/43548404/103769804-a2cc9900-502d-11eb-8249-2022d45698f7.png)
