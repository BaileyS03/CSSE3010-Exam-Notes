** RECAP: **
RTOS consists of a kernel which uses realtime scheduling, context switching and resource management.
RTOS provides threads of execution, syncronisation and parameter sharing.
Pre-emptive – tasks can be blocked while waiting for an event occur.

** FreeRTOS Task ** 
Only one task can be executing at any point in time.
The scheduler may start and stop each task (swap each task in and out) as the application executes. 
Each task has its own memory stack (TCB - Task Control Block)

What is a Task Control Block ?
It is a block of memory used by the task. It is used to tave the Task's: Local Variables, Current values of processor registers and current task state. 
This is used for context switching; suspend or resume a task, ensure that no 'glitches' occur after a context switch and allows a task to be suspended or resumes without knowing. 

A task may exist in one of the following states: 
 * Running: When a task is executing it is in the running state and utilising CPU
 * Ready: Tasks that are able to execute but are not currently executing due to another task of equal or higher priority.
 * Blocked: The task is waiting for an event ( i.e., queue, semaphore or vTaskDelay() ). A Blocked state has a timeout after which the task will be unblocked.
 * Suspended: Tasks will only enter or exit this state after vTaskSuspend() and xTaskResume().

FreeRTOS Task State Diagram: 
