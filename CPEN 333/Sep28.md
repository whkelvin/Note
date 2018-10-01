# The Pipeline
- A pipe line provides for sequential data transfer between two processes on a first in first out bases. (FIFO)

- can be unidirectional or bi-directional 

- read operation is destructive (cannot be reread)

- write operation results in the new data being appended to the end of the pipeline where it is held until such time as it is read

- usually a buffer is used when the buffer is full, the data in the buffer is overwritten

## Synchronisation Properties of a Pipeline

- read operation is blocked if pipeline is empty

- write operation is blocked if pipeline is full

- the thread is suspended when any of the above happens

- check data size in buffer before read operation

## Anonymous/Unnamed Pipe
- route the output of one program to the input of another program

## Using a Pipeline
- Create and Open a name/sized pipeline for reading or writing
- Read from pipeline
- Write to pipeline
- Delete the pipeline
- **THE PIPE IS SUSPENDED IF READ/WRITE OPERATION CAN NOT COMPLETE AND THIS COULD CAUSE A RIPPLE EFFECT THAT SUSPEND OTHER PROCESSES (check how much data/space is available to be read or written to/from the pipeline)**

- When the pipeline is deleted or goes **OUT OF SCOPE** the pipeline is destroyed if no other processes is still using the pipeline.

- **DO NOT PUT POINTERS AND OBJECTS IN A PIPELINE**

- read the data in the same order the data is written

## Type Safe Pipeline
- a pipe that only works with one data type

## Mutual Exclusion

##
sizeof (array_name) returns the total size of the array instead of the size of the pointer of the first element

# MailBox (Message Queue)
- Processes/threads can use mailboxes to post message to other processes and/or threads in the system

- Can be sequential and searched

- Grow as # of messages increased

- the message is destroyed when it's read

- only the parents are allowed to post message

- children creates mail boxes 

- DO NOT SHARE MAILBOX BETWEEN PROCESSES

# Inter-Process Communication in a Distributed System

- Sockets (HTTPs...) pipeline that uses internet instead of shared memory
- Remote Procedure Calls (RPC)
- CORBA/COM Programming

## Socket
- UNIX sockets is one of the fundamental technologies upon which the internet is based
- provides a programming interface to facilitate inter-process communication between a client program and a server program

### Using the Socket
 - IP Address of the server that the client wishes to connect with
 - A port number to identify a virtual channel or connection with an application running on that server (some are reserved for communication protocols) 

### Socket Server
1. opens a port
2. listen for incoming requests
3. accepts a client connection
4. begins communication

### Socket Client
1. Create Socket
2. Connect to server 
3. Communicate
4. Close the socket 

## Socket and RPC remote programming call

### COBRA and COM
- communicate with proxy (no ip and port crap)