# File: les/utils/exec_queue.go

在go-ethereum项目中，les/utils/exec_queue.go文件的作用是实现了一个执行队列（Execution Queue），用于按序执行一系列任务。

ExecQueue这几个结构体的作用如下：

1. ExecQueue：执行队列结构体，用于存储任务队列和控制任务执行。
2. Executor：任务执行器结构体，用于存储任务和任务执行状态。

下面对NewExecQueue, loop, waitNext, isClosed, CanQueue, Queue, Clear, Quit这几个函数进行详细介绍：

1. NewExecQueue：创建一个新的执行队列。该函数会返回一个ExecQueue结构体的指针，其中包括了任务队列、锁和信号等相关信息。

2. loop：执行队列的主循环函数，用于不断地从任务队列中获取任务并执行。该函数会一直循环执行，直到被Quit函数中的关闭信号中断。

3. waitNext：等待下一个任务的函数。当任务队列为空时，该函数会使当前协程进行等待。

4. isClosed：判断执行队列是否已关闭。该函数会返回一个布尔值，表示执行队列是否已关闭。

5. CanQueue：判断当前是否可以将任务插入执行队列。该函数会返回一个布尔值，表示是否可以将任务插入执行队列。如果执行队列已关闭或者当前正在执行某个任务，则无法插入新的任务。

6. Queue：将任务插入执行队列中的函数。该函数会将任务添加到任务队列中。

7. Clear：清空执行队列中的所有任务。该函数会移除执行队列中的所有任务。

8. Quit：关闭执行队列的函数。该函数会关闭执行队列，并发送一个关闭信号，以中断执行队列的主循环。

