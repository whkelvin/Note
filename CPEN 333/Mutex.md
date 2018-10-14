###  Semaphore
- suspend the thread if the resource is in used
- uses wait() and signal() to acquire and release resource
### Producer and Consumer Problem
- Producer thread produces data for data pool
- Consumer thread consumes data form data pool

- Problems: 
    - producer and consumer access the shared data at the same time
    - producer updates more than once before consumer read the data
    - consumer read twice before producer update

## Single Producer and Single Consumer
- Producer (0 initially busy)
    1. wait for consumer semaphore to release resource (wait for cs to become 1)
    2. produce data
    3. signal producer semaphore (release) ps = 1

- Consumer (1 initially free) 
    1. wait for producer semaphore to release resource (wait for ps to become 1)
    2. consume data
    3. signal consumer semaphore (release) cs = 1


## One Producer, Several Consumers
- Producer
    - must wait for all consumers to consume the data
    1. wait for cs1 and cs2 to become 1
    2. produce data
    3. signal ps1 and ps2

- Consumer1
    1. wait for ps1 to become 1
    2. consume data
    3. signal cs1

- Consumer2 
    1. wait for ps2 to become 1
    2. consume data
    3. signal cs2

## Multiple Producer, One Consumer
- Consumer read producer semaphore value instead of wait for the semaphore value to be 1 (polling)
- Create 2 threads in consumer to read data from each producer

### Counting Semaphore
- when only limited processes can share the same resources
- ->  CSemaphore s("counter", 6, 6);
- ->  CSemaphore s(string name, initial, final)
Resource is free when Semaphore = final
Resource is blocked when Semaphore < final

## Rollercoaster Problem
        Design the synchronisation mechanism for multiple passenger threads plus a rollercoaster thread such that

        - Only 2 passengers can board the rollercoaster
        -The rollercoaster will wait until 2 passenger have boarded
        - Each passenger will wait until they finish the ride before attempting to get off
        - New passengers will wait till the old passengers have got off