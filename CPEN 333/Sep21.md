# Threads
   - traceable path of sequential programming
   ## Granularity
   - describe the degree of parallelism that exists inside a system


$$System -> Process -> Thread -> Child\:Thread$$

$$No\:Granularity -> Fine\:Granularity$$

   ## Thread Synchronization
   - data dependencies?
   - two threads within the same the process are able to share memories directly

   ## Why Multithreading?
   - increase responsiveness of the program
   (ui thread, network thread...)
   - communication between thread is easier than between processes

# Data Sharing Between Processes
   ## Data Pool (Shared Memory MMF )
      -define a struct in header and include the header when sharing data
      -do not put object in pool (ptr inside class)
      1. Create data pool
      2. Link data pool (return a ptr pointing to where the pool is)
      3. Retrieve/modify data (multiple processes reading/writing at the same time?)
      4. Close data pool
       

