# Finding complex concurrency bugs

Types of bugs:
- Bugs that manifest themselves as violations of app semantics, like return of incorrect result.
- Latent bugs silently corrupt internal data structures.

The PIKE technique proposes that is possible to implicitly extract 
specification by testing if the application obeys linearizable semantics.
In this sense linearizability means that concurrent requests behave as if they
where executed serially, in some order that is consistent with real-time
ordering of the invocations.

By systematically testing if linearizability is upheld, is possible to find
subtle linearity.

Radomize process execution, and task priority.
The test framework takes the concurrent tasks and serializes the calls.
The test framework intercepts the syscalls at `pthread` level.

