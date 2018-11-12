# Deadlock and Starvation
- ignorance
- avoidance
- detection and recovery
- prevention

![](http://4.bp.blogspot.com/-jPOKuC9_um4/UmT2z7QBRTI/AAAAAAAABcg/POj2bFhpkLI/s1600/deadlock.jpg)

## Introduction
### Deadlock
- When two processes need two resources to run and each acquires access to one and waits for the other resource to be released by the other process.
- potential for deadlock and actual deadlock

### Conditions Required For Deadlock
- Coffman shows that four conditions must exist for deadlock to occur amongst a set of processes trying to use any set of resources
1. At least one of the resources that the process are trying to acquire must be non-sharable

2. Pre-emption is not possible, that is, once a resource has been given to a process, it cannot be forcibly taken away. (If a resource could be taken away from the process that has acquired it, then it might avoid deadlock but could introduce starvation

3. One process must be holding at least one resource while requesting use of another, held by a second process

4. There exists at the moment deadlock occurs, a circular wait dependency between the processes and resources they are requesting. (circular dependency)

#### solution
- when deadlock happens, have one process give up the resource and come back later

- Grouped the resources into one to prevent deadlock

- kill the processes

##### Four Solution To DeadLock
1. Ignorance
    - let it go (The Ostrich Algorithm)
2. Avoidance (write code in certain way)
    - write code such that all processes access the resources in the same order
    - wait for a timeout and try again later (wait for a time before giving up the resources altogether)
    (might have starvation in second solution)
3. Detection (detect the deadlock and resolve at run time) and Recovery
    - the operation maintaining all the resources and processes to detect deadlock and forcibly take away the resource from one process 
    - mirror of a resource (OS making a copy of the actual resource for processes to access): resources state might change
    - Roll Back Recovery
    - kill the process

4. Prevention (operating system preventing deadlock to happen)
    - NOT THE SAME AS AVOIDANCE
    - relies on operation system to do the work
    - os refuses to give resource at certain time and give only when it's free



 - no guaranteed, could also introduce starvation into the system

