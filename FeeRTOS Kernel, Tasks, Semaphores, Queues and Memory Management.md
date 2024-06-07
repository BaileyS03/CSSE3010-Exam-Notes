** RECAP: **
RTOS consists of a kernel which uses realtime scheduling, context switching and resource management.
RTOS provides threads of execution, syncronisation and parameter sharing.
Pre-emptive – tasks can be blocked while waiting for an event occur.

** FreeRTOS Task ** 
Only one task can be executing at any point in time.
The scheduler may start and stop each task (swap each task in and out) as the application executes. 
Each task has its own memory stack (TCB - Task Control Block)

What is a Task Control Block?
It is a block of memory used by the task. It is used to take the Task's: Local Variables, Current values of processor registers, and current task state. 
This is used for context switching; suspending or resuming a task, ensuring that no 'glitches' occur after a context switch, and allowing a task to be suspended or resumed without knowing. 

A task may exist in one of the following states: 
 * Running: When a task is executing it is in the running state and utilising CPU
 * Ready: Tasks that are able to execute but are not currently executing due to another task of equal or higher priority.
 * Blocked: The task is waiting for an event ( i.e., queue, semaphore or vTaskDelay() ). A Blocked state has a timeout after which the task will be unblocked.
 * Suspended: Tasks will only enter or exit this state after vTaskSuspend() and xTaskResume().

FreeRTOS Task State Diagram: 
![FreeRTOS State Diagram](images/FreeRTOS%20state%20diagram.png)

Ready states of equal priorities are scheduled using a time slices round-robin scheduling scheme.

** Critical Sectioning ** 

When one task is in a critical section, no others may be in a critical section. A task in a critical section may be changing common global variables, or accessing hardware peripherals.

** FreeRTOS Idle Task ** 
The idle task is created automatically when the RTOS scheduler is started. This task is used for freeing memory allocated to tasks that have been deleted. Has the lowest priority so that it does not use any CPU time if other higher-priority application tasks are in the ready state. 

** FreeROTS Co-Routine **
Similar to tasks but with two main differences:
* Stack Usage: All co-routines within an application share a single stack, reducing the amount of RAM required.
* Scheduling and priorities: Prioritised cooperative scheduling with respect to other co-routines.

Co-routine states: 
* Running: utilising the CPU
* Ready: Thay are able to be executed but are not currently executing.
* Blocked: Waiting for either a temporal or external event.
State Diagram :
![Co-Routine State Diagram](images/Co-Routine%20State%20Diagram.png)

** Items available in FreeRTOS ** 
