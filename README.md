# OS_mid
1. OS 是資源分配器、控製程序。資源分配器管理所有資源在有衝突的請求之間做出決定，以提高效率和公平的資源使用；控製程序的執行以防止錯誤和電腦使用不當控製程序。

   

2. (1) 在斷電後儲存的資料還是會消失（被稱為揮發性記憶體）(2) 內存速度比較快

   

3. 中斷通常用於服務硬件計時器、在存儲（例如磁盤 I/O）和通信接口（例如 UART、以太網）之間傳輸數據、處理鍵盤和鼠標事件以及響應任何其他時間敏感事件根據應用系統的要求。

   

4. API（應用程序編程接口）通過 System call 訪問作業系統提供的服務，應用程式回傳訊息。![What is system call interface? - Stack Overflow](https://i.stack.imgur.com/tLg6b.png)

   

5. 模塊化內核是一種內核，其中系統核心的某些部分將分配在稱為模塊的獨立文件中。 這可以在運行時添加到系統中。 它通常需要少量的加載模塊時間。 如果需要一個新模塊，那麼他們就不必重新編譯。

   - Modular Kernel, as name suggests, is a type of kernel in which some parts of system core will get allocated in independent files called modules. This can be added to system at run time. It usually requires small amount of time of load modules. If one needs a new module, then they won’t have to recompile.

     

6. **CPU Bound**意味著進程進行的速率受 CPU 速度的限制。對一小組數字執行計算的任務，例如乘小矩陣，可能會受到 CPU 限制。

   **I/O Bound**是指進程進行的速率受 I/O 子系統速度的限制。處理來自磁盤的數據的任務，例如，計算文件中的行數可能會受到 I/O 限制。

   

7. Process state, Program counter, CPU registers, CPU scheduling information, Memory-management information, Accounting information, I/O status information

![img](https://2.bp.blogspot.com/-ssN5gtdZhDc/VLR8MACu3uI/AAAAAAAAlAQ/YDMxHjh7ti8/s320/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-01-13%2B%E4%B8%8A%E5%8D%889.43.51-48.png)



8. ![Operating Systems: Processes](https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/images/Chapter3/3_12_CommunicationsModels.jpg)



9. (1) 間接通信 (Indirect communication) 中 Messages 是從 mailboxes 定向和接收的（也稱為作為端口）。(2) Indirect communication 不是直接寄給其他 process 而是寄到他家信箱 (also referred to as ports)，每個 mailbox 有一個特殊 id，一次可以連多個 process 但只能寄給一個 process，系統會自動選一個寄，然後告訴寄件者收件者是誰。![Inter process Communication - Message Passing System](https://notesformsc.org/wp-content/uploads/2020/08/Indirect-messaging.png)

   

10. 主要優點：

    - 應答 : 允許程式中的某部份被中斷或是執行得非常久時，該程式仍然可以繼續執行。

    - 資源分享 : 分享 code、data 和 OS 資源

    - 經濟 : 輕量化的 process。(context switch 一個 thread 比 process 快約 5 倍，建立一個 thread 比 process 快約 13 倍。)

    - 可使用多處理器架構 : 使用多核心。![img](https://1.bp.blogspot.com/-bL-KpF-K6KQ/VLaTGYdQzfI/AAAAAAAAlBI/mDU4BnYHGpk/s400/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2014-11-17%2B%E4%B8%8B%E5%8D%888.04.31-17.png)

      


11. challenges include:

    - 劃分活動

    - 平衡

    - 數據拆分

    - 數據依賴

    - 測試和調試

      

14. What's the Thread Libraries？Thread Libraries 為程序員提供了用於創建和管理線程的 API；What's the Thread Cancellation？Thread Cancellation 允許一個線程終止進程中任何其他線程的執行。

15. 虛擬機 (Virtual Machine, VM) 透過軟體模擬的機制，創造一份與底層硬體一模一樣的功能介面。對真正實際的系統而言，VM 上的 OS 只相當於一個執行中的 User Program，開發 OS 時較為安全且方便。 

    優點：

    - 對於 OS 的測試與開發是一個很好的平台工具。 

    - - 因為 VM 是孤立的，所以在OS的開發或測試過程中所引起的不當錯誤，也不會對實體系統造成危害。
      -  測試 OS 可在 VM上執行，而其它 User Program 仍可在其它的 VM 上正常運行不會中止。 

    - VM 具有安全性。 

    - 同一部機器上可執行多套不同的 OS，是實作 time-sharing system 的簡單方法。

16. 分別是：

    1. Scheduling Criteria
       - **CPU utilization**：CPU process exec. / CPU total time，CPU 使用的時間
       - **Throughput**：單位時間內完成的工作數目
       - Turnaround time：完成時間 (完成-到達)，進去process到出來花的時間
       - Waiting time：waiting in the ready queue
       - Response time：自使用者命令交付到系統產生第一個回應所需的時間 (time-sharing system, user-interactive App 特別重視)
    2. Scheduling Algorithm Optimization Criteria
       - 最大 CPU 利用率
       - 最大吞吐量
       - 最短周轉時間
       - 最短等待時間
       - 最短響應時間

17. https://www.studytonight.com/operating-system/priority-scheduling
   <img src="https://1.bp.blogspot.com/-LkPOa9wW8Pg/WZkYxt0_y4I/AAAAAAABVUk/Ve8ci-lOUB0-H-3ycEMIAAMN8wS2JxpMwCLcBGAs/s1600/FCFS.png" alt="img" style="zoom:67%;" /><img src="https://1.bp.blogspot.com/-HH4BeD9I6kw/WZkY54lwEeI/AAAAAAABVUs/hLHNwgYM3y0N2zRM9IgipGtqAHXgE66UQCLcBGAs/s1600/SJF.png" alt="img" style="zoom:67%;" /><img src="https://1.bp.blogspot.com/-eXqYRH_a8OE/WZkZJ2E7WTI/AAAAAAABVUw/L1AQtbGSncERREs_sZCcYPjaNTIrHLGSgCLcBGAs/s1600/RR.png" alt="img" style="zoom: 67%;" />

    

18. In multiple-processor scheduling, what's asymmetric multiprocessing? what's symmetric multiprocessing (SMP)? what's soft processor affinity? what's hard processor affinity?

    1. Asymmetric multiprocessing：只有一個處理器訪問系統數據結構，減少了數據共享的需要
    2. Symmetric multiprocessing：每個處理器都是自調度的，所有進程都在公共就緒隊列中，或者每個都有自己的就緒進程私有隊列
       - 目前最常見的
    3. soft affinity（也稱為 natural affinity）是調度程序試圖盡可能長時間地將進程保持在同一個 CPU 上的趨勢。
    4. hard affinity 使 process 能夠定義它可以在其上執行的處理器子集。

​		




---

Interrupt 的處理流程：![img](https://1.bp.blogspot.com/-fn6v9eTDIkw/WYwN5A3zqLI/AAAAAAABU8o/mHBm_y9_c48k0jXyWVsRGNQwlSsIdeMswCLcBGAs/s1600/MSP430%2BInterrupt%2BExecution.png)

1. 暫停目前 process 執行並保存此 process 當時執行狀況
2. OS 根據 Interrupt ID 查尋 Interrupt vector 並取得 ISR (Interrupt Service Routine) 起始位址
3. ISR 執行
4. 執行完成，恢復先前 process 執行狀況
5. 回到原先中斷前的執行

