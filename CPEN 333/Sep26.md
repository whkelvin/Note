# Process Priority and Pre-emptive Scheduling
- all OS assign numerical priorities to processes/threads to indicate their relative importance in the system and also to determine which process/thread should be run at each instant in time
- the priority is generally assigned during its creating, but can also be assigned at run time
- a process with high priority should always be scheduled to run in preference to a process with a lower priority when the process become active

# Priority Inversion
- a low priority task acquired some non-sharable resource by waiting on the mutex protecting that resource
- while a medium priority task that does not required the shared resource gets ran because it has a higher priority than the low priority task
## Solution
- raise the priority of the low priority task (priority inheritance)

# Real Time Scheduling - Rate Monotonic Scheduling (RMS)
- repetitive, periodic tasks at regular fixed time intervals
- statically assigned priority hard real time scheduling algorithm
- shortest deadline has the highest priority

## Period
- time before successive triggering

## Deadline
- time the system has to generate a response
- less than or equal to the period

## Compute Time
- time it takes to perform a certain task

# Harmonic Task Sets
- if the compute time for all the tasks are harmonics, CPU utilisation of 100% will be guaranteed to finish.