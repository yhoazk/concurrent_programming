# Finding complex concurrency bugs

Types of bugs:
- Bugs that manifest themselves as violations of app semantics, like return of incorrect result.
- Latent bugs silently corrupt internal data structures.

The PIKE technique proposes that is possible to implicitly extract 
specification by testing if the application obeys linearizable semantics.
In this sense linearizability means that concurrent requests behave as if they
where executed serially, in some order that is consistent with real-time
ordering of the invocations and replies to requests.

By systematically testing if linearizability is upheld, is possible to find
subtle violations of the application semantics without having a specification
of the application.

The "caracterization" of the application is accomplished by means of 
annotations 

To address the absence of a spec capturing deviations from the intended
application semantics we propose extracting such a spec 


### Capturing application state

Comparison bit-by-bit will not work due to thread interleaving in different
order, several threads in different order will quickly diverge the result.
For example different order in the memory allocations will lead to different
results.

This problem was addressed by creating a _state summary function_ which
captures an abstract notion of the state taking into consideration the 
semantics of the state allowing logical comparison, instead of low level
physical comparison. This structure should be compared in diff executions in
such way that is not only oblivious to the memory layout, but given the 
different structures which omply ordering, such a list. the state summary 
function must be oblivious to this ordering.

A latent bug is one whose effects are exposed to clients at a significantly
different point from the point where it is triggered.

Radomize process execution, and task priority.
The test framework takes the concurrent tasks and serializes the calls.
The test framework intercepts the syscalls at `pthread` level.

