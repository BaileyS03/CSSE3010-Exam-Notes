## Martin Exam Revision  
 * 2023, 2022, 2021 and 2019 are relevant exams (2020 is not relevant) 
 * Format almost the same as the last exam
 * 10 Questions 10 marks per question, a 100 mark exam
 * Key Concepts only, not specific information and CLI is not assessed

Review of information:
> Lecture 1: Focus on debouncing here (not just coding, what it is and how you can get rid of it)

> Lecture 2: ADCs remember what is the advantage of this ADC and what is the disadvantage of this ADC. Think about how they work and what are some of the advantages and shortcomings of these?

> Lecture 4: FSMs and Serial Interfaces. Questions related to what is half-duplex and full-duplex, what does it mean if you have a dedicated clock line and what happens if you are missing these lines?

> Lecture 3: How to encode data and basic maths.

> Lecture 5: Expect questions related to the Chanel Capacity -- Noise, bandwidth, synchronisation (transmitter and reciever)

> Lecture 6: DMA questions, Question 9 or 10

> Lecture 7: Some primitives that might make your life easier, what is a scheduler, what is a pre-emptive scheduler, and basic primitives.
> ** Go over the Queuesets ** There will also be some questions related to Memory Management and there are 4/5 so if there's any question related to memory management if you have heap 1 that does not allow memory freeing; what is the short-comings and what are the advantages.
> What is the advantage of using semaphores, when would we use a queue? How does the scheduler work?

FreeROTS depends on a single timer interrupt to generate a timing tick. The longer he talks about a concept then more likely to ask it. Delta-Sigma is not going to be there. 

FreeRTOS Summary
  Tasks: used as concurrent, sequential programming units. (4 states)
  Co-Routine: Similar to a task but shares a stack amongst their co-routines (3 States)
  Semaphore: Provides synchronization and mutual exclusion (Binary, Counting, and Mutex)
  Queue: Used to provide message passing between tasks
  Software Timer: Causes a function to execute after a period of time.
  
![FreeRTOS State Machine](images/FreeRTOSStateMachine.png)

Memory Management - 4 Heaps only:
Heap 1 does not allow the freeing of memory
Heap 2 Best fit algorithm and allows memory to be freed
Heap 3 implements Malloc and Free

Task Control Block contains: 
  * Microprocessor registers
  * Task state
  * Task variables
  * Stack variables
If a task is suspended the above needs to be saved
Waveform describing pre-emptive and disabled pre-emptive scheduler.

Question 1 is digital interfacing - expect mainly related to lecture 1 (coding questions are totally gone now) [Go to Lecture 1 Page](Digital IO Interfacing.md)
